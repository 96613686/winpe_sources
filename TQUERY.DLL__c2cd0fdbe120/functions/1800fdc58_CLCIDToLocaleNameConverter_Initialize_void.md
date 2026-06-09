# CLCIDToLocaleNameConverter::Initialize(void)

- ea: `0x1800fdc58`
- end: `0x1800fdccc`
- name: `?Initialize@CLCIDToLocaleNameConverter@@QEAAJXZ`
- size: `116`
- prototype: `__int64 __fastcall(CLCIDToLocaleNameConverter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800fdb94`
- `0x1801b5968`

## callees

- `0x1800fdc58`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fdc81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fdc95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fdc81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800fdc95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fdcc0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fdcc0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800fdc68`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800fdc68`

## string_xrefs

- `0x1800fdc61`: `kernelbase.dll`

## pseudocode

```c
HRESULT __fastcall CLCIDToLocaleNameConverter::Initialize(CLCIDToLocaleNameConverter *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v4; // rcx

  LibraryW = LoadLibraryW(L"kernelbase.dll");
  *((_QWORD *)this + 3) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "LocaleNameToLCID");
    v4 = (HMODULE)*((_QWORD *)this + 3);
    *(_QWORD *)this = ProcAddress;
    *((_QWORD *)this + 1) = GetProcAddress(v4, "LCIDToLocaleName");
  }
  *((_BYTE *)this + 32) = 1;
  return CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a, (LPVOID *)this + 2);
}

```

## disassembly

```asm
0x1800fdc58  push    rbx
0x1800fdc5a  sub     rsp, 30h
0x1800fdc5e  mov     rbx, rcx
0x1800fdc61  lea     rcx, LibFileName; "kernelbase.dll"
0x1800fdc68  call    cs:__imp_LoadLibraryW
0x1800fdc6e  mov     [rbx+18h], rax
0x1800fdc72  test    rax, rax
0x1800fdc75  jz      short loc_1800FDC9F
0x1800fdc77  lea     rdx, aLocalenametolc; "LocaleNameToLCID"
0x1800fdc7e  mov     rcx, rax; hModule
0x1800fdc81  call    cs:__imp_GetProcAddress
0x1800fdc87  mov     rcx, [rbx+18h]; hModule
0x1800fdc8b  lea     rdx, aLcidtolocalena; "LCIDToLocaleName"
0x1800fdc92  mov     [rbx], rax
0x1800fdc95  call    cs:__imp_GetProcAddress
0x1800fdc9b  mov     [rbx+8], rax
0x1800fdc9f  xor     edx, edx; pUnkOuter
0x1800fdca1  mov     byte ptr [rbx+20h], 1
0x1800fdca5  lea     rax, [rbx+10h]
0x1800fdca9  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x1800fdcb0  mov     [rsp+38h+ppv], rax; ppv
0x1800fdcb5  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1800fdcbc  lea     r8d, [rdx+1]; dwClsContext
0x1800fdcc0  call    cs:__imp_CoCreateInstance
0x1800fdcc6  add     rsp, 30h
0x1800fdcca  pop     rbx
0x1800fdccb  retn
```
