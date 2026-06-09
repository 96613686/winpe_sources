# Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002294c`
- end: `0x1800229bc`
- name: `?GetSidFromSidString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180021808`

## callees

- `0x18001b444`
- `0x18002294c`
- `0x180023690`
- `0x180023b8c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002298c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002298c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSID *__fastcall Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(PSID *Sid, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  const WCHAR *v7; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    Sid,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v4, v5, v6);
  if ( !ConvertStringSidToSidW(v7, Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v8);
  return Sid;
}

```

## disassembly

```asm
0x18002294c  mov     rax, rsp
0x18002294f  mov     [rax+10h], rbx
0x180022953  mov     [rax+8], rcx
0x180022957  push    rdi
0x180022958  sub     rsp, 30h
0x18002295c  mov     rbx, rdx
0x18002295f  mov     rdi, rcx
0x180022962  mov     dword ptr [rax-18h], 0
0x180022969  mov     qword ptr [rcx], 0
0x180022970  mov     dword ptr [rax-18h], 1
0x180022977  xor     edx, edx
0x180022979  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002297e  mov     rcx, rbx
0x180022981  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022986  mov     rdx, rdi; Sid
0x180022989  mov     rcx, rax; StringSid
0x18002298c  call    cs:__imp_ConvertStringSidToSidW
0x180022992  test    eax, eax
0x180022994  jnz     short loc_1800229AD
0x180022996  mov     rcx, [rsp+38h]; this
0x18002299b  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800229a2  mov     edx, 2DCh; void *
0x1800229a7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800229ad  mov     rax, rdi
0x1800229b0  mov     rbx, [rsp+38h+arg_8]
0x1800229b5  add     rsp, 30h
0x1800229b9  pop     rdi
0x1800229ba  retn
```
