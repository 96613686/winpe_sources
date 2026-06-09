# CStartMenuControlPanelResultSetManager::_AddShellFolderStringToScope(IScope *,ushort const *,ushort const *)

- ea: `0x1800313ac`
- end: `0x1800314a9`
- name: `?_AddShellFolderStringToScope@CStartMenuControlPanelResultSetManager@@AEAAJPEAUIScope@@PEBG1@Z`
- size: `253`
- prototype: `__int64 __fastcall(CStartMenuControlPanelResultSetManager *__hidden this, struct IScope *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800319f8`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x18002d880`
- `0x1800313ac`
- `0x180051010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x1800313eb`
- `SHELL32!SHParseDisplayName` at `0x1800313eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031421`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x180031460`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromIDList` at `0x180031460`

## pseudocode

```c
__int64 __fastcall CStartMenuControlPanelResultSetManager::_AddShellFolderStringToScope(
        CStartMenuControlPanelResultSetManager *this,
        struct IScope *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rdx
  HRESULT v7; // edi
  LPITEMIDLIST v8; // rcx
  ITEMIDLIST *v9; // rbx
  LPITEMIDLIST v10; // rcx
  CStartMenuControlPanelResultSetManager *v12; // [rsp+50h] [rbp+20h] BYREF
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp+30h] BYREF

  v12 = this;
  ppidl = 0;
  v7 = SHParseDisplayName(L"shell:::{ED7BA470-8E54-465E-825C-99712043E01C}", 0, &ppidl, 0, 0);
  if ( v7 >= 0 )
  {
    if ( a4 && *a4 )
    {
      v8 = ppidl;
      ppidl = 0;
      v9 = (ITEMIDLIST *)ILAppendHiddenStringW(v8, v6, a4);
      v10 = ppidl;
      ppidl = 0;
      CoTaskMemFree(v10);
      ppidl = v9;
    }
    else
    {
      v9 = ppidl;
    }
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v12);
    v7 = SHCreateScopeItemFromIDList(v9, 1, 2, 13, &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0, &v12);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(struct IScope *, CStartMenuControlPanelResultSetManager *))(*(_QWORD *)a2 + 24LL))(
             a2,
             v12);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v12);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppidl);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800313ac  mov     rax, rsp
0x1800313af  mov     [rax+10h], rbx
0x1800313b3  mov     [rax+20h], rsi
0x1800313b7  mov     [rax+18h], r8
0x1800313bb  mov     [rax+8], rcx
0x1800313bf  push    rbp
0x1800313c0  push    rdi
0x1800313c1  push    r14
0x1800313c3  mov     rbp, rsp
0x1800313c6  sub     rsp, 30h
0x1800313ca  mov     rbx, r9
0x1800313cd  mov     rsi, rdx
0x1800313d0  xor     r14d, r14d
0x1800313d3  mov     [rbp+ppidl], r14
0x1800313d7  mov     [rax-28h], r14
0x1800313db  xor     r9d, r9d; sfgaoIn
0x1800313de  lea     r8, [rbp+ppidl]; ppidl
0x1800313e2  xor     edx, edx; pbc
0x1800313e4  lea     rcx, aShellEd7ba4708; "shell:::{ED7BA470-8E54-465E-825C-997120"...
0x1800313eb  call    cs:__imp_SHParseDisplayName
0x1800313f1  mov     edi, eax
0x1800313f3  test    eax, eax
0x1800313f5  js      loc_18003148B
0x1800313fb  test    rbx, rbx
0x1800313fe  jz      short loc_18003142D
0x180031400  cmp     [rbx], r14w
0x180031404  jz      short loc_18003142D
0x180031406  mov     rcx, [rbp+ppidl]
0x18003140a  mov     [rbp+ppidl], r14
0x18003140e  mov     r8, rbx
0x180031411  call    ?ILAppendHiddenStringW@@YAPEAU_ITEMIDLIST_RELATIVE@@PEAU1@W4IDLHID@@PEBG@Z; ILAppendHiddenStringW(_ITEMIDLIST_RELATIVE *,IDLHID,ushort const *)
0x180031416  mov     rbx, rax
0x180031419  mov     rcx, [rbp+ppidl]; pv
0x18003141d  mov     [rbp+ppidl], r14
0x180031421  call    cs:__imp_CoTaskMemFree
0x180031427  mov     [rbp+ppidl], rbx
0x18003142b  jmp     short loc_180031431
0x18003142d  mov     rbx, [rbp+ppidl]
0x180031431  lea     rcx, [rbp+arg_0]; void *
0x180031435  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003143a  nop
0x18003143b  lea     rax, [rbp+arg_0]
0x18003143f  mov     [rsp+30h+var_8], rax
0x180031444  lea     rax, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18003144b  mov     [rsp+30h+var_10], rax
0x180031450  mov     edx, 1
0x180031455  lea     r9d, [rdx+0Ch]
0x180031459  lea     r8d, [rdx+1]
0x18003145d  mov     rcx, rbx
0x180031460  call    cs:__imp_SHCreateScopeItemFromIDList
0x180031466  mov     edi, eax
0x180031468  test    eax, eax
0x18003146a  js      short loc_180031481
0x18003146c  mov     rax, [rsi]
0x18003146f  mov     rdx, [rbp+arg_0]
0x180031473  mov     rcx, rsi
0x180031476  mov     rax, [rax+18h]
0x18003147a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003147f  mov     edi, eax
0x180031481  lea     rcx, [rbp+arg_0]
0x180031485  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003148a  nop
0x18003148b  lea     rcx, [rbp+ppidl]; void *
0x18003148f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180031494  mov     eax, edi
0x180031496  mov     rbx, [rsp+30h+arg_8]
0x18003149b  mov     rsi, [rsp+30h+arg_18]
0x1800314a0  add     rsp, 30h
0x1800314a4  pop     r14
0x1800314a6  pop     rdi
0x1800314a7  pop     rbp
0x1800314a8  retn
```
