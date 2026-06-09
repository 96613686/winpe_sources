# CTreeWalker::GetDefaultMailAppExecutionInfo(_STORAGE_EXECUTION_INFO *)

- ea: `0x180040c08`
- end: `0x180040d9b`
- name: `?GetDefaultMailAppExecutionInfo@CTreeWalker@@QEAAJPEAU_STORAGE_EXECUTION_INFO@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(CTreeWalker *__hidden this, struct _STORAGE_EXECUTION_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037620`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012734`
- `0x180012c9c`
- `0x180040c08`
- `0x180041398`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040d38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040d38`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180040d19`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180040d19`
- `RPCRT4!RpcRevertToSelf` at `0x180040d6b`
- `RPCRT4!RpcRevertToSelf` at `0x180040d6b`
- `RPCRT4!RpcImpersonateClient` at `0x180040c63`
- `RPCRT4!RpcImpersonateClient` at `0x180040c63`

## pseudocode

```c
__int64 __fastcall CTreeWalker::GetDefaultMailAppExecutionInfo(CTreeWalker *this, struct _STORAGE_EXECUTION_INFO *a2)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  int (__fastcall *v7)(_QWORD, __int64, const wchar_t *); // rax
  const WCHAR *FileNameW; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-268h]
  WCHAR pszPath[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  memset_0(pszPath, 0, 0x208u);
  if ( !a2 )
    return 2147942487LL;
  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *((_DWORD *)a2 + 1) = 2;
    StringCchCopyW((wchar_t *)a2 + 4, 0x104u, L"outlookmail:");
    StringCchCopyW((wchar_t *)a2 + 264, 0x104u, &word_180092AF0);
    if ( !*((_QWORD *)this + 44) )
      CTreeWalker::LoadDependencies(this);
    v7 = (int (__fastcall *)(_QWORD, __int64, const wchar_t *))*((_QWORD *)this + 44);
    if ( v7 && v7(0, 2, L"mailto") >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath);
      if ( CompareStringOrdinal(FileNameW, -1, L"outlook.exe", -1, 1) == 2 )
      {
        *((_DWORD *)a2 + 1) = 1;
        StringCchCopyW((wchar_t *)a2 + 4, 0x104u, L"outlook.exe");
        StringCchCopyW((wchar_t *)a2 + 264, 0x104u, L"/recycle");
      }
    }
    RpcRevertToSelf();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\treewalker\\treewalker.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    return v6;
  }
}

```

## disassembly

```asm
0x180040c08  mov     [rsp+arg_10], rbx
0x180040c0d  mov     [rsp+arg_18], rbp
0x180040c12  push    rsi
0x180040c13  push    rdi
0x180040c14  push    r14
0x180040c16  sub     rsp, 270h
0x180040c1d  mov     rax, cs:__security_cookie
0x180040c24  xor     rax, rsp
0x180040c27  mov     [rsp+288h+var_28], rax
0x180040c2f  mov     rdi, rdx
0x180040c32  mov     rsi, rcx
0x180040c35  xor     edx, edx; Val
0x180040c37  lea     rcx, [rsp+288h+pszPath]; void *
0x180040c3c  mov     r8d, 208h; Size
0x180040c42  call    memset_0
0x180040c47  mov     r14d, 104h
0x180040c4d  mov     [rsp+288h+var_248], r14d
0x180040c52  test    rdi, rdi
0x180040c55  jnz     short loc_180040C61
0x180040c57  mov     eax, 80070057h
0x180040c5c  jmp     loc_180040D73
0x180040c61  xor     ecx, ecx; BindingHandle
0x180040c63  call    cs:__imp_RpcImpersonateClient
0x180040c69  mov     ebx, eax
0x180040c6b  test    eax, eax
0x180040c6d  jns     short loc_180040C92
0x180040c6f  mov     rcx, [rsp+288h]; this
0x180040c77  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\storage\\storsvc\\tre"...
0x180040c7e  mov     r9d, eax; char *
0x180040c81  mov     edx, 1E5h; void *
0x180040c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c8b  mov     eax, ebx
0x180040c8d  jmp     loc_180040D73
0x180040c92  lea     r8, aOutlookmail; "outlookmail:"
0x180040c99  mov     dword ptr [rdi+4], 2
0x180040ca0  mov     rdx, r14; unsigned __int64
0x180040ca3  lea     rcx, [rdi+8]; wchar_t *
0x180040ca7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180040cac  lea     rbp, [rdi+210h]
0x180040cb3  mov     rdx, r14; unsigned __int64
0x180040cb6  mov     rcx, rbp; wchar_t *
0x180040cb9  lea     r8, word_180092AF0; wchar_t *
0x180040cc0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180040cc5  cmp     qword ptr [rsi+160h], 0
0x180040ccd  jnz     short loc_180040CD7
0x180040ccf  mov     rcx, rsi; this
0x180040cd2  call    ?LoadDependencies@CTreeWalker@@QEAAXXZ; CTreeWalker::LoadDependencies(void)
0x180040cd7  mov     rax, [rsi+160h]
0x180040cde  test    rax, rax
0x180040ce1  jz      loc_180040D6B
0x180040ce7  lea     rcx, [rsp+288h+var_248]
0x180040cec  xor     r9d, r9d
0x180040cef  mov     [rsp+288h+var_260], rcx
0x180040cf4  lea     r8, aMailto; "mailto"
0x180040cfb  lea     rcx, [rsp+288h+pszPath]
0x180040d00  mov     qword ptr [rsp+288h+bIgnoreCase], rcx
0x180040d05  xor     ecx, ecx
0x180040d07  lea     edx, [r9+2]
0x180040d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d10  test    eax, eax
0x180040d12  js      short loc_180040D6B
0x180040d14  lea     rcx, [rsp+288h+pszPath]; pszPath
0x180040d19  call    cs:__imp_PathFindFileNameW
0x180040d1f  or      edx, 0FFFFFFFFh; cchCount1
0x180040d22  lea     r8, aOutlookExe; "outlook.exe"
0x180040d29  mov     esi, 1
0x180040d2e  mov     r9d, edx; cchCount2
0x180040d31  mov     rcx, rax; lpString1
0x180040d34  mov     [rsp+288h+bIgnoreCase], esi; bIgnoreCase
0x180040d38  call    cs:__imp_CompareStringOrdinal
0x180040d3e  cmp     eax, 2
0x180040d41  jnz     short loc_180040D6B
0x180040d43  lea     r8, aOutlookExe; "outlook.exe"
0x180040d4a  mov     [rdi+4], esi
0x180040d4d  mov     rdx, r14; unsigned __int64
0x180040d50  lea     rcx, [rdi+8]; wchar_t *
0x180040d54  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180040d59  lea     r8, aRecycle; "/recycle"
0x180040d60  mov     rdx, r14; unsigned __int64
0x180040d63  mov     rcx, rbp; wchar_t *
0x180040d66  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180040d6b  call    cs:__imp_RpcRevertToSelf
0x180040d71  xor     eax, eax
0x180040d73  mov     rcx, [rsp+288h+var_28]
0x180040d7b  xor     rcx, rsp; StackCookie
0x180040d7e  call    __security_check_cookie
0x180040d83  lea     r11, [rsp+288h+var_18]
0x180040d8b  mov     rbx, [r11+30h]
0x180040d8f  mov     rbp, [r11+38h]
0x180040d93  mov     rsp, r11
0x180040d96  pop     r14
0x180040d98  pop     rdi
0x180040d99  pop     rsi
0x180040d9a  retn
```
