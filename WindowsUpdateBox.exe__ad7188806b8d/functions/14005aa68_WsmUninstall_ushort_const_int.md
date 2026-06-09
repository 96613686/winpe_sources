# WsmUninstall(ushort const *,int)

- ea: `0x14005aa68`
- end: `0x14005b202`
- name: `?WsmUninstall@@YAJPEBGH@Z`
- size: `1946`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400570e0`

## callees

- `0x140023dcc`
- `0x1400288bc`
- `0x140028d5c`
- `0x140055d10`
- `0x1400597b8`
- `0x140059970`
- `0x140059b7c`
- `0x140059ffc`
- `0x14005a3c0`
- `0x14005aa68`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x14005ad3c`
- `ADVAPI32!RegDeleteTreeW` at `0x14005ae06`
- `ADVAPI32!RegDeleteTreeW` at `0x14005afa3`
- `ADVAPI32!RegDeleteTreeW` at `0x14005ad3c`
- `ADVAPI32!RegDeleteTreeW` at `0x14005ae06`
- `ADVAPI32!RegDeleteTreeW` at `0x14005afa3`
- `KERNEL32!CloseHandle` at `0x14005af51`
- `KERNEL32!CloseHandle` at `0x14005af78`
- `KERNEL32!CloseHandle` at `0x14005af51`
- `KERNEL32!CloseHandle` at `0x14005af78`
- `KERNEL32!HeapFree` at `0x14005ac9a`
- `KERNEL32!HeapFree` at `0x14005acbf`
- `KERNEL32!HeapFree` at `0x14005ace4`
- `KERNEL32!HeapFree` at `0x14005ad04`
- `KERNEL32!HeapFree` at `0x14005ac9a`
- `KERNEL32!HeapFree` at `0x14005acbf`
- `KERNEL32!HeapFree` at `0x14005ace4`
- `KERNEL32!HeapFree` at `0x14005ad04`
- `KERNEL32!GetProcessHeap` at `0x14005ac85`
- `KERNEL32!GetProcessHeap` at `0x14005acab`
- `KERNEL32!GetProcessHeap` at `0x14005acd0`
- `KERNEL32!GetProcessHeap` at `0x14005acf0`
- `KERNEL32!GetProcessHeap` at `0x14005ac85`
- `KERNEL32!GetProcessHeap` at `0x14005acab`
- `KERNEL32!GetProcessHeap` at `0x14005acd0`
- `KERNEL32!GetProcessHeap` at `0x14005acf0`
- `KERNEL32!GetLastError` at `0x14005aac2`
- `KERNEL32!GetLastError` at `0x14005aae0`
- `KERNEL32!GetLastError` at `0x14005aafe`
- `KERNEL32!GetLastError` at `0x14005abdc`
- `KERNEL32!GetLastError` at `0x14005abf7`
- `KERNEL32!GetLastError` at `0x14005ad6d`
- `KERNEL32!GetLastError` at `0x14005ae2a`
- `KERNEL32!GetLastError` at `0x14005aec7`
- `KERNEL32!GetLastError` at `0x14005afdc`
- `KERNEL32!GetLastError` at `0x14005b005`
- `KERNEL32!GetLastError` at `0x14005b01c`
- `KERNEL32!GetLastError` at `0x14005b08c`
- `KERNEL32!GetLastError` at `0x14005b0a3`
- `KERNEL32!GetLastError` at `0x14005b11b`
- `KERNEL32!GetLastError` at `0x14005b18f`
- `KERNEL32!GetLastError` at `0x14005aac2`
- `KERNEL32!GetLastError` at `0x14005aae0`
- `KERNEL32!GetLastError` at `0x14005aafe`
- `KERNEL32!GetLastError` at `0x14005abdc`
- `KERNEL32!GetLastError` at `0x14005abf7`
- `KERNEL32!GetLastError` at `0x14005ad6d`
- `KERNEL32!GetLastError` at `0x14005ae2a`
- `KERNEL32!GetLastError` at `0x14005aec7`
- `KERNEL32!GetLastError` at `0x14005afdc`
- `KERNEL32!GetLastError` at `0x14005b005`
- `KERNEL32!GetLastError` at `0x14005b01c`
- `KERNEL32!GetLastError` at `0x14005b08c`
- `KERNEL32!GetLastError` at `0x14005b0a3`
- `KERNEL32!GetLastError` at `0x14005b11b`
- `KERNEL32!GetLastError` at `0x14005b18f`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005ab71`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005ac6a`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005ade3`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005aea7`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005ab71`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005ac6a`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005ade3`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005aea7`
- `WDSCORE!CurrentIP` at `0x14005ab0c`
- `WDSCORE!CurrentIP` at `0x14005ac05`
- `WDSCORE!CurrentIP` at `0x14005ad7b`
- `WDSCORE!CurrentIP` at `0x14005ae38`
- `WDSCORE!CurrentIP` at `0x14005aed5`
- `WDSCORE!CurrentIP` at `0x14005b02a`
- `WDSCORE!CurrentIP` at `0x14005b0b1`
- `WDSCORE!CurrentIP` at `0x14005b129`
- `WDSCORE!CurrentIP` at `0x14005b19d`
- `WDSCORE!CurrentIP` at `0x14005ab0c`
- `WDSCORE!CurrentIP` at `0x14005ac05`
- `WDSCORE!CurrentIP` at `0x14005ad7b`
- `WDSCORE!CurrentIP` at `0x14005ae38`
- `WDSCORE!CurrentIP` at `0x14005aed5`
- `WDSCORE!CurrentIP` at `0x14005b02a`
- `WDSCORE!CurrentIP` at `0x14005b0b1`
- `WDSCORE!CurrentIP` at `0x14005b129`
- `WDSCORE!CurrentIP` at `0x14005b19d`

## string_xrefs

- `0x14005ab34`: `WsmUninstall`
- `0x14005ac2d`: `WsmUninstall`
- `0x14005ada6`: `WsmUninstall`
- `0x14005ae66`: `WsmUninstall`
- `0x14005af04`: `WsmUninstall`
- `0x14005b055`: `WsmUninstall`
- `0x14005b0dc`: `WsmUninstall`
- `0x14005b158`: `WsmUninstall`
- `0x14005b1cb`: `WsmUninstall`
- `0x14005ab1b`: `WsmUninstall: Failed to build driver file path; hr = 0x%x`
- `0x14005ac14`: `WsmUninstall: Failed to reset error control value; hr = 0x%x`
- `0x14005ad8a`: `WsmUninstall: Failed to delete config key %s; hr = 0x%x`
- `0x14005ae47`: `WsmUninstall: Failed to delete legacy config key %s; hr = 0x%x`
- `0x14005aee5`: `WsmUninstall: Failed to determine whether driver is loaded; hr = 0x%x`
- `0x14005b039`: `WsmUninstall: Failed to close device, hr = 0x%08x`
- `0x14005b0c0`: `WsmUninstall: Failed to close filter communication port, hr = 0x%08x`
- `0x14005b139`: `WsmUninstall: Failed to delete service key %s; hr = 0x%x`
- `0x14005b1ac`: `WsmUninstall: Failed to delete driver file %s; hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WsmUninstall(const unsigned __int16 *a1)
{
  char *v1; // r14
  char *v2; // r15
  char *Expand; // r13
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  signed int ServiceKeyName; // esi
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  __int64 v11; // rcx
  signed int v12; // eax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  LSTATUS v21; // eax
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  int v25; // eax
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  LSTATUS v32; // eax
  signed int v33; // eax
  signed int v34; // eax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  signed int v38; // eax
  DWORD v39; // edi
  __int64 v40; // rbx
  struct tagLOG_PARTIAL_MSG *v41; // rax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  DWORD v45; // edi
  __int64 v46; // rbx
  struct tagLOG_PARTIAL_MSG *v47; // rax
  __int128 v48; // [rsp+60h] [rbp-9h] BYREF
  char v49; // [rsp+70h] [rbp+7h]
  __int128 v50; // [rsp+78h] [rbp+Fh]
  LPVOID lpMem; // [rsp+D0h] [rbp+67h] BYREF
  int v52; // [rsp+D8h] [rbp+6Fh] BYREF
  LPCWSTR v53; // [rsp+E0h] [rbp+77h] BYREF
  LPCWSTR lpSubKey; // [rsp+E8h] [rbp+7Fh] BYREF

  v49 = 0;
  v1 = 0;
  lpMem = 0;
  v2 = 0;
  lpSubKey = 0;
  v48 = 0;
  v53 = 0;
  v50 = 0;
  v52 = 0;
  Expand = (char *)AllocateExpand();
  if ( !Expand )
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError > 0 )
      v5 = 1;
    if ( v5 )
    {
      v6 = GetLastError();
      ServiceKeyName = v6;
      if ( v6 > 0 )
        ServiceKeyName = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      ServiceKeyName = -2147467259;
    }
    v8 = GetLastError();
    v9 = CurrentIP();
    v10 = ConstructPartialMsgW(0x2000000u, "WsmUninstall: Failed to build driver file path; hr = 0x%x", ServiceKeyName);
    WdsSetupLogMessageW(
      v10,
      0,
      L"D",
      0,
      1066,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmUninstall",
      v9,
      v8,
      0,
      0);
    goto LABEL_25;
  }
  ServiceKeyName = WsmGetServiceKeyName(L"SYSTEM", &lpMem);
  if ( ServiceKeyName >= 0 )
  {
    ServiceKeyName = WsmGetConfigKeyName(L"SYSTEM", &lpSubKey);
    if ( ServiceKeyName < 0 )
    {
LABEL_17:
      v1 = (char *)lpSubKey;
      goto LABEL_18;
    }
    ServiceKeyName = WsmGetConfigKeyNameLegacy(L"SYSTEM", &v53);
    if ( ServiceKeyName < 0 )
    {
LABEL_16:
      v2 = (char *)v53;
      goto LABEL_17;
    }
    if ( !(unsigned int)RegSetDword(v11, lpMem) )
    {
      v12 = GetLastError();
      ServiceKeyName = v12;
      if ( v12 > 0 )
        ServiceKeyName = (unsigned __int16)v12 | 0x80070000;
      v13 = GetLastError();
      v14 = CurrentIP();
      v15 = ConstructPartialMsgW(
              0x2000000u,
              "WsmUninstall: Failed to reset error control value; hr = 0x%x",
              ServiceKeyName);
      WdsSetupLogMessageW(
        v15,
        0,
        L"D",
        0,
        1111,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmUninstall",
        v14,
        v13,
        0,
        0);
      goto LABEL_16;
    }
    v1 = (char *)lpSubKey;
    v21 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey);
    ServiceKeyName = v21;
    if ( v21 > 0 )
      ServiceKeyName = (unsigned __int16)v21 | 0x80070000;
    if ( ServiceKeyName == -2147024894 || ServiceKeyName >= 0 )
    {
      v2 = (char *)v53;
      v25 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v53);
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      ServiceKeyName = 0;
      if ( v25 != -2147024894 )
        ServiceKeyName = v25;
      if ( ServiceKeyName < 0 )
      {
        v26 = GetLastError();
        v27 = CurrentIP();
        v28 = ConstructPartialMsgW(
                0x2000000u,
                "WsmUninstall: Failed to delete legacy config key %s; hr = 0x%x",
                v2,
                ServiceKeyName);
        WdsSetupLogMessageW(
          v28,
          0,
          L"D",
          0,
          1140,
          L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
          L"WsmUninstall",
          v27,
          v26,
          0,
          0);
        goto LABEL_18;
      }
      ServiceKeyName = WsmIsLoaded(&v52);
      if ( ServiceKeyName >= 0 )
      {
        if ( v52 )
        {
          if ( hObject != (HANDLE)-1LL )
          {
            if ( !CloseHandle(hObject) )
            {
              v34 = GetLastError();
              ServiceKeyName = v34;
              if ( v34 > 0 )
                ServiceKeyName = (unsigned __int16)v34 | 0x80070000;
              v35 = GetLastError();
              v36 = CurrentIP();
              v37 = ConstructPartialMsgW(
                      0x2000000u,
                      "WsmUninstall: Failed to close device, hr = 0x%08x",
                      ServiceKeyName);
              WdsSetupLogMessageW(
                v37,
                0,
                L"D",
                0,
                1163,
                L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                L"WsmUninstall",
                v36,
                v35,
                0,
                0);
              goto LABEL_18;
            }
            hObject = (HANDLE)-1LL;
          }
          if ( qword_1400A5598 != (HANDLE)-1LL )
          {
            if ( !CloseHandle(qword_1400A5598) )
            {
              v38 = GetLastError();
              ServiceKeyName = v38;
              if ( v38 > 0 )
                ServiceKeyName = (unsigned __int16)v38 | 0x80070000;
              v39 = GetLastError();
              v40 = CurrentIP();
              v41 = ConstructPartialMsgW(
                      0x2000000u,
                      "WsmUninstall: Failed to close filter communication port, hr = 0x%08x",
                      ServiceKeyName);
              WdsSetupLogMessageW(
                v41,
                0,
                L"D",
                0,
                1174,
                L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                L"WsmUninstall",
                v40,
                v39,
                0,
                0);
              goto LABEL_18;
            }
            qword_1400A5598 = (HANDLE)-1LL;
          }
        }
        v32 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpMem);
        ServiceKeyName = v32;
        if ( v32 > 0 )
          ServiceKeyName = (unsigned __int16)v32 | 0x80070000;
        if ( ServiceKeyName == -2147024894 )
        {
          ServiceKeyName = 1;
        }
        else if ( ServiceKeyName < 0 )
        {
          v42 = GetLastError();
          v43 = CurrentIP();
          v44 = ConstructPartialMsgW(
                  0x2000000u,
                  "WsmUninstall: Failed to delete service key %s; hr = 0x%x",
                  (const char *)lpMem,
                  ServiceKeyName);
          WdsSetupLogMessageW(
            v44,
            0,
            L"D",
            0,
            1215,
            L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
            L"WsmUninstall",
            v43,
            v42,
            0,
            0);
          goto LABEL_18;
        }
        if ( !(unsigned int)DeleteFileEx2((__int64)Expand, 64) )
        {
          v33 = GetLastError();
          ServiceKeyName = v33;
          if ( v33 > 0 )
            ServiceKeyName = (unsigned __int16)v33 | 0x80070000;
          if ( ServiceKeyName == -2147024894 )
          {
            ServiceKeyName = 1;
          }
          else
          {
            v45 = GetLastError();
            v46 = CurrentIP();
            v47 = ConstructPartialMsgW(
                    0x2000000u,
                    "WsmUninstall: Failed to delete driver file %s; hr = 0x%x",
                    Expand,
                    ServiceKeyName);
            WdsSetupLogMessageW(
              v47,
              0,
              L"D",
              0,
              1233,
              L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
              L"WsmUninstall",
              v46,
              v45,
              0,
              0);
          }
        }
        goto LABEL_18;
      }
      v29 = GetLastError();
      v30 = CurrentIP();
      v31 = ConstructPartialMsgW(
              0x2000000u,
              "WsmUninstall: Failed to determine whether driver is loaded; hr = 0x%x",
              (_DWORD)lpMem);
      WdsSetupLogMessageW(
        v31,
        0,
        L"D",
        0,
        1149,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmUninstall",
        v30,
        v29,
        0,
        0);
    }
    else
    {
      v22 = GetLastError();
      v23 = CurrentIP();
      v24 = ConstructPartialMsgW(
              0x2000000u,
              "WsmUninstall: Failed to delete config key %s; hr = 0x%x",
              v1,
              ServiceKeyName);
      WdsSetupLogMessageW(
        v24,
        0,
        L"D",
        0,
        1128,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmUninstall",
        v23,
        v22,
        0,
        0);
      v2 = (char *)v53;
    }
  }
LABEL_18:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v2 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v2);
  }
  if ( v1 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v1);
  }
  v19 = GetProcessHeap();
  HeapFree(v19, 0, Expand);
LABEL_25:
  CSystemHive::Unload((CSystemHive *)&v48);
  return (unsigned int)ServiceKeyName;
}

```

## disassembly

```asm
0x14005aa68  mov     [rsp-8+arg_8], edx
0x14005aa6c  mov     [rsp-8+lpMem], rcx
0x14005aa71  push    rbp
0x14005aa72  push    rbx
0x14005aa73  push    rsi
0x14005aa74  push    rdi
0x14005aa75  push    r13
0x14005aa77  push    r14
0x14005aa79  push    r15
0x14005aa7b  lea     rbp, [rsp-27h]
0x14005aa80  sub     rsp, 90h
0x14005aa87  xorps   xmm0, xmm0
0x14005aa8a  mov     [rbp+57h+var_50], 0
0x14005aa8e  xor     r14d, r14d
0x14005aa91  mov     [rbp+57h+lpMem], 0
0x14005aa99  xor     r15d, r15d
0x14005aa9c  mov     [rbp+57h+lpSubKey], r14
0x14005aaa0  movups  [rbp+57h+var_60], xmm0
0x14005aaa4  mov     [rbp+57h+arg_10], r15
0x14005aaa8  movdqu  [rbp+57h+var_48], xmm0
0x14005aaad  mov     [rbp+57h+arg_8], r14d
0x14005aab1  call    AllocateExpand
0x14005aab6  mov     r13, rax
0x14005aab9  test    rax, rax
0x14005aabc  jnz     loc_14005AB82
0x14005aac2  call    cs:__imp_GetLastError
0x14005aac9  nop     dword ptr [rax+rax+00h]
0x14005aace  mov     ebx, 80070000h
0x14005aad3  test    eax, eax
0x14005aad5  jle     short loc_14005AADE
0x14005aad7  movzx   eax, ax
0x14005aada  or      eax, ebx
0x14005aadc  test    eax, eax
0x14005aade  jns     short loc_14005AAF9
0x14005aae0  call    cs:__imp_GetLastError
0x14005aae7  nop     dword ptr [rax+rax+00h]
0x14005aaec  mov     esi, eax
0x14005aaee  test    eax, eax
0x14005aaf0  jle     short loc_14005AAFE
0x14005aaf2  movzx   esi, ax
0x14005aaf5  or      esi, ebx
0x14005aaf7  jmp     short loc_14005AAFE
0x14005aaf9  mov     esi, 80004005h
0x14005aafe  call    cs:__imp_GetLastError
0x14005ab05  nop     dword ptr [rax+rax+00h]
0x14005ab0a  mov     edi, eax
0x14005ab0c  call    cs:__imp_CurrentIP
0x14005ab13  nop     dword ptr [rax+rax+00h]
0x14005ab18  mov     r8d, esi
0x14005ab1b  lea     rdx, aWsmuninstallFa_0; "WsmUninstall: Failed to build driver fi"...
0x14005ab22  mov     ecx, 2000000h; unsigned int
0x14005ab27  mov     rbx, rax
0x14005ab2a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005ab2f  mov     [rsp+0C0h+var_70], r14d
0x14005ab34  lea     rcx, aWsmuninstall; "WsmUninstall"
0x14005ab3b  mov     [rsp+0C0h+var_78], r14
0x14005ab40  lea     r8, aD; "D"
0x14005ab47  mov     [rsp+0C0h+var_80], edi
0x14005ab4b  xor     r9d, r9d
0x14005ab4e  mov     [rsp+0C0h+var_88], rbx
0x14005ab53  xor     edx, edx
0x14005ab55  mov     [rsp+0C0h+var_90], rcx
0x14005ab5a  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005ab61  mov     [rsp+0C0h+var_98], rcx
0x14005ab66  mov     rcx, rax
0x14005ab69  mov     [rsp+0C0h+var_A0], 42Ah
0x14005ab71  call    cs:__imp_WdsSetupLogMessageW
0x14005ab78  nop     dword ptr [rax+rax+00h]
0x14005ab7d  jmp     loc_14005AD10
0x14005ab82  lea     rbx, aSystem; "SYSTEM"
0x14005ab89  mov     rcx, rbx
0x14005ab8c  lea     rdx, [rbp+57h+lpMem]
0x14005ab90  call    WsmGetServiceKeyName
0x14005ab95  mov     esi, eax
0x14005ab97  test    eax, eax
0x14005ab99  js      loc_14005AC7E
0x14005ab9f  lea     rdx, [rbp+57h+lpSubKey]
0x14005aba3  mov     rcx, rbx
0x14005aba6  call    WsmGetConfigKeyName
0x14005abab  mov     esi, eax
0x14005abad  test    eax, eax
0x14005abaf  js      loc_14005AC7A
0x14005abb5  lea     rdx, [rbp+57h+arg_10]
0x14005abb9  mov     rcx, rbx
0x14005abbc  call    WsmGetConfigKeyNameLegacy
0x14005abc1  mov     esi, eax
0x14005abc3  test    eax, eax
0x14005abc5  js      loc_14005AC76
0x14005abcb  mov     rdx, [rbp+57h+lpMem]
0x14005abcf  call    RegSetDword
0x14005abd4  test    eax, eax
0x14005abd6  jnz     loc_14005AD2E
0x14005abdc  call    cs:__imp_GetLastError
0x14005abe3  nop     dword ptr [rax+rax+00h]
0x14005abe8  mov     esi, eax
0x14005abea  test    eax, eax
0x14005abec  jle     short loc_14005ABF7
0x14005abee  movzx   esi, ax
0x14005abf1  or      esi, 80070000h
0x14005abf7  call    cs:__imp_GetLastError
0x14005abfe  nop     dword ptr [rax+rax+00h]
0x14005ac03  mov     edi, eax
0x14005ac05  call    cs:__imp_CurrentIP
0x14005ac0c  nop     dword ptr [rax+rax+00h]
0x14005ac11  mov     r8d, esi
0x14005ac14  lea     rdx, aWsmuninstallFa; "WsmUninstall: Failed to reset error con"...
0x14005ac1b  mov     ecx, 2000000h; unsigned int
0x14005ac20  mov     rbx, rax
0x14005ac23  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005ac28  mov     [rsp+0C0h+var_70], r14d
0x14005ac2d  lea     rcx, aWsmuninstall; "WsmUninstall"
0x14005ac34  mov     [rsp+0C0h+var_78], r14
0x14005ac39  lea     r8, aD; "D"
0x14005ac40  mov     [rsp+0C0h+var_80], edi
0x14005ac44  xor     r9d, r9d
0x14005ac47  mov     [rsp+0C0h+var_88], rbx
0x14005ac4c  xor     edx, edx
0x14005ac4e  mov     [rsp+0C0h+var_90], rcx
0x14005ac53  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005ac5a  mov     [rsp+0C0h+var_98], rcx
0x14005ac5f  mov     rcx, rax
0x14005ac62  mov     [rsp+0C0h+var_A0], 457h
0x14005ac6a  call    cs:__imp_WdsSetupLogMessageW
0x14005ac71  nop     dword ptr [rax+rax+00h]
0x14005ac76  mov     r15, [rbp+57h+arg_10]
0x14005ac7a  mov     r14, [rbp+57h+lpSubKey]
0x14005ac7e  cmp     [rbp+57h+lpMem], 0
0x14005ac83  jz      short loc_14005ACA6
0x14005ac85  call    cs:__imp_GetProcessHeap
0x14005ac8c  nop     dword ptr [rax+rax+00h]
0x14005ac91  mov     r8, [rbp+57h+lpMem]; lpMem
0x14005ac95  xor     edx, edx; dwFlags
0x14005ac97  mov     rcx, rax; hHeap
0x14005ac9a  call    cs:__imp_HeapFree
0x14005aca1  nop     dword ptr [rax+rax+00h]
0x14005aca6  test    r15, r15
0x14005aca9  jz      short loc_14005ACCB
0x14005acab  call    cs:__imp_GetProcessHeap
0x14005acb2  nop     dword ptr [rax+rax+00h]
0x14005acb7  mov     r8, r15; lpMem
0x14005acba  xor     edx, edx; dwFlags
0x14005acbc  mov     rcx, rax; hHeap
0x14005acbf  call    cs:__imp_HeapFree
0x14005acc6  nop     dword ptr [rax+rax+00h]
0x14005accb  test    r14, r14
0x14005acce  jz      short loc_14005ACF0
0x14005acd0  call    cs:__imp_GetProcessHeap
0x14005acd7  nop     dword ptr [rax+rax+00h]
0x14005acdc  mov     r8, r14; lpMem
0x14005acdf  xor     edx, edx; dwFlags
0x14005ace1  mov     rcx, rax; hHeap
0x14005ace4  call    cs:__imp_HeapFree
0x14005aceb  nop     dword ptr [rax+rax+00h]
0x14005acf0  call    cs:__imp_GetProcessHeap
0x14005acf7  nop     dword ptr [rax+rax+00h]
0x14005acfc  mov     r8, r13; lpMem
0x14005acff  xor     edx, edx; dwFlags
0x14005ad01  mov     rcx, rax; hHeap
0x14005ad04  call    cs:__imp_HeapFree
0x14005ad0b  nop     dword ptr [rax+rax+00h]
0x14005ad10  lea     rcx, [rbp+57h+var_60]; this
0x14005ad14  call    ?Unload@CSystemHive@@QEAAJXZ; CSystemHive::Unload(void)
0x14005ad19  mov     eax, esi
0x14005ad1b  add     rsp, 90h
0x14005ad22  pop     r15
0x14005ad24  pop     r14
0x14005ad26  pop     r13
0x14005ad28  pop     rdi
0x14005ad29  pop     rsi
0x14005ad2a  pop     rbx
0x14005ad2b  pop     rbp
0x14005ad2c  retn
0x14005ad2e  mov     r14, [rbp+57h+lpSubKey]
0x14005ad32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005ad39  mov     rdx, r14; lpSubKey
0x14005ad3c  call    cs:__imp_RegDeleteTreeW
0x14005ad43  nop     dword ptr [rax+rax+00h]
0x14005ad48  mov     esi, eax
0x14005ad4a  mov     ebx, 80070000h
0x14005ad4f  test    eax, eax
0x14005ad51  jle     short loc_14005AD58
0x14005ad53  movzx   esi, ax
0x14005ad56  or      esi, ebx
0x14005ad58  mov     edi, 80070002h
0x14005ad5d  cmp     esi, edi
0x14005ad5f  jz      loc_14005ADF8
0x14005ad65  test    esi, esi
0x14005ad67  jns     loc_14005ADF8
0x14005ad6d  call    cs:__imp_GetLastError
0x14005ad74  nop     dword ptr [rax+rax+00h]
0x14005ad79  mov     edi, eax
0x14005ad7b  call    cs:__imp_CurrentIP
0x14005ad82  nop     dword ptr [rax+rax+00h]
0x14005ad87  mov     r9d, esi
0x14005ad8a  lea     rdx, aWsmuninstallFa_3; "WsmUninstall: Failed to delete config k"...
0x14005ad91  mov     r8, r14
0x14005ad94  mov     ecx, 2000000h; unsigned int
0x14005ad99  mov     rbx, rax
0x14005ad9c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005ada1  mov     [rsp+0C0h+var_70], r15d
0x14005ada6  lea     rcx, aWsmuninstall; "WsmUninstall"
0x14005adad  mov     [rsp+0C0h+var_78], r15
0x14005adb2  lea     r8, aD; "D"
0x14005adb9  mov     [rsp+0C0h+var_80], edi
0x14005adbd  xor     r9d, r9d
0x14005adc0  mov     [rsp+0C0h+var_88], rbx
0x14005adc5  xor     edx, edx
0x14005adc7  mov     [rsp+0C0h+var_90], rcx
0x14005adcc  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005add3  mov     [rsp+0C0h+var_98], rcx
0x14005add8  mov     rcx, rax
0x14005addb  mov     [rsp+0C0h+var_A0], 468h
0x14005ade3  call    cs:__imp_WdsSetupLogMessageW
0x14005adea  nop     dword ptr [rax+rax+00h]
0x14005adef  mov     r15, [rbp+57h+arg_10]
0x14005adf3  jmp     loc_14005AC7E
0x14005adf8  mov     r15, [rbp+57h+arg_10]
0x14005adfc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005ae03  mov     rdx, r15; lpSubKey
0x14005ae06  call    cs:__imp_RegDeleteTreeW
0x14005ae0d  nop     dword ptr [rax+rax+00h]
0x14005ae12  test    eax, eax
0x14005ae14  jle     short loc_14005AE1B
0x14005ae16  movzx   eax, ax
0x14005ae19  or      eax, ebx
0x14005ae1b  xor     esi, esi
0x14005ae1d  cmp     eax, edi
0x14005ae1f  cmovnz  esi, eax
0x14005ae22  test    esi, esi
0x14005ae24  jns     loc_14005AEB8
0x14005ae2a  call    cs:__imp_GetLastError
0x14005ae31  nop     dword ptr [rax+rax+00h]
0x14005ae36  mov     edi, eax
0x14005ae38  call    cs:__imp_CurrentIP
0x14005ae3f  nop     dword ptr [rax+rax+00h]
0x14005ae44  mov     r9d, esi
0x14005ae47  lea     rdx, aWsmuninstallFa_2; "WsmUninstall: Failed to delete legacy c"...
0x14005ae4e  mov     r8, r15
0x14005ae51  mov     ecx, 2000000h; unsigned int
0x14005ae56  mov     rbx, rax
0x14005ae59  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005ae5e  mov     [rsp+0C0h+var_70], 0
0x14005ae66  lea     rcx, aWsmuninstall; "WsmUninstall"
0x14005ae6d  mov     [rsp+0C0h+var_78], 0
0x14005ae76  mov     [rsp+0C0h+var_80], edi
0x14005ae7a  mov     [rsp+0C0h+var_88], rbx
0x14005ae7f  mov     [rsp+0C0h+var_90], rcx
0x14005ae84  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005ae8b  mov     [rsp+0C0h+var_98], rcx
0x14005ae90  mov     [rsp+0C0h+var_A0], 474h
0x14005ae98  xor     r9d, r9d
0x14005ae9b  lea     r8, aD; "D"
0x14005aea2  xor     edx, edx
0x14005aea4  mov     rcx, rax
0x14005aea7  call    cs:__imp_WdsSetupLogMessageW
0x14005aeae  nop     dword ptr [rax+rax+00h]
0x14005aeb3  jmp     loc_14005AC7E
0x14005aeb8  lea     rcx, [rbp+57h+arg_8]; int *
0x14005aebc  call    ?WsmIsLoaded@@YAJPEAH@Z; WsmIsLoaded(int *)
0x14005aec1  mov     esi, eax
0x14005aec3  test    eax, eax
0x14005aec5  jns     short loc_14005AF3B
0x14005aec7  call    cs:__imp_GetLastError
0x14005aece  nop     dword ptr [rax+rax+00h]
0x14005aed3  mov     edi, eax
0x14005aed5  call    cs:__imp_CurrentIP
0x14005aedc  nop     dword ptr [rax+rax+00h]
0x14005aee1  mov     r8, [rbp+57h+lpMem]
0x14005aee5  lea     rdx, aWsmuninstallFa_4; "WsmUninstall: Failed to determine wheth"...
0x14005aeec  mov     r9d, esi
0x14005aeef  mov     ecx, 2000000h; unsigned int
0x14005aef4  mov     rbx, rax
0x14005aef7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005aefc  mov     [rsp+0C0h+var_70], 0
0x14005af04  lea     rcx, aWsmuninstall; "WsmUninstall"
0x14005af0b  mov     [rsp+0C0h+var_78], 0
0x14005af14  mov     [rsp+0C0h+var_80], edi
0x14005af18  mov     [rsp+0C0h+var_88], rbx
0x14005af1d  mov     [rsp+0C0h+var_90], rcx
0x14005af22  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005af29  mov     [rsp+0C0h+var_98], rcx
0x14005af2e  mov     [rsp+0C0h+var_A0], 47Dh
0x14005af36  jmp     loc_14005AE98
0x14005af3b  cmp     [rbp+57h+arg_8], 0
0x14005af3f  jz      short loc_14005AF98
0x14005af41  mov     rcx, cs:hObject; hObject
0x14005af48  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14005af4c  cmp     rcx, rdi
0x14005af4f  jz      short loc_14005AF6C
0x14005af51  call    cs:__imp_CloseHandle
0x14005af58  nop     dword ptr [rax+rax+00h]
0x14005af5d  test    eax, eax
0x14005af5f  jz      loc_14005B005
0x14005af65  mov     cs:hObject, rdi
0x14005af6c  mov     rcx, cs:qword_1400A5598; hObject
0x14005af73  cmp     rcx, rdi
0x14005af76  jz      short loc_14005AF93
0x14005af78  call    cs:__imp_CloseHandle
0x14005af7f  nop     dword ptr [rax+rax+00h]
0x14005af84  test    eax, eax
  ... truncated ...
```
