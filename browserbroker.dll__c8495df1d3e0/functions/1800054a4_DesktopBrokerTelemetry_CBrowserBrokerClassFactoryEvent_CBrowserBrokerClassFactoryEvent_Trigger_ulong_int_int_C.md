# DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,ulong &,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,ulong &,int &&,int &&)

- ea: `0x1800054a4`
- end: `0x180005584`
- name: `??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@AEAKHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@AEAK$$QEAH2@Z`
- size: `224`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007794`

## callees

- `0x180001284`
- `0x180001358`
- `0x1800054a4`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000551e`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18000551e`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000550f`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18000550f`

## pseudocode

```c
__int64 __fastcall DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,unsigned long &,int,int>(
        int *a1)
{
  __int64 v2; // rbx
  __int64 result; // rax
  char v4; // dl
  int *v5; // r8
  int *v6; // r9
  int *v7; // r11
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  _BYTE v11[4]; // [rsp+60h] [rbp+7h] BYREF
  int v12; // [rsp+64h] [rbp+Bh] BYREF
  int v13; // [rsp+68h] [rbp+Fh] BYREF
  int v14; // [rsp+6Ch] [rbp+13h] BYREF
  int v15; // [rsp+70h] [rbp+17h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v16; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v17[6]; // [rsp+80h] [rbp+27h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_BYTE *)(v2 + 8) = 1;
  result = (unsigned int)dword_18003F000;
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    result = tlgKeywordOn(a1, 1);
    if ( (_BYTE)result )
    {
      v12 = *v6;
      v13 = *v5;
      v14 = *v7;
      v15 = *a1;
      v11[0] = v4;
      v16 = GlobalThreadState();
      v17[0] = IEConfiguration_GetCLSID(268435459);
      result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                 v8,
                 (unsigned int)&word_18003508E,
                 v9,
                 v10,
                 (__int64)v17,
                 (__int64)&v16,
                 (__int64)v11,
                 (__int64)&v15,
                 (__int64)&v14,
                 (__int64)&v13,
                 (__int64)&v12);
    }
  }
  *(_BYTE *)(v2 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x1800054a4  push    rbp
0x1800054a6  push    rbx
0x1800054a7  push    rsi
0x1800054a8  push    rdi
0x1800054a9  lea     rbp, [rsp-3Fh]
0x1800054ae  sub     rsp, 98h
0x1800054b5  mov     r11, rdx
0x1800054b8  mov     rdi, rcx
0x1800054bb  mov     r10d, cs:_tls_index
0x1800054c2  mov     rax, gs:58h
0x1800054cb  mov     esi, 8
0x1800054d0  mov     rbx, [rax+r10*8]
0x1800054d4  mov     byte ptr [rbx+rsi], 1
0x1800054d8  mov     eax, cs:dword_18003F000
0x1800054de  cmp     eax, 5
0x1800054e1  jbe     loc_180005574
0x1800054e7  mov     edx, 1
0x1800054ec  call    _tlgKeywordOn
0x1800054f1  test    al, al
0x1800054f3  jz      short loc_180005574
0x1800054f5  mov     eax, [r9]
0x1800054f8  mov     [rbp+57h+var_4C], eax
0x1800054fb  mov     eax, [r8]
0x1800054fe  mov     [rbp+57h+var_48], eax
0x180005501  mov     eax, [r11]
0x180005504  mov     [rbp+57h+var_44], eax
0x180005507  mov     eax, [rdi]
0x180005509  mov     [rbp+57h+var_40], eax
0x18000550c  mov     [rbp+57h+var_50], dl
0x18000550f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180005515  mov     [rbp+57h+var_38], rax
0x180005519  mov     ecx, 10000003h
0x18000551e  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180005524  mov     [rbp+57h+var_30], rax
0x180005528  lea     rax, [rbp+57h+var_4C]
0x18000552c  mov     [rsp+0B0h+var_60], rax
0x180005531  lea     rax, [rbp+57h+var_48]
0x180005535  mov     [rsp+0B0h+var_68], rax
0x18000553a  lea     rax, [rbp+57h+var_44]
0x18000553e  mov     [rsp+0B0h+var_70], rax
0x180005543  lea     rax, [rbp+57h+var_40]
0x180005547  mov     [rsp+0B0h+var_78], rax
0x18000554c  lea     rax, [rbp+57h+var_50]
0x180005550  mov     [rsp+0B0h+var_80], rax
0x180005555  lea     rax, [rbp+57h+var_38]
0x180005559  mov     [rsp+0B0h+var_88], rax
0x18000555e  lea     rax, [rbp+57h+var_30]
0x180005562  mov     [rsp+0B0h+var_90], rax
0x180005567  lea     rdx, word_18003508E
0x18000556e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180005573  nop
0x180005574  mov     byte ptr [rbx+rsi], 0
0x180005578  add     rsp, 98h
0x18000557f  pop     rdi
0x180005580  pop     rsi
0x180005581  pop     rbx
0x180005582  pop     rbp
0x180005583  retn
```
