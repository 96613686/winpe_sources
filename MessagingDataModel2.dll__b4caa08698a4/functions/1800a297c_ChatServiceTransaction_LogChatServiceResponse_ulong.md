# ChatServiceTransaction::_LogChatServiceResponse(ulong)

- ea: `0x1800a297c`
- end: `0x1800a2d2d`
- name: `?_LogChatServiceResponse@ChatServiceTransaction@@AEAAJK@Z`
- size: `945`
- prototype: `__int64 __fastcall(ChatServiceTransaction *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a28c0`
- `0x1800a2920`

## callees

- `0x1800034f0`
- `0x180030bd0`
- `0x180084738`
- `0x1800a22a4`
- `0x1800a23d4`
- `0x1800a297c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a2c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2adc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2b89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2cd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2ce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2adc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2b89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2cd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2ce3`

## string_xrefs

- `0x1800a2bf5`: `[MessagingCloudServices] ChatService transaction response success`
- `0x1800a2c5b`: `[MessagingCloudServices] ChatService transaction response success`
- `0x1800a2c9d`: `[MessagingCloudServices] ChatService transaction response failure`

## pseudocode

```c
__int64 __fastcall ChatServiceTransaction::_LogChatServiceResponse(ChatServiceTransaction *this, int a2)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64); // rcx
  void (*v8)(void); // rax
  char v10; // r8
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, PVOID, char *); // rbx
  HSTRING_HEADER *v14; // rax
  char v15; // r8
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, PVOID, HSTRING *); // rbx
  char v18; // r8
  HSTRING_HEADER *v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, PVOID, _BYTE *); // rbx
  HSTRING_HEADER *v22; // rax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, PVOID, HSTRING *); // rbx
  char v25; // r8
  HSTRING_HEADER *v26; // rax
  int v27; // eax
  int v28; // esi
  int v29; // esi
  int v30; // esi
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  char *v37; // rdx
  const char *v38; // rax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // rcx
  int v40; // [rsp+40h] [rbp-49h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-41h] BYREF
  PCWSTR v42; // [rsp+50h] [rbp-39h] BYREF
  PCWSTR v43; // [rsp+58h] [rbp-31h] BYREF
  HSTRING_HEADER v44; // [rsp+60h] [rbp-29h] BYREF
  char v45; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v46[7]; // [rsp+81h] [rbp-8h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // [rsp+88h] [rbp-1h] BYREF
  HSTRING string; // [rsp+90h] [rbp+7h] BYREF
  __int64 v49; // [rsp+98h] [rbp+Fh] BYREF
  HSTRING v50; // [rsp+A0h] [rbp+17h] BYREF

  v4 = *((_QWORD *)this + 2);
  v47 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v4 + 64LL))(
         v4,
         &v47);
  v6 = v5;
  if ( v5 < 0 )
  {
    Log_HREvent_78(v5);
    v7 = v47;
    if ( !v47 )
      return (unsigned int)v6;
    v47 = 0;
    v8 = (void (*)(void))(*v7)[2];
LABEL_4:
    v8();
    return (unsigned int)v6;
  }
  v49 = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpResponseHeaderCollection>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(
         &v47,
         (__int64)&v49);
  if ( v6 < 0
    || (v12 = v49,
        v45 = 0,
        v13 = *(__int64 (__fastcall **)(__int64, PVOID, char *))(*(_QWORD *)v49 + 64LL),
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v44, (const WCHAR **)off_1800FD7E0, v10),
        v6 = v13(v12, v14[1].Reserved.Reserved1, &v45),
        v6 < 0) )
  {
    Log_HREvent_78(v6);
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v11 = v47;
    if ( !v47 )
      return (unsigned int)v6;
    v47 = 0;
    v8 = (void (*)(void))(*v11)[2];
    goto LABEL_4;
  }
  string = 0;
  if ( v45 )
  {
    v16 = v49;
    v17 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v49 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v44, (const WCHAR **)off_1800FD7E0, v18);
    v6 = v17(v16, v19[1].Reserved.Reserved1, &string);
    if ( v6 < 0 )
      goto LABEL_13;
  }
  v20 = v49;
  v46[0] = 0;
  v21 = *(__int64 (__fastcall **)(__int64, PVOID, _BYTE *))(*(_QWORD *)v49 + 64LL);
  v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v44, (const WCHAR **)off_1800FD7E8, v15);
  v6 = v21(v20, v22[1].Reserved.Reserved1, v46);
  if ( v6 < 0 )
  {
LABEL_13:
    Log_HREvent_78(v6);
LABEL_14:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_8;
  }
  v50 = 0;
  if ( v46[0] )
  {
    v23 = v49;
    v24 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v49 + 48LL);
    WindowsDeleteString(0);
    v50 = 0;
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v44, (const WCHAR **)off_1800FD7E8, v25);
    v27 = v24(v23, v26[1].Reserved.Reserved1, &v50);
    v6 = v27;
    if ( v27 < 0 )
    {
      Log_HREvent_78(v27);
      WindowsDeleteString(v50);
      v50 = 0;
      goto LABEL_14;
    }
  }
  v28 = a2 - 1;
  if ( v28 && (v29 = v28 - 1) != 0 && (v30 = v29 - 1) != 0 )
  {
    if ( v30 != 1 )
    {
      if ( (unsigned int)dword_1800FD5F0 > 5 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v50, 0);
        v42 = WindowsGetStringRawBuffer(string, 0);
        v40 = *((_DWORD *)this + 6);
        v43 = (PCWSTR)"[MessagingCloudServices] ChatService transaction response success";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v31,
          (int)word_1800F2FC2,
          v32,
          v33,
          &v43,
          (__int64)&v40,
          &v42,
          &StringRawBuffer);
      }
      goto LABEL_30;
    }
    if ( (unsigned int)dword_1800FD5F0 > 4 )
    {
      v43 = WindowsGetStringRawBuffer(v50, 0);
      v42 = WindowsGetStringRawBuffer(string, 0);
      v37 = byte_1800F2F5D;
      v40 = *((_DWORD *)this + 6);
      v38 = "[MessagingCloudServices] ChatService transaction response success";
LABEL_29:
      StringRawBuffer = (PCWSTR)v38;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v34,
        (int)v37,
        v35,
        v36,
        &StringRawBuffer,
        (__int64)&v40,
        &v42,
        &v43);
    }
  }
  else if ( (unsigned int)dword_1800FD5F0 > 2 )
  {
    v43 = WindowsGetStringRawBuffer(v50, 0);
    v42 = WindowsGetStringRawBuffer(string, 0);
    v37 = &byte_1800F3027;
    v40 = *((_DWORD *)this + 6);
    v38 = "[MessagingCloudServices] ChatService transaction response failure";
    goto LABEL_29;
  }
LABEL_30:
  WindowsDeleteString(v50);
  v50 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  v39 = v47;
  if ( v47 )
  {
    v47 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v39)[2])(v39);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a297c  push    rbp
0x1800a297e  push    rbx
0x1800a297f  push    rsi
0x1800a2980  push    rdi
0x1800a2981  push    r14
0x1800a2983  push    r15
0x1800a2985  lea     rbp, [rsp-2Fh]
0x1800a298a  sub     rsp, 0B8h
0x1800a2991  mov     rax, cs:__security_cookie
0x1800a2998  xor     rax, rsp
0x1800a299b  mov     [rbp+57h+var_38], rax
0x1800a299f  mov     r14, rcx
0x1800a29a2  mov     esi, edx
0x1800a29a4  mov     rcx, [rcx+10h]
0x1800a29a8  lea     rdx, [rbp+57h+var_58]
0x1800a29ac  xor     r15d, r15d
0x1800a29af  mov     [rbp+57h+var_58], r15
0x1800a29b3  mov     rax, [rcx]
0x1800a29b6  mov     rax, [rax+40h]
0x1800a29ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a29bf  mov     ebx, eax
0x1800a29c1  test    eax, eax
0x1800a29c3  jns     short loc_1800A29F4
0x1800a29c5  lea     edx, [r15+1]
0x1800a29c9  mov     ecx, eax; int
0x1800a29cb  lea     r9d, [r15+40h]
0x1800a29cf  call    Log_HREvent_78
0x1800a29d4  mov     rcx, [rbp+57h+var_58]
0x1800a29d8  test    rcx, rcx
0x1800a29db  jz      short loc_1800A29ED
0x1800a29dd  mov     [rbp+57h+var_58], r15
0x1800a29e1  mov     rdx, [rcx]
0x1800a29e4  mov     rax, [rdx+10h]
0x1800a29e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a29ed  mov     eax, ebx
0x1800a29ef  jmp     loc_1800A2D11
0x1800a29f4  lea     rdx, [rbp+57h+var_48]
0x1800a29f8  mov     [rbp+57h+var_48], r15
0x1800a29fc  lea     rcx, [rbp+57h+var_58]
0x1800a2a00  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@?$ComPtr@UIHttpResponseHeaderCollection@Headers@Http@Web@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpResponseHeaderCollection>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>>)
0x1800a2a05  mov     ebx, eax
0x1800a2a07  test    eax, eax
0x1800a2a09  jns     short loc_1800A2A3C
0x1800a2a0b  mov     r9d, 42h ; 'B'
0x1800a2a11  mov     edx, 1
0x1800a2a16  mov     ecx, ebx; int
0x1800a2a18  call    Log_HREvent_78
0x1800a2a1d  lea     rcx, [rbp+57h+var_48]
0x1800a2a21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2a26  mov     rcx, [rbp+57h+var_58]
0x1800a2a2a  test    rcx, rcx
0x1800a2a2d  jz      short loc_1800A29ED
0x1800a2a2f  mov     [rbp+57h+var_58], r15
0x1800a2a33  mov     rax, [rcx]
0x1800a2a36  mov     rax, [rax+10h]
0x1800a2a3a  jmp     short loc_1800A29E8
0x1800a2a3c  mov     rdi, [rbp+57h+var_48]
0x1800a2a40  lea     rdx, off_1800FD7E0; "ContextId"
0x1800a2a47  mov     [rbp+57h+var_60], r15b
0x1800a2a4b  lea     rcx, [rbp+57h+var_80]
0x1800a2a4f  mov     rax, [rdi]
0x1800a2a52  mov     rbx, [rax+40h]
0x1800a2a56  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a2a5b  lea     r8, [rbp+57h+var_60]
0x1800a2a5f  mov     rcx, rdi
0x1800a2a62  mov     rdx, [rax+18h]
0x1800a2a66  mov     rax, rbx
0x1800a2a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a6e  mov     ebx, eax
0x1800a2a70  test    eax, eax
0x1800a2a72  jns     short loc_1800A2A7C
0x1800a2a74  mov     r9d, 45h ; 'E'
0x1800a2a7a  jmp     short loc_1800A2A11
0x1800a2a7c  mov     [rbp+57h+string], r15
0x1800a2a80  cmp     [rbp+57h+var_60], r15b
0x1800a2a84  jz      short loc_1800A2AEB
0x1800a2a86  mov     rdi, [rbp+57h+var_48]
0x1800a2a8a  xor     ecx, ecx; string
0x1800a2a8c  mov     rax, [rdi]
0x1800a2a8f  mov     rbx, [rax+30h]
0x1800a2a93  call    cs:__imp_WindowsDeleteString
0x1800a2a99  lea     rdx, off_1800FD7E0; "ContextId"
0x1800a2aa0  mov     [rbp+57h+string], r15
0x1800a2aa4  lea     rcx, [rbp+57h+var_80]
0x1800a2aa8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a2aad  lea     r8, [rbp+57h+string]
0x1800a2ab1  mov     rcx, rdi
0x1800a2ab4  mov     rdx, [rax+18h]
0x1800a2ab8  mov     rax, rbx
0x1800a2abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ac0  mov     ebx, eax
0x1800a2ac2  test    eax, eax
0x1800a2ac4  jns     short loc_1800A2AEB
0x1800a2ac6  mov     r9d, 4Ah ; 'J'
0x1800a2acc  mov     edx, 1
0x1800a2ad1  mov     ecx, ebx; int
0x1800a2ad3  call    Log_HREvent_78
0x1800a2ad8  mov     rcx, [rbp+57h+string]; string
0x1800a2adc  call    cs:__imp_WindowsDeleteString
0x1800a2ae2  mov     [rbp+57h+string], r15
0x1800a2ae6  jmp     loc_1800A2A1D
0x1800a2aeb  mov     rdi, [rbp+57h+var_48]
0x1800a2aef  lea     rdx, off_1800FD7E8; "Date"
0x1800a2af6  mov     [rbp+57h+var_5F], r15b
0x1800a2afa  lea     rcx, [rbp+57h+var_80]
0x1800a2afe  mov     rax, [rdi]
0x1800a2b01  mov     rbx, [rax+40h]
0x1800a2b05  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a2b0a  lea     r8, [rbp+57h+var_5F]
0x1800a2b0e  mov     rcx, rdi
0x1800a2b11  mov     rdx, [rax+18h]
0x1800a2b15  mov     rax, rbx
0x1800a2b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2b1d  mov     ebx, eax
0x1800a2b1f  test    eax, eax
0x1800a2b21  jns     short loc_1800A2B2B
0x1800a2b23  mov     r9d, 4Eh ; 'N'
0x1800a2b29  jmp     short loc_1800A2ACC
0x1800a2b2b  mov     [rbp+57h+var_40], r15
0x1800a2b2f  cmp     [rbp+57h+var_5F], r15b
0x1800a2b33  jz      short loc_1800A2B98
0x1800a2b35  mov     rdi, [rbp+57h+var_48]
0x1800a2b39  xor     ecx, ecx; string
0x1800a2b3b  mov     rax, [rdi]
0x1800a2b3e  mov     rbx, [rax+30h]
0x1800a2b42  call    cs:__imp_WindowsDeleteString
0x1800a2b48  lea     rdx, off_1800FD7E8; "Date"
0x1800a2b4f  mov     [rbp+57h+var_40], r15
0x1800a2b53  lea     rcx, [rbp+57h+var_80]
0x1800a2b57  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800a2b5c  lea     r8, [rbp+57h+var_40]
0x1800a2b60  mov     rcx, rdi
0x1800a2b63  mov     rdx, [rax+18h]
0x1800a2b67  mov     rax, rbx
0x1800a2b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2b6f  mov     ebx, eax
0x1800a2b71  test    eax, eax
0x1800a2b73  jns     short loc_1800A2B98
0x1800a2b75  mov     edx, 1
0x1800a2b7a  mov     ecx, eax; int
0x1800a2b7c  lea     r9d, [rdx+52h]
0x1800a2b80  call    Log_HREvent_78
0x1800a2b85  mov     rcx, [rbp+57h+var_40]; string
0x1800a2b89  call    cs:__imp_WindowsDeleteString
0x1800a2b8f  mov     [rbp+57h+var_40], r15
0x1800a2b93  jmp     loc_1800A2AD8
0x1800a2b98  sub     esi, 1
0x1800a2b9b  jz      loc_1800A2C64
0x1800a2ba1  sub     esi, 1
0x1800a2ba4  jz      loc_1800A2C64
0x1800a2baa  sub     esi, 1
0x1800a2bad  jz      loc_1800A2C64
0x1800a2bb3  mov     eax, cs:dword_1800FD5F0
0x1800a2bb9  cmp     esi, 1
0x1800a2bbc  jz      short loc_1800A2C24
0x1800a2bbe  cmp     eax, 5
0x1800a2bc1  jbe     loc_1800A2CD1
0x1800a2bc7  mov     rcx, [rbp+57h+var_40]; string
0x1800a2bcb  xor     edx, edx; length
0x1800a2bcd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2bd3  mov     rcx, [rbp+57h+string]; string
0x1800a2bd7  xor     edx, edx; length
0x1800a2bd9  mov     [rbp+57h+var_98], rax
0x1800a2bdd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2be3  mov     [rbp+57h+var_90], rax
0x1800a2be7  lea     rdx, word_1800F2FC2
0x1800a2bee  mov     eax, [r14+18h]
0x1800a2bf2  mov     [rbp+57h+var_A0], eax
0x1800a2bf5  lea     rax, aMessagingcloud_4; "[MessagingCloudServices] ChatService tr"...
0x1800a2bfc  mov     [rbp+57h+var_88], rax
0x1800a2c00  lea     rax, [rbp+57h+var_98]
0x1800a2c04  mov     [rsp+0E0h+var_A8], rax
0x1800a2c09  lea     rax, [rbp+57h+var_90]
0x1800a2c0d  mov     [rsp+0E0h+var_B0], rax
0x1800a2c12  lea     rax, [rbp+57h+var_A0]
0x1800a2c16  mov     [rsp+0E0h+var_B8], rax
0x1800a2c1b  lea     rax, [rbp+57h+var_88]
0x1800a2c1f  jmp     loc_1800A2CC7
0x1800a2c24  cmp     eax, 4
0x1800a2c27  jbe     loc_1800A2CD1
0x1800a2c2d  mov     rcx, [rbp+57h+var_40]; string
0x1800a2c31  xor     edx, edx; length
0x1800a2c33  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2c39  mov     rcx, [rbp+57h+string]; string
0x1800a2c3d  xor     edx, edx; length
0x1800a2c3f  mov     [rbp+57h+var_88], rax
0x1800a2c43  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2c49  mov     [rbp+57h+var_90], rax
0x1800a2c4d  lea     rdx, byte_1800F2F5D
0x1800a2c54  mov     eax, [r14+18h]
0x1800a2c58  mov     [rbp+57h+var_A0], eax
0x1800a2c5b  lea     rax, aMessagingcloud_4; "[MessagingCloudServices] ChatService tr"...
0x1800a2c62  jmp     short loc_1800A2CA4
0x1800a2c64  mov     eax, cs:dword_1800FD5F0
0x1800a2c6a  cmp     eax, 2
0x1800a2c6d  jbe     short loc_1800A2CD1
0x1800a2c6f  mov     rcx, [rbp+57h+var_40]; string
0x1800a2c73  xor     edx, edx; length
0x1800a2c75  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2c7b  mov     rcx, [rbp+57h+string]; string
0x1800a2c7f  xor     edx, edx; length
0x1800a2c81  mov     [rbp+57h+var_88], rax
0x1800a2c85  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2c8b  mov     [rbp+57h+var_90], rax
0x1800a2c8f  lea     rdx, byte_1800F3027
0x1800a2c96  mov     eax, [r14+18h]
0x1800a2c9a  mov     [rbp+57h+var_A0], eax
0x1800a2c9d  lea     rax, aMessagingcloud_10; "[MessagingCloudServices] ChatService tr"...
0x1800a2ca4  mov     [rbp+57h+var_98], rax
0x1800a2ca8  lea     rax, [rbp+57h+var_88]
0x1800a2cac  mov     [rsp+0E0h+var_A8], rax
0x1800a2cb1  lea     rax, [rbp+57h+var_90]
0x1800a2cb5  mov     [rsp+0E0h+var_B0], rax
0x1800a2cba  lea     rax, [rbp+57h+var_A0]
0x1800a2cbe  mov     [rsp+0E0h+var_B8], rax
0x1800a2cc3  lea     rax, [rbp+57h+var_98]
0x1800a2cc7  mov     [rsp+0E0h+var_C0], rax
0x1800a2ccc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800a2cd1  mov     rcx, [rbp+57h+var_40]; string
0x1800a2cd5  call    cs:__imp_WindowsDeleteString
0x1800a2cdb  mov     rcx, [rbp+57h+string]; string
0x1800a2cdf  mov     [rbp+57h+var_40], r15
0x1800a2ce3  call    cs:__imp_WindowsDeleteString
0x1800a2ce9  lea     rcx, [rbp+57h+var_48]
0x1800a2ced  mov     [rbp+57h+string], r15
0x1800a2cf1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2cf6  mov     rcx, [rbp+57h+var_58]
0x1800a2cfa  test    rcx, rcx
0x1800a2cfd  jz      short loc_1800A2D0F
0x1800a2cff  mov     [rbp+57h+var_58], r15
0x1800a2d03  mov     rax, [rcx]
0x1800a2d06  mov     rax, [rax+10h]
0x1800a2d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d0f  xor     eax, eax
0x1800a2d11  mov     rcx, [rbp+57h+var_38]
0x1800a2d15  xor     rcx, rsp; StackCookie
0x1800a2d18  call    __security_check_cookie
0x1800a2d1d  add     rsp, 0B8h
0x1800a2d24  pop     r15
0x1800a2d26  pop     r14
0x1800a2d28  pop     rdi
0x1800a2d29  pop     rsi
0x1800a2d2a  pop     rbx
0x1800a2d2b  pop     rbp
0x1800a2d2c  retn
```
