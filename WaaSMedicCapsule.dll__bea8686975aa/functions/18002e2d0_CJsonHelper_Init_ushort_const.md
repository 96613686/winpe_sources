# CJsonHelper::Init(ushort const *)

- ea: `0x18002e2d0`
- end: `0x18002e4bd`
- name: `?Init@CJsonHelper@@QEAAJPEBG@Z`
- size: `493`
- prototype: `__int64 __fastcall(CJsonHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `24`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d170`
- `0x18001f140`
- `0x1800223b0`
- `0x18002e4c4`
- `0x18002e66c`
- `0x18002e814`
- `0x180038150`
- `0x18003b290`
- `0x18003c4e0`
- `0x18003efa0`
- `0x1800405a0`
- `0x1800412d0`
- `0x1800433f0`
- `0x180044320`
- `0x1800463c0`
- `0x18004b760`
- `0x18004dba0`
- `0x18004e930`
- `0x18004f290`
- `0x18004fc40`
- `0x180050ce0`
- `0x1800517a0`
- `0x180053870`
- `0x1800552d0`

## callees

- `0x180003bb0`
- `0x180023798`
- `0x180024980`
- `0x18002e2d0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e355`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e42b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e355`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002e42b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e3f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e31e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e3f4`

## string_xrefs

- `0x18002e317`: `Windows.Data.Json.JsonObject`
- `0x18002e3ed`: `Windows.Data.Json.JsonArray`

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
    JUMPOUT(0x18002E4BCLL);
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
0x18002e2d0  mov     [rsp-28h+arg_10], rbx
0x18002e2d5  push    rbp
0x18002e2d6  push    rsi
0x18002e2d7  push    rdi
0x18002e2d8  push    r14
0x18002e2da  push    r15
0x18002e2dc  mov     rbp, rsp
0x18002e2df  sub     rsp, 70h
0x18002e2e3  mov     rax, cs:__security_cookie
0x18002e2ea  xor     rax, rsp
0x18002e2ed  mov     [rbp+var_8], rax
0x18002e2f1  mov     rsi, rdx
0x18002e2f4  mov     rdi, rcx
0x18002e2f7  mov     [rbp+var_38], rdx
0x18002e2fb  xor     r15d, r15d
0x18002e2fe  lea     rbx, [rcx+10h]
0x18002e302  cmp     [rbx], r15
0x18002e305  jnz     short loc_18002E363
0x18002e307  mov     [rbp+string], r15
0x18002e30b  lea     r9, [rbp+string]; string
0x18002e30f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002e313  lea     edx, [r15+1Ch]; length
0x18002e317  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18002e31e  call    cs:__imp_WindowsCreateStringReference
0x18002e324  test    eax, eax
0x18002e326  js      loc_18002E4B5
0x18002e32c  mov     r14, [rbp+string]
0x18002e330  mov     rcx, [rbx]
0x18002e333  test    rcx, rcx
0x18002e336  jz      short loc_18002E348
0x18002e338  mov     [rbx], r15
0x18002e33b  mov     rax, [rcx]
0x18002e33e  mov     rax, [rax+10h]
0x18002e342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e347  nop
0x18002e348  mov     r8, rbx
0x18002e34b  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18002e352  mov     rcx, r14
0x18002e355  call    cs:__imp_RoGetActivationFactory
0x18002e35b  test    eax, eax
0x18002e35d  js      loc_18002E48D
0x18002e363  mov     [rbp+var_40], r15b
0x18002e367  mov     rbx, [rbx]
0x18002e36a  mov     rax, [rbx]
0x18002e36d  mov     r14, [rax+38h]
0x18002e371  mov     rcx, [rdi]
0x18002e374  test    rcx, rcx
0x18002e377  jz      short loc_18002E389
0x18002e379  mov     [rdi], r15
0x18002e37c  mov     rax, [rcx]
0x18002e37f  mov     rax, [rax+10h]
0x18002e383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e388  nop
0x18002e389  lea     rdx, [rbp+var_38]
0x18002e38d  lea     rcx, [rbp+hstringHeader]
0x18002e391  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002e396  nop
0x18002e397  lea     r9, [rbp+var_40]
0x18002e39b  mov     r8, rdi
0x18002e39e  mov     rdx, [rax+18h]
0x18002e3a2  mov     rcx, rbx
0x18002e3a5  mov     rax, r14
0x18002e3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3ad  nop
0x18002e3ae  test    eax, eax
0x18002e3b0  js      loc_18002E48D
0x18002e3b6  test    rsi, rsi
0x18002e3b9  jz      loc_18002E48D
0x18002e3bf  cmp     [rsi], r15w
0x18002e3c3  jz      loc_18002E48D
0x18002e3c9  cmp     [rbp+var_40], r15b
0x18002e3cd  jnz     loc_18002E48D
0x18002e3d3  lea     rbx, [rdi+18h]
0x18002e3d7  cmp     [rbx], r15
0x18002e3da  jnz     short loc_18002E435
0x18002e3dc  mov     [rbp+string], r15
0x18002e3e0  lea     r9, [rbp+string]; string
0x18002e3e4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002e3e8  mov     edx, 1Bh; length
0x18002e3ed  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18002e3f4  call    cs:__imp_WindowsCreateStringReference
0x18002e3fa  test    eax, eax
0x18002e3fc  js      loc_18002E4AD
0x18002e402  mov     rsi, [rbp+string]
0x18002e406  mov     rcx, [rbx]
0x18002e409  test    rcx, rcx
0x18002e40c  jz      short loc_18002E41E
0x18002e40e  mov     [rbx], r15
0x18002e411  mov     rax, [rcx]
0x18002e414  mov     rax, [rax+10h]
0x18002e418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e41d  nop
0x18002e41e  mov     r8, rbx
0x18002e421  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x18002e428  mov     rcx, rsi
0x18002e42b  call    cs:__imp_RoGetActivationFactory
0x18002e431  test    eax, eax
0x18002e433  js      short loc_18002E48D
0x18002e435  mov     rbx, [rbx]
0x18002e438  mov     rax, [rbx]
0x18002e43b  mov     rsi, [rax+38h]
0x18002e43f  mov     rcx, [rdi+8]
0x18002e443  test    rcx, rcx
0x18002e446  jz      short loc_18002E459
0x18002e448  mov     [rdi+8], r15
0x18002e44c  mov     rax, [rcx]
0x18002e44f  mov     rax, [rax+10h]
0x18002e453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e458  nop
0x18002e459  lea     rdx, [rbp+var_38]
0x18002e45d  lea     rcx, [rbp+hstringHeader]
0x18002e461  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002e466  nop
0x18002e467  lea     r9, [rbp+var_40]
0x18002e46b  lea     r8, [rdi+8]
0x18002e46f  mov     rdx, [rax+18h]
0x18002e473  mov     rcx, rbx
0x18002e476  mov     rax, rsi
0x18002e479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e47e  nop
0x18002e47f  test    eax, eax
0x18002e481  js      short loc_18002E48D
0x18002e483  mov     eax, r15d
0x18002e486  cmp     [rbp+var_40], r15b
0x18002e48a  setz    al
0x18002e48d  mov     rcx, [rbp+var_8]
0x18002e491  xor     rcx, rsp; StackCookie
0x18002e494  call    __security_check_cookie
0x18002e499  mov     rbx, [rsp+70h+arg_10]
0x18002e4a1  add     rsp, 70h
0x18002e4a5  pop     r15
0x18002e4a7  pop     r14
0x18002e4a9  pop     rdi
0x18002e4aa  pop     rsi
0x18002e4ab  pop     rbp
0x18002e4ac  retn
0x18002e4ad  mov     ecx, eax; this
0x18002e4af  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002e4b4  int     3; Trap to Debugger
0x18002e4b5  mov     ecx, eax; this
0x18002e4b7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
