# CSyncFolderBase::OnViewDelegate(_GUID const &,IDataObject *)

- ea: `0x180042d04`
- end: `0x180042ebe`
- name: `?OnViewDelegate@CSyncFolderBase@@QEAAJAEBU_GUID@@PEAUIDataObject@@@Z`
- size: `442`
- prototype: `int(CSyncFolderBase *__hidden this, const struct _GUID *, struct IDataObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041cd0`

## callees

- `0x180042d04`
- `0x1800431d4`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHGetKnownFolderIDList` at `0x180042d65`
- `SHELL32!SHGetKnownFolderIDList` at `0x180042d65`
- `SHELL32!SHBindToObject` at `0x180042d99`
- `SHELL32!SHBindToObject` at `0x180042d99`
- `SHELL32!__imp_ILCombine` at `0x180042e06`
- `SHELL32!__imp_ILCombine` at `0x180042e06`
- `SHELL32!__imp_ILFree` at `0x180042e6d`
- `SHELL32!__imp_ILFree` at `0x180042e78`
- `SHELL32!__imp_ILFree` at `0x180042e94`
- `SHELL32!__imp_ILFree` at `0x180042e6d`
- `SHELL32!__imp_ILFree` at `0x180042e78`
- `SHELL32!__imp_ILFree` at `0x180042e94`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180042e34`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180042e34`

## pseudocode

```c
__int64 __fastcall CSyncFolderBase::OnViewDelegate(IUnknown **this, const struct _GUID *a2, struct IDataObject *a3)
{
  HRESULT FilterParseName; // ebx
  ITEMIDLIST *v5; // rdi
  IUnknown *v6; // rcx
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+58h] [rbp-A8h] BYREF
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v13[264]; // [rsp+70h] [rbp-90h] BYREF

  FilterParseName = CSyncFolderBase::_GetFilterParseName((CSyncFolderBase *)this, v13, (unsigned int)a3, a2, a3);
  if ( FilterParseName >= 0 )
  {
    ppidl = 0;
    FilterParseName = SHGetKnownFolderIDList(&FOLDERID_SyncManagerFolder, 0, 0, &ppidl);
    if ( FilterParseName >= 0 )
    {
      ppv = 0;
      FilterParseName = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
      if ( FilterParseName >= 0 )
      {
        v9 = 0;
        pidl2 = 0;
        FilterParseName = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, unsigned __int16 *, int *, LPCITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                            ppv,
                            0,
                            0,
                            v13,
                            &v9,
                            &pidl2,
                            0);
        if ( FilterParseName >= 0 )
        {
          v5 = ILCombine(ppidl, pidl2);
          if ( v5 )
          {
            v6 = this[1];
            ppvOut = 0;
            FilterParseName = IUnknown_QueryService(
                                v6,
                                &IID_IShellBrowser,
                                &GUID_000214e2_0000_0000_c000_000000000046,
                                &ppvOut);
            if ( FilterParseName >= 0 )
            {
              FilterParseName = (*(__int64 (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(
                                  ppvOut,
                                  v5,
                                  0);
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
            }
            ILFree(v5);
          }
          ILFree((LPITEMIDLIST)pidl2);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ILFree(ppidl);
    }
  }
  return (unsigned int)FilterParseName;
}

```

## disassembly

```asm
0x180042d04  mov     [rsp-8+arg_18], rbx
0x180042d09  push    rbp
0x180042d0a  push    rsi
0x180042d0b  push    rdi
0x180042d0c  lea     rbp, [rsp-190h]
0x180042d14  sub     rsp, 290h
0x180042d1b  mov     rax, cs:__security_cookie
0x180042d22  xor     rax, rsp
0x180042d25  mov     [rbp+1A0h+var_20], rax
0x180042d2c  mov     r9, rdx; struct _GUID *
0x180042d2f  mov     [rsp+2A0h+ppv], r8; struct IDataObject *
0x180042d34  lea     rdx, [rsp+2A0h+var_230]; unsigned __int16 *
0x180042d39  mov     rsi, rcx
0x180042d3c  call    ?_GetFilterParseName@CSyncFolderBase@@AEAAJPEAGIAEBU_GUID@@PEAUIDataObject@@@Z; CSyncFolderBase::_GetFilterParseName(ushort *,uint,_GUID const &,IDataObject *)
0x180042d41  mov     ebx, eax
0x180042d43  test    eax, eax
0x180042d45  js      loc_180042E9A
0x180042d4b  lea     r9, [rsp+2A0h+ppidl]; ppidl
0x180042d50  mov     [rsp+2A0h+ppidl], 0
0x180042d59  xor     r8d, r8d; hToken
0x180042d5c  lea     rcx, FOLDERID_SyncManagerFolder; rfid
0x180042d63  xor     edx, edx; dwFlags
0x180042d65  call    cs:__imp_SHGetKnownFolderIDList
0x180042d6b  mov     ebx, eax
0x180042d6d  test    eax, eax
0x180042d6f  js      loc_180042E9A
0x180042d75  mov     rdx, [rsp+2A0h+ppidl]; pidl
0x180042d7a  lea     rax, [rsp+2A0h+var_240]
0x180042d7f  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180042d86  mov     [rsp+2A0h+ppv], rax; ppv
0x180042d8b  xor     r8d, r8d; pbc
0x180042d8e  mov     [rsp+2A0h+var_240], 0
0x180042d97  xor     ecx, ecx; psf
0x180042d99  call    cs:__imp_SHBindToObject
0x180042d9f  mov     ebx, eax
0x180042da1  test    eax, eax
0x180042da3  js      loc_180042E8F
0x180042da9  mov     rcx, [rsp+2A0h+var_240]
0x180042dae  lea     rdx, [rsp+2A0h+pidl2]
0x180042db3  mov     [rsp+2A0h+var_258], 0
0x180042dbb  lea     r9, [rsp+2A0h+var_230]
0x180042dc0  mov     [rsp+2A0h+pidl2], 0
0x180042dc9  xor     r8d, r8d
0x180042dcc  mov     [rsp+2A0h+var_270], 0
0x180042dd5  mov     rax, [rcx]
0x180042dd8  mov     [rsp+2A0h+var_278], rdx
0x180042ddd  lea     rdx, [rsp+2A0h+var_258]
0x180042de2  mov     [rsp+2A0h+ppv], rdx
0x180042de7  xor     edx, edx
0x180042de9  mov     rax, [rax+18h]
0x180042ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042df2  mov     ebx, eax
0x180042df4  test    eax, eax
0x180042df6  js      loc_180042E7E
0x180042dfc  mov     rdx, [rsp+2A0h+pidl2]; pidl2
0x180042e01  mov     rcx, [rsp+2A0h+ppidl]; pidl1
0x180042e06  call    cs:__imp_ILCombine
0x180042e0c  mov     rdi, rax
0x180042e0f  test    rax, rax
0x180042e12  jz      short loc_180042E73
0x180042e14  mov     rcx, [rsi+8]; punk
0x180042e18  lea     r9, [rsp+2A0h+ppvOut]; ppvOut
0x180042e1d  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180042e24  mov     [rsp+2A0h+ppvOut], 0
0x180042e2d  lea     rdx, IID_IShellBrowser; guidService
0x180042e34  call    cs:__imp_IUnknown_QueryService
0x180042e3a  mov     ebx, eax
0x180042e3c  test    eax, eax
0x180042e3e  js      short loc_180042E6A
0x180042e40  mov     rcx, [rsp+2A0h+ppvOut]
0x180042e45  xor     r8d, r8d
0x180042e48  mov     rdx, rdi
0x180042e4b  mov     rax, [rcx]
0x180042e4e  mov     rax, [rax+58h]
0x180042e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e57  mov     rcx, [rsp+2A0h+ppvOut]
0x180042e5c  mov     ebx, eax
0x180042e5e  mov     rax, [rcx]
0x180042e61  mov     rax, [rax+10h]
0x180042e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e6a  mov     rcx, rdi; pidl
0x180042e6d  call    cs:__imp_ILFree
0x180042e73  mov     rcx, [rsp+2A0h+pidl2]; pidl
0x180042e78  call    cs:__imp_ILFree
0x180042e7e  mov     rcx, [rsp+2A0h+var_240]
0x180042e83  mov     rax, [rcx]
0x180042e86  mov     rax, [rax+10h]
0x180042e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e8f  mov     rcx, [rsp+2A0h+ppidl]; pidl
0x180042e94  call    cs:__imp_ILFree
0x180042e9a  mov     eax, ebx
0x180042e9c  mov     rcx, [rbp+1A0h+var_20]
0x180042ea3  xor     rcx, rsp; StackCookie
0x180042ea6  call    __security_check_cookie
0x180042eab  mov     rbx, [rsp+2A0h+arg_18]
0x180042eb3  add     rsp, 290h
0x180042eba  pop     rdi
0x180042ebb  pop     rsi
0x180042ebc  pop     rbp
0x180042ebd  retn
```
