# CloudSettings::GetCloudSettingsSnapshot(void)

- ea: `0x18004b84c`
- end: `0x18004ba9e`
- name: `?GetCloudSettingsSnapshot@CloudSettings@@QEAAAEBUWinHttpSettings@@XZ`
- size: `594`
- prototype: `const struct WinHttpSettings *__fastcall(CloudSettings *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180049b40`
- `0x180049d1c`
- `0x18004a1bc`
- `0x18004a954`
- `0x18004b464`

## callees

- `0x18004b84c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b896`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ba79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ba79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b8cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b8cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b90e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b964`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b9cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ba3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b90e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b964`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b9cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ba3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b86b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004b86b`

## string_xrefs

- `0x18004b8bd`: `OSDATA\Cloud Settings Cache`
- `0x18004b8e6`: `WinHttp Reliability Configuration Flags`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
const struct WinHttpSettings *__fastcall CloudSettings::GetCloudSettingsSnapshot(CloudSettings *this)
{
  ULONGLONG TickCount64; // rax
  LSTATUS ValueW; // eax
  bool v3; // zf
  LSTATUS v4; // eax
  bool v5; // zf
  int v6; // eax
  LSTATUS v7; // eax
  bool v8; // zf
  int v9; // eax
  bool v10; // cc
  LSTATUS v11; // eax
  bool v12; // zf
  __int64 v13; // rax
  CloudSettings *pvData; // [rsp+50h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+20h] BYREF

  pvData = this;
  if ( byte_180066688 )
  {
    TickCount64 = GetTickCount64();
    if ( TickCount64 - qword_180066668 > 0x927C0 )
    {
      qword_180066668 = TickCount64;
      EnterCriticalSection(&stru_180066640);
      hkey = 0;
      LODWORD(pvData) = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"OSDATA\\Cloud Settings Cache", 0, 1u, &hkey) )
      {
LABEL_35:
        LeaveCriticalSection(&stru_180066640);
        return (const struct WinHttpSettings *)&dword_180066670;
      }
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"WinHttp Reliability Configuration Flags", 0x10u, 0, &pvData, &pcbData);
      v3 = ValueW == 0;
      if ( ValueW > 0 )
        v3 = 0;
      if ( v3 )
        dword_180066670 = (int)pvData;
      pcbData = 4;
      v4 = RegGetValueW(hkey, 0, L"WinHttp Reliability Max Host Count", 0x10u, 0, &pvData, &pcbData);
      v5 = v4 == 0;
      if ( v4 > 0 )
        v5 = 0;
      if ( v5 )
      {
        if ( (unsigned int)pvData <= 2 || (v6 = 1000, (unsigned int)pvData < 0x3E8) )
        {
          v6 = 2;
          if ( (unsigned int)pvData > 2 )
            v6 = (int)pvData;
        }
        dword_180066674 = v6;
      }
      pcbData = 4;
      v7 = RegGetValueW(hkey, 0, L"WinHttp Reliability Max Status Count", 0x10u, 0, &pvData, &pcbData);
      v8 = v7 == 0;
      if ( v7 > 0 )
        v8 = 0;
      if ( !v8 )
      {
LABEL_26:
        pcbData = 4;
        v11 = RegGetValueW(hkey, 0, L"WinHttp Reliability Upload Period in Seconds", 0x10u, 0, &pvData, &pcbData);
        v12 = v11 == 0;
        if ( v11 > 0 )
          v12 = 0;
        if ( v12 )
        {
          v13 = (unsigned int)(1000 * (_DWORD)pvData);
          if ( (unsigned int)v13 <= 0x2710 )
          {
            v13 = 10000;
          }
          else if ( (unsigned int)v13 >= 0x112A880 )
          {
            v13 = 18000000;
          }
          qword_180066680 = v13;
        }
        RegCloseKey(hkey);
        goto LABEL_35;
      }
      v9 = 5;
      v10 = (unsigned int)pvData <= 5;
      if ( (unsigned int)pvData > 5 )
      {
        if ( (unsigned int)pvData >= 0x2710 )
        {
          v9 = 10000;
LABEL_25:
          dword_180066678 = v9;
          goto LABEL_26;
        }
        v10 = (unsigned int)pvData <= 5;
      }
      if ( !v10 )
        v9 = (int)pvData;
      goto LABEL_25;
    }
  }
  return (const struct WinHttpSettings *)&dword_180066670;
}

```

## disassembly

```asm
0x18004b84c  mov     [rsp-8+arg_18], rsi
0x18004b851  mov     [rsp-8+arg_0], rcx
0x18004b856  push    rbp
0x18004b857  mov     rbp, rsp
0x18004b85a  sub     rsp, 40h
0x18004b85e  cmp     cs:byte_180066688, 0
0x18004b865  jz      loc_18004BA8C
0x18004b86b  call    cs:__imp_GetTickCount64
0x18004b871  mov     rcx, rax
0x18004b874  sub     rcx, cs:qword_180066668
0x18004b87b  cmp     rcx, 927C0h
0x18004b882  jbe     loc_18004BA8C
0x18004b888  lea     rcx, stru_180066640; lpCriticalSection
0x18004b88f  mov     cs:qword_180066668, rax
0x18004b896  call    cs:__imp_EnterCriticalSection
0x18004b89c  lea     rax, [rbp+hkey]
0x18004b8a0  mov     [rbp+hkey], 0
0x18004b8a8  mov     r9d, 1; samDesired
0x18004b8ae  mov     [rsp+40h+phkResult], rax; phkResult
0x18004b8b3  xor     r8d, r8d; ulOptions
0x18004b8b6  mov     dword ptr [rbp+arg_0], 0
0x18004b8bd  lea     rdx, aOsdataCloudSet; "OSDATA\\Cloud Settings Cache"
0x18004b8c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b8cb  call    cs:__imp_RegOpenKeyExW
0x18004b8d1  test    eax, eax
0x18004b8d3  jnz     loc_18004BA7F
0x18004b8d9  mov     rcx, [rbp+hkey]; hkey
0x18004b8dd  lea     rax, [rbp+arg_8]
0x18004b8e1  mov     [rsp+40h+pcbData], rax; pcbData
0x18004b8e6  lea     r8, aWinhttpReliabi_1; "WinHttp Reliability Configuration Flags"
0x18004b8ed  lea     rax, [rbp+arg_0]
0x18004b8f1  mov     [rbp+arg_8], 4
0x18004b8f8  mov     [rsp+40h+pvData], rax; pvData
0x18004b8fd  mov     r9d, 10h; dwFlags
0x18004b903  xor     edx, edx; lpSubKey
0x18004b905  mov     [rsp+40h+phkResult], 0; pdwType
0x18004b90e  call    cs:__imp_RegGetValueW
0x18004b914  mov     esi, 80070000h
0x18004b919  test    eax, eax
0x18004b91b  jle     short loc_18004B924
0x18004b91d  movzx   eax, ax
0x18004b920  or      eax, esi
0x18004b922  test    eax, eax
0x18004b924  jnz     short loc_18004B92F
0x18004b926  mov     eax, dword ptr [rbp+arg_0]
0x18004b929  mov     cs:dword_180066670, eax
0x18004b92f  mov     rcx, [rbp+hkey]; hkey
0x18004b933  lea     rax, [rbp+arg_8]
0x18004b937  mov     [rsp+40h+pcbData], rax; pcbData
0x18004b93c  lea     r8, aWinhttpReliabi; "WinHttp Reliability Max Host Count"
0x18004b943  lea     rax, [rbp+arg_0]
0x18004b947  mov     [rbp+arg_8], 4
0x18004b94e  mov     [rsp+40h+pvData], rax; pvData
0x18004b953  mov     r9d, 10h; dwFlags
0x18004b959  xor     edx, edx; lpSubKey
0x18004b95b  mov     [rsp+40h+phkResult], 0; pdwType
0x18004b964  call    cs:__imp_RegGetValueW
0x18004b96a  test    eax, eax
0x18004b96c  jle     short loc_18004B975
0x18004b96e  movzx   eax, ax
0x18004b971  or      eax, esi
0x18004b973  test    eax, eax
0x18004b975  jnz     short loc_18004B998
0x18004b977  mov     ecx, dword ptr [rbp+arg_0]
0x18004b97a  cmp     ecx, 2
0x18004b97d  jbe     short loc_18004B988
0x18004b97f  mov     eax, 3E8h
0x18004b984  cmp     ecx, eax
0x18004b986  jnb     short loc_18004B992
0x18004b988  mov     eax, 2
0x18004b98d  cmp     ecx, eax
0x18004b98f  cmova   eax, ecx
0x18004b992  mov     cs:dword_180066674, eax
0x18004b998  mov     rcx, [rbp+hkey]; hkey
0x18004b99c  lea     rax, [rbp+arg_8]
0x18004b9a0  mov     [rsp+40h+pcbData], rax; pcbData
0x18004b9a5  lea     r8, aWinhttpReliabi_2; "WinHttp Reliability Max Status Count"
0x18004b9ac  lea     rax, [rbp+arg_0]
0x18004b9b0  mov     [rbp+arg_8], 4
0x18004b9b7  mov     [rsp+40h+pvData], rax; pvData
0x18004b9bc  mov     r9d, 10h; dwFlags
0x18004b9c2  xor     edx, edx; lpSubKey
0x18004b9c4  mov     [rsp+40h+phkResult], 0; pdwType
0x18004b9cd  call    cs:__imp_RegGetValueW
0x18004b9d3  test    eax, eax
0x18004b9d5  jle     short loc_18004B9DE
0x18004b9d7  movzx   eax, ax
0x18004b9da  or      eax, esi
0x18004b9dc  test    eax, eax
0x18004b9de  jnz     short loc_18004BA06
0x18004b9e0  mov     ecx, dword ptr [rbp+arg_0]
0x18004b9e3  mov     eax, 5
0x18004b9e8  cmp     ecx, eax
0x18004b9ea  jbe     short loc_18004B9FD
0x18004b9ec  cmp     ecx, 2710h
0x18004b9f2  jb      short loc_18004B9FB
0x18004b9f4  mov     eax, 2710h
0x18004b9f9  jmp     short loc_18004BA00
0x18004b9fb  cmp     ecx, eax
0x18004b9fd  cmova   eax, ecx
0x18004ba00  mov     cs:dword_180066678, eax
0x18004ba06  mov     rcx, [rbp+hkey]; hkey
0x18004ba0a  lea     rax, [rbp+arg_8]
0x18004ba0e  mov     [rsp+40h+pcbData], rax; pcbData
0x18004ba13  lea     r8, aWinhttpReliabi_0; "WinHttp Reliability Upload Period in Se"...
0x18004ba1a  lea     rax, [rbp+arg_0]
0x18004ba1e  mov     [rbp+arg_8], 4
0x18004ba25  mov     [rsp+40h+pvData], rax; pvData
0x18004ba2a  mov     r9d, 10h; dwFlags
0x18004ba30  xor     edx, edx; lpSubKey
0x18004ba32  mov     [rsp+40h+phkResult], 0; pdwType
0x18004ba3b  call    cs:__imp_RegGetValueW
0x18004ba41  test    eax, eax
0x18004ba43  jle     short loc_18004BA4C
0x18004ba45  movzx   eax, ax
0x18004ba48  or      eax, esi
0x18004ba4a  test    eax, eax
0x18004ba4c  jnz     short loc_18004BA75
0x18004ba4e  imul    eax, dword ptr [rbp+arg_0], 3E8h
0x18004ba55  cmp     eax, 2710h
0x18004ba5a  jbe     short loc_18004BA69
0x18004ba5c  mov     ecx, 112A880h
0x18004ba61  cmp     eax, ecx
0x18004ba63  jb      short loc_18004BA6E
0x18004ba65  mov     eax, ecx
0x18004ba67  jmp     short loc_18004BA6E
0x18004ba69  mov     eax, 2710h
0x18004ba6e  mov     cs:qword_180066680, rax
0x18004ba75  mov     rcx, [rbp+hkey]; hKey
0x18004ba79  call    cs:__imp_RegCloseKey
0x18004ba7f  lea     rcx, stru_180066640; lpCriticalSection
0x18004ba86  call    cs:__imp_LeaveCriticalSection
0x18004ba8c  mov     rsi, [rsp+40h+arg_18]
0x18004ba91  lea     rax, dword_180066670
0x18004ba98  add     rsp, 40h
0x18004ba9c  pop     rbp
0x18004ba9d  retn
```
