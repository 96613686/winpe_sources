# BrowserToolThread::CreatePopupOnThread(IF12Platform *,HWND__ *,int,bool)

- ea: `0x180006440`
- end: `0x1800066ca`
- name: `?CreatePopupOnThread@BrowserToolThread@@QEAAJPEAUIF12Platform@@PEAUHWND__@@H_N@Z`
- size: `650`
- prototype: `__int64 __fastcall(BrowserToolThread *this, struct IF12Platform *, HWND, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180021764`

## callees

- `0x180003880`
- `0x1800045b4`
- `0x180006230`
- `0x180006440`
- `0x180035010`

## string_xrefs

- `0x180006557`: `pluginhost`
- `0x180006571`: `pluginhost`

## pseudocode

```c
__int64 __fastcall BrowserToolThread::CreatePopupOnThread(
        BrowserToolThread *this,
        struct IF12Platform *a2,
        HWND a3,
        int a4,
        char a5)
{
  unsigned int v9; // ebx
  wchar_t *v10; // rdx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  int v15; // [rsp+A0h] [rbp-31h]
  int v16; // [rsp+A8h] [rbp-29h]
  wchar_t *v17; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v18; // [rsp+C8h] [rbp-9h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-1h] BYREF
  __int64 v20; // [rsp+D8h] [rbp+7h] BYREF
  __int64 v21[8]; // [rsp+E0h] [rbp+Fh] BYREF

  v21[0] = 0;
  v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v20,
          (__int64)&String) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v20, &String, 0);
  v19 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v19,
          (__int64)&String) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v19, &String, 0);
  v18 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          (wchar_t **)&v18,
          (__int64)L"popupWindow.html") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v18, L"popupWindow.html", 16);
  v17 = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &v17,
          (__int64)L"pluginhost") )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v17, L"pluginhost", 10);
  v9 = BrowserToolThread::CreateBrowserToolOnThread(
         (unsigned int *)this,
         (__int64)a2,
         8u,
         (__int64 *)&v17,
         &v18,
         &v19,
         &v20,
         0,
         0,
         0,
         a3,
         0,
         v21,
         0,
         0,
         0,
         0,
         0,
         a5,
         -1,
         v15,
         v16,
         a4);
  v10 = v17 - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v17 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  v11 = (_QWORD *)(v18 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  v12 = (_QWORD *)(v19 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v19 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  v13 = (_QWORD *)(v20 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v20 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
  return v9;
}

```

## disassembly

```asm
0x180006440  push    rbp
0x180006442  push    rbx
0x180006443  push    rsi
0x180006444  push    rdi
0x180006445  push    r12
0x180006447  push    r14
0x180006449  lea     rbp, [rsp-27h]
0x18000644e  sub     rsp, 0F8h
0x180006455  mov     ebx, r9d
0x180006458  mov     rdi, r8
0x18000645b  mov     rsi, rdx
0x18000645e  mov     r14, rcx
0x180006461  mov     [rbp+4Fh+var_40], 0
0x180006469  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006470  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006477  mov     rax, [rax+18h]
0x18000647b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006480  add     rax, 18h
0x180006484  mov     [rbp+4Fh+var_48], rax
0x180006488  lea     r12, String
0x18000648f  mov     rdx, r12
0x180006492  lea     rcx, [rbp+4Fh+var_48]
0x180006496  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18000649b  test    al, al
0x18000649d  jnz     short loc_1800064AF
0x18000649f  xor     r8d, r8d
0x1800064a2  mov     rdx, r12
0x1800064a5  lea     rcx, [rbp+4Fh+var_48]
0x1800064a9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800064ae  nop
0x1800064af  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800064b6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800064bd  mov     rax, [rax+18h]
0x1800064c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c6  add     rax, 18h
0x1800064ca  mov     [rbp+4Fh+var_50], rax
0x1800064ce  mov     rdx, r12
0x1800064d1  lea     rcx, [rbp+4Fh+var_50]
0x1800064d5  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1800064da  test    al, al
0x1800064dc  jnz     short loc_1800064EE
0x1800064de  xor     r8d, r8d
0x1800064e1  mov     rdx, r12
0x1800064e4  lea     rcx, [rbp+4Fh+var_50]
0x1800064e8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800064ed  nop
0x1800064ee  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800064f5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800064fc  mov     rax, [rax+18h]
0x180006500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006505  add     rax, 18h
0x180006509  mov     [rbp+4Fh+var_58], rax
0x18000650d  lea     rdx, aPopupwindowHtm; "popupWindow.html"
0x180006514  lea     rcx, [rbp+4Fh+var_58]
0x180006518  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18000651d  test    al, al
0x18000651f  jnz     short loc_180006538
0x180006521  mov     r8d, 10h
0x180006527  lea     rdx, aPopupwindowHtm; "popupWindow.html"
0x18000652e  lea     rcx, [rbp+4Fh+var_58]
0x180006532  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006537  nop
0x180006538  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000653f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006546  mov     rax, [rax+18h]
0x18000654a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654f  add     rax, 18h
0x180006553  mov     [rbp+4Fh+var_60], rax
0x180006557  lea     rdx, aPluginhost; "pluginhost"
0x18000655e  lea     rcx, [rbp+4Fh+var_60]
0x180006562  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180006567  test    al, al
0x180006569  jnz     short loc_180006582
0x18000656b  mov     r8d, 0Ah
0x180006571  lea     rdx, aPluginhost; "pluginhost"
0x180006578  lea     rcx, [rbp+4Fh+var_60]
0x18000657c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180006581  nop
0x180006582  mov     [rsp+120h+var_70], ebx; int
0x180006589  or      r12d, 0FFFFFFFFh
0x18000658d  mov     [rsp+120h+var_88], r12d; int
0x180006595  mov     al, [rbp+4Fh+arg_20]
0x180006598  mov     [rsp+120h+var_90], al; char
0x18000659f  mov     [rsp+120h+var_98], 0; char
0x1800065a7  mov     [rsp+120h+var_A0], 0; char
0x1800065af  mov     [rsp+120h+var_A8], 0; char
0x1800065b4  mov     [rsp+120h+var_B0], 0; char
0x1800065b9  mov     [rsp+120h+var_B8], 0; char
0x1800065be  lea     rax, [rbp+4Fh+var_40]
0x1800065c2  mov     [rsp+120h+var_C0], rax; __int64
0x1800065c7  mov     [rsp+120h+var_C8], 0; int
0x1800065cf  mov     [rsp+120h+var_D0], rdi; HWND
0x1800065d4  mov     [rsp+120h+var_D8], 0; __int64
0x1800065dd  mov     [rsp+120h+var_E0], 0; __int64
0x1800065e6  mov     [rsp+120h+var_E8], 0; char
0x1800065eb  lea     rax, [rbp+4Fh+var_48]
0x1800065ef  mov     [rsp+120h+var_F0], rax; __int64
0x1800065f4  lea     rax, [rbp+4Fh+var_50]
0x1800065f8  mov     [rsp+120h+var_F8], rax; __int64
0x1800065fd  lea     rax, [rbp+4Fh+var_58]
0x180006601  mov     [rsp+120h+var_100], rax; __int64
0x180006606  lea     r9, [rbp+4Fh+var_60]
0x18000660a  lea     r8d, [r12+9]
0x18000660f  mov     rdx, rsi
0x180006612  mov     rcx, r14; unsigned int *
0x180006615  call    ?CreateBrowserToolOnThread@BrowserToolThread@@QEAAJPEAUIF12Platform@@W4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@222_NPEAUHWND__@@44KAEAV?$CComPtr@UIScriptHostFactory@@@5@3333331HHH@Z; BrowserToolThread::CreateBrowserToolOnThread(IF12Platform *,PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,HWND__ *,HWND__ *,HWND__ *,ulong,ATL::CComPtr<IScriptHostFactory> &,bool,bool,bool,bool,bool,bool,PluginId,int,int,int)
0x18000661a  mov     ebx, eax
0x18000661c  mov     rdx, [rbp+4Fh+var_60]
0x180006620  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180006624  mov     ecx, r12d
0x180006627  lock xadd [rdx+10h], ecx
0x18000662c  add     ecx, r12d
0x18000662f  test    ecx, ecx
0x180006631  jg      short loc_180006643
0x180006633  mov     rcx, [rdx]
0x180006636  mov     r8, [rcx]
0x180006639  mov     rax, [r8+8]
0x18000663d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006642  nop
0x180006643  mov     rdx, [rbp+4Fh+var_58]
0x180006647  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000664b  mov     eax, r12d
0x18000664e  lock xadd [rdx+10h], eax
0x180006653  add     eax, r12d
0x180006656  test    eax, eax
0x180006658  jg      short loc_18000666A
0x18000665a  mov     rcx, [rdx]
0x18000665d  mov     rax, [rcx]
0x180006660  mov     rax, [rax+8]
0x180006664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006669  nop
0x18000666a  mov     rdx, [rbp+4Fh+var_50]
0x18000666e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180006672  mov     eax, r12d
0x180006675  lock xadd [rdx+10h], eax
0x18000667a  add     eax, r12d
0x18000667d  test    eax, eax
0x18000667f  jg      short loc_180006691
0x180006681  mov     rcx, [rdx]
0x180006684  mov     rax, [rcx]
0x180006687  mov     rax, [rax+8]
0x18000668b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006690  nop
0x180006691  mov     rdx, [rbp+4Fh+var_48]
0x180006695  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180006699  mov     eax, r12d
0x18000669c  lock xadd [rdx+10h], eax
0x1800066a1  add     eax, r12d
0x1800066a4  test    eax, eax
0x1800066a6  jg      short loc_1800066B8
0x1800066a8  mov     rcx, [rdx]
0x1800066ab  mov     rax, [rcx]
0x1800066ae  mov     rax, [rax+8]
0x1800066b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b7  nop
0x1800066b8  mov     eax, ebx
0x1800066ba  add     rsp, 0F8h
0x1800066c1  pop     r14
0x1800066c3  pop     r12
0x1800066c5  pop     rdi
0x1800066c6  pop     rsi
0x1800066c7  pop     rbx
0x1800066c8  pop     rbp
0x1800066c9  retn
```
