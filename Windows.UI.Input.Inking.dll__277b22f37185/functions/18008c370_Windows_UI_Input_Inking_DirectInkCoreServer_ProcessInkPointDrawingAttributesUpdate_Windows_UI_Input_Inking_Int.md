# Windows::UI::Input::Inking::DirectInkCoreServer::ProcessInkPointDrawingAttributesUpdate(Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *)

- ea: `0x18008c370`
- end: `0x18008c499`
- name: `?ProcessInkPointDrawingAttributesUpdate@DirectInkCoreServer@Inking@Input@UI@Windows@@UEAAJPEAUIInkPointDrawingAttributes@Internal@2345@@Z`
- size: `297`
- prototype: `int(Windows::UI::Input::Inking::DirectInkCoreServer *__hidden this, struct Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x1800101bc`
- `0x180019248`
- `0x18008b1e4`
- `0x18008c370`
- `0x18008ee18`
- `0x180092ff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008c38a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008c38a`

## string_xrefs

- `0x18008c448`: `DirectInkCoreServer::ProcessInkPointDrawingAttributesUpdate[Exit]`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::DirectInkCoreServer::ProcessInkPointDrawingAttributesUpdate(
        Windows::UI::Input::Inking::DirectInkCoreServer *this,
        struct Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *a2)
{
  int v2; // ebx
  int updated; // ebx
  __int64 v6; // r8
  __int16 *v7; // rdx
  int v9; // [rsp+60h] [rbp+30h] BYREF
  struct Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *v10; // [rsp+68h] [rbp+38h] BYREF
  struct Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *v11; // [rsp+70h] [rbp+40h] BYREF
  const wchar_t *v12; // [rsp+78h] [rbp+48h] BYREF

  v2 = *((_DWORD *)this + 688);
  if ( GetCurrentThreadId() == v2 )
    updated = CObjLifetime::CheckAlive((Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 72));
  else
    updated = -2147417842;
  v10 = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v10);
  v11 = 0;
  if ( updated < 0
    || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v10),
        v11 = a2,
        updated = CDirectInkImpl::ProcessInkPointDrawingAttributesUpdate(
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this + 112),
                    a2),
        updated < 0)
    || a2
    && (updated = Windows::UI::Input::Inking::DirectInkCoreServer::_UpdateDefaultDrawingAttributesByInkPointDrawingAttributes(
                    (Windows::UI::Input::Inking::DirectInkCoreServer *)((char *)this - 144),
                    a2),
        updated < 0) )
  {
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v6) )
    {
      v7 = &word_1801355E6;
      goto LABEL_14;
    }
  }
  else if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 1, v6) )
  {
    v7 = (__int16 *)&dword_180135684;
LABEL_14:
    v12 = L"DirectInkCoreServer::ProcessInkPointDrawingAttributesUpdate[Exit]";
    v9 = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18015B128,
      (_DWORD)v7,
      0,
      0,
      (__int64)&v12,
      (__int64)&v9);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18008c370  push    rbp
0x18008c372  push    rbx
0x18008c373  push    rsi
0x18008c374  push    rdi
0x18008c375  push    r14
0x18008c377  mov     rbp, rsp
0x18008c37a  sub     rsp, 30h
0x18008c37e  mov     ebx, [rcx+0AC0h]
0x18008c384  mov     rdi, rdx
0x18008c387  mov     rsi, rcx
0x18008c38a  call    cs:__imp_GetCurrentThreadId
0x18008c390  cmp     eax, ebx
0x18008c392  jnz     short loc_18008C3A1
0x18008c394  lea     rcx, [rsi+48h]; this
0x18008c398  call    ?CheckAlive@CObjLifetime@@QEAAJXZ; CObjLifetime::CheckAlive(void)
0x18008c39d  mov     ebx, eax
0x18008c39f  jmp     short loc_18008C3A6
0x18008c3a1  mov     ebx, 8001010Eh
0x18008c3a6  lea     rcx, [rbp+arg_8]
0x18008c3aa  mov     [rbp+arg_8], rdi
0x18008c3ae  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x18008c3b3  mov     [rbp+arg_10], 0
0x18008c3bb  test    ebx, ebx
0x18008c3bd  js      short loc_18008C421
0x18008c3bf  lea     rcx, [rbp+arg_8]
0x18008c3c3  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x18008c3c8  lea     rcx, [rsi+70h]; this
0x18008c3cc  mov     [rbp+arg_10], rdi
0x18008c3d0  mov     rdx, rdi; struct Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *
0x18008c3d3  call    ?ProcessInkPointDrawingAttributesUpdate@CDirectInkImpl@@QEAAJPEAUIInkPointDrawingAttributes@Internal@Inking@Input@UI@Windows@@@Z; CDirectInkImpl::ProcessInkPointDrawingAttributesUpdate(Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *)
0x18008c3d8  mov     ebx, eax
0x18008c3da  test    eax, eax
0x18008c3dc  js      short loc_18008C421
0x18008c3de  test    rdi, rdi
0x18008c3e1  jz      short loc_18008C3F8
0x18008c3e3  mov     rdx, rdi; struct Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *
0x18008c3e6  lea     rcx, [rsi-90h]; this
0x18008c3ed  call    ?_UpdateDefaultDrawingAttributesByInkPointDrawingAttributes@DirectInkCoreServer@Inking@Input@UI@Windows@@AEAAJPEAUIInkPointDrawingAttributes@Internal@2345@@Z; Windows::UI::Input::Inking::DirectInkCoreServer::_UpdateDefaultDrawingAttributesByInkPointDrawingAttributes(Windows::UI::Input::Inking::Internal::IInkPointDrawingAttributes *)
0x18008c3f2  mov     ebx, eax
0x18008c3f4  test    eax, eax
0x18008c3f6  js      short loc_18008C421
0x18008c3f8  mov     eax, cs:dword_18015B128
0x18008c3fe  cmp     eax, 4
0x18008c401  jbe     short loc_18008C47A
0x18008c403  mov     edx, 1
0x18008c408  lea     rcx, dword_18015B128
0x18008c40f  call    _tlgKeywordOn
0x18008c414  test    al, al
0x18008c416  jz      short loc_18008C47A
0x18008c418  lea     rdx, dword_180135684
0x18008c41f  jmp     short loc_18008C448
0x18008c421  mov     eax, cs:dword_18015B128
0x18008c427  cmp     eax, 2
0x18008c42a  jbe     short loc_18008C47A
0x18008c42c  mov     edx, 1
0x18008c431  lea     rcx, dword_18015B128
0x18008c438  call    _tlgKeywordOn
0x18008c43d  test    al, al
0x18008c43f  jz      short loc_18008C47A
0x18008c441  lea     rdx, word_1801355E6
0x18008c448  lea     rax, aDirectinkcores_10; "DirectInkCoreServer::ProcessInkPointDra"...
0x18008c44f  mov     [rbp+arg_18], rax
0x18008c453  lea     rax, [rbp+arg_0]
0x18008c457  mov     [rsp+30h+var_8], rax
0x18008c45c  lea     rax, [rbp+arg_18]
0x18008c460  mov     [rsp+30h+var_10], rax
0x18008c465  xor     r9d, r9d
0x18008c468  mov     [rbp+arg_0], ebx
0x18008c46b  xor     r8d, r8d
0x18008c46e  lea     rcx, dword_18015B128
0x18008c475  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18008c47a  lea     rcx, [rbp+arg_10]
0x18008c47e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008c483  lea     rcx, [rbp+arg_8]
0x18008c487  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008c48c  mov     eax, ebx
0x18008c48e  add     rsp, 30h
0x18008c492  pop     r14
0x18008c494  pop     rdi
0x18008c495  pop     rsi
0x18008c496  pop     rbx
0x18008c497  pop     rbp
0x18008c498  retn
```
