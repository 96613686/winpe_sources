# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackSbcpToken(CodeIntegrity::Management::AuthorizationToken const &)

- ea: `0x180014734`
- end: `0x1800147d3`
- name: `?InstrumentRollbackSbcpToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z`
- size: `159`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this, const struct CodeIntegrity::Management::AuthorizationToken *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180014d20`

## callees

- `0x1800019bc`
- `0x180001b28`
- `0x18000828c`
- `0x180014734`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackSbcpToken(
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
        (__int64)&unk_180031F50,
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
0x180014734  mov     [rsp+arg_8], rbx
0x180014739  push    rdi
0x18001473a  sub     rsp, 40h
0x18001473e  mov     rbx, rdx
0x180014741  mov     rdi, rcx
0x180014744  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180014749  mov     r9, rax
0x18001474c  mov     r8d, [rax]
0x18001474f  cmp     r8d, 5
0x180014753  jbe     short loc_1800147C8
0x180014755  mov     rdx, 400000000000h
0x18001475f  mov     rcx, rax
0x180014762  call    _tlgKeywordOn
0x180014767  test    al, al
0x180014769  jz      short loc_1800147C8
0x18001476b  lea     rcx, [rbx+18h]
0x18001476f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014774  lea     rcx, [rbx+38h]
0x180014778  mov     [rsp+48h+arg_0], rax
0x18001477d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014782  mov     r8, [rdi+110h]
0x180014789  lea     rdx, unk_180031F50
0x180014790  mov     [rsp+48h+arg_10], rax
0x180014795  add     r8, 8
0x180014799  lea     rax, [rsp+48h+arg_0]
0x18001479e  mov     [rsp+48h+arg_18], 2000000h
0x1800147a7  mov     [rsp+48h+var_18], rax
0x1800147ac  mov     rcx, r9
0x1800147af  lea     rax, [rsp+48h+arg_10]
0x1800147b4  mov     [rsp+48h+var_20], rax
0x1800147b9  lea     rax, [rsp+48h+arg_18]
0x1800147be  mov     [rsp+48h+var_28], rax
0x1800147c3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800147c8  mov     rbx, [rsp+48h+arg_8]
0x1800147cd  add     rsp, 40h
0x1800147d1  pop     rdi
0x1800147d2  retn
```
