# RecMountOfflineHive(ushort const *,ushort const *,ushort const *)

- ea: `0x18003fec0`
- end: `0x1800401bb`
- name: `?RecMountOfflineHive@@YAPEAUHKEY__@@PEBG00@Z`
- size: `763`
- prototype: `HKEY __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18001178c`
- `0x1800170f0`

## callees

- `0x180009e04`
- `0x18001c5bc`
- `0x18003f7b0`
- `0x18003f8bc`
- `0x18003fc08`
- `0x18003fec0`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800401b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800401b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ffae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ffd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ffae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ffd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040137`
- `WDSCORE!CurrentIP` at `0x18003ff17`
- `WDSCORE!CurrentIP` at `0x18003ffe1`
- `WDSCORE!CurrentIP` at `0x18004009a`
- `WDSCORE!CurrentIP` at `0x18004013f`
- `WDSCORE!CurrentIP` at `0x18003ff17`
- `WDSCORE!CurrentIP` at `0x18003ffe1`
- `WDSCORE!CurrentIP` at `0x18004009a`
- `WDSCORE!CurrentIP` at `0x18004013f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003ff7a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180040041`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800400fa`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800401a3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003ff7a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180040041`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800400fa`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800401a3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180040050`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180040050`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180040066`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180040066`

## string_xrefs

- `0x18003fef6`: `%s\system32\config\%s`
- `0x18003ff4b`: `RecMountOfflineHive`
- `0x18003ffb6`: `RecMountOfflineHive`
- `0x18003ff20`: `Can't construct hive path`
- `0x18003ffee`: `RecMountOfflineHive`
- `0x1800400a7`: `RecMountOfflineHive`
- `0x180040150`: `RecMountOfflineHive`
- `0x18003fff5`: `%hs: Hive %s is in use, we'll attempt to unload it`
- `0x1800400ae`: `%hs: Hive %s was successfully mounted after unload`
- `0x180040157`: `%hs: Can't mount offline hive: %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
HKEY __fastcall RecMountOfflineHive(const unsigned __int16 *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HKEY v4; // rdx
  __int64 v5; // r9
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v10; // eax
  DWORD v11; // esi
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  struct UnBCL::String *v15; // rax
  int v16; // ebx
  HKEY v17; // rdx
  __int64 v18; // r9
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  HKEY v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[24]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR File[264]; // [rsp+80h] [rbp-80h] BYREF

  v25 = (int)a2;
  if ( (unsigned int)StringCchPrintfW(File, 0x104u, L"%s\\system32\\config\\%s", a1) )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(0x2000000, "Can't construct hive path");
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      602,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecMountOfflineHive",
      v7,
      LastError,
      0,
      0);
    return 0;
  }
  v27 = 0;
  if ( !(unsigned int)RecLoadKey((const char *)File, v4, a3, v5, v25, &v27) )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( !v10 )
    {
      v11 = 31;
LABEL_15:
      v22 = GetLastError();
      v23 = CurrentIP();
      v24 = ConstructPartialMsgW(
              0x2000000,
              "%hs: Can't mount offline hive: %s. Error: 0x%08X",
              "RecMountOfflineHive",
              (const char *)File,
              v11);
      WdsSetupLogMessageW(
        v24,
        0,
        L"D",
        0,
        638,
        L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
        L"RecMountOfflineHive",
        v23,
        v22,
        0,
        0);
      RecDumpNtHiveListToLog();
      SetLastError(v11);
      return 0;
    }
    if ( v10 != 32 )
      goto LABEL_15;
    v12 = GetLastError();
    v13 = CurrentIP();
    v14 = ConstructPartialMsgW(
            50331648,
            "%hs: Hive %s is in use, we'll attempt to unload it",
            "RecMountOfflineHive",
            (const char *)File);
    WdsSetupLogMessageW(
      v14,
      0,
      L"D",
      0,
      617,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecMountOfflineHive",
      v13,
      v12,
      0,
      0);
    v15 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v28, File);
    v16 = RecFindAndUnloadHive(v15);
    UnBCL::String::~String((UnBCL::String *)v28);
    if ( v16 < 0 )
    {
      v11 = (unsigned __int16)v16;
    }
    else
    {
      if ( (unsigned int)RecLoadKey((const char *)File, v17, a3, v18, v26, &v27) )
      {
        v19 = GetLastError();
        v20 = CurrentIP();
        v21 = ConstructPartialMsgW(
                0x4000000,
                "%hs: Hive %s was successfully mounted after unload",
                "RecMountOfflineHive",
                (const char *)File);
        WdsSetupLogMessageW(
          v21,
          0,
          L"D",
          0,
          623,
          L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
          L"RecMountOfflineHive",
          v20,
          v19,
          0,
          0);
        return v27;
      }
      v11 = GetLastError();
    }
    if ( v11 )
      goto LABEL_15;
  }
  return v27;
}

```

## disassembly

```asm
0x18003fec0  push    rbp
0x18003fec2  push    rbx
0x18003fec3  push    rsi
0x18003fec4  push    rdi
0x18003fec5  push    r12
0x18003fec7  push    r14
0x18003fec9  push    r15
0x18003fecb  lea     rbp, [rsp-1A0h]
0x18003fed3  sub     rsp, 2A0h
0x18003feda  mov     rax, cs:__security_cookie
0x18003fee1  xor     rax, rsp
0x18003fee4  mov     [rbp+1D0h+var_40], rax
0x18003feeb  mov     r12, r8
0x18003feee  mov     qword ptr [rsp+2D0h+var_2B0], rdx; int
0x18003fef3  mov     r9, rcx
0x18003fef6  lea     r8, aSSystem32Confi; "%s\\system32\\config\\%s"
0x18003fefd  mov     edx, 104h; unsigned __int64
0x18003ff02  lea     rcx, [rbp+1D0h+File]; unsigned __int16 *
0x18003ff06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ff0b  test    eax, eax
0x18003ff0d  jz      short loc_18003FF87
0x18003ff0f  call    cs:__imp_GetLastError
0x18003ff15  mov     edi, eax
0x18003ff17  call    cs:__imp_CurrentIP
0x18003ff1d  mov     rbx, rax
0x18003ff20  lea     rdx, aCanTConstructH; "Can't construct hive path"
0x18003ff27  mov     ecx, 2000000h; unsigned int
0x18003ff2c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003ff31  mov     [rsp+2D0h+var_280], 0
0x18003ff39  mov     [rsp+2D0h+var_288], 0
0x18003ff42  mov     [rsp+2D0h+var_290], edi
0x18003ff46  mov     [rsp+2D0h+var_298], rbx
0x18003ff4b  lea     r14, aRecmountofflin; "RecMountOfflineHive"
0x18003ff52  mov     [rsp+2D0h+var_2A0], r14
0x18003ff57  lea     r15, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003ff5e  mov     [rsp+2D0h+var_2A8], r15
0x18003ff63  mov     [rsp+2D0h+var_2B0], 25Ah
0x18003ff6b  xor     r9d, r9d
0x18003ff6e  lea     r8, aD; "D"
0x18003ff75  xor     edx, edx
0x18003ff77  mov     rcx, rax
0x18003ff7a  call    cs:__imp_WdsSetupLogMessageW
0x18003ff80  xor     eax, eax
0x18003ff82  jmp     loc_180040105
0x18003ff87  mov     [rsp+2D0h+var_270], 0
0x18003ff90  lea     rax, [rsp+2D0h+var_270]
0x18003ff95  mov     [rsp+2D0h+var_2A8], rax; HKEY *
0x18003ff9a  mov     r8, r12; unsigned __int16 *
0x18003ff9d  lea     rcx, [rbp+1D0h+File]; lpFile
0x18003ffa1  call    ?RecLoadKey@@YAHPEBGPEAUHKEY__@@0KHPEAPEAU1@@Z; RecLoadKey(ushort const *,HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x18003ffa6  test    eax, eax
0x18003ffa8  jnz     loc_180040100
0x18003ffae  call    cs:__imp_GetLastError
0x18003ffb4  mov     esi, eax
0x18003ffb6  lea     r14, aRecmountofflin; "RecMountOfflineHive"
0x18003ffbd  lea     r15, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003ffc4  test    eax, eax
0x18003ffc6  jnz     short loc_18003FFD0
0x18003ffc8  lea     esi, [rax+1Fh]
0x18003ffcb  jmp     loc_180040137
0x18003ffd0  cmp     eax, 20h ; ' '
0x18003ffd3  jnz     loc_180040137
0x18003ffd9  call    cs:__imp_GetLastError
0x18003ffdf  mov     edi, eax
0x18003ffe1  call    cs:__imp_CurrentIP
0x18003ffe7  mov     rbx, rax
0x18003ffea  lea     r9, [rbp+1D0h+File]
0x18003ffee  lea     r8, aRecmountofflin_0; "RecMountOfflineHive"
0x18003fff5  lea     rdx, aHsHiveSIsInUse; "%hs: Hive %s is in use, we'll attempt t"...
0x18003fffc  mov     ecx, 3000000h; unsigned int
0x180040001  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180040006  mov     [rsp+2D0h+var_280], 0
0x18004000e  mov     [rsp+2D0h+var_288], 0
0x180040017  mov     [rsp+2D0h+var_290], edi
0x18004001b  mov     [rsp+2D0h+var_298], rbx
0x180040020  mov     [rsp+2D0h+var_2A0], r14
0x180040025  mov     [rsp+2D0h+var_2A8], r15
0x18004002a  mov     [rsp+2D0h+var_2B0], 269h; int
0x180040032  xor     r9d, r9d
0x180040035  lea     r8, aD; "D"
0x18004003c  xor     edx, edx
0x18004003e  mov     rcx, rax
0x180040041  call    cs:__imp_WdsSetupLogMessageW
0x180040047  lea     rdx, [rbp+1D0h+File]
0x18004004b  lea     rcx, [rsp+2D0h+var_268]
0x180040050  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180040056  nop
0x180040057  mov     rcx, rax; struct UnBCL::String *
0x18004005a  call    ?RecFindAndUnloadHive@@YAJPEAVString@UnBCL@@H@Z; RecFindAndUnloadHive(UnBCL::String *,int)
0x18004005f  mov     ebx, eax
0x180040061  lea     rcx, [rsp+2D0h+var_268]
0x180040066  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18004006c  test    ebx, ebx
0x18004006e  js      loc_180040130
0x180040074  lea     rax, [rsp+2D0h+var_270]
0x180040079  mov     [rsp+2D0h+var_2A8], rax; HKEY *
0x18004007e  mov     r8, r12; unsigned __int16 *
0x180040081  lea     rcx, [rbp+1D0h+File]; lpFile
0x180040085  call    ?RecLoadKey@@YAHPEBGPEAUHKEY__@@0KHPEAPEAU1@@Z; RecLoadKey(ushort const *,HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x18004008a  test    eax, eax
0x18004008c  jz      loc_180040126
0x180040092  call    cs:__imp_GetLastError
0x180040098  mov     edi, eax
0x18004009a  call    cs:__imp_CurrentIP
0x1800400a0  mov     rbx, rax
0x1800400a3  lea     r9, [rbp+1D0h+File]
0x1800400a7  lea     r8, aRecmountofflin_0; "RecMountOfflineHive"
0x1800400ae  lea     rdx, aHsHiveSWasSucc; "%hs: Hive %s was successfully mounted a"...
0x1800400b5  mov     ecx, 4000000h; unsigned int
0x1800400ba  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800400bf  mov     [rsp+2D0h+var_280], 0
0x1800400c7  mov     [rsp+2D0h+var_288], 0
0x1800400d0  mov     [rsp+2D0h+var_290], edi
0x1800400d4  mov     [rsp+2D0h+var_298], rbx
0x1800400d9  mov     [rsp+2D0h+var_2A0], r14
0x1800400de  mov     [rsp+2D0h+var_2A8], r15
0x1800400e3  mov     [rsp+2D0h+var_2B0], 26Fh
0x1800400eb  xor     r9d, r9d
0x1800400ee  lea     r8, aD; "D"
0x1800400f5  xor     edx, edx
0x1800400f7  mov     rcx, rax
0x1800400fa  call    cs:__imp_WdsSetupLogMessageW
0x180040100  mov     rax, [rsp+2D0h+var_270]
0x180040105  mov     rcx, [rbp+1D0h+var_40]
0x18004010c  xor     rcx, rsp; StackCookie
0x18004010f  call    __security_check_cookie
0x180040114  add     rsp, 2A0h
0x18004011b  pop     r15
0x18004011d  pop     r14
0x18004011f  pop     r12
0x180040121  pop     rdi
0x180040122  pop     rsi
0x180040123  pop     rbx
0x180040124  pop     rbp
0x180040125  retn
0x180040126  call    cs:__imp_GetLastError
0x18004012c  mov     esi, eax
0x18004012e  jmp     short loc_180040133
0x180040130  movzx   esi, bx
0x180040133  test    esi, esi
0x180040135  jz      short loc_180040100
0x180040137  call    cs:__imp_GetLastError
0x18004013d  mov     edi, eax
0x18004013f  call    cs:__imp_CurrentIP
0x180040145  mov     rbx, rax
0x180040148  mov     [rsp+2D0h+var_2B0], esi
0x18004014c  lea     r9, [rbp+1D0h+File]
0x180040150  lea     r8, aRecmountofflin_0; "RecMountOfflineHive"
0x180040157  lea     rdx, aHsCanTMountOff; "%hs: Can't mount offline hive: %s. Erro"...
0x18004015e  mov     ecx, 2000000h; unsigned int
0x180040163  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180040168  mov     [rsp+2D0h+var_280], 0
0x180040170  mov     [rsp+2D0h+var_288], 0
0x180040179  mov     [rsp+2D0h+var_290], edi
0x18004017d  mov     [rsp+2D0h+var_298], rbx
0x180040182  mov     [rsp+2D0h+var_2A0], r14
0x180040187  mov     [rsp+2D0h+var_2A8], r15
0x18004018c  mov     [rsp+2D0h+var_2B0], 27Eh
0x180040194  xor     r9d, r9d
0x180040197  lea     r8, aD; "D"
0x18004019e  xor     edx, edx
0x1800401a0  mov     rcx, rax
0x1800401a3  call    cs:__imp_WdsSetupLogMessageW
0x1800401a9  call    ?RecDumpNtHiveListToLog@@YAXXZ; RecDumpNtHiveListToLog(void)
0x1800401ae  mov     ecx, esi; dwErrCode
0x1800401b0  call    cs:__imp_SetLastError
0x1800401b6  jmp     loc_18003FF80
```
