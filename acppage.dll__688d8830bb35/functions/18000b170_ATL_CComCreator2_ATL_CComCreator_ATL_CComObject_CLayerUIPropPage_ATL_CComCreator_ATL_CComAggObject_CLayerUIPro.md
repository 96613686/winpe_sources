# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CLayerUIPropPage>>,ATL::CComCreator<ATL::CComAggObject<CLayerUIPropPage>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b170`
- end: `0x18000b2d2`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCLayerUIPropPage@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCLayerUIPropPage@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000179c`
- `0x18000a684`
- `0x18000b170`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CLayerUIPropPage>>,ATL::CComCreator<ATL::CComAggObject<CLayerUIPropPage>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  CLayerUIPropPage *v7; // rax
  CLayerUIPropPage *v8; // rsi
  struct ATL::CAtlModule *v9; // rcx
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  _QWORD *v12; // rcx

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = (CLayerUIPropPage *)operator new(0x2B8u);
      v8 = v7;
      if ( v7 )
      {
        CLayerUIPropPage::CLayerUIPropPage(v7);
        *(_QWORD *)v8 = &ATL::CComObject<CLayerUIPropPage>::`vftable'{for `ILayerUIPropPage'};
        v9 = ATL::_pAtlModule;
        *((_QWORD *)v8 + 1) = &ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellExtInit'};
        *((_QWORD *)v8 + 2) = &ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellPropSheetExt'};
        (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
        v6 = (**(__int64 (__fastcall ***)(CLayerUIPropPage *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
          (*(void (__fastcall **)(CLayerUIPropPage *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v10 = operator new(0x2C8u);
  v11 = v10;
  if ( v10 )
  {
    v10[2] = 0;
    *(_QWORD *)v10 = &ATL::CComAggObject<CLayerUIPropPage>::`vftable';
    CLayerUIPropPage::CLayerUIPropPage((CLayerUIPropPage *)(v10 + 4));
    v12[3] = a1;
    v12[1] = &ATL::CComContainedObject<CLayerUIPropPage>::`vftable'{for `IShellExtInit'};
    *v12 = &ATL::CComContainedObject<CLayerUIPropPage>::`vftable'{for `ILayerUIPropPage'};
    v12[2] = &ATL::CComContainedObject<CLayerUIPropPage>::`vftable'{for `IShellPropSheetExt'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v11)(v11, a2, a3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000b170  push    rbx
0x18000b172  push    rbp
0x18000b173  push    rsi
0x18000b174  push    rdi
0x18000b175  push    r14
0x18000b177  sub     rsp, 20h
0x18000b17b  mov     rdi, r8
0x18000b17e  mov     r14, rdx
0x18000b181  mov     rbp, rcx
0x18000b184  test    rcx, rcx
0x18000b187  jnz     loc_18000B219
0x18000b18d  test    r8, r8
0x18000b190  jz      loc_18000B21E
0x18000b196  mov     [r8], rcx
0x18000b199  mov     ebx, 8007000Eh
0x18000b19e  mov     ecx, 2B8h; Size
0x18000b1a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b1a8  mov     rsi, rax
0x18000b1ab  test    rax, rax
0x18000b1ae  jz      loc_18000B2C5
0x18000b1b4  mov     rcx, rax; this
0x18000b1b7  call    ??0CLayerUIPropPage@@QEAA@XZ; CLayerUIPropPage::CLayerUIPropPage(void)
0x18000b1bc  lea     rcx, ??_7?$CComObject@VCLayerUIPropPage@@@ATL@@6BILayerUIPropPage@@@; const ATL::CComObject<CLayerUIPropPage>::`vftable'{for `ILayerUIPropPage'}
0x18000b1c3  mov     [rsi], rcx
0x18000b1c6  lea     rax, ??_7?$CComObject@VCLayerUIPropPage@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellExtInit'}
0x18000b1cd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b1d4  mov     [rsi+8], rax
0x18000b1d8  lea     rax, ??_7?$CComObject@VCLayerUIPropPage@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellPropSheetExt'}
0x18000b1df  mov     [rsi+10h], rax
0x18000b1e3  mov     rdx, [rcx]
0x18000b1e6  mov     rax, [rdx+8]
0x18000b1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ef  mov     rax, [rsi]
0x18000b1f2  mov     r8, rdi
0x18000b1f5  mov     rdx, r14
0x18000b1f8  mov     rcx, rsi
0x18000b1fb  mov     rax, [rax]
0x18000b1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b203  mov     ebx, eax
0x18000b205  test    eax, eax
0x18000b207  jz      loc_18000B2C5
0x18000b20d  mov     rcx, [rsi]
0x18000b210  mov     rax, [rcx+20h]
0x18000b214  jmp     loc_18000B2B8
0x18000b219  test    rdi, rdi
0x18000b21c  jnz     short loc_18000B228
0x18000b21e  mov     ebx, 80004003h
0x18000b223  jmp     loc_18000B2C5
0x18000b228  mov     ecx, 2C8h; Size
0x18000b22d  mov     qword ptr [r8], 0
0x18000b234  mov     ebx, 8007000Eh
0x18000b239  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b23e  mov     rsi, rax
0x18000b241  test    rax, rax
0x18000b244  jz      short loc_18000B2C5
0x18000b246  mov     dword ptr [rax+8], 0
0x18000b24d  lea     rcx, [rsi+10h]; this
0x18000b251  lea     rax, ??_7?$CComAggObject@VCLayerUIPropPage@@@ATL@@6B@; const ATL::CComAggObject<CLayerUIPropPage>::`vftable'
0x18000b258  mov     [rsi], rax
0x18000b25b  call    ??0CLayerUIPropPage@@QEAA@XZ; CLayerUIPropPage::CLayerUIPropPage(void)
0x18000b260  mov     [rcx+18h], rbp
0x18000b264  lea     rax, ??_7?$CComContainedObject@VCLayerUIPropPage@@@ATL@@6BIShellExtInit@@@; const ATL::CComContainedObject<CLayerUIPropPage>::`vftable'{for `IShellExtInit'}
0x18000b26b  mov     [rcx+8], rax
0x18000b26f  lea     r8, ??_7?$CComContainedObject@VCLayerUIPropPage@@@ATL@@6BILayerUIPropPage@@@; const ATL::CComContainedObject<CLayerUIPropPage>::`vftable'{for `ILayerUIPropPage'}
0x18000b276  mov     [rcx], r8
0x18000b279  lea     rax, ??_7?$CComContainedObject@VCLayerUIPropPage@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComContainedObject<CLayerUIPropPage>::`vftable'{for `IShellPropSheetExt'}
0x18000b280  mov     [rcx+10h], rax
0x18000b284  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b28b  mov     rax, [rcx]
0x18000b28e  mov     rax, [rax+8]
0x18000b292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b297  mov     rax, [rsi]
0x18000b29a  mov     r8, rdi
0x18000b29d  mov     rdx, r14
0x18000b2a0  mov     rcx, rsi
0x18000b2a3  mov     rax, [rax]
0x18000b2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ab  mov     ebx, eax
0x18000b2ad  test    eax, eax
0x18000b2af  jz      short loc_18000B2C5
0x18000b2b1  mov     rax, [rsi]
0x18000b2b4  mov     rax, [rax+18h]
0x18000b2b8  mov     edx, 1
0x18000b2bd  mov     rcx, rsi
0x18000b2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c5  mov     eax, ebx
0x18000b2c7  add     rsp, 20h
0x18000b2cb  pop     r14
0x18000b2cd  pop     rdi
0x18000b2ce  pop     rsi
0x18000b2cf  pop     rbp
0x18000b2d0  pop     rbx
0x18000b2d1  retn
```
