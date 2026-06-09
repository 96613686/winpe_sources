# PimIMService::FlushTrackedStoresInRegistry(void)

- ea: `0x180006a1c`
- end: `0x180006adb`
- name: `?FlushTrackedStoresInRegistry@PimIMService@@QEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800058d0`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x180006a1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006acd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006acd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006a55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006a55`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180006aa4`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180006aa4`

## string_xrefs

- `0x180006a7b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::FlushTrackedStoresInRegistry(PimIMService *this)
{
  HKEY *phkResult; // rax
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0xF003Fu, phkResult);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 != 1168 )
    {
      if ( v2 > 0 )
        v3 = (unsigned __int16)v2 | 0x80070000;
      v4 = 1174;
LABEL_6:
      Log_HREvent(
        v3,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v4);
      if ( hKey )
        RegCloseKey(hKey);
      return v3;
    }
  }
  else
  {
    v6 = RegFlushKey(hKey);
    v3 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      v4 = 1179;
      goto LABEL_6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180006a1c  mov     [rsp+hKey], rcx
0x180006a21  push    rbx
0x180006a22  sub     rsp, 30h
0x180006a26  lea     rcx, [rsp+38h+hKey]
0x180006a2b  mov     [rsp+38h+hKey], 0
0x180006a34  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180006a39  mov     r9d, 0F003Fh; samDesired
0x180006a3f  mov     [rsp+38h+phkResult], rax; phkResult
0x180006a44  xor     r8d, r8d; ulOptions
0x180006a47  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x180006a4e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006a55  call    cs:__imp_RegOpenKeyExW
0x180006a5b  mov     ebx, eax
0x180006a5d  test    eax, eax
0x180006a5f  jz      short loc_180006A9F
0x180006a61  cmp     eax, 490h
0x180006a66  jz      short loc_180006AC3
0x180006a68  test    eax, eax
0x180006a6a  jle     short loc_180006A75
0x180006a6c  movzx   ebx, ax
0x180006a6f  or      ebx, 80070000h
0x180006a75  mov     r9d, 496h
0x180006a7b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006a82  xor     edx, edx
0x180006a84  mov     ecx, ebx
0x180006a86  call    Log_HREvent
0x180006a8b  mov     rcx, [rsp+38h+hKey]; hKey
0x180006a90  test    rcx, rcx
0x180006a93  jz      short loc_180006A9B
0x180006a95  call    cs:__imp_RegCloseKey
0x180006a9b  mov     eax, ebx
0x180006a9d  jmp     short loc_180006AD5
0x180006a9f  mov     rcx, [rsp+38h+hKey]; hKey
0x180006aa4  call    cs:__imp_RegFlushKey
0x180006aaa  mov     ebx, eax
0x180006aac  test    eax, eax
0x180006aae  jz      short loc_180006AC3
0x180006ab0  jle     short loc_180006ABB
0x180006ab2  movzx   ebx, ax
0x180006ab5  or      ebx, 80070000h
0x180006abb  mov     r9d, 49Bh
0x180006ac1  jmp     short loc_180006A7B
0x180006ac3  mov     rcx, [rsp+38h+hKey]; hKey
0x180006ac8  test    rcx, rcx
0x180006acb  jz      short loc_180006AD3
0x180006acd  call    cs:__imp_RegCloseKey
0x180006ad3  xor     eax, eax
0x180006ad5  add     rsp, 30h
0x180006ad9  pop     rbx
0x180006ada  retn
```
