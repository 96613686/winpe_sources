# CheckValidDriveType

- ea: `0x1400120c0`
- end: `0x140012203`
- name: `CheckValidDriveType`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400122f0`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x1400120c0`
- `0x140045a5c`
- `0x140045a80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140012173`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x140012173`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14001214a`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14001214a`

## pseudocode

```c
__int64 __fastcall CheckValidDriveType(LPCWSTR lpszFileName, int a2, int a3)
{
  unsigned int LastError; // edi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  DWORD v10; // r15d
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  const char *v13; // r9
  UINT DriveTypeW; // eax
  UINT v15; // eax
  UINT v16; // eax
  UINT v17; // eax
  __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LastError = 0;
  if ( lpszFileName )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpszFileName[v9] );
    v10 = v9 + 1;
    v11 = (WCHAR *)o_malloc_0(saturated_mul((int)v9 + 1, 2u));
    v12 = v11;
    if ( !v11 )
    {
      v7 = -2147024882;
      v8 = 302;
      goto LABEL_3;
    }
    if ( !GetVolumePathNameW(lpszFileName, v11, v10) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x133,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
                    v13);
LABEL_10:
      v7 = LastError;
LABEL_22:
      free(v12);
      return v7;
    }
    DriveTypeW = GetDriveTypeW(v12);
    if ( DriveTypeW )
    {
      v15 = DriveTypeW - 2;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( !v16 )
          goto LABEL_10;
        v17 = v16 - 1;
        if ( !v17 )
        {
          v7 = a2 == 0 ? 0x80070005 : 0;
          if ( a2 )
            goto LABEL_22;
          v18 = 328;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
            (const char *)v7,
            v20);
          goto LABEL_22;
        }
        if ( v17 - 1 >= 2 )
        {
          v7 = -2147024809;
          v18 = 331;
          goto LABEL_21;
        }
      }
    }
    v7 = a3 == 0 ? 0x80070005 : 0;
    if ( a3 )
      goto LABEL_22;
    v18 = 325;
    goto LABEL_21;
  }
  v7 = -2147024809;
  v8 = 298;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
    (const char *)v7,
    v20);
  return v7;
}

```

## disassembly

```asm
0x1400120c0  mov     [rsp+arg_18], rbx
0x1400120c5  push    rbp
0x1400120c6  push    rsi
0x1400120c7  push    rdi
0x1400120c8  push    r14
0x1400120ca  push    r15; int
0x1400120cc  sub     rsp, 20h
0x1400120d0  xor     edi, edi
0x1400120d2  mov     r14d, r8d
0x1400120d5  mov     ebp, edx
0x1400120d7  mov     rbx, rcx
0x1400120da  test    rcx, rcx
0x1400120dd  jnz     short loc_140012102
0x1400120df  mov     ebx, 80070057h
0x1400120e4  mov     edx, 12Ah; void *
0x1400120e9  mov     rcx, [rsp+48h]; this
0x1400120ee  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x1400120f5  mov     r9d, ebx; char *
0x1400120f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400120fd  jmp     loc_1400121F0
0x140012102  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012106  mov     rax, r8
0x140012109  inc     rax
0x14001210c  cmp     [rcx+rax*2], di
0x140012110  jnz     short loc_140012109
0x140012112  lea     r15d, [rax+1]
0x140012116  mov     eax, 2
0x14001211b  movsxd  rcx, r15d
0x14001211e  mul     rcx
0x140012121  cmovb   rax, r8
0x140012125  mov     rcx, rax; Size
0x140012128  call    _o_malloc_0
0x14001212d  mov     rsi, rax
0x140012130  test    rax, rax
0x140012133  jnz     short loc_140012141
0x140012135  mov     ebx, 8007000Eh
0x14001213a  mov     edx, 12Eh
0x14001213f  jmp     short loc_1400120E9
0x140012141  mov     r8d, r15d; cchBufferLength
0x140012144  mov     rdx, rsi; lpszVolumePathName
0x140012147  mov     rcx, rbx; lpszFileName
0x14001214a  call    cs:__imp_GetVolumePathNameW
0x140012150  test    eax, eax
0x140012152  jnz     short loc_140012170
0x140012154  mov     rcx, [rsp+48h]; this
0x140012159  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x140012160  mov     edx, 133h; void *
0x140012165  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001216a  mov     edi, eax
0x14001216c  mov     ebx, edi
0x14001216e  jmp     short loc_1400121E8
0x140012170  mov     rcx, rsi; lpRootPathName
0x140012173  call    cs:__imp_GetDriveTypeW
0x140012179  test    eax, eax
0x14001217b  jz      short loc_1400121BB
0x14001217d  sub     eax, 2
0x140012180  jz      short loc_1400121BB
0x140012182  sub     eax, 1
0x140012185  jz      short loc_14001216C
0x140012187  sub     eax, 1
0x14001218a  jz      short loc_1400121A2
0x14001218c  sub     eax, 1
0x14001218f  jz      short loc_1400121BB
0x140012191  cmp     eax, 1
0x140012194  jz      short loc_1400121BB
0x140012196  mov     ebx, 80070057h
0x14001219b  mov     edx, 14Bh
0x1400121a0  jmp     short loc_1400121D4
0x1400121a2  mov     eax, ebp
0x1400121a4  neg     eax
0x1400121a6  sbb     ebx, ebx
0x1400121a8  not     ebx
0x1400121aa  and     ebx, 80070005h
0x1400121b0  test    ebp, ebp
0x1400121b2  jnz     short loc_1400121E8
0x1400121b4  mov     edx, 148h
0x1400121b9  jmp     short loc_1400121D4
0x1400121bb  mov     eax, r14d
0x1400121be  neg     eax
0x1400121c0  sbb     ebx, ebx
0x1400121c2  not     ebx
0x1400121c4  and     ebx, 80070005h
0x1400121ca  test    r14d, r14d
0x1400121cd  jnz     short loc_1400121E8
0x1400121cf  mov     edx, 145h; void *
0x1400121d4  mov     rcx, [rsp+48h]; this
0x1400121d9  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x1400121e0  mov     r9d, ebx; char *
0x1400121e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400121e8  mov     rcx, rsi; Block
0x1400121eb  call    free
0x1400121f0  mov     eax, ebx
0x1400121f2  mov     rbx, [rsp+48h+arg_18]
0x1400121f7  add     rsp, 20h
0x1400121fb  pop     r15
0x1400121fd  pop     r14
0x1400121ff  pop     rdi
0x140012200  pop     rsi
0x140012201  pop     rbp
0x140012202  retn
```
