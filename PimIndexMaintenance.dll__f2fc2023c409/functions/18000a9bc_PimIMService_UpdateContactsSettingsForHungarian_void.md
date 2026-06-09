# PimIMService::UpdateContactsSettingsForHungarian(void)

- ea: `0x18000a9bc`
- end: `0x18000ab3f`
- name: `?UpdateContactsSettingsForHungarian@PimIMService@@QEAAJXZ`
- size: `387`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x18000a9bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aab4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aab4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa33`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18000a9cc`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18000a9cc`
- `PIMSTORE!SetDisplayBy` at `0x18000ab0f`
- `PIMSTORE!SetDisplayBy` at `0x18000ab0f`
- `PIMSTORE!SetSortBy` at `0x18000aaee`
- `PIMSTORE!SetSortBy` at `0x18000aaee`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x18000aa09`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x18000aa09`

## string_xrefs

- `0x18000aa57`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::UpdateContactsSettingsForHungarian(PimIMService *this)
{
  HKEY *phkResult; // rbx
  int v3; // eax
  LSTATUS v4; // eax
  signed int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  if ( (GetSystemDefaultLCID() & 0x3FF) != 0xE || !*((_DWORD *)this + 124) )
    return 0;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v3 = IsCommsSystemService();
  v4 = RegOpenKeyExW(
         (HKEY)((v3 != 0) - 0x7FFFFFFFLL),
         L"Software\\Microsoft\\Pim\\Contacts\\Settings",
         0,
         0x20019u,
         phkResult);
  v5 = v4;
  if ( (v4 & 0xFFFFFFFD) == 0 )
  {
    Data = 0;
    if ( v4 )
      goto LABEL_19;
    Type = 0;
    cbData = 4;
    v9 = RegQueryValueExW(hKey, L"OEM_Overrides_SortDisplay", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v9;
    if ( (v9 || Type != 4) && v9 != 2 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      v6 = 3201;
      goto LABEL_7;
    }
    if ( !Data )
    {
LABEL_19:
      v5 = SetSortBy(1);
      if ( v5 < 0 )
      {
        v6 = 3212;
LABEL_21:
        v7 = 1;
        goto LABEL_8;
      }
      v5 = SetDisplayBy(1);
      if ( v5 < 0 )
      {
        v6 = 3213;
        goto LABEL_21;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v6 = 3186;
LABEL_7:
  v7 = 0;
LABEL_8:
  Log_HREvent(
    (unsigned int)v5,
    v7,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v6);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a9bc  mov     [rsp-8+arg_0], rbx
0x18000a9c1  push    rbp
0x18000a9c2  mov     rbp, rsp
0x18000a9c5  sub     rsp, 40h
0x18000a9c9  mov     rbx, rcx
0x18000a9cc  call    cs:__imp_GetSystemDefaultLCID
0x18000a9d2  mov     ecx, 3FFh
0x18000a9d7  and     ax, cx
0x18000a9da  mov     ecx, 0Eh
0x18000a9df  cmp     cx, ax
0x18000a9e2  jnz     loc_18000AB32
0x18000a9e8  cmp     dword ptr [rbx+1F0h], 0
0x18000a9ef  jz      loc_18000AB32
0x18000a9f5  lea     rcx, [rbp+hKey]
0x18000a9f9  mov     [rbp+hKey], 0
0x18000aa01  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000aa06  mov     rbx, rax
0x18000aa09  call    cs:__imp_IsCommsSystemService
0x18000aa0f  mov     r9d, 20019h; samDesired
0x18000aa15  mov     [rsp+40h+phkResult], rbx; phkResult
0x18000aa1a  neg     eax
0x18000aa1c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Pim\\Contacts\\Set"...
0x18000aa23  sbb     rcx, rcx
0x18000aa26  xor     r8d, r8d; ulOptions
0x18000aa29  neg     rcx
0x18000aa2c  add     rcx, 0FFFFFFFF80000001h; hKey
0x18000aa33  call    cs:__imp_RegOpenKeyExW
0x18000aa39  mov     ebx, eax
0x18000aa3b  test    eax, 0FFFFFFFDh
0x18000aa40  jz      short loc_18000AA7B
0x18000aa42  test    eax, eax
0x18000aa44  jle     short loc_18000AA4F
0x18000aa46  movzx   ebx, ax
0x18000aa49  or      ebx, 80070000h
0x18000aa4f  mov     r9d, 0C72h
0x18000aa55  xor     edx, edx
0x18000aa57  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000aa5e  mov     ecx, ebx
0x18000aa60  call    Log_HREvent
0x18000aa65  mov     rcx, [rbp+hKey]; hKey
0x18000aa69  test    rcx, rcx
0x18000aa6c  jz      short loc_18000AA74
0x18000aa6e  call    cs:__imp_RegCloseKey
0x18000aa74  mov     eax, ebx
0x18000aa76  jmp     loc_18000AB34
0x18000aa7b  mov     [rbp+Data], 0
0x18000aa82  test    eax, eax
0x18000aa84  jnz     short loc_18000AAE9
0x18000aa86  mov     rcx, [rbp+hKey]; hKey
0x18000aa8a  lea     r9, [rbp+Type]; lpType
0x18000aa8e  mov     [rbp+Type], eax
0x18000aa91  lea     rdx, aOemOverridesSo; "OEM_Overrides_SortDisplay"
0x18000aa98  lea     rax, [rbp+cbData]
0x18000aa9c  mov     [rbp+cbData], 4
0x18000aaa3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000aaa8  xor     r8d, r8d; lpReserved
0x18000aaab  lea     rax, [rbp+Data]
0x18000aaaf  mov     [rsp+40h+phkResult], rax; lpData
0x18000aab4  call    cs:__imp_RegQueryValueExW
0x18000aaba  mov     ebx, eax
0x18000aabc  test    eax, eax
0x18000aabe  jnz     short loc_18000AAC6
0x18000aac0  cmp     [rbp+Type], 4
0x18000aac4  jz      short loc_18000AAE3
0x18000aac6  cmp     eax, 2
0x18000aac9  jz      short loc_18000AAE3
0x18000aacb  test    eax, eax
0x18000aacd  jle     short loc_18000AAD8
0x18000aacf  movzx   ebx, ax
0x18000aad2  or      ebx, 80070000h
0x18000aad8  mov     r9d, 0C81h
0x18000aade  jmp     loc_18000AA55
0x18000aae3  cmp     [rbp+Data], 0
0x18000aae7  jnz     short loc_18000AB23
0x18000aae9  mov     ecx, 1
0x18000aaee  call    cs:__imp_SetSortBy
0x18000aaf4  mov     ebx, eax
0x18000aaf6  test    eax, eax
0x18000aaf8  jns     short loc_18000AB0A
0x18000aafa  mov     r9d, 0C8Ch
0x18000ab00  mov     edx, 1
0x18000ab05  jmp     loc_18000AA57
0x18000ab0a  mov     ecx, 1
0x18000ab0f  call    cs:__imp_SetDisplayBy
0x18000ab15  mov     ebx, eax
0x18000ab17  test    eax, eax
0x18000ab19  jns     short loc_18000AB23
0x18000ab1b  mov     r9d, 0C8Dh
0x18000ab21  jmp     short loc_18000AB00
0x18000ab23  mov     rcx, [rbp+hKey]; hKey
0x18000ab27  test    rcx, rcx
0x18000ab2a  jz      short loc_18000AB32
0x18000ab2c  call    cs:__imp_RegCloseKey
0x18000ab32  xor     eax, eax
0x18000ab34  mov     rbx, [rsp+40h+arg_0]
0x18000ab39  add     rsp, 40h
0x18000ab3d  pop     rbp
0x18000ab3e  retn
```
