# TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount::Stop(Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *)

- ea: `0x18001d6a0`
- end: `0x18001db9b`
- name: `?Stop@TokenBrokerInternalGetDefaultSignInAccount@TbLogProvider@@QEAAXPEAUIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Z`
- size: `1275`
- prototype: `void __fastcall(TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount *__hidden this, struct Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c3c8`

## callees

- `0x180003d14`
- `0x18000fcf8`
- `0x18001d6a0`
- `0x180024118`
- `0x1800455a4`
- `0x18004bd88`
- `0x18004c814`
- `0x18005e830`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dacd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dacd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d83f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001daa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dabf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d83f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001daa7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dabf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d75b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d7b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d75b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d7b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001db80`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount::Stop(
        TbLogProvider::TokenBrokerInternalGetDefaultSignInAccount *this,
        struct Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *a2)
{
  struct Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *v2; // r8
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  void (__fastcall *v7)(__int64, HSTRING *); // rdi
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, HSTRING *); // rbx
  __int64 v10; // rbx
  int v11; // eax
  int *v12; // rbx
  const struct _tlgProvider_t *v13; // rax
  int v14; // edi
  int v15; // r9d
  const struct _tlgProvider_t *v16; // rbx
  __int64 v17; // r8
  HSTRING v18; // [rsp+D0h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-B0h] BYREF
  __int64 *v20; // [rsp+E0h] [rbp-A8h] BYREF
  int v21; // [rsp+E8h] [rbp-A0h] BYREF
  int v22; // [rsp+ECh] [rbp-9Ch] BYREF
  int v23; // [rsp+F0h] [rbp-98h] BYREF
  int v24; // [rsp+F4h] [rbp-94h] BYREF
  int v25; // [rsp+F8h] [rbp-90h] BYREF
  __int64 v26; // [rsp+100h] [rbp-88h] BYREF
  PCWSTR v27; // [rsp+108h] [rbp-80h] BYREF
  PCWSTR StringRawBuffer; // [rsp+110h] [rbp-78h] BYREF
  PCWSTR v29; // [rsp+118h] [rbp-70h] BYREF
  __int64 v30; // [rsp+120h] [rbp-68h] BYREF
  __int64 v31; // [rsp+128h] [rbp-60h] BYREF
  __int64 v32; // [rsp+130h] [rbp-58h] BYREF
  __int64 v33; // [rsp+138h] [rbp-50h] BYREF
  __int64 v34; // [rsp+140h] [rbp-48h] BYREF
  __int64 v35; // [rsp+148h] [rbp-40h] BYREF
  __int64 v36; // [rsp+150h] [rbp-38h] BYREF
  __int64 v37; // [rsp+158h] [rbp-30h] BYREF
  _QWORD v38[5]; // [rsp+160h] [rbp-28h] BYREF
  __int64 v39; // [rsp+198h] [rbp+10h] BYREF
  __int64 v40; // [rsp+1A0h] [rbp+18h] BYREF
  PCWSTR v41; // [rsp+1A8h] [rbp+20h] BYREF

  try
  {
    v2 = a2;
    string = 0;
    v18 = 0;
    v20 = 0;
    if ( a2 )
    {
      v4 = *(_QWORD *)a2;
      v20 = 0;
      if ( (*(int (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *, __int64 **, struct Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult *))(v4 + 48))(
             a2,
             &v20,
             a2) >= 0 )
      {
        v39 = 0;
        if ( v20 )
        {
          v5 = *v20;
          v39 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64 *))(v5 + 48))(v20, &v39) >= 0 )
          {
            v6 = v39;
            if ( v39 )
            {
              v7 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
              WindowsDeleteString(string);
              string = 0;
              v7(v6, &string);
              v40 = 0;
              if ( (int)wil::com_query_to_nothrow<Windows::Security::Credentials::IWebAccountProvider2,wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &>(
                          &v39,
                          (__int64)&v40) >= 0 )
              {
                v8 = v40;
                v9 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 56LL);
                WindowsDeleteString(v18);
                v18 = 0;
                v9(v8, &v18);
              }
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v40);
            }
          }
        }
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v39);
      }
    }
    v10 = *((_QWORD *)this + 34);
    v11 = *(_DWORD *)(v10 + 72);
    if ( v11 < 0 && (v12 = (int *)(v10 + 80), v11 == v12[2]) && v12 )
    {
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this, a2, v2);
      v13 = TbLogProvider::Provider();
      v14 = (int)v13;
      if ( *(_DWORD *)v13 > 5u )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v18, 0);
        v29 = WindowsGetStringRawBuffer(string, 0);
        v30 = *((_QWORD *)v12 + 6);
        LODWORD(v39) = v12[17];
        LODWORD(v40) = v12[4];
        v31 = *((_QWORD *)v12 + 15);
        v32 = *((_QWORD *)v12 + 14);
        LODWORD(v41) = v12[26];
        v33 = *((_QWORD *)v12 + 12);
        v34 = *((_QWORD *)v12 + 11);
        v21 = v12[20];
        v35 = *((_QWORD *)v12 + 9);
        v22 = v12[8];
        v36 = *((_QWORD *)v12 + 3);
        v23 = *v12;
        v37 = *((_QWORD *)v12 + 16);
        v24 = v12[16];
        v38[0] = *((_QWORD *)v12 + 7);
        v25 = v12[2];
        v26 = 0x1000000;
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v14,
          (unsigned int)&unk_18014EF28,
          *((_QWORD *)this + 34) + 8,
          v15,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)v38,
          (__int64)&v24,
          (__int64)&v37,
          (__int64)&v23,
          (__int64)&v36,
          (__int64)&v22,
          (__int64)&v35,
          (__int64)&v21,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v41,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&StringRawBuffer);
      }
    }
    else
    {
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this, a2, v2);
      v16 = TbLogProvider::Provider();
      if ( *(_DWORD *)v16 > 5u )
      {
        v41 = WindowsGetStringRawBuffer(v18, 0);
        v27 = WindowsGetStringRawBuffer(string, 0);
        LODWORD(v39) = GetCurrentThreadId();
        v17 = *((_QWORD *)this + 34);
        LODWORD(v40) = *(_DWORD *)(v17 + 72);
        v26 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v16,
          &dword_18014F0A4,
          v17 + 8,
          0,
          &v26,
          &v40,
          &v39,
          &v27,
          &v41);
      }
    }
    wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v20);
    WindowsDeleteString(v18);
    v18 = 0;
    WindowsDeleteString(string);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18001d6a0  mov     r11, rsp
0x18001d6a3  mov     [r11+8], rbx
0x18001d6a7  push    rsi
0x18001d6a8  push    rdi
0x18001d6a9  push    r14
0x18001d6ab  sub     rsp, 170h
0x18001d6b2  mov     r8, rdx
0x18001d6b5  mov     rsi, rcx
0x18001d6b8  xor     r14d, r14d
0x18001d6bb  mov     [r11-0B0h], r14
0x18001d6c2  mov     [r11-0B8h], r14
0x18001d6c9  mov     [r11-0A8h], r14
0x18001d6d0  test    rdx, rdx
0x18001d6d3  jz      loc_18001D7F2
0x18001d6d9  mov     rax, [rdx]
0x18001d6dc  mov     [r11-0A8h], r14
0x18001d6e3  lea     rdx, [r11-0A8h]
0x18001d6ea  mov     rcx, r8
0x18001d6ed  mov     rax, [rax+30h]
0x18001d6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6f6  test    eax, eax
0x18001d6f8  js      loc_18001D7F2
0x18001d6fe  mov     [rsp+188h+arg_8], r14
0x18001d706  mov     rcx, [rsp+188h+var_A8]
0x18001d70e  test    rcx, rcx
0x18001d711  jz      loc_18001D7E5
0x18001d717  mov     rax, [rcx]
0x18001d71a  mov     [rsp+188h+arg_8], r14
0x18001d722  lea     rdx, [rsp+188h+arg_8]
0x18001d72a  mov     rax, [rax+30h]
0x18001d72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d733  test    eax, eax
0x18001d735  js      loc_18001D7E5
0x18001d73b  mov     rbx, [rsp+188h+arg_8]
0x18001d743  test    rbx, rbx
0x18001d746  jz      loc_18001D7E5
0x18001d74c  mov     rax, [rbx]
0x18001d74f  mov     rdi, [rax+30h]
0x18001d753  mov     rcx, [rsp+188h+string]; string
0x18001d75b  call    cs:__imp_WindowsDeleteString
0x18001d761  mov     [rsp+188h+string], r14
0x18001d769  lea     rdx, [rsp+188h+string]
0x18001d771  mov     rcx, rbx
0x18001d774  mov     rax, rdi
0x18001d777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d77c  nop
0x18001d77d  mov     [rsp+188h+arg_10], r14
0x18001d785  lea     rdx, [rsp+188h+arg_10]
0x18001d78d  lea     rcx, [rsp+188h+arg_8]
0x18001d795  call    ??$com_query_to_nothrow@UIWebAccountProvider2@Credentials@Security@Windows@@AEAV?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@0@PEAPEAUIWebAccountProvider2@Credentials@Security@Windows@@@Z; wil::com_query_to_nothrow<Windows::Security::Credentials::IWebAccountProvider2,wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &>(wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_returncode_policy> &,Windows::Security::Credentials::IWebAccountProvider2 * *)
0x18001d79a  test    eax, eax
0x18001d79c  js      short loc_18001D7D7
0x18001d79e  mov     rdi, [rsp+188h+arg_10]
0x18001d7a6  mov     rax, [rdi]
0x18001d7a9  mov     rbx, [rax+38h]
0x18001d7ad  mov     rcx, [rsp+188h+var_B8]; string
0x18001d7b5  call    cs:__imp_WindowsDeleteString
0x18001d7bb  mov     [rsp+188h+var_B8], r14
0x18001d7c3  lea     rdx, [rsp+188h+var_B8]
0x18001d7cb  mov     rcx, rdi
0x18001d7ce  mov     rax, rbx
0x18001d7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d6  nop
0x18001d7d7  lea     rcx, [rsp+188h+arg_10]
0x18001d7df  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18001d7e4  nop
0x18001d7e5  lea     rcx, [rsp+188h+arg_8]
0x18001d7ed  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18001d7f2  mov     rbx, [rsi+110h]
0x18001d7f9  mov     eax, [rbx+48h]
0x18001d7fc  test    eax, eax
0x18001d7fe  jns     loc_18001DA82
0x18001d804  add     rbx, 50h ; 'P'
0x18001d808  cmp     eax, [rbx+8]
0x18001d80b  jnz     loc_18001DA82
0x18001d811  test    rbx, rbx
0x18001d814  jz      loc_18001DA82
0x18001d81a  mov     rcx, rsi
0x18001d81d  call    ?zInternalStop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001d822  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x18001d827  mov     rdi, rax
0x18001d82a  mov     ecx, [rax]
0x18001d82c  cmp     ecx, 5
0x18001d82f  jbe     loc_18001DB4B
0x18001d835  xor     edx, edx; length
0x18001d837  mov     rcx, [rsp+188h+var_B8]; string
0x18001d83f  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d845  mov     [rsp+188h+var_78], rax
0x18001d84d  xor     edx, edx; length
0x18001d84f  mov     rcx, [rsp+188h+string]; string
0x18001d857  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d85d  mov     [rsp+188h+var_70], rax
0x18001d865  mov     rax, [rbx+30h]
0x18001d869  mov     [rsp+188h+var_68], rax
0x18001d871  mov     eax, [rbx+44h]
0x18001d874  mov     dword ptr [rsp+188h+arg_8], eax
0x18001d87b  mov     eax, [rbx+10h]
0x18001d87e  mov     dword ptr [rsp+188h+arg_10], eax
0x18001d885  mov     rax, [rbx+78h]
0x18001d889  mov     [rsp+188h+var_60], rax
0x18001d891  mov     rax, [rbx+70h]
0x18001d895  mov     [rsp+188h+var_58], rax
0x18001d89d  mov     eax, [rbx+68h]
0x18001d8a0  mov     dword ptr [rsp+188h+arg_18], eax
0x18001d8a7  mov     rax, [rbx+60h]
0x18001d8ab  mov     [rsp+188h+var_50], rax
0x18001d8b3  mov     rax, [rbx+58h]
0x18001d8b7  mov     [rsp+188h+var_48], rax
0x18001d8bf  mov     eax, [rbx+50h]
0x18001d8c2  mov     [rsp+188h+var_A0], eax
0x18001d8c9  mov     rax, [rbx+48h]
0x18001d8cd  mov     [rsp+188h+var_40], rax
0x18001d8d5  mov     eax, [rbx+20h]
0x18001d8d8  mov     [rsp+188h+var_9C], eax
0x18001d8df  mov     rax, [rbx+18h]
0x18001d8e3  mov     [rsp+188h+var_38], rax
0x18001d8eb  mov     eax, [rbx]
0x18001d8ed  mov     [rsp+188h+var_98], eax
0x18001d8f4  mov     rax, [rbx+80h]
0x18001d8fb  mov     [rsp+188h+var_30], rax
0x18001d903  mov     eax, [rbx+40h]
0x18001d906  mov     [rsp+188h+var_94], eax
0x18001d90d  mov     rax, [rbx+38h]
0x18001d911  mov     [rsp+188h+var_28], rax
0x18001d919  mov     eax, [rbx+8]
0x18001d91c  mov     [rsp+188h+var_90], eax
0x18001d923  mov     [rsp+188h+var_88], 1000000h
0x18001d92f  mov     [rsp+188h+var_80], r14
0x18001d937  mov     r8, [rsi+110h]
0x18001d93e  add     r8, 8
0x18001d942  lea     rax, [rsp+188h+var_78]
0x18001d94a  mov     [rsp+188h+var_C8], rax
0x18001d952  lea     rax, [rsp+188h+var_70]
0x18001d95a  mov     [rsp+188h+var_D0], rax
0x18001d962  lea     rax, [rsp+188h+var_68]
0x18001d96a  mov     [rsp+188h+var_D8], rax
0x18001d972  lea     rax, [rsp+188h+arg_8]
0x18001d97a  mov     [rsp+188h+var_E0], rax
0x18001d982  lea     rax, [rsp+188h+arg_10]
0x18001d98a  mov     [rsp+188h+var_E8], rax
0x18001d992  lea     rax, [rsp+188h+var_60]
0x18001d99a  mov     [rsp+188h+var_F0], rax
0x18001d9a2  lea     rax, [rsp+188h+var_58]
0x18001d9aa  mov     [rsp+188h+var_F8], rax
0x18001d9b2  lea     rax, [rsp+188h+arg_18]
0x18001d9ba  mov     [rsp+188h+var_100], rax
0x18001d9c2  lea     rax, [rsp+188h+var_50]
0x18001d9ca  mov     [rsp+188h+var_108], rax
0x18001d9d2  lea     rax, [rsp+188h+var_48]
0x18001d9da  mov     [rsp+188h+var_110], rax
0x18001d9df  lea     rax, [rsp+188h+var_A0]
0x18001d9e7  mov     [rsp+188h+var_118], rax
0x18001d9ec  lea     rax, [rsp+188h+var_40]
0x18001d9f4  mov     [rsp+188h+var_120], rax
0x18001d9f9  lea     rax, [rsp+188h+var_9C]
0x18001da01  mov     [rsp+188h+var_128], rax
0x18001da06  lea     rax, [rsp+188h+var_38]
0x18001da0e  mov     [rsp+188h+var_130], rax
0x18001da13  lea     rax, [rsp+188h+var_98]
0x18001da1b  mov     [rsp+188h+var_138], rax
0x18001da20  lea     rax, [rsp+188h+var_30]
0x18001da28  mov     [rsp+188h+var_140], rax
0x18001da2d  lea     rax, [rsp+188h+var_94]
0x18001da35  mov     [rsp+188h+var_148], rax
0x18001da3a  lea     rax, [rsp+188h+var_28]
0x18001da42  mov     [rsp+188h+var_150], rax
0x18001da47  lea     rax, [rsp+188h+var_90]
0x18001da4f  mov     [rsp+188h+var_158], rax
0x18001da54  lea     rax, [rsp+188h+var_88]
0x18001da5c  mov     [rsp+188h+var_160], rax
0x18001da61  lea     rax, [rsp+188h+var_80]
0x18001da69  mov     [rsp+188h+var_168], rax
0x18001da6e  lea     rdx, unk_18014EF28
0x18001da75  mov     rcx, rdi
0x18001da78  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001da7d  jmp     loc_18001DB4B
0x18001da82  mov     rcx, rsi
0x18001da85  call    ?zInternalStop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001da8a  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x18001da8f  mov     rbx, rax
0x18001da92  mov     ecx, [rax]
0x18001da94  cmp     ecx, 5
0x18001da97  jbe     loc_18001DB4B
0x18001da9d  xor     edx, edx; length
0x18001da9f  mov     rcx, [rsp+188h+var_B8]; string
0x18001daa7  call    cs:__imp_WindowsGetStringRawBuffer
0x18001daad  mov     [rsp+188h+arg_18], rax
0x18001dab5  xor     edx, edx; length
0x18001dab7  mov     rcx, [rsp+188h+string]; string
0x18001dabf  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dac5  mov     [rsp+188h+var_80], rax
0x18001dacd  call    cs:__imp_GetCurrentThreadId
0x18001dad3  mov     dword ptr [rsp+188h+arg_8], eax
0x18001dada  mov     r8, [rsi+110h]
0x18001dae1  mov     eax, [r8+48h]
0x18001dae5  mov     dword ptr [rsp+188h+arg_10], eax
0x18001daec  mov     [rsp+188h+var_88], r14
0x18001daf4  add     r8, 8
0x18001daf8  lea     rax, [rsp+188h+arg_18]
0x18001db00  mov     [rsp+188h+var_148], rax
0x18001db05  lea     rax, [rsp+188h+var_80]
0x18001db0d  mov     [rsp+188h+var_150], rax
0x18001db12  lea     rax, [rsp+188h+arg_8]
0x18001db1a  mov     [rsp+188h+var_158], rax
0x18001db1f  lea     rax, [rsp+188h+arg_10]
0x18001db27  mov     [rsp+188h+var_160], rax
0x18001db2c  lea     rax, [rsp+188h+var_88]
0x18001db34  mov     [rsp+188h+var_168], rax
0x18001db39  xor     r9d, r9d
0x18001db3c  lea     rdx, dword_18014F0A4
0x18001db43  mov     rcx, rbx
0x18001db46  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001db4b  mov     rcx, rsi
0x18001db4e  call    ?IgnoreCurrentThread@?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001db53  nop
0x18001db54  lea     rcx, [rsp+188h+var_A8]
0x18001db5c  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18001db61  nop
0x18001db62  mov     rcx, [rsp+188h+var_B8]; string
0x18001db6a  call    cs:__imp_WindowsDeleteString
0x18001db70  mov     [rsp+188h+var_B8], r14
0x18001db78  mov     rcx, [rsp+188h+string]; string
0x18001db80  call    cs:__imp_WindowsDeleteString
0x18001db86  nop
0x18001db87  mov     rbx, [rsp+188h+arg_0]
0x18001db8f  add     rsp, 170h
0x18001db96  pop     r14
0x18001db98  pop     rdi
0x18001db99  pop     rsi
0x18001db9a  retn
```
