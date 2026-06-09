# CMidi2MidiSrvConfigurationManager::UpdateConfiguration(ushort const *,ushort * *)

- ea: `0x18000c480`
- end: `0x18000c563`
- name: `?UpdateConfiguration@CMidi2MidiSrvConfigurationManager@@UEAAJPEBGPEAPEAG@Z`
- size: `227`
- prototype: `__int64 __fastcall(CMidi2MidiSrvConfigurationManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180001998`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c480`
- `0x180013bf4`

## string_xrefs

- `0x18000c527`: `avcore\midi2\transport\midisrvtransport\midi2.midisrvconfigurationmanager.cpp`
- `0x18000c4a8`: `Entering UpdateConfiguration`
- `0x18000c4c3`: `CMidi2MidiSrvConfigurationManager::UpdateConfiguration`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvConfigurationManager::UpdateConfiguration(
        CMidi2MidiSrv **this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  CMidi2MidiSrv *v9; // rcx
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-58h]
  const wchar_t *v13; // [rsp+50h] [rbp-28h] BYREF
  CMidi2MidiSrvConfigurationManager *v14; // [rsp+58h] [rbp-20h] BYREF
  int v15[2]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned __int16 **v17; // [rsp+80h] [rbp+8h] BYREF
  const unsigned __int16 *v18; // [rsp+98h] [rbp+20h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v17 = a3;
    v13 = L"Entering UpdateConfiguration";
    v18 = a2;
    *(_QWORD *)v15 = "CMidi2MidiSrvConfigurationManager::UpdateConfiguration";
    v14 = (CMidi2MidiSrvConfigurationManager *)this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)word_18001A0BA,
      v7,
      v8,
      (__int64)v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v18,
      (__int64)&v17);
  }
  v9 = this[3];
  if ( v9 )
  {
    return (unsigned int)CMidi2MidiSrv::UpdateConfiguration(v9, a2, a3);
  }
  else
  {
    v10 = -2147221008;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvconfigurationmanager.cpp",
      (const char *)0x800401F0LL,
      v12);
  }
  return v10;
}

```

## disassembly

```asm
0x18000c480  mov     [rsp+arg_8], rbx
0x18000c485  mov     [rsp+arg_10], rsi
0x18000c48a  push    rdi
0x18000c48b  sub     rsp, 70h
0x18000c48f  mov     rdi, r8
0x18000c492  mov     rsi, rdx
0x18000c495  mov     rbx, rcx
0x18000c498  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c49d  mov     rcx, [rax+8]
0x18000c4a1  mov     eax, [rcx]
0x18000c4a3  cmp     eax, 4
0x18000c4a6  jbe     short loc_18000C519
0x18000c4a8  lea     rax, aEnteringUpdate; "Entering UpdateConfiguration"
0x18000c4af  mov     [rsp+78h+arg_0], rdi
0x18000c4b7  mov     [rsp+78h+var_28], rax
0x18000c4bc  lea     rdx, word_18001A0BA
0x18000c4c3  lea     rax, aCmidi2midisrvc_0; "CMidi2MidiSrvConfigurationManager::Upda"...
0x18000c4ca  mov     [rsp+78h+arg_18], rsi
0x18000c4d2  mov     qword ptr [rsp+78h+var_18], rax
0x18000c4d7  lea     rax, [rsp+78h+arg_0]
0x18000c4df  mov     [rsp+78h+var_38], rax
0x18000c4e4  lea     rax, [rsp+78h+arg_18]
0x18000c4ec  mov     [rsp+78h+var_40], rax
0x18000c4f1  lea     rax, [rsp+78h+var_28]
0x18000c4f6  mov     [rsp+78h+var_48], rax
0x18000c4fb  lea     rax, [rsp+78h+var_20]
0x18000c500  mov     [rsp+78h+var_50], rax
0x18000c505  lea     rax, [rsp+78h+var_18]
0x18000c50a  mov     qword ptr [rsp+78h+var_58], rax; int
0x18000c50f  mov     [rsp+78h+var_20], rbx
0x18000c514  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18000c519  mov     rcx, [rbx+18h]; this
0x18000c51d  test    rcx, rcx
0x18000c520  jnz     short loc_18000C542
0x18000c522  mov     rcx, [rsp+78h]; this
0x18000c527  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c52e  mov     ebx, 800401F0h
0x18000c533  mov     edx, 3Bh ; ';'; void *
0x18000c538  mov     r9d, ebx; char *
0x18000c53b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c540  jmp     short loc_18000C54F
0x18000c542  mov     r8, rdi; unsigned __int16 **
0x18000c545  mov     rdx, rsi; unsigned __int16 *
0x18000c548  call    ?UpdateConfiguration@CMidi2MidiSrv@@QEAAJPEBGPEAPEAG@Z; CMidi2MidiSrv::UpdateConfiguration(ushort const *,ushort * *)
0x18000c54d  mov     ebx, eax
0x18000c54f  lea     r11, [rsp+78h+var_8]
0x18000c554  mov     eax, ebx
0x18000c556  mov     rbx, [r11+18h]
0x18000c55a  mov     rsi, [r11+20h]
0x18000c55e  mov     rsp, r11
0x18000c561  pop     rdi
0x18000c562  retn
```
