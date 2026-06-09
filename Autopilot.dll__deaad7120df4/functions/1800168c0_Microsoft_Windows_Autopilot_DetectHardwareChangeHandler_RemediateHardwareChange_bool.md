# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange(bool &)

- ea: `0x1800168c0`
- end: `0x180016b77`
- name: `?RemediateHardwareChange@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@AEAAJAEA_N@Z`
- size: `695`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017620`

## callees

- `0x1800016e4`
- `0x1800045d0`
- `0x180010764`
- `0x180013520`
- `0x180013618`
- `0x180013de4`
- `0x18001511c`
- `0x180015cd4`
- `0x180015db4`
- `0x1800167d8`
- `0x1800168c0`
- `0x1800179b8`
- `0x180017a20`
- `0x18001c190`
- `0x18001dcf4`

## string_xrefs

- `0x18001693e`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x180016b22`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange(
        Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *this,
        bool *a2)
{
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // ebx
  __int64 v7; // rdx
  int v9; // edi
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *AutopilotCorrelationVector; // rax
  int v16; // r8d
  int v17; // r9d
  __int64 *v18; // rdx
  __int64 TaskNameForType; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  int *v22; // [rsp+20h] [rbp-49h]
  char *v23; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  const wchar_t *v25; // [rsp+60h] [rbp-9h] BYREF
  const wchar_t *v26; // [rsp+68h] [rbp-1h] BYREF
  int v27[4]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v28; // [rsp+80h] [rbp+17h]
  int v29[2]; // [rsp+90h] [rbp+27h] BYREF
  __int64 *v30; // [rsp+98h] [rbp+2Fh]
  char v31; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  LODWORD(v23) = 0;
  *a2 = 0;
  v3 = Microsoft::Windows::Autopilot::HardwareInfo::MarkRemediationStatusIfNeeded((unsigned int *)&v23, a2);
  v6 = v3;
  if ( v3 < 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      LODWORD(v23) = v3;
      *(_QWORD *)&v28 = &v23;
      *((_QWORD *)&v28 + 1) = 4;
      v22 = v27;
      McGenEventWrite_EventWriteTransfer(v4, AutopilotDetectHardwareChangeRemediationReportFailed, v5, 2);
    }
    v7 = 223;
    goto LABEL_5;
  }
  v9 = (int)v23;
  if ( (_DWORD)v23 )
  {
    v10 = ZeroTouchProvCxhTelemetry::Provider();
    v12 = v10;
    v13 = *(unsigned int *)v10;
    if ( (unsigned int)v13 > 5 )
    {
      v14 = *((_QWORD *)v10 + 3);
      v13 = *((_QWORD *)v12 + 2);
      if ( (v13 & 0x800000000000LL) != 0 )
      {
        v13 = v14 & 0x800000000000LL;
        if ( (v14 & 0x800000000000LL) == v14 )
        {
          v24 = 0x2000000;
          LODWORD(v23) = v9;
          v25 = L"ForcedDelayWait";
          v26 = L"Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange";
          AutopilotCorrelationVector = (_QWORD *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v27);
          if ( AutopilotCorrelationVector[3] > 0xFu )
            AutopilotCorrelationVector = (_QWORD *)*AutopilotCorrelationVector;
          *(_QWORD *)v29 = AutopilotCorrelationVector;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (_DWORD)v12,
            (unsigned int)byte_18003B82D,
            v16,
            v17,
            (__int64)v29,
            (__int64)&v26,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v24);
          std::string::_Tidy_deallocate(v27);
        }
      }
    }
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      LODWORD(v23) = v9;
      *(_QWORD *)&v28 = &v23;
      *((_QWORD *)&v28 + 1) = 4;
      McGenEventWrite_EventWriteTransfer(v13, AutopilotDetectHardwareChangeEnforcedDelay, v11, 2);
    }
    return 2147947423LL;
  }
  if ( *a2 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      v18 = AutopilotDetectHardwareChangeTaskRemediateChanged;
LABEL_21:
      v22 = v29;
      McGenEventWrite_EventWriteTransfer(v4, v18, v5, 1);
    }
  }
  else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    v18 = AutopilotDetectHardwareChangeTaskRemediateNoChange;
    goto LABEL_21;
  }
  TaskNameForType = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType();
  v24 = TaskNameForType;
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v20, AutopilotDetectHardwareChangeTaskDisableStarted, TaskNameForType);
    TaskNameForType = v24;
  }
  LODWORD(v23) = -2147467263;
  *(_QWORD *)v29 = &v23;
  v30 = &v24;
  v31 = 1;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)(TaskNameForType + 2 * v21) );
  std::wstring::_Construct<1,unsigned short const *>(v27, TaskNameForType);
  LODWORD(v23) = Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask(v27);
  std::wstring::_Tidy_deallocate(v27);
  v6 = (int)v23;
  if ( (int)v23 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
      (const char *)(unsigned int)v23,
      (int)v22);
  wil::details::lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___::_lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___(v29);
  if ( v6 < 0 )
  {
    v7 = 255;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
      (const char *)(unsigned int)v6,
      (int)v22);
    return (unsigned int)v6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800168c0  mov     [rsp-8+arg_0], rbx
0x1800168c5  mov     [rsp-8+arg_10], rsi
0x1800168ca  push    rbp
0x1800168cb  push    rdi
0x1800168cc  push    r14
0x1800168ce  lea     rbp, [rsp-47h]
0x1800168d3  sub     rsp, 0B0h
0x1800168da  mov     rax, cs:__security_cookie
0x1800168e1  xor     rax, rsp
0x1800168e4  mov     [rbp+57h+var_18], rax
0x1800168e8  mov     rsi, rdx
0x1800168eb  xor     r14d, r14d
0x1800168ee  mov     dword ptr [rbp+57h+var_70], r14d
0x1800168f2  mov     [rdx], r14b
0x1800168f5  lea     rcx, [rbp+57h+var_70]; unsigned int *
0x1800168f9  call    ?MarkRemediationStatusIfNeeded@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAKAEA_N@Z; Microsoft::Windows::Autopilot::HardwareInfo::MarkRemediationStatusIfNeeded(ulong &,bool &)
0x1800168fe  mov     ebx, eax
0x180016900  test    eax, eax
0x180016902  jns     short loc_180016958
0x180016904  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001690b  jz      short loc_180016939
0x18001690d  mov     dword ptr [rbp+57h+var_70], eax
0x180016910  lea     rax, [rbp+57h+var_70]
0x180016914  mov     qword ptr [rbp+57h+var_40], rax
0x180016918  mov     qword ptr [rbp+57h+var_40+8], 4
0x180016920  lea     rax, [rbp+57h+var_50]
0x180016924  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180016929  lea     r9d, [r14+2]
0x18001692d  lea     rdx, AutopilotDetectHardwareChangeRemediationReportFailed
0x180016934  call    McGenEventWrite_EventWriteTransfer
0x180016939  mov     edx, 0DFh; void *
0x18001693e  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180016945  mov     r9d, ebx; char *
0x180016948  mov     rcx, [rbp+5Fh]; this
0x18001694c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016951  mov     eax, ebx
0x180016953  jmp     loc_180016B52
0x180016958  mov     edi, dword ptr [rbp+57h+var_70]
0x18001695b  test    edi, edi
0x18001695d  jz      loc_180016A5A
0x180016963  call    ?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ; ZeroTouchProvCxhTelemetry::Provider(void)
0x180016968  mov     rbx, rax
0x18001696b  mov     ecx, [rax]
0x18001696d  cmp     ecx, 5
0x180016970  jbe     loc_180016A19
0x180016976  mov     rax, [rax+18h]
0x18001697a  mov     rcx, [rbx+10h]
0x18001697e  mov     rdx, 800000000000h
0x180016988  test    rdx, rcx
0x18001698b  jz      loc_180016A19
0x180016991  mov     rcx, rax
0x180016994  and     rcx, rdx
0x180016997  cmp     rcx, rax
0x18001699a  jnz     short loc_180016A19
0x18001699c  mov     [rbp+57h+var_68], 2000000h
0x1800169a4  mov     dword ptr [rbp+57h+var_70], edi
0x1800169a7  lea     rax, aForceddelaywai; "ForcedDelayWait"
0x1800169ae  mov     [rbp+57h+var_60], rax
0x1800169b2  lea     rax, aMicrosoftWindo_1; "Microsoft::Windows::Autopilot::DetectHa"...
0x1800169b9  mov     [rbp+57h+var_58], rax
0x1800169bd  lea     rcx, [rbp+57h+var_50]
0x1800169c1  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x1800169c6  cmp     qword ptr [rax+18h], 0Fh
0x1800169cb  jbe     short loc_1800169D0
0x1800169cd  mov     rax, [rax]
0x1800169d0  mov     qword ptr [rbp+57h+var_30], rax
0x1800169d4  lea     rax, [rbp+57h+var_68]
0x1800169d8  mov     [rsp+0C0h+var_80], rax
0x1800169dd  lea     rax, [rbp+57h+var_70]
0x1800169e1  mov     [rsp+0C0h+var_88], rax
0x1800169e6  lea     rax, [rbp+57h+var_60]
0x1800169ea  mov     [rsp+0C0h+var_90], rax
0x1800169ef  lea     rax, [rbp+57h+var_58]
0x1800169f3  mov     [rsp+0C0h+var_98], rax
0x1800169f8  lea     rax, [rbp+57h+var_30]
0x1800169fc  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180016a01  lea     rdx, byte_18003B82D
0x180016a08  mov     rcx, rbx
0x180016a0b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180016a10  lea     rcx, [rbp+57h+var_50]
0x180016a14  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016a19  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 8
0x180016a20  jz      short loc_180016A50
0x180016a22  mov     dword ptr [rbp+57h+var_70], edi
0x180016a25  lea     rax, [rbp+57h+var_70]
0x180016a29  mov     qword ptr [rbp+57h+var_40], rax
0x180016a2d  mov     qword ptr [rbp+57h+var_40+8], 4
0x180016a35  lea     rax, [rbp+57h+var_50]
0x180016a39  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180016a3e  mov     r9d, 2
0x180016a44  lea     rdx, AutopilotDetectHardwareChangeEnforcedDelay
0x180016a4b  call    McGenEventWrite_EventWriteTransfer
0x180016a50  mov     eax, 8007139Fh
0x180016a55  jmp     loc_180016B52
0x180016a5a  mov     ebx, 1
0x180016a5f  cmp     [rsi], r14b
0x180016a62  jz      short loc_180016A75
0x180016a64  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x180016a6a  jz      short loc_180016A96
0x180016a6c  lea     rdx, AutopilotDetectHardwareChangeTaskRemediateChanged
0x180016a73  jmp     short loc_180016A85
0x180016a75  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180016a7c  jz      short loc_180016A96
0x180016a7e  lea     rdx, AutopilotDetectHardwareChangeTaskRemediateNoChange
0x180016a85  lea     rax, [rbp+57h+var_30]
0x180016a89  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180016a8e  mov     r9d, ebx
0x180016a91  call    McGenEventWrite_EventWriteTransfer
0x180016a96  call    ?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x180016a9b  mov     [rbp+57h+var_68], rax
0x180016a9f  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180016aa6  jz      short loc_180016ABB
0x180016aa8  mov     r8, rax
0x180016aab  lea     rdx, AutopilotDetectHardwareChangeTaskDisableStarted
0x180016ab2  call    McTemplateU0z_EventWriteTransfer
0x180016ab7  mov     rax, [rbp+57h+var_68]
0x180016abb  mov     dword ptr [rbp+57h+var_70], 80004001h
0x180016ac2  lea     rcx, [rbp+57h+var_70]
0x180016ac6  mov     qword ptr [rbp+57h+var_30], rcx
0x180016aca  lea     rcx, [rbp+57h+var_68]
0x180016ace  mov     [rbp+57h+var_28], rcx
0x180016ad2  mov     [rbp+57h+var_20], bl
0x180016ad5  xorps   xmm0, xmm0
0x180016ad8  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180016adc  xorps   xmm1, xmm1
0x180016adf  movdqu  [rbp+57h+var_40], xmm1
0x180016ae4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016ae8  inc     r8
0x180016aeb  cmp     [rax+r8*2], r14w
0x180016af0  jnz     short loc_180016AE8
0x180016af2  mov     rdx, rax
0x180016af5  lea     rcx, [rbp+57h+var_50]
0x180016af9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180016afe  nop
0x180016aff  lea     rcx, [rbp+57h+var_50]
0x180016b03  call    ?DisableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask(std::wstring const &)
0x180016b08  mov     dword ptr [rbp+57h+var_70], eax
0x180016b0b  lea     rcx, [rbp+57h+var_50]
0x180016b0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016b14  mov     ebx, dword ptr [rbp+57h+var_70]
0x180016b17  test    ebx, ebx
0x180016b19  jns     short loc_180016B36
0x180016b1b  mov     rcx, [rbp+5Fh]; this
0x180016b1f  mov     r9d, ebx; char *
0x180016b22  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180016b29  mov     edx, 0B8h; void *
0x180016b2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b33  nop
0x180016b34  jmp     short loc_180016B39
0x180016b36  mov     ebx, r14d
0x180016b39  lea     rcx, [rbp+57h+var_30]
0x180016b3d  call    wil__details__lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd______lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___
0x180016b42  test    ebx, ebx
0x180016b44  jns     short loc_180016B50
0x180016b46  mov     edx, 0FFh
0x180016b4b  jmp     loc_18001693E
0x180016b50  xor     eax, eax
0x180016b52  mov     rcx, [rbp+57h+var_18]
0x180016b56  xor     rcx, rsp; StackCookie
0x180016b59  call    __security_check_cookie
0x180016b5e  lea     r11, [rsp+0C0h+var_10]
0x180016b66  mov     rbx, [r11+20h]
0x180016b6a  mov     rsi, [r11+30h]
0x180016b6e  mov     rsp, r11
0x180016b71  pop     r14
0x180016b73  pop     rdi
0x180016b74  pop     rbp
0x180016b75  retn
```
