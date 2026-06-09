# PimIMService::GetUpdateCookie(ulong *)

- ea: `0x18000746c`
- end: `0x18000756d`
- name: `?GetUpdateCookie@PimIMService@@QEAAJPEAK@Z`
- size: `257`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cf70`
- `0x18000d020`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x18000746c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000755d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000755d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007509`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007509`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800074c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800074c6`

## string_xrefs

- `0x180007544`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetUpdateCookie(PimIMService *this, unsigned int *a2)
{
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  LSTATUS v7; // eax
  HKEY v8; // rcx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int v11; // [rsp+54h] [rbp+24h]
  unsigned int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v11 = HIDWORD(this);
  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  *a2 = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 1u, phkResult);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = 3242;
    goto LABEL_13;
  }
  v7 = RegQueryValueExW(hKey, L"RunCookie", 0, &Type, (LPBYTE)&Data, &cbData);
  v5 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_12;
  }
  if ( Type != 4 )
  {
LABEL_12:
    v6 = 3252;
LABEL_13:
    Log_HREvent(
      v5,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v6);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v8 = hKey;
  *a2 = Data;
  if ( v8 )
    RegCloseKey(v8);
  return 0;
}

```

## disassembly

```asm
0x18000746c  mov     qword ptr [rsp-18h+Type], rcx
0x180007471  push    rbp
0x180007472  push    rbx
0x180007473  push    rdi
0x180007474  mov     rbp, rsp
0x180007477  sub     rsp, 30h
0x18000747b  lea     rcx, [rbp+hKey]
0x18000747f  mov     [rbp+hKey], 0
0x180007487  mov     rdi, rdx
0x18000748a  mov     [rbp+Data], 0
0x180007491  mov     [rbp+cbData], 4
0x180007498  mov     [rbp+Type], 0
0x18000749f  mov     dword ptr [rdx], 0
0x1800074a5  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800074aa  mov     r9d, 1; samDesired
0x1800074b0  mov     [rsp+30h+phkResult], rax; phkResult
0x1800074b5  xor     r8d, r8d; ulOptions
0x1800074b8  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x1800074bf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800074c6  call    cs:__imp_RegOpenKeyExW
0x1800074cc  mov     ebx, eax
0x1800074ce  test    eax, eax
0x1800074d0  jz      short loc_1800074E5
0x1800074d2  jle     short loc_1800074DD
0x1800074d4  movzx   ebx, ax
0x1800074d7  or      ebx, 80070000h
0x1800074dd  mov     r9d, 0CAAh
0x1800074e3  jmp     short loc_180007544
0x1800074e5  mov     rcx, [rbp+hKey]; hKey
0x1800074e9  lea     rax, [rbp+cbData]
0x1800074ed  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800074f2  lea     r9, [rbp+Type]; lpType
0x1800074f6  lea     rax, [rbp+Data]
0x1800074fa  xor     r8d, r8d; lpReserved
0x1800074fd  lea     rdx, aRuncookie; "RunCookie"
0x180007504  mov     [rsp+30h+phkResult], rax; lpData
0x180007509  call    cs:__imp_RegQueryValueExW
0x18000750f  mov     ebx, eax
0x180007511  test    eax, eax
0x180007513  jnz     short loc_180007533
0x180007515  cmp     [rbp+Type], 4
0x180007519  jnz     short loc_18000753E
0x18000751b  mov     rcx, [rbp+hKey]; hKey
0x18000751f  mov     eax, [rbp+Data]
0x180007522  mov     [rdi], eax
0x180007524  test    rcx, rcx
0x180007527  jz      short loc_18000752F
0x180007529  call    cs:__imp_RegCloseKey
0x18000752f  xor     eax, eax
0x180007531  jmp     short loc_180007565
0x180007533  jle     short loc_18000753E
0x180007535  movzx   ebx, ax
0x180007538  or      ebx, 80070000h
0x18000753e  mov     r9d, 0CB4h
0x180007544  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000754b  xor     edx, edx
0x18000754d  mov     ecx, ebx
0x18000754f  call    Log_HREvent
0x180007554  mov     rcx, [rbp+hKey]; hKey
0x180007558  test    rcx, rcx
0x18000755b  jz      short loc_180007563
0x18000755d  call    cs:__imp_RegCloseKey
0x180007563  mov     eax, ebx
0x180007565  add     rsp, 30h
0x180007569  pop     rdi
0x18000756a  pop     rbx
0x18000756b  pop     rbp
0x18000756c  retn
```
