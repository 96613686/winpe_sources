# StructuredQuery1::QueryParser::IsDefaultPropertyName(wchar_t const *,ICondition *)

- ea: `0x18002f298`
- end: `0x18002f3d7`
- name: `?IsDefaultPropertyName@QueryParser@StructuredQuery1@@AEBA_NPEB_WPEAUICondition@@@Z`
- size: `319`
- prototype: `bool(StructuredQuery1::QueryParser *__hidden this, const wchar_t *, struct ICondition *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d5f4`
- `0x18002eebc`

## callees

- `0x180010620`
- `0x180010904`
- `0x18002f298`
- `0x180045298`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f313`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f399`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f313`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f3ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f3b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f3ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f3b7`

## pseudocode

```c
bool __fastcall StructuredQuery1::QueryParser::IsDefaultPropertyName(
        StructuredQuery1::QueryParser *this,
        const wchar_t *a2,
        struct ICondition *a3)
{
  struct IConditionVtbl *lpVtbl; // rax
  bool v6; // di
  WCHAR *v7; // rcx
  const struct IEntity *v8; // rax
  StructuredQuery1::QueryExpressionCustomization *v9; // rcx
  wchar_t **v10; // r8
  WCHAR *v11; // rbx
  PCNZWCH lpString1; // [rsp+30h] [rbp-30h] BYREF
  PCNZWCH v14; // [rsp+38h] [rbp-28h] BYREF
  PROPERTYKEY propkey; // [rsp+40h] [rbp-20h] BYREF

  lpVtbl = a3->lpVtbl;
  lpString1 = 0;
  v6 = 0;
  if ( ((int (__fastcall *)(struct ICondition *, PCNZWCH *))lpVtbl->GetValueType)(a3, &lpString1) >= 0 )
  {
    v7 = (WCHAR *)lpString1;
    if ( lpString1 )
    {
      if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"System.StructuredQueryType.String", -1) == 2 )
      {
        v8 = (const struct IEntity *)SemanticsUM::FindElementByName<SemanticsUM::Entity>(
                                       lpString1,
                                       *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 40LL),
                                       *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 13) + 8LL) + 32LL));
        if ( v8 )
        {
          v9 = (StructuredQuery1::QueryExpressionCustomization *)*((_QWORD *)this + 14);
          memset(&propkey, 0, sizeof(propkey));
          StructuredQuery1::QueryExpressionCustomization::LookupDefaultProperty(v9, v8, &propkey);
          v14 = 0;
          if ( (int)StructuredQuery1::GetConditionPropertyNameFromKey(
                      &propkey,
                      (const struct _tagpropertykey *)&v14,
                      v10) >= 0 )
          {
            v11 = (WCHAR *)v14;
            if ( v14 )
              v6 = CompareStringW(0x7Fu, 1u, v14, -1, a2, -1) == 2;
            CoTaskMemFree(v11);
          }
        }
      }
      v7 = (WCHAR *)lpString1;
    }
    CoTaskMemFree(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18002f298  push    rbp
0x18002f29a  push    rbx
0x18002f29b  push    rsi
0x18002f29c  push    rdi
0x18002f29d  push    r15
0x18002f29f  mov     rbp, rsp
0x18002f2a2  sub     rsp, 60h
0x18002f2a6  mov     rax, cs:__security_cookie
0x18002f2ad  xor     rax, rsp
0x18002f2b0  mov     [rbp+var_8], rax
0x18002f2b4  mov     rax, [r8]
0x18002f2b7  mov     rsi, rdx
0x18002f2ba  mov     rbx, rcx
0x18002f2bd  mov     [rbp+lpString1], 0
0x18002f2c5  lea     rdx, [rbp+lpString1]
0x18002f2c9  mov     rcx, r8
0x18002f2cc  xor     dil, dil
0x18002f2cf  mov     rax, [rax+58h]
0x18002f2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2d8  test    eax, eax
0x18002f2da  js      loc_18002F3BD
0x18002f2e0  mov     rcx, [rbp+lpString1]
0x18002f2e4  test    rcx, rcx
0x18002f2e7  jz      loc_18002F3B7
0x18002f2ed  or      r9d, 0FFFFFFFFh; cchCount1
0x18002f2f1  mov     [rsp+60h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002f2f9  lea     rax, aSystemStructur_24; "System.StructuredQueryType.String"
0x18002f300  mov     r8, rcx; lpString1
0x18002f303  mov     [rsp+60h+lpString2], rax; lpString2
0x18002f308  lea     r15d, [r9+2]
0x18002f30c  mov     edx, r15d; dwCmpFlags
0x18002f30f  lea     ecx, [r15+7Eh]; Locale
0x18002f313  call    cs:__imp_CompareStringW
0x18002f319  cmp     eax, 2
0x18002f31c  jnz     loc_18002F3B3
0x18002f322  mov     rax, [rbx+68h]
0x18002f326  mov     rcx, [rbp+lpString1]; lpString1
0x18002f32a  mov     rdx, [rax+8]
0x18002f32e  mov     r8d, [rdx+20h]
0x18002f332  mov     rdx, [rdx+28h]
0x18002f336  call    ??$FindElementByName@VEntity@SemanticsUM@@@SemanticsUM@@YAPEBVEntity@0@PEB_WPEBV10@K@Z; SemanticsUM::FindElementByName<SemanticsUM::Entity>(wchar_t const *,SemanticsUM::Entity const *,ulong)
0x18002f33b  test    rax, rax
0x18002f33e  jz      short loc_18002F3B3
0x18002f340  xor     ecx, ecx
0x18002f342  lea     r8, [rbp+propkey]; struct _tagpropertykey *
0x18002f346  mov     [rbp+propkey.pid], ecx
0x18002f349  xorps   xmm0, xmm0
0x18002f34c  mov     rcx, [rbx+70h]; this
0x18002f350  mov     rdx, rax; struct IEntity *
0x18002f353  movups  xmmword ptr [rbp+propkey.fmtid.Data1], xmm0
0x18002f357  call    ?LookupDefaultProperty@QueryExpressionCustomization@StructuredQuery1@@QEBAXPEBVIEntity@SemanticsUM@@PEAU_tagpropertykey@@@Z; StructuredQuery1::QueryExpressionCustomization::LookupDefaultProperty(SemanticsUM::IEntity const *,_tagpropertykey *)
0x18002f35c  lea     rdx, [rbp+var_28]; struct _tagpropertykey *
0x18002f360  mov     [rbp+var_28], 0
0x18002f368  lea     rcx, [rbp+propkey]; propkey
0x18002f36c  call    ?GetConditionPropertyNameFromKey@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAPEA_W@Z; StructuredQuery1::GetConditionPropertyNameFromKey(_tagpropertykey const &,wchar_t * *)
0x18002f371  test    eax, eax
0x18002f373  js      short loc_18002F3B3
0x18002f375  mov     rbx, [rbp+var_28]
0x18002f379  test    rbx, rbx
0x18002f37c  jz      short loc_18002F3AA
0x18002f37e  mov     [rsp+60h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002f386  lea     ecx, [r15+7Eh]; Locale
0x18002f38a  or      r9d, 0FFFFFFFFh; cchCount1
0x18002f38e  mov     [rsp+60h+lpString2], rsi; lpString2
0x18002f393  mov     r8, rbx; lpString1
0x18002f396  mov     edx, r15d; dwCmpFlags
0x18002f399  call    cs:__imp_CompareStringW
0x18002f39f  cmp     eax, 2
0x18002f3a2  movzx   edi, dil
0x18002f3a6  cmovz   edi, r15d
0x18002f3aa  mov     rcx, rbx; pv
0x18002f3ad  call    cs:__imp_CoTaskMemFree
0x18002f3b3  mov     rcx, [rbp+lpString1]; pv
0x18002f3b7  call    cs:__imp_CoTaskMemFree
0x18002f3bd  mov     al, dil
0x18002f3c0  mov     rcx, [rbp+var_8]
0x18002f3c4  xor     rcx, rsp; StackCookie
0x18002f3c7  call    __security_check_cookie
0x18002f3cc  add     rsp, 60h
0x18002f3d0  pop     r15
0x18002f3d2  pop     rdi
0x18002f3d3  pop     rsi
0x18002f3d4  pop     rbx
0x18002f3d5  pop     rbp
0x18002f3d6  retn
```
