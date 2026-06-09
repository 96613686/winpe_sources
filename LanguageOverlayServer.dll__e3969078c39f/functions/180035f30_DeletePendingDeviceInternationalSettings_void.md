# DeletePendingDeviceInternationalSettings(void)

- ea: `0x180035f30`
- end: `0x180035fc5`
- name: `?DeletePendingDeviceInternationalSettings@@YAJXZ`
- size: `149`
- prototype: `int(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180019b40`
- `0x1800261ac`

## callees

- `0x180009084`
- `0x180035f30`
- `0x180060320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fb0`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180035f63`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180035f63`

## string_xrefs

- `0x180035f8b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
__int64 __fastcall DeletePendingDeviceInternationalSettings(__int64 a1, __int64 a2)
{
  const char *v2; // r9
  LSTATUS v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    TryOpenLanguageOverlayKey(&hKey, a2, L"PendingSettings", 0xF003Fu);
    if ( hKey )
    {
      v3 = RegDeleteKeyValueW(hKey, 0, L"DeviceInternationalSettings");
      v4 = v3;
      if ( (v3 & 0xFFFFFFFD) != 0 )
      {
        if ( v3 > 0 )
          v4 = (unsigned __int16)v3 | 0x80070000;
        if ( (v4 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2FF,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
            (const char *)v4,
            v6);
        RegCloseKey(hKey);
        return v4;
      }
      RegCloseKey(hKey);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x303,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\language"
                                         "providerutils.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180035f30  push    rdi; int
0x180035f32  sub     rsp, 20h
0x180035f36  mov     r9d, 0F003Fh
0x180035f3c  lea     r8, aPendingsetting; "PendingSettings"
0x180035f43  lea     rcx, [rsp+28h+hKey]
0x180035f48  call    ?TryOpenLanguageOverlayKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4LanguageOverlayHive@@PEBGK@Z; TryOpenLanguageOverlayKey(LanguageOverlayHive,ushort const *,ulong)
0x180035f4d  cmp     [rsp+28h+hKey], 0
0x180035f53  jz      short loc_180035FB6
0x180035f55  lea     r8, aDeviceinternat; "DeviceInternationalSettings"
0x180035f5c  xor     edx, edx; lpSubKey
0x180035f5e  mov     rcx, [rsp+28h+hKey]; hKey
0x180035f63  call    cs:__imp_RegDeleteKeyValueW
0x180035f69  mov     edi, eax
0x180035f6b  test    eax, 0FFFFFFFDh
0x180035f70  jz      short loc_180035FAB
0x180035f72  test    eax, eax
0x180035f74  jle     short loc_180035F7F
0x180035f76  movzx   edi, ax
0x180035f79  or      edi, 80070000h
0x180035f7f  test    edi, edi
0x180035f81  jns     short loc_180035F9C
0x180035f83  mov     rcx, [rsp+28h]; this
0x180035f88  mov     r9d, edi; char *
0x180035f8b  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035f92  mov     edx, 2FFh; void *
0x180035f97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f9c  mov     rcx, [rsp+28h+hKey]; hKey
0x180035fa1  call    cs:__imp_RegCloseKey
0x180035fa7  mov     eax, edi
0x180035fa9  jmp     short loc_180035FBE
0x180035fab  mov     rcx, [rsp+28h+hKey]; hKey
0x180035fb0  call    cs:__imp_RegCloseKey
0x180035fb6  xor     eax, eax
0x180035fb8  jmp     short loc_180035FBE
0x180035fba  mov     eax, dword ptr [rsp+28h+hKey]
0x180035fbe  add     rsp, 20h
0x180035fc2  pop     rdi
0x180035fc3  retn
```
