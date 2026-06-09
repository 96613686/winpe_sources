# WsmUnload(void)

- ea: `0x14005b208`
- end: `0x14005b7a3`
- name: `?WsmUnload@@YAJXZ`
- size: `1435`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400570e0`

## callees

- `0x140023dcc`
- `0x1400288bc`
- `0x140028980`
- `0x140028b98`
- `0x140055d10`
- `0x140059970`
- `0x140059ffc`
- `0x14005b208`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x14005b59b`
- `ADVAPI32!RegDeleteTreeW` at `0x14005b59b`
- `KERNEL32!CloseHandle` at `0x14005b257`
- `KERNEL32!CloseHandle` at `0x14005b27e`
- `KERNEL32!CloseHandle` at `0x14005b257`
- `KERNEL32!CloseHandle` at `0x14005b27e`
- `KERNEL32!HeapFree` at `0x14005b707`
- `KERNEL32!HeapFree` at `0x14005b733`
- `KERNEL32!HeapFree` at `0x14005b765`
- `KERNEL32!HeapFree` at `0x14005b707`
- `KERNEL32!HeapFree` at `0x14005b733`
- `KERNEL32!HeapFree` at `0x14005b765`
- `KERNEL32!GetProcessHeap` at `0x14005b6f3`
- `KERNEL32!GetProcessHeap` at `0x14005b71f`
- `KERNEL32!GetProcessHeap` at `0x14005b74c`
- `KERNEL32!GetProcessHeap` at `0x14005b6f3`
- `KERNEL32!GetProcessHeap` at `0x14005b71f`
- `KERNEL32!GetProcessHeap` at `0x14005b74c`
- `KERNEL32!GetLastError` at `0x14005b2c3`
- `KERNEL32!GetLastError` at `0x14005b32d`
- `KERNEL32!GetLastError` at `0x14005b348`
- `KERNEL32!GetLastError` at `0x14005b3cc`
- `KERNEL32!GetLastError` at `0x14005b3e7`
- `KERNEL32!GetLastError` at `0x14005b450`
- `KERNEL32!GetLastError` at `0x14005b4ef`
- `KERNEL32!GetLastError` at `0x14005b5bf`
- `KERNEL32!GetLastError` at `0x14005b65c`
- `KERNEL32!GetLastError` at `0x14005b673`
- `KERNEL32!GetLastError` at `0x14005b2c3`
- `KERNEL32!GetLastError` at `0x14005b32d`
- `KERNEL32!GetLastError` at `0x14005b348`
- `KERNEL32!GetLastError` at `0x14005b3cc`
- `KERNEL32!GetLastError` at `0x14005b3e7`
- `KERNEL32!GetLastError` at `0x14005b450`
- `KERNEL32!GetLastError` at `0x14005b4ef`
- `KERNEL32!GetLastError` at `0x14005b5bf`
- `KERNEL32!GetLastError` at `0x14005b65c`
- `KERNEL32!GetLastError` at `0x14005b673`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b3bb`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b55f`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b62e`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b6e2`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b3bb`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b55f`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b62e`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005b6e2`
- `WDSCORE!CurrentIP` at `0x14005b2d1`
- `WDSCORE!CurrentIP` at `0x14005b356`
- `WDSCORE!CurrentIP` at `0x14005b3f5`
- `WDSCORE!CurrentIP` at `0x14005b45e`
- `WDSCORE!CurrentIP` at `0x14005b4fd`
- `WDSCORE!CurrentIP` at `0x14005b5cd`
- `WDSCORE!CurrentIP` at `0x14005b681`
- `WDSCORE!CurrentIP` at `0x14005b2d1`
- `WDSCORE!CurrentIP` at `0x14005b356`
- `WDSCORE!CurrentIP` at `0x14005b3f5`
- `WDSCORE!CurrentIP` at `0x14005b45e`
- `WDSCORE!CurrentIP` at `0x14005b4fd`
- `WDSCORE!CurrentIP` at `0x14005b5cd`
- `WDSCORE!CurrentIP` at `0x14005b681`
- `FLTLIB!FilterUnload` at `0x14005b2a0`
- `FLTLIB!FilterUnload` at `0x14005b2a0`

## string_xrefs

- `0x14005b220`: `SeLoadDriverPrivilege`
- `0x14005b783`: `SeLoadDriverPrivilege`
- `0x14005b404`: `WsmUnload: Failed to close filter communication port, hr = 0x%08x`
- `0x14005b2e9`: `Filter %s not installed; nothing to unload`
- `0x14005b509`: `Driver configuration does not exist after unload; uninstalling driver`
- `0x14005b5dc`: `WsmUnload: Failed to delete service key %s; hr = 0x%x`
- `0x14005b690`: `WsmUnload: Failed to delete driver file %s; hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 WsmUnload(void)
{
  int v0; // ebp
  HRESULT v1; // eax
  signed int ConfigKeyName; // esi
  DWORD v3; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  signed int LastError; // eax
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  signed int v10; // eax
  DWORD v11; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  __int64 v17; // rcx
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  int ServiceKeyName; // eax
  char *v22; // r13
  LSTATUS v23; // eax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  char *Expand; // rbp
  signed int v28; // eax
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  int v36; // [rsp+A0h] [rbp+8h]
  LPVOID lpMem; // [rsp+B0h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+B8h] [rbp+20h] BYREF

  lpMem = 0;
  lpSubKey = 0;
  v36 = EnablePrivilegeEx(L"SeLoadDriverPrivilege");
  v0 = v36;
  if ( hObject != (HANDLE)-1LL )
  {
    if ( !CloseHandle(hObject) )
    {
      LastError = GetLastError();
      ConfigKeyName = LastError;
      if ( LastError > 0 )
        ConfigKeyName = (unsigned __int16)LastError | 0x80070000;
      v7 = GetLastError();
      v8 = CurrentIP();
      v9 = ConstructPartialMsgW(0x2000000u, "WsmUnload: Failed to close device, hr = 0x%08x", ConfigKeyName);
      WdsSetupLogMessageW(
        v9,
        0,
        L"D",
        0,
        1428,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmUnload",
        v8,
        v7,
        0,
        0);
      goto LABEL_35;
    }
    hObject = (HANDLE)-1LL;
  }
  if ( qword_1400A5598 == (HANDLE)-1LL )
    goto LABEL_7;
  if ( CloseHandle(qword_1400A5598) )
  {
    qword_1400A5598 = (HANDLE)-1LL;
LABEL_7:
    v1 = FilterUnload(L"WinSetupMon");
    ConfigKeyName = v1;
    if ( v1 >= 0 )
    {
      ConfigKeyName = WsmGetConfigKeyName(L"SYSTEM", &lpMem);
      if ( ConfigKeyName >= 0 && !(unsigned int)RegExists(v17, lpMem, 0) )
      {
        v18 = GetLastError();
        v19 = CurrentIP();
        v20 = ConstructPartialMsgW(0x4000000u, "Driver configuration does not exist after unload; uninstalling driver");
        WdsSetupLogMessageW(
          v20,
          0,
          L"D",
          0,
          1469,
          L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
          L"WsmUnload",
          v19,
          v18,
          0,
          0);
        ServiceKeyName = WsmGetServiceKeyName(L"SYSTEM", &lpSubKey);
        v22 = (char *)lpSubKey;
        ConfigKeyName = ServiceKeyName;
        if ( ServiceKeyName >= 0 )
        {
          v23 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey);
          ConfigKeyName = v23;
          if ( v23 > 0 )
            ConfigKeyName = (unsigned __int16)v23 | 0x80070000;
          if ( ConfigKeyName >= 0 )
          {
            Expand = (char *)AllocateExpand();
            if ( !(unsigned int)DeleteFileEx2((__int64)Expand, 64) )
            {
              v28 = GetLastError();
              ConfigKeyName = v28;
              if ( v28 > 0 )
                ConfigKeyName = (unsigned __int16)v28 | 0x80070000;
              v29 = GetLastError();
              v30 = CurrentIP();
              v31 = ConstructPartialMsgW(
                      0x2000000u,
                      "WsmUnload: Failed to delete driver file %s; hr = 0x%x",
                      Expand,
                      ConfigKeyName);
              WdsSetupLogMessageW(
                v31,
                0,
                L"D",
                0,
                1500,
                L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
                L"WsmUnload",
                v30,
                v29,
                0,
                0);
            }
            if ( Expand )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, Expand);
            }
            v0 = v36;
          }
          else
          {
            v24 = GetLastError();
            v25 = CurrentIP();
            v26 = ConstructPartialMsgW(
                    0x2000000u,
                    "WsmUnload: Failed to delete service key %s; hr = 0x%x",
                    v22,
                    ConfigKeyName);
            WdsSetupLogMessageW(
              v26,
              0,
              L"D",
              0,
              1484,
              L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
              L"WsmUnload",
              v25,
              v24,
              0,
              0);
          }
        }
        if ( v22 )
        {
          v33 = GetProcessHeap();
          HeapFree(v33, 0, v22);
        }
      }
      if ( lpMem )
      {
        v34 = GetProcessHeap();
        HeapFree(v34, 0, lpMem);
      }
    }
    else if ( v1 == -2145452013 )
    {
      ConfigKeyName = 1;
      v3 = GetLastError();
      v4 = CurrentIP();
      v5 = ConstructPartialMsgW(0x4000000u, "Filter %s not installed; nothing to unload", (const char *)L"WinSetupMon");
      WdsSetupLogMessageW(
        v5,
        0,
        L"D",
        0,
        1445,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmUnload",
        v4,
        v3,
        0,
        0);
    }
    else
    {
      v14 = GetLastError();
      v15 = CurrentIP();
      v16 = ConstructPartialMsgW(0x2000000u, "WsmUnload: Failed FilterUnload(); hr = 0x%x", ConfigKeyName);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        1449,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmUnload",
        v15,
        v14,
        0,
        0);
    }
    goto LABEL_35;
  }
  v10 = GetLastError();
  ConfigKeyName = v10;
  if ( v10 > 0 )
    ConfigKeyName = (unsigned __int16)v10 | 0x80070000;
  v11 = GetLastError();
  v12 = CurrentIP();
  v13 = ConstructPartialMsgW(
          0x2000000u,
          "WsmUnload: Failed to close filter communication port, hr = 0x%08x",
          ConfigKeyName);
  WdsSetupLogMessageW(
    v13,
    0,
    L"D",
    0,
    1435,
    L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
    L"WsmUnload",
    v12,
    v11,
    0,
    0);
LABEL_35:
  if ( v0 == 1 )
    EnablePrivilegeEx(L"SeLoadDriverPrivilege");
  return (unsigned int)ConfigKeyName;
}

```

## disassembly

```asm
0x14005b208  mov     rax, rsp
0x14005b20b  push    rbx
0x14005b20c  push    rbp
0x14005b20d  push    rsi
0x14005b20e  push    rdi
0x14005b20f  push    r13
0x14005b211  push    r14
0x14005b213  push    r15
0x14005b215  sub     rsp, 60h
0x14005b219  xor     r13d, r13d
0x14005b21c  lea     r8, [rax+10h]
0x14005b220  lea     rcx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x14005b227  mov     [rax+10h], r13d
0x14005b22b  mov     [rax+18h], r13
0x14005b22f  mov     [rax+20h], r13
0x14005b233  lea     edi, [r13+1]
0x14005b237  mov     edx, edi
0x14005b239  call    EnablePrivilegeEx
0x14005b23e  mov     rcx, cs:hObject; hObject
0x14005b245  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14005b249  mov     [rsp+98h+arg_0], eax
0x14005b250  mov     ebp, eax
0x14005b252  cmp     rcx, rbx
0x14005b255  jz      short loc_14005B272
0x14005b257  call    cs:__imp_CloseHandle
0x14005b25e  nop     dword ptr [rax+rax+00h]
0x14005b263  test    eax, eax
0x14005b265  jz      loc_14005B32D
0x14005b26b  mov     cs:hObject, rbx
0x14005b272  mov     rcx, cs:qword_1400A5598; hObject
0x14005b279  cmp     rcx, rbx
0x14005b27c  jz      short loc_14005B299
0x14005b27e  call    cs:__imp_CloseHandle
0x14005b285  nop     dword ptr [rax+rax+00h]
0x14005b28a  test    eax, eax
0x14005b28c  jz      loc_14005B3CC
0x14005b292  mov     cs:qword_1400A5598, rbx
0x14005b299  lea     rcx, FilterName; "WinSetupMon"
0x14005b2a0  call    cs:__imp_FilterUnload
0x14005b2a7  nop     dword ptr [rax+rax+00h]
0x14005b2ac  mov     esi, eax
0x14005b2ae  test    eax, eax
0x14005b2b0  jns     loc_14005B4B9
0x14005b2b6  cmp     eax, 801F0013h
0x14005b2bb  jnz     loc_14005B450
0x14005b2c1  mov     esi, edi
0x14005b2c3  call    cs:__imp_GetLastError
0x14005b2ca  nop     dword ptr [rax+rax+00h]
0x14005b2cf  mov     edi, eax
0x14005b2d1  call    cs:__imp_CurrentIP
0x14005b2d8  nop     dword ptr [rax+rax+00h]
0x14005b2dd  lea     r8, FilterName; "WinSetupMon"
0x14005b2e4  mov     ecx, 4000000h; unsigned int
0x14005b2e9  lea     rdx, aFilterSNotInst; "Filter %s not installed; nothing to unl"...
0x14005b2f0  mov     rbx, rax
0x14005b2f3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b2f8  mov     [rsp+98h+var_48], r13d
0x14005b2fd  lea     r14, aWsmunload; "WsmUnload"
0x14005b304  mov     [rsp+98h+var_50], r13
0x14005b309  lea     r15, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005b310  mov     [rsp+98h+var_58], edi
0x14005b314  mov     [rsp+98h+var_60], rbx
0x14005b319  mov     [rsp+98h+var_68], r14
0x14005b31e  mov     [rsp+98h+var_70], r15
0x14005b323  mov     [rsp+98h+var_78], 5A5h
0x14005b32b  jmp     short loc_14005B3AC
0x14005b32d  call    cs:__imp_GetLastError
0x14005b334  nop     dword ptr [rax+rax+00h]
0x14005b339  mov     esi, eax
0x14005b33b  test    eax, eax
0x14005b33d  jle     short loc_14005B348
0x14005b33f  movzx   esi, ax
0x14005b342  or      esi, 80070000h
0x14005b348  call    cs:__imp_GetLastError
0x14005b34f  nop     dword ptr [rax+rax+00h]
0x14005b354  mov     edi, eax
0x14005b356  call    cs:__imp_CurrentIP
0x14005b35d  nop     dword ptr [rax+rax+00h]
0x14005b362  mov     r8d, esi
0x14005b365  lea     rdx, aWsmunloadFaile_0; "WsmUnload: Failed to close device, hr ="...
0x14005b36c  mov     ecx, 2000000h; unsigned int
0x14005b371  mov     rbx, rax
0x14005b374  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b379  mov     [rsp+98h+var_48], r13d
0x14005b37e  lea     r14, aWsmunload; "WsmUnload"
0x14005b385  mov     [rsp+98h+var_50], r13
0x14005b38a  lea     r15, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005b391  mov     [rsp+98h+var_58], edi
0x14005b395  mov     [rsp+98h+var_60], rbx
0x14005b39a  mov     [rsp+98h+var_68], r14
0x14005b39f  mov     [rsp+98h+var_70], r15
0x14005b3a4  mov     [rsp+98h+var_78], 594h
0x14005b3ac  xor     r9d, r9d
0x14005b3af  lea     r8, aD; "D"
0x14005b3b6  xor     edx, edx
0x14005b3b8  mov     rcx, rax
0x14005b3bb  call    cs:__imp_WdsSetupLogMessageW
0x14005b3c2  nop     dword ptr [rax+rax+00h]
0x14005b3c7  jmp     loc_14005B771
0x14005b3cc  call    cs:__imp_GetLastError
0x14005b3d3  nop     dword ptr [rax+rax+00h]
0x14005b3d8  mov     esi, eax
0x14005b3da  test    eax, eax
0x14005b3dc  jle     short loc_14005B3E7
0x14005b3de  movzx   esi, ax
0x14005b3e1  or      esi, 80070000h
0x14005b3e7  call    cs:__imp_GetLastError
0x14005b3ee  nop     dword ptr [rax+rax+00h]
0x14005b3f3  mov     edi, eax
0x14005b3f5  call    cs:__imp_CurrentIP
0x14005b3fc  nop     dword ptr [rax+rax+00h]
0x14005b401  mov     r8d, esi
0x14005b404  lea     rdx, aWsmunloadFaile; "WsmUnload: Failed to close filter commu"...
0x14005b40b  mov     ecx, 2000000h; unsigned int
0x14005b410  mov     rbx, rax
0x14005b413  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b418  mov     [rsp+98h+var_48], r13d
0x14005b41d  lea     r14, aWsmunload; "WsmUnload"
0x14005b424  mov     [rsp+98h+var_50], r13
0x14005b429  lea     r15, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005b430  mov     [rsp+98h+var_58], edi
0x14005b434  mov     [rsp+98h+var_60], rbx
0x14005b439  mov     [rsp+98h+var_68], r14
0x14005b43e  mov     [rsp+98h+var_70], r15
0x14005b443  mov     [rsp+98h+var_78], 59Bh
0x14005b44b  jmp     loc_14005B3AC
0x14005b450  call    cs:__imp_GetLastError
0x14005b457  nop     dword ptr [rax+rax+00h]
0x14005b45c  mov     edi, eax
0x14005b45e  call    cs:__imp_CurrentIP
0x14005b465  nop     dword ptr [rax+rax+00h]
0x14005b46a  mov     r8d, esi
0x14005b46d  lea     rdx, aWsmunloadFaile_2; "WsmUnload: Failed FilterUnload(); hr = "...
0x14005b474  mov     ecx, 2000000h; unsigned int
0x14005b479  mov     rbx, rax
0x14005b47c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b481  mov     [rsp+98h+var_48], r13d
0x14005b486  lea     r14, aWsmunload; "WsmUnload"
0x14005b48d  mov     [rsp+98h+var_50], r13
0x14005b492  lea     r15, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005b499  mov     [rsp+98h+var_58], edi
0x14005b49d  mov     [rsp+98h+var_60], rbx
0x14005b4a2  mov     [rsp+98h+var_68], r14
0x14005b4a7  mov     [rsp+98h+var_70], r15
0x14005b4ac  mov     [rsp+98h+var_78], 5A9h
0x14005b4b4  jmp     loc_14005B3AC
0x14005b4b9  lea     rdx, [rsp+98h+lpMem]
0x14005b4c1  lea     rcx, aSystem; "SYSTEM"
0x14005b4c8  call    WsmGetConfigKeyName
0x14005b4cd  mov     esi, eax
0x14005b4cf  test    eax, eax
0x14005b4d1  js      loc_14005B742
0x14005b4d7  mov     rdx, [rsp+98h+lpMem]
0x14005b4df  xor     r8d, r8d
0x14005b4e2  call    RegExists
0x14005b4e7  test    eax, eax
0x14005b4e9  jnz     loc_14005B742
0x14005b4ef  call    cs:__imp_GetLastError
0x14005b4f6  nop     dword ptr [rax+rax+00h]
0x14005b4fb  mov     edi, eax
0x14005b4fd  call    cs:__imp_CurrentIP
0x14005b504  nop     dword ptr [rax+rax+00h]
0x14005b509  lea     rdx, aDriverConfigur; "Driver configuration does not exist aft"...
0x14005b510  mov     ecx, 4000000h; unsigned int
0x14005b515  mov     rbx, rax
0x14005b518  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b51d  mov     [rsp+98h+var_48], r13d
0x14005b522  lea     r14, aWsmunload; "WsmUnload"
0x14005b529  mov     [rsp+98h+var_50], r13
0x14005b52e  lea     r15, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x14005b535  mov     [rsp+98h+var_58], edi
0x14005b539  lea     r8, aD; "D"
0x14005b540  mov     [rsp+98h+var_60], rbx
0x14005b545  xor     r9d, r9d
0x14005b548  mov     [rsp+98h+var_68], r14
0x14005b54d  xor     edx, edx
0x14005b54f  mov     [rsp+98h+var_70], r15
0x14005b554  mov     rcx, rax
0x14005b557  mov     [rsp+98h+var_78], 5BDh
0x14005b55f  call    cs:__imp_WdsSetupLogMessageW
0x14005b566  nop     dword ptr [rax+rax+00h]
0x14005b56b  lea     rdx, [rsp+98h+lpSubKey]
0x14005b573  lea     rcx, aSystem; "SYSTEM"
0x14005b57a  call    WsmGetServiceKeyName
0x14005b57f  mov     r13, [rsp+98h+lpSubKey]
0x14005b587  mov     esi, eax
0x14005b589  test    eax, eax
0x14005b58b  js      loc_14005B71A
0x14005b591  mov     rdx, r13; lpSubKey
0x14005b594  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005b59b  call    cs:__imp_RegDeleteTreeW
0x14005b5a2  nop     dword ptr [rax+rax+00h]
0x14005b5a7  mov     esi, eax
0x14005b5a9  mov     ebx, 80070000h
0x14005b5ae  test    eax, eax
0x14005b5b0  jle     short loc_14005B5B7
0x14005b5b2  movzx   esi, ax
0x14005b5b5  or      esi, ebx
0x14005b5b7  test    esi, esi
0x14005b5b9  jns     loc_14005B63F
0x14005b5bf  call    cs:__imp_GetLastError
0x14005b5c6  nop     dword ptr [rax+rax+00h]
0x14005b5cb  mov     edi, eax
0x14005b5cd  call    cs:__imp_CurrentIP
0x14005b5d4  nop     dword ptr [rax+rax+00h]
0x14005b5d9  mov     r9d, esi
0x14005b5dc  lea     rdx, aWsmunloadFaile_1; "WsmUnload: Failed to delete service key"...
0x14005b5e3  mov     r8, r13
0x14005b5e6  mov     ecx, 2000000h; unsigned int
0x14005b5eb  mov     rbx, rax
0x14005b5ee  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b5f3  mov     [rsp+98h+var_48], 0
0x14005b5fb  lea     r8, aD; "D"
0x14005b602  mov     [rsp+98h+var_50], 0
0x14005b60b  xor     r9d, r9d
0x14005b60e  mov     [rsp+98h+var_58], edi
0x14005b612  xor     edx, edx
0x14005b614  mov     [rsp+98h+var_60], rbx
0x14005b619  mov     rcx, rax
0x14005b61c  mov     [rsp+98h+var_68], r14
0x14005b621  mov     [rsp+98h+var_70], r15
0x14005b626  mov     [rsp+98h+var_78], 5CCh
0x14005b62e  call    cs:__imp_WdsSetupLogMessageW
0x14005b635  nop     dword ptr [rax+rax+00h]
0x14005b63a  jmp     loc_14005B71A
0x14005b63f  call    AllocateExpand
0x14005b644  mov     edx, 40h ; '@'
0x14005b649  mov     rcx, rax
0x14005b64c  mov     rbp, rax
0x14005b64f  call    DeleteFileEx2
0x14005b654  test    eax, eax
0x14005b656  jnz     loc_14005B6EE
0x14005b65c  call    cs:__imp_GetLastError
0x14005b663  nop     dword ptr [rax+rax+00h]
0x14005b668  mov     esi, eax
0x14005b66a  test    eax, eax
0x14005b66c  jle     short loc_14005B673
0x14005b66e  movzx   esi, ax
0x14005b671  or      esi, ebx
0x14005b673  call    cs:__imp_GetLastError
0x14005b67a  nop     dword ptr [rax+rax+00h]
0x14005b67f  mov     edi, eax
0x14005b681  call    cs:__imp_CurrentIP
0x14005b688  nop     dword ptr [rax+rax+00h]
0x14005b68d  mov     r9d, esi
0x14005b690  lea     rdx, aWsmunloadFaile_3; "WsmUnload: Failed to delete driver file"...
0x14005b697  mov     r8, rbp
0x14005b69a  mov     ecx, 2000000h; unsigned int
0x14005b69f  mov     rbx, rax
0x14005b6a2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005b6a7  mov     [rsp+98h+var_48], 0
0x14005b6af  lea     r8, aD; "D"
0x14005b6b6  mov     [rsp+98h+var_50], 0
0x14005b6bf  xor     r9d, r9d
0x14005b6c2  mov     [rsp+98h+var_58], edi
0x14005b6c6  xor     edx, edx
0x14005b6c8  mov     [rsp+98h+var_60], rbx
0x14005b6cd  mov     rcx, rax
0x14005b6d0  mov     [rsp+98h+var_68], r14
0x14005b6d5  mov     [rsp+98h+var_70], r15
0x14005b6da  mov     [rsp+98h+var_78], 5DCh
0x14005b6e2  call    cs:__imp_WdsSetupLogMessageW
0x14005b6e9  nop     dword ptr [rax+rax+00h]
0x14005b6ee  test    rbp, rbp
0x14005b6f1  jz      short loc_14005B713
0x14005b6f3  call    cs:__imp_GetProcessHeap
0x14005b6fa  nop     dword ptr [rax+rax+00h]
0x14005b6ff  mov     r8, rbp; lpMem
0x14005b702  xor     edx, edx; dwFlags
0x14005b704  mov     rcx, rax; hHeap
0x14005b707  call    cs:__imp_HeapFree
0x14005b70e  nop     dword ptr [rax+rax+00h]
0x14005b713  mov     ebp, [rsp+98h+arg_0]
0x14005b71a  test    r13, r13
0x14005b71d  jz      short loc_14005B73F
0x14005b71f  call    cs:__imp_GetProcessHeap
0x14005b726  nop     dword ptr [rax+rax+00h]
0x14005b72b  mov     r8, r13; lpMem
0x14005b72e  xor     edx, edx; dwFlags
0x14005b730  mov     rcx, rax; hHeap
0x14005b733  call    cs:__imp_HeapFree
0x14005b73a  nop     dword ptr [rax+rax+00h]
0x14005b73f  xor     r13d, r13d
0x14005b742  cmp     [rsp+98h+lpMem], r13
0x14005b74a  jz      short loc_14005B771
0x14005b74c  call    cs:__imp_GetProcessHeap
0x14005b753  nop     dword ptr [rax+rax+00h]
0x14005b758  mov     r8, [rsp+98h+lpMem]; lpMem
0x14005b760  xor     edx, edx; dwFlags
0x14005b762  mov     rcx, rax; hHeap
0x14005b765  call    cs:__imp_HeapFree
0x14005b76c  nop     dword ptr [rax+rax+00h]
0x14005b771  cmp     ebp, 1
0x14005b774  jnz     short loc_14005B791
0x14005b776  cmp     [rsp+98h+arg_8], r13d
0x14005b77e  jnz     short loc_14005B791
0x14005b780  xor     r8d, r8d
0x14005b783  lea     rcx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x14005b78a  xor     edx, edx
0x14005b78c  call    EnablePrivilegeEx
  ... truncated ...
```
