# CXAMLHostWindow::Show(ShowViewOptions)

- ea: `0x18002da50`
- end: `0x18002dd84`
- name: `?Show@CXAMLHostWindow@@UEAAJW4ShowViewOptions@@@Z`
- size: `820`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x18002da50`
- `0x18002e0d4`
- `0x18002fa58`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18002db0a`
- `SHCORE!IUnknown_QueryService` at `0x18002dcd1`
- `SHCORE!IUnknown_QueryService` at `0x18002db0a`
- `SHCORE!IUnknown_QueryService` at `0x18002dcd1`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18002dbdc`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18002dc5b`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18002dbdc`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18002dc5b`

## string_xrefs

- `0x18002dc86`: `UseCachedResponse`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CXAMLHostWindow::Show(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r12d
  int Window; // ebx
  void *v7; // rdi
  int (__fastcall *v8)(void *, __int64, GUID *, __int64 *); // rbx
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, __int64, _BYTE *); // rbx
  char v11; // al
  __int64 v12; // rsi
  void (__fastcall *v13)(__int64, __int64, void *, char *); // rdi
  void *v14; // rbx
  __int64 v15; // rsi
  void (__fastcall *v16)(__int64, __int64, void *, char *); // rdi
  void *v17; // rbx
  char v19; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v20[7]; // [rsp+31h] [rbp-38h] BYREF
  void *v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  void *v23; // [rsp+48h] [rbp-21h] BYREF
  void *ppv; // [rsp+50h] [rbp-19h] BYREF
  void *ppvOut; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER propvar; // [rsp+60h] [rbp-9h] BYREF
  __int64 v27; // [rsp+78h] [rbp+Fh]

  v3 = a2;
  LODWORD(v21) = 0;
  if ( (*(_DWORD *)(a1 + 332))++ == -1 )
    *(_DWORD *)(a1 + 332) = 1;
  if ( *(_BYTE *)(a1 + 265) )
  {
    *(_BYTE *)(a1 + 264) = 1;
    *(_DWORD *)(a1 + 268) = a2;
    return 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 64) )
    {
      Window = 0;
    }
    else
    {
      Window = CXAMLHostWindow::_CreateWindow((CXAMLHostWindow *)(a1 - 128), a2, a3);
      if ( Window < 0 )
        return (unsigned int)Window;
    }
    if ( !*(_BYTE *)(a1 + 320) )
      goto LABEL_24;
    *(_BYTE *)(a1 + 320) = 0;
    ppvOut = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( IUnknown_QueryService(
           *(IUnknown **)(a1 - 16),
           &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
           &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
           &ppvOut) >= 0 )
    {
      v22 = 0;
      v7 = ppvOut;
      v8 = *(int (__fastcall **)(void *, __int64, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v22);
      if ( v8(v7, 1, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v22) >= 0 )
      {
        v20[0] = 0;
        v9 = v22;
        v10 = *(int (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v22 + 64LL);
        v27 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"Instrumentation", 0x10u, 0xFu);
        LODWORD(v21) = 1;
        if ( v10(v9, v27, v20) < 0 || (v11 = 1, v20[0]) )
          v11 = 0;
        if ( v11 )
        {
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
          LOWORD(propvar.Reserved.Reserved1) = 31;
          *(_QWORD *)&propvar.Reserved.Reserved2[8] = L"form=REFRSH";
          if ( PropVariantToWinRTPropertyValue(
                 &propvar.Reserved.Reserved1,
                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                 &ppv) >= 0 )
          {
            v19 = 0;
            v12 = v22;
            v13 = *(void (__fastcall **)(__int64, __int64, void *, char *))(*(_QWORD *)v22 + 80LL);
            v14 = ppv;
            v27 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"Instrumentation", 0x10u, 0xFu);
            v13(v12, v27, v14, &v19);
          }
          v23 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v23);
          LOWORD(propvar.Reserved.Reserved1) = 11;
          *(_WORD *)&propvar.Reserved.Reserved2[8] = -1;
          if ( PropVariantToWinRTPropertyValue(
                 &propvar.Reserved.Reserved1,
                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                 &v23) >= 0 )
          {
            v19 = 0;
            v15 = v22;
            v16 = *(void (__fastcall **)(__int64, __int64, void *, char *))(*(_QWORD *)v22 + 80LL);
            v17 = v23;
            v27 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"UseCachedResponse", 0x12u, 0x11u);
            v16(v15, v27, v17, &v19);
          }
          v21 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
          if ( IUnknown_QueryService(
                 *(IUnknown **)(a1 - 16),
                 &IID_IConnectedSearchSettingsManager,
                 &GUID_cdd7f6c3_a648_4fbf_b844_68d78dae9d95,
                 &v21) >= 0 )
            (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v21 + 96LL))(v21, 1);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v23);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v22);
    }
    Window = CXAMLHostWindow::_StartupXAML((CXAMLHostWindow *)(a1 - 128));
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( Window >= 0 )
    {
LABEL_24:
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 80) + 88LL))(
        *(_QWORD *)(a1 + 80),
        v3,
        *(_QWORD *)(a1 + 120));
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 80) + 96LL))(
        *(_QWORD *)(a1 + 80),
        *(_QWORD *)(a1 + 120));
    }
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x18002da50  mov     [rsp-8+arg_10], rbx
0x18002da55  push    rbp
0x18002da56  push    rsi
0x18002da57  push    rdi
0x18002da58  push    r12
0x18002da5a  push    r13
0x18002da5c  push    r14
0x18002da5e  push    r15
0x18002da60  lea     rbp, [rsp-27h]
0x18002da65  sub     rsp, 90h
0x18002da6c  mov     rax, cs:__security_cookie
0x18002da73  xor     rax, rsp
0x18002da76  mov     [rbp+57h+var_40], rax
0x18002da7a  mov     r12d, edx
0x18002da7d  mov     r14, rcx
0x18002da80  xor     r13d, r13d
0x18002da83  mov     dword ptr [rbp+57h+var_88], r13d
0x18002da87  add     dword ptr [rcx+14Ch], 1
0x18002da8e  lea     esi, [r13+1]
0x18002da92  jnz     short loc_18002DA9A
0x18002da94  mov     [rcx+14Ch], esi
0x18002da9a  cmp     [rcx+109h], r13b
0x18002daa1  jz      short loc_18002DAB9
0x18002daa3  mov     [rcx+108h], sil
0x18002daaa  mov     [rcx+10Ch], r12d
0x18002dab1  mov     ebx, r13d
0x18002dab4  jmp     loc_18002DD5B
0x18002dab9  cmp     [rcx+40h], r13
0x18002dabd  jz      short loc_18002DAC4
0x18002dabf  mov     ebx, r13d
0x18002dac2  jmp     short loc_18002DAD7
0x18002dac4  add     rcx, 0FFFFFFFFFFFFFF80h; this
0x18002dac8  call    ?_CreateWindow@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_CreateWindow(void)
0x18002dacd  mov     ebx, eax
0x18002dacf  test    eax, eax
0x18002dad1  js      loc_18002DD5B
0x18002dad7  cmp     [r14+140h], r13b
0x18002dade  jz      loc_18002DD30
0x18002dae4  mov     [r14+140h], r13b
0x18002daeb  mov     [rbp+57h+ppvOut], r13
0x18002daef  lea     rcx, [rbp+57h+ppvOut]
0x18002daf3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002daf8  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x18002dafc  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x18002db03  mov     r8, rdx; riid
0x18002db06  mov     rcx, [r14-10h]; punk
0x18002db0a  call    cs:__imp_IUnknown_QueryService
0x18002db10  test    eax, eax
0x18002db12  js      loc_18002DD18
0x18002db18  mov     [rbp+57h+var_80], r13
0x18002db1c  mov     rdi, [rbp+57h+ppvOut]
0x18002db20  mov     rax, [rdi]
0x18002db23  mov     rbx, [rax+28h]
0x18002db27  lea     rcx, [rbp+57h+var_80]
0x18002db2b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002db30  lea     r9, [rbp+57h+var_80]
0x18002db34  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18002db3b  mov     edx, esi
0x18002db3d  mov     rcx, rdi
0x18002db40  mov     rax, rbx
0x18002db43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db48  test    eax, eax
0x18002db4a  js      loc_18002DD0F
0x18002db50  mov     [rbp+57h+var_8F], r13b
0x18002db54  mov     rdi, [rbp+57h+var_80]
0x18002db58  mov     rax, [rdi]
0x18002db5b  mov     rbx, [rax+40h]
0x18002db5f  mov     [rbp+57h+var_48], r13
0x18002db63  mov     r9d, 0Fh; unsigned int
0x18002db69  lea     r8d, [r9+1]; unsigned int
0x18002db6d  lea     rdx, aInstrumentatio; "Instrumentation"
0x18002db74  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x18002db78  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002db7d  nop
0x18002db7e  mov     dword ptr [rbp+57h+var_88], esi
0x18002db81  lea     r8, [rbp+57h+var_8F]
0x18002db85  mov     rdx, [rbp+57h+var_48]
0x18002db89  mov     rcx, rdi
0x18002db8c  mov     rax, rbx
0x18002db8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db94  test    eax, eax
0x18002db96  js      short loc_18002DBA1
0x18002db98  cmp     [rbp+57h+var_8F], r13b
0x18002db9c  mov     al, sil
0x18002db9f  jz      short loc_18002DBA4
0x18002dba1  mov     al, r13b
0x18002dba4  test    al, al
0x18002dba6  jz      loc_18002DD0F
0x18002dbac  mov     [rbp+57h+ppv], r13
0x18002dbb0  lea     rcx, [rbp+57h+ppv]
0x18002dbb4  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dbb9  mov     eax, 1Fh
0x18002dbbe  mov     word ptr [rbp+57h+propvar], ax
0x18002dbc2  lea     rax, aFormRefrsh; "form=REFRSH"
0x18002dbc9  mov     [rbp+57h+var_58], rax
0x18002dbcd  lea     r8, [rbp+57h+ppv]; ppv
0x18002dbd1  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x18002dbd8  lea     rcx, [rbp+57h+propvar]; propvar
0x18002dbdc  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18002dbe2  test    eax, eax
0x18002dbe4  js      short loc_18002DC2F
0x18002dbe6  mov     [rbp+57h+var_90], r13b
0x18002dbea  mov     rsi, [rbp+57h+var_80]
0x18002dbee  mov     rax, [rsi]
0x18002dbf1  mov     rdi, [rax+50h]
0x18002dbf5  mov     rbx, [rbp+57h+ppv]
0x18002dbf9  mov     [rbp+57h+var_48], r13
0x18002dbfd  mov     r9d, 0Fh; unsigned int
0x18002dc03  lea     r8d, [r9+1]; unsigned int
0x18002dc07  lea     rdx, aInstrumentatio; "Instrumentation"
0x18002dc0e  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x18002dc12  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002dc17  nop
0x18002dc18  lea     r9, [rbp+57h+var_90]
0x18002dc1c  mov     r8, rbx
0x18002dc1f  mov     rdx, [rbp+57h+var_48]
0x18002dc23  mov     rcx, rsi
0x18002dc26  mov     rax, rdi
0x18002dc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc2e  nop
0x18002dc2f  mov     [rbp+57h+var_78], r13
0x18002dc33  lea     rcx, [rbp+57h+var_78]
0x18002dc37  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dc3c  mov     eax, 0Bh
0x18002dc41  mov     word ptr [rbp+57h+propvar], ax
0x18002dc45  or      eax, 0FFFFFFFFh
0x18002dc48  mov     word ptr [rbp+57h+var_58], ax
0x18002dc4c  lea     r8, [rbp+57h+var_78]; ppv
0x18002dc50  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x18002dc57  lea     rcx, [rbp+57h+propvar]; propvar
0x18002dc5b  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18002dc61  test    eax, eax
0x18002dc63  js      short loc_18002DCAE
0x18002dc65  mov     [rbp+57h+var_90], r13b
0x18002dc69  mov     rsi, [rbp+57h+var_80]
0x18002dc6d  mov     rax, [rsi]
0x18002dc70  mov     rdi, [rax+50h]
0x18002dc74  mov     rbx, [rbp+57h+var_78]
0x18002dc78  mov     [rbp+57h+var_48], r13
0x18002dc7c  mov     r9d, 11h; unsigned int
0x18002dc82  lea     r8d, [r9+1]; unsigned int
0x18002dc86  lea     rdx, aUsecachedrespo; "UseCachedResponse"
0x18002dc8d  lea     rcx, [rbp+57h+propvar]; hstringHeader
0x18002dc91  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002dc96  nop
0x18002dc97  lea     r9, [rbp+57h+var_90]
0x18002dc9b  mov     r8, rbx
0x18002dc9e  mov     rdx, [rbp+57h+var_48]
0x18002dca2  mov     rcx, rsi
0x18002dca5  mov     rax, rdi
0x18002dca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcad  nop
0x18002dcae  mov     [rbp+57h+var_88], r13
0x18002dcb2  lea     rcx, [rbp+57h+var_88]
0x18002dcb6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dcbb  lea     r9, [rbp+57h+var_88]; ppvOut
0x18002dcbf  lea     r8, _GUID_cdd7f6c3_a648_4fbf_b844_68d78dae9d95; riid
0x18002dcc6  lea     rdx, IID_IConnectedSearchSettingsManager; guidService
0x18002dccd  mov     rcx, [r14-10h]; punk
0x18002dcd1  call    cs:__imp_IUnknown_QueryService
0x18002dcd7  test    eax, eax
0x18002dcd9  js      short loc_18002DCF1
0x18002dcdb  mov     rcx, [rbp+57h+var_88]
0x18002dcdf  mov     rax, [rcx]
0x18002dce2  mov     edx, 1
0x18002dce7  mov     rax, [rax+60h]
0x18002dceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcf0  nop
0x18002dcf1  lea     rcx, [rbp+57h+var_88]
0x18002dcf5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dcfa  nop
0x18002dcfb  lea     rcx, [rbp+57h+var_78]
0x18002dcff  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dd04  nop
0x18002dd05  lea     rcx, [rbp+57h+ppv]
0x18002dd09  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dd0e  nop
0x18002dd0f  lea     rcx, [rbp+57h+var_80]
0x18002dd13  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dd18  lea     rcx, [r14-80h]; this
0x18002dd1c  call    ?_StartupXAML@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_StartupXAML(void)
0x18002dd21  mov     ebx, eax
0x18002dd23  lea     rcx, [rbp+57h+ppvOut]
0x18002dd27  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002dd2c  test    ebx, ebx
0x18002dd2e  js      short loc_18002DD5B
0x18002dd30  mov     rcx, [r14+50h]
0x18002dd34  mov     rax, [rcx]
0x18002dd37  mov     r8, [r14+78h]
0x18002dd3b  mov     edx, r12d
0x18002dd3e  mov     rax, [rax+58h]
0x18002dd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd47  mov     rcx, [r14+50h]
0x18002dd4b  mov     rax, [rcx]
0x18002dd4e  mov     rdx, [r14+78h]
0x18002dd52  mov     rax, [rax+60h]
0x18002dd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd5b  mov     eax, ebx
0x18002dd5d  mov     rcx, [rbp+57h+var_40]
0x18002dd61  xor     rcx, rsp; StackCookie
0x18002dd64  call    __security_check_cookie
0x18002dd69  mov     rbx, [rsp+0C0h+arg_10]
0x18002dd71  add     rsp, 90h
0x18002dd78  pop     r15
0x18002dd7a  pop     r14
0x18002dd7c  pop     r13
0x18002dd7e  pop     r12
0x18002dd80  pop     rdi
0x18002dd81  pop     rsi
0x18002dd82  pop     rbp
0x18002dd83  retn
```
