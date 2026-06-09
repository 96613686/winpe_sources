# DllUnregisterServer

- ea: `0x18006bdf0`
- end: `0x18006be68`
- name: `DllUnregisterServer`
- size: `120`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ab90`
- `0x18006bdf0`
- `0x18006c110`

## import_xrefs

- `msdmo!DMOUnregister` at `0x18006be44`
- `msdmo!DMOUnregister` at `0x18006be44`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006be2e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006be2e`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LSTATUS CLSIDRegPath; // ebx
  HRESULT result; // eax
  WCHAR SubKey[80]; // [rsp+20h] [rbp-B8h] BYREF

  CLSIDRegPath = MakeCLSIDRegPath(&CLSID_CResamplerMediaObject, SubKey);
  if ( CLSIDRegPath >= 0 )
    CLSIDRegPath = RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey);
  result = DMOUnregister(&CLSID_CResamplerMediaObject, &DMOCATEGORY_AUDIO_EFFECT);
  if ( CLSIDRegPath < 0 )
    return CLSIDRegPath;
  return result;
}

```

## disassembly

```asm
0x18006bdf0  push    rbx
0x18006bdf2  sub     rsp, 0D0h
0x18006bdf9  mov     rax, cs:__security_cookie
0x18006be00  xor     rax, rsp
0x18006be03  mov     [rsp+0D8h+var_18], rax
0x18006be0b  lea     rdx, [rsp+0D8h+SubKey]; unsigned __int16 *
0x18006be10  lea     rcx, CLSID_CResamplerMediaObject; struct _GUID *
0x18006be17  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18006be1c  mov     ebx, eax
0x18006be1e  test    eax, eax
0x18006be20  js      short loc_18006BE36
0x18006be22  lea     rdx, [rsp+0D8h+SubKey]; lpSubKey
0x18006be27  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006be2e  call    cs:__imp_RegDeleteTreeW
0x18006be34  mov     ebx, eax
0x18006be36  lea     rdx, DMOCATEGORY_AUDIO_EFFECT; guidCategory
0x18006be3d  lea     rcx, CLSID_CResamplerMediaObject; clsidDMO
0x18006be44  call    cs:__imp_DMOUnregister
0x18006be4a  test    ebx, ebx
0x18006be4c  cmovs   eax, ebx
0x18006be4f  mov     rcx, [rsp+0D8h+var_18]
0x18006be57  xor     rcx, rsp; StackCookie
0x18006be5a  call    __security_check_cookie
0x18006be5f  add     rsp, 0D0h
0x18006be66  pop     rbx
0x18006be67  retn
```
