# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitSbcpToken(CodeIntegrity::Management::AuthorizationToken const &)

- ea: `0x180013f00`
- end: `0x180013f9f`
- name: `?InstrumentCommitSbcpToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z`
- size: `159`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this, const struct CodeIntegrity::Management::AuthorizationToken *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800128f0`

## callees

- `0x1800019bc`
- `0x180001b28`
- `0x18000828c`
- `0x180013f00`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitSbcpToken(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this,
        const struct CodeIntegrity::Management::AuthorizationToken *a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  int *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  int *v8; // [rsp+50h] [rbp+8h] BYREF
  int *v9; // [rsp+60h] [rbp+18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  v3 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  v4 = *(unsigned int *)v3;
  if ( (unsigned int)v4 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    {
      v8 = (int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v5 = (int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v6 = *((_QWORD *)this + 34);
      v9 = v5;
      v10 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)&byte_18003203F,
        v6 + 8,
        v7,
        (__int64)&v10,
        &v9,
        &v8);
    }
  }
}

```

## disassembly

```asm
0x180013f00  mov     [rsp+arg_8], rbx
0x180013f05  push    rdi
0x180013f06  sub     rsp, 40h
0x180013f0a  mov     rbx, rdx
0x180013f0d  mov     rdi, rcx
0x180013f10  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180013f15  mov     r9, rax
0x180013f18  mov     r8d, [rax]
0x180013f1b  cmp     r8d, 5
0x180013f1f  jbe     short loc_180013F94
0x180013f21  mov     rdx, 400000000000h
0x180013f2b  mov     rcx, rax
0x180013f2e  call    _tlgKeywordOn
0x180013f33  test    al, al
0x180013f35  jz      short loc_180013F94
0x180013f37  lea     rcx, [rbx+18h]
0x180013f3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013f40  lea     rcx, [rbx+38h]
0x180013f44  mov     [rsp+48h+arg_0], rax
0x180013f49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013f4e  mov     r8, [rdi+110h]
0x180013f55  lea     rdx, byte_18003203F
0x180013f5c  mov     [rsp+48h+arg_10], rax
0x180013f61  add     r8, 8
0x180013f65  lea     rax, [rsp+48h+arg_0]
0x180013f6a  mov     [rsp+48h+arg_18], 2000000h
0x180013f73  mov     [rsp+48h+var_18], rax
0x180013f78  mov     rcx, r9
0x180013f7b  lea     rax, [rsp+48h+arg_10]
0x180013f80  mov     [rsp+48h+var_20], rax
0x180013f85  lea     rax, [rsp+48h+arg_18]
0x180013f8a  mov     [rsp+48h+var_28], rax
0x180013f8f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180013f94  mov     rbx, [rsp+48h+arg_8]
0x180013f99  add     rsp, 40h
0x180013f9d  pop     rdi
0x180013f9e  retn
```
