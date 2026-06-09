# _CreateScopeItemForLocation(IShellItem *,ILocationDescription *,IShellItem * *)

- ea: `0x180032d54`
- end: `0x180032e53`
- name: `?_CreateScopeItemForLocation@@YAJPEAUIShellItem@@PEAUILocationDescription@@PEAPEAU1@@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct IShellItem *, struct ILocationDescription *, struct IShellItem **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031208`

## callees

- `0x18002fc80`
- `0x180032d54`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x180032e22`
- `SHELL32!SHCreateItemFromParsingName` at `0x180032e22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032ded`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032ded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032e2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032e2e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180032d88`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180032d88`

## string_xrefs

- `0x180032dd4`: `LibraryDescriptionParsingPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall _CreateScopeItemForLocation(
        struct IShellItem *a1,
        struct ILocationDescription *a2,
        struct IShellItem **a3)
{
  HRESULT v5; // ebx
  const unsigned __int16 *v6; // rcx
  PROPVARIANT pvar[4]; // [rsp+20h] [rbp-20h] BYREF
  void *ppv; // [rsp+68h] [rbp+28h] BYREF
  PCWSTR pszPath; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  ppv = 0;
  v5 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
  if ( v5 >= 0 )
  {
    memset(pvar, 0, 24);
    LOWORD(pvar[0]) = 31;
    v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PROPVARIANT *))a1->lpVtbl->GetDisplayName)(
           a1,
           2147844096LL,
           &pvar[1]);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(void *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
             ppv,
             L"LibraryDescriptionParsingPath",
             pvar);
      PropVariantClear(pvar);
      if ( v5 >= 0 )
      {
        pszPath = 0;
        v5 = SHGetParsingNameFromPropertyStore(v6, (struct INamedPropertyStore *)ppv, (unsigned __int16 **)&pszPath);
        if ( v5 >= 0 )
        {
          v5 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)a3);
          CoTaskMemFree((LPVOID)pszPath);
        }
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032d54  mov     [rsp-18h+arg_0], rbx
0x180032d59  mov     [rsp-18h+ppv], rdx
0x180032d5e  push    rbp
0x180032d5f  push    rsi
0x180032d60  push    rdi
0x180032d61  mov     rbp, rsp
0x180032d64  sub     rsp, 40h
0x180032d68  mov     rsi, rcx
0x180032d6b  mov     qword ptr [r8], 0
0x180032d72  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180032d79  mov     [rbp+ppv], 0
0x180032d81  lea     rdx, [rbp+ppv]; ppv
0x180032d85  mov     rdi, r8
0x180032d88  call    cs:__imp_PSCreateMemoryPropertyStore
0x180032d8e  mov     ebx, eax
0x180032d90  test    eax, eax
0x180032d92  js      loc_180032E44
0x180032d98  xor     eax, eax
0x180032d9a  lea     r8, [rbp+var_18]
0x180032d9e  mov     [rbp+var_10], rax
0x180032da2  xorps   xmm0, xmm0
0x180032da5  mov     eax, 1Fh
0x180032daa  mov     edx, 80058000h
0x180032daf  movups  xmmword ptr [rbp-20h], xmm0
0x180032db3  mov     word ptr [rbp+pvar], ax
0x180032db7  mov     rcx, rsi
0x180032dba  mov     rax, [rsi]
0x180032dbd  mov     rax, [rax+28h]
0x180032dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dc6  mov     ebx, eax
0x180032dc8  test    eax, eax
0x180032dca  js      short loc_180032E34
0x180032dcc  mov     rcx, [rbp+ppv]
0x180032dd0  lea     r8, [rbp+pvar]
0x180032dd4  lea     rdx, aLibrarydescrip; "LibraryDescriptionParsingPath"
0x180032ddb  mov     rax, [rcx]
0x180032dde  mov     rax, [rax+20h]
0x180032de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032de7  lea     rcx, [rbp+pvar]; pvar
0x180032deb  mov     ebx, eax
0x180032ded  call    cs:__imp_PropVariantClear
0x180032df3  test    ebx, ebx
0x180032df5  js      short loc_180032E34
0x180032df7  mov     rdx, [rbp+ppv]; struct INamedPropertyStore *
0x180032dfb  lea     r8, [rbp+pszPath]; unsigned __int16 **
0x180032dff  mov     [rbp+pszPath], 0
0x180032e07  call    ?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z; SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)
0x180032e0c  mov     ebx, eax
0x180032e0e  test    eax, eax
0x180032e10  js      short loc_180032E34
0x180032e12  mov     rcx, [rbp+pszPath]; pszPath
0x180032e16  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180032e1d  mov     r9, rdi; ppv
0x180032e20  xor     edx, edx; pbc
0x180032e22  call    cs:__imp_SHCreateItemFromParsingName
0x180032e28  mov     rcx, [rbp+pszPath]; pv
0x180032e2c  mov     ebx, eax
0x180032e2e  call    cs:__imp_CoTaskMemFree
0x180032e34  mov     rcx, [rbp+ppv]
0x180032e38  mov     rax, [rcx]
0x180032e3b  mov     rax, [rax+10h]
0x180032e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e44  mov     eax, ebx
0x180032e46  mov     rbx, [rsp+40h+arg_0]
0x180032e4b  add     rsp, 40h
0x180032e4f  pop     rdi
0x180032e50  pop     rsi
0x180032e51  pop     rbp
0x180032e52  retn
```
