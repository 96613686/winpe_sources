# DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int &,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &,int &&)

- ea: `0x18000558c`
- end: `0x18000566c`
- name: `??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HAEAHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAHAEAH1@Z`
- size: `224`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007620`

## callees

- `0x180001284`
- `0x180001358`
- `0x18000558c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180005606`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180005606`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800055f7`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800055f7`

## pseudocode

```c
__int64 __fastcall DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int &,int>(
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
                 (unsigned int)word_180035002,
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
0x18000558c  push    rbp
0x18000558e  push    rbx
0x18000558f  push    rsi
0x180005590  push    rdi
0x180005591  lea     rbp, [rsp-3Fh]
0x180005596  sub     rsp, 98h
0x18000559d  mov     r11, rdx
0x1800055a0  mov     rdi, rcx
0x1800055a3  mov     r10d, cs:_tls_index
0x1800055aa  mov     rax, gs:58h
0x1800055b3  mov     esi, 8
0x1800055b8  mov     rbx, [rax+r10*8]
0x1800055bc  mov     byte ptr [rbx+rsi], 1
0x1800055c0  mov     eax, cs:dword_18003F000
0x1800055c6  cmp     eax, 5
0x1800055c9  jbe     loc_18000565C
0x1800055cf  mov     edx, 1
0x1800055d4  call    _tlgKeywordOn
0x1800055d9  test    al, al
0x1800055db  jz      short loc_18000565C
0x1800055dd  mov     eax, [r9]
0x1800055e0  mov     [rbp+57h+var_4C], eax
0x1800055e3  mov     eax, [r8]
0x1800055e6  mov     [rbp+57h+var_48], eax
0x1800055e9  mov     eax, [r11]
0x1800055ec  mov     [rbp+57h+var_44], eax
0x1800055ef  mov     eax, [rdi]
0x1800055f1  mov     [rbp+57h+var_40], eax
0x1800055f4  mov     [rbp+57h+var_50], dl
0x1800055f7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800055fd  mov     [rbp+57h+var_38], rax
0x180005601  mov     ecx, 10000003h
0x180005606  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18000560c  mov     [rbp+57h+var_30], rax
0x180005610  lea     rax, [rbp+57h+var_4C]
0x180005614  mov     [rsp+0B0h+var_60], rax
0x180005619  lea     rax, [rbp+57h+var_48]
0x18000561d  mov     [rsp+0B0h+var_68], rax
0x180005622  lea     rax, [rbp+57h+var_44]
0x180005626  mov     [rsp+0B0h+var_70], rax
0x18000562b  lea     rax, [rbp+57h+var_40]
0x18000562f  mov     [rsp+0B0h+var_78], rax
0x180005634  lea     rax, [rbp+57h+var_50]
0x180005638  mov     [rsp+0B0h+var_80], rax
0x18000563d  lea     rax, [rbp+57h+var_38]
0x180005641  mov     [rsp+0B0h+var_88], rax
0x180005646  lea     rax, [rbp+57h+var_30]
0x18000564a  mov     [rsp+0B0h+var_90], rax
0x18000564f  lea     rdx, word_180035002
0x180005656  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000565b  nop
0x18000565c  mov     byte ptr [rbx+rsi], 0
0x180005660  add     rsp, 98h
0x180005667  pop     rdi
0x180005668  pop     rsi
0x180005669  pop     rbx
0x18000566a  pop     rbp
0x18000566b  retn
```
