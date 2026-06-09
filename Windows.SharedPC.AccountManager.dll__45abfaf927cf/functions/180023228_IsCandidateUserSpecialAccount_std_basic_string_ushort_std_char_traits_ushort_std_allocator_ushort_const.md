# IsCandidateUserSpecialAccount(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023228`
- end: `0x180023310`
- name: `?IsCandidateUserSpecialAccount@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015ee0`
- `0x180016eb8`

## callees

- `0x1800042c0`
- `0x180006e2c`
- `0x180007328`
- `0x18000a548`
- `0x18001138c`
- `0x180013dcc`
- `0x180023228`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023287`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023261`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023261`
- `ntdll!RtlIsMultiSessionSku` at `0x18002323e`
- `ntdll!RtlIsMultiSessionSku` at `0x18002323e`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x1800232e0`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x1800232e0`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x1800232bf`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x1800232bf`

## string_xrefs

- `0x180023295`: `shellcommon\shell\sharedpc\accountmanager\lib\util\specialaccountsutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char IsCandidateUserSpecialAccount()
{
  HLOCAL v0; // rbx
  const WCHAR *v1; // rax
  const char *v2; // r9
  __int64 v3; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  int v6; // [rsp+48h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+30h] BYREF
  char v8; // [rsp+58h] [rbp+38h] BYREF

  hMem = 0;
  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    goto LABEL_13;
  v0 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
    LocalFree(v0);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
  }
  hMem = 0;
  v1 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( !ConvertStringSidToSidW(v1, &hMem) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\specialaccountsutils.cpp",
      v2);
  if ( (v6 = 0, (unsigned __int8)IsCamIsEphemeralCandidateUserPresent(retaddr))
    && (int)CamIsCandidateUser(hMem, &v6) >= 0
    && v6
    || (unsigned __int8)IsCamIsEphemeralCandidateUserPresent(v3)
    && (int)CamIsEphemeralCandidateUser(hMem, &v6) >= 0
    && v6 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return 1;
  }
  else
  {
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return 0;
  }
}

```

## disassembly

```asm
0x180023228  push    rbp
0x18002322a  push    rbx
0x18002322b  push    rdi
0x18002322c  mov     rbp, rsp
0x18002322f  sub     rsp, 20h
0x180023233  mov     rdi, rcx
0x180023236  mov     [rbp+hMem], 0
0x18002323e  call    cs:__imp_RtlIsMultiSessionSku
0x180023244  test    al, al
0x180023246  jz      loc_1800232FD
0x18002324c  mov     rbx, [rbp+hMem]
0x180023250  test    rbx, rbx
0x180023253  jz      short loc_180023270
0x180023255  lea     rcx, [rbp+arg_18]; this
0x180023259  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002325e  mov     rcx, rbx; hMem
0x180023261  call    cs:__imp_LocalFree
0x180023267  lea     rcx, [rbp+arg_18]; this
0x18002326b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180023270  mov     [rbp+hMem], 0
0x180023278  mov     rcx, rdi
0x18002327b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180023280  lea     rdx, [rbp+hMem]; Sid
0x180023284  mov     rcx, rax; StringSid
0x180023287  call    cs:__imp_ConvertStringSidToSidW
0x18002328d  mov     rcx, [rbp+18h]; this
0x180023291  test    eax, eax
0x180023293  jnz     short loc_1800232A7
0x180023295  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002329c  mov     edx, 81h; void *
0x1800232a1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800232a7  mov     [rbp+arg_8], 0
0x1800232ae  call    IsCamIsEphemeralCandidateUserPresent
0x1800232b3  test    al, al
0x1800232b5  jz      short loc_1800232CF
0x1800232b7  lea     rdx, [rbp+arg_8]
0x1800232bb  mov     rcx, [rbp+hMem]
0x1800232bf  call    cs:__imp_CamIsCandidateUser
0x1800232c5  test    eax, eax
0x1800232c7  js      short loc_1800232CF
0x1800232c9  cmp     [rbp+arg_8], 0
0x1800232cd  jnz     short loc_1800232F0
0x1800232cf  call    IsCamIsEphemeralCandidateUserPresent
0x1800232d4  test    al, al
0x1800232d6  jz      short loc_1800232FD
0x1800232d8  lea     rdx, [rbp+arg_8]
0x1800232dc  mov     rcx, [rbp+hMem]
0x1800232e0  call    cs:__imp_CamIsEphemeralCandidateUser
0x1800232e6  test    eax, eax
0x1800232e8  js      short loc_1800232FD
0x1800232ea  cmp     [rbp+arg_8], 0
0x1800232ee  jz      short loc_1800232FD
0x1800232f0  lea     rcx, [rbp+hMem]
0x1800232f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800232f9  mov     al, 1
0x1800232fb  jmp     short loc_180023308
0x1800232fd  lea     rcx, [rbp+hMem]
0x180023301  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023306  xor     al, al
0x180023308  add     rsp, 20h
0x18002330c  pop     rdi
0x18002330d  pop     rbx
0x18002330e  pop     rbp
0x18002330f  retn
```
