# Windows::UI::Input::Inking::InkPresenterStencilBase::_CreateAndInitializeGestureRecognizer(void)

- ea: `0x1800c0830`
- end: `0x1800c0a2d`
- name: `?_CreateAndInitializeGestureRecognizer@InkPresenterStencilBase@Inking@Input@UI@Windows@@MEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::InkPresenterStencilBase *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001b9c`
- `0x180002c28`
- `0x180002f6c`
- `0x1800062a0`
- `0x1800101bc`
- `0x1800be894`
- `0x1800c0830`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c08d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c08d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c08bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c08bc`

## string_xrefs

- `0x1800c0878`: `InkPresenterStencilBase::_CreateAndInitializeGestureRecognizer[Enter]`
- `0x1800c09e4`: `InkPresenterStencilBase::_CreateAndInitializeGestureRecognizer[Exit]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::InkPresenterStencilBase::_CreateAndInitializeGestureRecognizer(
        Windows::UI::Input::Inking::InkPresenterStencilBase *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // rdi
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const wchar_t **); // rbx
  char *v10; // rdx
  const wchar_t *v12; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v13; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF

  if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4098, a3) )
  {
    v12 = L"InkPresenterStencilBase::_CreateAndInitializeGestureRecognizer[Enter]";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18015B128,
      (unsigned int)byte_18014018B,
      0,
      0,
      (__int64)&v12);
  }
  v4 = (_QWORD *)((char *)this + 352);
  if ( WindowsCreateStringReference(L"Windows.UI.Input.GestureRecognizer", 0x22u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Input::IGestureRecognizer>>(
         string,
         (char *)this + 352);
  if ( v5 < 0 )
    goto LABEL_23;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 56LL))(*v4, *((unsigned int *)this + 41));
  if ( v5 < 0 )
    goto LABEL_23;
  LOBYTE(v7) = 1;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v4 + 232LL))(*v4, v7);
  if ( v5 < 0 )
    goto LABEL_23;
  v12 = 0;
  v8 = *v4;
  v9 = *(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v8 + 304LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  v5 = v9(v8, &v12);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)v12 + 88LL))(v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(Windows::UI::Input::Inking::InkPresenterStencilBase *))(*(_QWORD *)this + 288LL))(this),
        v5 < 0) )
  {
LABEL_23:
    if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4098, v6) )
    {
      v10 = &byte_18014025F;
      goto LABEL_19;
    }
  }
  else if ( (unsigned int)dword_18015B128 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 4098, v6) )
  {
    v10 = byte_1801402D3;
LABEL_19:
    v13 = L"InkPresenterStencilBase::_CreateAndInitializeGestureRecognizer[Exit]";
    LODWORD(v12) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18015B128,
      (_DWORD)v10,
      0,
      0,
      (__int64)&v13,
      (__int64)&v12);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c0830  push    rbp
0x1800c0832  push    rbx
0x1800c0833  push    rsi
0x1800c0834  push    rdi
0x1800c0835  push    r14
0x1800c0837  push    r15
0x1800c0839  mov     rbp, rsp
0x1800c083c  sub     rsp, 78h
0x1800c0840  mov     rax, cs:__security_cookie
0x1800c0847  xor     rax, rsp
0x1800c084a  mov     [rbp+var_18], rax
0x1800c084e  mov     rsi, rcx
0x1800c0851  mov     eax, cs:dword_18015B128
0x1800c0857  mov     r15d, 1002h
0x1800c085d  lea     r14, dword_18015B128
0x1800c0864  cmp     eax, 4
0x1800c0867  jbe     short loc_1800C08A1
0x1800c0869  mov     edx, r15d
0x1800c086c  mov     rcx, r14
0x1800c086f  call    _tlgKeywordOn
0x1800c0874  test    al, al
0x1800c0876  jz      short loc_1800C08A1
0x1800c0878  lea     rax, aInkpresenterst_54; "InkPresenterStencilBase::_CreateAndInit"...
0x1800c087f  mov     [rbp+var_48], rax
0x1800c0883  lea     rax, [rbp+var_48]
0x1800c0887  mov     [rsp+78h+var_58], rax
0x1800c088c  xor     r9d, r9d
0x1800c088f  xor     r8d, r8d
0x1800c0892  lea     rdx, byte_18014018B
0x1800c0899  mov     rcx, r14
0x1800c089c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800c08a1  lea     rdi, [rsi+160h]
0x1800c08a8  lea     r9, [rbp+string]; string
0x1800c08ac  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800c08b0  mov     edx, 22h ; '"'; length
0x1800c08b5  lea     rcx, ?RuntimeClass_Windows_UI_Input_GestureRecognizer@@3QBGB; "Windows.UI.Input.GestureRecognizer"
0x1800c08bc  call    cs:__imp_WindowsCreateStringReference
0x1800c08c2  test    eax, eax
0x1800c08c4  jns     short loc_1800C08DB
0x1800c08c6  xor     r9d, r9d; lpArguments
0x1800c08c9  xor     r8d, r8d; nNumberOfArguments
0x1800c08cc  lea     edx, [r9+1]; dwExceptionFlags
0x1800c08d0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c08d5  call    cs:__imp_RaiseException
0x1800c08db  mov     rdx, rdi
0x1800c08de  mov     rcx, [rbp+string]
0x1800c08e2  call    ??$ActivateInstance@V?$ComPtr@UIGestureRecognizer@Input@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGestureRecognizer@Input@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Input::IGestureRecognizer>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Input::IGestureRecognizer>>)
0x1800c08e7  mov     ebx, eax
0x1800c08e9  test    eax, eax
0x1800c08eb  js      loc_1800C09C3
0x1800c08f1  mov     rcx, [rdi]
0x1800c08f4  mov     rax, [rcx]
0x1800c08f7  mov     edx, [rsi+0A4h]
0x1800c08fd  mov     rax, [rax+38h]
0x1800c0901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0906  mov     ebx, eax
0x1800c0908  test    eax, eax
0x1800c090a  js      loc_1800C09C3
0x1800c0910  mov     rcx, [rdi]
0x1800c0913  mov     rax, [rcx]
0x1800c0916  mov     dl, 1
0x1800c0918  mov     rax, [rax+0E8h]
0x1800c091f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0924  mov     ebx, eax
0x1800c0926  test    eax, eax
0x1800c0928  js      loc_1800C09C3
0x1800c092e  mov     [rbp+var_48], 0
0x1800c0936  mov     rdi, [rdi]
0x1800c0939  mov     rax, [rdi]
0x1800c093c  mov     rbx, [rax+130h]
0x1800c0943  lea     rcx, [rbp+var_48]
0x1800c0947  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c094c  lea     rdx, [rbp+var_48]
0x1800c0950  mov     rcx, rdi
0x1800c0953  mov     rax, rbx
0x1800c0956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c095b  mov     ebx, eax
0x1800c095d  test    eax, eax
0x1800c095f  js      short loc_1800C097B
0x1800c0961  mov     rcx, [rbp+var_48]
0x1800c0965  mov     rax, [rcx]
0x1800c0968  movss   xmm1, cs:__real@3f800000
0x1800c0970  mov     rax, [rax+58h]
0x1800c0974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0979  mov     ebx, eax
0x1800c097b  lea     rcx, [rbp+var_48]
0x1800c097f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0984  test    ebx, ebx
0x1800c0986  js      short loc_1800C09C3
0x1800c0988  mov     rax, [rsi]
0x1800c098b  mov     rcx, rsi
0x1800c098e  mov     rax, [rax+120h]
0x1800c0995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c099a  mov     ebx, eax
0x1800c099c  test    eax, eax
0x1800c099e  js      short loc_1800C09C3
0x1800c09a0  mov     eax, cs:dword_18015B128
0x1800c09a6  cmp     eax, 4
0x1800c09a9  jbe     short loc_1800C0A12
0x1800c09ab  mov     rdx, r15
0x1800c09ae  mov     rcx, r14
0x1800c09b1  call    _tlgKeywordOn
0x1800c09b6  test    al, al
0x1800c09b8  jz      short loc_1800C0A12
0x1800c09ba  lea     rdx, byte_1801402D3
0x1800c09c1  jmp     short loc_1800C09E4
0x1800c09c3  mov     eax, cs:dword_18015B128
0x1800c09c9  cmp     eax, 2
0x1800c09cc  jbe     short loc_1800C0A12
0x1800c09ce  mov     rdx, r15
0x1800c09d1  mov     rcx, r14
0x1800c09d4  call    _tlgKeywordOn
0x1800c09d9  test    al, al
0x1800c09db  jz      short loc_1800C0A12
0x1800c09dd  lea     rdx, byte_18014025F
0x1800c09e4  lea     rax, aInkpresenterst_40; "InkPresenterStencilBase::_CreateAndInit"...
0x1800c09eb  mov     [rbp+var_40], rax
0x1800c09ef  lea     rax, [rbp+var_48]
0x1800c09f3  mov     [rsp+78h+var_50], rax
0x1800c09f8  lea     rax, [rbp+var_40]
0x1800c09fc  mov     [rsp+78h+var_58], rax
0x1800c0a01  mov     dword ptr [rbp+var_48], ebx
0x1800c0a04  xor     r9d, r9d
0x1800c0a07  xor     r8d, r8d
0x1800c0a0a  mov     rcx, r14
0x1800c0a0d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800c0a12  mov     eax, ebx
0x1800c0a14  mov     rcx, [rbp+var_18]
0x1800c0a18  xor     rcx, rsp; StackCookie
0x1800c0a1b  call    __security_check_cookie
0x1800c0a20  add     rsp, 78h
0x1800c0a24  pop     r15
0x1800c0a26  pop     r14
0x1800c0a28  pop     rdi
0x1800c0a29  pop     rsi
0x1800c0a2a  pop     rbx
0x1800c0a2b  pop     rbp
0x1800c0a2c  retn
```
