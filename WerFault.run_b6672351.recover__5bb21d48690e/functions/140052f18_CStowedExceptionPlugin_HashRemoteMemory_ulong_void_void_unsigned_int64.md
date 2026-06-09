# CStowedExceptionPlugin::HashRemoteMemory(ulong *,void *,void *,unsigned __int64)

- ea: `0x140052f18`
- end: `0x14005314f`
- name: `?HashRemoteMemory@CStowedExceptionPlugin@@CAJPEAKPEAX1_K@Z`
- size: `567`
- prototype: `__int64 __fastcall(unsigned int *, HANDLE hProcess, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400533b0`

## callees

- `0x140002490`
- `0x140052e3c`
- `0x140052f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400530ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140053088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400530ed`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052fe9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140052fe9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140052f6f`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x140052f6f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140053122`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x140053122`
- `bcrypt!BCryptFinishHash` at `0x14005303f`
- `bcrypt!BCryptFinishHash` at `0x1400530bc`
- `bcrypt!BCryptFinishHash` at `0x14005303f`
- `bcrypt!BCryptFinishHash` at `0x1400530bc`
- `bcrypt!BCryptDestroyHash` at `0x14005305a`
- `bcrypt!BCryptDestroyHash` at `0x1400530d7`
- `bcrypt!BCryptDestroyHash` at `0x14005305a`
- `bcrypt!BCryptDestroyHash` at `0x1400530d7`
- `bcrypt!BCryptCreateHash` at `0x140052fa7`
- `bcrypt!BCryptCreateHash` at `0x140052fa7`
- `bcrypt!BCryptHashData` at `0x140053010`
- `bcrypt!BCryptHashData` at `0x140053010`

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
0x140052f18  push    rbp
0x140052f1a  push    rbx
0x140052f1b  push    rsi
0x140052f1c  push    rdi
0x140052f1d  push    r12
0x140052f1f  push    r13
0x140052f21  push    r14
0x140052f23  push    r15
0x140052f25  mov     rbp, rsp
0x140052f28  sub     rsp, 78h
0x140052f2c  mov     rax, cs:__security_cookie
0x140052f33  xor     rax, rsp
0x140052f36  mov     [rbp+var_10], rax
0x140052f3a  mov     r14, r9
0x140052f3d  mov     r13, r8
0x140052f40  mov     r12, rdx
0x140052f43  mov     r15, rcx
0x140052f46  mov     [rbp+NumberOfBytesRead], 0
0x140052f4e  xorps   xmm0, xmm0
0x140052f51  xor     eax, eax
0x140052f53  movups  xmmword ptr [rbp+phHash], xmm0
0x140052f57  mov     [rbp+var_18], rax
0x140052f5b  mov     [rcx], eax
0x140052f5d  mov     eax, 1000h
0x140052f62  mov     r9d, 4; flProtect
0x140052f68  mov     r8d, eax; flAllocationType
0x140052f6b  mov     edx, eax; dwSize
0x140052f6d  xor     ecx, ecx; lpAddress
0x140052f6f  call    cs:__imp_VirtualAlloc
0x140052f76  nop     dword ptr [rax+rax+00h]
0x140052f7b  mov     rsi, rax
0x140052f7e  mov     [rbp+var_30], rax
0x140052f82  test    rax, rax
0x140052f85  jz      loc_1400530ED
0x140052f8b  xor     ebx, ebx
0x140052f8d  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x140052f91  mov     [rsp+78h+cbSecret], ebx; cbSecret
0x140052f95  mov     [rsp+78h+pbSecret], rbx; pbSecret
0x140052f9a  xor     r9d, r9d; cbHashObject
0x140052f9d  xor     r8d, r8d; pbHashObject
0x140052fa0  lea     rdx, [rbp+phHash]; phHash
0x140052fa4  lea     ecx, [rbx+21h]; hAlgorithm
0x140052fa7  call    cs:__imp_BCryptCreateHash
0x140052fae  nop     dword ptr [rax+rax+00h]
0x140052fb3  test    eax, eax
0x140052fb5  jns     short loc_140052FBC
0x140052fb7  lea     ecx, [rbx+7]
0x140052fba  int     29h; Win8: RtlFailFast(ecx)
0x140052fbc  test    r14, r14
0x140052fbf  jz      short loc_140053030
0x140052fc1  mov     rdi, r14
0x140052fc4  sub     rdi, rbx
0x140052fc7  mov     eax, 1000h
0x140052fcc  cmp     rdi, rax
0x140052fcf  cmova   rdi, rax
0x140052fd3  lea     rdx, [rbx+r13]; lpBaseAddress
0x140052fd7  lea     rax, [rbp+NumberOfBytesRead]
0x140052fdb  mov     [rsp+78h+pbSecret], rax; lpNumberOfBytesRead
0x140052fe0  mov     r9, rdi; nSize
0x140052fe3  mov     r8, rsi; lpBuffer
0x140052fe6  mov     rcx, r12; hProcess
0x140052fe9  call    cs:__imp_ReadProcessMemory
0x140052ff0  nop     dword ptr [rax+rax+00h]
0x140052ff5  test    eax, eax
0x140052ff7  jz      loc_140053088
0x140052ffd  mov     r8, [rbp+NumberOfBytesRead]; cbInput
0x140053001  cmp     r8, rdi
0x140053004  jnz     short loc_140053081
0x140053006  xor     r9d, r9d; dwFlags
0x140053009  mov     rdx, rsi; pbInput
0x14005300c  mov     rcx, [rbp+phHash]; hHash
0x140053010  call    cs:__imp_BCryptHashData
0x140053017  nop     dword ptr [rax+rax+00h]
0x14005301c  test    eax, eax
0x14005301e  jns     short loc_140053027
0x140053020  mov     ecx, 7
0x140053025  int     29h; Win8: RtlFailFast(ecx)
0x140053027  add     rbx, [rbp+NumberOfBytesRead]
0x14005302b  cmp     rbx, r14
0x14005302e  jb      short loc_140052FC1
0x140053030  xor     r9d, r9d; dwFlags
0x140053033  lea     r8d, [r9+10h]; cbOutput
0x140053037  lea     rdx, [rbp+phHash+8]; pbOutput
0x14005303b  mov     rcx, [rbp+phHash]; hHash
0x14005303f  call    cs:__imp_BCryptFinishHash
0x140053046  nop     dword ptr [rax+rax+00h]
0x14005304b  test    eax, eax
0x14005304d  jns     short loc_140053056
0x14005304f  mov     ecx, 7
0x140053054  int     29h; Win8: RtlFailFast(ecx)
0x140053056  mov     rcx, [rbp+phHash]; hHash
0x14005305a  call    cs:__imp_BCryptDestroyHash
0x140053061  nop     dword ptr [rax+rax+00h]
0x140053066  mov     [rbp+phHash], 0
0x14005306e  lea     rdx, [rbp+phHash+8]; unsigned __int8 *
0x140053072  mov     rcx, r15; unsigned int *
0x140053075  call    ?CompactMD5Digest@CStowedExceptionPlugin@@CAXPEAKPEAE@Z; CStowedExceptionPlugin::CompactMD5Digest(ulong *,uchar *)
0x14005307a  xor     ebx, ebx
0x14005307c  jmp     loc_140053112
0x140053081  mov     ebx, 8007012Bh
0x140053086  jmp     short loc_1400530AD
0x140053088  call    cs:__imp_GetLastError
0x14005308f  nop     dword ptr [rax+rax+00h]
0x140053094  mov     ebx, eax
0x140053096  test    eax, eax
0x140053098  jle     short loc_1400530A3
0x14005309a  movzx   ebx, ax
0x14005309d  or      ebx, 80070000h
0x1400530a3  mov     eax, 80004005h
0x1400530a8  test    ebx, ebx
0x1400530aa  cmovns  ebx, eax
0x1400530ad  xor     r9d, r9d; dwFlags
0x1400530b0  lea     r8d, [r9+10h]; cbOutput
0x1400530b4  lea     rdx, [rbp+phHash+8]; pbOutput
0x1400530b8  mov     rcx, [rbp+phHash]; hHash
0x1400530bc  call    cs:__imp_BCryptFinishHash
0x1400530c3  nop     dword ptr [rax+rax+00h]
0x1400530c8  test    eax, eax
0x1400530ca  jns     short loc_1400530D3
0x1400530cc  mov     ecx, 7
0x1400530d1  int     29h; Win8: RtlFailFast(ecx)
0x1400530d3  mov     rcx, [rbp+phHash]; hHash
0x1400530d7  call    cs:__imp_BCryptDestroyHash
0x1400530de  nop     dword ptr [rax+rax+00h]
0x1400530e3  mov     [rbp+phHash], 0
0x1400530eb  jmp     short loc_140053112
0x1400530ed  call    cs:__imp_GetLastError
0x1400530f4  nop     dword ptr [rax+rax+00h]
0x1400530f9  mov     ebx, eax
0x1400530fb  test    eax, eax
0x1400530fd  jle     short loc_140053108
0x1400530ff  movzx   ebx, ax
0x140053102  or      ebx, 80070000h
0x140053108  mov     eax, 80004005h
0x14005310d  test    ebx, ebx
0x14005310f  cmovns  ebx, eax
0x140053112  test    rsi, rsi
0x140053115  jz      short loc_14005312F
0x140053117  xor     edx, edx; dwSize
0x140053119  mov     r8d, 8000h; dwFreeType
0x14005311f  mov     rcx, rsi; lpAddress
0x140053122  call    cs:__imp_VirtualFree
0x140053129  nop     dword ptr [rax+rax+00h]
0x14005312e  nop
0x14005312f  mov     eax, ebx
0x140053131  mov     rcx, [rbp+var_10]
0x140053135  xor     rcx, rsp; StackCookie
0x140053138  call    __security_check_cookie
0x14005313d  add     rsp, 78h
0x140053141  pop     r15
0x140053143  pop     r14
0x140053145  pop     r13
0x140053147  pop     r12
0x140053149  pop     rdi
0x14005314a  pop     rsi
0x14005314b  pop     rbx
0x14005314c  pop     rbp
0x14005314d  retn
```
