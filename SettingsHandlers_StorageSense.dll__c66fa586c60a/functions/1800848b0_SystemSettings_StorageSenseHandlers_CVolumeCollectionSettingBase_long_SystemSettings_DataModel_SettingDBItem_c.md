# SystemSettings::StorageSenseHandlers::CVolumeCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(HSTRING__ *,IInspectable *)

- ea: `0x1800848b0`
- end: `0x180084a8f`
- name: `?SetValue@?$CVolumeCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077ec`
- `0x180009d6c`
- `0x18000c964`
- `0x18000e6cc`
- `0x18001f688`
- `0x18005cc94`
- `0x1800724d4`
- `0x180082ba8`
- `0x180082cec`
- `0x1800848b0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180084a19`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180084a19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008494d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800849b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008494d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800849b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008497d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008497d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180084a88`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180084a88`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CVolumeCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(
        __int64 a1,
        SystemSettings::DataModel *a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  const unsigned __int16 *v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  PCWSTR StringRawBuffer; // rax
  _QWORD *v16; // rbx
  _QWORD *v17; // rax
  int v18; // [rsp+20h] [rbp-30h]
  __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING string; // [rsp+80h] [rbp+30h] BYREF
  __int64 v25; // [rsp+88h] [rbp+38h] BYREF

  v25 = 0;
  v6 = **a3;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
  v7 = v6(a3, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v25);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\volumes.cpp",
      (const char *)(unsigned int)v7,
      v18);
LABEL_9:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
    return v9;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A0E0, v8) )
  {
    string = 0;
    v10 = v25;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 152LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, &string);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 614;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\volumes.cpp",
        (const char *)(unsigned int)v12,
        v18);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_9;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            a1 + 312,
            StringRawBuffer,
            -1);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 617;
      goto LABEL_8;
    }
    v16 = (_QWORD *)_lambda_6a6dc3da692db91f482af15795b92753_::_lambda_6a6dc3da692db91f482af15795b92753_(v20, a1);
    v17 = operator new(8u);
    *v17 = *v16;
    v21 = _o__beginthreadex(
            0,
            0,
            std::thread::_Invoke<std::tuple<_lambda_6a6dc3da692db91f482af15795b92753_>,0>,
            v17,
            0,
            &v22,
            v17);
    if ( !v21 )
    {
      v22 = 0;
      std::_Throw_Cpp_error(6);
      JUMPOUT(0x180084A8ELL);
    }
    v19 = 0;
    std::unique_ptr<std::tuple<_lambda_2330f253cad904fd380e24c161b15496_>>::~unique_ptr<std::tuple<_lambda_2330f253cad904fd380e24c161b15496_>>(&v19);
    std::thread::operator=(a1 + 352, &v21);
    std::thread::~thread((std::thread *)&v21);
    WindowsDeleteString(string);
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
  return 0;
}

```

## disassembly

```asm
0x1800848b0  mov     [rsp-18h+arg_0], rbx
0x1800848b5  mov     [rsp-18h+arg_8], rsi
0x1800848ba  push    rbp
0x1800848bb  push    rdi
0x1800848bc  push    r14
0x1800848be  mov     rbp, rsp
0x1800848c1  sub     rsp, 50h
0x1800848c5  mov     rdi, r8
0x1800848c8  mov     r14, rdx
0x1800848cb  mov     rsi, rcx
0x1800848ce  mov     [rbp+arg_18], 0
0x1800848d6  mov     rax, [r8]
0x1800848d9  mov     rbx, [rax]
0x1800848dc  lea     rcx, [rbp+arg_18]
0x1800848e0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800848e5  lea     r8, [rbp+arg_18]
0x1800848e9  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800848f0  mov     rcx, rdi
0x1800848f3  mov     rax, rbx
0x1800848f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800848fb  mov     ebx, eax
0x1800848fd  test    eax, eax
0x1800848ff  jns     short loc_18008491E
0x180084901  mov     rcx, [rbp+18h]; this
0x180084905  mov     r9d, eax; char *
0x180084908  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\coresettinghandlers"...
0x18008490f  mov     edx, 260h; void *
0x180084914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084919  jmp     loc_1800849C7
0x18008491e  lea     rdx, stru_18010A0E0; HSTRING
0x180084925  mov     rcx, r14; this
0x180084928  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18008492d  test    al, al
0x18008492f  jz      loc_180084A5E
0x180084935  mov     [rbp+string], 0
0x18008493d  mov     rdi, [rbp+arg_18]
0x180084941  mov     rax, [rdi]
0x180084944  mov     rbx, [rax+98h]
0x18008494b  xor     ecx, ecx; string
0x18008494d  call    cs:__imp_WindowsDeleteString
0x180084953  mov     [rbp+string], 0
0x18008495b  lea     rdx, [rbp+string]
0x18008495f  mov     rcx, rdi
0x180084962  mov     rax, rbx
0x180084965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008496a  mov     ebx, eax
0x18008496c  test    eax, eax
0x18008496e  jns     short loc_180084977
0x180084970  mov     edx, 266h
0x180084975  jmp     short loc_1800849A1
0x180084977  xor     edx, edx; length
0x180084979  mov     rcx, [rbp+string]; string
0x18008497d  call    cs:__imp_WindowsGetStringRawBuffer
0x180084983  or      r8, 0FFFFFFFFFFFFFFFFh
0x180084987  mov     rdx, rax
0x18008498a  lea     rcx, [rsi+138h]
0x180084991  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180084996  mov     ebx, eax
0x180084998  test    eax, eax
0x18008499a  jns     short loc_1800849D7
0x18008499c  mov     edx, 269h; void *
0x1800849a1  mov     r9d, eax; char *
0x1800849a4  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\coresettinghandlers"...
0x1800849ab  mov     rcx, [rbp+18h]; this
0x1800849af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800849b4  nop
0x1800849b5  mov     rcx, [rbp+string]; string
0x1800849b9  call    cs:__imp_WindowsDeleteString
0x1800849bf  mov     [rbp+string], 0
0x1800849c7  lea     rcx, [rbp+arg_18]
0x1800849cb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800849d0  mov     eax, ebx
0x1800849d2  jmp     loc_180084A69
0x1800849d7  mov     rdx, rsi
0x1800849da  lea     rcx, [rbp+var_18]
0x1800849de  call    ??0_lambda_6a6dc3da692db91f482af15795b92753_@@QEAA@PEAV?$CVolumeCollectionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAUIUser@System@Windows@@PEAPEAUISettingItem@23@@Z@StorageSenseHandlers@SystemSettings@@@Z; _lambda_6a6dc3da692db91f482af15795b92753_::_lambda_6a6dc3da692db91f482af15795b92753_(SystemSettings::StorageSenseHandlers::CVolumeCollectionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,Windows::System::IUser *,SystemSettings::DataModel::ISettingItem * *)> *)
0x1800849e3  mov     rbx, rax
0x1800849e6  mov     ecx, 8; Size
0x1800849eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800849f0  mov     rcx, [rbx]
0x1800849f3  mov     [rax], rcx
0x1800849f6  mov     [rbp+var_20], rax
0x1800849fa  lea     rcx, [rbp+var_8]
0x1800849fe  mov     [rsp+50h+var_28], rcx
0x180084a03  mov     [rsp+50h+var_30], 0
0x180084a0b  mov     r9, rax
0x180084a0e  lea     r8, ??$_Invoke@V?$tuple@V_lambda_6a6dc3da692db91f482af15795b92753_@@@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<_lambda_6a6dc3da692db91f482af15795b92753_>,0>(void *)
0x180084a15  xor     edx, edx
0x180084a17  xor     ecx, ecx
0x180084a19  call    cs:__imp__o__beginthreadex
0x180084a1f  mov     [rbp+var_10], rax
0x180084a23  test    rax, rax
0x180084a26  jz      short loc_180084A7C
0x180084a28  mov     [rbp+var_20], 0
0x180084a30  lea     rcx, [rbp+var_20]
0x180084a34  call    ??1?$unique_ptr@V?$tuple@V_lambda_2330f253cad904fd380e24c161b15496_@@@std@@U?$default_delete@V?$tuple@V_lambda_2330f253cad904fd380e24c161b15496_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_2330f253cad904fd380e24c161b15496_>>::~unique_ptr<std::tuple<_lambda_2330f253cad904fd380e24c161b15496_>>(void)
0x180084a39  lea     rcx, [rsi+160h]
0x180084a40  lea     rdx, [rbp+var_10]
0x180084a44  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x180084a49  lea     rcx, [rbp+var_10]; this
0x180084a4d  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180084a52  nop
0x180084a53  mov     rcx, [rbp+string]; string
0x180084a57  call    cs:__imp_WindowsDeleteString
0x180084a5d  nop
0x180084a5e  lea     rcx, [rbp+arg_18]
0x180084a62  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180084a67  xor     eax, eax
0x180084a69  mov     rbx, [rsp+50h+arg_0]
0x180084a6e  mov     rsi, [rsp+50h+arg_8]
0x180084a73  add     rsp, 50h
0x180084a77  pop     r14
0x180084a79  pop     rdi
0x180084a7a  pop     rbp
0x180084a7b  retn
0x180084a7c  mov     [rbp+var_8], 0
0x180084a83  mov     ecx, 6
0x180084a88  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
