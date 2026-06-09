# WsbkGetCurrentControlSetKeyName

- ea: `0x180049e58`
- end: `0x18004a15f`
- name: `WsbkGetCurrentControlSetKeyName`
- size: `775`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18004a9d4`

## callees

- `0x180009e04`
- `0x18003ac10`
- `0x18003b990`
- `0x180049e58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049e97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a147`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a126`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a126`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a134`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0a4`
- `WDSCORE!CurrentIP` at `0x180049eb9`
- `WDSCORE!CurrentIP` at `0x180049f83`
- `WDSCORE!CurrentIP` at `0x18004a00e`
- `WDSCORE!CurrentIP` at `0x18004a0ac`
- `WDSCORE!CurrentIP` at `0x180049eb9`
- `WDSCORE!CurrentIP` at `0x180049f83`
- `WDSCORE!CurrentIP` at `0x18004a00e`
- `WDSCORE!CurrentIP` at `0x18004a0ac`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049f22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a074`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049f22`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004a074`

## string_xrefs

- `0x180049ec2`: `WsbkGetCurrentControlSetKeyName: Failed to open system hive key %s; hr = 0x%x`
- `0x18004a017`: `WsbkGetCurrentControlSetKeyName: Failed to allocate current control set key path; hr = 0x%x`

## pseudocode

```c
__int64 __fastcall WsbkGetCurrentControlSetKeyName(LPCWSTR lpSubKey, LPVOID *a2)
{
  LSTATUS v4; // eax
  signed int v5; // esi
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  unsigned int Dword; // eax
  signed int v10; // eax
  bool v11; // sf
  signed int v12; // eax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  void *v19; // rbx
  LSTATUS v20; // eax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp+20h] BYREF

  hKey = 0;
  lpMem = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x2000000,
           "WsbkGetCurrentControlSetKeyName: Failed to open system hive key %s; hr = 0x%x",
           (const char *)lpSubKey,
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      2962,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetCurrentControlSetKeyName",
      v7,
      LastError,
      0,
      0);
    goto LABEL_24;
  }
  Dword = RegGetDword(hKey, L"Select", L"Current");
  if ( !Dword )
  {
    v10 = GetLastError();
    v11 = v10 < 0;
    if ( v10 > 0 )
      v11 = 1;
    if ( v11 )
    {
      v12 = GetLastError();
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v13 = GetLastError();
    v14 = CurrentIP();
    v15 = ConstructPartialMsgW(
            0x2000000,
            "WsbkGetCurrentControlSetKeyName: Failed to get current control set value under hive key %s; hr = 0x%x",
            (const char *)lpSubKey,
            v5);
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      2970,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetCurrentControlSetKeyName",
      v14,
      v13,
      0,
      0);
    goto LABEL_24;
  }
  v5 = StrAllocatingPrintf(&lpMem, L"%s\\ControlSet%03u", lpSubKey, Dword);
  if ( v5 < 0 )
  {
    v16 = GetLastError();
    v17 = CurrentIP();
    v18 = ConstructPartialMsgW(
            0x2000000,
            "WsbkGetCurrentControlSetKeyName: Failed to allocate current control set key path; hr = 0x%x",
            v5);
    WdsSetupLogMessageW(
      v18,
      0,
      L"D",
      0,
      2977,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetCurrentControlSetKeyName",
      v17,
      v16,
      0,
      0);
LABEL_16:
    v19 = lpMem;
    goto LABEL_22;
  }
  v20 = RegCloseKey(hKey);
  v5 = v20;
  if ( v20 > 0 )
    v5 = (unsigned __int16)v20 | 0x80070000;
  if ( v5 < 0 )
  {
    v21 = GetLastError();
    v22 = CurrentIP();
    v23 = ConstructPartialMsgW(0x2000000, "WsbkGetCurrentControlSetKeyName: Failed to close system key; hr = 0x%x", v5);
    WdsSetupLogMessageW(
      v23,
      0,
      L"D",
      0,
      2984,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkGetCurrentControlSetKeyName",
      v22,
      v21,
      0,
      0);
    goto LABEL_16;
  }
  *a2 = lpMem;
  v19 = 0;
  hKey = 0;
LABEL_22:
  if ( v19 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180049e58  mov     r11, rsp
0x180049e5b  mov     [r11+8], rbx
0x180049e5f  push    rbp
0x180049e60  push    rsi
0x180049e61  push    rdi
0x180049e62  sub     rsp, 60h
0x180049e66  mov     rbx, rdx
0x180049e69  mov     qword ptr [r11+18h], 0
0x180049e71  mov     rdx, rcx; lpSubKey
0x180049e74  mov     qword ptr [r11+20h], 0
0x180049e7c  mov     rbp, rcx
0x180049e7f  lea     rax, [r11+18h]
0x180049e83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049e8a  mov     [r11-58h], rax
0x180049e8e  mov     r9d, 20019h; samDesired
0x180049e94  xor     r8d, r8d; ulOptions
0x180049e97  call    cs:__imp_RegOpenKeyExW
0x180049e9d  mov     esi, eax
0x180049e9f  mov     edi, 80070000h
0x180049ea4  test    eax, eax
0x180049ea6  jle     short loc_180049EAD
0x180049ea8  movzx   esi, ax
0x180049eab  or      esi, edi
0x180049ead  test    esi, esi
0x180049eaf  jns     short loc_180049F2D
0x180049eb1  call    cs:__imp_GetLastError
0x180049eb7  mov     edi, eax
0x180049eb9  call    cs:__imp_CurrentIP
0x180049ebf  mov     r9d, esi
0x180049ec2  lea     rdx, aWsbkgetcurrent_0; "WsbkGetCurrentControlSetKeyName: Failed"...
0x180049ec9  mov     r8, rbp
0x180049ecc  mov     ecx, 2000000h; unsigned int
0x180049ed1  mov     rbx, rax
0x180049ed4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180049ed9  mov     [rsp+78h+var_28], 0
0x180049ee1  lea     rcx, aWsbkgetcurrent_2; "WsbkGetCurrentControlSetKeyName"
0x180049ee8  mov     [rsp+78h+var_30], 0
0x180049ef1  mov     [rsp+78h+var_38], edi
0x180049ef5  mov     [rsp+78h+var_40], rbx
0x180049efa  mov     [rsp+78h+var_48], rcx
0x180049eff  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x180049f06  mov     [rsp+78h+var_50], rcx
0x180049f0b  mov     [rsp+78h+var_58], 0B92h
0x180049f13  xor     r9d, r9d
0x180049f16  lea     r8, aD; "D"
0x180049f1d  xor     edx, edx
0x180049f1f  mov     rcx, rax
0x180049f22  call    cs:__imp_WdsSetupLogMessageW
0x180049f28  jmp     loc_18004A13A
0x180049f2d  mov     rcx, [rsp+78h+hKey]
0x180049f35  lea     r8, aCurrent; "Current"
0x180049f3c  lea     rdx, aSelect; "Select"
0x180049f43  call    RegGetDword
0x180049f48  test    eax, eax
0x180049f4a  jnz     loc_180049FE2
0x180049f50  call    cs:__imp_GetLastError
0x180049f56  test    eax, eax
0x180049f58  jle     short loc_180049F61
0x180049f5a  movzx   eax, ax
0x180049f5d  or      eax, edi
0x180049f5f  test    eax, eax
0x180049f61  jns     short loc_180049F76
0x180049f63  call    cs:__imp_GetLastError
0x180049f69  mov     esi, eax
0x180049f6b  test    eax, eax
0x180049f6d  jle     short loc_180049F7B
0x180049f6f  movzx   esi, ax
0x180049f72  or      esi, edi
0x180049f74  jmp     short loc_180049F7B
0x180049f76  mov     esi, 80004005h
0x180049f7b  call    cs:__imp_GetLastError
0x180049f81  mov     edi, eax
0x180049f83  call    cs:__imp_CurrentIP
0x180049f89  mov     r9d, esi
0x180049f8c  lea     rdx, aWsbkgetcurrent; "WsbkGetCurrentControlSetKeyName: Failed"...
0x180049f93  mov     r8, rbp
0x180049f96  mov     ecx, 2000000h; unsigned int
0x180049f9b  mov     rbx, rax
0x180049f9e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180049fa3  mov     [rsp+78h+var_28], 0
0x180049fab  lea     rcx, aWsbkgetcurrent_2; "WsbkGetCurrentControlSetKeyName"
0x180049fb2  mov     [rsp+78h+var_30], 0
0x180049fbb  mov     [rsp+78h+var_38], edi
0x180049fbf  mov     [rsp+78h+var_40], rbx
0x180049fc4  mov     [rsp+78h+var_48], rcx
0x180049fc9  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x180049fd0  mov     [rsp+78h+var_50], rcx
0x180049fd5  mov     [rsp+78h+var_58], 0B9Ah
0x180049fdd  jmp     loc_180049F13
0x180049fe2  mov     r9d, eax
0x180049fe5  lea     rdx, aSControlset03u; "%s\\ControlSet%03u"
0x180049fec  mov     r8, rbp
0x180049fef  lea     rcx, [rsp+78h+lpMem]
0x180049ff7  call    StrAllocatingPrintf
0x180049ffc  mov     esi, eax
0x180049ffe  test    eax, eax
0x18004a000  jns     loc_18004A087
0x18004a006  call    cs:__imp_GetLastError
0x18004a00c  mov     edi, eax
0x18004a00e  call    cs:__imp_CurrentIP
0x18004a014  mov     r8d, esi
0x18004a017  lea     rdx, aWsbkgetcurrent_1; "WsbkGetCurrentControlSetKeyName: Failed"...
0x18004a01e  mov     ecx, 2000000h; unsigned int
0x18004a023  mov     rbx, rax
0x18004a026  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a02b  mov     [rsp+78h+var_28], 0
0x18004a033  lea     rcx, aWsbkgetcurrent_2; "WsbkGetCurrentControlSetKeyName"
0x18004a03a  mov     [rsp+78h+var_30], 0
0x18004a043  mov     [rsp+78h+var_38], edi
0x18004a047  mov     [rsp+78h+var_40], rbx
0x18004a04c  mov     [rsp+78h+var_48], rcx
0x18004a051  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a058  mov     [rsp+78h+var_50], rcx
0x18004a05d  mov     [rsp+78h+var_58], 0BA1h
0x18004a065  xor     r9d, r9d
0x18004a068  lea     r8, aD; "D"
0x18004a06f  xor     edx, edx
0x18004a071  mov     rcx, rax
0x18004a074  call    cs:__imp_WdsSetupLogMessageW
0x18004a07a  mov     rbx, [rsp+78h+lpMem]
0x18004a082  jmp     loc_18004A121
0x18004a087  mov     rcx, [rsp+78h+hKey]; hKey
0x18004a08f  call    cs:__imp_RegCloseKey
0x18004a095  mov     esi, eax
0x18004a097  test    eax, eax
0x18004a099  jle     short loc_18004A0A0
0x18004a09b  movzx   esi, ax
0x18004a09e  or      esi, edi
0x18004a0a0  test    esi, esi
0x18004a0a2  jns     short loc_18004A108
0x18004a0a4  call    cs:__imp_GetLastError
0x18004a0aa  mov     edi, eax
0x18004a0ac  call    cs:__imp_CurrentIP
0x18004a0b2  mov     r8d, esi
0x18004a0b5  lea     rdx, aWsbkgetcurrent_3; "WsbkGetCurrentControlSetKeyName: Failed"...
0x18004a0bc  mov     ecx, 2000000h; unsigned int
0x18004a0c1  mov     rbx, rax
0x18004a0c4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004a0c9  mov     [rsp+78h+var_28], 0
0x18004a0d1  lea     rcx, aWsbkgetcurrent_2; "WsbkGetCurrentControlSetKeyName"
0x18004a0d8  mov     [rsp+78h+var_30], 0
0x18004a0e1  mov     [rsp+78h+var_38], edi
0x18004a0e5  mov     [rsp+78h+var_40], rbx
0x18004a0ea  mov     [rsp+78h+var_48], rcx
0x18004a0ef  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004a0f6  mov     [rsp+78h+var_50], rcx
0x18004a0fb  mov     [rsp+78h+var_58], 0BA8h
0x18004a103  jmp     loc_18004A065
0x18004a108  mov     rax, [rsp+78h+lpMem]
0x18004a110  mov     [rbx], rax
0x18004a113  xor     ebx, ebx
0x18004a115  mov     [rsp+78h+hKey], 0
0x18004a121  test    rbx, rbx
0x18004a124  jz      short loc_18004A13A
0x18004a126  call    cs:__imp_GetProcessHeap
0x18004a12c  mov     r8, rbx; lpMem
0x18004a12f  xor     edx, edx; dwFlags
0x18004a131  mov     rcx, rax; hHeap
0x18004a134  call    cs:__imp_HeapFree
0x18004a13a  mov     rcx, [rsp+78h+hKey]; hKey
0x18004a142  test    rcx, rcx
0x18004a145  jz      short loc_18004A14D
0x18004a147  call    cs:__imp_RegCloseKey
0x18004a14d  mov     rbx, [rsp+78h+arg_0]
0x18004a155  mov     eax, esi
0x18004a157  add     rsp, 60h
0x18004a15b  pop     rdi
0x18004a15c  pop     rsi
0x18004a15d  pop     rbp
0x18004a15e  retn
```
