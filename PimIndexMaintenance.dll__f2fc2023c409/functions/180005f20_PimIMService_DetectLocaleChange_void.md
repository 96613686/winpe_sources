# PimIMService::DetectLocaleChange(void)

- ea: `0x180005f20`
- end: `0x18000605f`
- name: `?DetectLocaleChange@PimIMService@@QEAAJXZ`
- size: `319`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180008f30`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x180005f20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000604f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005f79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000604f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005fbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005fbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006027`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006027`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180005f2e`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180005f2e`
- `PIMSTORE!CreateContactSettingsRegKey` at `0x180005f4b`
- `PIMSTORE!CreateContactSettingsRegKey` at `0x180005f4b`

## string_xrefs

- `0x180005f62`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::DetectLocaleChange(PimIMService *this)
{
  HKEY *v2; // rax
  unsigned int ContactSettingsRegKey; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  LSTATUS v7; // eax
  HKEY v8; // rcx
  LSTATUS v9; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  LCID lpData; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  lpData = GetSystemDefaultLCID();
  v2 = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  ContactSettingsRegKey = CreateContactSettingsRegKey(v2);
  if ( (ContactSettingsRegKey & 0x80000000) != 0 )
  {
    v4 = 3126;
    v5 = 1;
LABEL_3:
    Log_HREvent(
      ContactSettingsRegKey,
      v5,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v4);
    if ( hKey )
      RegCloseKey(hKey);
    return ContactSettingsRegKey;
  }
  Type = 0;
  Data = 0;
  cbData = 4;
  v7 = RegQueryValueExW(hKey, L"Locale", 0, &Type, (LPBYTE)&Data, &cbData);
  ContactSettingsRegKey = v7;
  if ( (v7 || Type != 4) && v7 != 2 )
  {
    if ( v7 > 0 )
      ContactSettingsRegKey = (unsigned __int16)v7 | 0x80070000;
    v4 = 3140;
LABEL_12:
    v5 = 0;
    goto LABEL_3;
  }
  if ( lpData != Data )
  {
    v8 = hKey;
    *((_DWORD *)this + 124) = 1;
    v9 = RegSetValueExW(v8, L"Locale", 0, 4u, (const BYTE *)&lpData, 4u);
    ContactSettingsRegKey = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        ContactSettingsRegKey = (unsigned __int16)v9 | 0x80070000;
      v4 = 3155;
      goto LABEL_12;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180005f20  push    rbp
0x180005f22  push    rbx
0x180005f23  push    rdi
0x180005f24  mov     rbp, rsp
0x180005f27  sub     rsp, 40h
0x180005f2b  mov     rdi, rcx
0x180005f2e  call    cs:__imp_GetSystemDefaultLCID
0x180005f34  lea     rcx, [rbp+hKey]
0x180005f38  mov     [rbp+hKey], 0
0x180005f40  mov     [rbp+arg_18], eax
0x180005f43  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180005f48  mov     rcx, rax
0x180005f4b  call    cs:__imp_CreateContactSettingsRegKey
0x180005f51  mov     ebx, eax
0x180005f53  test    eax, eax
0x180005f55  jns     short loc_180005F86
0x180005f57  mov     r9d, 0C36h
0x180005f5d  mov     edx, 1
0x180005f62  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005f69  mov     ecx, ebx
0x180005f6b  call    Log_HREvent
0x180005f70  mov     rcx, [rbp+hKey]; hKey
0x180005f74  test    rcx, rcx
0x180005f77  jz      short loc_180005F7F
0x180005f79  call    cs:__imp_RegCloseKey
0x180005f7f  mov     eax, ebx
0x180005f81  jmp     loc_180006057
0x180005f86  mov     rcx, [rbp+hKey]; hKey
0x180005f8a  lea     rax, [rbp+cbData]
0x180005f8e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180005f93  lea     r9, [rbp+Type]; lpType
0x180005f97  lea     rax, [rbp+Data]
0x180005f9b  mov     [rbp+Type], 0
0x180005fa2  xor     r8d, r8d; lpReserved
0x180005fa5  mov     [rsp+40h+lpData], rax; lpData
0x180005faa  lea     rdx, ValueName; "Locale"
0x180005fb1  mov     [rbp+Data], 0
0x180005fb8  mov     [rbp+cbData], 4
0x180005fbf  call    cs:__imp_RegQueryValueExW
0x180005fc5  mov     ebx, eax
0x180005fc7  test    eax, eax
0x180005fc9  jnz     short loc_180005FD1
0x180005fcb  cmp     [rbp+Type], 4
0x180005fcf  jz      short loc_180005FF0
0x180005fd1  cmp     eax, 2
0x180005fd4  jz      short loc_180005FF0
0x180005fd6  test    eax, eax
0x180005fd8  jle     short loc_180005FE3
0x180005fda  movzx   ebx, ax
0x180005fdd  or      ebx, 80070000h
0x180005fe3  mov     r9d, 0C44h
0x180005fe9  xor     edx, edx
0x180005feb  jmp     loc_180005F62
0x180005ff0  mov     eax, [rbp+Data]
0x180005ff3  cmp     [rbp+arg_18], eax
0x180005ff6  jz      short loc_180006046
0x180005ff8  mov     rcx, [rbp+hKey]; hKey
0x180005ffc  lea     rax, [rbp+arg_18]
0x180006000  mov     dword ptr [rsp+40h+lpcbData], 4; cbData
0x180006008  lea     rdx, ValueName; "Locale"
0x18000600f  mov     r9d, 4; dwType
0x180006015  mov     [rsp+40h+lpData], rax; lpData
0x18000601a  xor     r8d, r8d; Reserved
0x18000601d  mov     dword ptr [rdi+1F0h], 1
0x180006027  call    cs:__imp_RegSetValueExW
0x18000602d  mov     ebx, eax
0x18000602f  test    eax, eax
0x180006031  jz      short loc_180006046
0x180006033  jle     short loc_18000603E
0x180006035  movzx   ebx, ax
0x180006038  or      ebx, 80070000h
0x18000603e  mov     r9d, 0C53h
0x180006044  jmp     short loc_180005FE9
0x180006046  mov     rcx, [rbp+hKey]; hKey
0x18000604a  test    rcx, rcx
0x18000604d  jz      short loc_180006055
0x18000604f  call    cs:__imp_RegCloseKey
0x180006055  xor     eax, eax
0x180006057  add     rsp, 40h
0x18000605b  pop     rdi
0x18000605c  pop     rbx
0x18000605d  pop     rbp
0x18000605e  retn
```
