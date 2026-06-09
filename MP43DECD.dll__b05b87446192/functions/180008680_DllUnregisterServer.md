# DllUnregisterServer

- ea: `0x180008680`
- end: `0x1800086ea`
- name: `DllUnregisterServer`
- size: `106`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008680`
- `0x180008e60`

## import_xrefs

- `MFPlat!MFTUnregister` at `0x1800086ce`
- `MFPlat!MFTUnregister` at `0x1800086ce`
- `msdmo!DMOUnregister` at `0x18000869f`
- `msdmo!DMOUnregister` at `0x18000869f`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const struct _GUID *v0; // rcx
  LSTATUS v1; // ebx
  const struct _GUID *v2; // rcx
  int v3; // edi
  LSTATUS v4; // eax
  int v5; // eax
  CLSID clsidMFT; // [rsp+20h] [rbp-18h] BYREF

  v1 = DeleteCLSIDRegKey(v0);
  v3 = DMOUnregister(&CLSID_CMpeg43DecMediaObject, &DMOCATEGORY_VIDEO_DECODER);
  if ( v1 < 0 )
    v3 = v1;
  v4 = DeleteCLSIDRegKey(v2);
  if ( v3 >= 0 )
  {
    v3 = 0;
    if ( v4 < 0 )
      v3 = v4;
  }
  clsidMFT = CLSID_CMpeg43DecMediaObject;
  v5 = MFTUnregister(&clsidMFT);
  if ( v3 >= 0 && v5 < 0 )
    return v5;
  return v3;
}

```

## disassembly

```asm
0x180008680  mov     [rsp+arg_0], rbx
0x180008685  push    rdi
0x180008686  sub     rsp, 30h
0x18000868a  call    DeleteCLSIDRegKey
0x18000868f  lea     rdx, DMOCATEGORY_VIDEO_DECODER; guidCategory
0x180008696  mov     ebx, eax
0x180008698  lea     rcx, CLSID_CMpeg43DecMediaObject; clsidDMO
0x18000869f  call    cs:__imp_DMOUnregister
0x1800086a5  mov     edi, eax
0x1800086a7  test    ebx, ebx
0x1800086a9  cmovs   edi, ebx
0x1800086ac  call    DeleteCLSIDRegKey
0x1800086b1  test    edi, edi
0x1800086b3  js      short loc_1800086BC
0x1800086b5  xor     edi, edi
0x1800086b7  test    eax, eax
0x1800086b9  cmovs   edi, eax
0x1800086bc  movups  xmm0, xmmword ptr cs:CLSID_CMpeg43DecMediaObject.Data1
0x1800086c3  lea     rcx, [rsp+38h+clsidMFT]; clsidMFT
0x1800086c8  movdqu  xmmword ptr [rsp+38h+clsidMFT.Data1], xmm0
0x1800086ce  call    cs:__imp_MFTUnregister
0x1800086d4  test    edi, edi
0x1800086d6  js      short loc_1800086DD
0x1800086d8  test    eax, eax
0x1800086da  cmovs   edi, eax
0x1800086dd  mov     rbx, [rsp+38h+arg_0]
0x1800086e2  mov     eax, edi
0x1800086e4  add     rsp, 30h
0x1800086e8  pop     rdi
0x1800086e9  retn
```
