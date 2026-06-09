# DownloadManager::ProcessResponseMessage(Windows::Web::Http::IHttpResponseMessage *,HSTRING__ * *)

- ea: `0x18001890c`
- end: `0x180018bf7`
- name: `?ProcessResponseMessage@DownloadManager@@AEAAJPEAUIHttpResponseMessage@Http@Web@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `747`
- prototype: `__int64 __fastcall(DownloadManager *__hidden this, struct Windows::Web::Http::IHttpResponseMessage *, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015978`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x18000216c`
- `0x18000517c`
- `0x180014a3c`
- `0x18001890c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018b2d`

## string_xrefs

- `0x1800189b2`: `Get Sas uri http response`
- `0x180018a7a`: `Get Sas uri http response to string async operation`
- `0x180018b4e`: `Get Sas uri http response to string result`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DownloadManager::ProcessResponseMessage(
        DownloadManager *this,
        struct Windows::Web::Http::IHttpResponseMessage *a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Web::Http::IHttpResponseMessage *, __int64 *); // rbx
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, char **); // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  char *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  char *v28; // [rsp+60h] [rbp-19h] BYREF
  const char *v29; // [rsp+68h] [rbp-11h] BYREF
  const char *v30; // [rsp+70h] [rbp-9h] BYREF
  const char *v31; // [rsp+78h] [rbp-1h] BYREF
  char *v32; // [rsp+80h] [rbp+7h] BYREF
  __int64 v33; // [rsp+88h] [rbp+Fh] BYREF
  PCWSTR StringRawBuffer; // [rsp+90h] [rbp+17h] BYREF
  char *v35; // [rsp+98h] [rbp+1Fh] BYREF
  struct Windows::Web::Http::IHttpResponseMessage *v36; // [rsp+A0h] [rbp+27h] BYREF
  int v37; // [rsp+E8h] [rbp+6Fh] BYREF
  int v38; // [rsp+F8h] [rbp+7Fh] BYREF

  v36 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Web::Http::IHttpResponseMessage *))(*(_QWORD *)a2 + 8LL))(a2);
  v33 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Web::Http::IHttpResponseMessage *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v33);
  v8 = v6(a2, &v33);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v7, v9) )
  {
    v28 = (char *)this + 108;
    v37 = 107;
    v29 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
    v30 = "DownloadManager::ProcessResponseMessage";
    v31 = "Get Sas uri http response";
    v38 = v8;
    v32 = (char *)this + 237;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)this + 108,
      (unsigned int)word_180031002,
      v10,
      v11,
      (__int64)&v32,
      (__int64)&v38,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v37,
      (__int64)&v28);
  }
  if ( v8 >= 0 )
  {
    v28 = 0;
    v12 = v33;
    v13 = *(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v33 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v28);
    v8 = v13(v12, &v28);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v15, v14, v16) )
    {
      v32 = (char *)this + 108;
      v37 = 117;
      v31 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
      v30 = "DownloadManager::ProcessResponseMessage";
      v29 = "Get Sas uri http response to string async operation";
      v38 = v8;
      StringRawBuffer = (PCWSTR)((char *)this + 237);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)&byte_180030F8F,
        v18,
        v19,
        (__int64)&StringRawBuffer,
        (__int64)&v38,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31,
        (__int64)&v37,
        (__int64)&v32);
    }
    if ( v8 >= 0 )
    {
      v20 = v28;
      v8 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(v28);
      if ( v8 >= 0 )
        v8 = (*(__int64 (__fastcall **)(char *, HSTRING *))(*(_QWORD *)v20 + 80LL))(v20, a3);
      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v22, v21, v23) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*a3, 0);
        v32 = (char *)this + 108;
        v37 = 127;
        v31 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
        v30 = "DownloadManager::ProcessResponseMessage";
        v29 = "Get Sas uri http response to string result";
        v38 = v8;
        v35 = (char *)this + 237;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v24,
          (unsigned int)byte_180030F09,
          v25,
          v26,
          (__int64)&v35,
          (__int64)&v38,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v37,
          (__int64)&v32,
          (__int64)&StringRawBuffer);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v28);
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v36);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001890c  mov     [rsp-8+arg_0], rbx
0x180018911  mov     [rsp-8+arg_10], rsi
0x180018916  push    rbp
0x180018917  push    rdi
0x180018918  push    r12
0x18001891a  push    r14
0x18001891c  push    r15
0x18001891e  lea     rbp, [rsp-37h]
0x180018923  sub     rsp, 0B0h
0x18001892a  mov     r14, r8
0x18001892d  mov     rdi, rdx
0x180018930  mov     rsi, rcx
0x180018933  mov     [rbp+57h+var_30], rdx
0x180018937  test    rdx, rdx
0x18001893a  jz      short loc_18001894C
0x18001893c  mov     rax, [rdx]
0x18001893f  mov     rcx, rdx
0x180018942  mov     rax, [rax+8]
0x180018946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001894b  nop
0x18001894c  mov     [rbp+57h+var_48], 0
0x180018954  mov     rax, [rdi]
0x180018957  mov     rbx, [rax+30h]
0x18001895b  lea     rcx, [rbp+57h+var_48]
0x18001895f  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018964  lea     rdx, [rbp+57h+var_48]
0x180018968  mov     rcx, rdi
0x18001896b  mov     rax, rbx
0x18001896e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018973  mov     ebx, eax
0x180018975  mov     ecx, cs:dword_180039000
0x18001897b  lea     r15, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180018982  lea     r12, aDownloadmanage_1; "DownloadManager::ProcessResponseMessage"
0x180018989  cmp     ecx, 5
0x18001898c  jbe     loc_180018A16
0x180018992  call    _tlgKeywordOn
0x180018997  test    al, al
0x180018999  jz      short loc_180018A16
0x18001899b  lea     rcx, [rsi+6Ch]
0x18001899f  mov     [rbp+57h+var_70], rcx
0x1800189a3  mov     [rbp+57h+arg_8], 6Bh ; 'k'
0x1800189aa  mov     [rbp+57h+var_68], r15
0x1800189ae  mov     [rbp+57h+var_60], r12
0x1800189b2  lea     rax, aGetSasUriHttpR_0; "Get Sas uri http response"
0x1800189b9  mov     [rbp+57h+var_58], rax
0x1800189bd  mov     [rbp+57h+arg_18], ebx
0x1800189c0  lea     rax, [rsi+0EDh]
0x1800189c7  mov     [rbp+57h+var_50], rax
0x1800189cb  lea     rax, [rbp+57h+var_70]
0x1800189cf  mov     [rsp+0D0h+var_80], rax
0x1800189d4  lea     rax, [rbp+57h+arg_8]
0x1800189d8  mov     [rsp+0D0h+var_88], rax
0x1800189dd  lea     rax, [rbp+57h+var_68]
0x1800189e1  mov     [rsp+0D0h+var_90], rax
0x1800189e6  lea     rax, [rbp+57h+var_60]
0x1800189ea  mov     [rsp+0D0h+var_98], rax
0x1800189ef  lea     rax, [rbp+57h+var_58]
0x1800189f3  mov     [rsp+0D0h+var_A0], rax
0x1800189f8  lea     rax, [rbp+57h+arg_18]
0x1800189fc  mov     [rsp+0D0h+var_A8], rax
0x180018a01  lea     rax, [rbp+57h+var_50]
0x180018a05  mov     [rsp+0D0h+var_B0], rax
0x180018a0a  lea     rdx, word_180031002
0x180018a11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018a16  test    ebx, ebx
0x180018a18  js      loc_180018BC6
0x180018a1e  mov     [rbp+57h+var_70], 0
0x180018a26  mov     rdi, [rbp+57h+var_48]
0x180018a2a  mov     rax, [rdi]
0x180018a2d  mov     rbx, [rax+50h]
0x180018a31  lea     rcx, [rbp+57h+var_70]
0x180018a35  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018a3a  lea     rdx, [rbp+57h+var_70]
0x180018a3e  mov     rcx, rdi
0x180018a41  mov     rax, rbx
0x180018a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a49  mov     ebx, eax
0x180018a4b  mov     eax, cs:dword_180039000
0x180018a51  cmp     eax, 5
0x180018a54  jbe     loc_180018ADE
0x180018a5a  call    _tlgKeywordOn
0x180018a5f  test    al, al
0x180018a61  jz      short loc_180018ADE
0x180018a63  lea     rax, [rsi+6Ch]
0x180018a67  mov     [rbp+57h+var_50], rax
0x180018a6b  mov     [rbp+57h+arg_8], 75h ; 'u'
0x180018a72  mov     [rbp+57h+var_58], r15
0x180018a76  mov     [rbp+57h+var_60], r12
0x180018a7a  lea     rax, aGetSasUriHttpR; "Get Sas uri http response to string asy"...
0x180018a81  mov     [rbp+57h+var_68], rax
0x180018a85  mov     [rbp+57h+arg_18], ebx
0x180018a88  lea     rax, [rsi+0EDh]
0x180018a8f  mov     [rbp+57h+var_40], rax
0x180018a93  lea     rax, [rbp+57h+var_50]
0x180018a97  mov     [rsp+0D0h+var_80], rax
0x180018a9c  lea     rax, [rbp+57h+arg_8]
0x180018aa0  mov     [rsp+0D0h+var_88], rax
0x180018aa5  lea     rax, [rbp+57h+var_58]
0x180018aa9  mov     [rsp+0D0h+var_90], rax
0x180018aae  lea     rax, [rbp+57h+var_60]
0x180018ab2  mov     [rsp+0D0h+var_98], rax
0x180018ab7  lea     rax, [rbp+57h+var_68]
0x180018abb  mov     [rsp+0D0h+var_A0], rax
0x180018ac0  lea     rax, [rbp+57h+arg_18]
0x180018ac4  mov     [rsp+0D0h+var_A8], rax
0x180018ac9  lea     rax, [rbp+57h+var_40]
0x180018acd  mov     [rsp+0D0h+var_B0], rax
0x180018ad2  lea     rdx, byte_180030F8F
0x180018ad9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018ade  test    ebx, ebx
0x180018ae0  js      loc_180018BBC
0x180018ae6  mov     rdi, [rbp+57h+var_70]
0x180018aea  mov     rcx, rdi
0x180018aed  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x180018af2  mov     ebx, eax
0x180018af4  test    eax, eax
0x180018af6  js      short loc_180018B0C
0x180018af8  mov     rax, [rdi]
0x180018afb  mov     rdx, r14
0x180018afe  mov     rcx, rdi
0x180018b01  mov     rax, [rax+50h]
0x180018b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b0a  mov     ebx, eax
0x180018b0c  mov     eax, cs:dword_180039000
0x180018b12  cmp     eax, 5
0x180018b15  jbe     loc_180018BBC
0x180018b1b  call    _tlgKeywordOn
0x180018b20  test    al, al
0x180018b22  jz      loc_180018BBC
0x180018b28  xor     edx, edx; length
0x180018b2a  mov     rcx, [r14]; string
0x180018b2d  call    cs:__imp_WindowsGetStringRawBuffer
0x180018b33  mov     [rbp+57h+var_40], rax
0x180018b37  lea     rax, [rsi+6Ch]
0x180018b3b  mov     [rbp+57h+var_50], rax
0x180018b3f  mov     [rbp+57h+arg_8], 7Fh
0x180018b46  mov     [rbp+57h+var_58], r15
0x180018b4a  mov     [rbp+57h+var_60], r12
0x180018b4e  lea     rax, aGetSasUriHttpR_1; "Get Sas uri http response to string res"...
0x180018b55  mov     [rbp+57h+var_68], rax
0x180018b59  mov     [rbp+57h+arg_18], ebx
0x180018b5c  lea     rax, [rsi+0EDh]
0x180018b63  mov     [rbp+57h+var_38], rax
0x180018b67  lea     rax, [rbp+57h+var_40]
0x180018b6b  mov     [rsp+0D0h+var_78], rax
0x180018b70  lea     rax, [rbp+57h+var_50]
0x180018b74  mov     [rsp+0D0h+var_80], rax
0x180018b79  lea     rax, [rbp+57h+arg_8]
0x180018b7d  mov     [rsp+0D0h+var_88], rax
0x180018b82  lea     rax, [rbp+57h+var_58]
0x180018b86  mov     [rsp+0D0h+var_90], rax
0x180018b8b  lea     rax, [rbp+57h+var_60]
0x180018b8f  mov     [rsp+0D0h+var_98], rax
0x180018b94  lea     rax, [rbp+57h+var_68]
0x180018b98  mov     [rsp+0D0h+var_A0], rax
0x180018b9d  lea     rax, [rbp+57h+arg_18]
0x180018ba1  mov     [rsp+0D0h+var_A8], rax
0x180018ba6  lea     rax, [rbp+57h+var_38]
0x180018baa  mov     [rsp+0D0h+var_B0], rax
0x180018baf  lea     rdx, byte_180030F09
0x180018bb6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018bbb  nop
0x180018bbc  lea     rcx, [rbp+57h+var_70]
0x180018bc0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018bc5  nop
0x180018bc6  lea     rcx, [rbp+57h+var_48]
0x180018bca  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018bcf  nop
0x180018bd0  lea     rcx, [rbp+57h+var_30]
0x180018bd4  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018bd9  mov     eax, ebx
0x180018bdb  lea     r11, [rsp+0D0h+var_20]
0x180018be3  mov     rbx, [r11+30h]
0x180018be7  mov     rsi, [r11+40h]
0x180018beb  mov     rsp, r11
0x180018bee  pop     r15
0x180018bf0  pop     r14
0x180018bf2  pop     r12
0x180018bf4  pop     rdi
0x180018bf5  pop     rbp
0x180018bf6  retn
```
