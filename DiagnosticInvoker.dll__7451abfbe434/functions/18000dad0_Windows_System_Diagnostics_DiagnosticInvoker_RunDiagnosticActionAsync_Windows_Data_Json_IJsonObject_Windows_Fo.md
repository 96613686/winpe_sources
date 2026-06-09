# Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionAsync(Windows::Data::Json::IJsonObject *,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> * *)

- ea: `0x18000dad0`
- end: `0x18000e065`
- name: `?RunDiagnosticActionAsync@DiagnosticInvoker@Diagnostics@System@Windows@@UEAAJPEAUIJsonObject@Json@Data@4@PEAPEAU?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@4@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(char *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800016a8`
- `0x180001e20`
- `0x180007a2c`
- `0x18000d4f0`
- `0x18000dad0`
- `0x18000f718`
- `0x180010064`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dbe2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000db25`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000db25`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000db1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000db1b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000dc2b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000dc2b`

## string_xrefs

- `0x18000dbdb`: `Windows.Data.Json.JsonObject`
- `0x18000dca7`: `DiagnosticInvoker::Activating JsonObject to do a copy of the input`
- `0x18000dd61`: `DiagnosticInvoker::Copying the input raw pointer to COM pointer`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionAsync(
        char *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3)
{
  int v6; // ecx
  __int64 v7; // r8
  int v8; // r9d
  int v9; // ebx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // ecx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // ecx
  __int64 v18; // rcx
  int v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22; // [rsp+80h] [rbp-80h] BYREF
  const char *v23; // [rsp+88h] [rbp-78h] BYREF
  const char *v24; // [rsp+90h] [rbp-70h] BYREF
  const char *v25; // [rsp+98h] [rbp-68h] BYREF
  const char *v26; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[12]; // [rsp+A8h] [rbp-58h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER Frequency; // [rsp+C0h] [rbp-40h] BYREF
  __int128 *v30; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER *p_hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING string[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v34; // [rsp+100h] [rbp+0h] BYREF
  __int128 v35; // [rsp+110h] [rbp+10h] BYREF
  __int128 v36; // [rsp+120h] [rbp+20h] BYREF

  v22 = 0;
  PerformanceCount.QuadPart = 0;
  Frequency.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_18001D000 > 5 )
    {
      v23 = "DiagnosticInvoker::bad input param";
      v20 = -2147024809;
      LODWORD(v21) = 352;
      v24 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
      v25 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionAsync";
      v26 = a1 + 72;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)&word_180018026,
        v7,
        v8,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v23);
    }
LABEL_32:
    if ( (unsigned int)dword_18001D000 > 5
      && (qword_18001D010 & 0x800000000000LL) != 0
      && (qword_18001D018 & 0x800000000000LL) == qword_18001D018 )
    {
      LODWORD(v21) = v9;
      v26 = 0;
      v20 = -2147467259;
      v25 = 0;
      v34 = 0;
      v24 = (const char *)&v34;
      v35 = 0;
      v23 = (const char *)&v35;
      v36 = 0;
      v30 = &v36;
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
      p_hstringHeader = &hstringHeader;
      *(_QWORD *)v27 = a1 + 72;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        qword_18001D018,
        (unsigned int)&byte_180017E4F,
        v7,
        v8,
        (__int64)v27,
        (__int64)&p_hstringHeader,
        (__int64)&v30,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v20,
        (__int64)&v26,
        (__int64)&v21);
    }
    DiagInvokerEventProvider::LogErrorEvent(v9);
    goto LABEL_37;
  }
  string[0] = 0;
  v10 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    JUMPOUT(0x18000E064LL);
  }
  v22 = 0;
  v21 = 0;
  v9 = RoActivateInstance(string[0], &v21);
  if ( v9 >= 0 )
  {
    if ( !memcmp_0(&GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v22 = v21;
    }
    else
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
             v21,
             &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
             &v22);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v26 = "DiagnosticInvoker::Activating JsonObject to do a copy of the input";
    LODWORD(v21) = v9;
    v20 = 358;
    v25 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v24 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionAsync";
    v23 = a1 + 72;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v13,
      (unsigned int)&unk_180017FC0,
      v7,
      v8,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v26);
  }
  if ( v9 < 0 )
    goto LABEL_32;
  v14 = **a2;
  v15 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v14(a2, &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3, &v22);
  v9 = v16;
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v26 = "DiagnosticInvoker::Copying the input raw pointer to COM pointer";
    LODWORD(v21) = v16;
    v20 = 363;
    v25 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v24 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionAsync";
    v23 = a1 + 72;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)a1 + 72,
      (unsigned int)word_180017F5A,
      v7,
      v8,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v26);
  }
  if ( v9 < 0 )
    goto LABEL_32;
  if ( a1 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  hstringHeader.Reserved.Reserved1 = a1;
  if ( a1 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &g_pResult;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = v22;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  string[0] = (HSTRING)PerformanceCount.QuadPart;
  string[1] = (HSTRING)Frequency.QuadPart;
  *(_DWORD *)v27 = 0;
  *(_QWORD *)&v27[4] = 128;
  v9 = Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f____(
         v27,
         a3,
         v7,
         &hstringHeader);
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v26 = "DiagnosticInvoker::MakeAsyncOperationWithProgress";
    LODWORD(v21) = v9;
    v20 = 608;
    v25 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v24 = "Windows::System::Diagnostics::DiagnosticInvoker::RunDiagnosticActionAsync";
    v23 = a1 + 72;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v17,
      (unsigned int)&dword_180017EF4,
      v7,
      v8,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v20,
      (__int64)&v21,
      (__int64)&v26);
  }
  if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&hstringHeader.Reserved.Reserved2[16] + 16LL))(*(_QWORD *)&hstringHeader.Reserved.Reserved2[16]);
  if ( hstringHeader.Reserved.Reserved1 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)hstringHeader.Reserved.Reserved1 + 16LL))(hstringHeader.Reserved.Reserved1);
  if ( a1 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v9 < 0 )
    goto LABEL_32;
LABEL_37:
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000dad0  mov     [rsp-8+arg_0], rbx
0x18000dad5  mov     [rsp-8+arg_18], rsi
0x18000dada  push    rbp
0x18000dadb  push    rdi
0x18000dadc  push    r12
0x18000dade  push    r14
0x18000dae0  push    r15
0x18000dae2  lea     rbp, [rsp-40h]
0x18000dae7  sub     rsp, 140h
0x18000daee  mov     rax, cs:__security_cookie
0x18000daf5  xor     rax, rsp
0x18000daf8  mov     [rbp+60h+var_30], rax
0x18000dafc  mov     r12, r8
0x18000daff  mov     r15, rdx
0x18000db02  mov     rdi, rcx
0x18000db05  mov     [rbp+60h+var_E0], 0
0x18000db0d  xor     eax, eax
0x18000db0f  mov     qword ptr [rbp+60h+PerformanceCount], rax
0x18000db13  mov     qword ptr [rbp+60h+Frequency], rax
0x18000db17  lea     rcx, [rbp+60h+PerformanceCount]; lpPerformanceCount
0x18000db1b  call    cs:__imp_QueryPerformanceCounter
0x18000db21  lea     rcx, [rbp+60h+Frequency]; lpFrequency
0x18000db25  call    cs:__imp_QueryPerformanceFrequency
0x18000db2b  test    r15, r15
0x18000db2e  jnz     loc_18000DBC6
0x18000db34  mov     ebx, 80070057h
0x18000db39  mov     eax, cs:dword_18001D000
0x18000db3f  cmp     eax, 5
0x18000db42  jbe     loc_18000DF18
0x18000db48  lea     rax, aDiagnosticinvo_16; "DiagnosticInvoker::bad input param"
0x18000db4f  mov     [rbp+60h+var_D8], rax
0x18000db53  mov     [rsp+160h+var_F0], ebx
0x18000db57  mov     dword ptr [rsp+160h+var_E8], 160h
0x18000db5f  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000db66  mov     [rbp+60h+var_D0], rsi
0x18000db6a  lea     r14, aWindowsSystemD_1; "Windows::System::Diagnostics::Diagnosti"...
0x18000db71  mov     [rbp+60h+var_C8], r14
0x18000db75  lea     rax, [rdi+48h]
0x18000db79  mov     [rbp+60h+var_C0], rax
0x18000db7d  lea     rax, [rbp+60h+var_D8]
0x18000db81  mov     [rsp+160h+var_118], rax
0x18000db86  lea     rax, [rsp+160h+var_F0]
0x18000db8b  mov     [rsp+160h+var_120], rax
0x18000db90  lea     rax, [rsp+160h+var_E8]
0x18000db95  mov     [rsp+160h+var_128], rax
0x18000db9a  lea     rax, [rbp+60h+var_D0]
0x18000db9e  mov     [rsp+160h+var_130], rax
0x18000dba3  lea     rax, [rbp+60h+var_C8]
0x18000dba7  mov     [rsp+160h+var_138], rax
0x18000dbac  lea     rax, [rbp+60h+var_C0]
0x18000dbb0  mov     [rsp+160h+var_140], rax
0x18000dbb5  lea     rdx, word_180018026
0x18000dbbc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000dbc1  jmp     loc_18000DF18
0x18000dbc6  mov     [rbp+60h+string], 0
0x18000dbce  lea     r9, [rbp+60h+string]; string
0x18000dbd2  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x18000dbd6  mov     edx, 1Ch; length
0x18000dbdb  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18000dbe2  call    cs:__imp_WindowsCreateStringReference
0x18000dbe8  test    eax, eax
0x18000dbea  js      loc_18000E05D
0x18000dbf0  mov     rbx, [rbp+60h+string]
0x18000dbf4  mov     rcx, [rbp+60h+var_E0]
0x18000dbf8  test    rcx, rcx
0x18000dbfb  jz      short loc_18000DC12
0x18000dbfd  mov     [rbp+60h+var_E0], 0
0x18000dc05  mov     rax, [rcx]
0x18000dc08  mov     rax, [rax+10h]
0x18000dc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc11  nop
0x18000dc12  mov     [rbp+60h+var_E0], 0
0x18000dc1a  mov     [rsp+160h+var_E8], 0
0x18000dc23  lea     rdx, [rsp+160h+var_E8]
0x18000dc28  mov     rcx, rbx
0x18000dc2b  call    cs:__imp_RoActivateInstance
0x18000dc31  mov     ebx, eax
0x18000dc33  test    eax, eax
0x18000dc35  js      short loc_18000DC8E
0x18000dc37  mov     r8d, 10h; Size
0x18000dc3d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000dc44  lea     rcx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3; Buf1
0x18000dc4b  call    memcmp_0
0x18000dc50  test    eax, eax
0x18000dc52  jnz     short loc_18000DC5F
0x18000dc54  mov     rax, [rsp+160h+var_E8]
0x18000dc59  mov     [rbp+60h+var_E0], rax
0x18000dc5d  jmp     short loc_18000DC8E
0x18000dc5f  mov     rcx, [rsp+160h+var_E8]
0x18000dc64  mov     rax, [rcx]
0x18000dc67  lea     r8, [rbp+60h+var_E0]
0x18000dc6b  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18000dc72  mov     rax, [rax]
0x18000dc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc7a  mov     ebx, eax
0x18000dc7c  mov     rcx, [rsp+160h+var_E8]
0x18000dc81  mov     rax, [rcx]
0x18000dc84  mov     rax, [rax+10h]
0x18000dc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc8d  nop
0x18000dc8e  mov     eax, cs:dword_18001D000
0x18000dc94  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000dc9b  lea     r14, aWindowsSystemD_1; "Windows::System::Diagnostics::Diagnosti"...
0x18000dca2  cmp     eax, 5
0x18000dca5  jbe     short loc_18000DD12
0x18000dca7  lea     rax, aDiagnosticinvo_6; "DiagnosticInvoker::Activating JsonObjec"...
0x18000dcae  mov     [rbp+60h+var_C0], rax
0x18000dcb2  mov     dword ptr [rsp+160h+var_E8], ebx
0x18000dcb6  mov     [rsp+160h+var_F0], 166h
0x18000dcbe  mov     [rbp+60h+var_C8], rsi
0x18000dcc2  mov     [rbp+60h+var_D0], r14
0x18000dcc6  lea     rax, [rdi+48h]
0x18000dcca  mov     [rbp+60h+var_D8], rax
0x18000dcce  lea     rax, [rbp+60h+var_C0]
0x18000dcd2  mov     [rsp+160h+var_118], rax
0x18000dcd7  lea     rax, [rsp+160h+var_E8]
0x18000dcdc  mov     [rsp+160h+var_120], rax
0x18000dce1  lea     rax, [rsp+160h+var_F0]
0x18000dce6  mov     [rsp+160h+var_128], rax
0x18000dceb  lea     rax, [rbp+60h+var_C8]
0x18000dcef  mov     [rsp+160h+var_130], rax
0x18000dcf4  lea     rax, [rbp+60h+var_D0]
0x18000dcf8  mov     [rsp+160h+var_138], rax
0x18000dcfd  lea     rax, [rbp+60h+var_D8]
0x18000dd01  mov     [rsp+160h+var_140], rax
0x18000dd06  lea     rdx, unk_180017FC0
0x18000dd0d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000dd12  test    ebx, ebx
0x18000dd14  js      loc_18000DF18
0x18000dd1a  mov     rax, [r15]
0x18000dd1d  mov     rbx, [rax]
0x18000dd20  mov     rcx, [rbp+60h+var_E0]
0x18000dd24  test    rcx, rcx
0x18000dd27  jz      short loc_18000DD3E
0x18000dd29  mov     [rbp+60h+var_E0], 0
0x18000dd31  mov     rax, [rcx]
0x18000dd34  mov     rax, [rax+10h]
0x18000dd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd3d  nop
0x18000dd3e  lea     r8, [rbp+60h+var_E0]
0x18000dd42  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18000dd49  mov     rcx, r15
0x18000dd4c  mov     rax, rbx
0x18000dd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd54  mov     ebx, eax
0x18000dd56  mov     ecx, cs:dword_18001D000
0x18000dd5c  cmp     ecx, 5
0x18000dd5f  jbe     short loc_18000DDCC
0x18000dd61  lea     rax, aDiagnosticinvo_19; "DiagnosticInvoker::Copying the input ra"...
0x18000dd68  mov     [rbp+60h+var_C0], rax
0x18000dd6c  mov     dword ptr [rsp+160h+var_E8], ebx
0x18000dd70  mov     [rsp+160h+var_F0], 16Bh
0x18000dd78  mov     [rbp+60h+var_C8], rsi
0x18000dd7c  mov     [rbp+60h+var_D0], r14
0x18000dd80  lea     rcx, [rdi+48h]
0x18000dd84  mov     [rbp+60h+var_D8], rcx
0x18000dd88  lea     rax, [rbp+60h+var_C0]
0x18000dd8c  mov     [rsp+160h+var_118], rax
0x18000dd91  lea     rax, [rsp+160h+var_E8]
0x18000dd96  mov     [rsp+160h+var_120], rax
0x18000dd9b  lea     rax, [rsp+160h+var_F0]
0x18000dda0  mov     [rsp+160h+var_128], rax
0x18000dda5  lea     rax, [rbp+60h+var_C8]
0x18000dda9  mov     [rsp+160h+var_130], rax
0x18000ddae  lea     rax, [rbp+60h+var_D0]
0x18000ddb2  mov     [rsp+160h+var_138], rax
0x18000ddb7  lea     rax, [rbp+60h+var_D8]
0x18000ddbb  mov     [rsp+160h+var_140], rax
0x18000ddc0  lea     rdx, word_180017F5A
0x18000ddc7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ddcc  test    ebx, ebx
0x18000ddce  js      loc_18000DF18
0x18000ddd4  test    rdi, rdi
0x18000ddd7  jz      short loc_18000DDE9
0x18000ddd9  mov     rax, [rdi]
0x18000dddc  mov     rcx, rdi
0x18000dddf  mov     rax, [rax+8]
0x18000dde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dde8  nop
0x18000dde9  mov     qword ptr [rbp+60h+hstringHeader.Reserved], rdi
0x18000dded  test    rdi, rdi
0x18000ddf0  jz      short loc_18000DE02
0x18000ddf2  mov     rax, [rdi]
0x18000ddf5  mov     rcx, rdi
0x18000ddf8  mov     rax, [rax+8]
0x18000ddfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de01  nop
0x18000de02  lea     rax, ?g_pResult@@3PEAV?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@Windows@@EA; Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState> * g_pResult
0x18000de09  mov     qword ptr [rbp+60h+hstringHeader.Reserved+8], rax
0x18000de0d  mov     rcx, [rbp+60h+var_E0]
0x18000de11  mov     qword ptr [rbp+60h+hstringHeader.Reserved+10h], rcx
0x18000de15  test    rcx, rcx
0x18000de18  jz      short loc_18000DE27
0x18000de1a  mov     rax, [rcx]
0x18000de1d  mov     rax, [rax+8]
0x18000de21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de26  nop
0x18000de27  mov     rax, qword ptr [rbp+60h+PerformanceCount]
0x18000de2b  mov     [rbp+60h+string], rax
0x18000de2f  mov     rax, qword ptr [rbp+60h+Frequency]
0x18000de33  mov     [rbp+60h+var_68], rax
0x18000de37  mov     dword ptr [rbp+60h+var_B8], 0
0x18000de3e  mov     [rbp+60h+var_B8+4], 80h
0x18000de46  lea     r9, [rbp+60h+hstringHeader]
0x18000de4a  mov     rdx, r12
0x18000de4d  lea     rcx, [rbp+60h+var_B8]
0x18000de51  call    Windows__Internal__MakeAsyncOperationWithProgress_Windows__Internal__ProgressResult_Windows__Internal__CMarshaledInterfaceResult_Windows__System__Diagnostics__IDiagnosticActionResult__enum_Windows__System__Diagnostics__DiagnosticActionState__Windows__System__Diagnostics__DiagnosticActionResult___enum_Windows__System__Diagnostics__DiagnosticActionState_Windows__Internal__ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f____
0x18000de56  mov     ebx, eax
0x18000de58  mov     eax, cs:dword_18001D000
0x18000de5e  cmp     eax, 5
0x18000de61  jbe     short loc_18000DECF
0x18000de63  lea     rax, aDiagnosticinvo_15; "DiagnosticInvoker::MakeAsyncOperationWi"...
0x18000de6a  mov     [rbp+60h+var_C0], rax
0x18000de6e  mov     dword ptr [rsp+160h+var_E8], ebx
0x18000de72  mov     [rsp+160h+var_F0], 260h
0x18000de7a  mov     [rbp+60h+var_C8], rsi
0x18000de7e  mov     [rbp+60h+var_D0], r14
0x18000de82  lea     rax, [rdi+48h]
0x18000de86  mov     [rbp+60h+var_D8], rax
0x18000de8a  lea     rax, [rbp+60h+var_C0]
0x18000de8e  mov     [rsp+160h+var_118], rax
0x18000de93  lea     rax, [rsp+160h+var_E8]
0x18000de98  mov     [rsp+160h+var_120], rax
0x18000de9d  lea     rax, [rsp+160h+var_F0]
0x18000dea2  mov     [rsp+160h+var_128], rax
0x18000dea7  lea     rax, [rbp+60h+var_C8]
0x18000deab  mov     [rsp+160h+var_130], rax
0x18000deb0  lea     rax, [rbp+60h+var_D0]
0x18000deb4  mov     [rsp+160h+var_138], rax
0x18000deb9  lea     rax, [rbp+60h+var_D8]
0x18000debd  mov     [rsp+160h+var_140], rax
0x18000dec2  lea     rdx, dword_180017EF4
0x18000dec9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000dece  nop
0x18000decf  mov     rcx, qword ptr [rbp+60h+hstringHeader.Reserved+10h]
0x18000ded3  test    rcx, rcx
0x18000ded6  jz      short loc_18000DEE5
0x18000ded8  mov     rax, [rcx]
0x18000dedb  mov     rax, [rax+10h]
0x18000dedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dee4  nop
0x18000dee5  mov     rcx, qword ptr [rbp+60h+hstringHeader.Reserved]
0x18000dee9  test    rcx, rcx
0x18000deec  jz      short loc_18000DEFB
0x18000deee  mov     rax, [rcx]
0x18000def1  mov     rax, [rax+10h]
0x18000def5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defa  nop
0x18000defb  test    rdi, rdi
0x18000defe  jz      short loc_18000DF10
0x18000df00  mov     rax, [rdi]
0x18000df03  mov     rcx, rdi
0x18000df06  mov     rax, [rax+10h]
0x18000df0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df0f  nop
0x18000df10  test    ebx, ebx
0x18000df12  jns     loc_18000E015
0x18000df18  mov     eax, cs:dword_18001D000
0x18000df1e  cmp     eax, 5
0x18000df21  jbe     loc_18000E00D
0x18000df27  mov     rcx, cs:qword_18001D018
0x18000df2e  mov     rax, cs:qword_18001D010
0x18000df35  mov     rdx, 800000000000h
0x18000df3f  test    rdx, rax
0x18000df42  jz      loc_18000E00D
0x18000df48  mov     rax, rcx
0x18000df4b  and     rax, rdx
0x18000df4e  cmp     rax, rcx
0x18000df51  jnz     loc_18000E00D
0x18000df57  mov     dword ptr [rsp+160h+var_E8], ebx
0x18000df5b  mov     [rbp+60h+var_C0], 0
0x18000df63  mov     [rsp+160h+var_F0], 80004005h
0x18000df6b  mov     [rbp+60h+var_C8], 0
0x18000df73  xorps   xmm0, xmm0
0x18000df76  movups  [rbp+60h+var_60], xmm0
0x18000df7a  lea     rax, [rbp+60h+var_60]
0x18000df7e  mov     [rbp+60h+var_D0], rax
0x18000df82  movups  [rbp+60h+var_50], xmm0
0x18000df86  lea     rax, [rbp+60h+var_50]
0x18000df8a  mov     [rbp+60h+var_D8], rax
0x18000df8e  movups  [rbp+60h+var_40], xmm0
0x18000df92  lea     rax, [rbp+60h+var_40]
0x18000df96  mov     [rbp+60h+var_98], rax
0x18000df9a  movups  xmmword ptr [rbp+60h+hstringHeader.Reserved], xmm0
0x18000df9e  lea     rax, [rbp+60h+hstringHeader]
0x18000dfa2  mov     [rbp+60h+var_90], rax
0x18000dfa6  lea     rax, [rdi+48h]
0x18000dfaa  mov     [rbp+60h+var_B8], rax
0x18000dfae  lea     rax, [rsp+160h+var_E8]
0x18000dfb3  mov     [rsp+160h+var_100], rax
0x18000dfb8  lea     rax, [rbp+60h+var_C0]
0x18000dfbc  mov     [rsp+160h+var_108], rax
0x18000dfc1  lea     rax, [rsp+160h+var_F0]
0x18000dfc6  mov     [rsp+160h+var_110], rax
0x18000dfcb  lea     rax, [rbp+60h+var_C8]
0x18000dfcf  mov     [rsp+160h+var_118], rax
0x18000dfd4  lea     rax, [rbp+60h+var_D0]
0x18000dfd8  mov     [rsp+160h+var_120], rax
0x18000dfdd  lea     rax, [rbp+60h+var_D8]
0x18000dfe1  mov     [rsp+160h+var_128], rax
  ... truncated ...
```
