# DpspEnumerateScenarioResourceInformation(HKEY__ *,__SCENARIOINFO *)

- ea: `0x18000d880`
- end: `0x18000dc29`
- name: `?DpspEnumerateScenarioResourceInformation@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@@Z`
- size: `937`
- prototype: `__int64 __fastcall(HKEY, struct __SCENARIOINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e9d4`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000a856`
- `0x18000d880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d8f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d8f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d92b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d9eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dabf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d92b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d9eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dabf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db96`

## pseudocode

```c
__int64 __fastcall DpspEnumerateScenarioResourceInformation(HKEY a1, struct __SCENARIOINFO *a2)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  int v6; // r8d
  __int64 v7; // rcx
  void *v8; // rax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  __int64 v11; // rcx
  void *v12; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rcx
  void *v16; // rax
  LSTATUS v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-10h]
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  hKey = 0;
  cbData = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (__int64)L"DpspEnumerateScenarioResourceInformation",
      540,
      (const wchar_t *)L"Error = %d",
      87);
    goto LABEL_46;
  }
  v4 = RegOpenKeyExW(a1, L"DisplayResources", 0, 0x20019u, &hKey);
  v3 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
LABEL_44:
    hKey = 0;
    if ( v3 >= 0 )
      goto LABEL_46;
    goto LABEL_45;
  }
  if ( !hKey )
    goto LABEL_44;
  v5 = RegQueryValueExW(hKey, L"IconResource", 0, 0, 0, &cbData);
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 < 0 )
  {
    v6 = 564;
    LODWORD(phkResult) = (unsigned __int16)v3;
LABEL_14:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
      (__int64)L"DpspEnumerateScenarioResourceInformation",
      v6,
      (const wchar_t *)L"Error = %d",
      phkResult);
    goto LABEL_45;
  }
  cbData += 2;
  if ( cbData > 1 )
  {
    v7 = (cbData + 7) & 0xFFFFFFF8;
    cbData = v7;
    *((_DWORD *)a2 + 20) = v7;
    v8 = (void *)WdipAlloc(v7);
    *((_QWORD *)a2 + 7) = v8;
    if ( v8 )
    {
      memset_0(v8, 0, cbData);
      v9 = RegQueryValueExW(hKey, L"IconResource", 0, 0, *((LPBYTE *)a2 + 7), &cbData);
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 < 0 )
      {
        v6 = 587;
        LODWORD(phkResult) = (unsigned __int16)v3;
        goto LABEL_14;
      }
      v10 = RegQueryValueExW(hKey, L"SourceNameResource", 0, 0, 0, &cbData);
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
      if ( v3 < 0 )
      {
        v6 = 599;
        LODWORD(phkResult) = (unsigned __int16)v3;
        goto LABEL_14;
      }
      cbData += 2;
      if ( cbData <= 1 )
        goto LABEL_10;
      v11 = (cbData + 7) & 0xFFFFFFF8;
      cbData = v11;
      *((_DWORD *)a2 + 21) = v11;
      v12 = (void *)WdipAlloc(v11);
      *((_QWORD *)a2 + 8) = v12;
      if ( v12 )
      {
        memset_0(v12, 0, cbData);
        v13 = RegQueryValueExW(hKey, L"SourceNameResource", 0, 0, *((LPBYTE *)a2 + 8), &cbData);
        v3 = v13;
        if ( v13 > 0 )
          v3 = (unsigned __int16)v13 | 0x80070000;
        if ( v3 < 0 )
        {
          v6 = 622;
          LODWORD(phkResult) = (unsigned __int16)v3;
          goto LABEL_14;
        }
        v14 = RegQueryValueExW(hKey, L"TypeNameResource", 0, 0, 0, &cbData);
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
        if ( v3 < 0 )
        {
          v6 = 635;
          LODWORD(phkResult) = (unsigned __int16)v3;
          goto LABEL_14;
        }
        cbData += 2;
        if ( cbData <= 1 )
          goto LABEL_10;
        v15 = (cbData + 7) & 0xFFFFFFF8;
        cbData = v15;
        *((_DWORD *)a2 + 22) = v15;
        v16 = (void *)WdipAlloc(v15);
        *((_QWORD *)a2 + 9) = v16;
        if ( v16 )
        {
          memset_0(v16, 0, cbData);
          v17 = RegQueryValueExW(hKey, L"TypeNameResource", 0, 0, *((LPBYTE *)a2 + 9), &cbData);
          v3 = v17;
          if ( v17 > 0 )
            v3 = (unsigned __int16)v17 | 0x80070000;
          if ( v3 >= 0 )
          {
            *((_DWORD *)a2 + 23) |= 1u;
            goto LABEL_46;
          }
          v6 = 658;
          LODWORD(phkResult) = (unsigned __int16)v3;
          goto LABEL_14;
        }
        v6 = 648;
      }
      else
      {
        v6 = 612;
      }
    }
    else
    {
      v6 = 577;
    }
    v3 = -2147024882;
    LODWORD(phkResult) = 14;
    goto LABEL_14;
  }
LABEL_10:
  v3 = -2147024362;
LABEL_45:
  WdipFree(*((_QWORD *)a2 + 7));
  v18 = *((_QWORD *)a2 + 8);
  *((_QWORD *)a2 + 7) = 0;
  WdipFree(v18);
  v19 = *((_QWORD *)a2 + 9);
  *((_QWORD *)a2 + 8) = 0;
  WdipFree(v19);
  *((_QWORD *)a2 + 9) = 0;
  *((_QWORD *)a2 + 10) = 0;
  *((_DWORD *)a2 + 22) = 0;
LABEL_46:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000d880  mov     [rsp-18h+arg_0], rbx
0x18000d885  mov     [rsp-18h+arg_18], rsi
0x18000d88a  push    rbp
0x18000d88b  push    rdi
0x18000d88c  push    r14
0x18000d88e  mov     rbp, rsp
0x18000d891  sub     rsp, 30h
0x18000d895  xor     r14d, r14d
0x18000d898  mov     rdi, rdx
0x18000d89b  mov     [rbp+hKey], r14
0x18000d89f  mov     [rbp+cbData], r14d
0x18000d8a3  test    rdx, rdx
0x18000d8a6  jnz     short loc_18000D8DA
0x18000d8a8  lea     r9, aErrorD; "Error = %d"
0x18000d8af  mov     dword ptr [rsp+30h+phkResult], 57h ; 'W'; Args
0x18000d8b7  mov     r8d, 21Ch; int
0x18000d8bd  lea     rdx, aDpspenumerates_0; "DpspEnumerateScenarioResourceInformatio"...
0x18000d8c4  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000d8cb  mov     ebx, 80070057h
0x18000d8d0  call    WdipTraceError
0x18000d8d5  jmp     loc_18000DC05
0x18000d8da  lea     rax, [rbp+hKey]
0x18000d8de  mov     r9d, 20019h; samDesired
0x18000d8e4  xor     r8d, r8d; ulOptions
0x18000d8e7  mov     [rsp+30h+phkResult], rax; phkResult
0x18000d8ec  lea     rdx, aDisplayresourc; "DisplayResources"
0x18000d8f3  call    cs:__imp_RegOpenKeyExW
0x18000d8f9  mov     ebx, eax
0x18000d8fb  test    eax, eax
0x18000d8fd  jnz     loc_18000DBC3
0x18000d903  mov     rcx, [rbp+hKey]; hKey
0x18000d907  test    rcx, rcx
0x18000d90a  jz      loc_18000DBCE
0x18000d910  lea     rax, [rbp+cbData]
0x18000d914  xor     r9d, r9d; lpType
0x18000d917  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000d91c  lea     rdx, aIconresource; "IconResource"
0x18000d923  xor     r8d, r8d; lpReserved
0x18000d926  mov     [rsp+30h+phkResult], r14; lpData
0x18000d92b  call    cs:__imp_RegQueryValueExW
0x18000d931  mov     ebx, eax
0x18000d933  mov     esi, 80070000h
0x18000d938  test    eax, eax
0x18000d93a  jle     short loc_18000D941
0x18000d93c  movzx   ebx, ax
0x18000d93f  or      ebx, esi
0x18000d941  test    ebx, ebx
0x18000d943  jns     short loc_18000D954
0x18000d945  movzx   eax, bx
0x18000d948  mov     r8d, 234h
0x18000d94e  mov     dword ptr [rsp+30h+phkResult], eax
0x18000d952  jmp     short loc_18000D99B
0x18000d954  mov     eax, [rbp+cbData]
0x18000d957  add     eax, 2
0x18000d95a  mov     [rbp+cbData], eax
0x18000d95d  mov     ecx, eax
0x18000d95f  cmp     eax, 1
0x18000d962  ja      short loc_18000D96E
0x18000d964  mov     ebx, 80070216h
0x18000d969  jmp     loc_18000DBD6
0x18000d96e  add     ecx, 7
0x18000d971  and     ecx, 0FFFFFFF8h
0x18000d974  mov     [rbp+cbData], ecx
0x18000d977  mov     [rdi+50h], ecx
0x18000d97a  call    WdipAlloc
0x18000d97f  mov     [rdi+38h], rax
0x18000d983  test    rax, rax
0x18000d986  jnz     short loc_18000D9BA
0x18000d988  mov     r8d, 241h; int
0x18000d98e  mov     ebx, 8007000Eh
0x18000d993  mov     dword ptr [rsp+30h+phkResult], 0Eh; Args
0x18000d99b  lea     r9, aErrorD; "Error = %d"
0x18000d9a2  lea     rdx, aDpspenumerates_0; "DpspEnumerateScenarioResourceInformatio"...
0x18000d9a9  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000d9b0  call    WdipTraceError
0x18000d9b5  jmp     loc_18000DBD6
0x18000d9ba  mov     r8d, [rbp+cbData]; Size
0x18000d9be  xor     edx, edx; Val
0x18000d9c0  mov     rcx, rax; void *
0x18000d9c3  call    memset_0
0x18000d9c8  mov     rcx, [rbp+hKey]; hKey
0x18000d9cc  lea     rax, [rbp+cbData]
0x18000d9d0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000d9d5  lea     rdx, aIconresource; "IconResource"
0x18000d9dc  mov     rax, [rdi+38h]
0x18000d9e0  xor     r9d, r9d; lpType
0x18000d9e3  xor     r8d, r8d; lpReserved
0x18000d9e6  mov     [rsp+30h+phkResult], rax; lpData
0x18000d9eb  call    cs:__imp_RegQueryValueExW
0x18000d9f1  mov     ebx, eax
0x18000d9f3  test    eax, eax
0x18000d9f5  jle     short loc_18000D9FC
0x18000d9f7  movzx   ebx, ax
0x18000d9fa  or      ebx, esi
0x18000d9fc  test    ebx, ebx
0x18000d9fe  jns     short loc_18000DA0F
0x18000da00  movzx   eax, bx
0x18000da03  mov     r8d, 24Bh
0x18000da09  mov     dword ptr [rsp+30h+phkResult], eax
0x18000da0d  jmp     short loc_18000D99B
0x18000da0f  mov     rcx, [rbp+hKey]; hKey
0x18000da13  lea     rax, [rbp+cbData]
0x18000da17  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000da1c  lea     rdx, aSourcenamereso; "SourceNameResource"
0x18000da23  xor     r9d, r9d; lpType
0x18000da26  mov     [rsp+30h+phkResult], r14; lpData
0x18000da2b  xor     r8d, r8d; lpReserved
0x18000da2e  call    cs:__imp_RegQueryValueExW
0x18000da34  mov     ebx, eax
0x18000da36  test    eax, eax
0x18000da38  jle     short loc_18000DA3F
0x18000da3a  movzx   ebx, ax
0x18000da3d  or      ebx, esi
0x18000da3f  test    ebx, ebx
0x18000da41  jns     short loc_18000DA55
0x18000da43  movzx   eax, bx
0x18000da46  mov     r8d, 257h
0x18000da4c  mov     dword ptr [rsp+30h+phkResult], eax
0x18000da50  jmp     loc_18000D99B
0x18000da55  mov     eax, [rbp+cbData]
0x18000da58  add     eax, 2
0x18000da5b  mov     [rbp+cbData], eax
0x18000da5e  mov     ecx, eax
0x18000da60  cmp     eax, 1
0x18000da63  jbe     loc_18000D964
0x18000da69  add     ecx, 7
0x18000da6c  and     ecx, 0FFFFFFF8h
0x18000da6f  mov     [rbp+cbData], ecx
0x18000da72  mov     [rdi+54h], ecx
0x18000da75  call    WdipAlloc
0x18000da7a  mov     [rdi+40h], rax
0x18000da7e  test    rax, rax
0x18000da81  jnz     short loc_18000DA8E
0x18000da83  mov     r8d, 264h
0x18000da89  jmp     loc_18000D98E
0x18000da8e  mov     r8d, [rbp+cbData]; Size
0x18000da92  xor     edx, edx; Val
0x18000da94  mov     rcx, rax; void *
0x18000da97  call    memset_0
0x18000da9c  mov     rcx, [rbp+hKey]; hKey
0x18000daa0  lea     rax, [rbp+cbData]
0x18000daa4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000daa9  lea     rdx, aSourcenamereso; "SourceNameResource"
0x18000dab0  mov     rax, [rdi+40h]
0x18000dab4  xor     r9d, r9d; lpType
0x18000dab7  xor     r8d, r8d; lpReserved
0x18000daba  mov     [rsp+30h+phkResult], rax; lpData
0x18000dabf  call    cs:__imp_RegQueryValueExW
0x18000dac5  mov     ebx, eax
0x18000dac7  test    eax, eax
0x18000dac9  jle     short loc_18000DAD0
0x18000dacb  movzx   ebx, ax
0x18000dace  or      ebx, esi
0x18000dad0  test    ebx, ebx
0x18000dad2  jns     short loc_18000DAE6
0x18000dad4  movzx   eax, bx
0x18000dad7  mov     r8d, 26Eh
0x18000dadd  mov     dword ptr [rsp+30h+phkResult], eax
0x18000dae1  jmp     loc_18000D99B
0x18000dae6  mov     rcx, [rbp+hKey]; hKey
0x18000daea  lea     rax, [rbp+cbData]
0x18000daee  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000daf3  lea     rdx, aTypenameresour; "TypeNameResource"
0x18000dafa  xor     r9d, r9d; lpType
0x18000dafd  mov     [rsp+30h+phkResult], r14; lpData
0x18000db02  xor     r8d, r8d; lpReserved
0x18000db05  call    cs:__imp_RegQueryValueExW
0x18000db0b  mov     ebx, eax
0x18000db0d  test    eax, eax
0x18000db0f  jle     short loc_18000DB16
0x18000db11  movzx   ebx, ax
0x18000db14  or      ebx, esi
0x18000db16  test    ebx, ebx
0x18000db18  jns     short loc_18000DB2C
0x18000db1a  movzx   eax, bx
0x18000db1d  mov     r8d, 27Bh
0x18000db23  mov     dword ptr [rsp+30h+phkResult], eax
0x18000db27  jmp     loc_18000D99B
0x18000db2c  mov     eax, [rbp+cbData]
0x18000db2f  add     eax, 2
0x18000db32  mov     [rbp+cbData], eax
0x18000db35  mov     ecx, eax
0x18000db37  cmp     eax, 1
0x18000db3a  jbe     loc_18000D964
0x18000db40  add     ecx, 7
0x18000db43  and     ecx, 0FFFFFFF8h
0x18000db46  mov     [rbp+cbData], ecx
0x18000db49  mov     [rdi+58h], ecx
0x18000db4c  call    WdipAlloc
0x18000db51  mov     [rdi+48h], rax
0x18000db55  test    rax, rax
0x18000db58  jnz     short loc_18000DB65
0x18000db5a  mov     r8d, 288h
0x18000db60  jmp     loc_18000D98E
0x18000db65  mov     r8d, [rbp+cbData]; Size
0x18000db69  xor     edx, edx; Val
0x18000db6b  mov     rcx, rax; void *
0x18000db6e  call    memset_0
0x18000db73  mov     rcx, [rbp+hKey]; hKey
0x18000db77  lea     rax, [rbp+cbData]
0x18000db7b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000db80  lea     rdx, aTypenameresour; "TypeNameResource"
0x18000db87  mov     rax, [rdi+48h]
0x18000db8b  xor     r9d, r9d; lpType
0x18000db8e  xor     r8d, r8d; lpReserved
0x18000db91  mov     [rsp+30h+phkResult], rax; lpData
0x18000db96  call    cs:__imp_RegQueryValueExW
0x18000db9c  mov     ebx, eax
0x18000db9e  test    eax, eax
0x18000dba0  jle     short loc_18000DBA7
0x18000dba2  movzx   ebx, ax
0x18000dba5  or      ebx, esi
0x18000dba7  test    ebx, ebx
0x18000dba9  jns     short loc_18000DBBD
0x18000dbab  movzx   eax, bx
0x18000dbae  mov     r8d, 292h
0x18000dbb4  mov     dword ptr [rsp+30h+phkResult], eax
0x18000dbb8  jmp     loc_18000D99B
0x18000dbbd  or      dword ptr [rdi+5Ch], 1
0x18000dbc1  jmp     short loc_18000DC05
0x18000dbc3  jle     short loc_18000DBCE
0x18000dbc5  movzx   ebx, ax
0x18000dbc8  or      ebx, 80070000h
0x18000dbce  mov     [rbp+hKey], r14
0x18000dbd2  test    ebx, ebx
0x18000dbd4  jns     short loc_18000DC05
0x18000dbd6  mov     rcx, [rdi+38h]
0x18000dbda  call    WdipFree
0x18000dbdf  mov     rcx, [rdi+40h]
0x18000dbe3  mov     [rdi+38h], r14
0x18000dbe7  call    WdipFree
0x18000dbec  mov     rcx, [rdi+48h]
0x18000dbf0  mov     [rdi+40h], r14
0x18000dbf4  call    WdipFree
0x18000dbf9  mov     [rdi+48h], r14
0x18000dbfd  mov     [rdi+50h], r14
0x18000dc01  mov     [rdi+58h], r14d
0x18000dc05  mov     rcx, [rbp+hKey]; hKey
0x18000dc09  test    rcx, rcx
0x18000dc0c  jz      short loc_18000DC14
0x18000dc0e  call    cs:__imp_RegCloseKey
0x18000dc14  mov     rsi, [rsp+30h+arg_18]
0x18000dc19  mov     eax, ebx
0x18000dc1b  mov     rbx, [rsp+30h+arg_0]
0x18000dc20  add     rsp, 30h
0x18000dc24  pop     r14
0x18000dc26  pop     rdi
0x18000dc27  pop     rbp
0x18000dc28  retn
```
