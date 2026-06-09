# CMobileClipboard::RequestAccessAsync(CTxtRange *,ushort,ulong,Windows::ApplicationModel::DataTransfer::IDataPackageView *)

- ea: `0x1801f60ac`
- end: `0x1801f6410`
- name: `?RequestAccessAsync@CMobileClipboard@@AEAAJPEAVCTxtRange@@GKPEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(CMobileClipboard *__hidden this, struct CTxtRange *, unsigned __int16, unsigned int, struct Windows::ApplicationModel::DataTransfer::IDataPackageView *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801f5d00`

## callees

- `0x180048d5c`
- `0x1800498d0`
- `0x180100c98`
- `0x180122958`
- `0x18012a0a8`
- `0x18013bf4c`
- `0x180146168`
- `0x1801f5acc`
- `0x1801f5b68`
- `0x1801f5b98`
- `0x1801f60ac`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801f621a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801f621a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801f61c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801f61c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f61eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f61eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f6400`

## pseudocode

```c
__int64 __fastcall CMobileClipboard::RequestAccessAsync(
        CMobileClipboard *this,
        struct CTxtRange *a2,
        __int16 a3,
        int a4,
        struct Windows::ApplicationModel::DataTransfer::IDataPackageView *a5)
{
  __int64 v5; // r14
  CMobileClipboard *v9; // rdi
  CTxtEdit *v10; // r14
  struct Windows::ApplicationModel::DataTransfer::IDataPackageView *v11; // rsi
  unsigned int (__fastcall *v12)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v13; // rdi
  unsigned int (__fastcall *v14)(__int64, HSTRING *); // rbx
  HRESULT v15; // eax
  void (__fastcall **v17)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rax
  void (__fastcall *v18)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rbx
  void (__fastcall **v19)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rax
  void (__fastcall *v20)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *); // rbx
  __int64 v21; // r8
  int v22; // ebx
  __int64 v23; // r8
  void *v24; // rax
  __int64 v25; // rsi
  __int64 v26; // rdi
  unsigned int (__fastcall *v27)(__int64, __int64 *); // rbx
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  __int64 v29; // [rsp+28h] [rbp-58h] BYREF
  __int64 v30; // [rsp+30h] [rbp-50h] BYREF
  unsigned int (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h] BYREF
  HWND v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  void *v35; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v36[8]; // [rsp+60h] [rbp-20h] BYREF
  __int16 v37; // [rsp+68h] [rbp-18h]
  int v38; // [rsp+6Ch] [rbp-14h]
  int v39; // [rsp+70h] [rbp-10h]
  _BYTE v40[8]; // [rsp+78h] [rbp-8h] BYREF
  __int64 result; // [rsp+C8h] [rbp+48h] BYREF

  v5 = *((_QWORD *)a2 + 3);
  v9 = this;
  if ( !v5 )
    return 0;
  v10 = *(CTxtEdit **)(v5 + 40);
  if ( !v10 || (*((_DWORD *)v10 + 70) & 0x40000000) == 0 || !GetEdpProcs() || !g_pfnEdpGetIsManaged() )
    return 0;
  v11 = a5;
  string = 0;
  v31 = 0;
  v30 = 0;
  v12 = *(unsigned int (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a5 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  if ( !v12(v11, &v31) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    if ( !(**v31)(v31, &GUID_db764ce5_d174_495c_84fc_1a51f6ab45d7, &v30) )
    {
      v13 = v30;
      v14 = *(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      if ( !v14(v13, &string) )
      {
        LODWORD(result) = 0;
        v15 = WindowsCompareStringOrdinal(string, 0, (INT32 *)&result);
        if ( v15 < 0 )
        {
          RaiseException(v15, 1u, 0, 0);
          __debugbreak();
        }
        if ( !(_DWORD)result )
          goto LABEL_11;
      }
      v9 = this;
    }
  }
  v33 = 0;
  CTxtEdit::TxGetWindow(v10, &v33);
  if ( v33 )
  {
    v17 = *(void (__fastcall ***)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *))v11;
    result = 0;
    v18 = *v17;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&result);
    v18(v11, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, &result);
    if ( result )
      (*(void (__fastcall **)(__int64, HWND))(*(_QWORD *)result + 24LL))(result, v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&result);
  }
  v19 = *(void (__fastcall ***)(struct Windows::ApplicationModel::DataTransfer::IDataPackageView *, GUID *, __int64 *))v11;
  v29 = 0;
  v20 = *v19;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v20(v11, &GUID_d37771a8_ddad_4288_8428_d1cae394128b, &v29);
  if ( !v29 )
  {
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    WindowsDeleteString(string);
    return 0;
  }
  LOBYTE(v21) = 1;
  v32 = 0;
  Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(&v34, a2, v21);
  Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(
    &result,
    v11);
  v22 = *((unsigned __int8 *)v9 + 8);
  LOBYTE(v23) = 1;
  Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(v36, v34, v23);
  v37 = a3;
  v38 = a4;
  v39 = v22;
  Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(
    v40,
    result);
  v24 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v24;
  v25 = 0;
  if ( v24 )
  {
    v25 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::*)(Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,enum ABI::Windows::Foundation::AsyncStatus>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,enum ABI::Windows::Foundation::AsyncStatus>(
            v24,
            v36);
    v35 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>(&v35);
  _lambda_964c3c227b4279fb3195d73415ff5a95_::~_lambda_964c3c227b4279fb3195d73415ff5a95_((_lambda_964c3c227b4279fb3195d73415ff5a95_ *)v36);
  if ( !v25 )
  {
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&result);
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    goto LABEL_20;
  }
  v26 = v29;
  v27 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  if ( !v27(v26, &v32) )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 48LL))(v32, v25);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&result);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  WindowsDeleteString(string);
  return 1;
}

```

## disassembly

```asm
0x1801f60ac  mov     [rsp-38h+arg_10], rbx
0x1801f60b1  mov     [rsp-38h+arg_0], rcx
0x1801f60b6  push    rbp
0x1801f60b7  push    rsi
0x1801f60b8  push    rdi
0x1801f60b9  push    r12
0x1801f60bb  push    r13
0x1801f60bd  push    r14
0x1801f60bf  push    r15
0x1801f60c1  mov     rbp, rsp
0x1801f60c4  sub     rsp, 80h
0x1801f60cb  mov     r14, [rdx+18h]
0x1801f60cf  xor     ebx, ebx
0x1801f60d1  mov     r12d, r9d
0x1801f60d4  movzx   r13d, r8w
0x1801f60d8  mov     r15, rdx
0x1801f60db  mov     rdi, rcx
0x1801f60de  test    r14, r14
0x1801f60e1  jz      loc_1801F61F1
0x1801f60e7  mov     r14, [r14+28h]
0x1801f60eb  test    r14, r14
0x1801f60ee  jz      loc_1801F61F1
0x1801f60f4  test    dword ptr [r14+118h], 40000000h
0x1801f60ff  jz      loc_1801F61F1
0x1801f6105  call    ?GetEdpProcs@@YA_NXZ; GetEdpProcs(void)
0x1801f610a  test    al, al
0x1801f610c  jz      loc_1801F61F1
0x1801f6112  mov     rax, cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA; int (*g_pfnEdpGetIsManaged)(void)
0x1801f6119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f611e  test    eax, eax
0x1801f6120  jz      loc_1801F61F1
0x1801f6126  mov     rsi, [rbp+arg_20]
0x1801f612a  lea     rcx, [rbp+var_48]
0x1801f612e  mov     [rbp+string], rbx
0x1801f6132  mov     [rbp+var_48], rbx
0x1801f6136  mov     [rbp+var_50], rbx
0x1801f613a  mov     rax, [rsi]
0x1801f613d  mov     rbx, [rax+30h]
0x1801f6141  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6146  lea     rdx, [rbp+var_48]
0x1801f614a  mov     rcx, rsi
0x1801f614d  mov     rax, rbx
0x1801f6150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6155  test    eax, eax
0x1801f6157  jnz     loc_1801F6225
0x1801f615d  lea     rcx, [rbp+var_50]
0x1801f6161  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6166  mov     rcx, [rbp+var_48]
0x1801f616a  lea     r8, [rbp+var_50]
0x1801f616e  lea     rdx, _GUID_db764ce5_d174_495c_84fc_1a51f6ab45d7
0x1801f6175  mov     rax, [rcx]
0x1801f6178  mov     rax, [rax]
0x1801f617b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6180  test    eax, eax
0x1801f6182  jnz     loc_1801F6225
0x1801f6188  mov     rdi, [rbp+var_50]
0x1801f618c  mov     rcx, [rbp+string]; string
0x1801f6190  mov     rax, [rdi]
0x1801f6193  mov     rbx, [rax+30h]
0x1801f6197  call    cs:__imp_WindowsDeleteString
0x1801f619d  lea     rdx, [rbp+string]
0x1801f61a1  mov     [rbp+string], 0
0x1801f61a9  mov     rcx, rdi
0x1801f61ac  mov     rax, rbx
0x1801f61af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f61b4  test    eax, eax
0x1801f61b6  jnz     short loc_1801F6221
0x1801f61b8  mov     rcx, [rbp+string]; string1
0x1801f61bc  lea     r8, [rbp+result]; result
0x1801f61c0  xor     edx, edx; string2
0x1801f61c2  mov     dword ptr [rbp+result], eax
0x1801f61c5  call    cs:__imp_WindowsCompareStringOrdinal
0x1801f61cb  test    eax, eax
0x1801f61cd  js      short loc_1801F620E
0x1801f61cf  cmp     dword ptr [rbp+result], 0
0x1801f61d3  jnz     short loc_1801F6221
0x1801f61d5  lea     rcx, [rbp+var_50]
0x1801f61d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f61de  lea     rcx, [rbp+var_48]
0x1801f61e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f61e7  mov     rcx, [rbp+string]; string
0x1801f61eb  call    cs:__imp_WindowsDeleteString
0x1801f61f1  xor     eax, eax
0x1801f61f3  mov     rbx, [rsp+80h+arg_10]
0x1801f61fb  add     rsp, 80h
0x1801f6202  pop     r15
0x1801f6204  pop     r14
0x1801f6206  pop     r13
0x1801f6208  pop     r12
0x1801f620a  pop     rdi
0x1801f620b  pop     rsi
0x1801f620c  pop     rbp
0x1801f620d  retn
0x1801f620e  xor     r9d, r9d; lpArguments
0x1801f6211  xor     r8d, r8d; nNumberOfArguments
0x1801f6214  mov     ecx, eax; dwExceptionCode
0x1801f6216  lea     edx, [r9+1]; dwExceptionFlags
0x1801f621a  call    cs:__imp_RaiseException
0x1801f6220  int     3; Trap to Debugger
0x1801f6221  mov     rdi, [rbp+arg_0]
0x1801f6225  lea     rdx, [rbp+var_38]; HWND *
0x1801f6229  mov     [rbp+var_38], 0
0x1801f6231  mov     rcx, r14; this
0x1801f6234  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x1801f6239  xor     r14d, r14d
0x1801f623c  cmp     [rbp+var_38], r14
0x1801f6240  jz      short loc_1801F628D
0x1801f6242  mov     rax, [rsi]
0x1801f6245  lea     rcx, [rbp+result]
0x1801f6249  mov     [rbp+result], r14
0x1801f624d  mov     rbx, [rax]
0x1801f6250  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6255  lea     r8, [rbp+result]
0x1801f6259  mov     rcx, rsi
0x1801f625c  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x1801f6263  mov     rax, rbx
0x1801f6266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f626b  mov     rcx, [rbp+result]
0x1801f626f  test    rcx, rcx
0x1801f6272  jz      short loc_1801F6284
0x1801f6274  mov     rax, [rcx]
0x1801f6277  mov     rdx, [rbp+var_38]
0x1801f627b  mov     rax, [rax+18h]
0x1801f627f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6284  lea     rcx, [rbp+result]
0x1801f6288  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f628d  mov     rax, [rsi]
0x1801f6290  lea     rcx, [rbp+var_58]
0x1801f6294  mov     [rbp+var_58], r14
0x1801f6298  mov     rbx, [rax]
0x1801f629b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f62a0  lea     r8, [rbp+var_58]
0x1801f62a4  mov     rcx, rsi
0x1801f62a7  lea     rdx, _GUID_d37771a8_ddad_4288_8428_d1cae394128b
0x1801f62ae  mov     rax, rbx
0x1801f62b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f62b6  cmp     [rbp+var_58], r14
0x1801f62ba  jnz     short loc_1801F62CA
0x1801f62bc  lea     rcx, [rbp+var_58]
0x1801f62c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f62c5  jmp     loc_1801F61D5
0x1801f62ca  mov     r8b, 1
0x1801f62cd  mov     [rbp+var_40], r14
0x1801f62d1  mov     rdx, r15
0x1801f62d4  lea     rcx, [rbp+var_30]
0x1801f62d8  call    ??0?$TCntBase@PEAVCTxtRange@@V?$TCntPtr@VCTxtRange@@@Resp@@@Resp@@IEAA@PEAVCTxtRange@@_N@Z; Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(CTxtRange *,bool)
0x1801f62dd  mov     rdx, rsi
0x1801f62e0  lea     rcx, [rbp+result]
0x1801f62e4  call    ??0?$TCntBase@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@V?$TCntPtr@UIDataPackageView@DataTransfer@ApplicationModel@Windows@@@Resp@@@Resp@@IEAA@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@_N@Z; Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(Windows::ApplicationModel::DataTransfer::IDataPackageView *,bool)
0x1801f62e9  mov     rdx, [rbp+var_30]
0x1801f62ed  lea     rcx, [rbp+var_20]
0x1801f62f1  movzx   ebx, byte ptr [rdi+8]
0x1801f62f5  mov     r8b, 1
0x1801f62f8  call    ??0?$TCntBase@PEAVCTxtRange@@V?$TCntPtr@VCTxtRange@@@Resp@@@Resp@@IEAA@PEAVCTxtRange@@_N@Z; Resp::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>::TCntBase<CTxtRange *,Resp::TCntPtr<CTxtRange>>(CTxtRange *,bool)
0x1801f62fd  mov     rdx, [rbp+result]
0x1801f6301  lea     rcx, [rbp+var_8]
0x1801f6305  mov     [rbp+var_18], r13w
0x1801f630a  mov     [rbp+var_14], r12d
0x1801f630e  mov     [rbp+var_10], ebx
0x1801f6311  call    ??0?$TCntBase@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@V?$TCntPtr@UIDataPackageView@DataTransfer@ApplicationModel@Windows@@@Resp@@@Resp@@IEAA@PEAUIDataPackageView@DataTransfer@ApplicationModel@Windows@@_N@Z; Resp::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>::TCntBase<Windows::ApplicationModel::DataTransfer::IDataPackageView *,Resp::TCntPtr<Windows::ApplicationModel::DataTransfer::IDataPackageView>>(Windows::ApplicationModel::DataTransfer::IDataPackageView *,bool)
0x1801f6316  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801f631d  mov     ecx, 40h ; '@'; unsigned __int64
0x1801f6322  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801f6327  mov     [rbp+var_28], rax
0x1801f632b  mov     rsi, r14
0x1801f632e  test    rax, rax
0x1801f6331  jz      short loc_1801F6346
0x1801f6333  lea     rdx, [rbp+var_20]
0x1801f6337  mov     rcx, rax
0x1801f633a  call    ??0?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@AEAV_lambda_964c3c227b4279fb3195d73415ff5a95_@@$0?0PEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@QEAA@AEAV_lambda_964c3c227b4279fb3195d73415ff5a95_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>::*)(Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,ABI::Windows::Foundation::AsyncStatus>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult>>,_lambda_964c3c227b4279fb3195d73415ff5a95_ &,-1,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *,ABI::Windows::Foundation::AsyncStatus>(_lambda_964c3c227b4279fb3195d73415ff5a95_ &)
0x1801f633f  mov     rsi, rax
0x1801f6342  mov     [rbp+var_28], r14
0x1801f6346  lea     rcx, [rbp+var_28]
0x1801f634a  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAVCoreTextSelectionUpdatingEventArgs@2345@@Foundation@Windows@@V_lambda_0dc445f034a1f32a7567697cfa885cc1_@@$0?0PEAUICoreTextEditContext@Core@Text@UI@3@PEAUICoreTextSelectionUpdatingEventArgs@6783@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextEditContext@2345@@Internal@Foundation@Windows@@U?$AggregateType@PEAVCoreTextSelectionUpdatingEventArgs@Core@Text@UI@Windows@@PEAUICoreTextSelectionUpdatingEventArgs@2345@@234@@Foundation@Windows@@EAAJPEAUICoreTextEditContext@Core@Text@UI@3@PEAUICoreTextSelectionUpdatingEventArgs@5673@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>(void)
0x1801f634f  lea     rcx, [rbp+var_20]; this
0x1801f6353  call    ??1_lambda_964c3c227b4279fb3195d73415ff5a95_@@QEAA@XZ; _lambda_964c3c227b4279fb3195d73415ff5a95_::~_lambda_964c3c227b4279fb3195d73415ff5a95_(void)
0x1801f6358  test    rsi, rsi
0x1801f635b  jnz     short loc_1801F637D
0x1801f635d  lea     rcx, [rbp+result]; void *
0x1801f6361  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f6366  lea     rcx, [rbp+var_30]; void *
0x1801f636a  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f636f  lea     rcx, [rbp+var_40]
0x1801f6373  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6378  jmp     loc_1801F62BC
0x1801f637d  mov     rdi, [rbp+var_58]
0x1801f6381  lea     rcx, [rbp+var_40]
0x1801f6385  mov     rax, [rdi]
0x1801f6388  mov     rbx, [rax+30h]
0x1801f638c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f6391  lea     rdx, [rbp+var_40]
0x1801f6395  mov     rcx, rdi
0x1801f6398  mov     rax, rbx
0x1801f639b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f63a0  test    eax, eax
0x1801f63a2  jnz     short loc_1801F63B7
0x1801f63a4  mov     rcx, [rbp+var_40]
0x1801f63a8  mov     rdx, rsi
0x1801f63ab  mov     rax, [rcx]
0x1801f63ae  mov     rax, [rax+30h]
0x1801f63b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f63b7  mov     rax, [rsi]
0x1801f63ba  mov     rcx, rsi
0x1801f63bd  mov     rax, [rax+10h]
0x1801f63c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f63c6  lea     rcx, [rbp+result]; void *
0x1801f63ca  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f63cf  lea     rcx, [rbp+var_30]; void *
0x1801f63d3  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801f63d8  lea     rcx, [rbp+var_40]
0x1801f63dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f63e1  lea     rcx, [rbp+var_58]
0x1801f63e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f63ea  lea     rcx, [rbp+var_50]
0x1801f63ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f63f3  lea     rcx, [rbp+var_48]
0x1801f63f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f63fc  mov     rcx, [rbp+string]; string
0x1801f6400  call    cs:__imp_WindowsDeleteString
0x1801f6406  mov     eax, 1
0x1801f640b  jmp     loc_1801F61F3
```
