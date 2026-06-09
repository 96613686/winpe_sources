# CJsonHelper::Init(ushort const *)

- ea: `0x1800336a0`
- end: `0x18003388d`
- name: `?Init@CJsonHelper@@QEAAJPEBG@Z`
- size: `493`
- prototype: `__int64 __fastcall(CJsonHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800217d4`
- `0x18002524c`

## callees

- `0x1800050a0`
- `0x180024360`
- `0x180024e48`
- `0x1800336a0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800336ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800337c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800336ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800337c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033725`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800337fb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033725`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800337fb`

## string_xrefs

- `0x1800336e7`: `Windows.Data.Json.JsonObject`
- `0x1800337bd`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CJsonHelper::Init(CJsonHelper *this, const unsigned __int16 *a2)
{
  __int64 *v4; // rbx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // r14
  __int64 v9; // rcx
  __int64 result; // rax
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, CJsonHelper *, _BYTE *); // r14
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 *v15; // rbx
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  HSTRING v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, char *, _BYTE *); // rsi
  __int64 v23; // rcx
  __int64 v24; // rax
  _BYTE v25[8]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF

  v26[0] = a2;
  v4 = (__int64 *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
    goto LABEL_6;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    JUMPOUT(0x18003388CLL);
  }
  v8 = string;
  v9 = *v4;
  if ( *v4 )
  {
    *v4 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  result = RoGetActivationFactory(v8, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, v4);
  if ( (int)result >= 0 )
  {
LABEL_6:
    v25[0] = 0;
    v11 = *v4;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, CJsonHelper *, _BYTE *))(*(_QWORD *)v11 + 56LL);
    v13 = *(_QWORD *)this;
    if ( *(_QWORD *)this )
    {
      *(_QWORD *)this = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v26);
    result = v12(v11, *(_QWORD *)(v14 + 24), this, v25);
    if ( (int)result >= 0 && a2 && *a2 && !v25[0] )
    {
      v15 = (__int64 *)((char *)this + 24);
      if ( *((_QWORD *)this + 3) )
        goto LABEL_17;
      string = 0;
      v16 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, &string);
      if ( v16 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
        __debugbreak();
      }
      v19 = string;
      v20 = *v15;
      if ( *v15 )
      {
        *v15 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      result = RoGetActivationFactory(v19, &GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba, (char *)this + 24);
      if ( (int)result >= 0 )
      {
LABEL_17:
        v21 = *v15;
        v22 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, _BYTE *))(*(_QWORD *)v21 + 56LL);
        v23 = *((_QWORD *)this + 1);
        if ( v23 )
        {
          *((_QWORD *)this + 1) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v26);
        result = v22(v21, *(_QWORD *)(v24 + 24), (char *)this + 8, v25);
        if ( (int)result >= 0 )
          return v25[0] == 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800336a0  mov     [rsp-28h+arg_10], rbx
0x1800336a5  push    rbp
0x1800336a6  push    rsi
0x1800336a7  push    rdi
0x1800336a8  push    r14
0x1800336aa  push    r15
0x1800336ac  mov     rbp, rsp
0x1800336af  sub     rsp, 70h
0x1800336b3  mov     rax, cs:__security_cookie
0x1800336ba  xor     rax, rsp
0x1800336bd  mov     [rbp+var_8], rax
0x1800336c1  mov     rsi, rdx
0x1800336c4  mov     rdi, rcx
0x1800336c7  mov     [rbp+var_38], rdx
0x1800336cb  xor     r15d, r15d
0x1800336ce  lea     rbx, [rcx+10h]
0x1800336d2  cmp     [rbx], r15
0x1800336d5  jnz     short loc_180033733
0x1800336d7  mov     [rbp+string], r15
0x1800336db  lea     r9, [rbp+string]; string
0x1800336df  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800336e3  lea     edx, [r15+1Ch]; length
0x1800336e7  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800336ee  call    cs:__imp_WindowsCreateStringReference
0x1800336f4  test    eax, eax
0x1800336f6  js      loc_180033885
0x1800336fc  mov     r14, [rbp+string]
0x180033700  mov     rcx, [rbx]
0x180033703  test    rcx, rcx
0x180033706  jz      short loc_180033718
0x180033708  mov     [rbx], r15
0x18003370b  mov     rax, [rcx]
0x18003370e  mov     rax, [rax+10h]
0x180033712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033717  nop
0x180033718  mov     r8, rbx
0x18003371b  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180033722  mov     rcx, r14
0x180033725  call    cs:__imp_RoGetActivationFactory
0x18003372b  test    eax, eax
0x18003372d  js      loc_18003385D
0x180033733  mov     [rbp+var_40], r15b
0x180033737  mov     rbx, [rbx]
0x18003373a  mov     rax, [rbx]
0x18003373d  mov     r14, [rax+38h]
0x180033741  mov     rcx, [rdi]
0x180033744  test    rcx, rcx
0x180033747  jz      short loc_180033759
0x180033749  mov     [rdi], r15
0x18003374c  mov     rax, [rcx]
0x18003374f  mov     rax, [rax+10h]
0x180033753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033758  nop
0x180033759  lea     rdx, [rbp+var_38]
0x18003375d  lea     rcx, [rbp+hstringHeader]
0x180033761  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180033766  nop
0x180033767  lea     r9, [rbp+var_40]
0x18003376b  mov     r8, rdi
0x18003376e  mov     rdx, [rax+18h]
0x180033772  mov     rcx, rbx
0x180033775  mov     rax, r14
0x180033778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003377d  nop
0x18003377e  test    eax, eax
0x180033780  js      loc_18003385D
0x180033786  test    rsi, rsi
0x180033789  jz      loc_18003385D
0x18003378f  cmp     [rsi], r15w
0x180033793  jz      loc_18003385D
0x180033799  cmp     [rbp+var_40], r15b
0x18003379d  jnz     loc_18003385D
0x1800337a3  lea     rbx, [rdi+18h]
0x1800337a7  cmp     [rbx], r15
0x1800337aa  jnz     short loc_180033805
0x1800337ac  mov     [rbp+string], r15
0x1800337b0  lea     r9, [rbp+string]; string
0x1800337b4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800337b8  mov     edx, 1Bh; length
0x1800337bd  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800337c4  call    cs:__imp_WindowsCreateStringReference
0x1800337ca  test    eax, eax
0x1800337cc  js      loc_18003387D
0x1800337d2  mov     rsi, [rbp+string]
0x1800337d6  mov     rcx, [rbx]
0x1800337d9  test    rcx, rcx
0x1800337dc  jz      short loc_1800337EE
0x1800337de  mov     [rbx], r15
0x1800337e1  mov     rax, [rcx]
0x1800337e4  mov     rax, [rax+10h]
0x1800337e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337ed  nop
0x1800337ee  mov     r8, rbx
0x1800337f1  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x1800337f8  mov     rcx, rsi
0x1800337fb  call    cs:__imp_RoGetActivationFactory
0x180033801  test    eax, eax
0x180033803  js      short loc_18003385D
0x180033805  mov     rbx, [rbx]
0x180033808  mov     rax, [rbx]
0x18003380b  mov     rsi, [rax+38h]
0x18003380f  mov     rcx, [rdi+8]
0x180033813  test    rcx, rcx
0x180033816  jz      short loc_180033829
0x180033818  mov     [rdi+8], r15
0x18003381c  mov     rax, [rcx]
0x18003381f  mov     rax, [rax+10h]
0x180033823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033828  nop
0x180033829  lea     rdx, [rbp+var_38]
0x18003382d  lea     rcx, [rbp+hstringHeader]
0x180033831  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180033836  nop
0x180033837  lea     r9, [rbp+var_40]
0x18003383b  lea     r8, [rdi+8]
0x18003383f  mov     rdx, [rax+18h]
0x180033843  mov     rcx, rbx
0x180033846  mov     rax, rsi
0x180033849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003384e  nop
0x18003384f  test    eax, eax
0x180033851  js      short loc_18003385D
0x180033853  mov     eax, r15d
0x180033856  cmp     [rbp+var_40], r15b
0x18003385a  setz    al
0x18003385d  mov     rcx, [rbp+var_8]
0x180033861  xor     rcx, rsp; StackCookie
0x180033864  call    __security_check_cookie
0x180033869  mov     rbx, [rsp+70h+arg_10]
0x180033871  add     rsp, 70h
0x180033875  pop     r15
0x180033877  pop     r14
0x180033879  pop     rdi
0x18003387a  pop     rsi
0x18003387b  pop     rbp
0x18003387c  retn
0x18003387d  mov     ecx, eax; this
0x18003387f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180033884  int     3; Trap to Debugger
0x180033885  mov     ecx, eax; this
0x180033887  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
