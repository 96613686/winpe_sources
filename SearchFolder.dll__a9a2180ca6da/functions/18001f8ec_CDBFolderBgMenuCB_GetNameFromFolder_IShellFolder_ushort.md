# CDBFolderBgMenuCB::_GetNameFromFolder(IShellFolder *,ushort * *)

- ea: `0x18001f8ec`
- end: `0x18001f988`
- name: `?_GetNameFromFolder@CDBFolderBgMenuCB@@AEAAJPEAUIShellFolder@@PEAPEAG@Z`
- size: `156`
- prototype: `__int64 __fastcall(WCHAR *this, IUnknown *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e834`

## callees

- `0x180014254`
- `0x18001f8ec`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x18001f913`
- `SHELL32!SHGetIDListFromObject` at `0x18001f913`
- `SHELL32!__imp_ILFree` at `0x18001f970`
- `SHELL32!__imp_ILFree` at `0x18001f970`
- `SHELL32!__imp_PathCleanupSpec` at `0x18001f940`
- `SHELL32!__imp_PathCleanupSpec` at `0x18001f940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f965`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f965`

## pseudocode

```c
__int64 __fastcall CDBFolderBgMenuCB::_GetNameFromFolder(WCHAR *this, IUnknown *a2, unsigned __int16 **a3)
{
  struct IShellFolder *v4; // rcx
  HRESULT v5; // ebx
  unsigned int v6; // r8d
  int v7; // eax
  PWSTR v8; // rcx
  PWSTR pszSpec; // [rsp+30h] [rbp+8h] BYREF
  LPITEMIDLIST pidl; // [rsp+40h] [rbp+18h] BYREF

  pszSpec = this;
  *a3 = 0;
  pidl = 0;
  v5 = SHGetIDListFromObject(a2, &pidl);
  if ( v5 >= 0 )
  {
    pszSpec = 0;
    v5 = DisplayNameOfAsString(v4, (const struct _ITEMIDLIST_RELATIVE *)pidl, v6, &pszSpec);
    if ( v5 >= 0 )
    {
      v7 = PathCleanupSpec(0, pszSpec);
      v8 = pszSpec;
      if ( v7 >= 0 && *pszSpec )
      {
        *a3 = pszSpec;
        v8 = 0;
        pszSpec = 0;
      }
      else
      {
        v5 = -2147467259;
      }
      CoTaskMemFree(v8);
    }
    ILFree(pidl);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f8ec  mov     rax, rsp
0x18001f8ef  mov     [rax+10h], rbx
0x18001f8f3  mov     [rax+20h], rsi
0x18001f8f7  mov     [rax+8], rcx
0x18001f8fb  push    rdi
0x18001f8fc  sub     rsp, 20h
0x18001f900  mov     rcx, rdx; punk
0x18001f903  xor     esi, esi
0x18001f905  lea     rdx, [rax+18h]; ppidl
0x18001f909  mov     [r8], rsi
0x18001f90c  mov     [rax+18h], rsi
0x18001f910  mov     rdi, r8
0x18001f913  call    cs:__imp_SHGetIDListFromObject
0x18001f919  mov     ebx, eax
0x18001f91b  test    eax, eax
0x18001f91d  js      short loc_18001F976
0x18001f91f  mov     rdx, [rsp+28h+pidl]; struct _ITEMIDLIST_RELATIVE *
0x18001f924  lea     r9, [rsp+28h+pszSpec]; unsigned __int16 **
0x18001f929  mov     [rsp+28h+pszSpec], rsi
0x18001f92e  call    ?DisplayNameOfAsString@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@KPEAPEAG@Z; DisplayNameOfAsString(IShellFolder *,_ITEMIDLIST_RELATIVE const *,ulong,ushort * *)
0x18001f933  mov     ebx, eax
0x18001f935  test    eax, eax
0x18001f937  js      short loc_18001F96B
0x18001f939  mov     rdx, [rsp+28h+pszSpec]; pszSpec
0x18001f93e  xor     ecx, ecx; pszDir
0x18001f940  call    cs:__imp_PathCleanupSpec
0x18001f946  mov     rcx, [rsp+28h+pszSpec]; pv
0x18001f94b  test    eax, eax
0x18001f94d  js      short loc_18001F960
0x18001f94f  cmp     [rcx], si
0x18001f952  jz      short loc_18001F960
0x18001f954  mov     [rdi], rcx
0x18001f957  mov     ecx, esi
0x18001f959  mov     [rsp+28h+pszSpec], rcx
0x18001f95e  jmp     short loc_18001F965
0x18001f960  mov     ebx, 80004005h
0x18001f965  call    cs:__imp_CoTaskMemFree
0x18001f96b  mov     rcx, [rsp+28h+pidl]; pidl
0x18001f970  call    cs:__imp_ILFree
0x18001f976  mov     rsi, [rsp+28h+arg_18]
0x18001f97b  mov     eax, ebx
0x18001f97d  mov     rbx, [rsp+28h+arg_8]
0x18001f982  add     rsp, 20h
0x18001f986  pop     rdi
0x18001f987  retn
```
