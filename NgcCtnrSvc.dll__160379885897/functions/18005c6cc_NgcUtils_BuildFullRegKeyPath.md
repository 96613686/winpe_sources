# NgcUtils::BuildFullRegKeyPath

- ea: `0x18005c6cc`
- end: `0x18005c77f`
- name: `NgcUtils::BuildFullRegKeyPath`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005c9ac`

## callees

- `0x180018194`
- `0x18001a77c`
- `0x1800264b8`
- `0x18005c6cc`
- `0x18005c788`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c709`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005c6f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005c6f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::BuildFullRegKeyPath(PSID *a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp+18h] BYREF

  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(*a1, &StringSid) )
  {
    v3 = NgcUtils::BuildFullRegKeyPath_0(StringSid);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v5 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&word_1800AE5D6,
        0,
        0,
        (__int64)&v5);
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  return v3;
}

```

## disassembly

```asm
0x18005c6cc  mov     [rsp+arg_8], rbx
0x18005c6d1  push    rdi
0x18005c6d2  sub     rsp, 30h
0x18005c6d6  mov     rdi, rdx
0x18005c6d9  mov     rbx, rcx
0x18005c6dc  mov     [rsp+38h+StringSid], 0
0x18005c6e5  xor     edx, edx
0x18005c6e7  lea     rcx, [rsp+38h+StringSid]
0x18005c6ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005c6f1  lea     rdx, [rsp+38h+StringSid]; StringSid
0x18005c6f6  mov     rcx, [rbx]; Sid
0x18005c6f9  call    cs:__imp_ConvertSidToStringSidW
0x18005c700  nop     dword ptr [rax+rax+00h]
0x18005c705  test    eax, eax
0x18005c707  jnz     short loc_18005C758
0x18005c709  call    cs:__imp_GetLastError
0x18005c710  nop     dword ptr [rax+rax+00h]
0x18005c715  mov     ebx, eax
0x18005c717  test    eax, eax
0x18005c719  jle     short loc_18005C724
0x18005c71b  movzx   ebx, ax
0x18005c71e  or      ebx, 80070000h
0x18005c724  mov     eax, cs:dword_1800BE0B8
0x18005c72a  cmp     eax, 2
0x18005c72d  jbe     short loc_18005C767
0x18005c72f  mov     [rsp+38h+arg_0], ebx
0x18005c733  lea     rax, [rsp+38h+arg_0]
0x18005c738  mov     [rsp+38h+var_18], rax
0x18005c73d  xor     r9d, r9d
0x18005c740  xor     r8d, r8d
0x18005c743  lea     rdx, word_1800AE5D6
0x18005c74a  lea     rcx, dword_1800BE0B8
0x18005c751  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005c756  jmp     short loc_18005C767
0x18005c758  mov     rdx, rdi
0x18005c75b  mov     rcx, [rsp+38h+StringSid]; unsigned __int16 *
0x18005c760  call    NgcUtils__BuildFullRegKeyPath_0
0x18005c765  mov     ebx, eax
0x18005c767  lea     rcx, [rsp+38h+StringSid]
0x18005c76c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005c771  mov     eax, ebx
0x18005c773  mov     rbx, [rsp+38h+arg_8]
0x18005c778  add     rsp, 30h
0x18005c77c  pop     rdi
0x18005c77d  retn
```
