# CreateSecuredHtmlDoc(IHTMLDocument2 * *)

- ea: `0x180009574`
- end: `0x1800099f1`
- name: `?CreateSecuredHtmlDoc@@YAJPEAPEAUIHTMLDocument2@@@Z`
- size: `1149`
- prototype: `__int64 __fastcall(struct IHTMLDocument2 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800078b0`
- `0x180009004`

## callees

- `0x180001184`
- `0x180009574`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800095db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800095db`

## pseudocode

```c
__int64 __fastcall CreateSecuredHtmlDoc(struct IHTMLDocument2 **a1)
{
  HRESULT v3; // ebx
  __int64 v4; // rcx
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  int v7; // esi
  __int64 v8; // rcx
  int v9; // eax
  struct IHTMLDocument2 *v10; // rax
  __int64 v11; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v12[4]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v13; // [rsp+90h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+30h] BYREF
  struct IHTMLDocument2 *v15; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+40h] BYREF

  ppv = 0;
  v15 = 0;
  v13 = 0;
  v11 = 0;
  v16 = 0;
  if ( !a1 )
    return 2147942487LL;
  v3 = CoCreateInstance(&CLSID_HTMLDocument, 0, 1u, &IID_IUnknown, &ppv);
  if ( v3 < 0 || (v3 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IOleObject, &v13), v3 < 0) )
  {
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v15 )
      ((void (__fastcall *)(struct IHTMLDocument2 *))v15->lpVtbl->Release)(v15);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v3;
  }
  v4 = v13;
  if ( !v13 )
  {
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v4 = v13;
    }
LABEL_42:
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v15 )
      ((void (__fastcall *)(struct IHTMLDocument2 *))v15->lpVtbl->Release)(v15);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 2147500034LL;
  }
  v5 = operator new(0x38u);
  v6 = v5;
  if ( !v5 )
  {
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v15 )
      ((void (__fastcall *)(struct IHTMLDocument2 *))v15->lpVtbl->Release)(v15);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 2147942414LL;
  }
  v5[10] = 1;
  *(_QWORD *)v5 = &HtmlDocForParsingSite::`vftable'{for `IOleClientSite'};
  *((_QWORD *)v5 + 6) = 0;
  *((_QWORD *)v5 + 1) = &HtmlDocForParsingSite::`vftable'{for `IServiceProvider'};
  *((_QWORD *)v5 + 2) = &HtmlDocForParsingSite::`vftable'{for `IDocHostShowUI'};
  *((_QWORD *)v5 + 3) = &HtmlDocForParsingSite::`vftable'{for `IDownloadNotify'};
  *((_QWORD *)v5 + 4) = &HtmlDocForParsingSite::`vftable'{for `IMarshal'};
  v7 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v13 + 24LL))(v13, v5);
  if ( v7 < 0
    || (v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IOleCommandTarget, &v11), v7 < 0)
    || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v6)(v6, &IID_IUnknown, &v16), v7 < 0)
    || (v12[2] = 0,
        v12[0] = 13,
        v12[1] = v16,
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, __int64, _QWORD *, _QWORD))(*(_QWORD *)v11 + 32LL))(
               v11,
               CGID_DownloadHost,
               0,
               2,
               v12,
               0),
        v7 < 0) )
  {
    v8 = v16;
LABEL_21:
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v15 )
      ((void (__fastcall *)(struct IHTMLDocument2 *))v15->lpVtbl->Release)(v15);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v7;
  }
  v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IHTMLDocument2 **))ppv)(
         ppv,
         &GUID_332c4425_26cb_11d0_b483_00c04fd90119,
         &v15);
  v8 = v16;
  v7 = v9;
  if ( v9 < 0 )
    goto LABEL_21;
  v10 = v15;
  if ( !v15 )
  {
    if ( v16 )
      (*(void (**)(void))(*(_QWORD *)v16 + 16LL))();
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v4 = v13;
    goto LABEL_42;
  }
  v15 = 0;
  *a1 = v10;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v15 )
    ((void (__fastcall *)(struct IHTMLDocument2 *))v15->lpVtbl->Release)(v15);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x180009574  push    rbp
0x180009576  push    rbx
0x180009577  push    rsi
0x180009578  push    rdi
0x180009579  mov     rbp, rsp
0x18000957c  sub     rsp, 68h
0x180009580  mov     [rbp+arg_8], 0
0x180009588  mov     rdi, rcx
0x18000958b  mov     [rbp+arg_10], 0
0x180009593  mov     [rbp+arg_0], 0
0x18000959b  mov     [rbp+var_28], 0
0x1800095a3  mov     [rbp+arg_18], 0
0x1800095ab  test    rcx, rcx
0x1800095ae  jnz     short loc_1800095BA
0x1800095b0  mov     eax, 80070057h
0x1800095b5  jmp     loc_1800099E8
0x1800095ba  lea     rax, [rbp+arg_8]
0x1800095be  mov     esi, 1
0x1800095c3  mov     r8d, esi; dwClsContext
0x1800095c6  mov     [rsp+68h+ppv], rax; ppv
0x1800095cb  lea     r9, IID_IUnknown; riid
0x1800095d2  xor     edx, edx; pUnkOuter
0x1800095d4  lea     rcx, CLSID_HTMLDocument; rclsid
0x1800095db  call    cs:__imp_CoCreateInstance
0x1800095e1  mov     ebx, eax
0x1800095e3  test    eax, eax
0x1800095e5  jns     short loc_180009657
0x1800095e7  mov     rcx, [rbp+arg_18]
0x1800095eb  test    rcx, rcx
0x1800095ee  jz      short loc_1800095FC
0x1800095f0  mov     rdx, [rcx]
0x1800095f3  mov     rax, [rdx+10h]
0x1800095f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095fc  mov     rcx, [rbp+var_28]
0x180009600  test    rcx, rcx
0x180009603  jz      short loc_180009611
0x180009605  mov     rax, [rcx]
0x180009608  mov     rax, [rax+10h]
0x18000960c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009611  mov     rcx, [rbp+arg_0]
0x180009615  test    rcx, rcx
0x180009618  jz      short loc_180009626
0x18000961a  mov     rax, [rcx]
0x18000961d  mov     rax, [rax+10h]
0x180009621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009626  mov     rcx, [rbp+arg_10]
0x18000962a  test    rcx, rcx
0x18000962d  jz      short loc_18000963B
0x18000962f  mov     rax, [rcx]
0x180009632  mov     rax, [rax+10h]
0x180009636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000963b  mov     rcx, [rbp+arg_8]
0x18000963f  test    rcx, rcx
0x180009642  jz      short loc_180009650
0x180009644  mov     rax, [rcx]
0x180009647  mov     rax, [rax+10h]
0x18000964b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009650  mov     eax, ebx
0x180009652  jmp     loc_1800099E8
0x180009657  mov     rcx, [rbp+arg_8]
0x18000965b  lea     r8, [rbp+arg_0]
0x18000965f  lea     rdx, IID_IOleObject
0x180009666  mov     rax, [rcx]
0x180009669  mov     rax, [rax]
0x18000966c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009671  mov     ebx, eax
0x180009673  test    eax, eax
0x180009675  js      loc_1800095E7
0x18000967b  mov     rcx, [rbp+arg_0]
0x18000967f  test    rcx, rcx
0x180009682  jnz     short loc_1800096B8
0x180009684  mov     rdx, [rbp+arg_18]
0x180009688  test    rdx, rdx
0x18000968b  jz      short loc_1800096A0
0x18000968d  mov     rax, [rdx]
0x180009690  mov     rcx, rdx
0x180009693  mov     rax, [rax+10h]
0x180009697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969c  mov     rcx, [rbp+arg_0]
0x1800096a0  mov     rdx, [rbp+var_28]
0x1800096a4  test    rdx, rdx
0x1800096a7  jz      loc_1800098B2
0x1800096ad  mov     rax, [rdx]
0x1800096b0  mov     rcx, rdx
0x1800096b3  jmp     loc_1800098A5
0x1800096b8  mov     ecx, 38h ; '8'; Size
0x1800096bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800096c2  mov     rbx, rax
0x1800096c5  test    rax, rax
0x1800096c8  jz      loc_18000997A
0x1800096ce  mov     [rbx+28h], esi
0x1800096d1  lea     rax, ??_7HtmlDocForParsingSite@@6BIOleClientSite@@@; const HtmlDocForParsingSite::`vftable'{for `IOleClientSite'}
0x1800096d8  mov     [rbx], rax
0x1800096db  mov     rdx, rbx
0x1800096de  mov     qword ptr [rbx+30h], 0
0x1800096e6  lea     rax, ??_7HtmlDocForParsingSite@@6BIServiceProvider@@@; const HtmlDocForParsingSite::`vftable'{for `IServiceProvider'}
0x1800096ed  mov     [rbx+8], rax
0x1800096f1  lea     rax, ??_7HtmlDocForParsingSite@@6BIDocHostShowUI@@@; const HtmlDocForParsingSite::`vftable'{for `IDocHostShowUI'}
0x1800096f8  mov     [rbx+10h], rax
0x1800096fc  lea     rax, ??_7HtmlDocForParsingSite@@6BIDownloadNotify@@@; const HtmlDocForParsingSite::`vftable'{for `IDownloadNotify'}
0x180009703  mov     [rbx+18h], rax
0x180009707  lea     rax, ??_7HtmlDocForParsingSite@@6BIMarshal@@@; const HtmlDocForParsingSite::`vftable'{for `IMarshal'}
0x18000970e  mov     [rbx+20h], rax
0x180009712  mov     rcx, [rbp+arg_0]
0x180009716  mov     rax, [rcx]
0x180009719  mov     rax, [rax+18h]
0x18000971d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009722  mov     esi, eax
0x180009724  test    eax, eax
0x180009726  jns     short loc_1800097A7
0x180009728  mov     rcx, [rbp+arg_18]
0x18000972c  test    rcx, rcx
0x18000972f  jz      short loc_18000973D
0x180009731  mov     rdx, [rcx]
0x180009734  mov     rax, [rdx+10h]
0x180009738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000973d  mov     rax, [rbx]
0x180009740  mov     rcx, rbx
0x180009743  mov     rax, [rax+10h]
0x180009747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000974c  mov     rcx, [rbp+var_28]
0x180009750  test    rcx, rcx
0x180009753  jz      short loc_180009761
0x180009755  mov     rax, [rcx]
0x180009758  mov     rax, [rax+10h]
0x18000975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009761  mov     rcx, [rbp+arg_0]
0x180009765  test    rcx, rcx
0x180009768  jz      short loc_180009776
0x18000976a  mov     rax, [rcx]
0x18000976d  mov     rax, [rax+10h]
0x180009771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009776  mov     rcx, [rbp+arg_10]
0x18000977a  test    rcx, rcx
0x18000977d  jz      short loc_18000978B
0x18000977f  mov     rax, [rcx]
0x180009782  mov     rax, [rax+10h]
0x180009786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978b  mov     rcx, [rbp+arg_8]
0x18000978f  test    rcx, rcx
0x180009792  jz      short loc_1800097A0
0x180009794  mov     rax, [rcx]
0x180009797  mov     rax, [rax+10h]
0x18000979b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097a0  mov     eax, esi
0x1800097a2  jmp     loc_1800099E8
0x1800097a7  mov     rcx, [rbp+arg_8]
0x1800097ab  lea     r8, [rbp+var_28]
0x1800097af  lea     rdx, IID_IOleCommandTarget
0x1800097b6  mov     rax, [rcx]
0x1800097b9  mov     rax, [rax]
0x1800097bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097c1  mov     esi, eax
0x1800097c3  test    eax, eax
0x1800097c5  js      loc_180009728
0x1800097cb  mov     rax, [rbx]
0x1800097ce  lea     r8, [rbp+arg_18]
0x1800097d2  lea     rdx, IID_IUnknown
0x1800097d9  mov     rcx, rbx
0x1800097dc  mov     rax, [rax]
0x1800097df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e4  mov     esi, eax
0x1800097e6  test    eax, eax
0x1800097e8  js      loc_180009728
0x1800097ee  mov     rcx, [rbp+var_28]
0x1800097f2  lea     rdx, [rbp+var_20]
0x1800097f6  xor     eax, eax
0x1800097f8  mov     [rsp+68h+var_40], 0
0x180009801  mov     [rbp+var_10], rax
0x180009805  xorps   xmm0, xmm0
0x180009808  movups  [rbp+var_20], xmm0
0x18000980c  mov     eax, 0Dh
0x180009811  mov     [rsp+68h+ppv], rdx
0x180009816  mov     word ptr [rbp+var_20], ax
0x18000981a  lea     rdx, CGID_DownloadHost
0x180009821  mov     rax, [rbp+arg_18]
0x180009825  mov     r9d, 2
0x18000982b  mov     qword ptr [rbp+var_20+8], rax
0x18000982f  xor     r8d, r8d
0x180009832  mov     rax, [rcx]
0x180009835  mov     rax, [rax+20h]
0x180009839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983e  mov     esi, eax
0x180009840  test    eax, eax
0x180009842  js      loc_180009728
0x180009848  mov     rcx, [rbp+arg_8]
0x18000984c  lea     r8, [rbp+arg_10]
0x180009850  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x180009857  mov     rax, [rcx]
0x18000985a  mov     rax, [rax]
0x18000985d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009862  mov     rcx, [rbp+arg_18]
0x180009866  mov     esi, eax
0x180009868  test    eax, eax
0x18000986a  js      loc_18000972C
0x180009870  mov     rax, [rbp+arg_10]
0x180009874  test    rax, rax
0x180009877  jnz     short loc_1800098F7
0x180009879  test    rcx, rcx
0x18000987c  jz      short loc_18000988A
0x18000987e  mov     rax, [rcx]
0x180009881  mov     rax, [rax+10h]
0x180009885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000988a  mov     rax, [rbx]
0x18000988d  mov     rcx, rbx
0x180009890  mov     rax, [rax+10h]
0x180009894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009899  mov     rcx, [rbp+var_28]
0x18000989d  test    rcx, rcx
0x1800098a0  jz      short loc_1800098AE
0x1800098a2  mov     rax, [rcx]
0x1800098a5  mov     rax, [rax+10h]
0x1800098a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ae  mov     rcx, [rbp+arg_0]
0x1800098b2  test    rcx, rcx
0x1800098b5  jz      short loc_1800098C3
0x1800098b7  mov     rax, [rcx]
0x1800098ba  mov     rax, [rax+10h]
0x1800098be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c3  mov     rcx, [rbp+arg_10]
0x1800098c7  test    rcx, rcx
0x1800098ca  jz      short loc_1800098D8
0x1800098cc  mov     rax, [rcx]
0x1800098cf  mov     rax, [rax+10h]
0x1800098d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d8  mov     rcx, [rbp+arg_8]
0x1800098dc  test    rcx, rcx
0x1800098df  jz      short loc_1800098ED
0x1800098e1  mov     rax, [rcx]
0x1800098e4  mov     rax, [rax+10h]
0x1800098e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ed  mov     eax, 80004002h
0x1800098f2  jmp     loc_1800099E8
0x1800098f7  mov     [rbp+arg_10], 0
0x1800098ff  mov     [rdi], rax
0x180009902  test    rcx, rcx
0x180009905  jz      short loc_180009913
0x180009907  mov     rax, [rcx]
0x18000990a  mov     rax, [rax+10h]
0x18000990e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009913  mov     rax, [rbx]
0x180009916  mov     rcx, rbx
0x180009919  mov     rax, [rax+10h]
0x18000991d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009922  mov     rcx, [rbp+var_28]
0x180009926  test    rcx, rcx
0x180009929  jz      short loc_180009937
0x18000992b  mov     rax, [rcx]
0x18000992e  mov     rax, [rax+10h]
0x180009932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009937  mov     rcx, [rbp+arg_0]
0x18000993b  test    rcx, rcx
0x18000993e  jz      short loc_18000994C
0x180009940  mov     rax, [rcx]
0x180009943  mov     rax, [rax+10h]
0x180009947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000994c  mov     rcx, [rbp+arg_10]
0x180009950  test    rcx, rcx
0x180009953  jz      short loc_180009961
0x180009955  mov     rax, [rcx]
0x180009958  mov     rax, [rax+10h]
0x18000995c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009961  mov     rcx, [rbp+arg_8]
0x180009965  test    rcx, rcx
0x180009968  jz      short loc_180009976
0x18000996a  mov     rax, [rcx]
0x18000996d  mov     rax, [rax+10h]
0x180009971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009976  xor     eax, eax
0x180009978  jmp     short loc_1800099E8
0x18000997a  mov     rcx, [rbp+arg_18]
0x18000997e  test    rcx, rcx
0x180009981  jz      short loc_18000998F
0x180009983  mov     rax, [rcx]
0x180009986  mov     rax, [rax+10h]
0x18000998a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998f  mov     rcx, [rbp+var_28]
0x180009993  test    rcx, rcx
0x180009996  jz      short loc_1800099A4
0x180009998  mov     rax, [rcx]
0x18000999b  mov     rax, [rax+10h]
0x18000999f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099a4  mov     rcx, [rbp+arg_0]
0x1800099a8  test    rcx, rcx
0x1800099ab  jz      short loc_1800099B9
0x1800099ad  mov     rax, [rcx]
0x1800099b0  mov     rax, [rax+10h]
0x1800099b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099b9  mov     rcx, [rbp+arg_10]
0x1800099bd  test    rcx, rcx
0x1800099c0  jz      short loc_1800099CE
0x1800099c2  mov     rax, [rcx]
0x1800099c5  mov     rax, [rax+10h]
0x1800099c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ce  mov     rcx, [rbp+arg_8]
0x1800099d2  test    rcx, rcx
0x1800099d5  jz      short loc_1800099E3
0x1800099d7  mov     rax, [rcx]
0x1800099da  mov     rax, [rax+10h]
0x1800099de  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
