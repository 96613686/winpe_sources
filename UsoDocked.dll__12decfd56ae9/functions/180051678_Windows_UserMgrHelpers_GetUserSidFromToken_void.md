# Windows::UserMgrHelpers::GetUserSidFromToken(void *)

- ea: `0x180051678`
- end: `0x180051802`
- name: `?GetUserSidFromToken@UserMgrHelpers@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180051808`

## callees

- `0x180007dc0`
- `0x1800083e0`
- `0x18000856c`
- `0x180013ccc`
- `0x1800209fc`
- `0x180023a18`
- `0x180023a34`
- `0x180025cd0`
- `0x180051678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800516c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800516c2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180051729`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180051729`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800516b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051718`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800516b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051718`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051761`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051761`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051735`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051735`

## string_xrefs

- `0x180051788`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x1800517af`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x1800517c9`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x1800517db`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`
- `0x1800517f0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Windows::UserMgrHelpers::GetUserSidFromToken(_QWORD *a1, void *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  PSID *v6; // rdi
  const char *v7; // r9
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  const char *v10; // r9
  const char *v11; // r9
  unsigned int v13; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  size_t Size; // [rsp+70h] [rbp+18h] BYREF
  PSID *v17; // [rsp+78h] [rbp+20h]

  LODWORD(Size) = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, (PDWORD)&Size) )
  {
    v13 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      (const char *)v13,
      ReturnLength);
  }
  LastError = GetLastError();
  if ( LastError != 122 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      (const char *)LastError,
      ReturnLength);
  v5 = Size;
  v6 = (PSID *)operator new[]((unsigned int)Size);
  memset_0(v6, 0, v5);
  v17 = v6;
  if ( !GetTokenInformation(a2, TokenUser, v6, Size, (PDWORD)&Size) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v7);
  LengthSid = GetLengthSid(*v6);
  v9 = LocalAlloc(0, LengthSid);
  *a1 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v10);
  if ( !CopySid(LengthSid, v9, *v6) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v11);
  operator delete(v6);
  return a1;
}

```

## disassembly

```asm
0x180051678  mov     rax, rsp
0x18005167b  mov     [rax+10h], rbx
0x18005167f  mov     [rax+8], rcx
0x180051683  push    rbp
0x180051684  push    rsi
0x180051685  push    rdi
0x180051686  sub     rsp, 40h
0x18005168a  mov     rbp, rdx
0x18005168d  mov     rsi, rcx
0x180051690  mov     dword ptr [rax-28h], 0
0x180051697  mov     dword ptr [rax+18h], 0
0x18005169e  lea     rax, [rax+18h]
0x1800516a2  mov     qword ptr [rsp+58h+ReturnLength], rax; unsigned int
0x1800516a7  xor     r9d, r9d; TokenInformationLength
0x1800516aa  xor     r8d, r8d; TokenInformation
0x1800516ad  lea     edx, [r9+1]; TokenInformationClass
0x1800516b1  mov     rcx, rbp; TokenHandle
0x1800516b4  call    cs:__imp_GetTokenInformation
0x1800516ba  test    eax, eax
0x1800516bc  jnz     loc_18005179D
0x1800516c2  call    cs:__imp_GetLastError
0x1800516c8  cmp     eax, 7Ah ; 'z'
0x1800516cb  jnz     loc_1800517C1
0x1800516d1  mov     ebx, dword ptr [rsp+58h+Size]
0x1800516d5  mov     ecx, ebx; unsigned __int64
0x1800516d7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800516dc  mov     rdi, rax
0x1800516df  mov     r8d, ebx; Size
0x1800516e2  xor     edx, edx; Val
0x1800516e4  mov     rcx, rax; void *
0x1800516e7  call    memset_0
0x1800516ec  mov     [rsp+58h+var_28], 2
0x1800516f4  mov     [rsp+58h+arg_18], rdi
0x1800516f9  mov     rbx, [rsp+58h]
0x1800516fe  lea     rax, [rsp+58h+Size]
0x180051703  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x180051708  mov     r9d, dword ptr [rsp+58h+Size]; TokenInformationLength
0x18005170d  mov     r8, rdi; TokenInformation
0x180051710  mov     edx, 1; TokenInformationClass
0x180051715  mov     rcx, rbp; TokenHandle
0x180051718  call    cs:__imp_GetTokenInformation
0x18005171e  test    eax, eax
0x180051720  jz      loc_1800517DB
0x180051726  mov     rcx, [rdi]; pSid
0x180051729  call    cs:__imp_GetLengthSid
0x18005172f  mov     ebx, eax
0x180051731  mov     edx, eax; uBytes
0x180051733  xor     ecx, ecx; uFlags
0x180051735  call    cs:__imp_LocalAlloc
0x18005173b  mov     [rsi], rax
0x18005173e  mov     [rsp+58h+var_28], 3
0x180051746  mov     rcx, [rsp+58h]; this
0x18005174b  test    rax, rax
0x18005174e  jz      loc_1800517F0
0x180051754  mov     rbp, [rsp+58h]
0x180051759  mov     r8, [rdi]; pSourceSid
0x18005175c  mov     rdx, rax; pDestinationSid
0x18005175f  mov     ecx, ebx; nDestinationSidLength
0x180051761  call    cs:__imp_CopySid
0x180051767  test    eax, eax
0x180051769  jz      short loc_180051788
0x18005176b  mov     edx, 10h
0x180051770  mov     rcx, rdi; Block
0x180051773  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051778  mov     rax, rsi
0x18005177b  mov     rbx, [rsp+58h+arg_8]
0x180051780  add     rsp, 40h
0x180051784  pop     rdi
0x180051785  pop     rsi
0x180051786  pop     rbp
0x180051787  retn
0x180051788  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005178f  mov     edx, 4Ch ; 'L'; void *
0x180051794  mov     rcx, rbp; this
0x180051797  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005179d  mov     ecx, 8000FFFFh
0x1800517a2  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800517a7  mov     r9d, eax; char *
0x1800517aa  mov     rcx, [rsp+58h]; this
0x1800517af  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800517b6  mov     edx, 3Ah ; ':'; void *
0x1800517bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800517c1  mov     rcx, [rsp+58h]; this
0x1800517c6  mov     r9d, eax; char *
0x1800517c9  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800517d0  mov     edx, 34h ; '4'; void *
0x1800517d5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800517db  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800517e2  mov     edx, 47h ; 'G'; void *
0x1800517e7  mov     rcx, rbx; this
0x1800517ea  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800517f0  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800517f7  mov     edx, 4Bh ; 'K'; void *
0x1800517fc  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
