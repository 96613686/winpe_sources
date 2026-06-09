# CheckToken(int *)

- ea: `0x18000c65c`
- end: `0x18000c758`
- name: `?CheckToken@@YAHPEAH@Z`
- size: `252`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180010350`

## callees

- `0x18000c65c`
- `0x18001b980`
- `0x18001c010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000c72b`
- `KERNEL32!FreeLibrary` at `0x18000c72b`
- `KERNEL32!GetProcAddress` at `0x18000c6ba`
- `KERNEL32!GetProcAddress` at `0x18000c6ba`
- `KERNEL32!LoadLibraryW` at `0x18000c69e`
- `KERNEL32!LoadLibraryW` at `0x18000c69e`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000c701`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000c701`
- `ADVAPI32!FreeSid` at `0x18000c722`
- `ADVAPI32!FreeSid` at `0x18000c722`

## string_xrefs

- `0x18000c691`: `advapi32.dll`
- `0x18000c6b0`: `CheckTokenMembership`

## pseudocode

```c
__int64 __fastcall CheckToken(int *a1)
{
  unsigned int v2; // edi
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rsi
  PSID pSid; // [rsp+60h] [rbp-38h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-30h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v2 = 0;
  LibraryW = LoadLibraryW(L"advapi32.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "CheckTokenMembership");
    if ( ProcAddress )
    {
      *a1 = 0;
      v2 = 1;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        ((void (__fastcall *)(_QWORD, PSID, int *))ProcAddress)(0, pSid, a1);
        FreeSid(pSid);
      }
    }
    FreeLibrary(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c65c  mov     [rsp+arg_8], rbx
0x18000c661  mov     [rsp+arg_10], rbp
0x18000c666  push    rsi
0x18000c667  push    rdi
0x18000c668  push    r14
0x18000c66a  sub     rsp, 80h
0x18000c671  mov     rax, cs:__security_cookie
0x18000c678  xor     rax, rsp
0x18000c67b  mov     [rsp+98h+var_28], rax
0x18000c680  xor     ebp, ebp
0x18000c682  mov     word ptr [rsp+98h+pIdentifierAuthority.Value+4], 500h
0x18000c689  mov     r14, rcx
0x18000c68c  mov     [rsp+98h+var_38], rbp
0x18000c691  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18000c698  mov     dword ptr [rsp+98h+pIdentifierAuthority.Value], ebp
0x18000c69c  mov     edi, ebp
0x18000c69e  call    cs:__imp_LoadLibraryW
0x18000c6a4  mov     rbx, rax
0x18000c6a7  test    rax, rax
0x18000c6aa  jz      loc_18000C731
0x18000c6b0  lea     rdx, aChecktokenmemb; "CheckTokenMembership"
0x18000c6b7  mov     rcx, rax; hModule
0x18000c6ba  call    cs:__imp_GetProcAddress
0x18000c6c0  mov     rsi, rax
0x18000c6c3  test    rax, rax
0x18000c6c6  jz      short loc_18000C728
0x18000c6c8  lea     rax, [rsp+98h+var_38]
0x18000c6cd  mov     [r14], ebp
0x18000c6d0  mov     [rsp+98h+pSid], rax; pSid
0x18000c6d5  lea     r8d, [rbp+20h]; nSubAuthority0
0x18000c6d9  mov     [rsp+98h+nSubAuthority7], ebp; nSubAuthority7
0x18000c6dd  lea     rcx, [rsp+98h+pIdentifierAuthority]; pIdentifierAuthority
0x18000c6e2  mov     [rsp+98h+nSubAuthority6], ebp; nSubAuthority6
0x18000c6e6  lea     edi, [rbp+1]
0x18000c6e9  mov     [rsp+98h+nSubAuthority5], ebp; nSubAuthority5
0x18000c6ed  mov     r9d, 220h; nSubAuthority1
0x18000c6f3  mov     [rsp+98h+nSubAuthority4], ebp; nSubAuthority4
0x18000c6f7  mov     dl, 2; nSubAuthorityCount
0x18000c6f9  mov     [rsp+98h+nSubAuthority3], ebp; nSubAuthority3
0x18000c6fd  mov     [rsp+98h+nSubAuthority2], ebp; nSubAuthority2
0x18000c701  call    cs:__imp_AllocateAndInitializeSid
0x18000c707  test    eax, eax
0x18000c709  jz      short loc_18000C728
0x18000c70b  mov     rdx, [rsp+98h+var_38]
0x18000c710  mov     r8, r14
0x18000c713  xor     ecx, ecx
0x18000c715  mov     rax, rsi
0x18000c718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c71d  mov     rcx, [rsp+98h+var_38]; pSid
0x18000c722  call    cs:__imp_FreeSid
0x18000c728  mov     rcx, rbx; hLibModule
0x18000c72b  call    cs:__imp_FreeLibrary
0x18000c731  mov     eax, edi
0x18000c733  mov     rcx, [rsp+98h+var_28]
0x18000c738  xor     rcx, rsp; StackCookie
0x18000c73b  call    __security_check_cookie
0x18000c740  lea     r11, [rsp+98h+var_18]
0x18000c748  mov     rbx, [r11+28h]
0x18000c74c  mov     rbp, [r11+30h]
0x18000c750  mov     rsp, r11
0x18000c753  pop     r14
0x18000c755  pop     rdi
0x18000c756  pop     rsi
0x18000c757  retn
```
