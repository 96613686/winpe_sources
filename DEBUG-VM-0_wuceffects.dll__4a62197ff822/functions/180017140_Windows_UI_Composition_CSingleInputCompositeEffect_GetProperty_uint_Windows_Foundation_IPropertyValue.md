# Windows::UI::Composition::CSingleInputCompositeEffect::GetProperty(uint,Windows::Foundation::IPropertyValue * *)

- ea: `0x180017140`
- end: `0x180017288`
- name: `?GetProperty@CSingleInputCompositeEffect@Composition@UI@Windows@@UEAAJIPEAPEAUIPropertyValue@Foundation@4@@Z`
- size: `328`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CSingleInputCompositeEffect *__hidden this, unsigned int, struct Windows::Foundation::IPropertyValue **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b900`
- `0x180017140`
- `0x18001f204`
- `0x180021060`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001727a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001727a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017189`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017189`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800171b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800171b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Composition::CSingleInputCompositeEffect::GetProperty(
        Windows::UI::Composition::CSingleInputCompositeEffect *this,
        __int64 a2,
        struct Windows::Foundation::IPropertyValue **a3)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, struct Windows::Foundation::IPropertyValue **); // rbx
  struct Windows::Foundation::IPropertyValue *v10; // rax
  struct Windows::Foundation::IPropertyValue *v11; // rcx
  __int64 v12; // rcx
  unsigned int v14; // edx
  struct Windows::Foundation::IPropertyValue *v15; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF

  v16 = 0;
  v15 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(&v16);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v16);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v14 = 115;
  }
  else
  {
    v8 = v16;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)v16 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(&v15);
    ActivationFactory = v9(v8, 10, &v15);
    v7 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v10 = v15;
      v15 = 0;
      *a3 = v10;
      v7 = 0;
      goto LABEL_5;
    }
    v14 = 116;
  }
  DoStackCaptureDirect(ActivationFactory, v14);
LABEL_5:
  string = 0;
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::IPropertyValue *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return v7;
}

```

## disassembly

```asm
0x180017140  push    rbp
0x180017142  push    rbx
0x180017143  push    rsi
0x180017144  push    rdi
0x180017145  mov     rbp, rsp
0x180017148  sub     rsp, 68h
0x18001714c  mov     rax, cs:__security_cookie
0x180017153  xor     rax, rsp
0x180017156  mov     [rbp+var_18], rax
0x18001715a  mov     rsi, r8
0x18001715d  mov     [rbp+var_40], 0
0x180017165  mov     [rbp+var_48], 0
0x18001716d  mov     [rbp+string], 0
0x180017175  lea     r9, [rbp+string]; string
0x180017179  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001717d  mov     edx, 20h ; ' '; length
0x180017182  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180017189  call    cs:__imp_WindowsCreateStringReference
0x18001718f  test    eax, eax
0x180017191  js      loc_18001726E
0x180017197  mov     rbx, [rbp+string]
0x18001719b  lea     rcx, [rbp+var_40]
0x18001719f  call    ?InternalRelease@?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(void)
0x1800171a4  lea     r8, [rbp+var_40]
0x1800171a8  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800171af  mov     rcx, rbx
0x1800171b2  call    cs:__imp_RoGetActivationFactory
0x1800171b8  mov     ebx, eax
0x1800171ba  test    eax, eax
0x1800171bc  js      loc_180017260
0x1800171c2  mov     rdi, [rbp+var_40]
0x1800171c6  mov     rax, [rdi]
0x1800171c9  mov     rbx, [rax+58h]
0x1800171cd  lea     rcx, [rbp+var_48]
0x1800171d1  call    ?InternalRelease@?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(void)
0x1800171d6  lea     r8, [rbp+var_48]
0x1800171da  mov     edx, 0Ah
0x1800171df  mov     rcx, rdi
0x1800171e2  mov     rax, rbx
0x1800171e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ea  mov     ebx, eax
0x1800171ec  test    eax, eax
0x1800171ee  js      loc_180017281
0x1800171f4  mov     rax, [rbp+var_48]
0x1800171f8  mov     [rbp+var_48], 0
0x180017200  mov     [rsi], rax
0x180017203  xor     ebx, ebx
0x180017205  mov     [rbp+string], 0
0x18001720d  mov     rcx, [rbp+var_48]
0x180017211  test    rcx, rcx
0x180017214  jz      short loc_18001722B
0x180017216  mov     [rbp+var_48], 0
0x18001721e  mov     rax, [rcx]
0x180017221  mov     rax, [rax+10h]
0x180017225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001722a  nop
0x18001722b  mov     rcx, [rbp+var_40]
0x18001722f  test    rcx, rcx
0x180017232  jz      short loc_180017249
0x180017234  mov     [rbp+var_40], 0
0x18001723c  mov     rax, [rcx]
0x18001723f  mov     rax, [rax+10h]
0x180017243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017248  nop
0x180017249  mov     eax, ebx
0x18001724b  mov     rcx, [rbp+var_18]
0x18001724f  xor     rcx, rsp; StackCookie
0x180017252  call    __security_check_cookie
0x180017257  add     rsp, 68h
0x18001725b  pop     rdi
0x18001725c  pop     rsi
0x18001725d  pop     rbx
0x18001725e  pop     rbp
0x18001725f  retn
0x180017260  mov     edx, 73h ; 's'; unsigned int
0x180017265  mov     ecx, eax; int
0x180017267  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18001726c  jmp     short loc_180017205
0x18001726e  xor     r9d, r9d; lpArguments
0x180017271  xor     r8d, r8d; nNumberOfArguments
0x180017274  lea     edx, [r9+1]; dwExceptionFlags
0x180017278  mov     ecx, eax; dwExceptionCode
0x18001727a  call    cs:__imp_RaiseException
0x180017280  int     3; Trap to Debugger
0x180017281  mov     edx, 74h ; 't'
0x180017286  jmp     short loc_180017265
```
