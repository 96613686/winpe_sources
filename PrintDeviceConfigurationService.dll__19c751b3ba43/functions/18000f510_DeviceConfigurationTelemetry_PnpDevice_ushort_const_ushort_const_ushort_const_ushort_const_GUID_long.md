# DeviceConfigurationTelemetry::PnpDevice_(ushort const *,ushort const *,ushort const *,ushort const *,_GUID,long)

- ea: `0x18000f510`
- end: `0x18000f5db`
- name: `?PnpDevice_@DeviceConfigurationTelemetry@@QEAAXPEBG000U_GUID@@J@Z`
- size: `203`
- prototype: `void __fastcall(DeviceConfigurationTelemetry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ed18`

## callees

- `0x18000172c`
- `0x1800018d0`
- `0x18000ad98`
- `0x18000f510`

## pseudocode

```c
void __fastcall DeviceConfigurationTelemetry::PnpDevice_(
        DeviceConfigurationTelemetry *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct _GUID *a6,
        int a7)
{
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r10
  __int64 v14; // [rsp+60h] [rbp-11h] BYREF
  struct _GUID *v15; // [rsp+68h] [rbp-9h] BYREF
  int *v16; // [rsp+70h] [rbp-1h] BYREF
  int *v17; // [rsp+78h] [rbp+7h] BYREF
  int *v18; // [rsp+80h] [rbp+Fh] BYREF
  int *v19; // [rsp+88h] [rbp+17h] BYREF
  DeviceConfigurationTelemetry *v20; // [rsp+C0h] [rbp+4Fh] BYREF

  v20 = this;
  v10 = DeviceConfigurationLogging::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
    {
      v15 = a6;
      v16 = (int *)a5;
      LODWORD(v20) = a7;
      v14 = 0x1000000;
      v17 = (int *)a4;
      v18 = (int *)a3;
      v19 = (int *)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v13,
        (__int64)byte_18001F4F3,
        v11,
        v12,
        &v19,
        &v18,
        &v17,
        &v16,
        (__int64 *)&v15,
        (__int64)&v20,
        (__int64)&v14);
    }
  }
}

```

## disassembly

```asm
0x18000f510  mov     [rsp-8+arg_0], rcx
0x18000f515  push    rbp
0x18000f516  push    rbx
0x18000f517  push    rsi
0x18000f518  push    rdi
0x18000f519  lea     rbp, [rsp-27h]
0x18000f51e  sub     rsp, 98h
0x18000f525  mov     rbx, r9
0x18000f528  mov     rdi, r8
0x18000f52b  mov     rsi, rdx
0x18000f52e  call    ?Provider@DeviceConfigurationLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceConfigurationLogging::Provider(void)
0x18000f533  mov     r10, rax
0x18000f536  mov     ecx, [rax]
0x18000f538  cmp     ecx, 5
0x18000f53b  jbe     loc_18000F5CF
0x18000f541  mov     rdx, 400000000000h
0x18000f54b  mov     rcx, rax
0x18000f54e  call    _tlgKeywordOn
0x18000f553  test    al, al
0x18000f555  jz      short loc_18000F5CF
0x18000f557  mov     rax, [rbp+3Fh+arg_28]
0x18000f55b  lea     rdx, byte_18001F4F3
0x18000f562  mov     ecx, [rbp+3Fh+arg_30]
0x18000f565  mov     [rbp+3Fh+var_48], rax
0x18000f569  mov     rax, [rbp+3Fh+arg_20]
0x18000f56d  mov     [rbp+3Fh+var_40], rax
0x18000f571  lea     rax, [rbp+3Fh+var_50]
0x18000f575  mov     [rsp+0B0h+var_60], rax
0x18000f57a  lea     rax, [rbp+3Fh+arg_0]
0x18000f57e  mov     [rsp+0B0h+var_68], rax
0x18000f583  lea     rax, [rbp+3Fh+var_48]
0x18000f587  mov     [rsp+0B0h+var_70], rax
0x18000f58c  lea     rax, [rbp+3Fh+var_40]
0x18000f590  mov     [rsp+0B0h+var_78], rax
0x18000f595  lea     rax, [rbp+3Fh+var_38]
0x18000f599  mov     [rsp+0B0h+var_80], rax
0x18000f59e  lea     rax, [rbp+3Fh+var_30]
0x18000f5a2  mov     [rsp+0B0h+var_88], rax
0x18000f5a7  lea     rax, [rbp+3Fh+var_28]
0x18000f5ab  mov     dword ptr [rbp+3Fh+arg_0], ecx
0x18000f5ae  mov     rcx, r10
0x18000f5b1  mov     [rsp+0B0h+var_90], rax
0x18000f5b6  mov     [rbp+3Fh+var_50], 1000000h
0x18000f5be  mov     [rbp+3Fh+var_38], rbx
0x18000f5c2  mov     [rbp+3Fh+var_30], rdi
0x18000f5c6  mov     [rbp+3Fh+var_28], rsi
0x18000f5ca  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000f5cf  add     rsp, 98h
0x18000f5d6  pop     rdi
0x18000f5d7  pop     rsi
0x18000f5d8  pop     rbx
0x18000f5d9  pop     rbp
0x18000f5da  retn
```
