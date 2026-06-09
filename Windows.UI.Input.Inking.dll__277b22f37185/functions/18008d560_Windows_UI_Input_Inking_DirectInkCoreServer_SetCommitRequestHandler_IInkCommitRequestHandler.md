# Windows::UI::Input::Inking::DirectInkCoreServer::SetCommitRequestHandler(IInkCommitRequestHandler *)

- ea: `0x18008d560`
- end: `0x18008d692`
- name: `?SetCommitRequestHandler@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAUIInkCommitRequestHandler@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::DirectInkCoreServer *__hidden this, struct IInkCommitRequestHandler *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b9c`
- `0x1800032f4`
- `0x1800101bc`
- `0x18008b1e4`
- `0x18008d560`
- `0x1800930e4`
- `0x180097410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d57b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d57b`

## string_xrefs

- `0x18008d651`: `DirectInkCoreServer::SetCommitRequestHandler[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::SetCommitRequestHandler(
        Windows::UI::Input::Inking::DirectInkCoreServer *this,
        struct IInkCommitRequestHandler *a2)
{
  int v2; // ebx
  __int64 v5; // r8
  int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int16 *v10; // rdx
  int v12; // [rsp+60h] [rbp+20h] BYREF
  struct ICommitProvider *v13; // [rsp+70h] [rbp+30h] BYREF
  const wchar_t *v14; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_DWORD *)this + 690);
  if ( GetCurrentThreadId() == v2 )
  {
    v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 80));
    if ( v6 >= 0 )
    {
      LOBYTE(v12) = 0;
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      v6 = CCommitProviderTracker::SetDesktopParam<IInkCommitRequestHandler>(
             (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 2600),
             &v13);
      if ( v6 >= 0 && (_BYTE)v12 )
        v6 = CDirectInkImpl::SetCommitProvider(
               (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 120),
               v13);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
        {
          v10 = word_1801365CA;
LABEL_14:
          v14 = L"DirectInkCoreServer::SetCommitRequestHandler[Exit]";
          v13 = a2;
          v12 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            v7,
            (_DWORD)v10,
            v8,
            v9,
            (__int64)&v14,
            (__int64)&v12,
            (__int64)&v13);
          return (unsigned int)v6;
        }
        return (unsigned int)v6;
      }
    }
  }
  else
  {
    v6 = -2147417842;
  }
  if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
  {
    v10 = &word_1801362D6;
    goto LABEL_14;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008d560  mov     [rsp-18h+arg_8], rbx
0x18008d565  push    rbp
0x18008d566  push    rsi
0x18008d567  push    rdi
0x18008d568  mov     rbp, rsp
0x18008d56b  sub     rsp, 40h
0x18008d56f  mov     ebx, [rcx+0AC8h]
0x18008d575  mov     rsi, rdx
0x18008d578  mov     rdi, rcx
0x18008d57b  call    cs:__imp_GetCurrentThreadId
0x18008d581  cmp     eax, ebx
0x18008d583  jnz     loc_18008D625
0x18008d589  lea     rcx, [rdi+50h]; this
0x18008d58d  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008d592  mov     ebx, eax
0x18008d594  test    eax, eax
0x18008d596  js      loc_18008D62A
0x18008d59c  lea     rcx, [rbp+arg_10]
0x18008d5a0  mov     byte ptr [rbp+arg_0], 0
0x18008d5a4  mov     [rbp+arg_10], 0
0x18008d5ac  lea     rbx, [rdi+0A28h]
0x18008d5b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d5b8  lea     rax, [rbp+arg_10]
0x18008d5bc  mov     r8, rsi
0x18008d5bf  lea     rdx, [rbx+18h]
0x18008d5c3  mov     [rsp+40h+var_20], rax; struct ICommitProvider **
0x18008d5c8  lea     r9, [rbp+arg_0]
0x18008d5cc  mov     rcx, rbx; this
0x18008d5cf  call    ??$SetDesktopParam@UIInkCommitRequestHandler@@@CCommitProviderTracker@@IEAAJAEAV?$ComPtr@UIInkCommitRequestHandler@@@WRL@Microsoft@@PEAUIUnknown@@PEA_NPEAPEAUICommitProvider@@@Z; CCommitProviderTracker::SetDesktopParam<IInkCommitRequestHandler>(Microsoft::WRL::ComPtr<IInkCommitRequestHandler> &,IUnknown *,bool *,ICommitProvider * *)
0x18008d5d4  mov     ebx, eax
0x18008d5d6  test    eax, eax
0x18008d5d8  js      short loc_18008D5EF
0x18008d5da  cmp     byte ptr [rbp+arg_0], 0
0x18008d5de  jz      short loc_18008D5EF
0x18008d5e0  mov     rdx, [rbp+arg_10]; struct ICommitProvider *
0x18008d5e4  lea     rcx, [rdi+78h]; this
0x18008d5e8  call    ?SetCommitProvider@CDirectInkImpl@@QEAAJPEAUICommitProvider@@@Z; CDirectInkImpl::SetCommitProvider(ICommitProvider *)
0x18008d5ed  mov     ebx, eax
0x18008d5ef  lea     rcx, [rbp+arg_10]
0x18008d5f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d5f8  test    ebx, ebx
0x18008d5fa  js      short loc_18008D62A
0x18008d5fc  mov     eax, cs:dword_18015B128
0x18008d602  cmp     eax, 4
0x18008d605  jbe     short loc_18008D683
0x18008d607  mov     edx, 1
0x18008d60c  lea     rcx, dword_18015B128
0x18008d613  call    _tlgKeywordOn
0x18008d618  test    al, al
0x18008d61a  jz      short loc_18008D683
0x18008d61c  lea     rdx, word_1801365CA
0x18008d623  jmp     short loc_18008D651
0x18008d625  mov     ebx, 8001010Eh
0x18008d62a  mov     eax, cs:dword_18015B128
0x18008d630  cmp     eax, 2
0x18008d633  jbe     short loc_18008D683
0x18008d635  mov     edx, 1
0x18008d63a  lea     rcx, dword_18015B128
0x18008d641  call    _tlgKeywordOn
0x18008d646  test    al, al
0x18008d648  jz      short loc_18008D683
0x18008d64a  lea     rdx, word_1801362D6
0x18008d651  lea     rax, aDirectinkcores_18; "DirectInkCoreServer::SetCommitRequestHa"...
0x18008d658  mov     [rbp+arg_18], rax
0x18008d65c  lea     rax, [rbp+arg_10]
0x18008d660  mov     [rsp+40h+var_10], rax
0x18008d665  lea     rax, [rbp+arg_0]
0x18008d669  mov     [rsp+40h+var_18], rax
0x18008d66e  lea     rax, [rbp+arg_18]
0x18008d672  mov     [rsp+40h+var_20], rax
0x18008d677  mov     [rbp+arg_10], rsi
0x18008d67b  mov     [rbp+arg_0], ebx
0x18008d67e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18008d683  mov     eax, ebx
0x18008d685  mov     rbx, [rsp+40h+arg_8]
0x18008d68a  add     rsp, 40h
0x18008d68e  pop     rdi
0x18008d68f  pop     rsi
0x18008d690  pop     rbp
0x18008d691  retn
```
