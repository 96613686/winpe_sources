# CreateSearchItemFromAutoList(IAutoListDescription *,INamedPropertyStore *,_GUID const &,void * *)

- ea: `0x180029bb0`
- end: `0x180029c12`
- name: `?CreateSearchItemFromAutoList@@YAJPEAUIAutoListDescription@@PEAUINamedPropertyStore@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `int(struct IAutoListDescription *, struct INamedPropertyStore *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800319f8`
- `0x18003202c`
- `0x180038848`
- `0x18003a608`

## callees

- `0x180005460`
- `0x180029bb0`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180029bf3`
- `SHELL32!SHCreateItemFromIDList` at `0x180029bf3`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x180029bd8`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x180029bd8`

## pseudocode

```c
__int64 __fastcall CreateSearchItemFromAutoList(
        struct IAutoListDescription *a1,
        struct INamedPropertyStore *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v5; // ebx
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp+18h] BYREF

  *a4 = 0;
  pidl = 0;
  v5 = SHCreateSearchIDListFromAutoList(a1, 0, &pidl);
  if ( v5 >= 0 )
    v5 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a4);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029bb0  mov     rax, rsp
0x180029bb3  mov     [rax+8], rbx
0x180029bb7  mov     [rax+18h], r8
0x180029bbb  push    rdi
0x180029bbc  sub     rsp, 20h
0x180029bc0  lea     r8, [rax+18h]
0x180029bc4  mov     qword ptr [r9], 0
0x180029bcb  xor     edx, edx
0x180029bcd  mov     qword ptr [rax+18h], 0
0x180029bd5  mov     rdi, r9
0x180029bd8  call    cs:__imp_SHCreateSearchIDListFromAutoList
0x180029bde  mov     ebx, eax
0x180029be0  test    eax, eax
0x180029be2  js      short loc_180029BFB
0x180029be4  mov     rcx, [rsp+28h+pidl]; pidl
0x180029be9  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180029bf0  mov     r8, rdi; ppv
0x180029bf3  call    cs:__imp_SHCreateItemFromIDList
0x180029bf9  mov     ebx, eax
0x180029bfb  lea     rcx, [rsp+28h+pidl]; void *
0x180029c00  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180029c05  mov     eax, ebx
0x180029c07  mov     rbx, [rsp+28h+arg_0]
0x180029c0c  add     rsp, 20h
0x180029c10  pop     rdi
0x180029c11  retn
```
