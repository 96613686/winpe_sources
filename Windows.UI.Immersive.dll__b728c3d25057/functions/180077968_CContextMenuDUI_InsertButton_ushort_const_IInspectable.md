# CContextMenuDUI::_InsertButton(ushort const *,IInspectable *)

- ea: `0x180077968`
- end: `0x180077ad8`
- name: `?_InsertButton@CContextMenuDUI@@AEAAJPEBGPEAUIInspectable@@@Z`
- size: `368`
- prototype: `int(CContextMenuDUI *__hidden this, const unsigned __int16 *, struct IInspectable *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180077b94`

## callees

- `0x18000a910`
- `0x18006f9c4`
- `0x180077968`

## import_xrefs

- `PROPSYS!PropVariantToStringAlloc` at `0x180077a80`
- `PROPSYS!PropVariantToStringAlloc` at `0x180077a80`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x180077a41`
- `PROPSYS!__imp_WinRTPropertyValueToPropVariant` at `0x180077a41`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800779cc`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800779cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180077aa4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180077aa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800779bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077abb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800779bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077abb`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180077a91`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180077a91`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800779f1`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800779f1`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180077a16`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180077a16`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180077ab1`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180077ab1`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180077a08`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180077a08`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x1800779e4`
- `SHLWAPI!__imp_SHStripMneumonicW` at `0x1800779e4`

## pseudocode

```c
__int64 __fastcall CContextMenuDUI::_InsertButton(CContextMenuDUI *this, const unsigned __int16 *a2, IUnknown *a3)
{
  struct DirectUI::Element *v4; // r8
  int v7; // ebx
  HRESULT v8; // eax
  DirectUI::Element *v9; // rdi
  DirectUI::Element *v11; // [rsp+30h] [rbp-40h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h]
  __int64 v14; // [rsp+48h] [rbp-28h]
  PROPVARIANT ppropvar[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h]
  unsigned int v17; // [rsp+90h] [rbp+20h] BYREF
  LPWSTR ppwsz; // [rsp+A8h] [rbp+38h] BYREF

  v11 = 0;
  v4 = (struct DirectUI::Element *)*((_QWORD *)this + 13);
  v17 = 0;
  v7 = ContextMenu_ParserCreateElement<UIContextMenuButton>((__int64)this, (__int64)a2, v4, &v17, &v11);
  if ( v7 >= 0 )
  {
    ppwsz = 0;
    CoTaskMemFree(0);
    v8 = SHStrDupW(a2, &ppwsz);
    v9 = v11;
    v7 = v8;
    if ( v8 < 0
      || (SHStripMneumonicW(ppwsz), v7 = DirectUI::Element::SetContentString(v9, ppwsz), v7 < 0)
      || (v7 = DirectUI::Element::Add(*((DirectUI::Element **)this + 13), v9),
          DirectUI::Element::EndDefer(v9, v17),
          v7 < 0) )
    {
      DirectUI::Element::Destroy(v9, 1);
    }
    else if ( a3 )
    {
      *(_OWORD *)ppropvar = 0;
      v16 = 0;
      if ( WinRTPropertyValueToPropVariant(a3, ppropvar) >= 0 )
      {
        ppszOut = 0;
        v13 = 0;
        v14 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszOut);
        v13 = -1;
        v14 = -1;
        if ( PropVariantToStringAlloc(ppropvar, &ppszOut) >= 0 )
          DirectUI::Element::SetID(v9, ppszOut);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszOut);
      }
      PropVariantClear(ppropvar);
    }
    CoTaskMemFree(ppwsz);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180077968  mov     [rsp-18h+arg_8], rbx
0x18007796d  mov     [rsp-18h+arg_10], rsi
0x180077972  push    rbp
0x180077973  push    rdi
0x180077974  push    r14
0x180077976  mov     rbp, rsp
0x180077979  sub     rsp, 70h
0x18007797d  mov     rsi, r8
0x180077980  mov     [rbp+var_40], 0
0x180077988  mov     r8, [rcx+68h]
0x18007798c  lea     rax, [rbp+var_40]
0x180077990  lea     r9, [rbp+arg_0]
0x180077994  mov     [rsp+70h+var_50], rax
0x180077999  mov     rdi, rdx
0x18007799c  mov     [rbp+arg_0], 0
0x1800779a3  mov     r14, rcx
0x1800779a6  call    ??$ContextMenu_ParserCreateElement@VUIContextMenuButton@@@@YAJPEBGPEAVElement@DirectUI@@1PEAKPEAPEAVUIContextMenuButton@@@Z; ContextMenu_ParserCreateElement<UIContextMenuButton>(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,UIContextMenuButton * *)
0x1800779ab  mov     ebx, eax
0x1800779ad  test    eax, eax
0x1800779af  js      loc_180077AC1
0x1800779b5  xor     ecx, ecx; pv
0x1800779b7  mov     [rbp+ppwsz], 0
0x1800779bf  call    cs:__imp_CoTaskMemFree
0x1800779c5  lea     rdx, [rbp+ppwsz]; ppwsz
0x1800779c9  mov     rcx, rdi; psz
0x1800779cc  call    cs:__imp_SHStrDupW
0x1800779d2  mov     rdi, [rbp+var_40]
0x1800779d6  mov     ebx, eax
0x1800779d8  test    eax, eax
0x1800779da  js      loc_180077AAC
0x1800779e0  mov     rcx, [rbp+ppwsz]; pszMenu
0x1800779e4  call    cs:__imp_SHStripMneumonicW
0x1800779ea  mov     rdx, [rbp+ppwsz]
0x1800779ee  mov     rcx, rdi
0x1800779f1  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800779f7  mov     ebx, eax
0x1800779f9  test    eax, eax
0x1800779fb  js      loc_180077AAC
0x180077a01  mov     rcx, [r14+68h]
0x180077a05  mov     rdx, rdi
0x180077a08  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180077a0e  mov     edx, [rbp+arg_0]
0x180077a11  mov     rcx, rdi
0x180077a14  mov     ebx, eax
0x180077a16  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x180077a1c  test    ebx, ebx
0x180077a1e  js      loc_180077AAC
0x180077a24  test    rsi, rsi
0x180077a27  jz      loc_180077AB7
0x180077a2d  xorps   xmm0, xmm0
0x180077a30  lea     rdx, [rbp+ppropvar]; ppropvar
0x180077a34  xor     eax, eax
0x180077a36  mov     rcx, rsi; punkPropertyValue
0x180077a39  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180077a3d  mov     [rbp+var_10], rax
0x180077a41  call    cs:__imp_WinRTPropertyValueToPropVariant
0x180077a47  test    eax, eax
0x180077a49  js      short loc_180077AA0
0x180077a4b  lea     rcx, [rbp+ppszOut]
0x180077a4f  mov     [rbp+ppszOut], 0
0x180077a57  mov     [rbp+var_30], 0
0x180077a5f  mov     [rbp+var_28], 0
0x180077a67  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180077a6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077a70  lea     rdx, [rbp+ppszOut]; ppszOut
0x180077a74  lea     rcx, [rbp+ppropvar]; propvar
0x180077a78  mov     [rbp+var_30], rax
0x180077a7c  mov     [rbp+var_28], rax
0x180077a80  call    cs:__imp_PropVariantToStringAlloc
0x180077a86  test    eax, eax
0x180077a88  js      short loc_180077A97
0x180077a8a  mov     rdx, [rbp+ppszOut]
0x180077a8e  mov     rcx, rdi
0x180077a91  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x180077a97  lea     rcx, [rbp+ppszOut]
0x180077a9b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180077aa0  lea     rcx, [rbp+ppropvar]; pvar
0x180077aa4  call    cs:__imp_PropVariantClear
0x180077aaa  jmp     short loc_180077AB7
0x180077aac  mov     dl, 1
0x180077aae  mov     rcx, rdi
0x180077ab1  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180077ab7  mov     rcx, [rbp+ppwsz]; pv
0x180077abb  call    cs:__imp_CoTaskMemFree
0x180077ac1  lea     r11, [rsp+70h+var_s0]
0x180077ac6  mov     eax, ebx
0x180077ac8  mov     rbx, [r11+28h]
0x180077acc  mov     rsi, [r11+30h]
0x180077ad0  mov     rsp, r11
0x180077ad3  pop     r14
0x180077ad5  pop     rdi
0x180077ad6  pop     rbp
0x180077ad7  retn
```
