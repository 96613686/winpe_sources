# DllUnregisterServer

- ea: `0x18000e480`
- end: `0x18000e4f7`
- name: `DllUnregisterServer`
- size: `119`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e480`
- `0x18000ecb0`

## import_xrefs

- `MFPlat!MFTUnregister` at `0x18000e4d4`
- `MFPlat!MFTUnregister` at `0x18000e4d4`
- `msdmo!DMOUnregister` at `0x18000e49f`
- `msdmo!DMOUnregister` at `0x18000e49f`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LSTATUS v0; // ebx
  int v1; // edi
  LSTATUS v2; // eax
  int v3; // eax
  CLSID clsidMFT; // [rsp+20h] [rbp-18h] BYREF

  v0 = sub_18000ECB0();
  v1 = DMOUnregister(&clsidDMO, &guidCategory);
  if ( v0 < 0 )
    v1 = v0;
  v2 = sub_18000ECB0();
  if ( v1 >= 0 )
  {
    v1 = 0;
    if ( v2 < 0 )
      v1 = v2;
  }
  clsidMFT = clsidDMO;
  v3 = MFTUnregister(&clsidMFT);
  if ( v1 >= 0 && v3 < 0 )
    return v3;
  return v1;
}

```

## disassembly

```asm
0x18000e480  mov     [rsp+arg_0], rbx
0x18000e485  push    rdi
0x18000e486  sub     rsp, 30h
0x18000e48a  call    sub_18000ECB0
0x18000e48f  lea     rdx, guidCategory; guidCategory
0x18000e496  mov     ebx, eax
0x18000e498  lea     rcx, clsidDMO; clsidDMO
0x18000e49f  call    cs:DMOUnregister
0x18000e4a6  nop     dword ptr [rax+rax+00h]
0x18000e4ab  mov     edi, eax
0x18000e4ad  test    ebx, ebx
0x18000e4af  cmovs   edi, ebx
0x18000e4b2  call    sub_18000ECB0
0x18000e4b7  test    edi, edi
0x18000e4b9  js      short loc_18000E4C2
0x18000e4bb  xor     edi, edi
0x18000e4bd  test    eax, eax
0x18000e4bf  cmovs   edi, eax
0x18000e4c2  movups  xmm0, xmmword ptr cs:clsidDMO.Data1
0x18000e4c9  lea     rcx, [rsp+38h+clsidMFT]; clsidMFT
0x18000e4ce  movdqu  xmmword ptr [rsp+38h+clsidMFT.Data1], xmm0
0x18000e4d4  call    cs:MFTUnregister
0x18000e4db  nop     dword ptr [rax+rax+00h]
0x18000e4e0  test    edi, edi
0x18000e4e2  js      short loc_18000E4E9
0x18000e4e4  test    eax, eax
0x18000e4e6  cmovs   edi, eax
0x18000e4e9  mov     rbx, [rsp+38h+arg_0]
0x18000e4ee  mov     eax, edi
0x18000e4f0  add     rsp, 30h
0x18000e4f4  pop     rdi
0x18000e4f5  retn
```
