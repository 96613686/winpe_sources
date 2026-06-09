# TiffCreate

- ea: `0x180007d60`
- end: `0x180008047`
- name: `TiffCreate`
- size: `743`
- prototype: `__int64 *__fastcall(LPCWSTR lpFileName, int, int, int, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800044f0`
- `0x180005d80`
- `0x18000ac38`
- `0x18000b604`

## callees

- `0x180007d60`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000ea18`
- `0x18000eac0`
- `0x180012ad4`
- `0x180017bce`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180007eaf`
- `KERNEL32!DeleteFileW` at `0x180008025`
- `KERNEL32!DeleteFileW` at `0x180007eaf`
- `KERNEL32!DeleteFileW` at `0x180008025`
- `KERNEL32!WriteFile` at `0x18000800f`
- `KERNEL32!WriteFile` at `0x18000800f`
- `KERNEL32!SetLastError` at `0x180007ed0`
- `KERNEL32!SetLastError` at `0x180007ed0`
- `KERNEL32!CloseHandle` at `0x180007ea6`
- `KERNEL32!CloseHandle` at `0x18000801c`
- `KERNEL32!CloseHandle` at `0x180007ea6`
- `KERNEL32!CloseHandle` at `0x18000801c`

## pseudocode

```c
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
0x180007d60  mov     [rsp+arg_8], edx
0x180007d64  push    rbx
0x180007d65  push    rbp
0x180007d66  push    rsi
0x180007d67  push    rdi
0x180007d68  push    r12
0x180007d6a  push    r13
0x180007d6c  push    r14
0x180007d6e  push    r15
0x180007d70  sub     rsp, 58h
0x180007d74  xor     ebx, ebx
0x180007d76  mov     r12d, r9d
0x180007d79  mov     [rsp+98h+NumberOfBytesWritten], ebx
0x180007d7d  mov     r13d, r8d
0x180007d80  mov     r14, rcx
0x180007d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d8a  lea     r15, WPP_GLOBAL_Control
0x180007d91  lea     ebp, [rbx+2]
0x180007d94  cmp     rcx, r15
0x180007d97  jz      short loc_180007DB8
0x180007d99  test    [rcx+1Ch], bpl
0x180007d9d  jz      short loc_180007DB8
0x180007d9f  cmp     byte ptr [rcx+19h], 5
0x180007da3  jb      short loc_180007DB8
0x180007da5  mov     rcx, [rcx+10h]
0x180007da9  lea     edx, [rbx+0Ah]
0x180007dac  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180007db3  call    WPP_SF_
0x180007db8  mov     esi, 6A0h
0x180007dbd  mov     ecx, esi; dwBytes
0x180007dbf  call    pMemAlloc
0x180007dc4  mov     rdi, rax
0x180007dc7  test    rax, rax
0x180007dca  jnz     short loc_180007DD3
0x180007dcc  xor     eax, eax
0x180007dce  jmp     loc_180008036
0x180007dd3  mov     r8, rsi; Size
0x180007dd6  xor     edx, edx; Val
0x180007dd8  mov     rcx, rdi; void *
0x180007ddb  call    memset_0
0x180007de0  test    r14, r14
0x180007de3  jz      loc_180007EDB
0x180007de9  mov     [rsp+98h+var_70], ebx; int
0x180007ded  xor     r8d, r8d; dwShareMode
0x180007df0  mov     edx, 0C0000000h; dwDesiredAccess
0x180007df5  mov     dword ptr [rsp+98h+lpOverlapped], ebp; DWORD
0x180007df9  mov     rcx, r14; lpFileName
0x180007dfc  call    InternalSafeCreateFile
0x180007e01  mov     [rdi], rax
0x180007e04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007e08  jnz     short loc_180007E14
0x180007e0a  mov     rcx, rdi; lpMem
0x180007e0d  call    pMemFree
0x180007e12  jmp     short loc_180007DCC
0x180007e14  mov     eax, 7FFFFFFEh
0x180007e19  lea     r8, [rdi+2Ch]
0x180007e1d  mov     rcx, r14
0x180007e20  mov     edx, 104h
0x180007e25  mov     rsi, rdi
0x180007e28  test    rax, rax
0x180007e2b  jz      short loc_180007E4A
0x180007e2d  movzx   r9d, word ptr [rcx]
0x180007e31  test    r9w, r9w
0x180007e35  jz      short loc_180007E4A
0x180007e37  mov     [r8], r9w
0x180007e3b  add     rcx, rbp
0x180007e3e  add     r8, rbp
0x180007e41  dec     rax
0x180007e44  sub     rdx, 1
0x180007e48  jnz     short loc_180007E28
0x180007e4a  mov     rax, rdx
0x180007e4d  lea     rcx, [r8-2]
0x180007e51  neg     rax
0x180007e54  sbb     ebx, ebx
0x180007e56  not     ebx
0x180007e58  and     ebx, 8007007Ah
0x180007e5e  test    rdx, rdx
0x180007e61  cmovnz  rcx, r8
0x180007e65  xor     eax, eax
0x180007e67  mov     [rcx], ax
0x180007e6a  test    rdx, rdx
0x180007e6d  jnz     short loc_180007EE7
0x180007e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e76  cmp     rcx, r15
0x180007e79  jz      short loc_180007E9D
0x180007e7b  test    [rcx+1Ch], bpl
0x180007e7f  jz      short loc_180007E9D
0x180007e81  cmp     [rcx+19h], bpl
0x180007e85  jb      short loc_180007E9D
0x180007e87  mov     rcx, [rcx+10h]
0x180007e8b  lea     edx, [rax+0Bh]
0x180007e8e  mov     r9d, ebx
0x180007e91  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180007e98  call    WPP_SF_d
0x180007e9d  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180007ea1  jz      short loc_180007EB5
0x180007ea3  mov     rcx, [rdi]; hObject
0x180007ea6  call    cs:__imp_CloseHandle
0x180007eac  mov     rcx, r14; lpFileName
0x180007eaf  call    cs:__imp_DeleteFileW
0x180007eb5  mov     rcx, rdi; lpMem
0x180007eb8  call    pMemFree
0x180007ebd  mov     eax, ebx
0x180007ebf  and     eax, 1FFF0000h
0x180007ec4  cmp     eax, 70000h
0x180007ec9  jnz     short loc_180007ECE
0x180007ecb  movzx   ebx, bx
0x180007ece  mov     ecx, ebx; dwErrCode
0x180007ed0  call    cs:__imp_SetLastError
0x180007ed6  jmp     loc_180007DCC
0x180007edb  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180007ee2  mov     rsi, rdi
0x180007ee5  jmp     short loc_180007EE9
0x180007ee7  xor     ebx, ebx
0x180007ee9  mov     eax, [rsp+98h+arg_8]
0x180007ef0  lea     r15, [rsi+234h]
0x180007ef7  neg     [rsp+98h+arg_20]
0x180007efe  mov     r8d, 288h; Size
0x180007f04  mov     [rsi+354h], eax
0x180007f0a  sbb     eax, eax
0x180007f0c  mov     [rsi+238h], ebx
0x180007f12  mov     [rsi+18h], ebx
0x180007f15  and     eax, 62h
0x180007f18  mov     [rsi+62Ch], ebx
0x180007f1e  add     eax, 62h ; 'b'
0x180007f21  mov     word ptr [r15], 4949h
0x180007f27  lea     rbx, [rsi+35Ch]
0x180007f2e  mov     word ptr [rsi+236h], 2Ah ; '*'
0x180007f37  xor     edx, edx; Val
0x180007f39  mov     qword ptr [rsi+344h], 0
0x180007f44  mov     rcx, rbx; void *
0x180007f47  mov     dword ptr [rsi+34Ch], 4
0x180007f51  mov     dword ptr [rsi+630h], 20h ; ' '
0x180007f5b  mov     [rsi+61Ch], r13d
0x180007f62  mov     [rsi+65Ch], r12d
0x180007f69  mov     [rdi+694h], eax
0x180007f6f  call    memset_0
0x180007f74  lea     rax, [rbx+0D8h]
0x180007f7b  mov     [rsi+5F0h], rbx
0x180007f82  mov     [rsi+5E8h], rax
0x180007f89  lea     rcx, [rsi+23Ch]
0x180007f90  mov     [rsi+638h], rax
0x180007f97  mov     edx, 80h
0x180007f9c  lea     rax, gc_FaxIFDTemplate
0x180007fa3  movups  xmm0, xmmword ptr [rax]
0x180007fa6  movups  xmmword ptr [rcx], xmm0
0x180007fa9  movups  xmm1, xmmword ptr [rax+10h]
0x180007fad  movups  xmmword ptr [rcx+10h], xmm1
0x180007fb1  movups  xmm0, xmmword ptr [rax+20h]
0x180007fb5  movups  xmmword ptr [rcx+20h], xmm0
0x180007fb9  movups  xmm1, xmmword ptr [rax+30h]
0x180007fbd  movups  xmmword ptr [rcx+30h], xmm1
0x180007fc1  movups  xmm0, xmmword ptr [rax+40h]
0x180007fc5  movups  xmmword ptr [rcx+40h], xmm0
0x180007fc9  movups  xmm1, xmmword ptr [rax+50h]
0x180007fcd  movups  xmmword ptr [rcx+50h], xmm1
0x180007fd1  movups  xmm0, xmmword ptr [rax+60h]
0x180007fd5  movups  xmmword ptr [rcx+60h], xmm0
0x180007fd9  movups  xmm1, xmmword ptr [rax+70h]
0x180007fdd  add     rax, rdx
0x180007fe0  movups  xmmword ptr [rcx+70h], xmm1
0x180007fe4  add     rcx, rdx
0x180007fe7  sub     rbp, 1
0x180007feb  jnz     short loc_180007FA3
0x180007fed  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180007ff1  mov     rax, [rax-2]
0x180007ff5  mov     [rcx-2], rax
0x180007ff9  jz      short loc_180008033
0x180007ffb  mov     rcx, [rdi]; hFile
0x180007ffe  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180008003  lea     r8d, [rbp+8]; nNumberOfBytesToWrite
0x180008007  mov     [rsp+98h+lpOverlapped], rbp; lpOverlapped
0x18000800c  mov     rdx, r15; lpBuffer
0x18000800f  call    cs:__imp_WriteFile
0x180008015  test    eax, eax
0x180008017  jnz     short loc_180008033
0x180008019  mov     rcx, [rdi]; hObject
0x18000801c  call    cs:__imp_CloseHandle
0x180008022  mov     rcx, r14; lpFileName
0x180008025  call    cs:__imp_DeleteFileW
0x18000802b  mov     rcx, rsi
0x18000802e  jmp     loc_180007E0D
0x180008033  mov     rax, rsi
0x180008036  add     rsp, 58h
0x18000803a  pop     r15
0x18000803c  pop     r14
0x18000803e  pop     r13
0x180008040  pop     r12
0x180008042  pop     rdi
0x180008043  pop     rsi
0x180008044  pop     rbp
0x180008045  pop     rbx
0x180008046  retn
```
