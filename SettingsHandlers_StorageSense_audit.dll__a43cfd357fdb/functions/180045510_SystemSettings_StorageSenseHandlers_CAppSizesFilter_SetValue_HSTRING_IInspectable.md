# SystemSettings::StorageSenseHandlers::CAppSizesFilter::SetValue(HSTRING__ *,IInspectable *)

- ea: `0x180045510`
- end: `0x18004580a`
- name: `?SetValue@CAppSizesFilter@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `762`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesFilter *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001f688`
- `0x18001fc0c`
- `0x1800352b4`
- `0x1800394a8`
- `0x18003b358`
- `0x18003b3c8`
- `0x18003dc10`
- `0x180044ddc`
- `0x180045510`
- `0x18004a0c0`
- `0x18004a6ec`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800455ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800455ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045622`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004574a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004578a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800457e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800455ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800455ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045622`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004574a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004578a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800457e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004566e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004566e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppSizesFilter::SetValue(
        HSTRING *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // eax
  const unsigned __int16 *v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v14; // rcx
  HSTRING *v15; // rbx
  PCWSTR v16; // rdi
  HSTRING v17; // rbx
  char v18; // di
  HSTRING v19; // rbx
  HSTRING v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  const unsigned __int16 *v24; // r8
  int v26[4]; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v27[56]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v28; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HSTRING string; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING v31; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)v26 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v26);
  v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, int *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         v26);
  v9 = v7;
  if ( v7 >= 0 )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A0E0, v8) )
    {
      string = 0;
      v10 = *(_QWORD *)v26;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v26 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v12 = v11(v10, &string);
      v9 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DD,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)(unsigned int)v12,
          v26[0]);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_19;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v15 = (HSTRING *)SystemSettings::StorageSenseHandlers::CAppSizesFilter::DecodeString(v14, &v31, StringRawBuffer);
      WindowsDeleteString(this[42]);
      this[42] = 0;
      this[42] = *v15;
      *v15 = 0;
      WindowsDeleteString(v31);
      if ( *((_BYTE *)this + 344) )
      {
        tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>>((struct wil::details::IFailureCallback *)v27);
        v16 = WindowsGetStringRawBuffer(this[42], 0);
        v17 = v28;
        v31 = v28;
        if ( v28 )
          _InterlockedIncrement((volatile signed __int32 *)v28 + 78);
        tip2::details::shared_data<1,0,0>::begin_update(v17 + 2);
        std::wstring::assign(v17 + 68, v16);
        tip2::test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>(&v31);
        v18 = *((_BYTE *)this + 344);
        v19 = v28;
        v31 = v28;
        if ( v28 )
          _InterlockedIncrement((volatile signed __int32 *)v28 + 78);
        tip2::details::shared_data<1,0,0>::begin_update(v19 + 2);
        *((_BYTE *)v19 + 304) = v18;
        tip2::test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>(&v31);
        *((_BYTE *)this + 345) = 1;
        (*((void (__fastcall **)(HSTRING *, HSTRING))*this + 28))(this, this[42]);
        SystemSettings::DataModel::CSettingBase::OnValueChanged(
          (SystemSettings::DataModel::CSettingBase *)this,
          (const unsigned __int16 *)&stru_1801068F0);
        tip2::details::shared_data<1,0,0>::complete_without_lock(v28 + 2);
        tip2::test_watcher<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>(v27);
      }
      v20 = string;
    }
    else
    {
      v31 = 0;
      v21 = *(_QWORD *)v26;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v26 + 152LL);
      WindowsDeleteString(0);
      v31 = 0;
      v23 = v22(v21, &v31);
      v9 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F2,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)(unsigned int)v23,
          v26[0]);
        WindowsDeleteString(v31);
        v31 = 0;
        goto LABEL_19;
      }
      (*((void (__fastcall **)(HSTRING *, HSTRING))*this + 28))(this, v31);
      if ( !SystemSettings::DataModel::IsHstringEqual(
              (SystemSettings::DataModel *)this[42],
              (HSTRING)&word_180106450,
              v24) )
        Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(this + 42), &word_180106450, 0);
      v20 = v31;
    }
    WindowsDeleteString(v20);
    v9 = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D9,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
    (const char *)(unsigned int)v7,
    v26[0]);
LABEL_19:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v26);
  return v9;
}

```

## disassembly

```asm
0x180045510  mov     [rsp-18h+arg_0], rbx
0x180045515  mov     [rsp-18h+arg_8], rsi
0x18004551a  push    rbp
0x18004551b  push    rdi
0x18004551c  push    r14
0x18004551e  mov     rbp, rsp
0x180045521  sub     rsp, 70h
0x180045525  mov     rdi, r8
0x180045528  mov     r14, rdx
0x18004552b  mov     rsi, rcx
0x18004552e  mov     qword ptr [rbp+var_50], 0
0x180045536  mov     rax, [r8]
0x180045539  mov     rbx, [rax]
0x18004553c  lea     rcx, [rbp+var_50]
0x180045540  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180045545  lea     r8, [rbp+var_50]
0x180045549  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180045550  mov     rcx, rdi
0x180045553  mov     rax, rbx
0x180045556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004555b  mov     ebx, eax
0x18004555d  test    eax, eax
0x18004555f  jns     short loc_18004557E
0x180045561  mov     rcx, [rbp+18h]; this
0x180045565  mov     r9d, eax; char *
0x180045568  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18004556f  mov     edx, 1D9h; void *
0x180045574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045579  jmp     loc_1800457EA
0x18004557e  lea     rdx, stru_18010A0E0; HSTRING
0x180045585  mov     rcx, r14; this
0x180045588  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004558d  test    al, al
0x18004558f  jz      loc_180045732
0x180045595  mov     [rbp+string], 0
0x18004559d  mov     rdi, qword ptr [rbp+var_50]
0x1800455a1  mov     rax, [rdi]
0x1800455a4  mov     rbx, [rax+98h]
0x1800455ab  xor     ecx, ecx; string
0x1800455ad  call    cs:__imp_WindowsDeleteString
0x1800455b3  mov     [rbp+string], 0
0x1800455bb  lea     rdx, [rbp+string]
0x1800455bf  mov     rcx, rdi
0x1800455c2  mov     rax, rbx
0x1800455c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800455ca  mov     ebx, eax
0x1800455cc  test    eax, eax
0x1800455ce  jns     short loc_180045600
0x1800455d0  mov     rcx, [rbp+18h]; this
0x1800455d4  mov     r9d, eax; char *
0x1800455d7  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x1800455de  mov     edx, 1DDh; void *
0x1800455e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800455e8  nop
0x1800455e9  mov     rcx, [rbp+string]; string
0x1800455ed  call    cs:__imp_WindowsDeleteString
0x1800455f3  mov     [rbp+string], 0
0x1800455fb  jmp     loc_1800457EA
0x180045600  xor     edx, edx; length
0x180045602  mov     rcx, [rbp+string]; string
0x180045606  call    cs:__imp_WindowsGetStringRawBuffer
0x18004560c  mov     r8, rax
0x18004560f  lea     rdx, [rbp+arg_18]
0x180045613  call    ?DecodeString@CAppSizesFilter@StorageSenseHandlers@SystemSettings@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; SystemSettings::StorageSenseHandlers::CAppSizesFilter::DecodeString(ushort const *)
0x180045618  mov     rbx, rax
0x18004561b  mov     rcx, [rsi+150h]; string
0x180045622  call    cs:__imp_WindowsDeleteString
0x180045628  mov     qword ptr [rsi+150h], 0
0x180045633  mov     rcx, [rbx]
0x180045636  mov     [rsi+150h], rcx
0x18004563d  mov     qword ptr [rbx], 0
0x180045644  mov     rcx, [rbp+arg_18]; string
0x180045648  call    cs:__imp_WindowsDeleteString
0x18004564e  cmp     byte ptr [rsi+158h], 0
0x180045655  jz      loc_180045729
0x18004565b  lea     rcx, [rbp+var_40]; struct wil::details::IFailureCallback *
0x18004565f  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_SelectedAppFilterTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180045664  nop
0x180045665  xor     edx, edx; length
0x180045667  mov     rcx, [rsi+150h]; string
0x18004566e  call    cs:__imp_WindowsGetStringRawBuffer
0x180045674  mov     rdi, rax
0x180045677  mov     rbx, [rbp+var_8]
0x18004567b  mov     [rbp+arg_18], rbx
0x18004567f  test    rbx, rbx
0x180045682  jz      short loc_18004568B
0x180045684  lock inc dword ptr [rbx+138h]
0x18004568b  lea     rcx, [rbx+8]
0x18004568f  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180045694  nop
0x180045695  lea     rcx, [rbx+110h]
0x18004569c  mov     rdx, rdi
0x18004569f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800456a4  nop
0x1800456a5  lea     rcx, [rbp+arg_18]
0x1800456a9  call    ??1?$test_data_control@V?$merged_data@U_tip_SelectedAppFilterTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>(void)
0x1800456ae  mov     dil, [rsi+158h]
0x1800456b5  mov     rbx, [rbp+var_8]
0x1800456b9  mov     [rbp+arg_18], rbx
0x1800456bd  test    rbx, rbx
0x1800456c0  jz      short loc_1800456C9
0x1800456c2  lock inc dword ptr [rbx+138h]
0x1800456c9  lea     rcx, [rbx+8]
0x1800456cd  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x1800456d2  mov     [rbx+130h], dil
0x1800456d9  lea     rcx, [rbp+arg_18]
0x1800456dd  call    ??1?$test_data_control@V?$merged_data@U_tip_SelectedAppFilterTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>::~test_data_control<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>(void)
0x1800456e2  mov     byte ptr [rsi+159h], 1
0x1800456e9  mov     rax, [rsi]
0x1800456ec  mov     rdx, [rsi+150h]
0x1800456f3  mov     rcx, rsi
0x1800456f6  mov     rax, [rax+0E0h]
0x1800456fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045702  lea     rdx, stru_1801068F0; unsigned __int16 *
0x180045709  mov     rcx, rsi; this
0x18004570c  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180045711  mov     rcx, [rbp+var_8]
0x180045715  add     rcx, 8
0x180045719  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18004571e  nop
0x18004571f  lea     rcx, [rbp+var_40]
0x180045723  call    ??1?$test_watcher@V?$merged_data@U_tip_SelectedAppFilterTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>::~test_watcher<tip2::details::merged_data<_tip_SelectedAppFilterTipTest,_tip_SelectedAppFilterTipTest>>(void)
0x180045728  nop
0x180045729  mov     rcx, [rbp+string]
0x18004572d  jmp     loc_1800457E2
0x180045732  mov     [rbp+arg_18], 0
0x18004573a  mov     rdi, qword ptr [rbp+var_50]
0x18004573e  mov     rax, [rdi]
0x180045741  mov     rbx, [rax+98h]
0x180045748  xor     ecx, ecx; string
0x18004574a  call    cs:__imp_WindowsDeleteString
0x180045750  mov     [rbp+arg_18], 0
0x180045758  lea     rdx, [rbp+arg_18]
0x18004575c  mov     rcx, rdi
0x18004575f  mov     rax, rbx
0x180045762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045767  mov     ebx, eax
0x180045769  test    eax, eax
0x18004576b  jns     short loc_18004579A
0x18004576d  mov     rcx, [rbp+18h]; this
0x180045771  mov     r9d, eax; char *
0x180045774  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18004577b  mov     edx, 1F2h; void *
0x180045780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045785  nop
0x180045786  mov     rcx, [rbp+arg_18]; string
0x18004578a  call    cs:__imp_WindowsDeleteString
0x180045790  mov     [rbp+arg_18], 0
0x180045798  jmp     short loc_1800457EA
0x18004579a  mov     rax, [rsi]
0x18004579d  mov     rdx, [rbp+arg_18]
0x1800457a1  mov     rcx, rsi
0x1800457a4  mov     rax, [rax+0E0h]
0x1800457ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457b0  lea     rdx, word_180106450; HSTRING
0x1800457b7  mov     rcx, [rsi+150h]; this
0x1800457be  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800457c3  test    al, al
0x1800457c5  jnz     short loc_1800457DE
0x1800457c7  xor     r8d, r8d; unsigned int
0x1800457ca  lea     rdx, word_180106450; unsigned __int16 *
0x1800457d1  lea     rcx, [rsi+150h]; this
0x1800457d8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800457dd  nop
0x1800457de  mov     rcx, [rbp+arg_18]; string
0x1800457e2  call    cs:__imp_WindowsDeleteString
0x1800457e8  xor     ebx, ebx
0x1800457ea  lea     rcx, [rbp+var_50]
0x1800457ee  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800457f3  mov     eax, ebx
0x1800457f5  lea     r11, [rsp+70h+var_s0]
0x1800457fa  mov     rbx, [r11+20h]
0x1800457fe  mov     rsi, [r11+28h]
0x180045802  mov     rsp, r11
0x180045805  pop     r14
0x180045807  pop     rdi
0x180045808  pop     rbp
0x180045809  retn
```
