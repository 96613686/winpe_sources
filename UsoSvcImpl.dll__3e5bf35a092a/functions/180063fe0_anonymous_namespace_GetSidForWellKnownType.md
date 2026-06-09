# _anonymous_namespace_::GetSidForWellKnownType

- ea: `0x180063fe0`
- end: `0x18006409b`
- name: `_anonymous_namespace_::GetSidForWellKnownType`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800640a4`

## callees

- `0x180010f24`
- `0x180063fe0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006401e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006401e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006404d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006404d`

## string_xrefs

- `0x180064077`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x180064089`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall anonymous_namespace_::GetSidForWellKnownType(_QWORD *a1, WELL_KNOWN_SID_TYPE a2)
{
  HLOCAL v4; // rax
  const char *v5; // r9
  const char *v6; // r9
  DWORD cbSid; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  v4 = LocalAlloc(0, 0x44u);
  *a1 = v4;
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
      v5);
  cbSid = 68;
  if ( !CreateWellKnownSid(a2, 0, v4, &cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x21,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
      v6);
  return a1;
}

```

## disassembly

```asm
0x180063fe0  mov     [rsp+arg_10], rbx
0x180063fe5  push    rdi
0x180063fe6  sub     rsp, 50h
0x180063fea  mov     rax, cs:__security_cookie
0x180063ff1  xor     rax, rsp
0x180063ff4  mov     [rsp+58h+var_18], rax
0x180063ff9  mov     edi, edx
0x180063ffb  mov     rbx, rcx
0x180063ffe  mov     [rsp+58h+var_30], rcx
0x180064003  mov     [rsp+58h+var_38], 0
0x18006400b  mov     [rsp+58h+var_28], 0
0x180064014  xor     eax, eax
0x180064016  mov     [rcx], rax
0x180064019  lea     edx, [rax+44h]; uBytes
0x18006401c  xor     ecx, ecx; uFlags
0x18006401e  call    cs:__imp_LocalAlloc
0x180064024  mov     [rbx], rax
0x180064027  mov     [rsp+58h+var_38], 1
0x18006402f  mov     rcx, [rsp+58h]; this
0x180064034  test    rax, rax
0x180064037  jz      short loc_180064089
0x180064039  mov     [rsp+58h+cbSid], 44h ; 'D'
0x180064041  lea     r9, [rsp+58h+cbSid]; cbSid
0x180064046  mov     r8, rax; pSid
0x180064049  xor     edx, edx; DomainSid
0x18006404b  mov     ecx, edi; WellKnownSidType
0x18006404d  call    cs:__imp_CreateWellKnownSid
0x180064053  mov     rcx, [rsp+58h]; this
0x180064058  test    eax, eax
0x18006405a  jz      short loc_180064077
0x18006405c  mov     rax, rbx
0x18006405f  mov     rcx, [rsp+58h+var_18]
0x180064064  xor     rcx, rsp; StackCookie
0x180064067  call    __security_check_cookie
0x18006406c  mov     rbx, [rsp+58h+arg_10]
0x180064071  add     rsp, 50h
0x180064075  pop     rdi
0x180064076  retn
0x180064077  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006407e  mov     edx, 21h ; '!'; void *
0x180064083  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180064089  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180064090  mov     edx, 1Eh; void *
0x180064095  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
