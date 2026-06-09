# AsyncMediaServiceCreateDocumentTransaction::_HandleSuccessResponse(void)

- ea: `0x1800acbe0`
- end: `0x1800acfcd`
- name: `?_HandleSuccessResponse@AsyncMediaServiceCreateDocumentTransaction@@EEAAJXZ`
- size: `1005`
- prototype: `__int64 __fastcall(AsyncMediaServiceCreateDocumentTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b7d4`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x180096cac`
- `0x18009d8a8`
- `0x1800a1b60`
- `0x1800aca4c`
- `0x1800acbe0`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800acd1d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800acd1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ace2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ace2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800accaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acdc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acf15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acf6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800accaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acdc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ace9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acf15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acf6b`

## string_xrefs

- `0x1800accf6`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall AsyncMediaServiceCreateDocumentTransaction::_HandleSuccessResponse(
        AsyncMediaServiceCreateDocumentTransaction *this)
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
    Log_HREvent_88(v3);
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
    Log_HREvent_88(v6);
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
    Log_HREvent_88(v4);
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
    Log_HREvent_88(ActivationFactory);
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
    Log_HREvent_88(v11);
    goto LABEL_15;
  }
  v13 = v34;
  string = 0;
  v14 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v34 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800FD828, v15);
  v4 = v14(v13, v16[1].Reserved.Reserved1, &string);
  if ( v4 < 0 )
    goto LABEL_18;
  v17 = *((_QWORD *)this + 11);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v17 + 24,
                           StringRawBuffer) )
  {
    v4 = -2147024882;
    Log_HREvent_69(-2147024882);
    Log_HREvent_88(-2147024882);
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
  v4 = CloudServiceTransaction::_HandleSuccessResponse(this);
  if ( v4 < 0 )
  {
LABEL_18:
    Log_HREvent_88(v4);
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
0x1800acbe0  mov     [rsp-8+arg_8], rbx
0x1800acbe5  mov     [rsp-8+arg_10], rsi
0x1800acbea  push    rbp
0x1800acbeb  push    rdi
0x1800acbec  push    r14
0x1800acbee  lea     rbp, [rsp-47h]
0x1800acbf3  sub     rsp, 90h
0x1800acbfa  mov     rax, cs:__security_cookie
0x1800acc01  xor     rax, rsp
0x1800acc04  mov     [rbp+57h+var_20], rax
0x1800acc08  mov     rsi, rcx
0x1800acc0b  lea     rdx, [rbp+57h+var_50]
0x1800acc0f  mov     rcx, [rcx+10h]
0x1800acc13  xor     r14d, r14d
0x1800acc16  mov     [rbp+57h+var_50], r14
0x1800acc1a  mov     rax, [rcx]
0x1800acc1d  mov     rax, [rax+30h]
0x1800acc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc26  mov     ebx, eax
0x1800acc28  test    eax, eax
0x1800acc2a  jns     short loc_1800ACC5B
0x1800acc2c  lea     edx, [r14+1]
0x1800acc30  mov     ecx, eax; int
0x1800acc32  lea     r9d, [r14+7Bh]
0x1800acc36  call    Log_HREvent_88
0x1800acc3b  mov     rdx, [rbp+57h+var_50]
0x1800acc3f  test    rdx, rdx
0x1800acc42  jz      loc_1800ACFA7
0x1800acc48  mov     [rbp+57h+var_50], r14
0x1800acc4c  mov     rcx, [rdx]
0x1800acc4f  mov     rax, [rcx+10h]
0x1800acc53  mov     rcx, rdx
0x1800acc56  jmp     loc_1800ACFA2
0x1800acc5b  mov     rcx, [rbp+57h+var_50]
0x1800acc5f  lea     rdx, [rbp+57h+var_48]
0x1800acc63  mov     [rbp+57h+var_48], r14
0x1800acc67  mov     rax, [rcx]
0x1800acc6a  mov     rax, [rax+50h]
0x1800acc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc73  mov     ebx, eax
0x1800acc75  test    eax, eax
0x1800acc77  jns     short loc_1800ACCA9
0x1800acc79  mov     edx, 1
0x1800acc7e  mov     ecx, eax; int
0x1800acc80  lea     r9d, [rdx+7Dh]
0x1800acc84  call    Log_HREvent_88
0x1800acc89  mov     rdx, [rbp+57h+var_48]
0x1800acc8d  test    rdx, rdx
0x1800acc90  jz      loc_1800ACF8E
0x1800acc96  mov     [rbp+57h+var_48], r14
0x1800acc9a  mov     rcx, [rdx]
0x1800acc9d  mov     rax, [rcx+10h]
0x1800acca1  mov     rcx, rdx
0x1800acca4  jmp     loc_1800ACF89
0x1800acca9  xor     ecx, ecx; string
0x1800accab  mov     [rbp+57h+var_40], r14
0x1800accaf  call    cs:__imp_WindowsDeleteString
0x1800accb5  mov     rdi, [rbp+57h+var_48]
0x1800accb9  mov     rcx, rdi
0x1800accbc  mov     [rbp+57h+var_40], r14
0x1800accc0  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x1800accc5  mov     ebx, eax
0x1800accc7  test    eax, eax
0x1800accc9  js      loc_1800ACF55
0x1800acccf  mov     rax, [rdi]
0x1800accd2  lea     rdx, [rbp+57h+var_40]
0x1800accd6  mov     rcx, rdi
0x1800accd9  mov     rax, [rax+50h]
0x1800accdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acce2  mov     ebx, eax
0x1800acce4  test    eax, eax
0x1800acce6  js      loc_1800ACF55
0x1800accec  mov     r9d, 1Ch; unsigned int
0x1800accf2  mov     [rbp+57h+var_38], r14
0x1800accf6  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800accfd  mov     [rbp+57h+var_58], r14
0x1800acd01  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800acd05  lea     r8d, [r9+1]; unsigned int
0x1800acd09  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800acd0e  mov     rcx, [rbp+57h+var_58]
0x1800acd12  lea     r8, [rbp+57h+var_38]
0x1800acd16  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1800acd1d  call    cs:__imp_RoGetActivationFactory
0x1800acd23  mov     ebx, eax
0x1800acd25  test    eax, eax
0x1800acd27  jns     short loc_1800ACD60
0x1800acd29  mov     edx, 1
0x1800acd2e  mov     r9d, 87h
0x1800acd34  mov     ecx, eax; int
0x1800acd36  call    Log_HREvent_88
0x1800acd3b  mov     rdx, [rbp+57h+var_38]
0x1800acd3f  test    rdx, rdx
0x1800acd42  jz      loc_1800ACF67
0x1800acd48  mov     [rbp+57h+var_38], r14
0x1800acd4c  mov     rcx, [rdx]
0x1800acd4f  mov     rax, [rcx+10h]
0x1800acd53  mov     rcx, rdx
0x1800acd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acd5b  jmp     loc_1800ACF67
0x1800acd60  mov     rcx, [rbp+57h+var_38]
0x1800acd64  lea     r8, [rbp+57h+var_28]
0x1800acd68  mov     rdx, [rbp+57h+var_40]
0x1800acd6c  mov     [rbp+57h+var_28], r14
0x1800acd70  mov     rax, [rcx]
0x1800acd73  mov     rax, [rax+30h]
0x1800acd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acd7c  mov     ebx, eax
0x1800acd7e  test    eax, eax
0x1800acd80  jns     short loc_1800ACDB7
0x1800acd82  mov     edx, 1
0x1800acd87  mov     r9d, 8Ah
0x1800acd8d  mov     ecx, eax; int
0x1800acd8f  call    Log_HREvent_88
0x1800acd94  lea     rcx, [rbp+57h+var_28]
0x1800acd98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800acd9d  mov     rcx, [rbp+57h+var_38]
0x1800acda1  test    rcx, rcx
0x1800acda4  jz      loc_1800ACF67
0x1800acdaa  mov     [rbp+57h+var_38], r14
0x1800acdae  mov     rax, [rcx]
0x1800acdb1  mov     rax, [rax+10h]
0x1800acdb5  jmp     short loc_1800ACD56
0x1800acdb7  mov     rdi, [rbp+57h+var_28]
0x1800acdbb  xor     ecx, ecx; string
0x1800acdbd  mov     [rbp+57h+string], r14
0x1800acdc1  mov     rax, [rdi]
0x1800acdc4  mov     rbx, [rax+50h]
0x1800acdc8  call    cs:__imp_WindowsDeleteString
0x1800acdce  lea     rdx, off_1800FD828; "id"
0x1800acdd5  mov     [rbp+57h+string], r14
0x1800acdd9  lea     rcx, [rbp+57h+hstringHeader]
0x1800acddd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800acde2  lea     r8, [rbp+57h+string]
0x1800acde6  mov     rcx, rdi
0x1800acde9  mov     rdx, [rax+18h]
0x1800acded  mov     rax, rbx
0x1800acdf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdf5  mov     ebx, eax
0x1800acdf7  test    eax, eax
0x1800acdf9  jns     short loc_1800ACE20
0x1800acdfb  mov     r9d, 8Dh
0x1800ace01  mov     edx, 1
0x1800ace06  mov     ecx, ebx; int
0x1800ace08  call    Log_HREvent_88
0x1800ace0d  mov     rcx, [rbp+57h+string]; string
0x1800ace11  call    cs:__imp_WindowsDeleteString
0x1800ace17  mov     [rbp+57h+string], r14
0x1800ace1b  jmp     loc_1800ACD94
0x1800ace20  mov     rcx, [rbp+57h+string]; string
0x1800ace24  xor     edx, edx; length
0x1800ace26  mov     rbx, [rsi+58h]
0x1800ace2a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ace30  mov     rdx, rax
0x1800ace33  lea     rcx, [rbx+18h]
0x1800ace37  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800ace3c  test    al, al
0x1800ace3e  jnz     loc_1800ACEC8
0x1800ace44  xor     edx, edx
0x1800ace46  mov     ebx, 8007000Eh
0x1800ace4b  mov     ecx, ebx; int
0x1800ace4d  lea     r9d, [rdx+57h]
0x1800ace51  call    Log_HREvent_69
0x1800ace56  mov     edx, 1
0x1800ace5b  mov     r9d, 8Fh
0x1800ace61  mov     ecx, ebx; int
0x1800ace63  call    Log_HREvent_88
0x1800ace68  mov     rcx, [rbp+57h+string]; string
0x1800ace6c  call    cs:__imp_WindowsDeleteString
0x1800ace72  lea     rcx, [rbp+57h+var_28]
0x1800ace76  mov     [rbp+57h+string], r14
0x1800ace7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ace7f  mov     rcx, [rbp+57h+var_38]
0x1800ace83  test    rcx, rcx
0x1800ace86  jz      short loc_1800ACE98
0x1800ace88  mov     [rbp+57h+var_38], r14
0x1800ace8c  mov     rax, [rcx]
0x1800ace8f  mov     rax, [rax+10h]
0x1800ace93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace98  mov     rcx, [rbp+57h+var_40]; string
0x1800ace9c  call    cs:__imp_WindowsDeleteString
0x1800acea2  mov     rcx, [rbp+57h+var_48]
0x1800acea6  mov     [rbp+57h+var_40], r14
0x1800aceaa  test    rcx, rcx
0x1800acead  jz      loc_1800ACC3B
0x1800aceb3  mov     [rbp+57h+var_48], r14
0x1800aceb7  mov     rax, [rcx]
0x1800aceba  mov     rax, [rax+10h]
0x1800acebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acec3  jmp     loc_1800ACC3B
0x1800acec8  mov     rcx, rsi; this
0x1800acecb  call    ?_HandleSuccessResponse@CloudServiceTransaction@@MEAAJXZ; CloudServiceTransaction::_HandleSuccessResponse(void)
0x1800aced0  mov     ebx, eax
0x1800aced2  test    eax, eax
0x1800aced4  jns     short loc_1800ACEE1
0x1800aced6  mov     r9d, 92h
0x1800acedc  jmp     loc_1800ACE01
0x1800acee1  mov     rcx, [rbp+57h+string]; string
0x1800acee5  call    cs:__imp_WindowsDeleteString
0x1800aceeb  lea     rcx, [rbp+57h+var_28]
0x1800aceef  mov     [rbp+57h+string], r14
0x1800acef3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800acef8  mov     rcx, [rbp+57h+var_38]
0x1800acefc  test    rcx, rcx
0x1800aceff  jz      short loc_1800ACF11
0x1800acf01  mov     [rbp+57h+var_38], r14
0x1800acf05  mov     rax, [rcx]
0x1800acf08  mov     rax, [rax+10h]
0x1800acf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf11  mov     rcx, [rbp+57h+var_40]; string
0x1800acf15  call    cs:__imp_WindowsDeleteString
0x1800acf1b  mov     rcx, [rbp+57h+var_48]
0x1800acf1f  mov     [rbp+57h+var_40], r14
0x1800acf23  test    rcx, rcx
0x1800acf26  jz      short loc_1800ACF38
0x1800acf28  mov     [rbp+57h+var_48], r14
0x1800acf2c  mov     rax, [rcx]
0x1800acf2f  mov     rax, [rax+10h]
0x1800acf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf38  mov     rcx, [rbp+57h+var_50]
0x1800acf3c  test    rcx, rcx
0x1800acf3f  jz      short loc_1800ACF51
0x1800acf41  mov     [rbp+57h+var_50], r14
0x1800acf45  mov     rax, [rcx]
0x1800acf48  mov     rax, [rax+10h]
0x1800acf4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf51  xor     eax, eax
0x1800acf53  jmp     short loc_1800ACFA9
0x1800acf55  mov     edx, 1
0x1800acf5a  mov     r9d, 81h
0x1800acf60  mov     ecx, ebx; int
0x1800acf62  call    Log_HREvent_88
0x1800acf67  mov     rcx, [rbp+57h+var_40]; string
0x1800acf6b  call    cs:__imp_WindowsDeleteString
0x1800acf71  mov     rcx, [rbp+57h+var_48]
0x1800acf75  mov     [rbp+57h+var_40], r14
0x1800acf79  test    rcx, rcx
0x1800acf7c  jz      short loc_1800ACF8E
0x1800acf7e  mov     [rbp+57h+var_48], r14
0x1800acf82  mov     rax, [rcx]
0x1800acf85  mov     rax, [rax+10h]
0x1800acf89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf8e  mov     rcx, [rbp+57h+var_50]
0x1800acf92  test    rcx, rcx
0x1800acf95  jz      short loc_1800ACFA7
0x1800acf97  mov     [rbp+57h+var_50], r14
0x1800acf9b  mov     rax, [rcx]
0x1800acf9e  mov     rax, [rax+10h]
0x1800acfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acfa7  mov     eax, ebx
0x1800acfa9  mov     rcx, [rbp+57h+var_20]
0x1800acfad  xor     rcx, rsp; StackCookie
0x1800acfb0  call    __security_check_cookie
0x1800acfb5  lea     r11, [rsp+0A0h+var_10]
0x1800acfbd  mov     rbx, [r11+28h]
0x1800acfc1  mov     rsi, [r11+30h]
0x1800acfc5  mov     rsp, r11
0x1800acfc8  pop     r14
0x1800acfca  pop     rdi
0x1800acfcb  pop     rbp
0x1800acfcc  retn
```
