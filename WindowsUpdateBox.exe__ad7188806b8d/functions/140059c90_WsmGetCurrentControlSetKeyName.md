# WsmGetCurrentControlSetKeyName

- ea: `0x140059c90`
- end: `0x140059ff4`
- name: `WsmGetCurrentControlSetKeyName`
- size: `868`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140059970`
- `0x140059ffc`

## callees

- `0x140027438`
- `0x140028c68`
- `0x140055d10`
- `0x140059c90`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140059ccf`
- `ADVAPI32!RegOpenKeyExW` at `0x140059ccf`
- `ADVAPI32!RegCloseKey` at `0x140059eff`
- `ADVAPI32!RegCloseKey` at `0x140059fd5`
- `ADVAPI32!RegCloseKey` at `0x140059eff`
- `ADVAPI32!RegCloseKey` at `0x140059fd5`
- `KERNEL32!HeapFree` at `0x140059fbc`
- `KERNEL32!HeapFree` at `0x140059fbc`
- `KERNEL32!GetProcessHeap` at `0x140059fa8`
- `KERNEL32!GetProcessHeap` at `0x140059fa8`
- `KERNEL32!GetLastError` at `0x140059cf3`
- `KERNEL32!GetLastError` at `0x140059d96`
- `KERNEL32!GetLastError` at `0x140059daf`
- `KERNEL32!GetLastError` at `0x140059dcd`
- `KERNEL32!GetLastError` at `0x140059e64`
- `KERNEL32!GetLastError` at `0x140059f1a`
- `KERNEL32!GetLastError` at `0x140059cf3`
- `KERNEL32!GetLastError` at `0x140059d96`
- `KERNEL32!GetLastError` at `0x140059daf`
- `KERNEL32!GetLastError` at `0x140059dcd`
- `KERNEL32!GetLastError` at `0x140059e64`
- `KERNEL32!GetLastError` at `0x140059f1a`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059d70`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059ede`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059d70`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059ede`
- `WDSCORE!CurrentIP` at `0x140059d01`
- `WDSCORE!CurrentIP` at `0x140059ddb`
- `WDSCORE!CurrentIP` at `0x140059e72`
- `WDSCORE!CurrentIP` at `0x140059f28`
- `WDSCORE!CurrentIP` at `0x140059d01`
- `WDSCORE!CurrentIP` at `0x140059ddb`
- `WDSCORE!CurrentIP` at `0x140059e72`
- `WDSCORE!CurrentIP` at `0x140059f28`

## string_xrefs

- `0x140059d10`: `WsmGetCurrentControlSetKeyName: Failed to open system hive key %s; hr = 0x%x`
- `0x140059e81`: `WsmGetCurrentControlSetKeyName: Failed to allocate current control set key path; hr = 0x%x`

## pseudocode

```c
__int64 __fastcall WsmGetCurrentControlSetKeyName(LPCWSTR lpSubKey, LPVOID *a2)
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
           "WsmGetCurrentControlSetKeyName: Failed to open system hive key %s; hr = 0x%x",
           (const char *)lpSubKey,
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      396,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmGetCurrentControlSetKeyName",
      v7,
      LastError,
      0,
      0);
    goto LABEL_24;
  }
  Dword = RegGetDword(hKey);
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
            "WsmGetCurrentControlSetKeyName: Failed to get current control set value under hive key %s; hr = 0x%x",
            (const char *)lpSubKey,
            v5);
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      404,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmGetCurrentControlSetKeyName",
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
            "WsmGetCurrentControlSetKeyName: Failed to allocate current control set key path; hr = 0x%x",
            v5);
    WdsSetupLogMessageW(
      v18,
      0,
      L"D",
      0,
      411,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmGetCurrentControlSetKeyName",
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
    v23 = ConstructPartialMsgW(0x2000000, "WsmGetCurrentControlSetKeyName: Failed to close system key; hr = 0x%x", v5);
    WdsSetupLogMessageW(
      v23,
      0,
      L"D",
      0,
      418,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmGetCurrentControlSetKeyName",
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
0x140059c90  mov     r11, rsp
0x140059c93  mov     [r11+8], rbx
0x140059c97  push    rbp
0x140059c98  push    rsi
0x140059c99  push    rdi
0x140059c9a  sub     rsp, 60h
0x140059c9e  mov     rbx, rdx
0x140059ca1  mov     qword ptr [r11+18h], 0
0x140059ca9  mov     rdx, rcx; lpSubKey
0x140059cac  mov     qword ptr [r11+20h], 0
0x140059cb4  mov     rbp, rcx
0x140059cb7  lea     rax, [r11+18h]
0x140059cbb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140059cc2  mov     [r11-58h], rax
0x140059cc6  mov     r9d, 20019h; samDesired
0x140059ccc  xor     r8d, r8d; ulOptions
0x140059ccf  call    cs:__imp_RegOpenKeyExW
0x140059cd6  nop     dword ptr [rax+rax+00h]
0x140059cdb  mov     esi, eax
0x140059cdd  mov     edi, 80070000h
0x140059ce2  test    eax, eax
0x140059ce4  jle     short loc_140059CEB
0x140059ce6  movzx   esi, ax
0x140059ce9  or      esi, edi
0x140059ceb  test    esi, esi
0x140059ced  jns     loc_140059D81
0x140059cf3  call    cs:__imp_GetLastError
0x140059cfa  nop     dword ptr [rax+rax+00h]
0x140059cff  mov     edi, eax
0x140059d01  call    cs:__imp_CurrentIP
0x140059d08  nop     dword ptr [rax+rax+00h]
0x140059d0d  mov     r9d, esi
0x140059d10  lea     rdx, aWsmgetcurrentc_2; "WsmGetCurrentControlSetKeyName: Failed "...
0x140059d17  mov     r8, rbp
0x140059d1a  mov     ecx, 2000000h; unsigned int
0x140059d1f  mov     rbx, rax
0x140059d22  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140059d27  mov     [rsp+78h+var_28], 0
0x140059d2f  lea     rcx, aWsmgetcurrentc_1; "WsmGetCurrentControlSetKeyName"
0x140059d36  mov     [rsp+78h+var_30], 0
0x140059d3f  mov     [rsp+78h+var_38], edi
0x140059d43  mov     [rsp+78h+var_40], rbx
0x140059d48  mov     [rsp+78h+var_48], rcx
0x140059d4d  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x140059d54  mov     [rsp+78h+var_50], rcx
0x140059d59  mov     [rsp+78h+var_58], 18Ch
0x140059d61  xor     r9d, r9d
0x140059d64  lea     r8, aD; "D"
0x140059d6b  xor     edx, edx
0x140059d6d  mov     rcx, rax
0x140059d70  call    cs:__imp_WdsSetupLogMessageW
0x140059d77  nop     dword ptr [rax+rax+00h]
0x140059d7c  jmp     loc_140059FC8
0x140059d81  mov     rcx, [rsp+78h+hKey]
0x140059d89  call    RegGetDword
0x140059d8e  test    eax, eax
0x140059d90  jnz     loc_140059E40
0x140059d96  call    cs:__imp_GetLastError
0x140059d9d  nop     dword ptr [rax+rax+00h]
0x140059da2  test    eax, eax
0x140059da4  jle     short loc_140059DAD
0x140059da6  movzx   eax, ax
0x140059da9  or      eax, edi
0x140059dab  test    eax, eax
0x140059dad  jns     short loc_140059DC8
0x140059daf  call    cs:__imp_GetLastError
0x140059db6  nop     dword ptr [rax+rax+00h]
0x140059dbb  mov     esi, eax
0x140059dbd  test    eax, eax
0x140059dbf  jle     short loc_140059DCD
0x140059dc1  movzx   esi, ax
0x140059dc4  or      esi, edi
0x140059dc6  jmp     short loc_140059DCD
0x140059dc8  mov     esi, 80004005h
0x140059dcd  call    cs:__imp_GetLastError
0x140059dd4  nop     dword ptr [rax+rax+00h]
0x140059dd9  mov     edi, eax
0x140059ddb  call    cs:__imp_CurrentIP
0x140059de2  nop     dword ptr [rax+rax+00h]
0x140059de7  mov     r9d, esi
0x140059dea  lea     rdx, aWsmgetcurrentc_0; "WsmGetCurrentControlSetKeyName: Failed "...
0x140059df1  mov     r8, rbp
0x140059df4  mov     ecx, 2000000h; unsigned int
0x140059df9  mov     rbx, rax
0x140059dfc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140059e01  mov     [rsp+78h+var_28], 0
0x140059e09  lea     rcx, aWsmgetcurrentc_1; "WsmGetCurrentControlSetKeyName"
0x140059e10  mov     [rsp+78h+var_30], 0
0x140059e19  mov     [rsp+78h+var_38], edi
0x140059e1d  mov     [rsp+78h+var_40], rbx
0x140059e22  mov     [rsp+78h+var_48], rcx
0x140059e27  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x140059e2e  mov     [rsp+78h+var_50], rcx
0x140059e33  mov     [rsp+78h+var_58], 194h
0x140059e3b  jmp     loc_140059D61
0x140059e40  mov     r9d, eax
0x140059e43  lea     rdx, aSControlset03u; "%s\\ControlSet%03u"
0x140059e4a  mov     r8, rbp
0x140059e4d  lea     rcx, [rsp+78h+lpMem]
0x140059e55  call    StrAllocatingPrintf
0x140059e5a  mov     esi, eax
0x140059e5c  test    eax, eax
0x140059e5e  jns     loc_140059EF7
0x140059e64  call    cs:__imp_GetLastError
0x140059e6b  nop     dword ptr [rax+rax+00h]
0x140059e70  mov     edi, eax
0x140059e72  call    cs:__imp_CurrentIP
0x140059e79  nop     dword ptr [rax+rax+00h]
0x140059e7e  mov     r8d, esi
0x140059e81  lea     rdx, aWsmgetcurrentc; "WsmGetCurrentControlSetKeyName: Failed "...
0x140059e88  mov     ecx, 2000000h; unsigned int
0x140059e8d  mov     rbx, rax
0x140059e90  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140059e95  mov     [rsp+78h+var_28], 0
0x140059e9d  lea     rcx, aWsmgetcurrentc_1; "WsmGetCurrentControlSetKeyName"
0x140059ea4  mov     [rsp+78h+var_30], 0
0x140059ead  mov     [rsp+78h+var_38], edi
0x140059eb1  mov     [rsp+78h+var_40], rbx
0x140059eb6  mov     [rsp+78h+var_48], rcx
0x140059ebb  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x140059ec2  mov     [rsp+78h+var_50], rcx
0x140059ec7  mov     [rsp+78h+var_58], 19Bh
0x140059ecf  xor     r9d, r9d
0x140059ed2  lea     r8, aD; "D"
0x140059ed9  xor     edx, edx
0x140059edb  mov     rcx, rax
0x140059ede  call    cs:__imp_WdsSetupLogMessageW
0x140059ee5  nop     dword ptr [rax+rax+00h]
0x140059eea  mov     rbx, [rsp+78h+lpMem]
0x140059ef2  jmp     loc_140059FA3
0x140059ef7  mov     rcx, [rsp+78h+hKey]; hKey
0x140059eff  call    cs:__imp_RegCloseKey
0x140059f06  nop     dword ptr [rax+rax+00h]
0x140059f0b  mov     esi, eax
0x140059f0d  test    eax, eax
0x140059f0f  jle     short loc_140059F16
0x140059f11  movzx   esi, ax
0x140059f14  or      esi, edi
0x140059f16  test    esi, esi
0x140059f18  jns     short loc_140059F8A
0x140059f1a  call    cs:__imp_GetLastError
0x140059f21  nop     dword ptr [rax+rax+00h]
0x140059f26  mov     edi, eax
0x140059f28  call    cs:__imp_CurrentIP
0x140059f2f  nop     dword ptr [rax+rax+00h]
0x140059f34  mov     r8d, esi
0x140059f37  lea     rdx, aWsmgetcurrentc_3; "WsmGetCurrentControlSetKeyName: Failed "...
0x140059f3e  mov     ecx, 2000000h; unsigned int
0x140059f43  mov     rbx, rax
0x140059f46  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140059f4b  mov     [rsp+78h+var_28], 0
0x140059f53  lea     rcx, aWsmgetcurrentc_1; "WsmGetCurrentControlSetKeyName"
0x140059f5a  mov     [rsp+78h+var_30], 0
0x140059f63  mov     [rsp+78h+var_38], edi
0x140059f67  mov     [rsp+78h+var_40], rbx
0x140059f6c  mov     [rsp+78h+var_48], rcx
0x140059f71  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x140059f78  mov     [rsp+78h+var_50], rcx
0x140059f7d  mov     [rsp+78h+var_58], 1A2h
0x140059f85  jmp     loc_140059ECF
0x140059f8a  mov     rax, [rsp+78h+lpMem]
0x140059f92  mov     [rbx], rax
0x140059f95  xor     ebx, ebx
0x140059f97  mov     [rsp+78h+hKey], 0
0x140059fa3  test    rbx, rbx
0x140059fa6  jz      short loc_140059FC8
0x140059fa8  call    cs:__imp_GetProcessHeap
0x140059faf  nop     dword ptr [rax+rax+00h]
0x140059fb4  mov     r8, rbx; lpMem
0x140059fb7  xor     edx, edx; dwFlags
0x140059fb9  mov     rcx, rax; hHeap
0x140059fbc  call    cs:__imp_HeapFree
0x140059fc3  nop     dword ptr [rax+rax+00h]
0x140059fc8  mov     rcx, [rsp+78h+hKey]; hKey
0x140059fd0  test    rcx, rcx
0x140059fd3  jz      short loc_140059FE1
0x140059fd5  call    cs:__imp_RegCloseKey
0x140059fdc  nop     dword ptr [rax+rax+00h]
0x140059fe1  mov     rbx, [rsp+78h+arg_0]
0x140059fe9  mov     eax, esi
0x140059feb  add     rsp, 60h
0x140059fef  pop     rdi
0x140059ff0  pop     rsi
0x140059ff1  pop     rbp
0x140059ff2  retn
```
