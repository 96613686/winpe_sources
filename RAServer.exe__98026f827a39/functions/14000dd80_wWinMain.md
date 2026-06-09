# wWinMain

- ea: `0x14000dd80`
- end: `0x14000debb`
- name: `wWinMain`
- size: `315`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400016a0`

## callees

- `0x14000d440`
- `0x14000d6d0`
- `0x14000d990`
- `0x14000dd80`
- `0x14000fd90`
- `0x14000ff18`
- `0x140015240`
- `0x1400153d4`
- `0x140015600`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x14000dda0`
- `ADVAPI32!EventRegister` at `0x14000dda0`
- `KERNEL32!HeapSetInformation` at `0x14000ddbe`
- `KERNEL32!HeapSetInformation` at `0x14000ddbe`
- `KERNEL32!CompareStringW` at `0x14000de07`
- `KERNEL32!CompareStringW` at `0x14000de07`
- `KERNEL32!GetCommandLineW` at `0x14000de7e`
- `KERNEL32!GetCommandLineW` at `0x14000de7e`

## string_xrefs

- `0x14000ddf1`: `offerraupdate`
- `0x14000de53`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  CEventLogger *v5; // rcx
  __int64 v6; // rcx
  int v7; // ebx
  int RegistryValue; // eax
  int v9; // edx
  signed int v10; // eax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  unsigned int v12; // r9d
  LPWSTR CommandLineW; // rax
  __int64 v14; // rcx
  int v16; // [rsp+50h] [rbp+18h] BYREF

  EventRegister(&RemoteAssistanceGUID, 0, 0, &g_Logger);
  CEventLogger::LogEvent(v5, &RA_Server_Starting);
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  EnableMitigations();
  v7 = -1;
  if ( lpCmdLine
    && (v6 = 65533, ((*lpCmdLine - 45) & 0xFFFD) == 0)
    && CompareStringW(0x7Fu, 1u, lpCmdLine + 1, -1, L"offerraupdate", -1) == 2 )
  {
    v7 = 0;
    v16 = 0;
    RegistryValue = GetRegistryValue(v6, &v16);
    v9 = v16;
    if ( RegistryValue < 0 )
      v9 = 0;
    if ( v9 )
    {
      v10 = CRAGroupPolicy::RA_EnableORASupport(0);
      if ( v10 < 0 )
      {
        v12 = 60;
LABEL_11:
        CEventLogger::LogError(
          (CEventLogger *)v6,
          v11,
          L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
          v12,
          L"CRAGroupPolicy::RAGroupPolicyRefresh",
          v10);
      }
    }
    else
    {
      v10 = CRAGroupPolicy::RA_DisableORASupport(0);
      if ( v10 < 0 )
      {
        v12 = 71;
        goto LABEL_11;
      }
    }
  }
  else if ( !ATL::CAtlBaseModule::m_bInitFailed )
  {
    v16 = 0;
    CommandLineW = GetCommandLineW();
    if ( (unsigned __int8)ATL::CAtlExeModuleT<CRAServerModule>::ParseCommandLine(v14, CommandLineW, &v16) == 1 )
      v7 = ATL::CAtlExeModuleT<CRAServerModule>::Run();
    else
      v7 = v16;
  }
  CEventLogger::LogEvent((CEventLogger *)v6, &RA_Server_Ending);
  return v7;
}

```

## disassembly

```asm
0x14000dd80  mov     [rsp+arg_0], rbx
0x14000dd85  push    rdi
0x14000dd86  sub     rsp, 30h
0x14000dd8a  mov     rdi, r8
0x14000dd8d  lea     r9, ?g_Logger@@3VCEventLogger@@A; RegHandle
0x14000dd94  xor     r8d, r8d; CallbackContext
0x14000dd97  lea     rcx, RemoteAssistanceGUID; ProviderId
0x14000dd9e  xor     edx, edx; EnableCallback
0x14000dda0  call    cs:__imp_EventRegister
0x14000dda6  lea     rdx, RA_Server_Starting; struct _EVENT_DESCRIPTOR *
0x14000ddad  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x14000ddb2  xor     r9d, r9d; HeapInformationLength
0x14000ddb5  xor     r8d, r8d; HeapInformation
0x14000ddb8  xor     ecx, ecx; HeapHandle
0x14000ddba  lea     edx, [r9+1]; HeapInformationClass
0x14000ddbe  call    cs:__imp_HeapSetInformation
0x14000ddc4  call    ?EnableMitigations@@YAXXZ; EnableMitigations(void)
0x14000ddc9  or      ebx, 0FFFFFFFFh
0x14000ddcc  test    rdi, rdi
0x14000ddcf  jz      loc_14000DE6D
0x14000ddd5  movzx   eax, word ptr [rdi]
0x14000ddd8  mov     ecx, 0FFFDh
0x14000dddd  sub     ax, 2Dh ; '-'
0x14000dde1  test    cx, ax
0x14000dde4  jnz     loc_14000DE6D
0x14000ddea  lea     edx, [rbx+2]; dwCmpFlags
0x14000dded  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x14000ddf1  lea     rax, aOfferraupdate; "offerraupdate"
0x14000ddf8  mov     r9d, ebx; cchCount1
0x14000ddfb  lea     ecx, [rdx+7Eh]; Locale
0x14000ddfe  mov     [rsp+38h+lpString2], rax; lpString2
0x14000de03  lea     r8, [rdi+2]; lpString1
0x14000de07  call    cs:__imp_CompareStringW
0x14000de0d  cmp     eax, 2
0x14000de10  jnz     short loc_14000DE6D
0x14000de12  xor     ebx, ebx
0x14000de14  lea     rdx, [rsp+38h+arg_10]
0x14000de19  mov     [rsp+38h+arg_10], ebx
0x14000de1d  call    ?GetRegistryValue@@YAJPEAGPEAKW4_RAREGHIVE@@@Z; GetRegistryValue(ushort *,ulong *,_RAREGHIVE)
0x14000de22  mov     edx, [rsp+38h+arg_10]
0x14000de26  xor     ecx, ecx; this
0x14000de28  test    eax, eax
0x14000de2a  cmovs   edx, ecx
0x14000de2d  test    edx, edx
0x14000de2f  jz      short loc_14000DE40
0x14000de31  call    ?RA_EnableORASupport@CRAGroupPolicy@@AEAAJXZ; CRAGroupPolicy::RA_EnableORASupport(void)
0x14000de36  test    eax, eax
0x14000de38  jns     short loc_14000DEA2
0x14000de3a  lea     r9d, [rbx+3Ch]
0x14000de3e  jmp     short loc_14000DE4F
0x14000de40  call    ?RA_DisableORASupport@CRAGroupPolicy@@AEAAJXZ; CRAGroupPolicy::RA_DisableORASupport(void)
0x14000de45  test    eax, eax
0x14000de47  jns     short loc_14000DEA2
0x14000de49  mov     r9d, 47h ; 'G'; unsigned int
0x14000de4f  mov     [rsp+38h+cchCount2], eax; unsigned int
0x14000de53  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000de5a  lea     rax, aCragrouppolicy_12; "CRAGroupPolicy::RAGroupPolicyRefresh"
0x14000de61  mov     [rsp+38h+lpString2], rax; unsigned __int16 *
0x14000de66  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000de6b  jmp     short loc_14000DEA2
0x14000de6d  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x14000de74  jnz     short loc_14000DEA2
0x14000de76  mov     [rsp+38h+arg_10], 0
0x14000de7e  call    cs:__imp_GetCommandLineW
0x14000de84  mov     rdx, rax
0x14000de87  lea     r8, [rsp+38h+arg_10]
0x14000de8c  call    ?ParseCommandLine@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@QEAA_NPEBGPEAJ@Z; ATL::CAtlExeModuleT<CRAServerModule>::ParseCommandLine(ushort const *,long *)
0x14000de91  cmp     al, 1
0x14000de93  jnz     short loc_14000DE9E
0x14000de95  call    ?Run@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@QEAAJH@Z; ATL::CAtlExeModuleT<CRAServerModule>::Run(int)
0x14000de9a  mov     ebx, eax
0x14000de9c  jmp     short loc_14000DEA2
0x14000de9e  mov     ebx, [rsp+38h+arg_10]
0x14000dea2  lea     rdx, RA_Server_Ending; struct _EVENT_DESCRIPTOR *
0x14000dea9  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x14000deae  mov     eax, ebx
0x14000deb0  mov     rbx, [rsp+38h+arg_0]
0x14000deb5  add     rsp, 30h
0x14000deb9  pop     rdi
0x14000deba  retn
```
