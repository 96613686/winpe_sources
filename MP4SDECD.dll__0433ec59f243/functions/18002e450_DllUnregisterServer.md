# DllUnregisterServer

- ea: `0x18002e450`
- end: `0x18002e4de`
- name: `DllUnregisterServer`
- size: `142`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002e450`
- `0x18002ea10`

## import_xrefs

- `MFPlat!MFTUnregister` at `0x18002e4a3`
- `MFPlat!MFTUnregister` at `0x18002e4a3`
- `msdmo!DMOUnregister` at `0x18002e47a`
- `msdmo!DMOUnregister` at `0x18002e47a`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LSTATUS v0; // ebx
  int v1; // esi
  LSTATUS v2; // edi
  int v3; // ebx
  LSTATUS v4; // eax
  CLSID clsidMFT; // [rsp+20h] [rbp-18h] BYREF

  v0 = DeleteCLSIDRegKey(&CLSID_CMpeg4sDecMediaObject);
  v1 = DMOUnregister(&CLSID_CMpeg4sDecMediaObject, &DMOCATEGORY_VIDEO_DECODER);
  if ( v0 < 0 )
    v1 = v0;
  v2 = DeleteCLSIDRegKey(&CLSID_CMpeg4sDecMediaObject);
  clsidMFT = CLSID_CMpeg4sDecMFT;
  v3 = MFTUnregister(&clsidMFT);
  v4 = DeleteCLSIDRegKey(&CLSID_CMpeg4sDecMFT);
  if ( v1 < 0 )
    return v1;
  if ( v2 < 0 )
    return v2;
  if ( v3 >= 0 )
    return v4;
  return v3;
}

```

## disassembly

```asm
0x18002e450  mov     [rsp+arg_0], rbx
0x18002e455  mov     [rsp+arg_8], rsi
0x18002e45a  push    rdi
0x18002e45b  sub     rsp, 30h
0x18002e45f  lea     rdi, CLSID_CMpeg4sDecMediaObject
0x18002e466  mov     rcx, rdi
0x18002e469  call    DeleteCLSIDRegKey
0x18002e46e  lea     rdx, DMOCATEGORY_VIDEO_DECODER; guidCategory
0x18002e475  mov     rcx, rdi; clsidDMO
0x18002e478  mov     ebx, eax
0x18002e47a  call    cs:__imp_DMOUnregister
0x18002e480  test    ebx, ebx
0x18002e482  mov     rcx, rdi
0x18002e485  mov     esi, eax
0x18002e487  cmovs   esi, ebx
0x18002e48a  call    DeleteCLSIDRegKey
0x18002e48f  movups  xmm0, xmmword ptr cs:CLSID_CMpeg4sDecMFT.Data1
0x18002e496  lea     rcx, [rsp+38h+clsidMFT]; clsidMFT
0x18002e49b  mov     edi, eax
0x18002e49d  movdqu  xmmword ptr [rsp+38h+clsidMFT.Data1], xmm0
0x18002e4a3  call    cs:__imp_MFTUnregister
0x18002e4a9  lea     rcx, CLSID_CMpeg4sDecMFT
0x18002e4b0  mov     ebx, eax
0x18002e4b2  call    DeleteCLSIDRegKey
0x18002e4b7  test    esi, esi
0x18002e4b9  js      short loc_18002E4CA
0x18002e4bb  test    edi, edi
0x18002e4bd  js      short loc_18002E4C6
0x18002e4bf  test    ebx, ebx
0x18002e4c1  cmovns  ebx, eax
0x18002e4c4  jmp     short loc_18002E4CC
0x18002e4c6  mov     ebx, edi
0x18002e4c8  jmp     short loc_18002E4CC
0x18002e4ca  mov     ebx, esi
0x18002e4cc  mov     rsi, [rsp+38h+arg_8]
0x18002e4d1  mov     eax, ebx
0x18002e4d3  mov     rbx, [rsp+38h+arg_0]
0x18002e4d8  add     rsp, 30h
0x18002e4dc  pop     rdi
0x18002e4dd  retn
```
