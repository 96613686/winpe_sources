# StructuredQuery1::LoadConditionFromXml(IXMLDOMNode *,_GUID const &,void * *)

- ea: `0x18005d050`
- end: `0x18005d28b`
- name: `?LoadConditionFromXml@StructuredQuery1@@YAJPEAUIXMLDOMNode@@AEBU_GUID@@PEAPEAX@Z`
- size: `571`
- prototype: `__int64 __fastcall(StructuredQuery1 *__hidden this, struct IXMLDOMNode *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800631b0`
- `0x180063660`
- `0x18006e7b0`
- `0x180070cd0`

## callees

- `0x18000c144`
- `0x180043e68`
- `0x18004a0dc`
- `0x18005d050`
- `0x18005db64`
- `0x180074338`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d0de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d12d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d171`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d1a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d0de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d12d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d171`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005d1a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d25b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d25b`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::LoadConditionFromXml(
        StructuredQuery1 *this,
        struct IXMLDOMNode *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rax
  int v8; // ebx
  StructuredQuery1::CompoundCondition *v9; // rax
  enum tagCONDITION_TYPE v10; // edx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, void **); // rax
  struct IUnknown *v12; // rcx
  StructuredQuery1::LeafCondition *v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, void **); // rdi
  void *v16; // [rsp+70h] [rbp+30h] BYREF
  LPCWCH lpString1; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMNamedNodeMap *v18; // [rsp+88h] [rbp+48h] BYREF

  *(_QWORD *)&a3->Data1 = 0;
  v5 = *(_QWORD *)this;
  v18 = 0;
  v8 = (*(__int64 (__fastcall **)(StructuredQuery1 *, struct IXMLDOMNamedNodeMap **, const struct _GUID *, void **))(v5 + 136))(
         this,
         &v18,
         a3,
         a4);
  if ( v8 >= 0 )
  {
    lpString1 = 0;
    if ( XmlGetStringAttribute(L"type", v18, (wchar_t **)&lpString1) )
    {
      v8 = -2147024809;
      goto LABEL_24;
    }
    v16 = 0;
    if ( CompareStringOrdinal(lpString1, -1, L"andCondition", -1, 1) == 2 )
    {
      v8 = -2147024882;
      v9 = (StructuredQuery1::CompoundCondition *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 )
      {
        v10 = CT_AND_CONDITION;
LABEL_6:
        v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))StructuredQuery1::CompoundCondition::CompoundCondition(
                                                                   v9,
                                                                   v10);
        goto LABEL_15;
      }
    }
    else if ( CompareStringOrdinal(lpString1, -1, L"orCondition", -1, 1) == 2 )
    {
      v8 = -2147024882;
      v9 = (StructuredQuery1::CompoundCondition *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v9 )
      {
        v10 = CT_OR_CONDITION;
        goto LABEL_6;
      }
    }
    else if ( CompareStringOrdinal(lpString1, -1, L"notCondition", -1, 1) == 2 )
    {
      v8 = StructuredQuery1::NegationCondition::CreateInstance(v12, &GUID_169db284_8361_4be4_bdb0_0b73ad8764f1, &v16);
    }
    else
    {
      if ( CompareStringOrdinal(lpString1, -1, L"leafCondition", -1, 1) != 2 )
      {
        v8 = -2147024809;
LABEL_22:
        CoTaskMemFree((LPVOID)lpString1);
LABEL_24:
        ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v18->lpVtbl->Release)(v18);
        return (unsigned int)v8;
      }
      v8 = -2147024882;
      v13 = (StructuredQuery1::LeafCondition *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v13 )
      {
        v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))StructuredQuery1::LeafCondition::LeafCondition(v13);
LABEL_15:
        v14 = v11;
        if ( v11 )
        {
          v8 = (**v11)(v11, &GUID_169db284_8361_4be4_bdb0_0b73ad8764f1, &v16);
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, void **)))(*v14)[2])(v14);
        }
      }
    }
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(void *, StructuredQuery1 *))(*(_QWORD *)v16 + 32LL))(v16, this);
      if ( v8 >= 0 )
        v8 = (**(__int64 (__fastcall ***)(void *, struct IXMLDOMNode *, const struct _GUID *))v16)(v16, a2, a3);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_22;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005d050  mov     [rsp-28h+arg_8], rbx
0x18005d055  push    rbp
0x18005d056  push    rsi
0x18005d057  push    rdi
0x18005d058  push    r14
0x18005d05a  push    r15
0x18005d05c  mov     rbp, rsp
0x18005d05f  sub     rsp, 40h
0x18005d063  mov     qword ptr [r8], 0
0x18005d06a  mov     r15, rdx
0x18005d06d  mov     rax, [rcx]
0x18005d070  lea     rdx, [rbp+arg_18]
0x18005d074  mov     r14, r8
0x18005d077  mov     [rbp+arg_18], 0
0x18005d07f  mov     rsi, rcx
0x18005d082  mov     rax, [rax+88h]
0x18005d089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d08e  mov     ebx, eax
0x18005d090  test    eax, eax
0x18005d092  js      loc_18005D278
0x18005d098  mov     rdx, [rbp+arg_18]; struct IXMLDOMNamedNodeMap *
0x18005d09c  lea     r8, [rbp+lpString1]; wchar_t **
0x18005d0a0  lea     rcx, aType; "type"
0x18005d0a7  mov     [rbp+lpString1], 0
0x18005d0af  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x18005d0b4  test    eax, eax
0x18005d0b6  jnz     loc_18005D263
0x18005d0bc  mov     rcx, [rbp+lpString1]; lpString1
0x18005d0c0  lea     edi, [rax+1]
0x18005d0c3  or      ebx, 0FFFFFFFFh
0x18005d0c6  mov     [rbp+arg_0], 0
0x18005d0ce  mov     r9d, ebx; cchCount2
0x18005d0d1  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x18005d0d5  mov     edx, ebx; cchCount1
0x18005d0d7  lea     r8, aAndcondition; "andCondition"
0x18005d0de  call    cs:__imp_CompareStringOrdinal
0x18005d0e4  cmp     eax, 2
0x18005d0e7  jnz     short loc_18005D119
0x18005d0e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d0f0  mov     ebx, 8007000Eh
0x18005d0f5  lea     ecx, [rdi+3Fh]; unsigned __int64
0x18005d0f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d0fd  mov     [rbp+var_10], rax
0x18005d101  test    rax, rax
0x18005d104  jz      loc_18005D20C
0x18005d10a  xor     edx, edx; enum tagCONDITION_TYPE
0x18005d10c  mov     rcx, rax; this
0x18005d10f  call    ??0CompoundCondition@StructuredQuery1@@AEAA@W4tagCONDITION_TYPE@@@Z; StructuredQuery1::CompoundCondition::CompoundCondition(tagCONDITION_TYPE)
0x18005d114  jmp     loc_18005D1DA
0x18005d119  mov     rcx, [rbp+lpString1]; lpString1
0x18005d11d  lea     r8, aOrcondition; "orCondition"
0x18005d124  mov     r9d, ebx; cchCount2
0x18005d127  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x18005d12b  mov     edx, ebx; cchCount1
0x18005d12d  call    cs:__imp_CompareStringOrdinal
0x18005d133  cmp     eax, 2
0x18005d136  jnz     short loc_18005D15D
0x18005d138  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d13f  mov     ebx, 8007000Eh
0x18005d144  lea     ecx, [rax+3Eh]; unsigned __int64
0x18005d147  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d14c  mov     [rbp+var_10], rax
0x18005d150  test    rax, rax
0x18005d153  jz      loc_18005D20C
0x18005d159  mov     edx, edi
0x18005d15b  jmp     short loc_18005D10C
0x18005d15d  mov     rcx, [rbp+lpString1]; lpString1
0x18005d161  lea     r8, aNotcondition; "notCondition"
0x18005d168  mov     r9d, ebx; cchCount2
0x18005d16b  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x18005d16f  mov     edx, ebx; cchCount1
0x18005d171  call    cs:__imp_CompareStringOrdinal
0x18005d177  cmp     eax, 2
0x18005d17a  jnz     short loc_18005D190
0x18005d17c  lea     r8, [rbp+arg_0]; void **
0x18005d180  lea     rdx, _GUID_169db284_8361_4be4_bdb0_0b73ad8764f1; struct _GUID *
0x18005d187  call    ?CreateInstance@NegationCondition@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::NegationCondition::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18005d18c  mov     ebx, eax
0x18005d18e  jmp     short loc_18005D20C
0x18005d190  mov     rcx, [rbp+lpString1]; lpString1
0x18005d194  lea     r8, aLeafcondition; "leafCondition"
0x18005d19b  mov     r9d, ebx; cchCount2
0x18005d19e  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x18005d1a2  mov     edx, ebx; cchCount1
0x18005d1a4  call    cs:__imp_CompareStringOrdinal
0x18005d1aa  cmp     eax, 2
0x18005d1ad  jnz     loc_18005D252
0x18005d1b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d1ba  mov     ecx, 0B0h; unsigned __int64
0x18005d1bf  mov     ebx, 8007000Eh
0x18005d1c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d1c9  mov     [rbp+var_10], rax
0x18005d1cd  test    rax, rax
0x18005d1d0  jz      short loc_18005D20C
0x18005d1d2  mov     rcx, rax; this
0x18005d1d5  call    ??0LeafCondition@StructuredQuery1@@AEAA@XZ; StructuredQuery1::LeafCondition::LeafCondition(void)
0x18005d1da  mov     rdi, rax
0x18005d1dd  test    rax, rax
0x18005d1e0  jz      short loc_18005D20C
0x18005d1e2  mov     rcx, [rax]
0x18005d1e5  lea     r8, [rbp+arg_0]
0x18005d1e9  lea     rdx, _GUID_169db284_8361_4be4_bdb0_0b73ad8764f1
0x18005d1f0  mov     rax, [rcx]
0x18005d1f3  mov     rcx, rdi
0x18005d1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1fb  mov     rcx, [rdi]
0x18005d1fe  mov     ebx, eax
0x18005d200  mov     rax, [rcx+10h]
0x18005d204  mov     rcx, rdi
0x18005d207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d20c  test    ebx, ebx
0x18005d20e  js      short loc_18005D257
0x18005d210  mov     rcx, [rbp+arg_0]
0x18005d214  mov     rdx, rsi
0x18005d217  mov     rax, [rcx]
0x18005d21a  mov     rax, [rax+20h]
0x18005d21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d223  mov     ebx, eax
0x18005d225  test    eax, eax
0x18005d227  js      short loc_18005D240
0x18005d229  mov     rcx, [rbp+arg_0]
0x18005d22d  mov     r8, r14
0x18005d230  mov     rdx, r15
0x18005d233  mov     rax, [rcx]
0x18005d236  mov     rax, [rax]
0x18005d239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d23e  mov     ebx, eax
0x18005d240  mov     rcx, [rbp+arg_0]
0x18005d244  mov     rax, [rcx]
0x18005d247  mov     rax, [rax+10h]
0x18005d24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d250  jmp     short loc_18005D257
0x18005d252  mov     ebx, 80070057h
0x18005d257  mov     rcx, [rbp+lpString1]; pv
0x18005d25b  call    cs:__imp_CoTaskMemFree
0x18005d261  jmp     short loc_18005D268
0x18005d263  mov     ebx, 80070057h
0x18005d268  mov     rcx, [rbp+arg_18]
0x18005d26c  mov     rax, [rcx]
0x18005d26f  mov     rax, [rax+10h]
0x18005d273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d278  mov     eax, ebx
0x18005d27a  mov     rbx, [rsp+40h+arg_8]
0x18005d27f  add     rsp, 40h
0x18005d283  pop     r15
0x18005d285  pop     r14
0x18005d287  pop     rdi
0x18005d288  pop     rsi
0x18005d289  pop     rbp
0x18005d28a  retn
```
