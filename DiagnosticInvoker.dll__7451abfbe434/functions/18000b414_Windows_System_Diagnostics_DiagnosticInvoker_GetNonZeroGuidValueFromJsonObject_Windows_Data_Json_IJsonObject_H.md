# Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject(Windows::Data::Json::IJsonObject *,HSTRING__ *,_GUID *)

- ea: `0x18000b414`
- end: `0x18000b6d0`
- name: `?GetNonZeroGuidValueFromJsonObject@DiagnosticInvoker@Diagnostics@System@Windows@@AEAAJPEAUIJsonObject@Json@Data@4@PEAUHSTRING__@@PEAU_GUID@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(Windows::System::Diagnostics::DiagnosticInvoker *this, struct Windows::Data::Json::IJsonObject *, HSTRING, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000881c`

## callees

- `0x18000108c`
- `0x18000b414`
- `0x180011010`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18000b642`
- `RPCRT4!UuidFromStringW` at `0x18000b642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b64e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b64e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b636`

## string_xrefs

- `0x18000b483`: `DiagnosticInvoker::GetJsonNamedValue`
- `0x18000b477`: `Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject`
- `0x18000b516`: `DiagnosticInvoker::Get Json Value Type`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject(
        Windows::System::Diagnostics::DiagnosticInvoker *this,
        struct Windows::Data::Json::IJsonObject *a2,
        HSTRING a3,
        struct _GUID *a4)
{
  RPC_STATUS v6; // eax
  int v7; // r8d
  int v8; // r9d
  RPC_STATUS v9; // edi
  const char *v10; // rsi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  HSTRING v19; // rcx
  unsigned __int16 *StringRawBuffer; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  int v24; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+58h] [rbp-1h] BYREF
  const char *v26; // [rsp+60h] [rbp+7h] BYREF
  __int64 v27; // [rsp+68h] [rbp+Fh] BYREF
  const char *v28; // [rsp+70h] [rbp+17h] BYREF
  const char *v29; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v30; // [rsp+80h] [rbp+27h] BYREF
  const char *v31; // [rsp+88h] [rbp+2Fh] BYREF
  RPC_STATUS v32; // [rsp+C8h] [rbp+6Fh] BYREF

  v27 = 0;
  string = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, __int64 *))(*(_QWORD *)a2 + 48LL))(
         a2,
         a3,
         &v27);
  v9 = v6;
  v10 = (char *)this + 72;
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v26 = "DiagnosticInvoker::GetJsonNamedValue";
    v32 = v6;
    v24 = 188;
    v28 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v29 = "Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject";
    v30 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_18001D000,
      (unsigned int)&dword_180018E34,
      v7,
      v8,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v24,
      (__int64)&v32,
      (__int64)&v26);
  }
  if ( v9 < 0 )
    goto LABEL_18;
  v32 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, RPC_STATUS *))(*(_QWORD *)v27 + 48LL))(v27, &v32);
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v30 = "DiagnosticInvoker::Get Json Value Type";
    v24 = v9;
    LODWORD(v26) = 194;
    v29 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v28 = "Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject";
    v31 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v11,
      (unsigned int)&word_180018DCE,
      v12,
      v13,
      (__int64)&v31,
      (__int64)&v28,
      (__int64)&v29,
      (__int64)&v26,
      (__int64)&v24,
      (__int64)&v30);
  }
  if ( v9 < 0 )
    goto LABEL_18;
  if ( v32 != 3 )
    goto LABEL_11;
  v14 = v27;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 64LL);
  WindowsDeleteString(string);
  string = 0;
  v9 = v15(v14, &string);
  if ( (unsigned int)dword_18001D000 > 5 )
  {
    v31 = "DiagnosticInvoker::Get Value";
    LODWORD(v26) = v9;
    v24 = 199;
    v30 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
    v29 = "Windows::System::Diagnostics::DiagnosticInvoker::GetNonZeroGuidValueFromJsonObject";
    v28 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v16,
      (unsigned int)&unk_180018D68,
      v17,
      v18,
      (__int64)&v28,
      (__int64)&v29,
      (__int64)&v30,
      (__int64)&v24,
      (__int64)&v26,
      (__int64)&v31);
  }
  if ( v9 < 0 )
  {
LABEL_18:
    v19 = string;
  }
  else
  {
LABEL_11:
    v19 = string;
    if ( !string
      || (StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0),
          v9 = UuidFromStringW(StringRawBuffer, a4),
          WindowsDeleteString(string),
          v19 = 0,
          string = 0,
          v9 >= 0) )
    {
      v21 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v21 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( !v21 )
        v9 = 13;
    }
  }
  WindowsDeleteString(v19);
  string = 0;
  v22 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b414  mov     [rsp-8+arg_0], rbx
0x18000b419  mov     [rsp-8+arg_10], rsi
0x18000b41e  push    rbp
0x18000b41f  push    rdi
0x18000b420  push    r12
0x18000b422  push    r13
0x18000b424  push    r14
0x18000b426  lea     rbp, [rsp-37h]
0x18000b42b  sub     rsp, 90h
0x18000b432  mov     r14, r9
0x18000b435  mov     r10, r8
0x18000b438  mov     r11, rdx
0x18000b43b  mov     rsi, rcx
0x18000b43e  mov     [rbp+57h+var_48], 0
0x18000b446  mov     [rbp+57h+string], 0
0x18000b44e  mov     rax, [rdx]
0x18000b451  lea     r8, [rbp+57h+var_48]
0x18000b455  mov     rdx, r10
0x18000b458  mov     rcx, r11
0x18000b45b  mov     rax, [rax+30h]
0x18000b45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b464  mov     edi, eax
0x18000b466  mov     ecx, cs:dword_18001D000
0x18000b46c  add     rsi, 48h ; 'H'
0x18000b470  lea     r12, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000b477  lea     r13, aWindowsSystemD_5; "Windows::System::Diagnostics::Diagnosti"...
0x18000b47e  cmp     ecx, 5
0x18000b481  jbe     short loc_18000B4E6
0x18000b483  lea     rax, aDiagnosticinvo_12; "DiagnosticInvoker::GetJsonNamedValue"
0x18000b48a  mov     [rbp+57h+var_50], rax
0x18000b48e  mov     [rbp+57h+arg_8], edi
0x18000b491  mov     [rbp+57h+var_60], 0BCh
0x18000b498  mov     [rbp+57h+var_40], r12
0x18000b49c  mov     [rbp+57h+var_38], r13
0x18000b4a0  mov     [rbp+57h+var_30], rsi
0x18000b4a4  lea     rax, [rbp+57h+var_50]
0x18000b4a8  mov     [rsp+0B0h+var_68], rax
0x18000b4ad  lea     rax, [rbp+57h+arg_8]
0x18000b4b1  mov     [rsp+0B0h+var_70], rax
0x18000b4b6  lea     rax, [rbp+57h+var_60]
0x18000b4ba  mov     [rsp+0B0h+var_78], rax
0x18000b4bf  lea     rax, [rbp+57h+var_40]
0x18000b4c3  mov     [rsp+0B0h+var_80], rax
0x18000b4c8  lea     rax, [rbp+57h+var_38]
0x18000b4cc  mov     [rsp+0B0h+var_88], rax
0x18000b4d1  lea     rax, [rbp+57h+var_30]
0x18000b4d5  mov     [rsp+0B0h+var_90], rax
0x18000b4da  lea     rdx, dword_180018E34
0x18000b4e1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b4e6  test    edi, edi
0x18000b4e8  js      loc_18000B682
0x18000b4ee  mov     [rbp+57h+arg_8], 0
0x18000b4f5  mov     rcx, [rbp+57h+var_48]
0x18000b4f9  mov     rax, [rcx]
0x18000b4fc  lea     rdx, [rbp+57h+arg_8]
0x18000b500  mov     rax, [rax+30h]
0x18000b504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b509  mov     edi, eax
0x18000b50b  mov     eax, cs:dword_18001D000
0x18000b511  cmp     eax, 5
0x18000b514  jbe     short loc_18000B579
0x18000b516  lea     rax, aDiagnosticinvo_26; "DiagnosticInvoker::Get Json Value Type"
0x18000b51d  mov     [rbp+57h+var_30], rax
0x18000b521  mov     [rbp+57h+var_60], edi
0x18000b524  mov     dword ptr [rbp+57h+var_50], 0C2h
0x18000b52b  mov     [rbp+57h+var_38], r12
0x18000b52f  mov     [rbp+57h+var_40], r13
0x18000b533  mov     [rbp+57h+var_28], rsi
0x18000b537  lea     rax, [rbp+57h+var_30]
0x18000b53b  mov     [rsp+0B0h+var_68], rax
0x18000b540  lea     rax, [rbp+57h+var_60]
0x18000b544  mov     [rsp+0B0h+var_70], rax
0x18000b549  lea     rax, [rbp+57h+var_50]
0x18000b54d  mov     [rsp+0B0h+var_78], rax
0x18000b552  lea     rax, [rbp+57h+var_38]
0x18000b556  mov     [rsp+0B0h+var_80], rax
0x18000b55b  lea     rax, [rbp+57h+var_40]
0x18000b55f  mov     [rsp+0B0h+var_88], rax
0x18000b564  lea     rax, [rbp+57h+var_28]
0x18000b568  mov     [rsp+0B0h+var_90], rax
0x18000b56d  lea     rdx, word_180018DCE
0x18000b574  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b579  test    edi, edi
0x18000b57b  js      loc_18000B682
0x18000b581  cmp     [rbp+57h+arg_8], 3
0x18000b585  jnz     loc_18000B62B
0x18000b58b  mov     rdi, [rbp+57h+var_48]
0x18000b58f  mov     rax, [rdi]
0x18000b592  mov     rbx, [rax+40h]
0x18000b596  mov     rcx, [rbp+57h+string]; string
0x18000b59a  call    cs:__imp_WindowsDeleteString
0x18000b5a0  mov     [rbp+57h+string], 0
0x18000b5a8  lea     rdx, [rbp+57h+string]
0x18000b5ac  mov     rcx, rdi
0x18000b5af  mov     rax, rbx
0x18000b5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b7  mov     edi, eax
0x18000b5b9  mov     eax, cs:dword_18001D000
0x18000b5bf  cmp     eax, 5
0x18000b5c2  jbe     short loc_18000B627
0x18000b5c4  lea     rax, aDiagnosticinvo_21; "DiagnosticInvoker::Get Value"
0x18000b5cb  mov     [rbp+57h+var_28], rax
0x18000b5cf  mov     dword ptr [rbp+57h+var_50], edi
0x18000b5d2  mov     [rbp+57h+var_60], 0C7h
0x18000b5d9  mov     [rbp+57h+var_30], r12
0x18000b5dd  mov     [rbp+57h+var_38], r13
0x18000b5e1  mov     [rbp+57h+var_40], rsi
0x18000b5e5  lea     rax, [rbp+57h+var_28]
0x18000b5e9  mov     [rsp+0B0h+var_68], rax
0x18000b5ee  lea     rax, [rbp+57h+var_50]
0x18000b5f2  mov     [rsp+0B0h+var_70], rax
0x18000b5f7  lea     rax, [rbp+57h+var_60]
0x18000b5fb  mov     [rsp+0B0h+var_78], rax
0x18000b600  lea     rax, [rbp+57h+var_30]
0x18000b604  mov     [rsp+0B0h+var_80], rax
0x18000b609  lea     rax, [rbp+57h+var_38]
0x18000b60d  mov     [rsp+0B0h+var_88], rax
0x18000b612  lea     rax, [rbp+57h+var_40]
0x18000b616  mov     [rsp+0B0h+var_90], rax
0x18000b61b  lea     rdx, unk_180018D68
0x18000b622  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000b627  test    edi, edi
0x18000b629  js      short loc_18000B682
0x18000b62b  mov     rcx, [rbp+57h+string]; string
0x18000b62f  test    rcx, rcx
0x18000b632  jz      short loc_18000B65E
0x18000b634  xor     edx, edx; length
0x18000b636  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b63c  mov     rcx, rax; StringUuid
0x18000b63f  mov     rdx, r14; Uuid
0x18000b642  call    cs:__imp_UuidFromStringW
0x18000b648  mov     edi, eax
0x18000b64a  mov     rcx, [rbp+57h+string]; string
0x18000b64e  call    cs:__imp_WindowsDeleteString
0x18000b654  xor     ecx, ecx
0x18000b656  mov     [rbp+57h+string], rcx
0x18000b65a  test    edi, edi
0x18000b65c  js      short loc_18000B686
0x18000b65e  mov     rax, [r14]
0x18000b661  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000b668  jnz     short loc_18000B675
0x18000b66a  mov     rax, [r14+8]
0x18000b66e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000b675  mov     edx, 0Dh
0x18000b67a  test    rax, rax
0x18000b67d  cmovz   edi, edx
0x18000b680  jmp     short loc_18000B686
0x18000b682  mov     rcx, [rbp+57h+string]; string
0x18000b686  call    cs:__imp_WindowsDeleteString
0x18000b68c  mov     [rbp+57h+string], 0
0x18000b694  mov     rcx, [rbp+57h+var_48]
0x18000b698  test    rcx, rcx
0x18000b69b  jz      short loc_18000B6B2
0x18000b69d  mov     [rbp+57h+var_48], 0
0x18000b6a5  mov     rax, [rcx]
0x18000b6a8  mov     rax, [rax+10h]
0x18000b6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b1  nop
0x18000b6b2  mov     eax, edi
0x18000b6b4  lea     r11, [rsp+0B0h+var_20]
0x18000b6bc  mov     rbx, [r11+30h]
0x18000b6c0  mov     rsi, [r11+40h]
0x18000b6c4  mov     rsp, r11
0x18000b6c7  pop     r14
0x18000b6c9  pop     r13
0x18000b6cb  pop     r12
0x18000b6cd  pop     rdi
0x18000b6ce  pop     rbp
0x18000b6cf  retn
```
