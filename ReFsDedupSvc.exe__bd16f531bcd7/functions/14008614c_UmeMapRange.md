# UmeMapRange

- ea: `0x14008614c`
- end: `0x1400862db`
- name: `UmeMapRange`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140096334`

## callees

- `0x1400057f8`
- `0x140085794`
- `0x14008614c`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400862b2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400862b2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140086202`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140086202`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140086248`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140086248`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140086293`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140086293`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1400861a3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1400861a3`

## pseudocode

```c
__int64 __fastcall UmeMapRange(__int64 a1, __m128i *a2)
{
  __int64 v2; // rax
  __int64 (*v4)(void); // rax
  __m128i v6; // xmm6
  void *v7; // rcx
  DWORD FileSize; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  __m128i v11; // xmm6
  void *v12; // rbp
  void *v13; // rcx
  int v14; // edx
  unsigned __int64 v15; // rsi
  void *v16; // rcx
  __m128i v17; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v18[16]; // [rsp+40h] [rbp-38h] BYREF
  DWORD FileSizeHigh; // [rsp+80h] [rbp+8h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+90h] [rbp+18h] BYREF

  v2 = *(_QWORD *)(a1 + 24);
  if ( v2 )
  {
    v4 = *(__int64 (**)(void))(v2 + 872);
    if ( v4 )
      return v4();
  }
  v6 = *a2;
  v7 = *(void **)a1;
  FileSizeHigh = 0;
  v17 = v6;
  FileSize = GetFileSize(v7, &FileSizeHigh);
  if ( (FileSize | ((unsigned __int64)FileSizeHigh << 32)) >= v6.m128i_i64[0] + _mm_srli_si128(v6, 8).m128i_u64[0] )
  {
    LOBYTE(v9) = 1;
    v11 = *(__m128i *)GetTpMapRange(v18, &v17, v9);
    v12 = malloc(0x100000u);
    if ( !v12 )
      return (unsigned int)-1073741670;
    v13 = *(void **)a1;
    liDistanceToMove = (LARGE_INTEGER)v11.m128i_i64[0];
    if ( SetFilePointerEx(v13, (LARGE_INTEGER)v11.m128i_i64[0], 0, 0) )
    {
      LOBYTE(v14) = -1;
      v15 = _mm_srli_si128(v11, 8).m128i_u64[0];
      v10 = 0;
      memset_0(v12, v14, 0x100000u);
      if ( !v15 )
      {
LABEL_14:
        free(v12);
        return v10;
      }
      while ( 1 )
      {
        v16 = *(void **)a1;
        liDistanceToMove.LowPart = 0;
        if ( !WriteFile(v16, v12, 0x100000u, (LPDWORD)&liDistanceToMove, 0) )
          break;
        v15 -= 0x100000LL;
        if ( !v15 )
          goto LABEL_14;
      }
    }
    v10 = -1073741436;
    goto LABEL_14;
  }
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14008614c  mov     [rsp+arg_8], rbx
0x140086151  mov     [rsp+arg_18], rbp
0x140086156  push    rsi
0x140086157  push    rdi
0x140086158  push    r15
0x14008615a  sub     rsp, 60h
0x14008615e  mov     rax, [rcx+18h]
0x140086162  mov     rdi, rcx
0x140086165  movaps  [rsp+78h+var_28], xmm6
0x14008616a  test    rax, rax
0x14008616d  jz      short loc_140086185
0x14008616f  mov     rax, [rax+368h]
0x140086176  test    rax, rax
0x140086179  jz      short loc_140086185
0x14008617b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086180  jmp     loc_1400862C0
0x140086185  movups  xmm6, xmmword ptr [rdx]
0x140086188  mov     rcx, [rcx]; hFile
0x14008618b  lea     rdx, [rsp+78h+FileSizeHigh]; lpFileSizeHigh
0x140086193  mov     [rsp+78h+FileSizeHigh], 0
0x14008619e  movups  [rsp+78h+var_48], xmm6
0x1400861a3  call    cs:__imp_GetFileSize
0x1400861aa  nop     dword ptr [rax+rax+00h]
0x1400861af  mov     edx, [rsp+78h+FileSizeHigh]
0x1400861b6  movdqa  xmm0, xmm6
0x1400861ba  shl     rdx, 20h
0x1400861be  mov     eax, eax
0x1400861c0  or      rdx, rax
0x1400861c3  psrldq  xmm0, 8
0x1400861c8  movq    rax, xmm6
0x1400861cd  movq    rcx, xmm0
0x1400861d2  add     rcx, rax
0x1400861d5  cmp     rdx, rcx
0x1400861d8  jnb     short loc_1400861E4
0x1400861da  mov     ebx, 0C000000Dh
0x1400861df  jmp     loc_1400862BE
0x1400861e4  mov     r8b, 1
0x1400861e7  lea     rdx, [rsp+78h+var_48]
0x1400861ec  lea     rcx, [rsp+78h+var_38]
0x1400861f1  call    ?GetTpMapRange@@YA?AU_RANGE@@PEAU1@E@Z; GetTpMapRange(_RANGE *,uchar)
0x1400861f6  mov     r15d, 100000h
0x1400861fc  mov     ecx, r15d; Size
0x1400861ff  movups  xmm6, xmmword ptr [rax]
0x140086202  call    cs:__imp_malloc
0x140086209  nop     dword ptr [rax+rax+00h]
0x14008620e  mov     rbp, rax
0x140086211  test    rax, rax
0x140086214  jnz     short loc_140086220
0x140086216  mov     ebx, 0C000009Ah
0x14008621b  jmp     loc_1400862BE
0x140086220  mov     rcx, [rdi]; hFile
0x140086223  movq    rax, xmm6
0x140086228  mov     dword ptr [rsp+78h+liDistanceToMove], eax
0x14008622f  xor     r9d, r9d; dwMoveMethod
0x140086232  shr     rax, 20h
0x140086236  xor     r8d, r8d; lpNewFilePointer
0x140086239  mov     dword ptr [rsp+78h+liDistanceToMove+4], eax
0x140086240  mov     rdx, qword ptr [rsp+78h+liDistanceToMove]; liDistanceToMove
0x140086248  call    cs:__imp_SetFilePointerEx
0x14008624f  nop     dword ptr [rax+rax+00h]
0x140086254  test    eax, eax
0x140086256  jz      short loc_1400862AA
0x140086258  psrldq  xmm6, 8
0x14008625d  mov     r8, r15; Size
0x140086260  mov     dl, 0FFh; Val
0x140086262  mov     rcx, rbp; void *
0x140086265  movq    rsi, xmm6
0x14008626a  xor     ebx, ebx
0x14008626c  call    memset_0
0x140086271  test    rsi, rsi
0x140086274  jz      short loc_1400862AF
0x140086276  mov     rcx, [rdi]; hFile
0x140086279  lea     r9, [rsp+78h+liDistanceToMove]; lpNumberOfBytesWritten
0x140086281  mov     r8d, r15d; nNumberOfBytesToWrite
0x140086284  mov     dword ptr [rsp+78h+liDistanceToMove], ebx
0x14008628b  mov     rdx, rbp; lpBuffer
0x14008628e  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x140086293  call    cs:__imp_WriteFile
0x14008629a  nop     dword ptr [rax+rax+00h]
0x14008629f  test    eax, eax
0x1400862a1  jz      short loc_1400862AA
0x1400862a3  sub     rsi, r15
0x1400862a6  jnz     short loc_140086276
0x1400862a8  jmp     short loc_1400862AF
0x1400862aa  mov     ebx, 0C0000184h
0x1400862af  mov     rcx, rbp; Block
0x1400862b2  call    cs:__imp_free
0x1400862b9  nop     dword ptr [rax+rax+00h]
0x1400862be  mov     eax, ebx
0x1400862c0  movaps  xmm6, [rsp+78h+var_28]
0x1400862c5  lea     r11, [rsp+78h+var_18]
0x1400862ca  mov     rbx, [r11+28h]
0x1400862ce  mov     rbp, [r11+38h]
0x1400862d2  mov     rsp, r11
0x1400862d5  pop     r15
0x1400862d7  pop     rdi
0x1400862d8  pop     rsi
0x1400862d9  retn
```
