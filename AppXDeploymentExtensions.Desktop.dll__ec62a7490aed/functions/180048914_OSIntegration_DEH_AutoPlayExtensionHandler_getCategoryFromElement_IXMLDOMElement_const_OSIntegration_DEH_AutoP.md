# OSIntegration::DEH::AutoPlayExtensionHandler::getCategoryFromElement(IXMLDOMElement const *,OSIntegration::DEH::AutoPlayExtensionHandler::AutoPlayCategory *)

- ea: `0x180048914`
- end: `0x180048c18`
- name: `?getCategoryFromElement@AutoPlayExtensionHandler@DEH@OSIntegration@@AEAAJPEBUIXMLDOMElement@@PEAW4AutoPlayCategory@123@@Z`
- size: `772`
- prototype: `__int64 __fastcall(OSIntegration::DEH::AutoPlayExtensionHandler *__hidden this, const struct IXMLDOMElement *, enum OSIntegration::DEH::AutoPlayExtensionHandler::AutoPlayCategory *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005a4f0`
- `0x18005a700`
- `0x1800e8410`

## callees

- `0x180009dc0`
- `0x180012fc8`
- `0x18001adb4`
- `0x180048914`
- `0x18004e3e8`
- `0x18007cdc0`
- `0x1800af1bc`
- `0x1800ba469`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180048b4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180048bb4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180048b4f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180048bb4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800489e6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800489e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004897c`
- `OLEAUT32!__imp_SysFreeString` at `0x180048ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x18004897c`
- `OLEAUT32!__imp_SysFreeString` at `0x180048ab2`
- `OLEAUT32!__imp_VariantClear` at `0x180048ac3`
- `OLEAUT32!__imp_VariantClear` at `0x180048ac3`

## string_xrefs

- `0x180048a16`: `onecore\admin\appmodel\common\xmltools.cpp`
- `0x180048ada`: `onecore\admin\appmodel\osim\src\deh\autoplay\autoplayextensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSIntegration::DEH::AutoPlayExtensionHandler::getCategoryFromElement(
        OSIntegration::DEH::AutoPlayExtensionHandler *this,
        const struct IXMLDOMElement *a2,
        enum OSIntegration::DEH::AutoPlayExtensionHandler::AutoPlayCategory *a3)
{
  OLECHAR *v5; // rbx
  __int64 v6; // rcx
  const OLECHAR *v7; // rax
  signed int v8; // edi
  __int64 v9; // rdx
  wil::details::in1diag3 *v10; // rcx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r14d
  __int64 v16; // rax
  _BYTE *v17; // rsi
  _BYTE *i; // rcx
  const struct std::nothrow_t *v19; // rdx
  int v21; // ebx
  LPCWCH v22; // rdi
  const struct std::nothrow_t *v23; // rdx
  const WCHAR *v24; // r12
  const WCHAR *v25; // rcx
  const WCHAR *v26; // r8
  int v27; // ebx
  LPCWCH v28; // rdi
  const WCHAR *v29; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  __int128 v31; // [rsp+30h] [rbp-48h] BYREF
  int v32; // [rsp+40h] [rbp-38h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v31 = 0;
  v32 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v5 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_25;
  }
  SysFreeString(0);
  v6 = 0x7FFFFFFF;
  v7 = L"Category";
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = v6 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v6) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64);
  if ( v6 )
  {
    if ( (unsigned int)v9 <= 0x3FFFFFFF )
    {
      v5 = SysAllocStringLen(L"Category", v9);
      v8 = v5 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v8 = -2147024809;
    }
  }
  v10 = retaddr;
  if ( v8 < 0 )
  {
    v11 = (unsigned int)v8;
    v12 = 308;
    goto LABEL_15;
  }
  v13 = ((__int64 (__fastcall *)(const struct IXMLDOMElement *, OLECHAR *, VARIANTARG *))a2->lpVtbl->getAttribute)(
          a2,
          v5,
          &pvarg);
  v8 = v13;
  v10 = retaddr;
  if ( v13 < 0 )
  {
    v11 = (unsigned int)v13;
    v12 = 309;
    goto LABEL_15;
  }
  if ( pvarg.llVal )
  {
    v14 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v31, pvarg.bstrVal);
    v8 = v14;
    v10 = retaddr;
    if ( v14 >= 0 )
      goto LABEL_25;
    v11 = (unsigned int)v14;
    v12 = 317;
LABEL_15:
    wil::details::in1diag3::_Log_Hr(
      v10,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\common\\xmltools.cpp",
      (const char *)v11,
      bIgnoreCase);
LABEL_25:
    v17 = (_BYTE *)*((_QWORD *)&v31 + 1);
    v15 = v31;
    goto LABEL_26;
  }
  v15 = _mm_cvtsi128_si32((__m128i)0LL);
  v16 = 2LL * v15;
  v17 = (_BYTE *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  for ( i = v17; v16; --v16 )
    *i++ = 0;
LABEL_26:
  SysFreeString(v5);
  VariantClear(&pvarg);
  if ( v8 >= 0 )
  {
    v21 = cchCount2;
    v22 = lpString2;
    if ( v15 == cchCount2 && !memcmp_0(v17, lpString2, 2LL * v15) )
      goto LABEL_37;
    v24 = &Value;
    v25 = &Value;
    if ( v15 )
      v25 = (const WCHAR *)v17;
    v26 = &Value;
    if ( v21 )
      v26 = v22;
    if ( CompareStringOrdinal(v25, v15, v26, v21, 1) == 2 )
    {
LABEL_37:
      *(_DWORD *)a3 = 1;
    }
    else
    {
      v27 = dword_180244450;
      v28 = Buf2;
      if ( v15 == dword_180244450 && !memcmp_0(v17, Buf2, 2LL * v15) )
        goto LABEL_45;
      v29 = &Value;
      if ( v15 )
        v29 = (const WCHAR *)v17;
      if ( v27 )
        v24 = v28;
      if ( CompareStringOrdinal(v29, v15, v24, v27, 1) == 2 )
      {
LABEL_45:
        *(_DWORD *)a3 = 2;
      }
      else if ( (unsigned int)Common::String::CaseInsensitiveEquals((LPCWCH)v17, v15, off_180244448, dword_180244440) )
      {
        *(_DWORD *)a3 = 3;
      }
    }
    if ( v17 )
      operator delete(v17, v23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\autoplay\\autoplayextensionhandler.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    if ( v17 )
      operator delete(v17, v19);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180048914  mov     [rsp-40h+arg_0], rcx
0x180048919  push    rbp
0x18004891a  push    rbx
0x18004891b  push    rsi
0x18004891c  push    rdi
0x18004891d  push    r12
0x18004891f  push    r13
0x180048921  push    r14
0x180048923  push    r15
0x180048925  mov     rbp, rsp
0x180048928  sub     rsp, 78h
0x18004892c  movaps  [rsp+78h+var_18], xmm6
0x180048931  mov     r15, r8
0x180048934  mov     rsi, rdx
0x180048937  xorps   xmm6, xmm6
0x18004893a  movups  [rbp+var_48], xmm6
0x18004893e  xor     r13d, r13d
0x180048941  mov     [rbp+var_38], r13d
0x180048945  test    rdx, rdx
0x180048948  jnz     short loc_18004894F
0x18004894a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "extensionElement != NULL")
0x18004894f  test    r15, r15
0x180048952  jnz     short loc_180048959
0x180048954  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "category != NULL")
0x180048959  mov     [r15], r13d
0x18004895c  xorps   xmm0, xmm0
0x18004895f  xor     eax, eax
0x180048961  movups  xmmword ptr [rbp+pvarg], xmm0
0x180048965  mov     qword ptr [rbp+pvarg+10h], rax
0x180048969  mov     word ptr [rbp+pvarg], r13w
0x18004896e  mov     rbx, r13
0x180048971  test    rsi, rsi
0x180048974  jz      loc_180048AA2
0x18004897a  xor     ecx, ecx; bstrString
0x18004897c  call    cs:__imp_SysFreeString
0x180048983  nop     dword ptr [rax+rax+00h]
0x180048988  mov     [rbp+arg_0], rbx
0x18004898c  mov     r8d, 7FFFFFFFh
0x180048992  mov     ecx, r8d
0x180048995  lea     rax, ?Category@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Category"
0x18004899c  cmp     [rax], r13w
0x1800489a0  jz      short loc_1800489AC
0x1800489a2  add     rax, 2
0x1800489a6  sub     rcx, 1
0x1800489aa  jnz     short loc_18004899C
0x1800489ac  mov     rax, rcx
0x1800489af  neg     rax
0x1800489b2  sbb     edi, edi
0x1800489b4  not     edi
0x1800489b6  and     edi, 80070057h
0x1800489bc  mov     rax, rcx
0x1800489bf  sub     r8, rcx
0x1800489c2  neg     rax
0x1800489c5  sbb     rdx, rdx
0x1800489c8  and     rdx, r8; ui
0x1800489cb  test    rcx, rcx
0x1800489ce  jz      short loc_180048A06
0x1800489d0  cmp     edx, 3FFFFFFFh
0x1800489d6  jbe     short loc_1800489DF
0x1800489d8  mov     edi, 80070057h
0x1800489dd  jmp     short loc_180048A06
0x1800489df  lea     rcx, ?Category@AttributeNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "Category"
0x1800489e6  call    cs:__imp_SysAllocStringLen
0x1800489ed  nop     dword ptr [rax+rax+00h]
0x1800489f2  mov     rbx, rax
0x1800489f5  mov     [rbp+arg_0], rax
0x1800489f9  neg     rax
0x1800489fc  sbb     edi, edi
0x1800489fe  not     edi
0x180048a00  and     edi, 8007000Eh
0x180048a06  mov     rcx, [rbp+40h]; this
0x180048a0a  test    edi, edi
0x180048a0c  jns     short loc_180048A27
0x180048a0e  mov     r9d, edi; char *
0x180048a11  mov     edx, 134h; void *
0x180048a16  lea     r8, aOnecoreAdminAp_120; "onecore\\admin\\appmodel\\common\\xmlto"...
0x180048a1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048a22  jmp     loc_180048AA7
0x180048a27  mov     rax, [rsi]
0x180048a2a  lea     r8, [rbp+pvarg]
0x180048a2e  mov     rdx, rbx
0x180048a31  mov     rcx, rsi
0x180048a34  mov     rax, [rax+160h]
0x180048a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a40  mov     edi, eax
0x180048a42  mov     rcx, [rbp+40h]
0x180048a46  test    eax, eax
0x180048a48  jns     short loc_180048A54
0x180048a4a  mov     r9d, eax
0x180048a4d  mov     edx, 135h
0x180048a52  jmp     short loc_180048A16
0x180048a54  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180048a58  test    rdx, rdx
0x180048a5b  jz      short loc_180048A7A
0x180048a5d  lea     rcx, [rbp+var_48]; this
0x180048a61  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180048a66  mov     edi, eax
0x180048a68  mov     rcx, [rbp+40h]
0x180048a6c  test    eax, eax
0x180048a6e  jns     short loc_180048AA7
0x180048a70  mov     r9d, eax
0x180048a73  mov     edx, 13Dh
0x180048a78  jmp     short loc_180048A16
0x180048a7a  movd    r14d, xmm6
0x180048a7f  mov     eax, r14d
0x180048a82  add     rax, rax
0x180048a85  psrldq  xmm6, 8
0x180048a8a  movq    rsi, xmm6
0x180048a8f  mov     rcx, rsi
0x180048a92  jz      short loc_180048AAF
0x180048a94  mov     [rcx], r13b
0x180048a97  inc     rcx
0x180048a9a  sub     rax, 1
0x180048a9e  jnz     short loc_180048A94
0x180048aa0  jmp     short loc_180048AAF
0x180048aa2  mov     edi, 80070057h
0x180048aa7  mov     rsi, qword ptr [rbp+var_48+8]
0x180048aab  mov     r14d, dword ptr [rbp+var_48]
0x180048aaf  mov     rcx, rbx; bstrString
0x180048ab2  call    cs:__imp_SysFreeString
0x180048ab9  nop     dword ptr [rax+rax+00h]
0x180048abe  nop
0x180048abf  lea     rcx, [rbp+pvarg]; pvarg
0x180048ac3  call    cs:__imp_VariantClear
0x180048aca  nop     dword ptr [rax+rax+00h]
0x180048acf  test    edi, edi
0x180048ad1  jns     short loc_180048B00
0x180048ad3  mov     rcx, [rbp+40h]; this
0x180048ad7  mov     r9d, edi; char *
0x180048ada  lea     r8, aOnecoreAdminAp_70; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180048ae1  mov     edx, 54h ; 'T'; void *
0x180048ae6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048aeb  nop
0x180048aec  test    rsi, rsi
0x180048aef  jz      short loc_180048AF9
0x180048af1  mov     rcx, rsi; void *
0x180048af4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048af9  mov     eax, edi
0x180048afb  jmp     loc_180048C01
0x180048b00  mov     ebx, cs:cchCount2
0x180048b06  mov     rdi, cs:lpString2
0x180048b0d  cmp     r14d, ebx
0x180048b10  jnz     short loc_180048B27
0x180048b12  mov     r8d, r14d
0x180048b15  add     r8, r8; Size
0x180048b18  mov     rdx, rdi; Buf2
0x180048b1b  mov     rcx, rsi; Buf1
0x180048b1e  call    memcmp_0
0x180048b23  test    eax, eax
0x180048b25  jz      short loc_180048B60
0x180048b27  lea     r12, Value
0x180048b2e  mov     rcx, r12
0x180048b31  test    r14d, r14d
0x180048b34  cmovnz  rcx, rsi; lpString1
0x180048b38  mov     r8, r12
0x180048b3b  test    ebx, ebx
0x180048b3d  cmovnz  r8, rdi; lpString2
0x180048b41  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180048b49  mov     r9d, ebx; cchCount2
0x180048b4c  mov     edx, r14d; cchCount1
0x180048b4f  call    cs:__imp_CompareStringOrdinal
0x180048b56  nop     dword ptr [rax+rax+00h]
0x180048b5b  add     eax, 0FFFFFFFEh
0x180048b5e  jnz     short loc_180048B6C
0x180048b60  mov     dword ptr [r15], 1
0x180048b67  jmp     loc_180048BF2
0x180048b6c  mov     ebx, cs:dword_180244450
0x180048b72  mov     rdi, cs:Buf2
0x180048b79  cmp     r14d, ebx
0x180048b7c  jnz     short loc_180048B93
0x180048b7e  mov     r8d, r14d
0x180048b81  add     r8, r8; Size
0x180048b84  mov     rdx, rdi; Buf2
0x180048b87  mov     rcx, rsi; Buf1
0x180048b8a  call    memcmp_0
0x180048b8f  test    eax, eax
0x180048b91  jz      short loc_180048BC5
0x180048b93  mov     rcx, r12
0x180048b96  test    r14d, r14d
0x180048b99  cmovnz  rcx, rsi; lpString1
0x180048b9d  test    ebx, ebx
0x180048b9f  cmovnz  r12, rdi
0x180048ba3  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180048bab  mov     r9d, ebx; cchCount2
0x180048bae  mov     r8, r12; lpString2
0x180048bb1  mov     edx, r14d; cchCount1
0x180048bb4  call    cs:__imp_CompareStringOrdinal
0x180048bbb  nop     dword ptr [rax+rax+00h]
0x180048bc0  add     eax, 0FFFFFFFEh
0x180048bc3  jnz     short loc_180048BCE
0x180048bc5  mov     dword ptr [r15], 2
0x180048bcc  jmp     short loc_180048BF2
0x180048bce  mov     r9d, cs:dword_180244440; cchCount2
0x180048bd5  mov     r8, cs:off_180244448; Buf2
0x180048bdc  mov     edx, r14d; cchCount1
0x180048bdf  mov     rcx, rsi; lpString1
0x180048be2  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBGK0K@Z; Common::String::CaseInsensitiveEquals(ushort const *,ulong,ushort const *,ulong)
0x180048be7  test    eax, eax
0x180048be9  jz      short loc_180048BF2
0x180048beb  mov     dword ptr [r15], 3
0x180048bf2  test    rsi, rsi
0x180048bf5  jz      short loc_180048BFF
0x180048bf7  mov     rcx, rsi; void *
0x180048bfa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048bff  xor     eax, eax
0x180048c01  movaps  xmm6, [rsp+78h+var_18]
0x180048c06  add     rsp, 78h
0x180048c0a  pop     r15
0x180048c0c  pop     r14
0x180048c0e  pop     r13
0x180048c10  pop     r12
0x180048c12  pop     rdi
0x180048c13  pop     rsi
0x180048c14  pop     rbx
0x180048c15  pop     rbp
0x180048c16  retn
```
