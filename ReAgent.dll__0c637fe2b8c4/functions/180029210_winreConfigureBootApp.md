# winreConfigureBootApp

- ea: `0x180029210`
- end: `0x180029599`
- name: `winreConfigureBootApp`
- size: `905`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x1800209a0`
- `0x180023b50`
- `0x180025920`

## callees

- `0x1800059fc`
- `0x180008b94`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180011344`
- `0x180011974`
- `0x1800121b0`
- `0x180014754`
- `0x180029210`
- `0x18004d3a0`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029506`
- `KERNEL32!GetLastError` at `0x180029506`
- `KERNEL32!SetLastError` at `0x18002954e`
- `KERNEL32!SetLastError` at `0x18002954e`
- `KERNEL32!DeleteFileW` at `0x1800294fc`
- `KERNEL32!DeleteFileW` at `0x1800294fc`

## string_xrefs

- `0x180029417`: `DisableUpdateEnhancedConfigInfo`
- `0x1800293af`: `ReAgent.xml`
- `0x18002936c`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800294b9`: `Failed to update agent config`
- `0x1800292e8`: `winreConfigureBootAppwinre.wim not found at %s`
- `0x180029365`: `Append path failed`
- `0x180029376`: `winreConfigureBootApp %s (0x%x) in file %S line %d`
- `0x180029447`: `Failed to init agent config`
- `0x1800294ea`: `winreConfigureBootAppOne-time boot app not specified. Leaving ReAgent.xml unchanged. Error: 0x%x`
- `0x180029512`: `winreConfigureBootAppFailed to delete configuration file at %s`
- `0x180029527`: `winreConfigureBootApp failed:  0x%x`
- `0x180029539`: `winreConfigureBootApp succeeded`

## pseudocode

```c
__int64 __fastcall winreConfigureBootApp(unsigned __int16 *a1, int a2, __int64 a3, unsigned __int16 *a4, int a5)
{
  int DoesFileExist; // ebx
  unsigned int v9; // edi
  const wchar_t *v10; // r8
  const unsigned __int16 *v11; // r8
  __int64 v12; // rcx
  int v13; // edx
  DWORD v14; // ecx
  int v16; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v18[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+88h] [rbp-78h]
  WCHAR FileName; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[606]; // [rsp+92h] [rbp-6Eh] BYREF

  v18[1] = 0;
  v18[0] = &ReAgentConfig::`vftable';
  v18[2] = 0;
  FileName = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v20 = 2;
  v23 = 0;
  v24 = 0;
  memset_0(v26, 0, 0x25Au);
  if ( !a1 || a2 && !a4 )
  {
    v14 = 87;
    goto LABEL_37;
  }
  DoesFileExist = Utils::DoesFileExist(a1, L"Winre.wim");
  v9 = 1;
  if ( DoesFileExist )
  {
    UnattendLogW(1, L"winreConfigureBootAppwinre.wim not found at %s", a1);
LABEL_34:
    UnattendLogW(1, L"winreConfigureBootApp failed:  0x%x", (unsigned int)DoesFileExist);
    v14 = DoesFileExist;
LABEL_37:
    SetLastError(v14);
    v9 = 0;
    goto LABEL_38;
  }
  v17 = 0;
  DoesFileExist = StringCchLengthW(a1, 0x7FFFFFFFu, &v17);
  if ( DoesFileExist >= 0 )
  {
    if ( !v17 || (v11 = L"%s\\%s", a1[v17 - 1] == 92) )
      v11 = L"%s%s";
    DoesFileExist = StringCchPrintfW(&FileName, 0x12Eu, v11, a1, L"ReAgent.xml");
    if ( DoesFileExist >= 0 )
      goto LABEL_20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        (unsigned int)DoesFileExist);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
      (unsigned int)DoesFileExist);
  }
  DoesFileExist = (unsigned __int16)DoesFileExist;
  if ( (_WORD)DoesFileExist )
  {
    v16 = 5704;
    v10 = L"Append path failed";
LABEL_12:
    UnattendLogW(
      2,
      L"winreConfigureBootApp %s (0x%x) in file %S line %d",
      v10,
      (unsigned int)DoesFileExist,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      v16);
    goto LABEL_34;
  }
LABEL_20:
  UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
  v24 = 1;
  DoesFileExist = ReAgentConfig::Init((ReAgentConfig *)v18, &FileName, 1);
  if ( DoesFileExist )
  {
    v16 = 5711;
    v10 = L"Failed to init agent config";
    goto LABEL_12;
  }
  if ( a2 )
  {
    v12 = 12;
    if ( a5 == 1 )
      v12 = 15;
    *(_DWORD *)(v23 + 5612) = v12;
    DoesFileExist = ReAgentXMLParser::CopyPathInfo((ReAgentXMLParser *)v12, a4, (unsigned __int16 *)(v23 + 5616));
    if ( DoesFileExist )
    {
      v16 = 5724;
      v10 = L"Failed to set operation param";
      goto LABEL_12;
    }
    DoesFileExist = ReAgentXMLParser::Update((ReAgentXMLParser *)v18);
    if ( DoesFileExist )
    {
      v16 = 5726;
      v10 = L"Failed to update agent config";
      goto LABEL_12;
    }
  }
  else
  {
    v13 = *((_DWORD *)ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v18) + 1403);
    if ( v13 != 12 && v13 != 15 )
    {
      DoesFileExist = 13;
      UnattendLogW(
        1,
        L"winreConfigureBootAppOne-time boot app not specified. Leaving ReAgent.xml unchanged. Error: 0x%x",
        13);
      goto LABEL_34;
    }
    if ( !DeleteFileW(&FileName) )
    {
      DoesFileExist = GetLastError();
      UnattendLogW(1, L"winreConfigureBootAppFailed to delete configuration file at %s", &FileName);
      if ( DoesFileExist )
        goto LABEL_34;
    }
  }
  UnattendLogW(0, L"winreConfigureBootApp succeeded");
LABEL_38:
  v18[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v18);
  return v9;
}

```

## disassembly

```asm
0x180029210  mov     [rsp-8+arg_8], rbx
0x180029215  mov     [rsp-8+arg_10], rsi
0x18002921a  push    rbp
0x18002921b  push    rdi
0x18002921c  push    r13
0x18002921e  push    r14
0x180029220  push    r15
0x180029222  lea     rbp, [rsp-200h]
0x18002922a  sub     rsp, 300h
0x180029231  mov     rax, cs:__security_cookie
0x180029238  xor     rax, rsp
0x18002923b  mov     [rbp+220h+var_30], rax
0x180029242  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180029249  mov     [rsp+320h+var_2D8], 0
0x180029252  mov     [rsp+320h+var_2E0], rax
0x180029257  mov     r14d, edx
0x18002925a  xor     eax, eax
0x18002925c  mov     [rsp+320h+var_2D0], 0
0x180029265  mov     rsi, rcx
0x180029268  mov     [rbp+220h+FileName], ax
0x18002926c  xorps   xmm0, xmm0
0x18002926f  mov     [rsp+320h+var_2C8], 0
0x180029277  xorps   xmm1, xmm1
0x18002927a  movdqa  [rsp+320h+var_2C0], xmm0
0x180029280  mov     r13d, 2
0x180029286  movdqa  [rsp+320h+var_2B0], xmm1
0x18002928c  xor     edx, edx; Val
0x18002928e  mov     [rsp+320h+var_2C4], r13d
0x180029293  mov     r8d, 25Ah; Size
0x180029299  mov     [rbp+220h+var_2A0], 0
0x1800292a1  lea     rcx, [rbp+220h+var_28E]; void *
0x1800292a5  mov     [rbp+220h+var_298], 0
0x1800292ac  mov     r15, r9
0x1800292af  call    memset_0
0x1800292b4  test    rsi, rsi
0x1800292b7  jz      loc_180029549
0x1800292bd  test    r14d, r14d
0x1800292c0  jz      short loc_1800292CB
0x1800292c2  test    r15, r15
0x1800292c5  jz      loc_180029549
0x1800292cb  lea     rdx, aWinreWim; "Winre.wim"
0x1800292d2  mov     rcx, rsi; unsigned __int16 *
0x1800292d5  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x1800292da  mov     ebx, eax
0x1800292dc  mov     edi, 1
0x1800292e1  test    eax, eax
0x1800292e3  jz      short loc_1800292FB
0x1800292e5  mov     r8, rsi
0x1800292e8  lea     rdx, aWinreconfigure_6; "winreConfigureBootAppwinre.wim not foun"...
0x1800292ef  mov     ecx, edi
0x1800292f1  call    UnattendLogW
0x1800292f6  jmp     loc_180029524
0x1800292fb  lea     r8, [rsp+320h+var_2F0]; unsigned __int64 *
0x180029300  mov     [rsp+320h+var_2F0], 0
0x180029309  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002930e  mov     rcx, rsi; unsigned __int16 *
0x180029311  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180029316  mov     ebx, eax
0x180029318  test    eax, eax
0x18002931a  jns     short loc_18002938F
0x18002931c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029323  lea     rax, WPP_GLOBAL_Control
0x18002932a  cmp     rcx, rax
0x18002932d  jz      short loc_18002934D
0x18002932f  test    [rcx+1Ch], r13b
0x180029333  jz      short loc_18002934D
0x180029335  mov     rcx, [rcx+10h]
0x180029339  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180029340  mov     edx, 0Eh
0x180029345  mov     r9d, ebx
0x180029348  call    WPP_SF_d
0x18002934d  mov     esi, 0Fh
0x180029352  movzx   ebx, bx
0x180029355  test    ebx, ebx
0x180029357  jz      loc_180029417
0x18002935d  mov     [rsp+320h+var_2F8], 1648h
0x180029365  lea     r8, aAppendPathFail; "Append path failed"
0x18002936c  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029373  mov     r9d, ebx
0x180029376  lea     rdx, aWinreconfigure_1; "winreConfigureBootApp %s (0x%x) in file"...
0x18002937d  mov     [rsp+320h+var_300], rax
0x180029382  mov     ecx, r13d
0x180029385  call    UnattendLogW
0x18002938a  jmp     loc_180029524
0x18002938f  mov     rax, [rsp+320h+var_2F0]
0x180029394  test    rax, rax
0x180029397  jz      short loc_1800293A8
0x180029399  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x18002939f  lea     r8, aSS_1; "%s\\%s"
0x1800293a6  jnz     short loc_1800293AF
0x1800293a8  lea     r8, aSS_2; "%s%s"
0x1800293af  lea     rax, aReagentXml_1; "ReAgent.xml"
0x1800293b6  mov     r9, rsi
0x1800293b9  mov     edx, 12Eh; unsigned __int64
0x1800293be  mov     [rsp+320h+var_300], rax
0x1800293c3  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x1800293c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800293cc  mov     ebx, eax
0x1800293ce  test    eax, eax
0x1800293d0  jns     short loc_180029412
0x1800293d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293d9  lea     rax, WPP_GLOBAL_Control
0x1800293e0  cmp     rcx, rax
0x1800293e3  jz      loc_18002934D
0x1800293e9  mov     esi, 0Fh
0x1800293ee  test    [rcx+1Ch], r13b
0x1800293f2  jz      loc_180029352
0x1800293f8  mov     rcx, [rcx+10h]
0x1800293fc  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180029403  mov     edx, esi
0x180029405  mov     r9d, ebx
0x180029408  call    WPP_SF_d
0x18002940d  jmp     loc_180029352
0x180029412  mov     esi, 0Fh
0x180029417  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18002941e  xor     ecx, ecx
0x180029420  call    UnattendLogW
0x180029425  mov     r8d, edi; int
0x180029428  mov     [rbp+220h+var_298], edi
0x18002942b  lea     rdx, [rbp+220h+FileName]; unsigned __int16 *
0x18002942f  lea     rcx, [rsp+320h+var_2E0]; this
0x180029434  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180029439  mov     ebx, eax
0x18002943b  test    eax, eax
0x18002943d  jz      short loc_180029453
0x18002943f  mov     [rsp+320h+var_2F8], 164Fh
0x180029447  lea     r8, aFailedToInitAg_0; "Failed to init agent config"
0x18002944e  jmp     loc_18002936C
0x180029453  test    r14d, r14d
0x180029456  jz      short loc_1800294C5
0x180029458  mov     rax, [rbp+220h+var_2A0]
0x18002945c  mov     ecx, 0Ch
0x180029461  cmp     [rbp+220h+arg_20], edi
0x180029467  mov     rdx, r15; unsigned __int16 *
0x18002946a  cmovz   ecx, esi; this
0x18002946d  mov     [rax+15ECh], ecx
0x180029473  mov     r8, [rbp+220h+var_2A0]
0x180029477  add     r8, 15F0h; unsigned __int16 *
0x18002947e  call    ?CopyPathInfo@ReAgentXMLParser@@IEAAKPEAG0@Z; ReAgentXMLParser::CopyPathInfo(ushort *,ushort *)
0x180029483  mov     ebx, eax
0x180029485  test    eax, eax
0x180029487  jz      short loc_18002949D
0x180029489  mov     [rsp+320h+var_2F8], 165Ch
0x180029491  lea     r8, aFailedToSetOpe_1; "Failed to set operation param"
0x180029498  jmp     loc_18002936C
0x18002949d  lea     rcx, [rsp+320h+var_2E0]; this
0x1800294a2  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x1800294a7  mov     ebx, eax
0x1800294a9  test    eax, eax
0x1800294ab  jz      loc_180029539
0x1800294b1  mov     [rsp+320h+var_2F8], 165Eh
0x1800294b9  lea     r8, aFailedToUpdate_10; "Failed to update agent config"
0x1800294c0  jmp     loc_18002936C
0x1800294c5  lea     rcx, [rsp+320h+var_2E0]; this
0x1800294ca  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x1800294cf  mov     ecx, 0Ch
0x1800294d4  mov     edx, [rax+15ECh]
0x1800294da  cmp     edx, ecx
0x1800294dc  jz      short loc_1800294F8
0x1800294de  cmp     edx, esi
0x1800294e0  jz      short loc_1800294F8
0x1800294e2  lea     ebx, [rcx+1]
0x1800294e5  mov     ecx, edi
0x1800294e7  mov     r8d, ebx
0x1800294ea  lea     rdx, aWinreconfigure_7; "winreConfigureBootAppOne-time boot app "...
0x1800294f1  call    UnattendLogW
0x1800294f6  jmp     short loc_180029524
0x1800294f8  lea     rcx, [rbp+220h+FileName]; lpFileName
0x1800294fc  call    cs:__imp_DeleteFileW
0x180029502  test    eax, eax
0x180029504  jnz     short loc_180029539
0x180029506  call    cs:__imp_GetLastError
0x18002950c  lea     r8, [rbp+220h+FileName]
0x180029510  mov     ecx, edi
0x180029512  lea     rdx, aWinreconfigure_4; "winreConfigureBootAppFailed to delete c"...
0x180029519  mov     ebx, eax
0x18002951b  call    UnattendLogW
0x180029520  test    ebx, ebx
0x180029522  jz      short loc_180029539
0x180029524  mov     r8d, ebx
0x180029527  lea     rdx, aWinreconfigure_3; "winreConfigureBootApp failed:  0x%x"
0x18002952e  mov     ecx, edi
0x180029530  call    UnattendLogW
0x180029535  mov     ecx, ebx
0x180029537  jmp     short loc_18002954E
0x180029539  lea     rdx, aWinreconfigure_5; "winreConfigureBootApp succeeded"
0x180029540  xor     ecx, ecx
0x180029542  call    UnattendLogW
0x180029547  jmp     short loc_180029556
0x180029549  mov     ecx, 57h ; 'W'; dwErrCode
0x18002954e  call    cs:__imp_SetLastError
0x180029554  xor     edi, edi
0x180029556  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002955d  lea     rcx, [rsp+320h+var_2E0]; this
0x180029562  mov     [rsp+320h+var_2E0], rax
0x180029567  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18002956c  mov     eax, edi
0x18002956e  mov     rcx, [rbp+220h+var_30]
0x180029575  xor     rcx, rsp; StackCookie
0x180029578  call    __security_check_cookie
0x18002957d  lea     r11, [rsp+320h+var_20]
0x180029585  mov     rbx, [r11+38h]
0x180029589  mov     rsi, [r11+40h]
0x18002958d  mov     rsp, r11
0x180029590  pop     r15
0x180029592  pop     r14
0x180029594  pop     r13
0x180029596  pop     rdi
0x180029597  pop     rbp
0x180029598  retn
```
