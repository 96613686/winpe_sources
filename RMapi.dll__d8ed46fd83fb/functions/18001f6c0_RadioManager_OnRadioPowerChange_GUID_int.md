# RadioManager::OnRadioPowerChange(_GUID,int)

- ea: `0x18001f6c0`
- end: `0x18001f863`
- name: `?OnRadioPowerChange@RadioManager@@UEAAJU_GUID@@H@Z`
- size: `419`
- prototype: `int(RadioManager *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006200`
- `0x180006a2c`
- `0x180009614`
- `0x18000b814`
- `0x18000be90`
- `0x180019da0`
- `0x18001f250`
- `0x18001f6c0`
- `0x180023308`

## string_xrefs

- `0x18001f78a`: `No action taken because Modern APM is disabled via registry`

## pseudocode

```c
__int64 __fastcall RadioManager::OnRadioPowerChange(RadioManager *this, struct _GUID *a2, int a3)
{
  RMAPI *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // rax
  unsigned __int8 *v15; // rdx
  wil *v16; // rcx
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+40h] [rbp-48h] BYREF
  const wchar_t *v21; // [rsp+48h] [rbp-40h] BYREF
  __int64 v22[2]; // [rsp+50h] [rbp-38h] BYREF
  struct _GUID v23; // [rsp+60h] [rbp-28h] BYREF
  int v24; // [rsp+70h] [rbp-18h]
  int v25; // [rsp+74h] [rbp-14h]
  char *v26; // [rsp+78h] [rbp-10h]

  v23 = *a2;
  if ( (unsigned __int8)IsWiFiOrBluetooth(&v23) )
  {
    if ( RMAPI::IsModernAirplaneModeDisabled(v6) )
    {
      if ( (unsigned int)dword_180037050 > 4 )
      {
        *(_QWORD *)&v23.Data1 = RmGuidToMediaTypeString(a2);
        v14 = "No action taken because Modern APM is disabled via registry";
        v15 = (unsigned __int8 *)&unk_18002F820;
LABEL_11:
        v21 = (const wchar_t *)v14;
        v22[0] = (__int64)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v11,
          v15,
          v12,
          v13,
          &v21,
          v22,
          (const wchar_t **)&v23);
      }
    }
    else
    {
      ProtectedSystemState::GetSystemState((char *)this + 24, &v23);
      if ( !v23.Data4[0] )
      {
        try
        {
          v23 = (struct _GUID)0LL;
          v25 = 0;
          v23 = *a2;
          v24 = a3;
          v26 = (char *)this - 24;
          WcmCommon::ThreadPoolWorkQueue::SubmitWork__RadioManager::OnRadioPowerChange_::_33_::_lambda_1___(
            (__int64)this + 416,
            (__int64)&v23);
        }
        catch ( ... )
        {
          v17 = wil::ResultFromCaughtException(v16);
          LODWORD(v21) = v17;
          if ( (unsigned int)dword_180037050 > 2 )
          {
            v20 = v17;
            *(_QWORD *)&v23.Data1 = "std::exception thrown trying to submit a workitem";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)dword_180037050,
              (unsigned __int8 *)byte_18002F785,
              v18,
              v19,
              (const wchar_t **)&v23,
              (__int64)&v20);
          }
          return (unsigned int)v21;
        }
        return 0;
      }
      if ( (unsigned int)dword_180037050 > 4 )
      {
        *(_QWORD *)&v23.Data1 = RmGuidToMediaTypeString(a2);
        v14 = "SystemRadioState is ON, no action taken";
        v15 = (unsigned __int8 *)byte_18002F7CB;
        goto LABEL_11;
      }
    }
    return 0;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)dword_180037050 > 2 )
  {
    v20 = -2147024809;
    v21 = (const wchar_t *)RmGuidToMediaTypeString(a2);
    v22[0] = (__int64)a2;
    *(_QWORD *)&v23.Data1 = "Invalid RM GUID - only Wlan and Bluetooth RM GUIDs are supported";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned __int8 *)byte_18002F875,
      v8,
      v9,
      (const wchar_t **)&v23,
      v22,
      &v21,
      (__int64)&v20);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001f6c0  mov     rax, rsp
0x18001f6c3  mov     [rax+10h], rbx
0x18001f6c7  mov     [rax+18h], rsi
0x18001f6cb  push    rdi
0x18001f6cc  sub     rsp, 80h
0x18001f6d3  mov     esi, r8d
0x18001f6d6  mov     rbx, rdx
0x18001f6d9  mov     rdi, rcx
0x18001f6dc  movups  xmm0, xmmword ptr [rdx]
0x18001f6df  movdqu  xmmword ptr [rax-28h], xmm0
0x18001f6e4  lea     rcx, [rax-28h]; Buf1
0x18001f6e8  call    IsWiFiOrBluetooth
0x18001f6ed  test    al, al
0x18001f6ef  jnz     short loc_18001F765
0x18001f6f1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f6f6  mov     eax, cs:dword_180037050
0x18001f6fc  cmp     eax, 2
0x18001f6ff  jbe     short loc_18001F75B
0x18001f701  mov     [rsp+88h+var_48], 80070057h
0x18001f709  mov     rcx, rbx; struct _GUID *
0x18001f70c  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001f711  mov     [rsp+88h+var_40], rax
0x18001f716  mov     [rsp+88h+var_38], rbx
0x18001f71b  lea     rax, aInvalidRmGuidO; "Invalid RM GUID - only Wlan and Bluetoo"...
0x18001f722  mov     qword ptr [rsp+88h+var_28], rax
0x18001f727  lea     rax, [rsp+88h+var_48]
0x18001f72c  mov     [rsp+88h+var_50], rax
0x18001f731  lea     rax, [rsp+88h+var_40]
0x18001f736  mov     [rsp+88h+var_58], rax
0x18001f73b  lea     rax, [rsp+88h+var_38]
0x18001f740  mov     [rsp+88h+var_60], rax
0x18001f745  lea     rax, [rsp+88h+var_28]
0x18001f74a  mov     [rsp+88h+var_68], rax
0x18001f74f  lea     rdx, byte_18002F875
0x18001f756  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001f75b  mov     eax, 80070057h
0x18001f760  jmp     loc_18001F84E
0x18001f765  call    ?IsModernAirplaneModeDisabled@RMAPI@@YA_NXZ; RMAPI::IsModernAirplaneModeDisabled(void)
0x18001f76a  test    al, al
0x18001f76c  jz      short loc_18001F79A
0x18001f76e  mov     eax, cs:dword_180037050
0x18001f774  cmp     eax, 4
0x18001f777  jbe     loc_18001F802
0x18001f77d  mov     rcx, rbx; struct _GUID *
0x18001f780  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001f785  mov     qword ptr [rsp+88h+var_28], rax
0x18001f78a  lea     rax, aNoActionTakenB; "No action taken because Modern APM is d"...
0x18001f791  lea     rdx, unk_18002F820
0x18001f798  jmp     short loc_18001F7D5
0x18001f79a  lea     rcx, [rdi+18h]
0x18001f79e  lea     rdx, [rsp+88h+var_28]
0x18001f7a3  call    ?GetSystemState@ProtectedSystemState@@QEBA?AUSystemState@@XZ; ProtectedSystemState::GetSystemState(void)
0x18001f7a8  cmp     byte ptr [rsp+88h+var_28+8], 0
0x18001f7ad  jz      short loc_18001F806
0x18001f7af  mov     eax, cs:dword_180037050
0x18001f7b5  cmp     eax, 4
0x18001f7b8  jbe     short loc_18001F802
0x18001f7ba  mov     rcx, rbx; struct _GUID *
0x18001f7bd  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x18001f7c2  mov     qword ptr [rsp+88h+var_28], rax
0x18001f7c7  lea     rax, aSystemradiosta; "SystemRadioState is ON, no action taken"
0x18001f7ce  lea     rdx, byte_18002F7CB
0x18001f7d5  mov     [rsp+88h+var_40], rax
0x18001f7da  lea     rax, [rsp+88h+var_28]
0x18001f7df  mov     [rsp+88h+var_58], rax
0x18001f7e4  lea     rax, [rsp+88h+var_38]
0x18001f7e9  mov     [rsp+88h+var_60], rax
0x18001f7ee  lea     rax, [rsp+88h+var_40]
0x18001f7f3  mov     [rsp+88h+var_68], rax
0x18001f7f8  mov     [rsp+88h+var_38], rbx
0x18001f7fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18001f802  xor     eax, eax
0x18001f804  jmp     short loc_18001F84E
0x18001f806  mov     qword ptr [rsp+88h+var_28], 0
0x18001f80f  mov     qword ptr [rsp+88h+var_28+8], 0
0x18001f818  mov     [rsp+88h+var_14], 0
0x18001f820  movups  xmm0, xmmword ptr [rbx]
0x18001f823  movdqu  [rsp+88h+var_28], xmm0
0x18001f829  mov     [rsp+88h+var_18], esi
0x18001f82d  lea     rax, [rdi-18h]
0x18001f831  mov     [rsp+88h+var_10], rax
0x18001f836  lea     rcx, [rdi+1A0h]
0x18001f83d  lea     rdx, [rsp+88h+var_28]
0x18001f842  call    WcmCommon__ThreadPoolWorkQueue__SubmitWork__RadioManager__OnRadioPowerChange____33____lambda_1___
0x18001f847  nop
0x18001f848  jmp     short loc_18001F802
0x18001f84a  mov     eax, dword ptr [rsp+88h+var_40]
0x18001f84e  lea     r11, [rsp+88h+var_8]
0x18001f856  mov     rbx, [r11+18h]
0x18001f85a  mov     rsi, [r11+20h]
0x18001f85e  mov     rsp, r11
0x18001f861  pop     rdi
0x18001f862  retn
```
