# DllUnregisterServer

- ea: `0x1800036d0`
- end: `0x180003726`
- name: `DllUnregisterServer`
- size: `86`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800036d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800036e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800036e4`
- `MFPlat!MFTUnregister` at `0x180003718`
- `MFPlat!MFTUnregister` at `0x180003718`

## string_xrefs

- `0x1800036d6`: `Software\Classes\CLSID\{265011AE-5481-4f77-A295-ABB6FFE8D63E}`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LSTATUS v0; // eax
  HRESULT v1; // ebx
  CLSID clsidMFT; // [rsp+20h] [rbp-18h] BYREF

  v0 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID\\{265011AE-5481-4f77-A295-ABB6FFE8D63E}");
  v1 = v0;
  if ( v0 == 2 )
  {
    v1 = 0;
LABEL_6:
    clsidMFT = CLSID_MSAMRNBDecoder;
    MFTUnregister(&clsidMFT);
    return v1;
  }
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
    goto LABEL_6;
  return v1;
}

```

## disassembly

```asm
0x1800036d0  push    rbx
0x1800036d2  sub     rsp, 30h
0x1800036d6  lea     rdx, SubKey; "Software\\Classes\\CLSID\\{265011AE-548"...
0x1800036dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800036e4  call    cs:__imp_RegDeleteTreeW
0x1800036ea  mov     ebx, eax
0x1800036ec  cmp     eax, 2
0x1800036ef  jnz     short loc_1800036F5
0x1800036f1  xor     ebx, ebx
0x1800036f3  jmp     short loc_180003706
0x1800036f5  test    eax, eax
0x1800036f7  jle     short loc_180003702
0x1800036f9  movzx   ebx, ax
0x1800036fc  or      ebx, 80070000h
0x180003702  test    ebx, ebx
0x180003704  js      short loc_18000371E
0x180003706  movups  xmm0, xmmword ptr cs:CLSID_MSAMRNBDecoder.Data1
0x18000370d  lea     rcx, [rsp+38h+clsidMFT]; clsidMFT
0x180003712  movdqu  xmmword ptr [rsp+38h+clsidMFT.Data1], xmm0
0x180003718  call    cs:__imp_MFTUnregister
0x18000371e  mov     eax, ebx
0x180003720  add     rsp, 30h
0x180003724  pop     rbx
0x180003725  retn
```
