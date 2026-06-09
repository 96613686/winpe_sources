# Windows::UI::Input::Inking::DirectInkCoreServer::SetCommitProvider(ICommitProvider *)

- ea: `0x18008d420`
- end: `0x18008d555`
- name: `?SetCommitProvider@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAUICommitProvider@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::DirectInkCoreServer *__hidden this, struct ICommitProvider *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001b9c`
- `0x1800032f4`
- `0x1800101bc`
- `0x180019248`
- `0x180024444`
- `0x18008b1e4`
- `0x18008d420`
- `0x1800930e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d43b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008d43b`

## string_xrefs

- `0x18008d514`: `DirectInkCoreServer::SetCommitProvider[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::SetCommitProvider(
        Windows::UI::Input::Inking::DirectInkCoreServer *this,
        struct ICommitProvider *a2)
{
  int v2; // ebx
  __int64 v5; // r8
  int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rdx
  struct ICommitProvider *v12; // [rsp+60h] [rbp+20h] BYREF
  struct ICommitProvider *v13; // [rsp+70h] [rbp+30h] BYREF
  const wchar_t *v14; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_DWORD *)this + 712);
  if ( GetCurrentThreadId() == v2 )
  {
    v6 = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 168));
    if ( v6 >= 0 )
    {
      v12 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
      Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=((char *)this + 2696, a2);
      *((_BYTE *)this + 2688) = 1;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2704);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef((char *)this + 2696);
      v12 = (struct ICommitProvider *)*((_QWORD *)this + 337);
      v6 = CDirectInkImpl::SetCommitProvider(
             (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 208),
             v12);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
      if ( v6 >= 0 )
      {
        if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v5) )
        {
          v10 = byte_180136269;
LABEL_11:
          v14 = L"DirectInkCoreServer::SetCommitProvider[Exit]";
          v13 = a2;
          LODWORD(v12) = v6;
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
    v10 = &byte_180136467;
    goto LABEL_11;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008d420  mov     [rsp-18h+arg_8], rbx
0x18008d425  push    rbp
0x18008d426  push    rsi
0x18008d427  push    rdi
0x18008d428  mov     rbp, rsp
0x18008d42b  sub     rsp, 40h
0x18008d42f  mov     ebx, [rcx+0B20h]
0x18008d435  mov     rsi, rdx
0x18008d438  mov     rdi, rcx
0x18008d43b  call    cs:__imp_GetCurrentThreadId
0x18008d441  cmp     eax, ebx
0x18008d443  jnz     loc_18008D4E8
0x18008d449  lea     rcx, [rdi+0A8h]; this
0x18008d450  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008d455  mov     ebx, eax
0x18008d457  test    eax, eax
0x18008d459  js      loc_18008D4ED
0x18008d45f  lea     rcx, [rbp+arg_0]
0x18008d463  mov     [rbp+arg_0], 0
0x18008d46b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d470  lea     rbx, [rdi+0A88h]
0x18008d477  mov     rdx, rsi
0x18008d47a  mov     rcx, rbx
0x18008d47d  call    ??4?$ComPtr@UIDispatcherQueue@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDispatcherQueue@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(Windows::System::IDispatcherQueue *)
0x18008d482  lea     rcx, [rdi+0A90h]
0x18008d489  mov     byte ptr [rdi+0A80h], 1
0x18008d490  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d495  mov     rcx, rbx
0x18008d498  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x18008d49d  mov     rdx, [rbx]; struct ICommitProvider *
0x18008d4a0  lea     rcx, [rdi+0D0h]; this
0x18008d4a7  mov     [rbp+arg_0], rdx
0x18008d4ab  call    ?SetCommitProvider@CDirectInkImpl@@QEAAJPEAUICommitProvider@@@Z; CDirectInkImpl::SetCommitProvider(ICommitProvider *)
0x18008d4b0  lea     rcx, [rbp+arg_0]
0x18008d4b4  mov     ebx, eax
0x18008d4b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008d4bb  test    ebx, ebx
0x18008d4bd  js      short loc_18008D4ED
0x18008d4bf  mov     ecx, cs:dword_18015B128
0x18008d4c5  cmp     ecx, 4
0x18008d4c8  jbe     short loc_18008D546
0x18008d4ca  mov     edx, 1
0x18008d4cf  lea     rcx, dword_18015B128
0x18008d4d6  call    _tlgKeywordOn
0x18008d4db  test    al, al
0x18008d4dd  jz      short loc_18008D546
0x18008d4df  lea     rdx, byte_180136269
0x18008d4e6  jmp     short loc_18008D514
0x18008d4e8  mov     ebx, 8001010Eh
0x18008d4ed  mov     eax, cs:dword_18015B128
0x18008d4f3  cmp     eax, 2
0x18008d4f6  jbe     short loc_18008D546
0x18008d4f8  mov     edx, 1
0x18008d4fd  lea     rcx, dword_18015B128
0x18008d504  call    _tlgKeywordOn
0x18008d509  test    al, al
0x18008d50b  jz      short loc_18008D546
0x18008d50d  lea     rdx, byte_180136467
0x18008d514  lea     rax, aDirectinkcores_13; "DirectInkCoreServer::SetCommitProvider["...
0x18008d51b  mov     [rbp+arg_18], rax
0x18008d51f  lea     rax, [rbp+arg_10]
0x18008d523  mov     [rsp+40h+var_10], rax
0x18008d528  lea     rax, [rbp+arg_0]
0x18008d52c  mov     [rsp+40h+var_18], rax
0x18008d531  lea     rax, [rbp+arg_18]
0x18008d535  mov     [rsp+40h+var_20], rax
0x18008d53a  mov     [rbp+arg_10], rsi
0x18008d53e  mov     dword ptr [rbp+arg_0], ebx
0x18008d541  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18008d546  mov     eax, ebx
0x18008d548  mov     rbx, [rsp+40h+arg_8]
0x18008d54d  add     rsp, 40h
0x18008d551  pop     rdi
0x18008d552  pop     rsi
0x18008d553  pop     rbp
0x18008d554  retn
```
