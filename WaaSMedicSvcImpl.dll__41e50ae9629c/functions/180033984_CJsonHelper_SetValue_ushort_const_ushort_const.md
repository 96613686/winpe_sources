# CJsonHelper::_SetValue(ushort const *,ushort const *)

- ea: `0x180033984`
- end: `0x180033adb`
- name: `?_SetValue@CJsonHelper@@AEAAJPEBG0@Z`
- size: `343`
- prototype: `__int64 __fastcall(CJsonHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800338fc`

## callees

- `0x1800050a0`
- `0x180024360`
- `0x180024e48`
- `0x180033984`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800339d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800339d2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033a0d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033a0d`

## string_xrefs

- `0x1800339cb`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CJsonHelper::_SetValue(CJsonHelper *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 *v4; // rdi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rbx
  __int64 v9; // rcx
  int ActivationFactory; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64); // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v20; // [rsp+20h] [rbp-40h] BYREF
  const unsigned __int16 *v21; // [rsp+28h] [rbp-38h] BYREF
  const unsigned __int16 *v22; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  v22 = a2;
  v21 = a3;
  v4 = (__int64 *)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    goto LABEL_18;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    JUMPOUT(0x180033ADALL);
  }
  v8 = string;
  v9 = *v4;
  if ( *v4 )
  {
    *v4 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  ActivationFactory = RoGetActivationFactory(v8, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, v4);
  if ( ActivationFactory >= 0 )
  {
LABEL_18:
    if ( *(_QWORD *)this )
    {
      v20 = 0;
      v11 = *v4;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 80LL);
      v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v21);
      ActivationFactory = v12(v11, *(_QWORD *)(v13 + 24), &v20);
      if ( ActivationFactory >= 0 )
      {
        v14 = *(_QWORD *)this;
        v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 56LL);
        v16 = v20;
        v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v22);
        ActivationFactory = v15(v14, *(_QWORD *)(v17 + 24), v16);
      }
      v18 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180033984  mov     [rsp-18h+arg_18], rbx
0x180033989  push    rbp
0x18003398a  push    rsi
0x18003398b  push    rdi
0x18003398c  mov     rbp, rsp
0x18003398f  sub     rsp, 60h
0x180033993  mov     rax, cs:__security_cookie
0x18003399a  xor     rax, rsp
0x18003399d  mov     [rbp+var_8], rax
0x1800339a1  mov     rsi, rcx
0x1800339a4  mov     [rbp+var_30], rdx
0x1800339a8  mov     [rbp+var_38], r8
0x1800339ac  lea     rdi, [rcx+20h]
0x1800339b0  cmp     qword ptr [rdi], 0
0x1800339b4  jnz     short loc_180033A1D
0x1800339b6  mov     [rbp+string], 0
0x1800339be  lea     r9, [rbp+string]; string
0x1800339c2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800339c6  mov     edx, 1Bh; length
0x1800339cb  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1800339d2  call    cs:__imp_WindowsCreateStringReference
0x1800339d8  test    eax, eax
0x1800339da  js      loc_180033AD3
0x1800339e0  mov     rbx, [rbp+string]
0x1800339e4  mov     rcx, [rdi]
0x1800339e7  test    rcx, rcx
0x1800339ea  jz      short loc_180033A00
0x1800339ec  mov     qword ptr [rdi], 0
0x1800339f3  mov     rax, [rcx]
0x1800339f6  mov     rax, [rax+10h]
0x1800339fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339ff  nop
0x180033a00  mov     r8, rdi
0x180033a03  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x180033a0a  mov     rcx, rbx
0x180033a0d  call    cs:__imp_RoGetActivationFactory
0x180033a13  mov     ebx, eax
0x180033a15  test    eax, eax
0x180033a17  js      loc_180033AB5
0x180033a1d  cmp     qword ptr [rsi], 0
0x180033a21  jz      loc_180033AB0
0x180033a27  mov     [rbp+var_40], 0
0x180033a2f  mov     rdi, [rdi]
0x180033a32  mov     rax, [rdi]
0x180033a35  mov     rbx, [rax+50h]
0x180033a39  lea     rdx, [rbp+var_38]
0x180033a3d  lea     rcx, [rbp+hstringHeader]
0x180033a41  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180033a46  nop
0x180033a47  lea     r8, [rbp+var_40]
0x180033a4b  mov     rdx, [rax+18h]
0x180033a4f  mov     rcx, rdi
0x180033a52  mov     rax, rbx
0x180033a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a5a  mov     ebx, eax
0x180033a5c  test    eax, eax
0x180033a5e  js      short loc_180033A90
0x180033a60  mov     rsi, [rsi]
0x180033a63  mov     rax, [rsi]
0x180033a66  mov     rdi, [rax+38h]
0x180033a6a  mov     rbx, [rbp+var_40]
0x180033a6e  lea     rdx, [rbp+var_30]
0x180033a72  lea     rcx, [rbp+hstringHeader]
0x180033a76  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180033a7b  nop
0x180033a7c  mov     r8, rbx
0x180033a7f  mov     rdx, [rax+18h]
0x180033a83  mov     rcx, rsi
0x180033a86  mov     rax, rdi
0x180033a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a8e  mov     ebx, eax
0x180033a90  mov     rcx, [rbp+var_40]
0x180033a94  test    rcx, rcx
0x180033a97  jz      short loc_180033AAE
0x180033a99  mov     [rbp+var_40], 0
0x180033aa1  mov     rax, [rcx]
0x180033aa4  mov     rax, [rax+10h]
0x180033aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033aad  nop
0x180033aae  jmp     short loc_180033AB5
0x180033ab0  mov     ebx, 80004003h
0x180033ab5  mov     eax, ebx
0x180033ab7  mov     rcx, [rbp+var_8]
0x180033abb  xor     rcx, rsp; StackCookie
0x180033abe  call    __security_check_cookie
0x180033ac3  mov     rbx, [rsp+60h+arg_18]
0x180033acb  add     rsp, 60h
0x180033acf  pop     rdi
0x180033ad0  pop     rsi
0x180033ad1  pop     rbp
0x180033ad2  retn
0x180033ad3  mov     ecx, eax; this
0x180033ad5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
