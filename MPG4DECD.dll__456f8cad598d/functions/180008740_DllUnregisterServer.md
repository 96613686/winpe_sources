# DllUnregisterServer

- ea: `0x180008740`
- end: `0x1800087aa`
- name: `DllUnregisterServer`
- size: `106`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008740`
- `0x180008f20`

## import_xrefs

- `MFPlat!MFTUnregister` at `0x18000878e`
- `MFPlat!MFTUnregister` at `0x18000878e`
- `msdmo!DMOUnregister` at `0x18000875f`
- `msdmo!DMOUnregister` at `0x18000875f`

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
  v3 = DMOUnregister(&CLSID_CMpeg4DecMediaObject, &DMOCATEGORY_VIDEO_DECODER);
  if ( v1 < 0 )
    v3 = v1;
  v4 = DeleteCLSIDRegKey(v2);
  if ( v3 >= 0 )
  {
    v3 = 0;
    if ( v4 < 0 )
      v3 = v4;
  }
  clsidMFT = CLSID_CMpeg4DecMediaObject;
  v5 = MFTUnregister(&clsidMFT);
  if ( v3 >= 0 && v5 < 0 )
    return v5;
  return v3;
}

```

## disassembly

```asm
0x180008740  mov     [rsp+arg_0], rbx
0x180008745  push    rdi
0x180008746  sub     rsp, 30h
0x18000874a  call    DeleteCLSIDRegKey
0x18000874f  lea     rdx, DMOCATEGORY_VIDEO_DECODER; guidCategory
0x180008756  mov     ebx, eax
0x180008758  lea     rcx, CLSID_CMpeg4DecMediaObject; clsidDMO
0x18000875f  call    cs:__imp_DMOUnregister
0x180008765  mov     edi, eax
0x180008767  test    ebx, ebx
0x180008769  cmovs   edi, ebx
0x18000876c  call    DeleteCLSIDRegKey
0x180008771  test    edi, edi
0x180008773  js      short loc_18000877C
0x180008775  xor     edi, edi
0x180008777  test    eax, eax
0x180008779  cmovs   edi, eax
0x18000877c  movups  xmm0, xmmword ptr cs:CLSID_CMpeg4DecMediaObject.Data1
0x180008783  lea     rcx, [rsp+38h+clsidMFT]; clsidMFT
0x180008788  movdqu  xmmword ptr [rsp+38h+clsidMFT.Data1], xmm0
0x18000878e  call    cs:__imp_MFTUnregister
0x180008794  test    edi, edi
0x180008796  js      short loc_18000879D
0x180008798  test    eax, eax
0x18000879a  cmovs   edi, eax
0x18000879d  mov     rbx, [rsp+38h+arg_0]
0x1800087a2  mov     eax, edi
0x1800087a4  add     rsp, 30h
0x1800087a8  pop     rdi
0x1800087a9  retn
```
