# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitCiPolicy(CodeIntegrity::Management::SiPolicyView const &)

- ea: `0x180013d14`
- end: `0x180013de7`
- name: `?InstrumentCommitCiPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z`
- size: `211`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this, const struct CodeIntegrity::Management::SiPolicyView *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800128f0`

## callees

- `0x1800019bc`
- `0x180001da4`
- `0x18000828c`
- `0x180013d14`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitCiPolicy(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this,
        const struct CodeIntegrity::Management::SiPolicyView *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  int *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // [rsp+50h] [rbp-18h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF
  int *v12; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF

  v4 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  v5 = *(unsigned int *)v4;
  if ( (unsigned int)v5 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5) )
    {
      v11 = *((_QWORD *)a2 + 2);
      v6 = (int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v7 = *((_QWORD *)this + 34);
      v12 = v6;
      v13 = *((_QWORD *)a2 + 1);
      v9 = *(_QWORD *)a2;
      v10 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v8,
        (__int64)&dword_180031FDC,
        v7 + 8,
        v8,
        (__int64)&v10,
        &v9,
        &v13,
        &v12,
        (__int64)&v11);
    }
  }
}

```

## disassembly

```asm
0x180013d14  mov     [rsp+arg_8], rbx
0x180013d19  push    rdi
0x180013d1a  sub     rsp, 60h
0x180013d1e  mov     rbx, rdx
0x180013d21  mov     rdi, rcx
0x180013d24  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180013d29  mov     r9, rax
0x180013d2c  mov     r8d, [rax]
0x180013d2f  cmp     r8d, 5
0x180013d33  jbe     loc_180013DDC
0x180013d39  mov     rdx, 400000000000h
0x180013d43  mov     rcx, rax
0x180013d46  call    _tlgKeywordOn
0x180013d4b  test    al, al
0x180013d4d  jz      loc_180013DDC
0x180013d53  mov     rcx, [rbx+10h]
0x180013d57  mov     [rsp+68h+arg_0], rcx
0x180013d5c  lea     rcx, [rbx+18h]
0x180013d60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013d65  mov     r8, [rdi+110h]
0x180013d6c  lea     rdx, dword_180031FDC
0x180013d73  mov     [rsp+68h+arg_10], rax
0x180013d7b  add     r8, 8
0x180013d7f  mov     rax, [rbx+8]
0x180013d83  mov     rcx, r9
0x180013d86  mov     [rsp+68h+arg_18], rax
0x180013d8e  mov     rax, [rbx]
0x180013d91  mov     [rsp+68h+var_18], rax
0x180013d96  lea     rax, [rsp+68h+arg_0]
0x180013d9b  mov     [rsp+68h+var_28], rax
0x180013da0  lea     rax, [rsp+68h+arg_10]
0x180013da8  mov     [rsp+68h+var_30], rax
0x180013dad  lea     rax, [rsp+68h+arg_18]
0x180013db5  mov     [rsp+68h+var_38], rax
0x180013dba  lea     rax, [rsp+68h+var_18]
0x180013dbf  mov     [rsp+68h+var_40], rax
0x180013dc4  lea     rax, [rsp+68h+var_10]
0x180013dc9  mov     [rsp+68h+var_48], rax
0x180013dce  mov     [rsp+68h+var_10], 2000000h
0x180013dd7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180013ddc  mov     rbx, [rsp+68h+arg_8]
0x180013de1  add     rsp, 60h
0x180013de5  pop     rdi
0x180013de6  retn
```
