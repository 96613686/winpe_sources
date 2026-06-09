# _lambda_ce445c862fe53406fef30ea5c4d9fcd6_::operator()

- ea: `0x180054484`
- end: `0x18005453f`
- name: `_lambda_ce445c862fe53406fef30ea5c4d9fcd6_::operator()`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053e58`

## callees

- `0x180018194`
- `0x18001a77c`
- `0x1800264b8`
- `0x180054484`
- `0x1800545a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544bd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800544ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800544ad`

## pseudocode

```c
__int64 __fastcall lambda_ce445c862fe53406fef30ea5c4d9fcd6_::operator()(__int64 a1)
{
  DWORD LastError; // eax
  signed int IsAccountEnabled; // ebx
  DWORD v5; // [rsp+40h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp+10h] BYREF

  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(**(PSID **)a1, &StringSid) )
  {
    IsAccountEnabled = NgcPreboot::IsAccountEnabled(
                         StringSid,
                         **(unsigned int **)(a1 + 8),
                         **(_QWORD **)(a1 + 16),
                         **(_QWORD **)(a1 + 24));
  }
  else
  {
    LastError = GetLastError();
    IsAccountEnabled = LastError;
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v5 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AD7A5,
        0,
        0,
        (__int64)&v5);
    }
    if ( IsAccountEnabled > 0 )
      IsAccountEnabled = (unsigned __int16)IsAccountEnabled | 0x80070000;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  return (unsigned int)IsAccountEnabled;
}

```

## disassembly

```asm
0x180054484  push    rbx
0x180054486  sub     rsp, 30h
0x18005448a  mov     rbx, rcx
0x18005448d  mov     [rsp+38h+StringSid], 0
0x180054496  lea     rcx, [rsp+38h+StringSid]
0x18005449b  xor     edx, edx
0x18005449d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800544a2  mov     rcx, [rbx]
0x1800544a5  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800544aa  mov     rcx, [rcx]; Sid
0x1800544ad  call    cs:__imp_ConvertSidToStringSidW
0x1800544b4  nop     dword ptr [rax+rax+00h]
0x1800544b9  test    eax, eax
0x1800544bb  jnz     short loc_18005450C
0x1800544bd  call    cs:__imp_GetLastError
0x1800544c4  nop     dword ptr [rax+rax+00h]
0x1800544c9  mov     ecx, cs:dword_1800BE0B8
0x1800544cf  mov     ebx, eax
0x1800544d1  cmp     ecx, 2
0x1800544d4  jbe     short loc_1800544FD
0x1800544d6  mov     [rsp+38h+arg_0], eax
0x1800544da  lea     rdx, byte_1800AD7A5
0x1800544e1  lea     rax, [rsp+38h+arg_0]
0x1800544e6  xor     r9d, r9d
0x1800544e9  xor     r8d, r8d
0x1800544ec  mov     [rsp+38h+var_18], rax
0x1800544f1  lea     rcx, dword_1800BE0B8
0x1800544f8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800544fd  test    ebx, ebx
0x1800544ff  jle     short loc_18005452C
0x180054501  movzx   ebx, bx
0x180054504  or      ebx, 80070000h
0x18005450a  jmp     short loc_18005452C
0x18005450c  mov     r9, [rbx+18h]
0x180054510  mov     r8, [rbx+10h]
0x180054514  mov     rdx, [rbx+8]
0x180054518  mov     rcx, [rsp+38h+StringSid]
0x18005451d  mov     r9, [r9]
0x180054520  mov     r8, [r8]
0x180054523  mov     edx, [rdx]
0x180054525  call    ?IsAccountEnabled@NgcPreboot@@YAJPEBGW4AccountCapability@1@PEA_N2@Z; NgcPreboot::IsAccountEnabled(ushort const *,NgcPreboot::AccountCapability,bool *,bool *)
0x18005452a  mov     ebx, eax
0x18005452c  lea     rcx, [rsp+38h+StringSid]
0x180054531  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180054536  mov     eax, ebx
0x180054538  add     rsp, 30h
0x18005453c  pop     rbx
0x18005453d  retn
```
