# Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_ParseFullyQualifiedReference(ushort const *,ushort *,ushort *,Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *)

- ea: `0x180034988`
- end: `0x180034c34`
- name: `?s_ParseFullyQualifiedReference@CResourceReferenceHandlerInternal@Runtime@Resources@Microsoft@@SAJPEBGPEAG1PEAW4FULLY_QUALIFIED_REFERENCE_TYPE@234@@Z`
- size: `684`
- prototype: `static int(const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, enum Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800351dc`
- `0x18008ec00`
- `0x1800a9a10`

## callees

- `0x18002c8d0`
- `0x180034988`
- `0x180034c3c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800349e8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800349e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034b53`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034b53`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b99`
- `OLEAUT32!__imp_SysFreeString` at `0x180034ba8`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b99`
- `OLEAUT32!__imp_SysFreeString` at `0x180034ba8`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b8e`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b8e`
- `iertutil!CreateUri` at `0x180034aeb`
- `iertutil!CreateUri` at `0x180034aeb`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_ParseFullyQualifiedReference(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        enum Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *a4)
{
  unsigned __int64 v4; // rax
  __int64 v9; // rsi
  wchar_t *v10; // rax
  wchar_t *v11; // r9
  unsigned __int64 v12; // rcx
  __int64 v13; // r8
  const unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  unsigned __int16 *v16; // r10
  unsigned __int16 *v17; // rcx
  unsigned int FullyQualifiedReferenceType; // ebx
  unsigned __int16 *v19; // rdx
  unsigned __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rdx
  bool v23; // di
  WCHAR *v24; // rbx
  OLECHAR *v25; // rdi
  UINT v26; // esi
  __int64 v28; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  IUri *ppURI; // [rsp+30h] [rbp-58h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-50h] BYREF
  BSTR bstrString[9]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 < 0x19 )
    return 2147957520LL;
  if ( *a1 != 64 )
    return 2147957520LL;
  if ( a1[1] != 123 )
    return 2147957520LL;
  v9 = 2 * v4;
  if ( a1[v4 - 1] != 125 )
    return 2147957520LL;
  v10 = wcschr(a1, 0x3Fu);
  v11 = v10;
  if ( !v10 )
    return 2147957520LL;
  v12 = v10 - a1 - 2;
  if ( v12 > 0x7FFFFFFE )
  {
    FullyQualifiedReferenceType = -2147024809;
    *a2 = 0;
LABEL_38:
    v28 = 157;
    goto LABEL_39;
  }
  v13 = 276;
  v14 = a1 + 2;
  v15 = 276;
  v16 = a2;
  do
  {
    if ( !v12 )
      break;
    if ( !*v14 )
      break;
    *v16++ = *v14++;
    --v12;
    --v15;
  }
  while ( v15 );
  v17 = v16 - 1;
  FullyQualifiedReferenceType = v15 == 0 ? 0x8007007A : 0;
  if ( v15 )
    v17 = v16;
  *v17 = 0;
  if ( !v15 )
    goto LABEL_38;
  v19 = v11 + 1;
  v20 = ((__int64)a1 + v9 - (__int64)(v11 + 1) - 2) >> 1;
  if ( v20 > 0x7FFFFFFE )
  {
    FullyQualifiedReferenceType = -2147024809;
    *a3 = 0;
  }
  else
  {
    v21 = a3;
    do
    {
      if ( !v20 )
        break;
      if ( !*v19 )
        break;
      *v21++ = *v19++;
      --v20;
      --v13;
    }
    while ( v13 );
    v22 = v21 - 1;
    FullyQualifiedReferenceType = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v22 = v21;
    *v22 = 0;
    if ( v13 )
    {
      ppURI = 0;
      if ( CreateUri(a3, 0x4B84u, 0, &ppURI) >= 0 )
      {
        pbstr = 0;
        v23 = 0;
        if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetSchemeName)(ppURI, &pbstr) >= 0 )
        {
          v24 = pbstr;
          if ( pbstr )
          {
            if ( SysStringLen(pbstr) == 11 && CompareStringOrdinal(v24, -1, L"ms-resource", -1, 1) == 2 )
            {
              bstrString[0] = 0;
              if ( ((int (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetPath)(ppURI, bstrString) >= 0 )
              {
                v25 = bstrString[0];
                if ( bstrString[0] )
                  v26 = SysStringLen(bstrString[0]);
                else
                  v26 = 0;
                SysFreeString(v25);
                v23 = v26 != 0;
              }
            }
          }
          SysFreeString(v24);
        }
        ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        if ( v23 )
        {
          FullyQualifiedReferenceType = Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_GetFullyQualifiedReferenceType(
                                          a2,
                                          a4);
          if ( (FullyQualifiedReferenceType & 0x80000000) == 0 )
            return 0;
          v28 = 171;
          goto LABEL_39;
        }
      }
      return 2147957520LL;
    }
  }
  v28 = 162;
LABEL_39:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v28,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcereferencehandlerinternal.cpp",
    (const char *)FullyQualifiedReferenceType,
    bIgnoreCase);
  return FullyQualifiedReferenceType;
}

```

## disassembly

```asm
0x180034988  push    rbx
0x18003498a  push    rbp
0x18003498b  push    rsi
0x18003498c  push    rdi
0x18003498d  push    r12
0x18003498f  push    r14
0x180034991  push    r15
0x180034993  sub     rsp, 50h
0x180034997  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003499b  mov     rbp, r9
0x18003499e  xor     r12d, r12d
0x1800349a1  mov     r14, r8
0x1800349a4  mov     r15, rdx
0x1800349a7  mov     rdi, rcx
0x1800349aa  inc     rax
0x1800349ad  cmp     [rcx+rax*2], r12w
0x1800349b2  jnz     short loc_1800349AA
0x1800349b4  cmp     rax, 19h
0x1800349b8  jb      loc_180034BD9
0x1800349be  cmp     word ptr [rcx], 40h ; '@'
0x1800349c2  jnz     loc_180034BD9
0x1800349c8  cmp     word ptr [rcx+2], 7Bh ; '{'
0x1800349cd  jnz     loc_180034BD9
0x1800349d3  lea     rsi, [rax+rax]
0x1800349d7  cmp     word ptr [rsi+rcx-2], 7Dh ; '}'
0x1800349dd  jnz     loc_180034BD9
0x1800349e3  mov     edx, 3Fh ; '?'; Ch
0x1800349e8  call    cs:__imp_wcschr
0x1800349ee  mov     r9, rax
0x1800349f1  test    rax, rax
0x1800349f4  jz      loc_180034BD9
0x1800349fa  mov     rcx, rax
0x1800349fd  sub     rcx, rdi
0x180034a00  sar     rcx, 1
0x180034a03  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180034a07  cmp     rcx, 7FFFFFFEh
0x180034a0e  ja      loc_180034C12
0x180034a14  mov     r8d, 114h
0x180034a1a  lea     rax, [rdi+4]
0x180034a1e  mov     edx, r8d
0x180034a21  mov     r10, r15
0x180034a24  test    rcx, rcx
0x180034a27  jz      short loc_180034A48
0x180034a29  movzx   r11d, word ptr [rax]
0x180034a2d  test    r11w, r11w
0x180034a31  jz      short loc_180034A48
0x180034a33  mov     [r10], r11w
0x180034a37  add     rax, 2
0x180034a3b  add     r10, 2
0x180034a3f  dec     rcx
0x180034a42  sub     rdx, 1
0x180034a46  jnz     short loc_180034A24
0x180034a48  mov     rax, rdx
0x180034a4b  lea     rcx, [r10-2]
0x180034a4f  neg     rax
0x180034a52  mov     r11d, 8007007Ah
0x180034a58  sbb     ebx, ebx
0x180034a5a  not     ebx
0x180034a5c  and     ebx, r11d
0x180034a5f  test    rdx, rdx
0x180034a62  cmovnz  rcx, r10
0x180034a66  mov     [rcx], r12w
0x180034a6a  jz      loc_180034BED
0x180034a70  lea     rdx, [r9+2]
0x180034a74  sub     rsi, rdx
0x180034a77  lea     rax, [rdi-2]
0x180034a7b  add     rax, rsi
0x180034a7e  sar     rax, 1
0x180034a81  cmp     rax, 7FFFFFFEh
0x180034a87  ja      loc_180034C1D
0x180034a8d  mov     rcx, r14
0x180034a90  test    rax, rax
0x180034a93  jz      short loc_180034AB4
0x180034a95  movzx   r9d, word ptr [rdx]
0x180034a99  test    r9w, r9w
0x180034a9d  jz      short loc_180034AB4
0x180034a9f  mov     [rcx], r9w
0x180034aa3  add     rdx, 2
0x180034aa7  add     rcx, 2
0x180034aab  dec     rax
0x180034aae  sub     r8, 1
0x180034ab2  jnz     short loc_180034A90
0x180034ab4  mov     rax, r8
0x180034ab7  lea     rdx, [rcx-2]
0x180034abb  neg     rax
0x180034abe  sbb     ebx, ebx
0x180034ac0  not     ebx
0x180034ac2  and     ebx, r11d
0x180034ac5  test    r8, r8
0x180034ac8  cmovnz  rdx, rcx
0x180034acc  mov     [rdx], r12w
0x180034ad0  jz      loc_180034C26
0x180034ad6  lea     r9, [rsp+88h+ppURI]; ppURI
0x180034adb  mov     [rsp+88h+ppURI], r12
0x180034ae0  xor     r8d, r8d; dwReserved
0x180034ae3  mov     edx, 4B84h; dwFlags
0x180034ae8  mov     rcx, r14; pwzURI
0x180034aeb  call    cs:__imp_CreateUri
0x180034af1  test    eax, eax
0x180034af3  js      loc_180034BD9
0x180034af9  mov     rcx, [rsp+88h+ppURI]
0x180034afe  lea     rdx, [rsp+88h+pbstr]
0x180034b03  mov     [rsp+88h+pbstr], r12
0x180034b08  mov     dil, r12b
0x180034b0b  mov     rax, [rcx]
0x180034b0e  mov     rax, [rax+98h]
0x180034b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b1a  test    eax, eax
0x180034b1c  js      loc_180034BAE
0x180034b22  mov     rbx, [rsp+88h+pbstr]
0x180034b27  test    rbx, rbx
0x180034b2a  jz      short loc_180034BA5
0x180034b2c  mov     rcx, rbx; pbstr
0x180034b2f  call    cs:__imp_SysStringLen
0x180034b35  cmp     eax, 0Bh
0x180034b38  jnz     short loc_180034BA5
0x180034b3a  or      r9d, 0FFFFFFFFh; cchCount2
0x180034b3e  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180034b46  or      edx, r9d; cchCount1
0x180034b49  lea     r8, aMsResource_0; "ms-resource"
0x180034b50  mov     rcx, rbx; lpString1
0x180034b53  call    cs:__imp_CompareStringOrdinal
0x180034b59  cmp     eax, 2
0x180034b5c  jnz     short loc_180034BA5
0x180034b5e  mov     rcx, [rsp+88h+ppURI]
0x180034b63  lea     rdx, [rsp+88h+bstrString]
0x180034b68  mov     [rsp+88h+bstrString], r12
0x180034b6d  mov     rax, [rcx]
0x180034b70  mov     rax, [rax+78h]
0x180034b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b79  test    eax, eax
0x180034b7b  js      short loc_180034BA5
0x180034b7d  mov     rdi, [rsp+88h+bstrString]
0x180034b82  test    rdi, rdi
0x180034b85  jz      loc_180034C0D
0x180034b8b  mov     rcx, rdi; pbstr
0x180034b8e  call    cs:__imp_SysStringLen
0x180034b94  mov     esi, eax
0x180034b96  mov     rcx, rdi; bstrString
0x180034b99  call    cs:__imp_SysFreeString
0x180034b9f  test    esi, esi
0x180034ba1  setnz   dil
0x180034ba5  mov     rcx, rbx; bstrString
0x180034ba8  call    cs:__imp_SysFreeString
0x180034bae  mov     rcx, [rsp+88h+ppURI]
0x180034bb3  mov     rax, [rcx]
0x180034bb6  mov     rax, [rax+10h]
0x180034bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bbf  test    dil, dil
0x180034bc2  jz      short loc_180034BD9
0x180034bc4  mov     rdx, rbp; enum Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *
0x180034bc7  mov     rcx, r15; packageFullName
0x180034bca  call    ?s_GetFullyQualifiedReferenceType@CResourceReferenceHandlerInternal@Runtime@Resources@Microsoft@@SAJPEBGPEAW4FULLY_QUALIFIED_REFERENCE_TYPE@234@@Z; Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_GetFullyQualifiedReferenceType(ushort const *,Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *)
0x180034bcf  mov     ebx, eax
0x180034bd1  test    eax, eax
0x180034bd3  js      short loc_180034C2D
0x180034bd5  xor     eax, eax
0x180034bd7  jmp     short loc_180034BDE
0x180034bd9  mov     eax, 80073B10h
0x180034bde  add     rsp, 50h
0x180034be2  pop     r15
0x180034be4  pop     r14
0x180034be6  pop     r12
0x180034be8  pop     rdi
0x180034be9  pop     rsi
0x180034bea  pop     rbp
0x180034beb  pop     rbx
0x180034bec  retn
0x180034bed  mov     edx, 9Dh; void *
0x180034bf2  mov     rcx, [rsp+88h]; this
0x180034bfa  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180034c01  mov     r9d, ebx; char *
0x180034c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c09  mov     eax, ebx
0x180034c0b  jmp     short loc_180034BDE
0x180034c0d  mov     esi, r12d
0x180034c10  jmp     short loc_180034B96
0x180034c12  mov     ebx, 80070057h
0x180034c17  mov     [r15], r12w
0x180034c1b  jmp     short loc_180034BED
0x180034c1d  mov     ebx, 80070057h
0x180034c22  mov     [r14], r12w
0x180034c26  mov     edx, 0A2h
0x180034c2b  jmp     short loc_180034BF2
0x180034c2d  mov     edx, 0ABh
0x180034c32  jmp     short loc_180034BF2
```
