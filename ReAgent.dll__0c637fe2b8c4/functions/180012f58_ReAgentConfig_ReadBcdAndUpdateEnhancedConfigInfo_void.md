# ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo(void)

- ea: `0x180012f58`
- end: `0x180013292`
- name: `?ReadBcdAndUpdateEnhancedConfigInfo@ReAgentConfig@@IEAAKXZ`
- size: `826`
- prototype: `unsigned int __fastcall(ReAgentConfig *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180012ae0`

## callees

- `0x180001f94`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000ed74`
- `0x180010010`
- `0x1800103f4`
- `0x180011264`
- `0x1800127bc`
- `0x180012f58`
- `0x1800145f4`
- `0x180035300`
- `0x180051dc8`
- `0x18005cee2`
- `0x18005cf30`

## string_xrefs

- `0x180013004`: `DisableUpdateEnhancedConfigInfo`
- `0x18001311b`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180012fbd`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo (In WinPE) Using winre guid from the config file`
- `0x180012fec`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo Target config file isn't config file of current OS`
- `0x180013022`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo Still use BCD info to update enhanced info due to caller request`
- `0x180013048`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo WinRE disabled, WinRE Guid could not be determined  (0x%x) `
- `0x1800130da`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo GetOsInfoForBootEntry returned 0x%x `
- `0x180013132`: `failed to copy boot application directory name`
- `0x18001313c`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo %s (0x%x) in file %S line %d`
- `0x18001317c`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo BCD recovery entry points to invalid location (no winre.wim at %s)`
- `0x1800131b8`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo BCD recovery entry points to invalid location (no boot.sdi at %s)`
- `0x1800131e9`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo winreConvertDirNameToOffset (%s) returned 0X%X `
- `0x18001322b`: `ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo SetWinreLocationPath returned 0x%x `
- `0x18001323c`: `WinRE is installed`

## pseudocode

```c
__int64 __fastcall ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo(ReAgentConfig *this)
{
  __int64 v1; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // ebx
  unsigned int WinReGuid; // eax
  unsigned int OsInfoForBootEntry; // eax
  WCHAR *v8; // r15
  int v9; // esi
  __int64 v10; // r11
  unsigned int v11; // eax
  unsigned int v12; // eax
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+60h] [rbp-A0h]
  struct _GUID v17; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int64 v18; // [rsp+530h] [rbp+430h]
  struct _GUID v19; // [rsp+570h] [rbp+470h] BYREF
  unsigned __int16 v20; // [rsp+580h] [rbp+480h] BYREF
  char v21[526]; // [rsp+582h] [rbp+482h] BYREF
  unsigned __int16 v22; // [rsp+790h] [rbp+690h] BYREF
  char v23[526]; // [rsp+792h] [rbp+692h] BYREF

  v1 = *((_QWORD *)this + 8);
  v19 = 0;
  Block = 0;
  *(_DWORD *)(v1 + 5588) = 0;
  if ( (unsigned int)winreIsWinPE() )
  {
    UnattendLogW(
      0,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo (In WinPE) Using winre guid from the config file");
    v19 = *(struct _GUID *)*((_QWORD *)this + 8);
    goto LABEL_11;
  }
  if ( !(unsigned int)IsOSConfigFile(*((wchar_t **)this + 1), v3, v4) )
  {
    UnattendLogW(
      0,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo Target config file isn't config file of current OS");
    if ( *((_DWORD *)this + 18) != 2 )
    {
      v5 = 0;
      UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
      *((_DWORD *)this + 18) = 1;
LABEL_6:
      ReAgentError = 0;
      return v5;
    }
    UnattendLogW(
      0,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo Still use BCD info to update enhanced info due to caller request");
  }
  WinReGuid = winreGetWinReGuid((__int64)&GUID_CURRENT_BOOT_ENTRY, &v19);
  if ( WinReGuid )
  {
    UnattendLogW(
      0,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo WinRE disabled, WinRE Guid could not be determined  (0x%x) ",
      WinReGuid);
    v5 = 0;
    goto LABEL_6;
  }
  *(struct _GUID *)*((_QWORD *)this + 8) = v19;
LABEL_11:
  memset_0(v15, 0, 0x530u);
  v22 = 0;
  memset_0(v23, 0, 0x206u);
  v20 = 0;
  memset_0(v21, 0, 0x206u);
  OsInfoForBootEntry = CBootCfg::GetOsInfoForBootEntry(
                         (CBootCfg *)CBootCfg::m_instance,
                         &v19,
                         (struct _SRT_OS_INFO **)&Block);
  v8 = (WCHAR *)Block;
  v5 = OsInfoForBootEntry;
  if ( OsInfoForBootEntry )
  {
    UnattendLogW(
      2,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo GetOsInfoForBootEntry returned 0x%x ",
      OsInfoForBootEntry);
    v5 = 0;
    ReAgentError = 0;
    goto LABEL_25;
  }
  v9 = StringCchCopyW(&v20, 0x104u, (const unsigned __int16 *)Block + 1416);
  if ( v9 < 0 )
  {
    UnattendLogW(
      2,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo %s (0x%x) in file %S line %d",
      L"failed to copy boot application directory name",
      (unsigned int)v9,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
      2177);
    v5 = (unsigned __int16)v9;
    goto LABEL_25;
  }
  winreStripFilename(&v20, L"Winre.wim", v10);
  if ( !(unsigned int)winreDoesFileExist(&v20, L"Winre.wim") )
  {
    UnattendLogW(
      2,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo BCD recovery entry points to invalid location (no winre.wim at %s)",
      &v20);
LABEL_17:
    ReAgentError = 0;
    goto LABEL_25;
  }
  if ( !(unsigned int)winreDoesFileExist(&v20, L"boot.sdi") )
  {
    UnattendLogW(
      2,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo BCD recovery entry points to invalid location (no boot.sdi at %s)",
      &v20);
    goto LABEL_17;
  }
  v11 = winreConvertDirNameToOffset(v8 + 1416, (__int64)L"Winre.wim", v15, 0, (__int64)&v22);
  v5 = v11;
  if ( v11 )
  {
    UnattendLogW(
      2,
      L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo winreConvertDirNameToOffset (%s) returned 0X%X ",
      v8 + 1416,
      v11);
  }
  else
  {
    v12 = ReAgentConfig::SetWinreLocationPath(this, v18, &v17, v16, &v22);
    v5 = v12;
    if ( v12 )
    {
      UnattendLogW(2, L"ReAgentConfig::ReadBcdAndUpdateEnhancedConfigInfo SetWinreLocationPath returned 0x%x ", v12);
    }
    else
    {
      UnattendLogW(0, L"WinRE is installed");
      *(_DWORD *)(*((_QWORD *)this + 8) + 5588LL) = 1;
    }
  }
LABEL_25:
  if ( v8 )
    operator delete(v8);
  return v5;
}

```

## disassembly

```asm
0x180012f58  mov     [rsp-8+arg_8], rbx
0x180012f5d  mov     [rsp-8+arg_10], rsi
0x180012f62  push    rbp
0x180012f63  push    rdi
0x180012f64  push    r13
0x180012f66  push    r14
0x180012f68  push    r15
0x180012f6a  lea     rbp, [rsp-8B0h]
0x180012f72  sub     rsp, 9B0h
0x180012f79  mov     rax, cs:__security_cookie
0x180012f80  xor     rax, rsp
0x180012f83  mov     [rbp+8D0h+var_30], rax
0x180012f8a  mov     rax, [rcx+40h]
0x180012f8e  xorps   xmm0, xmm0
0x180012f91  movups  xmmword ptr [rbp+8D0h+var_460.Data1], xmm0
0x180012f98  mov     rdi, rcx
0x180012f9b  mov     [rsp+9D0h+Block], 0
0x180012fa4  mov     dword ptr [rax+15D4h], 0
0x180012fae  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x180012fb3  mov     r13d, 2
0x180012fb9  test    eax, eax
0x180012fbb  jz      short loc_180012FDF
0x180012fbd  lea     rdx, aReagentconfigR_8; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x180012fc4  xor     ecx, ecx
0x180012fc6  call    UnattendLogW
0x180012fcb  mov     rax, [rdi+40h]
0x180012fcf  movups  xmm0, xmmword ptr [rax]
0x180012fd2  movdqu  xmmword ptr [rbp+8D0h+var_460.Data1], xmm0
0x180012fda  jmp     loc_180013069
0x180012fdf  mov     rcx, [rdi+8]; String2
0x180012fe3  call    ?IsOSConfigFile@@YAHPEAG@Z; IsOSConfigFile(ushort *)
0x180012fe8  test    eax, eax
0x180012fea  jnz     short loc_18001302E
0x180012fec  lea     rdx, aReagentconfigR_1; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x180012ff3  xor     ecx, ecx
0x180012ff5  call    UnattendLogW
0x180012ffa  xor     ecx, ecx
0x180012ffc  cmp     [rdi+48h], r13d
0x180013000  jz      short loc_180013022
0x180013002  xor     ebx, ebx
0x180013004  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18001300b  call    UnattendLogW
0x180013010  mov     dword ptr [rdi+48h], 1
0x180013017  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, ebx; _ReAgentErrorCodes ReAgentError
0x18001301d  jmp     loc_180013265
0x180013022  lea     rdx, aReagentconfigR; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x180013029  call    UnattendLogW
0x18001302e  lea     rdx, [rbp+8D0h+var_460]
0x180013035  lea     rcx, GUID_CURRENT_BOOT_ENTRY
0x18001303c  call    winreGetWinReGuid
0x180013041  test    eax, eax
0x180013043  jz      short loc_18001305A
0x180013045  mov     r8d, eax
0x180013048  lea     rdx, aReagentconfigR_2; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x18001304f  xor     ecx, ecx
0x180013051  call    UnattendLogW
0x180013056  xor     ebx, ebx
0x180013058  jmp     short loc_180013017
0x18001305a  mov     rax, [rdi+40h]
0x18001305e  movups  xmm0, xmmword ptr [rbp+8D0h+var_460.Data1]
0x180013065  movdqu  xmmword ptr [rax], xmm0
0x180013069  xor     edx, edx; Val
0x18001306b  lea     rcx, [rsp+9D0h+var_990]; void *
0x180013070  mov     r8d, 530h; Size
0x180013076  call    memset_0
0x18001307b  xor     eax, eax
0x18001307d  lea     rcx, [rbp+8D0h+var_23E]; void *
0x180013084  mov     ebx, 206h
0x180013089  mov     [rbp+8D0h+var_240], ax
0x180013090  mov     r8d, ebx; Size
0x180013093  xor     edx, edx; Val
0x180013095  call    memset_0
0x18001309a  xor     eax, eax
0x18001309c  lea     rcx, [rbp+8D0h+var_44E]; void *
0x1800130a3  mov     r8d, ebx; Size
0x1800130a6  mov     [rbp+8D0h+var_450], ax
0x1800130ad  xor     edx, edx; Val
0x1800130af  call    memset_0
0x1800130b4  lea     r8, [rsp+9D0h+Block]; struct _SRT_OS_INFO **
0x1800130b9  lea     rdx, [rbp+8D0h+var_460]; struct _GUID *
0x1800130c0  lea     rcx, ?m_instance@CBootCfg@@0V1@A; this
0x1800130c7  call    ?GetOsInfoForBootEntry@CBootCfg@@QEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z; CBootCfg::GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)
0x1800130cc  mov     r15, [rsp+9D0h+Block]
0x1800130d1  mov     ebx, eax
0x1800130d3  test    eax, eax
0x1800130d5  jz      short loc_1800130F6
0x1800130d7  mov     r8d, eax
0x1800130da  lea     rdx, aReagentconfigR_6; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x1800130e1  mov     ecx, r13d
0x1800130e4  call    UnattendLogW
0x1800130e9  xor     ebx, ebx
0x1800130eb  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, ebx; _ReAgentErrorCodes ReAgentError
0x1800130f1  jmp     loc_180013258
0x1800130f6  lea     r14, [r15+0B10h]
0x1800130fd  mov     r11d, 104h
0x180013103  mov     r8, r14; unsigned __int16 *
0x180013106  lea     rcx, [rbp+8D0h+var_450]; unsigned __int16 *
0x18001310d  mov     edx, r11d; unsigned __int64
0x180013110  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013115  mov     esi, eax
0x180013117  test    eax, eax
0x180013119  jns     short loc_180013150
0x18001311b  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180013122  mov     [rsp+9D0h+var_9A8], 881h
0x18001312a  mov     r9d, esi
0x18001312d  mov     [rsp+9D0h+var_9B0], rax
0x180013132  lea     r8, aFailedToCopyBo; "failed to copy boot application directo"...
0x180013139  mov     ecx, r13d
0x18001313c  lea     rdx, aReagentconfigR_7; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x180013143  call    UnattendLogW
0x180013148  movzx   ebx, si
0x18001314b  jmp     loc_180013258
0x180013150  lea     rsi, aWinreWim; "Winre.wim"
0x180013157  mov     r8, r11
0x18001315a  mov     rdx, rsi
0x18001315d  lea     rcx, [rbp+8D0h+var_450]
0x180013164  call    winreStripFilename
0x180013169  mov     rdx, rsi; unsigned __int16 *
0x18001316c  lea     rcx, [rbp+8D0h+var_450]; unsigned __int16 *
0x180013173  call    winreDoesFileExist
0x180013178  test    eax, eax
0x18001317a  jnz     short loc_1800131A1
0x18001317c  lea     rdx, aReagentconfigR_3; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x180013183  lea     r8, [rbp+8D0h+var_450]
0x18001318a  mov     ecx, r13d
0x18001318d  call    UnattendLogW
0x180013192  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x18001319c  jmp     loc_180013258
0x1800131a1  lea     rdx, aBootSdi; "boot.sdi"
0x1800131a8  lea     rcx, [rbp+8D0h+var_450]; unsigned __int16 *
0x1800131af  call    winreDoesFileExist
0x1800131b4  test    eax, eax
0x1800131b6  jnz     short loc_1800131C1
0x1800131b8  lea     rdx, aReagentconfigR_5; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x1800131bf  jmp     short loc_180013183
0x1800131c1  lea     rax, [rbp+8D0h+var_240]
0x1800131c8  xor     r9d, r9d
0x1800131cb  lea     r8, [rsp+9D0h+var_990]
0x1800131d0  mov     [rsp+9D0h+var_9B0], rax; __int64
0x1800131d5  mov     rdx, rsi
0x1800131d8  mov     rcx, r14; lpszFileName
0x1800131db  call    winreConvertDirNameToOffset
0x1800131e0  mov     ebx, eax
0x1800131e2  test    eax, eax
0x1800131e4  jz      short loc_1800131FD
0x1800131e6  mov     r9d, eax
0x1800131e9  lea     rdx, aReagentconfigR_0; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x1800131f0  mov     r8, r14
0x1800131f3  mov     ecx, r13d
0x1800131f6  call    UnattendLogW
0x1800131fb  jmp     short loc_180013258
0x1800131fd  mov     r9d, [rsp+9D0h+var_970]; unsigned int
0x180013202  lea     rax, [rbp+8D0h+var_240]
0x180013209  mov     rdx, [rbp+8D0h+var_4A0]; unsigned __int64
0x180013210  lea     r8, [rsp+9D0h+var_96C]; struct _GUID *
0x180013215  mov     rcx, rdi; this
0x180013218  mov     [rsp+9D0h+var_9B0], rax; unsigned __int16 *
0x18001321d  call    ?SetWinreLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetWinreLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x180013222  mov     ebx, eax
0x180013224  test    eax, eax
0x180013226  jz      short loc_18001323C
0x180013228  mov     r8d, eax
0x18001322b  lea     rdx, aReagentconfigR_4; "ReAgentConfig::ReadBcdAndUpdateEnhanced"...
0x180013232  mov     ecx, r13d
0x180013235  call    UnattendLogW
0x18001323a  jmp     short loc_180013258
0x18001323c  lea     rdx, aWinreIsInstall; "WinRE is installed"
0x180013243  xor     ecx, ecx
0x180013245  call    UnattendLogW
0x18001324a  mov     rax, [rdi+40h]
0x18001324e  mov     dword ptr [rax+15D4h], 1
0x180013258  test    r15, r15
0x18001325b  jz      short loc_180013265
0x18001325d  mov     rcx, r15; Block
0x180013260  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013265  mov     eax, ebx
0x180013267  mov     rcx, [rbp+8D0h+var_30]
0x18001326e  xor     rcx, rsp; StackCookie
0x180013271  call    __security_check_cookie
0x180013276  lea     r11, [rsp+9D0h+var_20]
0x18001327e  mov     rbx, [r11+38h]
0x180013282  mov     rsi, [r11+40h]
0x180013286  mov     rsp, r11
0x180013289  pop     r15
0x18001328b  pop     r14
0x18001328d  pop     r13
0x18001328f  pop     rdi
0x180013290  pop     rbp
0x180013291  retn
```
