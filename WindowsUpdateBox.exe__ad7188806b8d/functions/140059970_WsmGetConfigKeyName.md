# WsmGetConfigKeyName

- ea: `0x140059970`
- end: `0x140059b73`
- name: `WsmGetConfigKeyName`
- size: `515`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14005aa68`
- `0x14005b208`

## callees

- `0x140021dd4`
- `0x140055d10`
- `0x140059970`
- `0x140059c90`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140059b23`
- `KERNEL32!HeapFree` at `0x140059b53`
- `KERNEL32!HeapFree` at `0x140059b23`
- `KERNEL32!HeapFree` at `0x140059b53`
- `KERNEL32!GetProcessHeap` at `0x140059b0f`
- `KERNEL32!GetProcessHeap` at `0x140059b3a`
- `KERNEL32!GetProcessHeap` at `0x140059b0f`
- `KERNEL32!GetProcessHeap` at `0x140059b3a`
- `KERNEL32!GetLastError` at `0x1400599a8`
- `KERNEL32!GetLastError` at `0x140059a6d`
- `KERNEL32!GetLastError` at `0x1400599a8`
- `KERNEL32!GetLastError` at `0x140059a6d`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059a25`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059ae7`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059a25`
- `WDSCORE!WdsSetupLogMessageW` at `0x140059ae7`
- `WDSCORE!CurrentIP` at `0x1400599b6`
- `WDSCORE!CurrentIP` at `0x140059a7b`
- `WDSCORE!CurrentIP` at `0x1400599b6`
- `WDSCORE!CurrentIP` at `0x140059a7b`

## string_xrefs

- `0x1400599e4`: `WsmGetConfigKeyName`
- `0x140059aa6`: `WsmGetConfigKeyName`
- `0x1400599c5`: `WsmGetConfigKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x`
- `0x140059a8a`: `WsmGetConfigKeyName: Failed to build config key path; hr = 0x%x`

## pseudocode

```c
__int64 __fastcall WsmGetConfigKeyName(const WCHAR *a1, LPVOID *a2)
{
  int CurrentControlSetKeyName; // esi
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  LPVOID v15; // [rsp+90h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp+20h] BYREF

  v15 = 0;
  lpMem = 0;
  CurrentControlSetKeyName = WsmGetCurrentControlSetKeyName(a1, &v15);
  if ( CurrentControlSetKeyName >= 0 )
  {
    CurrentControlSetKeyName = BuildPathMultiHr(&lpMem, 3, v15, L"Control", L"WinSetupMon");
    if ( CurrentControlSetKeyName >= 0 )
    {
      *a2 = lpMem;
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(
              0x2000000,
              "WsmGetConfigKeyName: Failed to build config key path; hr = 0x%x",
              CurrentControlSetKeyName);
      WdsSetupLogMessageW(
        v10,
        0,
        L"D",
        0,
        491,
        L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
        L"WsmGetConfigKeyName",
        v9,
        LastError,
        0,
        0);
      v11 = lpMem;
    }
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(
           0x2000000,
           "WsmGetConfigKeyName: Failed to get current control set key name under hive key %s; hr = 0x%x",
           (const char *)a1,
           CurrentControlSetKeyName);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      484,
      L"base\\ntsetup\\setupplatform\\deployment\\monitor\\api\\winsetupmonapi.cpp",
      L"WsmGetConfigKeyName",
      v6,
      v5,
      0,
      0);
  }
  if ( v15 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v15);
  }
  return (unsigned int)CurrentControlSetKeyName;
}

```

## disassembly

```asm
0x140059970  mov     rax, rsp
0x140059973  mov     [rax+8], rbx
0x140059977  push    rsi
0x140059978  push    rdi
0x140059979  push    r14
0x14005997b  sub     rsp, 60h
0x14005997f  mov     rbx, rdx
0x140059982  mov     qword ptr [rax+18h], 0
0x14005998a  lea     rdx, [rax+18h]
0x14005998e  mov     qword ptr [rax+20h], 0
0x140059996  mov     r14, rcx
0x140059999  call    WsmGetCurrentControlSetKeyName
0x14005999e  mov     esi, eax
0x1400599a0  test    eax, eax
0x1400599a2  jns     loc_140059A36
0x1400599a8  call    cs:__imp_GetLastError
0x1400599af  nop     dword ptr [rax+rax+00h]
0x1400599b4  mov     edi, eax
0x1400599b6  call    cs:__imp_CurrentIP
0x1400599bd  nop     dword ptr [rax+rax+00h]
0x1400599c2  mov     r9d, esi
0x1400599c5  lea     rdx, aWsmgetconfigke_2; "WsmGetConfigKeyName: Failed to get curr"...
0x1400599cc  mov     r8, r14
0x1400599cf  mov     ecx, 2000000h; unsigned int
0x1400599d4  mov     rbx, rax
0x1400599d7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400599dc  mov     [rsp+78h+var_28], 0
0x1400599e4  lea     rcx, aWsmgetconfigke_1; "WsmGetConfigKeyName"
0x1400599eb  mov     [rsp+78h+var_30], 0
0x1400599f4  lea     r8, aD; "D"
0x1400599fb  mov     [rsp+78h+var_38], edi
0x1400599ff  xor     r9d, r9d
0x140059a02  mov     [rsp+78h+var_40], rbx
0x140059a07  xor     edx, edx
0x140059a09  mov     [rsp+78h+var_48], rcx
0x140059a0e  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x140059a15  mov     [rsp+78h+var_50], rcx
0x140059a1a  mov     rcx, rax
0x140059a1d  mov     dword ptr [rsp+78h+var_58], 1E4h
0x140059a25  call    cs:__imp_WdsSetupLogMessageW
0x140059a2c  nop     dword ptr [rax+rax+00h]
0x140059a31  jmp     loc_140059B2F
0x140059a36  mov     r8, [rsp+78h+arg_10]
0x140059a3e  lea     rax, aWinsetupmon_0; "WinSetupMon"
0x140059a45  lea     r9, aControl; "Control"
0x140059a4c  mov     [rsp+78h+var_58], rax
0x140059a51  mov     edx, 3
0x140059a56  lea     rcx, [rsp+78h+lpMem]
0x140059a5e  call    BuildPathMultiHr
0x140059a63  mov     esi, eax
0x140059a65  test    eax, eax
0x140059a67  jns     loc_140059AFD
0x140059a6d  call    cs:__imp_GetLastError
0x140059a74  nop     dword ptr [rax+rax+00h]
0x140059a79  mov     edi, eax
0x140059a7b  call    cs:__imp_CurrentIP
0x140059a82  nop     dword ptr [rax+rax+00h]
0x140059a87  mov     r8d, esi
0x140059a8a  lea     rdx, aWsmgetconfigke_0; "WsmGetConfigKeyName: Failed to build co"...
0x140059a91  mov     ecx, 2000000h; unsigned int
0x140059a96  mov     rbx, rax
0x140059a99  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140059a9e  mov     [rsp+78h+var_28], 0
0x140059aa6  lea     rcx, aWsmgetconfigke_1; "WsmGetConfigKeyName"
0x140059aad  mov     [rsp+78h+var_30], 0
0x140059ab6  lea     r8, aD; "D"
0x140059abd  mov     [rsp+78h+var_38], edi
0x140059ac1  xor     r9d, r9d
0x140059ac4  mov     [rsp+78h+var_40], rbx
0x140059ac9  xor     edx, edx
0x140059acb  mov     [rsp+78h+var_48], rcx
0x140059ad0  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\deploymen"...
0x140059ad7  mov     [rsp+78h+var_50], rcx
0x140059adc  mov     rcx, rax
0x140059adf  mov     dword ptr [rsp+78h+var_58], 1EBh
0x140059ae7  call    cs:__imp_WdsSetupLogMessageW
0x140059aee  nop     dword ptr [rax+rax+00h]
0x140059af3  mov     rbx, [rsp+78h+lpMem]
0x140059afb  jmp     short loc_140059B0A
0x140059afd  mov     rax, [rsp+78h+lpMem]
0x140059b05  mov     [rbx], rax
0x140059b08  xor     ebx, ebx
0x140059b0a  test    rbx, rbx
0x140059b0d  jz      short loc_140059B2F
0x140059b0f  call    cs:__imp_GetProcessHeap
0x140059b16  nop     dword ptr [rax+rax+00h]
0x140059b1b  mov     r8, rbx; lpMem
0x140059b1e  xor     edx, edx; dwFlags
0x140059b20  mov     rcx, rax; hHeap
0x140059b23  call    cs:__imp_HeapFree
0x140059b2a  nop     dword ptr [rax+rax+00h]
0x140059b2f  cmp     [rsp+78h+arg_10], 0
0x140059b38  jz      short loc_140059B5F
0x140059b3a  call    cs:__imp_GetProcessHeap
0x140059b41  nop     dword ptr [rax+rax+00h]
0x140059b46  mov     r8, [rsp+78h+arg_10]; lpMem
0x140059b4e  xor     edx, edx; dwFlags
0x140059b50  mov     rcx, rax; hHeap
0x140059b53  call    cs:__imp_HeapFree
0x140059b5a  nop     dword ptr [rax+rax+00h]
0x140059b5f  mov     rbx, [rsp+78h+arg_0]
0x140059b67  mov     eax, esi
0x140059b69  add     rsp, 60h
0x140059b6d  pop     r14
0x140059b6f  pop     rdi
0x140059b70  pop     rsi
0x140059b71  retn
```
