# _lambda_3e094a8d88a97ae8e9c36388a403dfb3_::operator()

- ea: `0x18005bcac`
- end: `0x18005bd74`
- name: `_lambda_3e094a8d88a97ae8e9c36388a403dfb3_::operator()`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050070`

## callees

- `0x18001a77c`
- `0x180022e68`
- `0x180023278`
- `0x1800281a4`
- `0x180034870`
- `0x18005bcac`
- `0x18005bd7c`
- `0x18005c028`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005bd16`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005bd16`

## string_xrefs

- `0x18005bcce`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18005bd2b`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
__int64 __fastcall lambda_3e094a8d88a97ae8e9c36388a403dfb3_::operator()(NgcUtils::Detail *a1)
{
  const unsigned __int16 *v2; // rdx
  int updated; // ebx
  __int64 v4; // rdx
  PSID *v5; // rax
  __int64 v6; // rcx
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  updated = NgcUtils::Detail::CacheUpdateVersion(a1);
  if ( updated < 0 )
  {
    v4 = 943;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)updated,
      v9);
    return (unsigned int)updated;
  }
  updated = NgcUtils::Detail::CacheRemoveUser(**(LPCWSTR **)a1, v2);
  if ( updated < 0 )
  {
    v4 = 945;
    goto LABEL_3;
  }
  v11 = 0;
  v5 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v11);
  if ( ConvertStringSidToSidW(**(LPCWSTR **)a1, v5) )
  {
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      McTemplateU0k_EventWriteTransfer(v6, EVENT_HFB_USERNAMESIDCACHE_REMOVED_USER, v11);
    updated = 0;
  }
  else
  {
    updated = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x3B6,
                (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                v7);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v11);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18005bcac  mov     [rsp+arg_0], rbx
0x18005bcb1  push    rdi; int
0x18005bcb2  sub     rsp, 20h
0x18005bcb6  mov     rdi, rcx
0x18005bcb9  call    ?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheUpdateVersion(void)
0x18005bcbe  mov     ebx, eax
0x18005bcc0  test    eax, eax
0x18005bcc2  jns     short loc_18005BCE2
0x18005bcc4  mov     edx, 3AFh; void *
0x18005bcc9  mov     rcx, [rsp+28h]; this
0x18005bcce  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005bcd5  mov     r9d, ebx; char *
0x18005bcd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bcdd  jmp     loc_18005BD66
0x18005bce2  mov     rcx, [rdi]
0x18005bce5  mov     rcx, [rcx]; lpSubKey
0x18005bce8  call    ?CacheRemoveUser@Detail@NgcUtils@@YAJQEBG@Z; NgcUtils::Detail::CacheRemoveUser(ushort const * const)
0x18005bced  mov     ebx, eax
0x18005bcef  test    eax, eax
0x18005bcf1  jns     short loc_18005BCFA
0x18005bcf3  mov     edx, 3B1h
0x18005bcf8  jmp     short loc_18005BCC9
0x18005bcfa  lea     rcx, [rsp+28h+arg_8]
0x18005bcff  mov     [rsp+28h+arg_8], 0
0x18005bd08  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x18005bd0d  mov     rcx, [rdi]
0x18005bd10  mov     rdx, rax; Sid
0x18005bd13  mov     rcx, [rcx]; StringSid
0x18005bd16  call    cs:__imp_ConvertStringSidToSidW
0x18005bd1d  nop     dword ptr [rax+rax+00h]
0x18005bd22  test    eax, eax
0x18005bd24  jnz     short loc_18005BD40
0x18005bd26  mov     rcx, [rsp+28h]; this
0x18005bd2b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005bd32  mov     edx, 3B6h; void *
0x18005bd37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005bd3c  mov     ebx, eax
0x18005bd3e  jmp     short loc_18005BD5C
0x18005bd40  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18005bd47  jz      short loc_18005BD5A
0x18005bd49  mov     r8, [rsp+28h+arg_8]
0x18005bd4e  lea     rdx, EVENT_HFB_USERNAMESIDCACHE_REMOVED_USER
0x18005bd55  call    McTemplateU0k_EventWriteTransfer
0x18005bd5a  xor     ebx, ebx
0x18005bd5c  lea     rcx, [rsp+28h+arg_8]
0x18005bd61  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005bd66  mov     eax, ebx
0x18005bd68  mov     rbx, [rsp+28h+arg_0]
0x18005bd6d  add     rsp, 20h
0x18005bd71  pop     rdi
0x18005bd72  retn
```
