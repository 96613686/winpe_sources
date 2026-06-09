# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(long)

- ea: `0x1800140f4`
- end: `0x180014173`
- name: `?InstrumentRemoveCIPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXJ@Z`
- size: `127`
- prototype: `void __fastcall(CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a6e4`
- `0x18002a7fb`

## callees

- `0x1800019bc`
- `0x180001fe4`
- `0x1800140f4`
- `0x180014ce4`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(
        CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *this,
        int a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r10
  __int64 v7; // r8
  int v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v4 = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  v5 = *(unsigned int *)v4;
  if ( (unsigned int)v5 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5) )
    {
      v7 = *((_QWORD *)this + 34);
      v8 = a2;
      v9 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&byte_180031F9F,
        v7 + 8,
        0,
        (__int64)&v9,
        (__int64)&v8);
    }
  }
}

```

## disassembly

```asm
0x1800140f4  mov     [rsp+arg_8], rbx
0x1800140f9  push    rdi
0x1800140fa  sub     rsp, 30h
0x1800140fe  mov     ebx, edx
0x180014100  mov     rdi, rcx
0x180014103  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180014108  mov     r10, rax
0x18001410b  mov     r8d, [rax]
0x18001410e  cmp     r8d, 5
0x180014112  jbe     short loc_180014168
0x180014114  mov     rdx, 400000000000h
0x18001411e  mov     rcx, rax
0x180014121  call    _tlgKeywordOn
0x180014126  test    al, al
0x180014128  jz      short loc_180014168
0x18001412a  mov     r8, [rdi+110h]
0x180014131  lea     rax, [rsp+38h+arg_0]
0x180014136  mov     [rsp+38h+var_10], rax
0x18001413b  lea     rdx, byte_180031F9F
0x180014142  lea     rax, [rsp+38h+arg_10]
0x180014147  mov     [rsp+38h+arg_0], ebx
0x18001414b  add     r8, 8
0x18001414f  mov     [rsp+38h+var_18], rax
0x180014154  xor     r9d, r9d
0x180014157  mov     [rsp+38h+arg_10], 2000000h
0x180014160  mov     rcx, r10
0x180014163  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180014168  mov     rbx, [rsp+38h+arg_8]
0x18001416d  add     rsp, 30h
0x180014171  pop     rdi
0x180014172  retn
```
