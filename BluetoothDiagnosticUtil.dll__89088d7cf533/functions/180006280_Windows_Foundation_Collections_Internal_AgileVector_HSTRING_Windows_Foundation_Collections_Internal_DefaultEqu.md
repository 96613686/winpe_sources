# Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)

- ea: `0x180006280`
- end: `0x1800063d7`
- name: `?Make@?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@SAJPEAPEAV12345@@Z`
- size: `343`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003b08`
- `0x180004210`
- `0x1800087a0`
- `0x180008f80`

## callees

- `0x180004990`
- `0x180006280`
- `0x180006c6c`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800062f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800062f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800062ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800062ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(
        _QWORD *a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-40h] BYREF
  __int64 v13; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a1 = 0;
  v12 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x1800063D6LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v12);
  if ( ActivationFactory >= 0 )
  {
    v13 = 0;
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{216,{flat}}(v12, &v13);
    if ( ActivationFactory >= 0 )
    {
      v9 = v13;
      v13 = 0;
      *a1 = v9;
      v10 = v12;
      if ( v12 )
      {
        v12 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      return 0;
    }
    else
    {
      v7 = v13;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      v8 = v12;
      if ( v12 )
      {
        v12 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
  }
  else
  {
    v6 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180006280  mov     [rsp-8+arg_8], rbx
0x180006285  mov     [rsp-8+arg_10], rdi
0x18000628a  push    rbp
0x18000628b  mov     rbp, rsp
0x18000628e  sub     rsp, 60h
0x180006292  mov     rax, cs:__security_cookie
0x180006299  xor     rax, rsp
0x18000629c  mov     [rbp+var_10], rax
0x1800062a0  mov     rdi, rcx
0x1800062a3  mov     qword ptr [rcx], 0
0x1800062aa  mov     [rbp+var_40], 0
0x1800062b2  mov     [rbp+string], 0
0x1800062ba  lea     r9, [rbp+string]; string
0x1800062be  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800062c2  mov     edx, 2Ch ; ','; length
0x1800062c7  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800062ce  call    cs:__imp_WindowsCreateStringReference
0x1800062d5  nop     dword ptr [rax+rax+00h]
0x1800062da  test    eax, eax
0x1800062dc  js      loc_1800063CF
0x1800062e2  lea     r8, [rbp+var_40]
0x1800062e6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800062ed  mov     rcx, [rbp+string]
0x1800062f1  call    cs:__imp_RoGetActivationFactory
0x1800062f8  nop     dword ptr [rax+rax+00h]
0x1800062fd  mov     ebx, eax
0x1800062ff  test    eax, eax
0x180006301  jns     short loc_180006326
0x180006303  mov     rcx, [rbp+var_40]
0x180006307  test    rcx, rcx
0x18000630a  jz      short loc_180006321
0x18000630c  mov     [rbp+var_40], 0
0x180006314  mov     rax, [rcx]
0x180006317  mov     rax, [rax+10h]
0x18000631b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006320  nop
0x180006321  jmp     loc_1800063AE
0x180006326  mov     [rbp+var_38], 0
0x18000632e  lea     rdx, [rbp+var_38]
0x180006332  mov     rcx, [rbp+var_40]
0x180006336  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{216,{flat}}
0x18000633b  mov     ebx, eax
0x18000633d  test    eax, eax
0x18000633f  jns     short loc_18000637F
0x180006341  mov     rcx, [rbp+var_38]
0x180006345  test    rcx, rcx
0x180006348  jz      short loc_18000635F
0x18000634a  mov     [rbp+var_38], 0
0x180006352  mov     rax, [rcx]
0x180006355  mov     rax, [rax+10h]
0x180006359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635e  nop
0x18000635f  mov     rcx, [rbp+var_40]
0x180006363  test    rcx, rcx
0x180006366  jz      short loc_18000637D
0x180006368  mov     [rbp+var_40], 0
0x180006370  mov     rax, [rcx]
0x180006373  mov     rax, [rax+10h]
0x180006377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637c  nop
0x18000637d  jmp     short loc_1800063AE
0x18000637f  mov     rax, [rbp+var_38]
0x180006383  mov     [rbp+var_38], 0
0x18000638b  mov     [rdi], rax
0x18000638e  mov     rcx, [rbp+var_40]
0x180006392  test    rcx, rcx
0x180006395  jz      short loc_1800063AC
0x180006397  mov     [rbp+var_40], 0
0x18000639f  mov     rax, [rcx]
0x1800063a2  mov     rax, [rax+10h]
0x1800063a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ab  nop
0x1800063ac  xor     ebx, ebx
0x1800063ae  mov     eax, ebx
0x1800063b0  mov     rcx, [rbp+var_10]
0x1800063b4  xor     rcx, rsp; StackCookie
0x1800063b7  call    __security_check_cookie
0x1800063bc  lea     r11, [rsp+60h+var_s0]
0x1800063c1  mov     rbx, [r11+18h]
0x1800063c5  mov     rdi, [r11+20h]
0x1800063c9  mov     rsp, r11
0x1800063cc  pop     rbp
0x1800063cd  retn
0x1800063cf  mov     ecx, eax; this
0x1800063d1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
