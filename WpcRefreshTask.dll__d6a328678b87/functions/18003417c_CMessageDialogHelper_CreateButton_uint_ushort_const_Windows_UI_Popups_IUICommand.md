# CMessageDialogHelper::_CreateButton(uint,ushort const *,Windows::UI::Popups::IUICommand * *)

- ea: `0x18003417c`
- end: `0x18003453f`
- name: `?_CreateButton@CMessageDialogHelper@@AEAAJIPEBGPEAPEAUIUICommand@Popups@UI@Windows@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CMessageDialogHelper *__hidden this, unsigned int, const unsigned __int16 *, struct Windows::UI::Popups::IUICommand **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800327bc`

## callees

- `0x1800060a0`
- `0x1800065c8`
- `0x180007ec1`
- `0x18002ca60`
- `0x18002eb3c`
- `0x18003417c`
- `0x1800ae010`

## import_xrefs

- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180034483`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180034483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180034375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180034375`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800343b0`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800343b0`

## string_xrefs

- `0x18003436e`: `Windows.UI.Popups.UICommand`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CMessageDialogHelper::_CreateButton(
        CMessageDialogHelper *this,
        int a2,
        const unsigned __int16 *a3,
        struct Windows::UI::Popups::IUICommand **a4)
{
  HRESULT v7; // edi
  struct Windows::UI::Popups::IUICommand *v8; // rcx
  void *v9; // rcx
  struct Windows::UI::Popups::IUICommand *v10; // rcx
  void *v11; // rbx
  void *v12; // rcx
  void *v13; // rcx
  struct Windows::UI::Popups::IUICommand *v14; // rcx
  void *v15; // rdi
  WCHAR *v16; // rax
  WCHAR *v17; // rbx
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  HSTRING v21; // rdi
  struct Windows::UI::Popups::IUICommand *v22; // rcx
  unsigned int v23; // r8d
  struct Windows::UI::Popups::IUICommand *v24; // rsi
  __int64 (__fastcall *v25)(struct Windows::UI::Popups::IUICommand *, PVOID); // rdi
  HSTRING_HEADER *v26; // rax
  struct Windows::UI::Popups::IUICommand *v27; // rax
  void *v28; // rcx
  struct Windows::UI::Popups::IUICommand *v29; // rcx
  void *v30; // rcx
  struct Windows::UI::Popups::IUICommand *v32; // [rsp+20h] [rbp-60h] BYREF
  void *ppv; // [rsp+28h] [rbp-58h] BYREF
  void *v34; // [rsp+30h] [rbp-50h]
  const WCHAR *v35[2]; // [rsp+38h] [rbp-48h] BYREF
  char v36; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF

  v35[0] = a3;
  *a4 = 0;
  v34 = 0;
  v32 = 0;
  v7 = (**(__int64 (__fastcall ***)(CMessageDialogHelper *, GUID *, void **))this)(
         this,
         &GUID_00000038_0000_0000_c000_000000000046,
         (void **)&v32);
  if ( v7 >= 0 )
  {
    ppv = 0;
    v7 = (*(__int64 (__fastcall **)(struct Windows::UI::Popups::IUICommand *, void **))(*(_QWORD *)v32 + 24LL))(
           v32,
           &ppv);
    if ( v7 >= 0 )
    {
      v11 = ppv;
      if ( ppv )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 8LL))(ppv);
      v12 = v34;
      v34 = v11;
      if ( v12 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      v13 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v14 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(struct Windows::UI::Popups::IUICommand *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v7 = 0;
    }
    else
    {
      v9 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v10 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(struct Windows::UI::Popups::IUICommand *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
  }
  else
  {
    v8 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Popups::IUICommand *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  if ( v7 >= 0 )
  {
    v15 = v34;
    if ( v34 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 8LL))(v34);
    v16 = (WCHAR *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( v16 )
    {
      *((_DWORD *)v16 + 3) = 1;
      *(_QWORD *)v16 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::UI::Popups::IUICommandInvokedHandler>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *((_QWORD *)v17 + 2) = 0;
      if ( v17 + 8 != (WCHAR *)&v36 )
      {
        *((_QWORD *)v17 + 2) = v15;
        v15 = 0;
      }
      *((_QWORD *)v17 + 3) = this;
      *(_QWORD *)v17 = &Microsoft::WRL::Details::DelegateArgTraits<long (Windows::UI::Popups::IUICommandInvokedHandler::*)(Windows::UI::Popups::IUICommand *)>::DelegateInvokeHelper<Windows::UI::Popups::IUICommandInvokedHandler,_lambda_48f03e61741d85dde7999758d1807eca_,-1,Windows::UI::Popups::IUICommand *>::`vftable';
    }
    else
    {
      v17 = 0;
    }
    v35[1] = v17;
    if ( v15 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    v32 = 0;
    string = 0;
    v18 = WindowsCreateStringReference(L"Windows.UI.Popups.UICommand", 0x1Bu, &hstringHeader, &string);
    if ( v18 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
      JUMPOUT(0x18003453ELL);
    }
    v21 = string;
    v22 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Popups::IUICommand *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v32 = 0;
    ppv = 0;
    v7 = RoActivateInstance(v21, &ppv);
    if ( v7 >= 0 )
    {
      if ( !memcmp_0(&GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        v32 = (struct Windows::UI::Popups::IUICommand *)ppv;
      }
      else
      {
        v7 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
               ppv,
               &GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f,
               (void **)&v32);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    if ( v7 >= 0 )
    {
      v24 = v32;
      v25 = *(__int64 (__fastcall **)(struct Windows::UI::Popups::IUICommand *, PVOID))(*(_QWORD *)v32 + 56LL);
      v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v35, v23);
      v7 = v25(v24, v26[1].Reserved.Reserved1);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(struct Windows::UI::Popups::IUICommand *, WCHAR *))(*(_QWORD *)v32 + 72LL))(
               v32,
               v17);
        if ( v7 >= 0 )
        {
          ppv = 0;
          LOWORD(hstringHeader.Reserved.Reserved1) = 19;
          *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = a2;
          v7 = PropVariantToWinRTPropertyValue(
                 &hstringHeader.Reserved.Reserved1,
                 &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                 &ppv);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(struct Windows::UI::Popups::IUICommand *, void *))(*(_QWORD *)v32 + 88LL))(
                   v32,
                   ppv);
            if ( v7 >= 0 )
            {
              v27 = v32;
              v32 = 0;
              *a4 = v27;
            }
          }
          v28 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
          }
        }
      }
    }
    v29 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::UI::Popups::IUICommand *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v17 )
      (*(void (__fastcall **)(WCHAR *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v30 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003417c  push    rbp
0x18003417e  push    rbx
0x18003417f  push    rsi
0x180034180  push    rdi
0x180034181  push    r12
0x180034183  push    r14
0x180034185  push    r15
0x180034187  mov     rbp, rsp
0x18003418a  sub     rsp, 80h
0x180034191  mov     rax, cs:__security_cookie
0x180034198  xor     rax, rsp
0x18003419b  mov     [rbp+var_8], rax
0x18003419f  mov     r14, r9
0x1800341a2  mov     r15d, edx
0x1800341a5  mov     rsi, rcx
0x1800341a8  mov     [rbp+var_48], r8
0x1800341ac  xor     r12d, r12d
0x1800341af  mov     [r9], r12
0x1800341b2  mov     [rbp+var_50], r12
0x1800341b6  mov     [rbp+var_60], r12
0x1800341ba  mov     rax, [rcx]
0x1800341bd  lea     r8, [rbp+var_60]
0x1800341c1  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x1800341c8  mov     rax, [rax]
0x1800341cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341d0  mov     edi, eax
0x1800341d2  test    eax, eax
0x1800341d4  jns     short loc_1800341F5
0x1800341d6  mov     rcx, [rbp+var_60]
0x1800341da  test    rcx, rcx
0x1800341dd  jz      short loc_1800341F0
0x1800341df  mov     [rbp+var_60], r12
0x1800341e3  mov     rax, [rcx]
0x1800341e6  mov     rax, [rax+10h]
0x1800341ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341ef  nop
0x1800341f0  jmp     loc_1800342B3
0x1800341f5  mov     [rbp+ppv], r12
0x1800341f9  mov     rcx, [rbp+var_60]
0x1800341fd  mov     rax, [rcx]
0x180034200  lea     rdx, [rbp+ppv]
0x180034204  mov     rax, [rax+18h]
0x180034208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003420d  mov     edi, eax
0x18003420f  test    eax, eax
0x180034211  jns     short loc_180034249
0x180034213  mov     rcx, [rbp+ppv]
0x180034217  test    rcx, rcx
0x18003421a  jz      short loc_18003422D
0x18003421c  mov     [rbp+ppv], r12
0x180034220  mov     rax, [rcx]
0x180034223  mov     rax, [rax+10h]
0x180034227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003422c  nop
0x18003422d  mov     rcx, [rbp+var_60]
0x180034231  test    rcx, rcx
0x180034234  jz      short loc_180034247
0x180034236  mov     [rbp+var_60], r12
0x18003423a  mov     rax, [rcx]
0x18003423d  mov     rax, [rax+10h]
0x180034241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034246  nop
0x180034247  jmp     short loc_1800342B3
0x180034249  mov     rbx, [rbp+ppv]
0x18003424d  test    rbx, rbx
0x180034250  jz      short loc_180034262
0x180034252  mov     rax, [rbx]
0x180034255  mov     rcx, rbx
0x180034258  mov     rax, [rax+8]
0x18003425c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034261  nop
0x180034262  mov     rcx, [rbp+var_50]
0x180034266  mov     [rbp+var_50], rbx
0x18003426a  test    rcx, rcx
0x18003426d  jz      short loc_18003427C
0x18003426f  mov     rax, [rcx]
0x180034272  mov     rax, [rax+10h]
0x180034276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003427b  nop
0x18003427c  mov     rcx, [rbp+ppv]
0x180034280  test    rcx, rcx
0x180034283  jz      short loc_180034296
0x180034285  mov     [rbp+ppv], r12
0x180034289  mov     rax, [rcx]
0x18003428c  mov     rax, [rax+10h]
0x180034290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034295  nop
0x180034296  mov     rcx, [rbp+var_60]
0x18003429a  test    rcx, rcx
0x18003429d  jz      short loc_1800342B0
0x18003429f  mov     [rbp+var_60], r12
0x1800342a3  mov     rax, [rcx]
0x1800342a6  mov     rax, [rax+10h]
0x1800342aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342af  nop
0x1800342b0  mov     edi, r12d
0x1800342b3  test    edi, edi
0x1800342b5  js      loc_1800344FD
0x1800342bb  mov     rdi, [rbp+var_50]
0x1800342bf  test    rdi, rdi
0x1800342c2  jz      short loc_1800342D4
0x1800342c4  mov     rax, [rdi]
0x1800342c7  mov     rcx, rdi
0x1800342ca  mov     rax, [rax+8]
0x1800342ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342d3  nop
0x1800342d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800342db  mov     ecx, 20h ; ' '; unsigned __int64
0x1800342e0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800342e5  mov     rbx, rax
0x1800342e8  test    rax, rax
0x1800342eb  jz      short loc_18003433D
0x1800342ed  mov     dword ptr [rax+0Ch], 1
0x1800342f4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUICommandInvokedHandler@Popups@UI@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::UI::Popups::IUICommandInvokedHandler>::`vftable'
0x1800342fb  mov     [rbx], rax
0x1800342fe  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180034305  test    rcx, rcx
0x180034308  jz      short loc_180034317
0x18003430a  mov     rax, [rcx]
0x18003430d  mov     rax, [rax+8]
0x180034311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034316  nop
0x180034317  lea     rax, [rbx+10h]
0x18003431b  mov     [rax], r12
0x18003431e  lea     rcx, [rbp+var_38]
0x180034322  cmp     rax, rcx
0x180034325  jz      short loc_18003432D
0x180034327  mov     [rax], rdi
0x18003432a  mov     rdi, r12
0x18003432d  mov     [rax+8], rsi
0x180034331  lea     rax, ??_7?$DelegateInvokeHelper@UIUICommandInvokedHandler@Popups@UI@Windows@@V_lambda_48f03e61741d85dde7999758d1807eca_@@$0?0PEAUIUICommand@234@@?$DelegateArgTraits@P8IUICommandInvokedHandler@Popups@UI@Windows@@EAAJPEAUIUICommand@234@@Z@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::DelegateArgTraits<long (Windows::UI::Popups::IUICommandInvokedHandler::*)(Windows::UI::Popups::IUICommand *)>::DelegateInvokeHelper<Windows::UI::Popups::IUICommandInvokedHandler,_lambda_48f03e61741d85dde7999758d1807eca_,-1,Windows::UI::Popups::IUICommand *>::`vftable'
0x180034338  mov     [rbx], rax
0x18003433b  jmp     short loc_180034340
0x18003433d  mov     rbx, r12
0x180034340  mov     [rbp+var_40], rbx
0x180034344  test    rdi, rdi
0x180034347  jz      short loc_180034359
0x180034349  mov     rax, [rdi]
0x18003434c  mov     rcx, rdi
0x18003434f  mov     rax, [rax+10h]
0x180034353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034358  nop
0x180034359  mov     [rbp+var_60], r12
0x18003435d  mov     [rbp+string], r12
0x180034361  lea     r9, [rbp+string]; string
0x180034365  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180034369  mov     edx, 1Bh; length
0x18003436e  lea     rcx, ?RuntimeClass_Windows_UI_Popups_UICommand@@3QBGB; "Windows.UI.Popups.UICommand"
0x180034375  call    cs:__imp_WindowsCreateStringReference
0x18003437b  test    eax, eax
0x18003437d  js      loc_180034537
0x180034383  mov     rdi, [rbp+string]
0x180034387  mov     rcx, [rbp+var_60]
0x18003438b  test    rcx, rcx
0x18003438e  jz      short loc_1800343A1
0x180034390  mov     [rbp+var_60], r12
0x180034394  mov     rax, [rcx]
0x180034397  mov     rax, [rax+10h]
0x18003439b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343a0  nop
0x1800343a1  mov     [rbp+var_60], r12
0x1800343a5  mov     [rbp+ppv], r12
0x1800343a9  lea     rdx, [rbp+ppv]
0x1800343ad  mov     rcx, rdi
0x1800343b0  call    cs:__imp_RoActivateInstance
0x1800343b6  mov     edi, eax
0x1800343b8  test    eax, eax
0x1800343ba  js      short loc_180034410
0x1800343bc  mov     r8d, 10h; Size
0x1800343c2  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800343c9  lea     rcx, _GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f; Buf1
0x1800343d0  call    memcmp_0
0x1800343d5  test    eax, eax
0x1800343d7  jnz     short loc_1800343E3
0x1800343d9  mov     rax, [rbp+ppv]
0x1800343dd  mov     [rbp+var_60], rax
0x1800343e1  jmp     short loc_180034410
0x1800343e3  mov     rcx, [rbp+ppv]
0x1800343e7  mov     rax, [rcx]
0x1800343ea  lea     r8, [rbp+var_60]
0x1800343ee  lea     rdx, _GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f
0x1800343f5  mov     rax, [rax]
0x1800343f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343fd  mov     edi, eax
0x1800343ff  mov     rcx, [rbp+ppv]
0x180034403  mov     rax, [rcx]
0x180034406  mov     rax, [rax+10h]
0x18003440a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003440f  nop
0x180034410  test    edi, edi
0x180034412  js      loc_1800344CE
0x180034418  mov     rsi, [rbp+var_60]
0x18003441c  mov     rax, [rsi]
0x18003441f  mov     rdi, [rax+38h]
0x180034423  lea     rdx, [rbp+var_48]
0x180034427  lea     rcx, [rbp+hstringHeader]
0x18003442b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180034430  nop
0x180034431  mov     rdx, [rax+18h]
0x180034435  mov     rcx, rsi
0x180034438  mov     rax, rdi
0x18003443b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034440  mov     edi, eax
0x180034442  test    eax, eax
0x180034444  js      loc_1800344CE
0x18003444a  mov     rcx, [rbp+var_60]
0x18003444e  mov     rax, [rcx]
0x180034451  mov     rdx, rbx
0x180034454  mov     rax, [rax+48h]
0x180034458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003445d  mov     edi, eax
0x18003445f  test    eax, eax
0x180034461  js      short loc_1800344CE
0x180034463  mov     [rbp+ppv], r12
0x180034467  mov     eax, 13h
0x18003446c  mov     word ptr [rbp+hstringHeader.Reserved], ax
0x180034470  mov     dword ptr [rbp+hstringHeader.Reserved+8], r15d
0x180034474  lea     r8, [rbp+ppv]; ppv
0x180034478  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62; riid
0x18003447f  lea     rcx, [rbp+hstringHeader]; propvar
0x180034483  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180034489  mov     edi, eax
0x18003448b  test    eax, eax
0x18003448d  js      short loc_1800344B4
0x18003448f  mov     rcx, [rbp+var_60]
0x180034493  mov     rax, [rcx]
0x180034496  mov     rdx, [rbp+ppv]
0x18003449a  mov     rax, [rax+58h]
0x18003449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344a3  mov     edi, eax
0x1800344a5  test    eax, eax
0x1800344a7  js      short loc_1800344B4
0x1800344a9  mov     rax, [rbp+var_60]
0x1800344ad  mov     [rbp+var_60], r12
0x1800344b1  mov     [r14], rax
0x1800344b4  mov     rcx, [rbp+ppv]
0x1800344b8  test    rcx, rcx
0x1800344bb  jz      short loc_1800344CE
0x1800344bd  mov     [rbp+ppv], r12
0x1800344c1  mov     rax, [rcx]
0x1800344c4  mov     rax, [rax+10h]
0x1800344c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344cd  nop
0x1800344ce  mov     rcx, [rbp+var_60]
0x1800344d2  test    rcx, rcx
0x1800344d5  jz      short loc_1800344E8
0x1800344d7  mov     [rbp+var_60], r12
0x1800344db  mov     rax, [rcx]
0x1800344de  mov     rax, [rax+10h]
0x1800344e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344e7  nop
0x1800344e8  test    rbx, rbx
0x1800344eb  jz      short loc_1800344FD
0x1800344ed  mov     rax, [rbx]
0x1800344f0  mov     rcx, rbx
0x1800344f3  mov     rax, [rax+10h]
0x1800344f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344fc  nop
0x1800344fd  mov     rcx, [rbp+var_50]
0x180034501  test    rcx, rcx
0x180034504  jz      short loc_180034517
0x180034506  mov     [rbp+var_50], r12
0x18003450a  mov     rax, [rcx]
0x18003450d  mov     rax, [rax+10h]
0x180034511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034516  nop
0x180034517  mov     eax, edi
0x180034519  mov     rcx, [rbp+var_8]
0x18003451d  xor     rcx, rsp; StackCookie
0x180034520  call    __security_check_cookie
0x180034525  add     rsp, 80h
0x18003452c  pop     r15
0x18003452e  pop     r14
0x180034530  pop     r12
0x180034532  pop     rdi
0x180034533  pop     rsi
0x180034534  pop     rbx
0x180034535  pop     rbp
0x180034536  retn
0x180034537  mov     ecx, eax; this
0x180034539  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
