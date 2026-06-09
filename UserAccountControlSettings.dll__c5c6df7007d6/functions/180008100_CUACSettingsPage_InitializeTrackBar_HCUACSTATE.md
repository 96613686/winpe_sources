# CUACSettingsPage::_InitializeTrackBar(HCUACSTATE)

- ea: `0x180008100`
- end: `0x180008553`
- name: `?_InitializeTrackBar@CUACSettingsPage@@AEAAXW4HCUACSTATE@@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000751c`

## callees

- `0x180004a10`
- `0x180004cac`
- `0x1800072ac`
- `0x180007358`
- `0x1800073a8`
- `0x1800074d8`
- `0x180008100`
- `0x1800088dc`
- `0x18000890c`
- `0x180009800`
- `0x180009930`
- `0x18000b710`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800083b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000841b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000841b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000822c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000826e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800082da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000831c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000835e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000822c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000826e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800082da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000831c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000835e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800084e2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008519`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800084e2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008519`
- `DUI70!StrToID` at `0x1800084d6`
- `DUI70!StrToID` at `0x18000850d`
- `DUI70!StrToID` at `0x1800084d6`
- `DUI70!StrToID` at `0x18000850d`
- `DUI70!?SetThumbPosition@CCTrackBar@DirectUI@@QEAAJH@Z` at `0x180008139`
- `DUI70!?SetThumbPosition@CCTrackBar@DirectUI@@QEAAJH@Z` at `0x180008139`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18000814f`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18000814f`

## pseudocode

```c
__int64 __fastcall CUACSettingsPage::_InitializeTrackBar(__int64 a1, int a2)
{
  DirectUI::CCTrackBar *v2; // r13
  HLOCAL *p_hMem; // rbx
  __int64 v5; // rdi
  int v6; // r8d
  int v7; // r9d
  HLOCAL v8; // rbx
  int v9; // r8d
  int v10; // r9d
  HLOCAL v11; // rbx
  int v12; // r8d
  int v13; // r9d
  HLOCAL v14; // rbx
  int v15; // r8d
  int v16; // r9d
  HLOCAL v17; // rbx
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  HLOCAL v21; // rbx
  int v22; // r8d
  int v23; // r9d
  HLOCAL v24; // rbx
  HLOCAL v25; // rbx
  void *v26; // rbx
  HLOCAL v27; // rdi
  HLOCAL v28; // rsi
  HLOCAL v29; // r15
  HLOCAL v30; // r12
  __int64 v31; // rcx
  LPVOID v32; // rax
  __int64 v33; // rsi
  LPVOID v34; // rbx
  void (__fastcall *v35)(__int64, __int64, __int64, _QWORD, LPVOID *, LPVOID); // rdi
  __int64 v36; // rax
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // r8
  void (*v39)(void *); // r9
  DirectUI::Element *v40; // rbx
  const wchar_t *v41; // rcx
  unsigned __int16 v42; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::Element *v44; // rbx
  const wchar_t *v45; // rcx
  unsigned __int16 v46; // ax
  struct DirectUI::Element *v47; // rax
  int ppv; // [rsp+28h] [rbp-49h]
  int ppva; // [rsp+28h] [rbp-49h]
  int ppvb; // [rsp+28h] [rbp-49h]
  int ppvc; // [rsp+28h] [rbp-49h]
  int ppvd; // [rsp+28h] [rbp-49h]
  int ppve; // [rsp+28h] [rbp-49h]
  LPVOID v55[2]; // [rsp+48h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-11h] BYREF
  HLOCAL Src; // [rsp+68h] [rbp-9h] BYREF
  HLOCAL v59; // [rsp+70h] [rbp-1h] BYREF
  HLOCAL v60; // [rsp+78h] [rbp+7h] BYREF

  v2 = *(DirectUI::CCTrackBar **)(a1 + 48);
  DirectUI::CCTrackBar::SetThumbPosition(v2, a2);
  if ( !*(_BYTE *)(a1 + 24) )
  {
    DirectUI::Element::AddListener(*(DirectUI::Element **)(a1 + 48), (struct DirectUI::IElementListener *)a1);
    *(_BYTE *)(a1 + 24) = 1;
  }
  if ( !*(_QWORD *)(a1 + 176) )
  {
    pv = 0;
    p_hMem = &hMem;
    v5 = 4;
    do
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(p_hMem++);
      --v5;
    }
    while ( v5 );
    v8 = hMem;
    if ( *(_DWORD *)(a1 + 144) )
    {
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      hMem = 0;
      TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 208, v6, v7, ppv, &hMem);
      v11 = Src;
      if ( Src )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v11);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      Src = 0;
      TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 209, v9, v10, ppva, &Src);
      v14 = v59;
      if ( v59 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      v59 = 0;
      TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 210, v12, v13, ppvb, &v59);
      v17 = v60;
      if ( v60 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v17);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      v18 = 211;
    }
    else
    {
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      hMem = 0;
      TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 212, v6, v7, ppv, &hMem);
      v21 = Src;
      if ( Src )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v21);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      Src = 0;
      TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 213, v19, v20, ppvd, &Src);
      v24 = v59;
      if ( v59 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v24);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      v59 = 0;
      TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, 214, v22, v23, ppve, &v59);
      v25 = v60;
      if ( v60 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v55);
        LocalFree(v25);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
      }
      v18 = 215;
    }
    v60 = 0;
    TResourceStringAllocCopyEx<unsigned short *>((int)g_hinst, v18, v15, v16, ppvc, &v60);
    v26 = pv;
    v27 = v60;
    v28 = v59;
    v29 = Src;
    v30 = hMem;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v55);
      CoTaskMemFree(v26);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
    }
    pv = 0;
    ResourceStringCoAllocFormatMessage(g_hinst, 216, &pv, v30, v29, v28, v27);
    v55[0] = 0;
    wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::reset(v55);
    CoCreateInstance(&CLSID_AccPropServices, 0, 1u, &GUID_6e26e776_04f0_495d_80e4_3330352e3169, v55);
    v31 = *(_QWORD *)(a1 + 176);
    v32 = v55[0];
    v55[0] = 0;
    *(_QWORD *)(a1 + 176) = v32;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::~com_ptr_t<IAccPropServices,wil::err_returncode_policy>(v55);
    v33 = *(_QWORD *)(a1 + 176);
    v34 = pv;
    v35 = *(void (__fastcall **)(__int64, __int64, __int64, _QWORD, LPVOID *, LPVOID))(*(_QWORD *)v33 + 56LL);
    v36 = (*(__int64 (__fastcall **)(DirectUI::CCTrackBar *))(*(_QWORD *)v2 + 360LL))(v2);
    *(GUID *)v55 = PROPID_ACC_VALUEMAP;
    v35(v33, v36, 4294967292LL, 0, v55, v34);
    `vector destructor iterator'(&hMem, v37, v38, v39);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  }
  v40 = *(DirectUI::Element **)(a1 + 40);
  v41 = L"admin_default_tickmark_left";
  if ( !*(_DWORD *)(a1 + 144) )
    v41 = L"user_default_tickmark_left";
  v42 = StrToID(v41);
  Descendent = DirectUI::Element::FindDescendent(v40, v42);
  CUACSettingsPage::s_SetDefaultTickMark(Descendent);
  v44 = *(DirectUI::Element **)(a1 + 40);
  v45 = L"admin_default_tickmark_right";
  if ( !*(_DWORD *)(a1 + 144) )
    v45 = L"user_default_tickmark_right";
  v46 = StrToID(v45);
  v47 = DirectUI::Element::FindDescendent(v44, v46);
  return CUACSettingsPage::s_SetDefaultTickMark(v47);
}

```

## disassembly

```asm
0x180008100  mov     rax, rsp
0x180008103  mov     [rax+18h], rbx
0x180008107  push    rbp
0x180008108  push    rsi
0x180008109  push    rdi
0x18000810a  push    r12
0x18000810c  push    r13
0x18000810e  push    r14
0x180008110  push    r15
0x180008112  lea     rbp, [rax-5Fh]
0x180008116  sub     rsp, 90h
0x18000811d  movaps  xmmword ptr [rax-48h], xmm6
0x180008121  mov     rax, cs:__security_cookie
0x180008128  xor     rax, rsp
0x18000812b  mov     [rbp+57h+var_48], rax
0x18000812f  mov     r13, [rcx+30h]
0x180008133  mov     r14, rcx
0x180008136  mov     rcx, r13
0x180008139  call    cs:__imp_?SetThumbPosition@CCTrackBar@DirectUI@@QEAAJH@Z; DirectUI::CCTrackBar::SetThumbPosition(int)
0x18000813f  xor     r15d, r15d
0x180008142  cmp     [r14+18h], r15b
0x180008146  jnz     short loc_18000815A
0x180008148  mov     rcx, [r14+30h]
0x18000814c  mov     rdx, r14
0x18000814f  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180008155  mov     byte ptr [r14+18h], 1
0x18000815a  cmp     [r14+0B0h], r15
0x180008161  jnz     loc_1800084B9
0x180008167  mov     [rbp+57h+pv], r15
0x18000816b  lea     rbx, [rbp+57h+hMem]
0x18000816f  mov     edi, 4
0x180008174  mov     rcx, rbx
0x180008177  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000817c  add     rbx, 8
0x180008180  sub     rdi, 1
0x180008184  jnz     short loc_180008174
0x180008186  mov     rbx, [rbp+57h+hMem]
0x18000818a  cmp     [r14+90h], r15d
0x180008191  jz      loc_180008287
0x180008197  test    rbx, rbx
0x18000819a  jz      short loc_1800081B7
0x18000819c  lea     rcx, [rbp+57h+var_80]; this
0x1800081a0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800081a5  mov     rcx, rbx; hMem
0x1800081a8  call    cs:__imp_LocalFree
0x1800081ae  lea     rcx, [rbp+57h+var_80]; this
0x1800081b2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800081b7  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x1800081be  lea     rax, [rbp+57h+hMem]
0x1800081c2  mov     edx, 0D0h; int
0x1800081c7  mov     [rsp+0C0h+Src], rax; Src
0x1800081cc  mov     [rbp+57h+hMem], r15
0x1800081d0  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800081d5  mov     rbx, [rbp+57h+var_60]
0x1800081d9  test    rbx, rbx
0x1800081dc  jz      short loc_1800081F9
0x1800081de  lea     rcx, [rbp+57h+var_80]; this
0x1800081e2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800081e7  mov     rcx, rbx; hMem
0x1800081ea  call    cs:__imp_LocalFree
0x1800081f0  lea     rcx, [rbp+57h+var_80]; this
0x1800081f4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800081f9  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x180008200  lea     rax, [rbp+57h+var_60]
0x180008204  mov     edx, 0D1h; int
0x180008209  mov     [rsp+0C0h+Src], rax; Src
0x18000820e  mov     [rbp+57h+var_60], r15
0x180008212  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008217  mov     rbx, [rbp+57h+var_58]
0x18000821b  test    rbx, rbx
0x18000821e  jz      short loc_18000823B
0x180008220  lea     rcx, [rbp+57h+var_80]; this
0x180008224  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008229  mov     rcx, rbx; hMem
0x18000822c  call    cs:__imp_LocalFree
0x180008232  lea     rcx, [rbp+57h+var_80]; this
0x180008236  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000823b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x180008242  lea     rax, [rbp+57h+var_58]
0x180008246  mov     edx, 0D2h; int
0x18000824b  mov     [rsp+0C0h+Src], rax; Src
0x180008250  mov     [rbp+57h+var_58], r15
0x180008254  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008259  mov     rbx, [rbp+57h+var_50]
0x18000825d  test    rbx, rbx
0x180008260  jz      short loc_18000827D
0x180008262  lea     rcx, [rbp+57h+var_80]; this
0x180008266  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000826b  mov     rcx, rbx; hMem
0x18000826e  call    cs:__imp_LocalFree
0x180008274  lea     rcx, [rbp+57h+var_80]; this
0x180008278  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000827d  mov     edx, 0D3h
0x180008282  jmp     loc_180008372
0x180008287  test    rbx, rbx
0x18000828a  jz      short loc_1800082A7
0x18000828c  lea     rcx, [rbp+57h+var_80]; this
0x180008290  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008295  mov     rcx, rbx; hMem
0x180008298  call    cs:__imp_LocalFree
0x18000829e  lea     rcx, [rbp+57h+var_80]; this
0x1800082a2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800082a7  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x1800082ae  lea     rax, [rbp+57h+hMem]
0x1800082b2  mov     edx, 0D4h; int
0x1800082b7  mov     [rsp+0C0h+Src], rax; Src
0x1800082bc  mov     [rbp+57h+hMem], r15
0x1800082c0  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800082c5  mov     rbx, [rbp+57h+var_60]
0x1800082c9  test    rbx, rbx
0x1800082cc  jz      short loc_1800082E9
0x1800082ce  lea     rcx, [rbp+57h+var_80]; this
0x1800082d2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800082d7  mov     rcx, rbx; hMem
0x1800082da  call    cs:__imp_LocalFree
0x1800082e0  lea     rcx, [rbp+57h+var_80]; this
0x1800082e4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800082e9  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x1800082f0  lea     rax, [rbp+57h+var_60]
0x1800082f4  mov     edx, 0D5h; int
0x1800082f9  mov     [rsp+0C0h+Src], rax; Src
0x1800082fe  mov     [rbp+57h+var_60], r15
0x180008302  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008307  mov     rbx, [rbp+57h+var_58]
0x18000830b  test    rbx, rbx
0x18000830e  jz      short loc_18000832B
0x180008310  lea     rcx, [rbp+57h+var_80]; this
0x180008314  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008319  mov     rcx, rbx; hMem
0x18000831c  call    cs:__imp_LocalFree
0x180008322  lea     rcx, [rbp+57h+var_80]; this
0x180008326  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000832b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x180008332  lea     rax, [rbp+57h+var_58]
0x180008336  mov     edx, 0D6h; int
0x18000833b  mov     [rsp+0C0h+Src], rax; Src
0x180008340  mov     [rbp+57h+var_58], r15
0x180008344  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180008349  mov     rbx, [rbp+57h+var_50]
0x18000834d  test    rbx, rbx
0x180008350  jz      short loc_18000836D
0x180008352  lea     rcx, [rbp+57h+var_80]; this
0x180008356  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000835b  mov     rcx, rbx; hMem
0x18000835e  call    cs:__imp_LocalFree
0x180008364  lea     rcx, [rbp+57h+var_80]; this
0x180008368  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000836d  mov     edx, 0D7h; int
0x180008372  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; int
0x180008379  lea     rax, [rbp+57h+var_50]
0x18000837d  mov     [rsp+0C0h+Src], rax; Src
0x180008382  mov     [rbp+57h+var_50], r15
0x180008386  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18000838b  mov     rbx, [rbp+57h+pv]
0x18000838f  mov     rdi, [rbp+57h+var_50]
0x180008393  mov     rsi, [rbp+57h+var_58]
0x180008397  mov     r15, [rbp+57h+var_60]
0x18000839b  mov     r12, [rbp+57h+hMem]
0x18000839f  test    rbx, rbx
0x1800083a2  jz      short loc_1800083BF
0x1800083a4  lea     rcx, [rbp+57h+var_80]; this
0x1800083a8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800083ad  mov     rcx, rbx; pv
0x1800083b0  call    cs:__imp_CoTaskMemFree
0x1800083b6  lea     rcx, [rbp+57h+var_80]; this
0x1800083ba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800083bf  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x1800083c6  lea     r8, [rbp+57h+pv]
0x1800083ca  mov     [rsp+0C0h+var_90], rdi
0x1800083cf  mov     r9, r12
0x1800083d2  mov     [rsp+0C0h+Src], rsi
0x1800083d7  mov     edx, 0D8h
0x1800083dc  mov     [rsp+0C0h+ppv], r15
0x1800083e1  mov     [rbp+57h+pv], 0
0x1800083e9  call    ResourceStringCoAllocFormatMessage
0x1800083ee  xor     r15d, r15d
0x1800083f1  lea     rcx, [rbp+57h+var_80]
0x1800083f5  mov     [rbp+57h+var_80], r15
0x1800083f9  call    ?reset@?$com_ptr_t@UIAccPropServices@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::reset(void)
0x1800083fe  lea     rax, [rbp+57h+var_80]
0x180008402  xor     edx, edx; pUnkOuter
0x180008404  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x18000840b  mov     [rsp+0C0h+ppv], rax; ppv
0x180008410  lea     r8d, [r15+1]; dwClsContext
0x180008414  lea     rcx, CLSID_AccPropServices; rclsid
0x18000841b  call    cs:__imp_CoCreateInstance
0x180008421  mov     rcx, [r14+0B0h]
0x180008428  mov     rax, [rbp+57h+var_80]
0x18000842c  mov     [rbp+57h+var_80], r15
0x180008430  mov     [r14+0B0h], rax
0x180008437  test    rcx, rcx
0x18000843a  jz      short loc_180008448
0x18000843c  mov     rax, [rcx]
0x18000843f  mov     rax, [rax+10h]
0x180008443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008448  lea     rcx, [rbp+57h+var_80]
0x18000844c  call    ??1?$com_ptr_t@UIAccPropServices@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::~com_ptr_t<IAccPropServices,wil::err_returncode_policy>(void)
0x180008451  mov     rsi, [r14+0B0h]
0x180008458  mov     rcx, r13
0x18000845b  mov     rbx, [rbp+57h+pv]
0x18000845f  movups  xmm6, xmmword ptr cs:PROPID_ACC_VALUEMAP.Data1
0x180008466  mov     rax, [rsi]
0x180008469  mov     rdi, [rax+38h]
0x18000846d  mov     rax, [r13+0]
0x180008471  mov     rax, [rax+168h]
0x180008478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000847d  lea     rcx, [rbp+57h+var_80]
0x180008481  mov     [rsp+0C0h+Src], rbx
0x180008486  mov     [rsp+0C0h+ppv], rcx
0x18000848b  mov     rdx, rax
0x18000848e  mov     rcx, rsi
0x180008491  xor     r9d, r9d
0x180008494  mov     r8d, 0FFFFFFFCh
0x18000849a  mov     rax, rdi
0x18000849d  movdqu  xmmword ptr [rbp+57h+var_80], xmm6
0x1800084a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a7  lea     rcx, [rbp+57h+hMem]; void *
0x1800084ab  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800084b0  lea     rcx, [rbp+57h+pv]
0x1800084b4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800084b9  cmp     [r14+90h], r15d
0x1800084c0  lea     rax, aUserDefaultTic; "user_default_tickmark_left"
0x1800084c7  mov     rbx, [r14+28h]
0x1800084cb  lea     rcx, aAdminDefaultTi; "admin_default_tickmark_left"
0x1800084d2  cmovz   rcx, rax
0x1800084d6  call    cs:__imp_StrToID
0x1800084dc  movzx   edx, ax
0x1800084df  mov     rcx, rbx
0x1800084e2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800084e8  mov     rcx, rax; struct DirectUI::Element *
0x1800084eb  call    ?s_SetDefaultTickMark@CUACSettingsPage@@CAJPEAVElement@DirectUI@@@Z; CUACSettingsPage::s_SetDefaultTickMark(DirectUI::Element *)
0x1800084f0  cmp     [r14+90h], r15d
0x1800084f7  lea     rax, aUserDefaultTic_0; "user_default_tickmark_right"
0x1800084fe  mov     rbx, [r14+28h]
0x180008502  lea     rcx, aAdminDefaultTi_0; "admin_default_tickmark_right"
0x180008509  cmovz   rcx, rax
0x18000850d  call    cs:__imp_StrToID
0x180008513  movzx   edx, ax
0x180008516  mov     rcx, rbx
0x180008519  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000851f  mov     rcx, rax; struct DirectUI::Element *
0x180008522  call    ?s_SetDefaultTickMark@CUACSettingsPage@@CAJPEAVElement@DirectUI@@@Z; CUACSettingsPage::s_SetDefaultTickMark(DirectUI::Element *)
0x180008527  mov     rcx, [rbp+57h+var_48]
0x18000852b  xor     rcx, rsp; StackCookie
0x18000852e  call    __security_check_cookie
0x180008533  lea     r11, [rsp+0C0h+var_30]
0x18000853b  mov     rbx, [r11+50h]
0x18000853f  movaps  xmm6, xmmword ptr [r11-10h]
0x180008544  mov     rsp, r11
0x180008547  pop     r15
0x180008549  pop     r14
0x18000854b  pop     r13
0x18000854d  pop     r12
0x18000854f  pop     rdi
0x180008550  pop     rsi
0x180008551  pop     rbp
0x180008552  retn
```
