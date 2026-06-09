# Windows::Internal::CapabilityAccess::Private::GetSidStringFromSid(void * const)

- ea: `0x1800229c4`
- end: `0x180022a44`
- name: `?GetSidStringFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAX@Z`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180022d2c`
- `0x180022d88`

## callees

- `0x18000a248`
- `0x180021530`
- `0x1800229c4`
- `0x180023690`
- `0x180023ae4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800229fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800229fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetSidStringFromSid(__int64 a1, void *a2)
{
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPWSTR StringSid; // [rsp+50h] [rbp+18h] BYREF

  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  std::wstring::wstring(a1, (__int64)StringSid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return a1;
}

```

## disassembly

```asm
0x1800229c4  mov     rax, rsp
0x1800229c7  mov     [rax+8], rbx
0x1800229cb  mov     [rax+10h], rsi
0x1800229cf  push    rdi
0x1800229d0  sub     rsp, 30h
0x1800229d4  mov     rbx, rdx
0x1800229d7  mov     rdi, rcx
0x1800229da  mov     qword ptr [rax+18h], 0
0x1800229e2  xor     edx, edx
0x1800229e4  lea     rcx, [rax+18h]
0x1800229e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800229ed  mov     rsi, [rsp+38h]
0x1800229f2  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800229f7  mov     rcx, rbx; Sid
0x1800229fa  call    cs:__imp_ConvertSidToStringSidW
0x180022a00  test    eax, eax
0x180022a02  jnz     short loc_180022A19
0x180022a04  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022a0b  mov     edx, 2D5h; void *
0x180022a10  mov     rcx, rsi; this
0x180022a13  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180022a19  mov     rdx, [rsp+38h+StringSid]
0x180022a1e  mov     rcx, rdi
0x180022a21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022a26  nop
0x180022a27  lea     rcx, [rsp+38h+StringSid]
0x180022a2c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180022a31  mov     rax, rdi
0x180022a34  mov     rbx, [rsp+38h+arg_0]
0x180022a39  mov     rsi, [rsp+38h+arg_8]
0x180022a3e  add     rsp, 30h
0x180022a42  pop     rdi
0x180022a43  retn
```
