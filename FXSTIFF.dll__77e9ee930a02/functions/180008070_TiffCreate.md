# TiffCreate

- ea: `0x180008070`
- end: `0x180008380`
- name: `TiffCreate`
- size: `784`
- prototype: `__int64 *__fastcall(LPCWSTR lpFileName, int, int, int, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180004540`
- `0x180005ed0`
- `0x18000b120`
- `0x18000bb50`

## callees

- `0x180008070`
- `0x180009f04`
- `0x180009f34`
- `0x18000f128`
- `0x18000f1c8`
- `0x1800131b4`
- `0x18001899e`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800081c9`
- `KERNEL32!DeleteFileW` at `0x180008357`
- `KERNEL32!DeleteFileW` at `0x1800081c9`
- `KERNEL32!DeleteFileW` at `0x180008357`
- `KERNEL32!WriteFile` at `0x180008335`
- `KERNEL32!WriteFile` at `0x180008335`
- `KERNEL32!SetLastError` at `0x1800081f0`
- `KERNEL32!SetLastError` at `0x1800081f0`
- `KERNEL32!CloseHandle` at `0x1800081ba`
- `KERNEL32!CloseHandle` at `0x180008348`
- `KERNEL32!CloseHandle` at `0x1800081ba`
- `KERNEL32!CloseHandle` at `0x180008348`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall TiffCreate(LPCWSTR lpFileName, int a2, int a3, int a4, int a5)
{
  __int64 v8; // rbp
  __int64 *v9; // rax
  __int64 *v10; // rdi
  __int64 File; // rax
  __int64 *v13; // rcx
  __int64 v14; // rax
  _WORD *v15; // r8
  LPCWSTR v16; // rcx
  __int64 v17; // rdx
  __int64 *v18; // rsi
  _WORD *v19; // rcx
  DWORD v20; // ebx
  _OWORD *v21; // rcx
  __int64 *v22; // rax
  __int128 v23; // xmm1
  bool v24; // zf
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-58h] BYREF

  NumberOfBytesWritten = 0;
  v8 = 2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  v9 = (__int64 *)pMemAlloc(0x6A0u);
  v10 = v9;
  if ( !v9 )
    return 0;
  memset_0(v9, 0, 0x6A0u);
  if ( lpFileName )
  {
    File = InternalSafeCreateFile(lpFileName, 0xC0000000, 0, 2u, 0);
    *v10 = File;
    if ( File == -1 )
    {
      v13 = v10;
LABEL_10:
      pMemFree(v13);
      return 0;
    }
    v14 = 2147483646;
    v15 = (_WORD *)v10 + 22;
    v16 = lpFileName;
    v17 = 260;
    v18 = v10;
    do
    {
      if ( !v14 )
        break;
      if ( !*v16 )
        break;
      *v15++ = *v16++;
      --v14;
      --v17;
    }
    while ( v17 );
    v19 = v15 - 1;
    v20 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v19 = v15;
    *v19 = 0;
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids, v20);
      }
      if ( *v10 != -1 )
      {
        CloseHandle((HANDLE)*v10);
        DeleteFileW(lpFileName);
      }
      pMemFree(v10);
      if ( (v20 & 0x1FFF0000) == 0x70000 )
        v20 = (unsigned __int16)v20;
      SetLastError(v20);
      return 0;
    }
  }
  else
  {
    *v10 = -1;
    v18 = v10;
  }
  *((_DWORD *)v18 + 213) = a2;
  *((_DWORD *)v18 + 142) = 0;
  *((_DWORD *)v18 + 6) = 0;
  *((_DWORD *)v18 + 395) = 0;
  *((_WORD *)v18 + 282) = 18761;
  *((_WORD *)v18 + 283) = 42;
  *(__int64 *)((char *)v18 + 836) = 0;
  *((_DWORD *)v18 + 211) = 4;
  *((_DWORD *)v18 + 396) = 32;
  *((_DWORD *)v18 + 391) = a3;
  *((_DWORD *)v18 + 407) = a4;
  *((_DWORD *)v10 + 421) = a5 != 0 ? 196 : 98;
  memset_0((char *)v18 + 860, 0, 0x288u);
  v18[190] = (__int64)v18 + 860;
  v18[189] = (__int64)v18 + 1076;
  v21 = (_OWORD *)((char *)v18 + 572);
  v18[199] = (__int64)v18 + 1076;
  v22 = gc_FaxIFDTemplate;
  do
  {
    *v21 = *(_OWORD *)v22;
    v21[1] = *((_OWORD *)v22 + 1);
    v21[2] = *((_OWORD *)v22 + 2);
    v21[3] = *((_OWORD *)v22 + 3);
    v21[4] = *((_OWORD *)v22 + 4);
    v21[5] = *((_OWORD *)v22 + 5);
    v21[6] = *((_OWORD *)v22 + 6);
    v23 = *((_OWORD *)v22 + 7);
    v22 += 16;
    v21[7] = v23;
    v21 += 8;
    --v8;
  }
  while ( v8 );
  v24 = *v10 == -1;
  *(_QWORD *)((char *)v21 - 2) = *(__int64 *)((char *)v22 - 2);
  if ( !v24 && !WriteFile((HANDLE)*v10, (char *)v18 + 564, 8u, &NumberOfBytesWritten, 0) )
  {
    CloseHandle((HANDLE)*v10);
    DeleteFileW(lpFileName);
    v13 = v18;
    goto LABEL_10;
  }
  return v18;
}

```

## disassembly

```asm
0x180008070  mov     [rsp+arg_8], edx
0x180008074  push    rbx
0x180008075  push    rbp
0x180008076  push    rsi
0x180008077  push    rdi
0x180008078  push    r12
0x18000807a  push    r13
0x18000807c  push    r14
0x18000807e  push    r15
0x180008080  sub     rsp, 58h
0x180008084  xor     ebx, ebx
0x180008086  mov     r12d, r9d
0x180008089  mov     [rsp+98h+NumberOfBytesWritten], ebx
0x18000808d  mov     r13d, r8d
0x180008090  mov     r14, rcx
0x180008093  mov     rcx, cs:WPP_GLOBAL_Control
0x18000809a  lea     r15, WPP_GLOBAL_Control
0x1800080a1  lea     ebp, [rbx+2]
0x1800080a4  cmp     rcx, r15
0x1800080a7  jz      short loc_1800080C8
0x1800080a9  test    [rcx+1Ch], bpl
0x1800080ad  jz      short loc_1800080C8
0x1800080af  cmp     byte ptr [rcx+19h], 5
0x1800080b3  jb      short loc_1800080C8
0x1800080b5  mov     rcx, [rcx+10h]
0x1800080b9  lea     edx, [rbx+0Ah]
0x1800080bc  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800080c3  call    WPP_SF_
0x1800080c8  mov     esi, 6A0h
0x1800080cd  mov     ecx, esi; dwBytes
0x1800080cf  call    pMemAlloc
0x1800080d4  mov     rdi, rax
0x1800080d7  test    rax, rax
0x1800080da  jnz     short loc_1800080E3
0x1800080dc  xor     eax, eax
0x1800080de  jmp     loc_18000836E
0x1800080e3  mov     r8, rsi; Size
0x1800080e6  xor     edx, edx; Val
0x1800080e8  mov     rcx, rdi; void *
0x1800080eb  call    memset_0
0x1800080f0  test    r14, r14
0x1800080f3  jz      loc_180008201
0x1800080f9  mov     [rsp+98h+var_70], ebx; int
0x1800080fd  xor     r8d, r8d; dwShareMode
0x180008100  mov     edx, 0C0000000h; dwDesiredAccess
0x180008105  mov     dword ptr [rsp+98h+lpOverlapped], ebp; DWORD
0x180008109  mov     rcx, r14; lpFileName
0x18000810c  call    InternalSafeCreateFile
0x180008111  mov     [rdi], rax
0x180008114  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008118  jnz     short loc_180008124
0x18000811a  mov     rcx, rdi; lpMem
0x18000811d  call    pMemFree
0x180008122  jmp     short loc_1800080DC
0x180008124  mov     eax, 7FFFFFFEh
0x180008129  lea     r8, [rdi+2Ch]
0x18000812d  mov     rcx, r14
0x180008130  mov     edx, 104h
0x180008135  mov     rsi, rdi
0x180008138  test    rax, rax
0x18000813b  jz      short loc_18000815A
0x18000813d  movzx   r9d, word ptr [rcx]
0x180008141  test    r9w, r9w
0x180008145  jz      short loc_18000815A
0x180008147  mov     [r8], r9w
0x18000814b  add     rcx, rbp
0x18000814e  add     r8, rbp
0x180008151  dec     rax
0x180008154  sub     rdx, 1
0x180008158  jnz     short loc_180008138
0x18000815a  mov     rax, rdx
0x18000815d  lea     rcx, [r8-2]
0x180008161  neg     rax
0x180008164  sbb     ebx, ebx
0x180008166  not     ebx
0x180008168  and     ebx, 8007007Ah
0x18000816e  test    rdx, rdx
0x180008171  cmovnz  rcx, r8
0x180008175  xor     eax, eax
0x180008177  mov     [rcx], ax
0x18000817a  test    rdx, rdx
0x18000817d  jnz     loc_18000820D
0x180008183  mov     rcx, cs:WPP_GLOBAL_Control
0x18000818a  cmp     rcx, r15
0x18000818d  jz      short loc_1800081B1
0x18000818f  test    [rcx+1Ch], bpl
0x180008193  jz      short loc_1800081B1
0x180008195  cmp     [rcx+19h], bpl
0x180008199  jb      short loc_1800081B1
0x18000819b  mov     rcx, [rcx+10h]
0x18000819f  lea     edx, [rax+0Bh]
0x1800081a2  mov     r9d, ebx
0x1800081a5  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x1800081ac  call    WPP_SF_d
0x1800081b1  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800081b5  jz      short loc_1800081D5
0x1800081b7  mov     rcx, [rdi]; hObject
0x1800081ba  call    cs:__imp_CloseHandle
0x1800081c1  nop     dword ptr [rax+rax+00h]
0x1800081c6  mov     rcx, r14; lpFileName
0x1800081c9  call    cs:__imp_DeleteFileW
0x1800081d0  nop     dword ptr [rax+rax+00h]
0x1800081d5  mov     rcx, rdi; lpMem
0x1800081d8  call    pMemFree
0x1800081dd  mov     eax, ebx
0x1800081df  and     eax, 1FFF0000h
0x1800081e4  cmp     eax, 70000h
0x1800081e9  jnz     short loc_1800081EE
0x1800081eb  movzx   ebx, bx
0x1800081ee  mov     ecx, ebx; dwErrCode
0x1800081f0  call    cs:__imp_SetLastError
0x1800081f7  nop     dword ptr [rax+rax+00h]
0x1800081fc  jmp     loc_1800080DC
0x180008201  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180008208  mov     rsi, rdi
0x18000820b  jmp     short loc_18000820F
0x18000820d  xor     ebx, ebx
0x18000820f  mov     eax, [rsp+98h+arg_8]
0x180008216  lea     r15, [rsi+234h]
0x18000821d  neg     [rsp+98h+arg_20]
0x180008224  mov     r8d, 288h; Size
0x18000822a  mov     [rsi+354h], eax
0x180008230  sbb     eax, eax
0x180008232  mov     [rsi+238h], ebx
0x180008238  mov     [rsi+18h], ebx
0x18000823b  and     eax, 62h
0x18000823e  mov     [rsi+62Ch], ebx
0x180008244  add     eax, 62h ; 'b'
0x180008247  mov     word ptr [r15], 4949h
0x18000824d  lea     rbx, [rsi+35Ch]
0x180008254  mov     word ptr [rsi+236h], 2Ah ; '*'
0x18000825d  xor     edx, edx; Val
0x18000825f  mov     qword ptr [rsi+344h], 0
0x18000826a  mov     rcx, rbx; void *
0x18000826d  mov     dword ptr [rsi+34Ch], 4
0x180008277  mov     dword ptr [rsi+630h], 20h ; ' '
0x180008281  mov     [rsi+61Ch], r13d
0x180008288  mov     [rsi+65Ch], r12d
0x18000828f  mov     [rdi+694h], eax
0x180008295  call    memset_0
0x18000829a  lea     rax, [rbx+0D8h]
0x1800082a1  mov     [rsi+5F0h], rbx
0x1800082a8  mov     [rsi+5E8h], rax
0x1800082af  lea     rcx, [rsi+23Ch]
0x1800082b6  mov     [rsi+638h], rax
0x1800082bd  mov     edx, 80h
0x1800082c2  lea     rax, gc_FaxIFDTemplate
0x1800082c9  movups  xmm0, xmmword ptr [rax]
0x1800082cc  movups  xmmword ptr [rcx], xmm0
0x1800082cf  movups  xmm1, xmmword ptr [rax+10h]
0x1800082d3  movups  xmmword ptr [rcx+10h], xmm1
0x1800082d7  movups  xmm0, xmmword ptr [rax+20h]
0x1800082db  movups  xmmword ptr [rcx+20h], xmm0
0x1800082df  movups  xmm1, xmmword ptr [rax+30h]
0x1800082e3  movups  xmmword ptr [rcx+30h], xmm1
0x1800082e7  movups  xmm0, xmmword ptr [rax+40h]
0x1800082eb  movups  xmmword ptr [rcx+40h], xmm0
0x1800082ef  movups  xmm1, xmmword ptr [rax+50h]
0x1800082f3  movups  xmmword ptr [rcx+50h], xmm1
0x1800082f7  movups  xmm0, xmmword ptr [rax+60h]
0x1800082fb  movups  xmmword ptr [rcx+60h], xmm0
0x1800082ff  movups  xmm1, xmmword ptr [rax+70h]
0x180008303  add     rax, rdx
0x180008306  movups  xmmword ptr [rcx+70h], xmm1
0x18000830a  add     rcx, rdx
0x18000830d  sub     rbp, 1
0x180008311  jnz     short loc_1800082C9
0x180008313  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180008317  mov     rax, [rax-2]
0x18000831b  mov     [rcx-2], rax
0x18000831f  jz      short loc_18000836B
0x180008321  mov     rcx, [rdi]; hFile
0x180008324  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008329  lea     r8d, [rbp+8]; nNumberOfBytesToWrite
0x18000832d  mov     [rsp+98h+lpOverlapped], rbp; lpOverlapped
0x180008332  mov     rdx, r15; lpBuffer
0x180008335  call    cs:__imp_WriteFile
0x18000833c  nop     dword ptr [rax+rax+00h]
0x180008341  test    eax, eax
0x180008343  jnz     short loc_18000836B
0x180008345  mov     rcx, [rdi]; hObject
0x180008348  call    cs:__imp_CloseHandle
0x18000834f  nop     dword ptr [rax+rax+00h]
0x180008354  mov     rcx, r14; lpFileName
0x180008357  call    cs:__imp_DeleteFileW
0x18000835e  nop     dword ptr [rax+rax+00h]
0x180008363  mov     rcx, rsi
0x180008366  jmp     loc_18000811D
0x18000836b  mov     rax, rsi
0x18000836e  add     rsp, 58h
0x180008372  pop     r15
0x180008374  pop     r14
0x180008376  pop     r13
0x180008378  pop     r12
0x18000837a  pop     rdi
0x18000837b  pop     rsi
0x18000837c  pop     rbp
0x18000837d  pop     rbx
0x18000837e  retn
```
