# DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,long &>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,long &)

- ea: `0x18000575c`
- end: `0x18000583c`
- name: `??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHAEAJ@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH1AEAJ@Z`
- size: `224`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007794`
- `0x180007a04`
- `0x180007a8c`

## callees

- `0x180001284`
- `0x180001358`
- `0x18000575c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800057d6`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800057d6`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800057c7`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800057c7`

## pseudocode

```c
__int64 __fastcall DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,long &>(
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
                 (unsigned int)word_180034DD2,
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
0x18000575c  push    rbp
0x18000575e  push    rbx
0x18000575f  push    rsi
0x180005760  push    rdi
0x180005761  lea     rbp, [rsp-3Fh]
0x180005766  sub     rsp, 98h
0x18000576d  mov     r11, rdx
0x180005770  mov     rdi, rcx
0x180005773  mov     r10d, cs:_tls_index
0x18000577a  mov     rax, gs:58h
0x180005783  mov     esi, 8
0x180005788  mov     rbx, [rax+r10*8]
0x18000578c  mov     byte ptr [rbx+rsi], 1
0x180005790  mov     eax, cs:dword_18003F000
0x180005796  cmp     eax, 5
0x180005799  jbe     loc_18000582C
0x18000579f  mov     edx, 1
0x1800057a4  call    _tlgKeywordOn
0x1800057a9  test    al, al
0x1800057ab  jz      short loc_18000582C
0x1800057ad  mov     eax, [r9]
0x1800057b0  mov     [rbp+57h+var_4C], eax
0x1800057b3  mov     eax, [r8]
0x1800057b6  mov     [rbp+57h+var_48], eax
0x1800057b9  mov     eax, [r11]
0x1800057bc  mov     [rbp+57h+var_44], eax
0x1800057bf  mov     eax, [rdi]
0x1800057c1  mov     [rbp+57h+var_40], eax
0x1800057c4  mov     [rbp+57h+var_50], dl
0x1800057c7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800057cd  mov     [rbp+57h+var_38], rax
0x1800057d1  mov     ecx, 10000003h
0x1800057d6  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800057dc  mov     [rbp+57h+var_30], rax
0x1800057e0  lea     rax, [rbp+57h+var_4C]
0x1800057e4  mov     [rsp+0B0h+var_60], rax
0x1800057e9  lea     rax, [rbp+57h+var_48]
0x1800057ed  mov     [rsp+0B0h+var_68], rax
0x1800057f2  lea     rax, [rbp+57h+var_44]
0x1800057f6  mov     [rsp+0B0h+var_70], rax
0x1800057fb  lea     rax, [rbp+57h+var_40]
0x1800057ff  mov     [rsp+0B0h+var_78], rax
0x180005804  lea     rax, [rbp+57h+var_50]
0x180005808  mov     [rsp+0B0h+var_80], rax
0x18000580d  lea     rax, [rbp+57h+var_38]
0x180005811  mov     [rsp+0B0h+var_88], rax
0x180005816  lea     rax, [rbp+57h+var_30]
0x18000581a  mov     [rsp+0B0h+var_90], rax
0x18000581f  lea     rdx, word_180034DD2
0x180005826  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000582b  nop
0x18000582c  mov     byte ptr [rbx+rsi], 0
0x180005830  add     rsp, 98h
0x180005837  pop     rdi
0x180005838  pop     rsi
0x180005839  pop     rbx
0x18000583a  pop     rbp
0x18000583b  retn
```
