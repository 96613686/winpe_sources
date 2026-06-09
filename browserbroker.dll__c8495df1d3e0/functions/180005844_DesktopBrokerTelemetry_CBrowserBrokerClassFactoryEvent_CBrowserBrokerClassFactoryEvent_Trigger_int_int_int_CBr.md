# DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(CBrowserBrokerClassFactoryEvent_Trigger &&,int &&,int &&,int &&)

- ea: `0x180005844`
- end: `0x180005924`
- name: `??$CBrowserBrokerClassFactoryEvent@W4CBrowserBrokerClassFactoryEvent_Trigger@@HHH@DesktopBrokerTelemetry@@SAX$$QEAW4CBrowserBrokerClassFactoryEvent_Trigger@@$$QEAH11@Z`
- size: `224`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008060`

## callees

- `0x180001284`
- `0x180001358`
- `0x180005844`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800058be`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800058be`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800058af`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800058af`

## pseudocode

```c
__int64 __fastcall DesktopBrokerTelemetry::CBrowserBrokerClassFactoryEvent<enum CBrowserBrokerClassFactoryEvent_Trigger,int,int,int>(
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
                 (unsigned int)word_180034EEA,
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
0x180005844  push    rbp
0x180005846  push    rbx
0x180005847  push    rsi
0x180005848  push    rdi
0x180005849  lea     rbp, [rsp-3Fh]
0x18000584e  sub     rsp, 98h
0x180005855  mov     r11, rdx
0x180005858  mov     rdi, rcx
0x18000585b  mov     r10d, cs:_tls_index
0x180005862  mov     rax, gs:58h
0x18000586b  mov     esi, 8
0x180005870  mov     rbx, [rax+r10*8]
0x180005874  mov     byte ptr [rbx+rsi], 1
0x180005878  mov     eax, cs:dword_18003F000
0x18000587e  cmp     eax, 5
0x180005881  jbe     loc_180005914
0x180005887  mov     edx, 1
0x18000588c  call    _tlgKeywordOn
0x180005891  test    al, al
0x180005893  jz      short loc_180005914
0x180005895  mov     eax, [r9]
0x180005898  mov     [rbp+57h+var_4C], eax
0x18000589b  mov     eax, [r8]
0x18000589e  mov     [rbp+57h+var_48], eax
0x1800058a1  mov     eax, [r11]
0x1800058a4  mov     [rbp+57h+var_44], eax
0x1800058a7  mov     eax, [rdi]
0x1800058a9  mov     [rbp+57h+var_40], eax
0x1800058ac  mov     [rbp+57h+var_50], dl
0x1800058af  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800058b5  mov     [rbp+57h+var_38], rax
0x1800058b9  mov     ecx, 10000003h
0x1800058be  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800058c4  mov     [rbp+57h+var_30], rax
0x1800058c8  lea     rax, [rbp+57h+var_4C]
0x1800058cc  mov     [rsp+0B0h+var_60], rax
0x1800058d1  lea     rax, [rbp+57h+var_48]
0x1800058d5  mov     [rsp+0B0h+var_68], rax
0x1800058da  lea     rax, [rbp+57h+var_44]
0x1800058de  mov     [rsp+0B0h+var_70], rax
0x1800058e3  lea     rax, [rbp+57h+var_40]
0x1800058e7  mov     [rsp+0B0h+var_78], rax
0x1800058ec  lea     rax, [rbp+57h+var_50]
0x1800058f0  mov     [rsp+0B0h+var_80], rax
0x1800058f5  lea     rax, [rbp+57h+var_38]
0x1800058f9  mov     [rsp+0B0h+var_88], rax
0x1800058fe  lea     rax, [rbp+57h+var_30]
0x180005902  mov     [rsp+0B0h+var_90], rax
0x180005907  lea     rdx, word_180034EEA
0x18000590e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180005913  nop
0x180005914  mov     byte ptr [rbx+rsi], 0
0x180005918  add     rsp, 98h
0x18000591f  pop     rdi
0x180005920  pop     rsi
0x180005921  pop     rbx
0x180005922  pop     rbp
0x180005923  retn
```
