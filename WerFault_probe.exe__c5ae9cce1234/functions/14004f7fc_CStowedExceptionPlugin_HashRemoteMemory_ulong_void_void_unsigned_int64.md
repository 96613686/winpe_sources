# CStowedExceptionPlugin::HashRemoteMemory(ulong *,void *,void *,unsigned __int64)

- ea: `0x14004f7fc`
- end: `0x14004f9e9`
- name: `?HashRemoteMemory@CStowedExceptionPlugin@@CAJPEAKPEAX1_K@Z`
- size: `493`
- prototype: `__int64 __fastcall(unsigned int *, HANDLE hProcess, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004fc20`

## callees

- `0x140002470`
- `0x14004f720`
- `0x14004f7fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f994`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f8c1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14004f8c1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14004f853`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x14004f853`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14004f9c3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x14004f9c3`
- `bcrypt!BCryptFinishHash` at `0x14004f907`
- `bcrypt!BCryptFinishHash` at `0x14004f96f`
- `bcrypt!BCryptFinishHash` at `0x14004f907`
- `bcrypt!BCryptFinishHash` at `0x14004f96f`
- `bcrypt!BCryptDestroyHash` at `0x14004f91c`
- `bcrypt!BCryptDestroyHash` at `0x14004f984`
- `bcrypt!BCryptDestroyHash` at `0x14004f91c`
- `bcrypt!BCryptDestroyHash` at `0x14004f984`
- `bcrypt!BCryptCreateHash` at `0x14004f885`
- `bcrypt!BCryptCreateHash` at `0x14004f885`
- `bcrypt!BCryptHashData` at `0x14004f8de`
- `bcrypt!BCryptHashData` at `0x14004f8de`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStowedExceptionPlugin::HashRemoteMemory(
        unsigned int *a1,
        HANDLE hProcess,
        char *a3,
        unsigned __int64 a4)
{
  void *v8; // rsi
  unsigned __int64 v9; // rbx
  SIZE_T v10; // rdi
  signed int v11; // ebx
  signed int LastError; // eax
  signed int v13; // eax
  SIZE_T NumberOfBytesRead[2]; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-18h]

  NumberOfBytesRead[0] = 0;
  *(_OWORD *)phHash = 0;
  v17 = 0;
  *a1 = 0;
  v8 = VirtualAlloc(0, 0x1000u, 0x1000u, 4u);
  NumberOfBytesRead[1] = (SIZE_T)v8;
  if ( v8 )
  {
    v9 = 0;
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = a4 - v9;
        if ( a4 - v9 > 0x1000 )
          v10 = 4096;
        if ( !ReadProcessMemory(hProcess, &a3[v9], v8, v10, NumberOfBytesRead) )
          break;
        if ( NumberOfBytesRead[0] != v10 )
        {
          v11 = -2147024597;
          goto LABEL_20;
        }
        if ( BCryptHashData(phHash[0], (PUCHAR)v8, NumberOfBytesRead[0], 0) < 0 )
          __fastfail(7u);
        v9 += NumberOfBytesRead[0];
        if ( v9 >= a4 )
          goto LABEL_12;
      }
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
LABEL_20:
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      phHash[0] = 0;
    }
    else
    {
LABEL_12:
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      phHash[0] = 0;
      CStowedExceptionPlugin::CompactMD5Digest(a1, (unsigned __int8 *)&phHash[1]);
      v11 = 0;
    }
  }
  else
  {
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
  }
  if ( v8 )
    VirtualFree(v8, 0, 0x8000u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14004f7fc  push    rbp
0x14004f7fe  push    rbx
0x14004f7ff  push    rsi
0x14004f800  push    rdi
0x14004f801  push    r12
0x14004f803  push    r13
0x14004f805  push    r14
0x14004f807  push    r15
0x14004f809  mov     rbp, rsp
0x14004f80c  sub     rsp, 78h
0x14004f810  mov     rax, cs:__security_cookie
0x14004f817  xor     rax, rsp
0x14004f81a  mov     [rbp+var_10], rax
0x14004f81e  mov     r14, r9
0x14004f821  mov     r13, r8
0x14004f824  mov     r12, rdx
0x14004f827  mov     r15, rcx
0x14004f82a  mov     [rbp+NumberOfBytesRead], 0
0x14004f832  xorps   xmm0, xmm0
0x14004f835  xor     eax, eax
0x14004f837  movups  xmmword ptr [rbp+phHash], xmm0
0x14004f83b  mov     [rbp+var_18], rax
0x14004f83f  mov     [rcx], eax
0x14004f841  mov     eax, 1000h
0x14004f846  mov     r9d, 4; flProtect
0x14004f84c  mov     r8d, eax; flAllocationType
0x14004f84f  mov     edx, eax; dwSize
0x14004f851  xor     ecx, ecx; lpAddress
0x14004f853  call    cs:__imp_VirtualAlloc
0x14004f859  mov     rsi, rax
0x14004f85c  mov     [rbp+var_30], rax
0x14004f860  test    rax, rax
0x14004f863  jz      loc_14004F994
0x14004f869  xor     ebx, ebx
0x14004f86b  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x14004f86f  mov     [rsp+78h+cbSecret], ebx; cbSecret
0x14004f873  mov     [rsp+78h+pbSecret], rbx; pbSecret
0x14004f878  xor     r9d, r9d; cbHashObject
0x14004f87b  xor     r8d, r8d; pbHashObject
0x14004f87e  lea     rdx, [rbp+phHash]; phHash
0x14004f882  lea     ecx, [rbx+21h]; hAlgorithm
0x14004f885  call    cs:__imp_BCryptCreateHash
0x14004f88b  test    eax, eax
0x14004f88d  jns     short loc_14004F894
0x14004f88f  lea     ecx, [rbx+7]
0x14004f892  int     29h; Win8: RtlFailFast(ecx)
0x14004f894  test    r14, r14
0x14004f897  jz      short loc_14004F8F8
0x14004f899  mov     rdi, r14
0x14004f89c  sub     rdi, rbx
0x14004f89f  mov     eax, 1000h
0x14004f8a4  cmp     rdi, rax
0x14004f8a7  cmova   rdi, rax
0x14004f8ab  lea     rdx, [rbx+r13]; lpBaseAddress
0x14004f8af  lea     rax, [rbp+NumberOfBytesRead]
0x14004f8b3  mov     [rsp+78h+pbSecret], rax; lpNumberOfBytesRead
0x14004f8b8  mov     r9, rdi; nSize
0x14004f8bb  mov     r8, rsi; lpBuffer
0x14004f8be  mov     rcx, r12; hProcess
0x14004f8c1  call    cs:__imp_ReadProcessMemory
0x14004f8c7  test    eax, eax
0x14004f8c9  jz      short loc_14004F941
0x14004f8cb  mov     r8, [rbp+NumberOfBytesRead]; cbInput
0x14004f8cf  cmp     r8, rdi
0x14004f8d2  jnz     short loc_14004F93A
0x14004f8d4  xor     r9d, r9d; dwFlags
0x14004f8d7  mov     rdx, rsi; pbInput
0x14004f8da  mov     rcx, [rbp+phHash]; hHash
0x14004f8de  call    cs:__imp_BCryptHashData
0x14004f8e4  test    eax, eax
0x14004f8e6  jns     short loc_14004F8EF
0x14004f8e8  mov     ecx, 7
0x14004f8ed  int     29h; Win8: RtlFailFast(ecx)
0x14004f8ef  add     rbx, [rbp+NumberOfBytesRead]
0x14004f8f3  cmp     rbx, r14
0x14004f8f6  jb      short loc_14004F899
0x14004f8f8  xor     r9d, r9d; dwFlags
0x14004f8fb  lea     r8d, [r9+10h]; cbOutput
0x14004f8ff  lea     rdx, [rbp+phHash+8]; pbOutput
0x14004f903  mov     rcx, [rbp+phHash]; hHash
0x14004f907  call    cs:__imp_BCryptFinishHash
0x14004f90d  test    eax, eax
0x14004f90f  jns     short loc_14004F918
0x14004f911  mov     ecx, 7
0x14004f916  int     29h; Win8: RtlFailFast(ecx)
0x14004f918  mov     rcx, [rbp+phHash]; hHash
0x14004f91c  call    cs:__imp_BCryptDestroyHash
0x14004f922  mov     [rbp+phHash], 0
0x14004f92a  lea     rdx, [rbp+phHash+8]; unsigned __int8 *
0x14004f92e  mov     rcx, r15; unsigned int *
0x14004f931  call    ?CompactMD5Digest@CStowedExceptionPlugin@@CAXPEAKPEAE@Z; CStowedExceptionPlugin::CompactMD5Digest(ulong *,uchar *)
0x14004f936  xor     ebx, ebx
0x14004f938  jmp     short loc_14004F9B3
0x14004f93a  mov     ebx, 8007012Bh
0x14004f93f  jmp     short loc_14004F960
0x14004f941  call    cs:__imp_GetLastError
0x14004f947  mov     ebx, eax
0x14004f949  test    eax, eax
0x14004f94b  jle     short loc_14004F956
0x14004f94d  movzx   ebx, ax
0x14004f950  or      ebx, 80070000h
0x14004f956  mov     eax, 80004005h
0x14004f95b  test    ebx, ebx
0x14004f95d  cmovns  ebx, eax
0x14004f960  xor     r9d, r9d; dwFlags
0x14004f963  lea     r8d, [r9+10h]; cbOutput
0x14004f967  lea     rdx, [rbp+phHash+8]; pbOutput
0x14004f96b  mov     rcx, [rbp+phHash]; hHash
0x14004f96f  call    cs:__imp_BCryptFinishHash
0x14004f975  test    eax, eax
0x14004f977  jns     short loc_14004F980
0x14004f979  mov     ecx, 7
0x14004f97e  int     29h; Win8: RtlFailFast(ecx)
0x14004f980  mov     rcx, [rbp+phHash]; hHash
0x14004f984  call    cs:__imp_BCryptDestroyHash
0x14004f98a  mov     [rbp+phHash], 0
0x14004f992  jmp     short loc_14004F9B3
0x14004f994  call    cs:__imp_GetLastError
0x14004f99a  mov     ebx, eax
0x14004f99c  test    eax, eax
0x14004f99e  jle     short loc_14004F9A9
0x14004f9a0  movzx   ebx, ax
0x14004f9a3  or      ebx, 80070000h
0x14004f9a9  mov     eax, 80004005h
0x14004f9ae  test    ebx, ebx
0x14004f9b0  cmovns  ebx, eax
0x14004f9b3  test    rsi, rsi
0x14004f9b6  jz      short loc_14004F9CA
0x14004f9b8  xor     edx, edx; dwSize
0x14004f9ba  mov     r8d, 8000h; dwFreeType
0x14004f9c0  mov     rcx, rsi; lpAddress
0x14004f9c3  call    cs:__imp_VirtualFree
0x14004f9c9  nop
0x14004f9ca  mov     eax, ebx
0x14004f9cc  mov     rcx, [rbp+var_10]
0x14004f9d0  xor     rcx, rsp; StackCookie
0x14004f9d3  call    __security_check_cookie
0x14004f9d8  add     rsp, 78h
0x14004f9dc  pop     r15
0x14004f9de  pop     r14
0x14004f9e0  pop     r13
0x14004f9e2  pop     r12
0x14004f9e4  pop     rdi
0x14004f9e5  pop     rsi
0x14004f9e6  pop     rbx
0x14004f9e7  pop     rbp
0x14004f9e8  retn
```
