# ChatServiceUploadConversationTransaction::_HandleSuccessResponse(void)

- ea: `0x1800a73c0`
- end: `0x1800a77ab`
- name: `?_HandleSuccessResponse@ChatServiceUploadConversationTransaction@@EEAAJXZ`
- size: `1003`
- prototype: `__int64 __fastcall(ChatServiceUploadConversationTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x18008f830`
- `0x18009d8a8`
- `0x1800a2920`
- `0x1800a722c`
- `0x1800a73c0`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a74fd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a74fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a760a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a760a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a748f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a764c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a767c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a76c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a76f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a748f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a75f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a764c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a767c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a76c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a76f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7749`

## string_xrefs

- `0x1800a74d6`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceUploadConversationTransaction::_HandleSuccessResponse(
        ChatServiceUploadConversationTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rdx
  int (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rdi
  int ActivationFactory; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, HSTRING *); // rbx
  char v15; // r8
  HSTRING_HEADER *v16; // rax
  __int64 v17; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rcx
  int (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v21; // rcx
  int (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v23; // rcx
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v26; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-19h] BYREF
  __int64 v28; // [rsp+48h] [rbp-1h]
  __int64 v29; // [rsp+50h] [rbp+7h] BYREF
  int (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp+Fh] BYREF
  HSTRING v31; // [rsp+60h] [rbp+17h] BYREF
  __int64 v32; // [rsp+68h] [rbp+1Fh] BYREF
  HSTRING string; // [rsp+70h] [rbp+27h] BYREF
  __int64 v34; // [rsp+78h] [rbp+2Fh] BYREF

  v2 = *((_QWORD *)this + 2);
  v29 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, &v29);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_82(v3);
LABEL_3:
    v5 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)v4;
  }
  v30 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v29 + 80LL))(
         v29,
         &v30);
  v4 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_82(v6);
    v7 = v30;
    if ( v30 )
    {
      v30 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v7)[2])(v7);
    }
LABEL_35:
    v26 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return (unsigned int)v4;
  }
  v31 = 0;
  WindowsDeleteString(0);
  v8 = v30;
  v31 = 0;
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(v30);
  if ( v4 < 0
    || (v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v8)[10])(v8, &v31),
        v4 < 0) )
  {
    Log_HREvent_82(v4);
LABEL_33:
    WindowsDeleteString(v31);
    v25 = v30;
    v31 = 0;
    if ( v30 )
    {
      v30 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v25)[2])(v25);
    }
    goto LABEL_35;
  }
  v32 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  ActivationFactory = RoGetActivationFactory(v28, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v32);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_82(ActivationFactory);
    v10 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    goto LABEL_33;
  }
  v34 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, v31, &v34);
  v4 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent_82(v11);
    goto LABEL_15;
  }
  v13 = v34;
  string = 0;
  v14 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v34 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD818, v15);
  v4 = v14(v13, v16[1].Reserved.Reserved1, &string);
  if ( v4 < 0 )
    goto LABEL_18;
  v17 = *((_QWORD *)this + 12);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v17 + 56,
                           StringRawBuffer) )
  {
    v4 = -2147024882;
    Log_HREvent_67(-2147024882);
    Log_HREvent_82(-2147024882);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v19 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    WindowsDeleteString(v31);
    v20 = v30;
    v31 = 0;
    if ( v30 )
    {
      v30 = 0;
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v20)[2])(v20);
    }
    goto LABEL_3;
  }
  v4 = ChatServiceTransaction::_HandleSuccessResponse(this);
  if ( v4 < 0 )
  {
LABEL_18:
    Log_HREvent_82(v4);
    WindowsDeleteString(string);
    string = 0;
LABEL_15:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v12 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_33;
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v21 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  WindowsDeleteString(v31);
  v22 = v30;
  v31 = 0;
  if ( v30 )
  {
    v30 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
  }
  v23 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a73c0  mov     [rsp-8+arg_8], rbx
0x1800a73c5  mov     [rsp-8+arg_10], rsi
0x1800a73ca  push    rbp
0x1800a73cb  push    rdi
0x1800a73cc  push    r14
0x1800a73ce  lea     rbp, [rsp-47h]
0x1800a73d3  sub     rsp, 90h
0x1800a73da  mov     rax, cs:__security_cookie
0x1800a73e1  xor     rax, rsp
0x1800a73e4  mov     [rbp+57h+var_20], rax
0x1800a73e8  mov     rsi, rcx
0x1800a73eb  lea     rdx, [rbp+57h+var_50]
0x1800a73ef  mov     rcx, [rcx+10h]
0x1800a73f3  xor     r14d, r14d
0x1800a73f6  mov     [rbp+57h+var_50], r14
0x1800a73fa  mov     rax, [rcx]
0x1800a73fd  mov     rax, [rax+30h]
0x1800a7401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7406  mov     ebx, eax
0x1800a7408  test    eax, eax
0x1800a740a  jns     short loc_1800A743B
0x1800a740c  lea     edx, [r14+1]
0x1800a7410  mov     ecx, eax; int
0x1800a7412  lea     r9d, [r14+76h]
0x1800a7416  call    Log_HREvent_82
0x1800a741b  mov     rdx, [rbp+57h+var_50]
0x1800a741f  test    rdx, rdx
0x1800a7422  jz      loc_1800A7785
0x1800a7428  mov     [rbp+57h+var_50], r14
0x1800a742c  mov     rcx, [rdx]
0x1800a742f  mov     rax, [rcx+10h]
0x1800a7433  mov     rcx, rdx
0x1800a7436  jmp     loc_1800A7780
0x1800a743b  mov     rcx, [rbp+57h+var_50]
0x1800a743f  lea     rdx, [rbp+57h+var_48]
0x1800a7443  mov     [rbp+57h+var_48], r14
0x1800a7447  mov     rax, [rcx]
0x1800a744a  mov     rax, [rax+50h]
0x1800a744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7453  mov     ebx, eax
0x1800a7455  test    eax, eax
0x1800a7457  jns     short loc_1800A7489
0x1800a7459  mov     edx, 1
0x1800a745e  mov     ecx, eax; int
0x1800a7460  lea     r9d, [rdx+78h]
0x1800a7464  call    Log_HREvent_82
0x1800a7469  mov     rdx, [rbp+57h+var_48]
0x1800a746d  test    rdx, rdx
0x1800a7470  jz      loc_1800A776C
0x1800a7476  mov     [rbp+57h+var_48], r14
0x1800a747a  mov     rcx, [rdx]
0x1800a747d  mov     rax, [rcx+10h]
0x1800a7481  mov     rcx, rdx
0x1800a7484  jmp     loc_1800A7767
0x1800a7489  xor     ecx, ecx; string
0x1800a748b  mov     [rbp+57h+var_40], r14
0x1800a748f  call    cs:__imp_WindowsDeleteString
0x1800a7495  mov     rdi, [rbp+57h+var_48]
0x1800a7499  mov     rcx, rdi
0x1800a749c  mov     [rbp+57h+var_40], r14
0x1800a74a0  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x1800a74a5  mov     ebx, eax
0x1800a74a7  test    eax, eax
0x1800a74a9  js      loc_1800A7735
0x1800a74af  mov     rax, [rdi]
0x1800a74b2  lea     rdx, [rbp+57h+var_40]
0x1800a74b6  mov     rcx, rdi
0x1800a74b9  mov     rax, [rax+50h]
0x1800a74bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a74c2  mov     ebx, eax
0x1800a74c4  test    eax, eax
0x1800a74c6  js      loc_1800A7735
0x1800a74cc  mov     r9d, 1Ch; unsigned int
0x1800a74d2  mov     [rbp+57h+var_38], r14
0x1800a74d6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800a74dd  mov     [rbp+57h+var_58], r14
0x1800a74e1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800a74e5  lea     r8d, [r9+1]; unsigned int
0x1800a74e9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a74ee  mov     rcx, [rbp+57h+var_58]
0x1800a74f2  lea     r8, [rbp+57h+var_38]
0x1800a74f6  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1800a74fd  call    cs:__imp_RoGetActivationFactory
0x1800a7503  mov     ebx, eax
0x1800a7505  test    eax, eax
0x1800a7507  jns     short loc_1800A7540
0x1800a7509  mov     edx, 1
0x1800a750e  mov     r9d, 81h
0x1800a7514  mov     ecx, eax; int
0x1800a7516  call    Log_HREvent_82
0x1800a751b  mov     rdx, [rbp+57h+var_38]
0x1800a751f  test    rdx, rdx
0x1800a7522  jz      loc_1800A7745
0x1800a7528  mov     [rbp+57h+var_38], r14
0x1800a752c  mov     rcx, [rdx]
0x1800a752f  mov     rax, [rcx+10h]
0x1800a7533  mov     rcx, rdx
0x1800a7536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a753b  jmp     loc_1800A7745
0x1800a7540  mov     rcx, [rbp+57h+var_38]
0x1800a7544  lea     r8, [rbp+57h+var_28]
0x1800a7548  mov     rdx, [rbp+57h+var_40]
0x1800a754c  mov     [rbp+57h+var_28], r14
0x1800a7550  mov     rax, [rcx]
0x1800a7553  mov     rax, [rax+30h]
0x1800a7557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a755c  mov     ebx, eax
0x1800a755e  test    eax, eax
0x1800a7560  jns     short loc_1800A7597
0x1800a7562  mov     edx, 1
0x1800a7567  mov     r9d, 84h
0x1800a756d  mov     ecx, eax; int
0x1800a756f  call    Log_HREvent_82
0x1800a7574  lea     rcx, [rbp+57h+var_28]
0x1800a7578  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a757d  mov     rcx, [rbp+57h+var_38]
0x1800a7581  test    rcx, rcx
0x1800a7584  jz      loc_1800A7745
0x1800a758a  mov     [rbp+57h+var_38], r14
0x1800a758e  mov     rax, [rcx]
0x1800a7591  mov     rax, [rax+10h]
0x1800a7595  jmp     short loc_1800A7536
0x1800a7597  mov     rdi, [rbp+57h+var_28]
0x1800a759b  xor     ecx, ecx; string
0x1800a759d  mov     [rbp+57h+string], r14
0x1800a75a1  mov     rax, [rdi]
0x1800a75a4  mov     rbx, [rax+50h]
0x1800a75a8  call    cs:__imp_WindowsDeleteString
0x1800a75ae  lea     rdx, off_1800FD818; "id"
0x1800a75b5  mov     [rbp+57h+string], r14
0x1800a75b9  lea     rcx, [rbp+57h+hstringHeader]
0x1800a75bd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a75c2  lea     r8, [rbp+57h+string]
0x1800a75c6  mov     rcx, rdi
0x1800a75c9  mov     rdx, [rax+18h]
0x1800a75cd  mov     rax, rbx
0x1800a75d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a75d5  mov     ebx, eax
0x1800a75d7  test    eax, eax
0x1800a75d9  jns     short loc_1800A7600
0x1800a75db  mov     r9d, 87h
0x1800a75e1  mov     edx, 1
0x1800a75e6  mov     ecx, ebx; int
0x1800a75e8  call    Log_HREvent_82
0x1800a75ed  mov     rcx, [rbp+57h+string]; string
0x1800a75f1  call    cs:__imp_WindowsDeleteString
0x1800a75f7  mov     [rbp+57h+string], r14
0x1800a75fb  jmp     loc_1800A7574
0x1800a7600  mov     rcx, [rbp+57h+string]; string
0x1800a7604  xor     edx, edx; length
0x1800a7606  mov     rbx, [rsi+60h]
0x1800a760a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a7610  mov     rdx, rax
0x1800a7613  lea     rcx, [rbx+38h]
0x1800a7617  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a761c  test    al, al
0x1800a761e  jnz     loc_1800A76A8
0x1800a7624  xor     edx, edx
0x1800a7626  mov     ebx, 8007000Eh
0x1800a762b  mov     ecx, ebx; int
0x1800a762d  lea     r9d, [rdx+64h]
0x1800a7631  call    Log_HREvent_67
0x1800a7636  mov     edx, 1
0x1800a763b  mov     r9d, 89h
0x1800a7641  mov     ecx, ebx; int
0x1800a7643  call    Log_HREvent_82
0x1800a7648  mov     rcx, [rbp+57h+string]; string
0x1800a764c  call    cs:__imp_WindowsDeleteString
0x1800a7652  lea     rcx, [rbp+57h+var_28]
0x1800a7656  mov     [rbp+57h+string], r14
0x1800a765a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a765f  mov     rcx, [rbp+57h+var_38]
0x1800a7663  test    rcx, rcx
0x1800a7666  jz      short loc_1800A7678
0x1800a7668  mov     [rbp+57h+var_38], r14
0x1800a766c  mov     rax, [rcx]
0x1800a766f  mov     rax, [rax+10h]
0x1800a7673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7678  mov     rcx, [rbp+57h+var_40]; string
0x1800a767c  call    cs:__imp_WindowsDeleteString
0x1800a7682  mov     rcx, [rbp+57h+var_48]
0x1800a7686  mov     [rbp+57h+var_40], r14
0x1800a768a  test    rcx, rcx
0x1800a768d  jz      loc_1800A741B
0x1800a7693  mov     [rbp+57h+var_48], r14
0x1800a7697  mov     rax, [rcx]
0x1800a769a  mov     rax, [rax+10h]
0x1800a769e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a76a3  jmp     loc_1800A741B
0x1800a76a8  mov     rcx, rsi; this
0x1800a76ab  call    ?_HandleSuccessResponse@ChatServiceTransaction@@MEAAJXZ; ChatServiceTransaction::_HandleSuccessResponse(void)
0x1800a76b0  mov     ebx, eax
0x1800a76b2  test    eax, eax
0x1800a76b4  jns     short loc_1800A76C1
0x1800a76b6  mov     r9d, 8Ch
0x1800a76bc  jmp     loc_1800A75E1
0x1800a76c1  mov     rcx, [rbp+57h+string]; string
0x1800a76c5  call    cs:__imp_WindowsDeleteString
0x1800a76cb  lea     rcx, [rbp+57h+var_28]
0x1800a76cf  mov     [rbp+57h+string], r14
0x1800a76d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a76d8  mov     rcx, [rbp+57h+var_38]
0x1800a76dc  test    rcx, rcx
0x1800a76df  jz      short loc_1800A76F1
0x1800a76e1  mov     [rbp+57h+var_38], r14
0x1800a76e5  mov     rax, [rcx]
0x1800a76e8  mov     rax, [rax+10h]
0x1800a76ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a76f1  mov     rcx, [rbp+57h+var_40]; string
0x1800a76f5  call    cs:__imp_WindowsDeleteString
0x1800a76fb  mov     rcx, [rbp+57h+var_48]
0x1800a76ff  mov     [rbp+57h+var_40], r14
0x1800a7703  test    rcx, rcx
0x1800a7706  jz      short loc_1800A7718
0x1800a7708  mov     [rbp+57h+var_48], r14
0x1800a770c  mov     rax, [rcx]
0x1800a770f  mov     rax, [rax+10h]
0x1800a7713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7718  mov     rcx, [rbp+57h+var_50]
0x1800a771c  test    rcx, rcx
0x1800a771f  jz      short loc_1800A7731
0x1800a7721  mov     [rbp+57h+var_50], r14
0x1800a7725  mov     rax, [rcx]
0x1800a7728  mov     rax, [rax+10h]
0x1800a772c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7731  xor     eax, eax
0x1800a7733  jmp     short loc_1800A7787
0x1800a7735  mov     edx, 1
0x1800a773a  mov     ecx, ebx; int
0x1800a773c  lea     r9d, [rdx+7Bh]
0x1800a7740  call    Log_HREvent_82
0x1800a7745  mov     rcx, [rbp+57h+var_40]; string
0x1800a7749  call    cs:__imp_WindowsDeleteString
0x1800a774f  mov     rcx, [rbp+57h+var_48]
0x1800a7753  mov     [rbp+57h+var_40], r14
0x1800a7757  test    rcx, rcx
0x1800a775a  jz      short loc_1800A776C
0x1800a775c  mov     [rbp+57h+var_48], r14
0x1800a7760  mov     rax, [rcx]
0x1800a7763  mov     rax, [rax+10h]
0x1800a7767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a776c  mov     rcx, [rbp+57h+var_50]
0x1800a7770  test    rcx, rcx
0x1800a7773  jz      short loc_1800A7785
0x1800a7775  mov     [rbp+57h+var_50], r14
0x1800a7779  mov     rax, [rcx]
0x1800a777c  mov     rax, [rax+10h]
0x1800a7780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7785  mov     eax, ebx
0x1800a7787  mov     rcx, [rbp+57h+var_20]
0x1800a778b  xor     rcx, rsp; StackCookie
0x1800a778e  call    __security_check_cookie
0x1800a7793  lea     r11, [rsp+0A0h+var_10]
0x1800a779b  mov     rbx, [r11+28h]
0x1800a779f  mov     rsi, [r11+30h]
0x1800a77a3  mov     rsp, r11
0x1800a77a6  pop     r14
0x1800a77a8  pop     rdi
0x1800a77a9  pop     rbp
0x1800a77aa  retn
```
