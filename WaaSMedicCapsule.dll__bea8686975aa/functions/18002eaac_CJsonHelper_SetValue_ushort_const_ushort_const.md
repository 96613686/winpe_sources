# CJsonHelper::_SetValue(ushort const *,ushort const *)

- ea: `0x18002eaac`
- end: `0x18002ec03`
- name: `?_SetValue@CJsonHelper@@AEAAJPEBG0@Z`
- size: `343`
- prototype: `__int64 __fastcall(CJsonHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e4c4`
- `0x18002e66c`
- `0x18002e814`
- `0x18002ea2c`

## callees

- `0x180003bb0`
- `0x180023798`
- `0x180024980`
- `0x18002eaac`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002eb35`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002eb35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002eafa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002eafa`

## string_xrefs

- `0x18002eaf3`: `Windows.Data.Json.JsonValue`

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
    JUMPOUT(0x18002EC02LL);
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
0x18002eaac  mov     [rsp-18h+arg_18], rbx
0x18002eab1  push    rbp
0x18002eab2  push    rsi
0x18002eab3  push    rdi
0x18002eab4  mov     rbp, rsp
0x18002eab7  sub     rsp, 60h
0x18002eabb  mov     rax, cs:__security_cookie
0x18002eac2  xor     rax, rsp
0x18002eac5  mov     [rbp+var_8], rax
0x18002eac9  mov     rsi, rcx
0x18002eacc  mov     [rbp+var_30], rdx
0x18002ead0  mov     [rbp+var_38], r8
0x18002ead4  lea     rdi, [rcx+20h]
0x18002ead8  cmp     qword ptr [rdi], 0
0x18002eadc  jnz     short loc_18002EB45
0x18002eade  mov     [rbp+string], 0
0x18002eae6  lea     r9, [rbp+string]; string
0x18002eaea  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002eaee  mov     edx, 1Bh; length
0x18002eaf3  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18002eafa  call    cs:__imp_WindowsCreateStringReference
0x18002eb00  test    eax, eax
0x18002eb02  js      loc_18002EBFB
0x18002eb08  mov     rbx, [rbp+string]
0x18002eb0c  mov     rcx, [rdi]
0x18002eb0f  test    rcx, rcx
0x18002eb12  jz      short loc_18002EB28
0x18002eb14  mov     qword ptr [rdi], 0
0x18002eb1b  mov     rax, [rcx]
0x18002eb1e  mov     rax, [rax+10h]
0x18002eb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb27  nop
0x18002eb28  mov     r8, rdi
0x18002eb2b  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18002eb32  mov     rcx, rbx
0x18002eb35  call    cs:__imp_RoGetActivationFactory
0x18002eb3b  mov     ebx, eax
0x18002eb3d  test    eax, eax
0x18002eb3f  js      loc_18002EBDD
0x18002eb45  cmp     qword ptr [rsi], 0
0x18002eb49  jz      loc_18002EBD8
0x18002eb4f  mov     [rbp+var_40], 0
0x18002eb57  mov     rdi, [rdi]
0x18002eb5a  mov     rax, [rdi]
0x18002eb5d  mov     rbx, [rax+50h]
0x18002eb61  lea     rdx, [rbp+var_38]
0x18002eb65  lea     rcx, [rbp+hstringHeader]
0x18002eb69  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002eb6e  nop
0x18002eb6f  lea     r8, [rbp+var_40]
0x18002eb73  mov     rdx, [rax+18h]
0x18002eb77  mov     rcx, rdi
0x18002eb7a  mov     rax, rbx
0x18002eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb82  mov     ebx, eax
0x18002eb84  test    eax, eax
0x18002eb86  js      short loc_18002EBB8
0x18002eb88  mov     rsi, [rsi]
0x18002eb8b  mov     rax, [rsi]
0x18002eb8e  mov     rdi, [rax+38h]
0x18002eb92  mov     rbx, [rbp+var_40]
0x18002eb96  lea     rdx, [rbp+var_30]
0x18002eb9a  lea     rcx, [rbp+hstringHeader]
0x18002eb9e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002eba3  nop
0x18002eba4  mov     r8, rbx
0x18002eba7  mov     rdx, [rax+18h]
0x18002ebab  mov     rcx, rsi
0x18002ebae  mov     rax, rdi
0x18002ebb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebb6  mov     ebx, eax
0x18002ebb8  mov     rcx, [rbp+var_40]
0x18002ebbc  test    rcx, rcx
0x18002ebbf  jz      short loc_18002EBD6
0x18002ebc1  mov     [rbp+var_40], 0
0x18002ebc9  mov     rax, [rcx]
0x18002ebcc  mov     rax, [rax+10h]
0x18002ebd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebd5  nop
0x18002ebd6  jmp     short loc_18002EBDD
0x18002ebd8  mov     ebx, 80004003h
0x18002ebdd  mov     eax, ebx
0x18002ebdf  mov     rcx, [rbp+var_8]
0x18002ebe3  xor     rcx, rsp; StackCookie
0x18002ebe6  call    __security_check_cookie
0x18002ebeb  mov     rbx, [rsp+60h+arg_18]
0x18002ebf3  add     rsp, 60h
0x18002ebf7  pop     rdi
0x18002ebf8  pop     rsi
0x18002ebf9  pop     rbp
0x18002ebfa  retn
0x18002ebfb  mov     ecx, eax; this
0x18002ebfd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
