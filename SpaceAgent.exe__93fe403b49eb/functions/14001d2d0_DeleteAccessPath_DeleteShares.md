# DeleteAccessPath_DeleteShares

- ea: `0x14001d2d0`
- end: `0x14001d419`
- name: `DeleteAccessPath_DeleteShares`
- size: `329`
- prototype: `_BOOL8 __fastcall(PCWSTR psz2, unsigned __int64 nChar)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d190`

## callees

- `0x14001d2d0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001d3d1`
- `KERNEL32!SetLastError` at `0x14001d3fd`
- `KERNEL32!SetLastError` at `0x14001d3d1`
- `KERNEL32!SetLastError` at `0x14001d3fd`
- `KERNEL32!GetLastError` at `0x14001d3d7`
- `KERNEL32!GetLastError` at `0x14001d3d7`
- `SHLWAPI!StrCmpNIW` at `0x14001d36e`
- `SHLWAPI!StrCmpNIW` at `0x14001d36e`
- `NETAPI32!NetShareDelEx` at `0x14001d38a`
- `NETAPI32!NetShareDelEx` at `0x14001d38a`
- `NETAPI32!NetApiBufferFree` at `0x14001d3a8`
- `NETAPI32!NetApiBufferFree` at `0x14001d3e8`
- `NETAPI32!NetApiBufferFree` at `0x14001d3a8`
- `NETAPI32!NetApiBufferFree` at `0x14001d3e8`
- `NETAPI32!NetShareEnum` at `0x14001d341`
- `NETAPI32!NetShareEnum` at `0x14001d341`

## pseudocode

```c
_BOOL8 __fastcall DeleteAccessPath_DeleteShares(PCWSTR psz2, unsigned __int64 nChar)
{
  int v2; // r14d
  BOOL v4; // ebx
  DWORD v5; // esi
  DWORD v6; // eax
  DWORD v7; // edi
  DWORD v8; // ecx
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD LastError; // edi
  DWORD v12; // eax
  LPBYTE bufptr; // [rsp+40h] [rbp-10h] BYREF
  DWORD entriesread; // [rsp+88h] [rbp+38h] BYREF
  DWORD resume_handle; // [rsp+90h] [rbp+40h] BYREF
  DWORD totalentries; // [rsp+98h] [rbp+48h] BYREF

  bufptr = 0;
  v2 = nChar;
  resume_handle = 0;
  v4 = 1;
  if ( nChar < 2 )
  {
    v5 = 0;
    do
    {
      entriesread = 0;
      totalentries = 0;
      v6 = NetShareEnum(0, 2u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, &resume_handle);
      v7 = v6;
      if ( v6 && v6 != 234 )
      {
        v4 = 0;
        v8 = v6;
        goto LABEL_14;
      }
      while ( entriesread )
      {
        if ( !StrCmpNIW(*(PCWSTR *)&bufptr[56 * --entriesread + 40], psz2, v2) )
        {
          v9 = NetShareDelEx(0, 2u, &bufptr[56 * entriesread]);
          if ( v4 )
          {
            v5 = v9;
            v4 = v9 == 0;
          }
        }
      }
      v10 = NetApiBufferFree(bufptr);
      bufptr = 0;
      if ( v4 )
      {
        v5 = v10;
        v4 = v10 == 0;
      }
    }
    while ( v7 == 234 );
    v8 = v5;
LABEL_14:
    SetLastError(v8);
  }
  LastError = GetLastError();
  if ( bufptr )
  {
    v12 = NetApiBufferFree(bufptr);
    if ( v4 )
    {
      LastError = v12;
      v4 = v12 == 0;
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x14001d2d0  mov     [rsp-28h+arg_0], rbx
0x14001d2d5  push    rbp
0x14001d2d6  push    rsi
0x14001d2d7  push    rdi
0x14001d2d8  push    r14
0x14001d2da  push    r15
0x14001d2dc  mov     rbp, rsp
0x14001d2df  sub     rsp, 50h
0x14001d2e3  mov     [rbp+bufptr], 0
0x14001d2eb  mov     r14, rdx
0x14001d2ee  mov     [rbp+arg_10], 0
0x14001d2f5  mov     r15, rcx
0x14001d2f8  mov     ebx, 1
0x14001d2fd  cmp     rdx, 2
0x14001d301  jnb     loc_14001D3D7
0x14001d307  xor     esi, esi
0x14001d309  lea     rax, [rbp+arg_10]
0x14001d30d  mov     [rbp+arg_8], 0
0x14001d314  mov     [rsp+50h+resume_handle], rax; resume_handle
0x14001d319  lea     r8, [rbp+bufptr]; bufptr
0x14001d31d  lea     rax, [rbp+arg_18]
0x14001d321  mov     [rbp+arg_18], 0
0x14001d328  mov     [rsp+50h+totalentries], rax; totalentries
0x14001d32d  or      r9d, 0FFFFFFFFh; prefmaxlen
0x14001d331  lea     rax, [rbp+arg_8]
0x14001d335  mov     edx, 2; level
0x14001d33a  xor     ecx, ecx; servername
0x14001d33c  mov     [rsp+50h+entriesread], rax; entriesread
0x14001d341  call    cs:__imp_NetShareEnum
0x14001d347  mov     edi, eax
0x14001d349  test    eax, eax
0x14001d34b  jz      short loc_14001D39D
0x14001d34d  cmp     eax, 0EAh
0x14001d352  jz      short loc_14001D39D
0x14001d354  xor     ebx, ebx
0x14001d356  mov     ecx, eax
0x14001d358  jmp     short loc_14001D3D1
0x14001d35a  dec     eax
0x14001d35c  mov     r8d, r14d; nChar
0x14001d35f  imul    r9, rax, 38h ; '8'
0x14001d363  mov     [rbp+arg_8], eax
0x14001d366  mov     rdx, r15; psz2
0x14001d369  mov     rcx, [r9+rcx+28h]; psz1
0x14001d36e  call    cs:__imp_StrCmpNIW
0x14001d374  test    eax, eax
0x14001d376  jnz     short loc_14001D39D
0x14001d378  mov     eax, [rbp+arg_8]
0x14001d37b  mov     edx, 2; level
0x14001d380  imul    r8, rax, 38h ; '8'
0x14001d384  xor     ecx, ecx; servername
0x14001d386  add     r8, [rbp+bufptr]; buf
0x14001d38a  call    cs:__imp_NetShareDelEx
0x14001d390  test    ebx, ebx
0x14001d392  jz      short loc_14001D39D
0x14001d394  xor     ebx, ebx
0x14001d396  mov     esi, eax
0x14001d398  test    eax, eax
0x14001d39a  setz    bl
0x14001d39d  mov     eax, [rbp+arg_8]
0x14001d3a0  mov     rcx, [rbp+bufptr]; Buffer
0x14001d3a4  test    eax, eax
0x14001d3a6  jnz     short loc_14001D35A
0x14001d3a8  call    cs:__imp_NetApiBufferFree
0x14001d3ae  mov     [rbp+bufptr], 0
0x14001d3b6  test    ebx, ebx
0x14001d3b8  jz      short loc_14001D3C3
0x14001d3ba  xor     ebx, ebx
0x14001d3bc  mov     esi, eax
0x14001d3be  test    eax, eax
0x14001d3c0  setz    bl
0x14001d3c3  cmp     edi, 0EAh
0x14001d3c9  jz      loc_14001D309
0x14001d3cf  mov     ecx, esi; dwErrCode
0x14001d3d1  call    cs:__imp_SetLastError
0x14001d3d7  call    cs:__imp_GetLastError
0x14001d3dd  mov     rcx, [rbp+bufptr]; Buffer
0x14001d3e1  mov     edi, eax
0x14001d3e3  test    rcx, rcx
0x14001d3e6  jz      short loc_14001D3FB
0x14001d3e8  call    cs:__imp_NetApiBufferFree
0x14001d3ee  test    ebx, ebx
0x14001d3f0  jz      short loc_14001D3FB
0x14001d3f2  xor     ebx, ebx
0x14001d3f4  mov     edi, eax
0x14001d3f6  test    eax, eax
0x14001d3f8  setz    bl
0x14001d3fb  mov     ecx, edi; dwErrCode
0x14001d3fd  call    cs:__imp_SetLastError
0x14001d403  mov     eax, ebx
0x14001d405  mov     rbx, [rsp+50h+arg_0]
0x14001d40d  add     rsp, 50h
0x14001d411  pop     r15
0x14001d413  pop     r14
0x14001d415  pop     rdi
0x14001d416  pop     rsi
0x14001d417  pop     rbp
0x14001d418  retn
```
