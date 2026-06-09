# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange(bool &)

- ea: `0x180016420`
- end: `0x1800166d6`
- name: `?RemediateHardwareChange@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@AEAAJAEA_N@Z`
- size: `694`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017100`

## callees

- `0x1800016dc`
- `0x1800045b0`
- `0x1800105f4`
- `0x180013280`
- `0x180013370`
- `0x180013a40`
- `0x180014d24`
- `0x180015898`
- `0x180015978`
- `0x180016344`
- `0x180016420`
- `0x180017488`
- `0x1800174f0`
- `0x18001ba54`
- `0x18001d55c`

## string_xrefs

- `0x18001649e`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x180016682`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

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
            (unsigned int)byte_18003A82D,
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
  std::wstring::_Construct<1,unsigned short const *>(v27, TaskNameForType, v21);
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
0x180016420  mov     [rsp-8+arg_0], rbx
0x180016425  mov     [rsp-8+arg_10], rsi
0x18001642a  push    rbp
0x18001642b  push    rdi
0x18001642c  push    r14
0x18001642e  lea     rbp, [rsp-47h]
0x180016433  sub     rsp, 0B0h
0x18001643a  mov     rax, cs:__security_cookie
0x180016441  xor     rax, rsp
0x180016444  mov     [rbp+57h+var_18], rax
0x180016448  mov     rsi, rdx
0x18001644b  xor     r14d, r14d
0x18001644e  mov     dword ptr [rbp+57h+var_70], r14d
0x180016452  mov     [rdx], r14b
0x180016455  lea     rcx, [rbp+57h+var_70]; unsigned int *
0x180016459  call    ?MarkRemediationStatusIfNeeded@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAKAEA_N@Z; Microsoft::Windows::Autopilot::HardwareInfo::MarkRemediationStatusIfNeeded(ulong &,bool &)
0x18001645e  mov     ebx, eax
0x180016460  test    eax, eax
0x180016462  jns     short loc_1800164B8
0x180016464  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001646b  jz      short loc_180016499
0x18001646d  mov     dword ptr [rbp+57h+var_70], eax
0x180016470  lea     rax, [rbp+57h+var_70]
0x180016474  mov     qword ptr [rbp+57h+var_40], rax
0x180016478  mov     qword ptr [rbp+57h+var_40+8], 4
0x180016480  lea     rax, [rbp+57h+var_50]
0x180016484  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180016489  lea     r9d, [r14+2]
0x18001648d  lea     rdx, AutopilotDetectHardwareChangeRemediationReportFailed
0x180016494  call    McGenEventWrite_EventWriteTransfer
0x180016499  mov     edx, 0DFh; void *
0x18001649e  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800164a5  mov     r9d, ebx; char *
0x1800164a8  mov     rcx, [rbp+5Fh]; this
0x1800164ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164b1  mov     eax, ebx
0x1800164b3  jmp     loc_1800166B2
0x1800164b8  mov     edi, dword ptr [rbp+57h+var_70]
0x1800164bb  test    edi, edi
0x1800164bd  jz      loc_1800165BA
0x1800164c3  call    ?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ; ZeroTouchProvCxhTelemetry::Provider(void)
0x1800164c8  mov     rbx, rax
0x1800164cb  mov     ecx, [rax]
0x1800164cd  cmp     ecx, 5
0x1800164d0  jbe     loc_180016579
0x1800164d6  mov     rax, [rax+18h]
0x1800164da  mov     rcx, [rbx+10h]
0x1800164de  mov     rdx, 800000000000h
0x1800164e8  test    rdx, rcx
0x1800164eb  jz      loc_180016579
0x1800164f1  mov     rcx, rax
0x1800164f4  and     rcx, rdx
0x1800164f7  cmp     rcx, rax
0x1800164fa  jnz     short loc_180016579
0x1800164fc  mov     [rbp+57h+var_68], 2000000h
0x180016504  mov     dword ptr [rbp+57h+var_70], edi
0x180016507  lea     rax, aForceddelaywai; "ForcedDelayWait"
0x18001650e  mov     [rbp+57h+var_60], rax
0x180016512  lea     rax, aMicrosoftWindo_1; "Microsoft::Windows::Autopilot::DetectHa"...
0x180016519  mov     [rbp+57h+var_58], rax
0x18001651d  lea     rcx, [rbp+57h+var_50]
0x180016521  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180016526  cmp     qword ptr [rax+18h], 0Fh
0x18001652b  jbe     short loc_180016530
0x18001652d  mov     rax, [rax]
0x180016530  mov     qword ptr [rbp+57h+var_30], rax
0x180016534  lea     rax, [rbp+57h+var_68]
0x180016538  mov     [rsp+0C0h+var_80], rax
0x18001653d  lea     rax, [rbp+57h+var_70]
0x180016541  mov     [rsp+0C0h+var_88], rax
0x180016546  lea     rax, [rbp+57h+var_60]
0x18001654a  mov     [rsp+0C0h+var_90], rax
0x18001654f  lea     rax, [rbp+57h+var_58]
0x180016553  mov     [rsp+0C0h+var_98], rax
0x180016558  lea     rax, [rbp+57h+var_30]
0x18001655c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180016561  lea     rdx, byte_18003A82D
0x180016568  mov     rcx, rbx
0x18001656b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180016570  lea     rcx, [rbp+57h+var_50]
0x180016574  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180016579  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 8
0x180016580  jz      short loc_1800165B0
0x180016582  mov     dword ptr [rbp+57h+var_70], edi
0x180016585  lea     rax, [rbp+57h+var_70]
0x180016589  mov     qword ptr [rbp+57h+var_40], rax
0x18001658d  mov     qword ptr [rbp+57h+var_40+8], 4
0x180016595  lea     rax, [rbp+57h+var_50]
0x180016599  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001659e  mov     r9d, 2
0x1800165a4  lea     rdx, AutopilotDetectHardwareChangeEnforcedDelay
0x1800165ab  call    McGenEventWrite_EventWriteTransfer
0x1800165b0  mov     eax, 8007139Fh
0x1800165b5  jmp     loc_1800166B2
0x1800165ba  mov     ebx, 1
0x1800165bf  cmp     [rsi], r14b
0x1800165c2  jz      short loc_1800165D5
0x1800165c4  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, bl
0x1800165ca  jz      short loc_1800165F6
0x1800165cc  lea     rdx, AutopilotDetectHardwareChangeTaskRemediateChanged
0x1800165d3  jmp     short loc_1800165E5
0x1800165d5  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800165dc  jz      short loc_1800165F6
0x1800165de  lea     rdx, AutopilotDetectHardwareChangeTaskRemediateNoChange
0x1800165e5  lea     rax, [rbp+57h+var_30]
0x1800165e9  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800165ee  mov     r9d, ebx
0x1800165f1  call    McGenEventWrite_EventWriteTransfer
0x1800165f6  call    ?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x1800165fb  mov     [rbp+57h+var_68], rax
0x1800165ff  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180016606  jz      short loc_18001661B
0x180016608  mov     r8, rax
0x18001660b  lea     rdx, AutopilotDetectHardwareChangeTaskDisableStarted
0x180016612  call    McTemplateU0z_EventWriteTransfer
0x180016617  mov     rax, [rbp+57h+var_68]
0x18001661b  mov     dword ptr [rbp+57h+var_70], 80004001h
0x180016622  lea     rcx, [rbp+57h+var_70]
0x180016626  mov     qword ptr [rbp+57h+var_30], rcx
0x18001662a  lea     rcx, [rbp+57h+var_68]
0x18001662e  mov     [rbp+57h+var_28], rcx
0x180016632  mov     [rbp+57h+var_20], bl
0x180016635  xorps   xmm0, xmm0
0x180016638  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001663c  xorps   xmm1, xmm1
0x18001663f  movdqu  [rbp+57h+var_40], xmm1
0x180016644  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016648  inc     r8
0x18001664b  cmp     [rax+r8*2], r14w
0x180016650  jnz     short loc_180016648
0x180016652  mov     rdx, rax
0x180016655  lea     rcx, [rbp+57h+var_50]
0x180016659  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001665e  nop
0x18001665f  lea     rcx, [rbp+57h+var_50]
0x180016663  call    ?DisableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::DisableNamedTask(std::wstring const &)
0x180016668  mov     dword ptr [rbp+57h+var_70], eax
0x18001666b  lea     rcx, [rbp+57h+var_50]
0x18001666f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016674  mov     ebx, dword ptr [rbp+57h+var_70]
0x180016677  test    ebx, ebx
0x180016679  jns     short loc_180016696
0x18001667b  mov     rcx, [rbp+5Fh]; this
0x18001667f  mov     r9d, ebx; char *
0x180016682  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180016689  mov     edx, 0B8h; void *
0x18001668e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016693  nop
0x180016694  jmp     short loc_180016699
0x180016696  mov     ebx, r14d
0x180016699  lea     rcx, [rbp+57h+var_30]
0x18001669d  call    wil__details__lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd______lambda_call__lambda_be80a26cb822cd6d4254dfc0df6fefdd___
0x1800166a2  test    ebx, ebx
0x1800166a4  jns     short loc_1800166B0
0x1800166a6  mov     edx, 0FFh
0x1800166ab  jmp     loc_18001649E
0x1800166b0  xor     eax, eax
0x1800166b2  mov     rcx, [rbp+57h+var_18]
0x1800166b6  xor     rcx, rsp; StackCookie
0x1800166b9  call    __security_check_cookie
0x1800166be  lea     r11, [rsp+0C0h+var_10]
0x1800166c6  mov     rbx, [r11+20h]
0x1800166ca  mov     rsi, [r11+30h]
0x1800166ce  mov     rsp, r11
0x1800166d1  pop     r14
0x1800166d3  pop     rdi
0x1800166d4  pop     rbp
0x1800166d5  retn
```
