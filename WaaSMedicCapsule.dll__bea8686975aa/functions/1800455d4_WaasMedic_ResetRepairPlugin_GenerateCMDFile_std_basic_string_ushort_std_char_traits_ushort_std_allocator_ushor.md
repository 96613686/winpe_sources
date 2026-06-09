# WaasMedic::ResetRepairPlugin::GenerateCMDFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800455d4`
- end: `0x180045a06`
- name: `?GenerateCMDFile@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N00@Z`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004815c`

## callees

- `0x180003bb0`
- `0x180005ee5`
- `0x180006fdc`
- `0x1800070cc`
- `0x180007520`
- `0x180007590`
- `0x18002543c`
- `0x180033128`
- `0x180044930`
- `0x1800455d4`
- `0x18004a840`

## string_xrefs

- `0x180045622`: `rem Define %TARGETOS% as the Windows folder (This later becomes C:\Windows)\nfor /F "tokens=1,2,3 delims= " %%A in ('reg query "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\RecoveryEnvironment" /v TargetOS') DO SET TARGETOS=%%C\n\nrem Define %TARGETOSDRIVE% as the Windows partition (This later becomes C:)\nfor /F "tokens=1 delims=\" %%A in ('Echo %TARGETOS%') DO SET TARGETOSDRIVE=%%A\n\n`
- `0x1800456bb`: `rem delete Windows.old\Users\nrmdir /s /q \\?\%TARGETOSDRIVE%\Windows.old\Users\n\nIf EXIST %TARGETOSDRIVE%\Windows.old\Users (\n  rmdir /s /q \\?\%TARGETOSDRIVE%\Windows.old\Users\n)\n\nIf EXIST %TARGETOSDRIVE%\Windows.old\Users (\n  rmdir /s /q \\?\%TARGETOSDRIVE%\Windows.old\Users\n)\n\nIf EXIST %TARGETOSDRIVE%\Windows.old\Users (\n  rmdir /s /q \\?\%TARGETOSDRIVE%\Windows.old\Users\n)\n\nrem if folder still exists on the 4-th time, reboot to trigger a failure\nIf EXIST %TARGE`
- `0x18004573e`: `rem Check Auto Apply folder\nset AUTOAPPLYFOLDER=%TARGETOSDRIVE%\Recovery\AutoApply\n\nrem LayoutModification.xml\nIF EXIST %AUTOAPPLYFOLDER%\LayoutModification.xml (\n  copy %AUTOAPPLYFOLDER%\LayoutModification.xml %TARGETOSDRIVE%\Users\Default\AppData\Local\Microsoft\Windows\Shell\LayoutModification.xml /Y\n)\n\nrem LayoutModification.json\nIF EXIST %AUTOAPPLYFOLDER%\LayoutModification.json (\n  copy %AUTOAPPLYFOLDER%\LayoutModification.json %TARGETOSDRIVE%\Users\Default\AppData\Loca`
- `0x1800457c1`: `Add command to execute OEM script [%s]`
- `0x18004598f`: `Create target cmd file [%s]`
- `0x1800459bb`: `Failed to write command to target cmd file. Err=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::ResetRepairPlugin::GenerateCMDFile(
        __int64 a1,
        __int64 *a2,
        const WCHAR *a3,
        char a4,
        _QWORD *a5,
        _QWORD *a6)
{
  _QWORD *v9; // rbx
  _OWORD *v10; // rax
  const char *v11; // rcx
  __int64 v12; // rdx
  char *v13; // rax
  const char *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r14
  __int64 v17; // r8
  _QWORD *v18; // r8
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  _QWORD *v21; // r8
  __int64 v22; // rcx
  _QWORD *v23; // r8
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // ebx
  _BYTE v29[384]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD Src[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v31[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v32[24]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v33[72]; // [rsp+208h] [rbp+108h] BYREF
  char v34; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v35[1776]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v9 = a5;
  v10 = v29;
  v11 = "rem Define %TARGETOS% as the Windows folder (This later becomes C:\\Windows)\r\n"
        "for /F \"tokens=1,2,3 delims= \" %%A in ('reg query \"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\RecoveryEnvironme"
        "nt\" /v TargetOS') DO SET TARGETOS=%%C\r\n"
        "\r\n"
        "rem Define %TARGETOSDRIVE% as the Windows partition (This later becomes C:)\r\n"
        "for /F \"tokens=1 delims=\\\" %%A in ('Echo %TARGETOS%') DO SET TARGETOSDRIVE=%%A\r\n"
        "\r\n";
  v12 = 3;
  do
  {
    *v10 = *(_OWORD *)v11;
    v10[1] = *((_OWORD *)v11 + 1);
    v10[2] = *((_OWORD *)v11 + 2);
    v10[3] = *((_OWORD *)v11 + 3);
    v10[4] = *((_OWORD *)v11 + 4);
    v10[5] = *((_OWORD *)v11 + 5);
    v10[6] = *((_OWORD *)v11 + 6);
    v10[7] = *((_OWORD *)v11 + 7);
    v10 += 8;
    v11 += 128;
    --v12;
  }
  while ( v12 );
  strcpy(v33, "rem Execute OEM script\r\ncmd /c %TARGETOSDRIVE%\\Recovery\\OEM\\");
  v13 = &v34;
  v14 = "rem delete Windows.old\\Users\r\n"
        "rmdir /s /q \\\\?\\%TARGETOSDRIVE%\\Windows.old\\Users\r\n"
        "\r\n"
        "If EXIST %TARGETOSDRIVE%\\Windows.old\\Users (\r\n"
        "  rmdir /s /q \\\\?\\%TARGETOSDRIVE%\\Windows.old\\Users\r\n"
        ")\r\n"
        "\r\n"
        "If EXIST %TARGETOSDRIVE%\\Windows.old\\Users (\r\n"
        "  rmdir /s /q \\\\?\\%TARGETOSDRIVE%\\Windows.old\\Users\r\n"
        ")\r\n"
        "\r\n"
        "If EXIST %TARGETOSDRIVE%\\Windows.old\\Users (\r\n"
        "  rmdir /s /q \\\\?\\%TARGETOSDRIVE%\\Windows.old\\Users\r\n"
        ")\r\n"
        "\r\n"
        "rem if folder still exists on the 4-th time, reboot to trigger a failure\r\n"
        "If EXIST %TARGETOSDRIVE%\\Windows.old\\Users (\r\n"
        "rem Windows.old\\Users exist\r\n"
        "wpeutil reboot\r\n"
        ")\r\n"
        "\r\n"
        "rem Deletion succeed\r\n"
        "\r\n";
  v15 = 4;
  do
  {
    *(_OWORD *)v13 = *(_OWORD *)v14;
    *((_OWORD *)v13 + 1) = *((_OWORD *)v14 + 1);
    *((_OWORD *)v13 + 2) = *((_OWORD *)v14 + 2);
    *((_OWORD *)v13 + 3) = *((_OWORD *)v14 + 3);
    *((_OWORD *)v13 + 4) = *((_OWORD *)v14 + 4);
    *((_OWORD *)v13 + 5) = *((_OWORD *)v14 + 5);
    *((_OWORD *)v13 + 6) = *((_OWORD *)v14 + 6);
    *((_OWORD *)v13 + 7) = *((_OWORD *)v14 + 7);
    v13 += 128;
    v14 += 128;
    --v15;
  }
  while ( v15 );
  *(_OWORD *)v13 = *(_OWORD *)v14;
  *((_OWORD *)v13 + 1) = *((_OWORD *)v14 + 1);
  *((_OWORD *)v13 + 2) = *((_OWORD *)v14 + 2);
  *((_OWORD *)v13 + 3) = *((_OWORD *)v14 + 3);
  *(_OWORD *)(v13 + 62) = *(_OWORD *)(v14 + 62);
  memcpy_0(
    v35,
    "rem Check Auto Apply folder\r\n"
    "set AUTOAPPLYFOLDER=%TARGETOSDRIVE%\\Recovery\\AutoApply\r\n"
    "\r\n"
    "rem LayoutModification.xml\r\n"
    "IF EXIST %AUTOAPPLYFOLDER%\\LayoutModification.xml (\r\n"
    "  copy %AUTOAPPLYFOLDER%\\LayoutModification.xml %TARGETOSDRIVE%\\Users\\Default\\AppData\\Local\\Microsoft\\Windows"
    "\\Shell\\LayoutModification.xml /Y\r\n"
    ")\r\n"
    "\r\n"
    "rem LayoutModification.json\r\n"
    "IF EXIST %AUTOAPPLYFOLDER%\\LayoutModification.json (\r\n"
    "  copy %AUTOAPPLYFOLDER%\\LayoutModification.json %TARGETOSDRIVE%\\Users\\Default\\AppData\\Local\\Microsoft\\Window"
    "s\\Shell\\LayoutModification.json /Y\r\n"
    ")\r\n"
    "\r\n"
    "rem Unattend.xml\r\n"
    "  IF EXIST %AUTOAPPLYFOLDER%\\Unattend.xml (\r\n"
    "copy %AUTOAPPLYFOLDER%\\Unattend.xml %TARGETOSDRIVE%\\Windows\\Panther\\Unattend.xml /Y\r\n"
    ")\r\n"
    "\r\n"
    "rem Create Windows\\OEM\r\n"
    "  IF not EXIST %TARGETOSDRIVE%\\Windows\\OEM (\r\n"
    "mkdir %TARGETOSDRIVE%\\Windows\\OEM\r\n"
    ")\r\n"
    "\r\n"
    "rem TaskbarLayoutModification.xml\r\n"
    "IF EXIST %AUTOAPPLYFOLDER%\\TaskbarLayoutModification.xml (\r\n"
    "  copy %AUTOAPPLYFOLDER%\\TaskbarLayoutModification.xml %TARGETOSDRIVE%\\Windows\\OEM\\TaskbarLayoutModification.xml"
    " /Y\r\n"
    ")\r\n"
    "\r\n"
    "rem OOBE\r\n"
    "IF EXIST %AUTOAPPLYFOLDER%\\OOBE (\r\n"
    "  xcopy %AUTOAPPLYFOLDER%\\OOBE %TARGETOSDRIVE%\\Windows\\System32\\Oobe\\Info\\ /Y /S /E\r\n"
    ")\r\n"
    "\r\n"
    "rem TaskbarLayoutModification.xml\r\n"
    "IF EXIST %AUTOAPPLYFOLDER%\\CustomizationFiles (\r\n"
    "  xcopy %AUTOAPPLYFOLDER%\\CustomizationFiles %TARGETOSDRIVE%\\Windows\\OEM\\CustomizationFiles\\ /S /E /Y\r\n"
    ")\r\n"
    "\r\n"
    "rem registry key changes for taskbar layout\r\n"
    "IF EXIST %TARGETOSDRIVE%\\Windows\\OEM\\TaskbarLayoutModification.xml (\r\n"
    "  reg load HKLM\\$OfflineSoftware %TARGETOSDRIVE%\\Windows\\System32\\config\\Software \r\n"
    "  reg add HKLM\\$OfflineSoftware\\Microsoft\\Windows\\CurrentVersion\\Explorer    /v LayoutXMLPath /t REG_SZ /d %TAR"
    "GETOSDRIVE%\\Windows\\OEM\\TaskbarLayoutModification.xml\r\n"
    "  reg unload HKLM\\$OfflineSoftware \r\n"
    ")\r\n"
    "\r\n",
    0x6E4u);
  strcpy(v32, "rem exit\r\nEXIT 0\r\n");
  memset(Src, 0, sizeof(Src));
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( v29[v17] );
  std::string::_Construct<1,char const *>(Src, v29, v17);
  if ( a5[2] )
  {
    if ( a5[3] <= 7u )
      v18 = a5;
    else
      v18 = (_QWORD *)*a5;
    LogLevelW(4u, L"Add command to execute OEM script [%s]", v18);
    v19 = 0;
    v20 = a5[2];
    if ( v20 )
    {
      do
      {
        if ( a5[3] <= 7u )
          v21 = a5;
        else
          v21 = (_QWORD *)*a5;
        if ( *((_WORD *)v21 + v19) != 32 )
          break;
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < v20 );
    }
    if ( (unsigned int)v19 >= v20 )
    {
      if ( a5[3] > 7u )
        v9 = (_QWORD *)*a5;
      LogLevelW(3u, L"OEM script [%s] is actually empty", v9);
    }
    else
    {
      memset(v31, 0, sizeof(v31));
      v22 = v20 - (unsigned int)v19;
      if ( v22 != -1 )
        v16 = v22;
      if ( a5[3] > 7u )
        v9 = (_QWORD *)*a5;
      std::wstring::_Construct<1,unsigned short const *>(v31, (char *)v9 + 2 * v19, v16);
      std::string::operator+=(Src);
      WaasMedic::ws2s(v33, v31);
      std::string::operator+=(Src);
      std::string::~string(v33);
      std::string::operator+=(Src);
      if ( a6[2] )
      {
        if ( a6[3] <= 7u )
          v23 = a6;
        else
          v23 = (_QWORD *)*a6;
        LogLevelW(4u, L"OEM script parameter [%s]", v23);
        WaasMedic::ws2s(v33, a6);
        std::string::operator+=(Src);
        std::string::~string(v33);
      }
      std::string::operator+=(Src);
      std::wstring::~wstring(v31);
    }
  }
  std::string::operator+=(Src);
  if ( a4 )
    std::string::operator+=(Src);
  std::string::operator+=(Src);
  if ( (unsigned __int64)a2[3] <= 7 )
    v24 = (__int64)a2;
  else
    v24 = *a2;
  LogLevelW(4u, L"Create target cmd file [%s]", v24);
  v26 = WaasMedic::ResetRepairPlugin::WriteToFile(v25, Src, a2, a3);
  v27 = v26;
  if ( v26 < 0 )
    LogLevelW(2u, L"Failed to write command to target cmd file. Err=0x%08x", (unsigned int)v26);
  std::string::~string(Src);
  return v27;
}

```

## disassembly

```asm
0x1800455d4  mov     [rsp-8+arg_0], rbx
0x1800455d9  mov     [rsp-8+arg_18], rsi
0x1800455de  push    rbp
0x1800455df  push    rdi
0x1800455e0  push    r12
0x1800455e2  push    r14
0x1800455e4  push    r15
0x1800455e6  lea     rbp, [rsp-0AA0h]
0x1800455ee  sub     rsp, 0BA0h
0x1800455f5  mov     rax, cs:__security_cookie
0x1800455fc  xor     rax, rsp
0x1800455ff  mov     [rbp+0AC0h+var_30], rax
0x180045606  mov     r15b, r9b
0x180045609  mov     r12, r8
0x18004560c  mov     rsi, rdx
0x18004560f  mov     rdi, [rbp+0AC0h+arg_28]
0x180045616  mov     rbx, [rbp+0AC0h+arg_20]
0x18004561d  lea     rax, [rsp+0BC0h+var_B90]
0x180045622  lea     rcx, aRemDefineTarge; "rem Define %TARGETOS% as the Windows fo"...
0x180045629  mov     edx, 3
0x18004562e  lea     r8d, [rdx+7Dh]
0x180045632  movups  xmm0, xmmword ptr [rcx]
0x180045635  movups  xmmword ptr [rax], xmm0
0x180045638  movups  xmm1, xmmword ptr [rcx+10h]
0x18004563c  movups  xmmword ptr [rax+10h], xmm1
0x180045640  movups  xmm0, xmmword ptr [rcx+20h]
0x180045644  movups  xmmword ptr [rax+20h], xmm0
0x180045648  movups  xmm1, xmmword ptr [rcx+30h]
0x18004564c  movups  xmmword ptr [rax+30h], xmm1
0x180045650  movups  xmm0, xmmword ptr [rcx+40h]
0x180045654  movups  xmmword ptr [rax+40h], xmm0
0x180045658  movups  xmm1, xmmword ptr [rcx+50h]
0x18004565c  movups  xmmword ptr [rax+50h], xmm1
0x180045660  movups  xmm0, xmmword ptr [rcx+60h]
0x180045664  movups  xmmword ptr [rax+60h], xmm0
0x180045668  movups  xmm1, xmmword ptr [rcx+70h]
0x18004566c  movups  xmmword ptr [rax+70h], xmm1
0x180045670  add     rax, r8
0x180045673  add     rcx, r8
0x180045676  sub     rdx, 1
0x18004567a  jnz     short loc_180045632
0x18004567c  movups  xmm0, xmmword ptr cs:aRemExecuteOemS; "rem Execute OEM script\r\ncmd /c %TARGE"...
0x180045683  movups  xmmword ptr [rbp+0AC0h+var_9B8], xmm0
0x18004568a  movups  xmm1, xmmword ptr cs:aRemExecuteOemS+10h; "script\r\ncmd /c %TARGETOSDRIVE%\\Recov"...
0x180045691  movups  xmmword ptr [rbp+0AC0h+var_9B8+10h], xmm1
0x180045698  movups  xmm0, xmmword ptr cs:aRemExecuteOemS+20h; "TARGETOSDRIVE%\\Recovery\\OEM\\"
0x18004569f  movups  xmmword ptr [rbp+0AC0h+var_9B8+20h], xmm0
0x1800456a6  movups  xmm1, xmmword ptr cs:aRemExecuteOemS+2Dh; "%\\Recovery\\OEM\\"
0x1800456ad  movups  xmmword ptr [rbp+0AC0h+var_9B8+2Dh], xmm1
0x1800456b4  lea     rax, [rbp+0AC0h+var_970]
0x1800456bb  lea     rcx, aRemDeleteWindo; "rem delete Windows.old\\Users\r\nrmdir "...
0x1800456c2  mov     edx, 4
0x1800456c7  movups  xmm0, xmmword ptr [rcx]
0x1800456ca  movups  xmmword ptr [rax], xmm0
0x1800456cd  movups  xmm1, xmmword ptr [rcx+10h]
0x1800456d1  movups  xmmword ptr [rax+10h], xmm1
0x1800456d5  movups  xmm0, xmmword ptr [rcx+20h]
0x1800456d9  movups  xmmword ptr [rax+20h], xmm0
0x1800456dd  movups  xmm1, xmmword ptr [rcx+30h]
0x1800456e1  movups  xmmword ptr [rax+30h], xmm1
0x1800456e5  movups  xmm0, xmmword ptr [rcx+40h]
0x1800456e9  movups  xmmword ptr [rax+40h], xmm0
0x1800456ed  movups  xmm1, xmmword ptr [rcx+50h]
0x1800456f1  movups  xmmword ptr [rax+50h], xmm1
0x1800456f5  movups  xmm0, xmmword ptr [rcx+60h]
0x1800456f9  movups  xmmword ptr [rax+60h], xmm0
0x1800456fd  movups  xmm1, xmmword ptr [rcx+70h]
0x180045701  movups  xmmword ptr [rax+70h], xmm1
0x180045705  add     rax, r8
0x180045708  add     rcx, r8
0x18004570b  sub     rdx, 1
0x18004570f  jnz     short loc_1800456C7
0x180045711  movups  xmm0, xmmword ptr [rcx]
0x180045714  movups  xmmword ptr [rax], xmm0
0x180045717  movups  xmm1, xmmword ptr [rcx+10h]
0x18004571b  movups  xmmword ptr [rax+10h], xmm1
0x18004571f  movups  xmm0, xmmword ptr [rcx+20h]
0x180045723  movups  xmmword ptr [rax+20h], xmm0
0x180045727  movups  xmm1, xmmword ptr [rcx+30h]
0x18004572b  movups  xmmword ptr [rax+30h], xmm1
0x18004572f  movups  xmm0, xmmword ptr [rcx+3Eh]
0x180045733  movups  xmmword ptr [rax+3Eh], xmm0
0x180045737  lea     rcx, [rbp+0AC0h+var_720]; void *
0x18004573e  lea     rdx, aRemCheckAutoAp; "rem Check Auto Apply folder\r\nset AUTO"...
0x180045745  mov     r8d, 6E4h; Size
0x18004574b  call    memcpy_0
0x180045750  movups  xmm0, xmmword ptr cs:aRemExitExit0; "rem exit\r\nEXIT 0\r\n"
0x180045757  movups  xmmword ptr [rbp+0AC0h+var_9D0], xmm0
0x18004575e  mov     eax, dword ptr cs:aRemExitExit0+0Fh; "0\r\n"
0x180045764  mov     dword ptr [rbp+0AC0h+var_9D0+0Fh], eax
0x18004576a  xorps   xmm0, xmm0
0x18004576d  movups  [rbp+0AC0h+Src], xmm0
0x180045774  xorps   xmm1, xmm1
0x180045777  movdqu  [rbp+0AC0h+var_A00], xmm1
0x18004577f  lea     rax, [rsp+0BC0h+var_B90]
0x180045784  or      r14, 0FFFFFFFFFFFFFFFFh
0x180045788  mov     r8, r14
0x18004578b  inc     r8
0x18004578e  cmp     byte ptr [rax+r8], 0
0x180045793  jnz     short loc_18004578B
0x180045795  lea     rdx, [rsp+0BC0h+var_B90]
0x18004579a  lea     rcx, [rbp+0AC0h+Src]
0x1800457a1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800457a6  nop
0x1800457a7  cmp     qword ptr [rbx+10h], 0
0x1800457ac  jz      loc_180045942
0x1800457b2  cmp     qword ptr [rbx+18h], 7
0x1800457b7  jbe     short loc_1800457BE
0x1800457b9  mov     r8, [rbx]
0x1800457bc  jmp     short loc_1800457C1
0x1800457be  mov     r8, rbx
0x1800457c1  lea     rdx, aAddCommandToEx; "Add command to execute OEM script [%s]"
0x1800457c8  mov     ecx, 4; unsigned __int8
0x1800457cd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800457d2  xor     edx, edx
0x1800457d4  mov     rcx, [rbx+10h]
0x1800457d8  test    rcx, rcx
0x1800457db  jz      short loc_1800457FD
0x1800457dd  cmp     qword ptr [rbx+18h], 7
0x1800457e2  jbe     short loc_1800457E9
0x1800457e4  mov     r8, [rbx]
0x1800457e7  jmp     short loc_1800457EC
0x1800457e9  mov     r8, rbx
0x1800457ec  cmp     word ptr [r8+rdx*2], 20h ; ' '
0x1800457f2  jnz     short loc_1800457FD
0x1800457f4  inc     edx
0x1800457f6  mov     eax, edx
0x1800457f8  cmp     rax, rcx
0x1800457fb  jb      short loc_1800457DD
0x1800457fd  mov     eax, edx
0x1800457ff  cmp     rax, rcx
0x180045802  jnb     loc_180045924
0x180045808  xorps   xmm0, xmm0
0x18004580b  movups  [rbp+0AC0h+var_9F0], xmm0
0x180045812  xorps   xmm1, xmm1
0x180045815  movdqu  [rbp+0AC0h+var_9E0], xmm1
0x18004581d  sub     rcx, rax
0x180045820  cmp     rcx, r14
0x180045823  cmovb   r14, rcx
0x180045827  cmp     qword ptr [rbx+18h], 7
0x18004582c  jbe     short loc_180045831
0x18004582e  mov     rbx, [rbx]
0x180045831  lea     rdx, [rbx+rdx*2]
0x180045835  mov     r8, r14
0x180045838  lea     rcx, [rbp+0AC0h+var_9F0]
0x18004583f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180045844  nop
0x180045845  lea     rdx, [rbp+0AC0h+var_9B8]
0x18004584c  lea     rcx, [rbp+0AC0h+Src]; Src
0x180045853  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x180045858  lea     rdx, [rbp+0AC0h+var_9F0]
0x18004585f  lea     rcx, [rbp+0AC0h+var_9B8]
0x180045866  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x18004586b  nop
0x18004586c  cmp     qword ptr [rax+18h], 0Fh
0x180045871  jbe     short loc_180045876
0x180045873  mov     rax, [rax]
0x180045876  mov     rdx, rax
0x180045879  lea     rcx, [rbp+0AC0h+Src]; Src
0x180045880  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x180045885  nop
0x180045886  lea     rcx, [rbp+0AC0h+var_9B8]
0x18004588d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180045892  lea     rdx, asc_18007D854; " "
0x180045899  lea     rcx, [rbp+0AC0h+Src]; Src
0x1800458a0  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x1800458a5  cmp     qword ptr [rdi+10h], 0
0x1800458aa  jz      short loc_180045902
0x1800458ac  cmp     qword ptr [rdi+18h], 7
0x1800458b1  jbe     short loc_1800458B8
0x1800458b3  mov     r8, [rdi]
0x1800458b6  jmp     short loc_1800458BB
0x1800458b8  mov     r8, rdi
0x1800458bb  lea     rdx, aOemScriptParam; "OEM script parameter [%s]"
0x1800458c2  mov     ecx, 4; unsigned __int8
0x1800458c7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800458cc  mov     rdx, rdi
0x1800458cf  lea     rcx, [rbp+0AC0h+var_9B8]
0x1800458d6  call    ?ws2s@WaasMedic@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; WaasMedic::ws2s(std::wstring const &)
0x1800458db  nop
0x1800458dc  cmp     qword ptr [rax+18h], 0Fh
0x1800458e1  jbe     short loc_1800458E6
0x1800458e3  mov     rax, [rax]
0x1800458e6  mov     rdx, rax
0x1800458e9  lea     rcx, [rbp+0AC0h+Src]; Src
0x1800458f0  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x1800458f5  nop
0x1800458f6  lea     rcx, [rbp+0AC0h+var_9B8]
0x1800458fd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180045902  lea     rdx, asc_18007D8B0; "\r\n\r\n"
0x180045909  lea     rcx, [rbp+0AC0h+Src]; Src
0x180045910  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x180045915  nop
0x180045916  lea     rcx, [rbp+0AC0h+var_9F0]; void *
0x18004591d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045922  jmp     short loc_180045942
0x180045924  cmp     qword ptr [rbx+18h], 7
0x180045929  jbe     short loc_18004592E
0x18004592b  mov     rbx, [rbx]
0x18004592e  mov     r8, rbx
0x180045931  lea     rdx, aOemScriptSIsAc; "OEM script [%s] is actually empty"
0x180045938  mov     ecx, 3; unsigned __int8
0x18004593d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180045942  lea     rdx, [rbp+0AC0h+var_970]
0x180045949  lea     rcx, [rbp+0AC0h+Src]; Src
0x180045950  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x180045955  test    r15b, r15b
0x180045958  jz      short loc_18004596D
0x18004595a  lea     rdx, [rbp+0AC0h+var_720]
0x180045961  lea     rcx, [rbp+0AC0h+Src]; Src
0x180045968  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x18004596d  lea     rdx, [rbp+0AC0h+var_9D0]
0x180045974  lea     rcx, [rbp+0AC0h+Src]; Src
0x18004597b  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator+=(char const * const)
0x180045980  cmp     qword ptr [rsi+18h], 7
0x180045985  jbe     short loc_18004598C
0x180045987  mov     r8, [rsi]
0x18004598a  jmp     short loc_18004598F
0x18004598c  mov     r8, rsi
0x18004598f  lea     rdx, aCreateTargetCm; "Create target cmd file [%s]"
0x180045996  mov     ecx, 4; unsigned __int8
0x18004599b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800459a0  mov     r9, r12
0x1800459a3  mov     r8, rsi
0x1800459a6  lea     rdx, [rbp+0AC0h+Src]
0x1800459ad  call    ?WriteToFile@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@1@Z; WaasMedic::ResetRepairPlugin::WriteToFile(std::string const &,std::wstring const &,std::wstring const &)
0x1800459b2  mov     ebx, eax
0x1800459b4  test    eax, eax
0x1800459b6  jns     short loc_1800459CD
0x1800459b8  mov     r8d, eax
0x1800459bb  lea     rdx, aFailedToWriteC; "Failed to write command to target cmd f"...
0x1800459c2  mov     ecx, 2; unsigned __int8
0x1800459c7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800459cc  nop
0x1800459cd  lea     rcx, [rbp+0AC0h+Src]
0x1800459d4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800459d9  mov     eax, ebx
0x1800459db  mov     rcx, [rbp+0AC0h+var_30]
0x1800459e2  xor     rcx, rsp; StackCookie
0x1800459e5  call    __security_check_cookie
0x1800459ea  lea     r11, [rsp+0BC0h+var_20]
0x1800459f2  mov     rbx, [r11+30h]
0x1800459f6  mov     rsi, [r11+48h]
0x1800459fa  mov     rsp, r11
0x1800459fd  pop     r15
0x1800459ff  pop     r14
0x180045a01  pop     r12
0x180045a03  pop     rdi
0x180045a04  pop     rbp
0x180045a05  retn
```
