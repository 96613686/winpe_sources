# CSpellContextHandler::CreateCommand(ushort const *,int)

- ea: `0x180273cc4`
- end: `0x180273e61`
- name: `?CreateCommand@CSpellContextHandler@@AEAAJPEBGH@Z`
- size: `413`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this, PCWSTR sourceString, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180273e68`
- `0x180274678`
- `0x18027494c`

## callees

- `0x180048d5c`
- `0x180107aa0`
- `0x18013bad0`
- `0x18013beb8`
- `0x180273470`
- `0x1802734bc`
- `0x1802738bc`
- `0x180273cc4`
- `0x1802740e8`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180273d49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180273d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180273d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180273d5d`

## string_xrefs

- `0x180273cee`: `Windows.UI.Popups.UICommand`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::CreateCommand(
        CSpellContextHandler *this,
        PCWSTR sourceString,
        unsigned int a3)
{
  _QWORD *v6; // rax
  int PropertyValueUInt32; // ebx
  unsigned __int64 v8; // rcx
  CSpellContextHandler *v9; // rcx
  CSpellingCommandHandler *v10; // rax
  CSpellingCommandHandler *v11; // rax
  CSpellingCommandHandler *v12; // rdi
  UINT32 length[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF

  v15 = 0;
  v6 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, L"Windows.UI.Popups.UICommand");
  PropertyValueUInt32 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(
                          *v6,
                          &v15);
  if ( PropertyValueUInt32 >= 0 )
  {
    length[0] = 0;
    v8 = -1;
    do
      ++v8;
    while ( sourceString[v8] );
    if ( (int)ULongLongToUInt(v8, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(sourceString, length[0], &hstringHeader, &string);
    PropertyValueUInt32 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v15 + 56LL))(v15, string);
    if ( PropertyValueUInt32 >= 0 )
    {
      *(_QWORD *)length = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(length);
      PropertyValueUInt32 = CSpellContextHandler::CreatePropertyValueUInt32(v9, a3, (struct IInspectable **)length);
      if ( PropertyValueUInt32 >= 0 )
      {
        PropertyValueUInt32 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 88LL))(
                                v15,
                                *(_QWORD *)length);
        if ( PropertyValueUInt32 >= 0 )
        {
          v10 = (CSpellingCommandHandler *)operator new(0x20u);
          v11 = CSpellingCommandHandler::CSpellingCommandHandler(v10, this, a3);
          v12 = v11;
          if ( v11 )
          {
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v11 + 8LL))(v11);
            PropertyValueUInt32 = (*(__int64 (__fastcall **)(__int64, CSpellingCommandHandler *))(*(_QWORD *)v15 + 72LL))(
                                    v15,
                                    v12);
            if ( PropertyValueUInt32 >= 0 )
              PropertyValueUInt32 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 104LL))(
                                      *((_QWORD *)this + 18),
                                      v15);
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(length);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)PropertyValueUInt32;
}

```

## disassembly

```asm
0x180273cc4  mov     [rsp-28h+arg_18], rbx
0x180273cc9  push    rbp
0x180273cca  push    rsi
0x180273ccb  push    rdi
0x180273ccc  push    r14
0x180273cce  push    r15
0x180273cd0  mov     rbp, rsp
0x180273cd3  sub     rsp, 60h
0x180273cd7  mov     rax, cs:__security_cookie
0x180273cde  xor     rax, rsp
0x180273ce1  mov     [rbp+var_10], rax
0x180273ce5  mov     rsi, rdx
0x180273ce8  mov     r14, rcx
0x180273ceb  xor     r15d, r15d
0x180273cee  lea     rdx, ?RuntimeClass_Windows_UI_Popups_UICommand@@3QBGB; "Windows.UI.Popups.UICommand"
0x180273cf5  lea     rcx, [rbp+string]; string
0x180273cf9  mov     [rbp+var_38], r15
0x180273cfd  mov     edi, r8d
0x180273d00  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x180273d05  lea     rdx, [rbp+var_38]
0x180273d09  mov     rcx, [rax]
0x180273d0c  call    ??$ActivateInstance@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>)
0x180273d11  mov     ebx, eax
0x180273d13  test    eax, eax
0x180273d15  js      loc_180273E36
0x180273d1b  mov     [rbp+length], r15d
0x180273d1f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180273d23  inc     rcx; unsigned __int64
0x180273d26  cmp     [rsi+rcx*2], r15w
0x180273d2b  jnz     short loc_180273D23
0x180273d2d  lea     rdx, [rbp+length]; unsigned int *
0x180273d31  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180273d36  test    eax, eax
0x180273d38  jns     short loc_180273D4F
0x180273d3a  xor     r9d, r9d; lpArguments
0x180273d3d  xor     r8d, r8d; nNumberOfArguments
0x180273d40  mov     ecx, 0C000000Dh; dwExceptionCode
0x180273d45  lea     edx, [r9+1]; dwExceptionFlags
0x180273d49  call    cs:__imp_RaiseException
0x180273d4f  mov     edx, [rbp+length]; length
0x180273d52  lea     r9, [rbp+string]; string
0x180273d56  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180273d5a  mov     rcx, rsi; sourceString
0x180273d5d  call    cs:__imp_WindowsCreateStringReference
0x180273d63  mov     rcx, [rbp+var_38]
0x180273d67  mov     rdx, [rbp+string]
0x180273d6b  mov     rax, [rcx]
0x180273d6e  mov     rax, [rax+38h]
0x180273d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273d77  mov     ebx, eax
0x180273d79  test    eax, eax
0x180273d7b  js      loc_180273E36
0x180273d81  lea     rcx, [rbp+length]
0x180273d85  mov     qword ptr [rbp+length], r15
0x180273d89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273d8e  lea     r8, [rbp+length]; struct IInspectable **
0x180273d92  mov     edx, edi; unsigned int
0x180273d94  call    ?CreatePropertyValueUInt32@CSpellContextHandler@@AEAAJIPEAPEAUIInspectable@@@Z; CSpellContextHandler::CreatePropertyValueUInt32(uint,IInspectable * *)
0x180273d99  mov     ebx, eax
0x180273d9b  test    eax, eax
0x180273d9d  js      loc_180273E2D
0x180273da3  mov     rcx, [rbp+var_38]
0x180273da7  mov     rdx, qword ptr [rbp+length]
0x180273dab  mov     rax, [rcx]
0x180273dae  mov     rax, [rax+58h]
0x180273db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273db7  mov     ebx, eax
0x180273db9  test    eax, eax
0x180273dbb  js      short loc_180273E2D
0x180273dbd  mov     ecx, 20h ; ' '; Size
0x180273dc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180273dc7  mov     r8d, edi; int
0x180273dca  mov     rdx, r14; struct CSpellContextHandler *
0x180273dcd  mov     rcx, rax; this
0x180273dd0  call    ??0CSpellingCommandHandler@@QEAA@PEAVCSpellContextHandler@@H@Z; CSpellingCommandHandler::CSpellingCommandHandler(CSpellContextHandler *,int)
0x180273dd5  mov     rdi, rax
0x180273dd8  test    rax, rax
0x180273ddb  jz      short loc_180273E2D
0x180273ddd  mov     rcx, [rax]
0x180273de0  mov     rax, [rcx+8]
0x180273de4  mov     rcx, rdi
0x180273de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273dec  mov     rcx, [rbp+var_38]
0x180273df0  mov     rdx, [rcx]
0x180273df3  mov     rax, [rdx+48h]
0x180273df7  mov     rdx, rdi
0x180273dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273dff  mov     ebx, eax
0x180273e01  test    eax, eax
0x180273e03  js      short loc_180273E1E
0x180273e05  mov     rcx, [r14+90h]
0x180273e0c  mov     rdx, [rbp+var_38]
0x180273e10  mov     rax, [rcx]
0x180273e13  mov     rax, [rax+68h]
0x180273e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273e1c  mov     ebx, eax
0x180273e1e  mov     rax, [rdi]
0x180273e21  mov     rcx, rdi
0x180273e24  mov     rax, [rax+10h]
0x180273e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273e2d  lea     rcx, [rbp+length]
0x180273e31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273e36  lea     rcx, [rbp+var_38]
0x180273e3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273e3f  mov     eax, ebx
0x180273e41  mov     rcx, [rbp+var_10]
0x180273e45  xor     rcx, rsp; StackCookie
0x180273e48  call    __security_check_cookie
0x180273e4d  mov     rbx, [rsp+60h+arg_18]
0x180273e55  add     rsp, 60h
0x180273e59  pop     r15
0x180273e5b  pop     r14
0x180273e5d  pop     rdi
0x180273e5e  pop     rsi
0x180273e5f  pop     rbp
0x180273e60  retn
```
