# COpenSearchRowset::_ParseItemProperties(IPropertyStore *,IXmlReader *)

- ea: `0x180045b58`
- end: `0x180045e2a`
- name: `?_ParseItemProperties@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@PEAUIXmlReader@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, struct IPropertyStore *, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045774`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18000ebd0`
- `0x1800120a4`
- `0x18004419c`
- `0x1800459f0`
- `0x180045b58`
- `0x180045e30`
- `0x180047b74`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180045c30`
- `SHLWAPI!__imp_StrCmpICW` at `0x180045c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045d6d`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseItemProperties(
        COpenSearchRowset *this,
        struct IPropertyStore *a2,
        struct IXmlReader *a3)
{
  int ElementText; // ebx
  int v6; // r12d
  int v7; // r15d
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v9; // eax
  bool v10; // zf
  struct IXmlReaderVtbl *v11; // rax
  COpenSearchRowset *v12; // rcx
  struct IXmlReaderVtbl *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  struct IXmlReaderVtbl *v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int16 *v20; // r14
  int v21; // esi
  COpenSearchRowset *v22; // rcx
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszStr1; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  struct IPropertyStore *v29; // [rsp+58h] [rbp-A8h]
  LPVOID pv; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v31[264]; // [rsp+70h] [rbp-90h] BYREF

  v29 = a2;
  v24 = 0;
  ElementText = 0;
  memset_0(v31, 0, 0x208u);
  v6 = 0;
  v7 = 1;
  while ( !v6 )
  {
    lpVtbl = a3->lpVtbl;
    if ( v7 )
      v9 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))lpVtbl->Read)(a3, &v24);
    else
      v9 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))lpVtbl->GetNodeType)(a3, &v24);
    ElementText = v9;
    v7 = 1;
    v10 = v9 == 0;
    if ( v9 < 0 )
      goto LABEL_26;
    if ( v24 != 1 )
    {
      if ( v24 == 15 )
      {
        v11 = a3->lpVtbl;
        pszStr1 = 0;
        ElementText = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v11->GetLocalName)(
                        a3,
                        &pszStr1,
                        0);
        if ( ElementText >= 0 )
        {
          if ( StrCmpICW(pszStr1, L"item") )
            COpenSearchRowset::_XmlPathRemoveElement(v12, v31);
          else
            v6 = 1;
        }
      }
      goto LABEL_25;
    }
    v13 = a3->lpVtbl;
    v28 = 0;
    ElementText = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))v13->GetNamespaceUri)(a3, &v28, 0);
    if ( ElementText >= 0 )
    {
      v25 = 0;
      ElementText = _AllocString<CTCoAllocPolicy>(v15, v14, v28);
      if ( ElementText >= 0 )
      {
        v16 = a3->lpVtbl;
        v26 = 0;
        v17 = ((__int64 (__fastcall *)(struct IXmlReader *, unsigned __int16 **, _QWORD))v16->GetLocalName)(a3, &v26, 0);
        v20 = v25;
        ElementText = v17;
        if ( v17 >= 0 )
        {
          pv = 0;
          ElementText = _AllocString<CTCoAllocPolicy>(v19, v18, (__int64)v26);
          if ( ElementText >= 0 )
          {
            if ( !v31[0] || (ElementText = StringCchCatW(v31, 0x104u, L"/"), ElementText >= 0) )
            {
              ElementText = StringCchCatW(v31, 0x104u, v26);
              if ( ElementText >= 0 )
              {
                v21 = ((__int64 (__fastcall *)(struct IXmlReader *))a3->lpVtbl->IsEmptyElement)(a3);
                ElementText = COpenSearchRowset::_ParseItemElementAttributes(this, v29, a3, v31, v20);
                if ( ElementText >= 0 )
                {
                  if ( v21 )
                    goto LABEL_22;
                  v25 = 0;
                  ElementText = COpenSearchRowset::_GetElementText(v22, a3, (const unsigned __int16 **)&v25);
                  if ( ElementText >= 0 )
                    ElementText = COpenSearchRowset::_ParseMappedProperty(this, v29, v25, v20, v31);
                  if ( ElementText == -2147023728 )
                  {
                    ElementText = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a3->lpVtbl->GetNodeType)(
                                    a3,
                                    &v24);
                    if ( ElementText >= 0 )
                    {
                      if ( v24 == 15 )
LABEL_22:
                        COpenSearchRowset::_XmlPathRemoveElement(v22, v31);
                      else
                        v7 = 0;
                    }
                  }
                }
              }
            }
            CoTaskMemFree(pv);
          }
        }
        CoTaskMemFree(v20);
      }
    }
LABEL_25:
    v10 = ElementText == 0;
LABEL_26:
    if ( !v10 )
      return (unsigned int)ElementText;
  }
  return (unsigned int)ElementText;
}

```

## disassembly

```asm
0x180045b58  mov     [rsp-8+arg_18], rbx
0x180045b5d  push    rbp
0x180045b5e  push    rsi
0x180045b5f  push    rdi
0x180045b60  push    r12
0x180045b62  push    r13
0x180045b64  push    r14
0x180045b66  push    r15
0x180045b68  lea     rbp, [rsp-190h]
0x180045b70  sub     rsp, 290h
0x180045b77  mov     rax, cs:__security_cookie
0x180045b7e  xor     rax, rsp
0x180045b81  mov     [rbp+1C0h+var_40], rax
0x180045b88  xor     esi, esi
0x180045b8a  mov     [rsp+2C0h+var_268], rdx
0x180045b8f  mov     rdi, r8
0x180045b92  mov     [rsp+2C0h+var_290], esi
0x180045b96  mov     r13, rcx
0x180045b99  xor     edx, edx; Val
0x180045b9b  mov     r8d, 208h; Size
0x180045ba1  lea     rcx, [rsp+2C0h+var_250]; void *
0x180045ba6  mov     ebx, esi
0x180045ba8  call    memset_0
0x180045bad  mov     r12d, esi
0x180045bb0  lea     r15d, [rsi+1]
0x180045bb4  test    r12d, r12d
0x180045bb7  jnz     loc_180045D7B
0x180045bbd  mov     rax, [rdi]
0x180045bc0  lea     rdx, [rsp+2C0h+var_290]
0x180045bc5  mov     rcx, rdi
0x180045bc8  test    r15d, r15d
0x180045bcb  jz      short loc_180045BD3
0x180045bcd  mov     rax, [rax+30h]
0x180045bd1  jmp     short loc_180045BD7
0x180045bd3  mov     rax, [rax+38h]
0x180045bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bdc  mov     ebx, eax
0x180045bde  mov     r15d, 1
0x180045be4  test    eax, eax
0x180045be6  js      loc_180045D75
0x180045bec  mov     ecx, [rsp+2C0h+var_290]
0x180045bf0  sub     ecx, r15d
0x180045bf3  jz      short loc_180045C51
0x180045bf5  cmp     ecx, 0Eh
0x180045bf8  jnz     loc_180045D73
0x180045bfe  mov     rax, [rdi]
0x180045c01  lea     rdx, [rsp+2C0h+pszStr1]
0x180045c06  xor     r8d, r8d
0x180045c09  mov     [rsp+2C0h+pszStr1], rsi
0x180045c0e  mov     rcx, rdi
0x180045c11  mov     rax, [rax+70h]
0x180045c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c1a  mov     ebx, eax
0x180045c1c  test    eax, eax
0x180045c1e  js      loc_180045D73
0x180045c24  mov     rcx, [rsp+2C0h+pszStr1]; pszStr1
0x180045c29  lea     rdx, aItem; "item"
0x180045c30  call    cs:__imp_StrCmpICW
0x180045c36  test    eax, eax
0x180045c38  jnz     short loc_180045C42
0x180045c3a  mov     r12d, r15d
0x180045c3d  jmp     loc_180045D73
0x180045c42  lea     rdx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180045c47  call    ?_XmlPathRemoveElement@COpenSearchRowset@@AEAAXPEAG@Z; COpenSearchRowset::_XmlPathRemoveElement(ushort *)
0x180045c4c  jmp     loc_180045D73
0x180045c51  mov     rax, [rdi]
0x180045c54  lea     rdx, [rsp+2C0h+var_270]
0x180045c59  xor     r8d, r8d
0x180045c5c  mov     [rsp+2C0h+var_270], rsi
0x180045c61  mov     rcx, rdi
0x180045c64  mov     rax, [rax+68h]
0x180045c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c6d  mov     ebx, eax
0x180045c6f  test    eax, eax
0x180045c71  js      loc_180045D73
0x180045c77  mov     r8, [rsp+2C0h+var_270]
0x180045c7c  lea     r9, [rsp+2C0h+var_288]
0x180045c81  mov     [rsp+2C0h+var_288], rsi
0x180045c86  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180045c8b  mov     ebx, eax
0x180045c8d  test    eax, eax
0x180045c8f  js      loc_180045D73
0x180045c95  mov     rax, [rdi]
0x180045c98  lea     rdx, [rsp+2C0h+var_280]
0x180045c9d  xor     r8d, r8d
0x180045ca0  mov     [rsp+2C0h+var_280], rsi
0x180045ca5  mov     rcx, rdi
0x180045ca8  mov     rax, [rax+70h]
0x180045cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cb1  mov     r14, [rsp+2C0h+var_288]
0x180045cb6  mov     ebx, eax
0x180045cb8  test    eax, eax
0x180045cba  js      loc_180045D6A
0x180045cc0  mov     r8, [rsp+2C0h+var_280]
0x180045cc5  lea     r9, [rsp+2C0h+pv]
0x180045cca  mov     [rsp+2C0h+pv], rsi
0x180045ccf  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180045cd4  mov     ebx, eax
0x180045cd6  test    eax, eax
0x180045cd8  js      loc_180045D6A
0x180045cde  cmp     [rsp+2C0h+var_250], si
0x180045ce3  jz      short loc_180045D01
0x180045ce5  lea     r8, asc_180058A0C; "/"
0x180045cec  mov     edx, 104h; unsigned __int64
0x180045cf1  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180045cf6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180045cfb  mov     ebx, eax
0x180045cfd  test    eax, eax
0x180045cff  js      short loc_180045D5F
0x180045d01  mov     r8, [rsp+2C0h+var_280]; unsigned __int16 *
0x180045d06  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180045d0b  mov     edx, 104h; unsigned __int64
0x180045d10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180045d15  mov     ebx, eax
0x180045d17  test    eax, eax
0x180045d19  js      short loc_180045D5F
0x180045d1b  mov     rax, [rdi]
0x180045d1e  mov     rcx, rdi
0x180045d21  mov     rax, [rax+0A0h]
0x180045d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d2d  mov     rdx, [rsp+2C0h+var_268]; struct IPropertyStore *
0x180045d32  lea     r9, [rsp+2C0h+var_250]; unsigned __int16 *
0x180045d37  mov     r8, rdi; struct IXmlReader *
0x180045d3a  mov     [rsp+2C0h+var_2A0], r14; unsigned __int16 *
0x180045d3f  mov     rcx, r13; this
0x180045d42  mov     esi, eax
0x180045d44  call    ?_ParseItemElementAttributes@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@PEAUIXmlReader@@PEBG2@Z; COpenSearchRowset::_ParseItemElementAttributes(IPropertyStore *,IXmlReader *,ushort const *,ushort const *)
0x180045d49  mov     ebx, eax
0x180045d4b  test    eax, eax
0x180045d4d  js      short loc_180045D5D
0x180045d4f  test    esi, esi
0x180045d51  jz      short loc_180045DA7
0x180045d53  lea     rdx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180045d58  call    ?_XmlPathRemoveElement@COpenSearchRowset@@AEAAXPEAG@Z; COpenSearchRowset::_XmlPathRemoveElement(ushort *)
0x180045d5d  xor     esi, esi
0x180045d5f  mov     rcx, [rsp+2C0h+pv]; pv
0x180045d64  call    cs:__imp_CoTaskMemFree
0x180045d6a  mov     rcx, r14; pv
0x180045d6d  call    cs:__imp_CoTaskMemFree
0x180045d73  test    ebx, ebx
0x180045d75  jz      loc_180045BB4
0x180045d7b  mov     eax, ebx
0x180045d7d  mov     rcx, [rbp+1C0h+var_40]
0x180045d84  xor     rcx, rsp; StackCookie
0x180045d87  call    __security_check_cookie
0x180045d8c  mov     rbx, [rsp+2C0h+arg_18]
0x180045d94  add     rsp, 290h
0x180045d9b  pop     r15
0x180045d9d  pop     r14
0x180045d9f  pop     r13
0x180045da1  pop     r12
0x180045da3  pop     rdi
0x180045da4  pop     rsi
0x180045da5  pop     rbp
0x180045da6  retn
0x180045da7  xor     esi, esi
0x180045da9  lea     r8, [rsp+2C0h+var_288]; unsigned __int16 **
0x180045dae  mov     rdx, rdi; struct IXmlReader *
0x180045db1  mov     [rsp+2C0h+var_288], rsi
0x180045db6  call    ?_GetElementText@COpenSearchRowset@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; COpenSearchRowset::_GetElementText(IXmlReader *,ushort const * *)
0x180045dbb  mov     ebx, eax
0x180045dbd  test    eax, eax
0x180045dbf  js      short loc_180045DE2
0x180045dc1  mov     r8, [rsp+2C0h+var_288]; unsigned __int16 *
0x180045dc6  lea     rax, [rsp+2C0h+var_250]
0x180045dcb  mov     rdx, [rsp+2C0h+var_268]; struct IPropertyStore *
0x180045dd0  mov     r9, r14; unsigned __int16 *
0x180045dd3  mov     rcx, r13; this
0x180045dd6  mov     [rsp+2C0h+var_2A0], rax; unsigned __int16 *
0x180045ddb  call    ?_ParseMappedProperty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@PEBG11@Z; COpenSearchRowset::_ParseMappedProperty(IPropertyStore *,ushort const *,ushort const *,ushort const *)
0x180045de0  mov     ebx, eax
0x180045de2  cmp     ebx, 80070490h
0x180045de8  jnz     loc_180045D5F
0x180045dee  mov     rax, [rdi]
0x180045df1  lea     rdx, [rsp+2C0h+var_290]
0x180045df6  mov     rcx, rdi
0x180045df9  mov     rax, [rax+38h]
0x180045dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e02  mov     ebx, eax
0x180045e04  test    eax, eax
0x180045e06  js      loc_180045D5F
0x180045e0c  cmp     [rsp+2C0h+var_290], 0Fh
0x180045e11  jnz     short loc_180045E22
0x180045e13  lea     rdx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180045e18  call    ?_XmlPathRemoveElement@COpenSearchRowset@@AEAAXPEAG@Z; COpenSearchRowset::_XmlPathRemoveElement(ushort *)
0x180045e1d  jmp     loc_180045D5F
0x180045e22  mov     r15d, esi
0x180045e25  jmp     loc_180045D5F
```
