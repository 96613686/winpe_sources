# CMetadataXMPReaderWriter::UpdateXMPMetadataNode(IXMLDOMDocument *,IXMLDOMNode *,IXMLDOMNode * *)

- ea: `0x180015958`
- end: `0x180015c5a`
- name: `?UpdateXMPMetadataNode@CMetadataXMPReaderWriter@@IEAAJPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAPEAU3@@Z`
- size: `770`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, struct IXMLDOMDocument *, struct IXMLDOMNode *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000d550`

## callees

- `0x180004500`
- `0x180015958`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800159c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800159d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800159c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800159d5`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::UpdateXMPMetadataNode(
        CMetadataXMPReaderWriter *this,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode *a3,
        struct IXMLDOMNode **a4)
{
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // rbx
  int v9; // eax
  int v10; // esi
  int v11; // ecx
  bool v12; // zf
  HRESULT (__stdcall *createNode)(IXMLDOMDocument *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  struct IXMLDOMNode *v14; // rbx
  struct IXMLDOMNode *v16; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+38h] [rbp-31h] BYREF
  __int64 v18; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h] BYREF
  __int128 v20; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  __int64 v22; // [rsp+70h] [rbp+7h]
  unsigned __int16 *v23; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int16 *v24; // [rsp+80h] [rbp+17h] BYREF
  int v25; // [rsp+D0h] [rbp+67h] BYREF
  int v26; // [rsp+D4h] [rbp+6Bh]
  __int64 v27; // [rsp+E0h] [rbp+77h] BYREF

  v26 = HIDWORD(this);
  v18 = 0;
  v22 = 0;
  v20 = 0;
  v16 = 0;
  LOWORD(v20) = 18;
  v19 = 0;
  WORD4(v20) = 1;
  v17 = 0;
  v27 = 0;
  v25 = 0;
  v24 = SysAllocString(L"x:xmpmeta");
  v7 = v24;
  v23 = SysAllocString(L"adobe:ns:meta/");
  v8 = v23;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a3->lpVtbl->get_parentNode)(a3, &v19);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  if ( v9 )
    goto LABEL_5;
  if ( !v7 || !v8 )
  {
    v10 = -2147024882;
LABEL_8:
    v12 = g_doStackCaptures == 0;
    goto LABEL_30;
  }
  createNode = a2->lpVtbl->createNode;
  v21 = v22;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int128 *, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNode **))createNode)(
         a2,
         &v20,
         v7,
         v8,
         &v16);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  if ( v9 )
    goto LABEL_5;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a3->lpVtbl->get_childNodes)(a3, &v17);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  if ( v9 )
    goto LABEL_5;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 64LL))(v17, &v25);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  if ( v9 )
  {
LABEL_5:
    v12 = g_doStackCaptures == 0;
LABEL_29:
    v10 = -2147467259;
LABEL_30:
    if ( v12 )
      goto LABEL_37;
    goto LABEL_31;
  }
  if ( v25 != 1 )
  {
    v10 = -2003292273;
    goto LABEL_8;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 56LL))(v17, 0, &v18);
  v10 = v9;
  if ( v9 < 0 )
  {
LABEL_2:
    if ( !g_doStackCaptures )
      goto LABEL_37;
    v11 = v9;
    goto LABEL_32;
  }
  if ( v9 )
    goto LABEL_5;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, __int64 *))v16->lpVtbl->appendChild)(v16, v18, &v27);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  if ( v9 )
    goto LABEL_5;
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode *, struct IXMLDOMNode *, __int64 *))(*(_QWORD *)v19
                                                                                                  + 152LL))(
          v19,
          v16,
          a3,
          &v27);
  if ( v10 >= 0 )
  {
    if ( v10 )
    {
      v12 = g_doStackCaptures == 0;
      goto LABEL_29;
    }
    v14 = v16;
    if ( *a4 )
      ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
    *a4 = v14;
    if ( v14 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->AddRef)(v14);
  }
  else if ( g_doStackCaptures )
  {
LABEL_31:
    v11 = v10;
LABEL_32:
    DoStackCapture(v11);
  }
LABEL_37:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  FreeBSTR(&v23);
  FreeBSTR(&v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180015958  mov     [rsp-8+arg_8], rbx
0x18001595d  mov     [rsp-8+arg_0], rcx
0x180015962  push    rbp
0x180015963  push    rsi
0x180015964  push    rdi
0x180015965  push    r12
0x180015967  push    r13
0x180015969  push    r14
0x18001596b  push    r15
0x18001596d  lea     rbp, [rsp-27h]
0x180015972  sub     rsp, 90h
0x180015979  xor     r13d, r13d
0x18001597c  lea     rcx, aXXmpmeta; "x:xmpmeta"
0x180015983  xor     eax, eax
0x180015985  mov     [rbp+57h+var_80], r13
0x180015989  mov     [rbp+57h+var_50], rax
0x18001598d  xorps   xmm0, xmm0
0x180015990  movups  [rbp+57h+var_70], xmm0
0x180015994  lea     eax, [r13+12h]
0x180015998  mov     [rbp+57h+var_90], r13
0x18001599c  mov     word ptr [rbp+57h+var_70], ax
0x1800159a0  mov     r15, r9
0x1800159a3  lea     eax, [r13+1]
0x1800159a7  mov     [rbp+57h+var_78], r13
0x1800159ab  mov     word ptr [rbp+57h+var_70+8], ax
0x1800159af  mov     r14, r8
0x1800159b2  mov     r12, rdx
0x1800159b5  mov     [rbp+57h+var_88], r13
0x1800159b9  mov     [rbp+57h+arg_10], r13
0x1800159bd  mov     dword ptr [rbp+57h+arg_0], r13d
0x1800159c1  call    cs:__imp_SysAllocString
0x1800159c7  lea     rcx, aAdobeNsMeta; "adobe:ns:meta/"
0x1800159ce  mov     [rbp+57h+var_40], rax
0x1800159d2  mov     rdi, rax
0x1800159d5  call    cs:__imp_SysAllocString
0x1800159db  mov     [rbp+57h+var_48], rax
0x1800159df  lea     rdx, [rbp+57h+var_78]
0x1800159e3  mov     rbx, rax
0x1800159e6  mov     rcx, r14
0x1800159e9  mov     rax, [r14]
0x1800159ec  mov     rax, [rax+58h]
0x1800159f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f5  mov     esi, eax
0x1800159f7  test    eax, eax
0x1800159f9  jns     short loc_180015A0F
0x1800159fb  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015a02  jz      loc_180015BAE
0x180015a08  mov     ecx, eax
0x180015a0a  jmp     loc_180015B78
0x180015a0f  jz      short loc_180015A1D
0x180015a11  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015a18  jmp     loc_180015B6F
0x180015a1d  test    rdi, rdi
0x180015a20  jnz     short loc_180015A33
0x180015a22  mov     esi, 8007000Eh
0x180015a27  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015a2e  jmp     loc_180015B74
0x180015a33  test    rbx, rbx
0x180015a36  jz      short loc_180015A22
0x180015a38  mov     rax, [r12]
0x180015a3c  lea     rcx, [rbp+57h+var_90]
0x180015a40  movups  xmm0, [rbp+57h+var_70]
0x180015a44  lea     rdx, [rbp+57h+var_70]
0x180015a48  mov     [rsp+0C0h+var_A0], rcx
0x180015a4d  movsd   xmm1, [rbp+57h+var_50]
0x180015a52  mov     r9, rbx
0x180015a55  mov     rax, [rax+1C0h]
0x180015a5c  mov     r8, rdi
0x180015a5f  mov     rcx, r12
0x180015a62  movaps  [rbp+57h+var_70], xmm0
0x180015a66  movsd   [rbp+57h+var_60], xmm1
0x180015a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a70  mov     esi, eax
0x180015a72  test    eax, eax
0x180015a74  js      short loc_1800159FB
0x180015a76  jnz     short loc_180015A11
0x180015a78  mov     rax, [r14]
0x180015a7b  lea     rdx, [rbp+57h+var_88]
0x180015a7f  mov     rcx, r14
0x180015a82  mov     rax, [rax+60h]
0x180015a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a8b  mov     esi, eax
0x180015a8d  test    eax, eax
0x180015a8f  js      loc_1800159FB
0x180015a95  jnz     loc_180015A11
0x180015a9b  mov     rcx, [rbp+57h+var_88]
0x180015a9f  lea     rdx, [rbp+57h+arg_0]
0x180015aa3  mov     rax, [rcx]
0x180015aa6  mov     rax, [rax+40h]
0x180015aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aaf  mov     esi, eax
0x180015ab1  test    eax, eax
0x180015ab3  js      loc_1800159FB
0x180015ab9  jnz     loc_180015A11
0x180015abf  cmp     dword ptr [rbp+57h+arg_0], 1
0x180015ac3  jz      short loc_180015ACF
0x180015ac5  mov     esi, 88982F8Fh
0x180015aca  jmp     loc_180015A27
0x180015acf  mov     rcx, [rbp+57h+var_88]
0x180015ad3  lea     r8, [rbp+57h+var_80]
0x180015ad7  xor     edx, edx
0x180015ad9  mov     rax, [rcx]
0x180015adc  mov     rax, [rax+38h]
0x180015ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae5  mov     esi, eax
0x180015ae7  test    eax, eax
0x180015ae9  js      loc_1800159FB
0x180015aef  jnz     loc_180015A11
0x180015af5  mov     rcx, [rbp+57h+var_90]
0x180015af9  lea     r8, [rbp+57h+arg_10]
0x180015afd  mov     rdx, [rbp+57h+var_80]
0x180015b01  mov     rax, [rcx]
0x180015b04  mov     rax, [rax+0A8h]
0x180015b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b10  mov     esi, eax
0x180015b12  test    eax, eax
0x180015b14  js      loc_1800159FB
0x180015b1a  jnz     loc_180015A11
0x180015b20  mov     rcx, [rbp+57h+arg_10]
0x180015b24  test    rcx, rcx
0x180015b27  jz      short loc_180015B39
0x180015b29  mov     rax, [rcx]
0x180015b2c  mov     rax, [rax+10h]
0x180015b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b35  mov     [rbp+57h+arg_10], r13
0x180015b39  mov     rcx, [rbp+57h+var_78]
0x180015b3d  lea     r9, [rbp+57h+arg_10]
0x180015b41  mov     rdx, [rbp+57h+var_90]
0x180015b45  mov     r8, r14
0x180015b48  mov     rax, [rcx]
0x180015b4b  mov     rax, [rax+98h]
0x180015b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b57  mov     esi, eax
0x180015b59  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180015b5f  test    esi, esi
0x180015b61  jns     short loc_180015B6B
0x180015b63  test    eax, eax
0x180015b65  jnz     short loc_180015B76
0x180015b67  test    esi, esi
0x180015b69  js      short loc_180015BAE
0x180015b6b  jz      short loc_180015B7F
0x180015b6d  test    eax, eax
0x180015b6f  mov     esi, 80004005h
0x180015b74  jz      short loc_180015BAE
0x180015b76  mov     ecx, esi; int
0x180015b78  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180015b7d  jmp     short loc_180015BAE
0x180015b7f  mov     rcx, [r15]
0x180015b82  mov     rbx, [rbp+57h+var_90]
0x180015b86  test    rcx, rcx
0x180015b89  jz      short loc_180015B97
0x180015b8b  mov     rax, [rcx]
0x180015b8e  mov     rax, [rax+10h]
0x180015b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b97  mov     [r15], rbx
0x180015b9a  test    rbx, rbx
0x180015b9d  jz      short loc_180015BAE
0x180015b9f  mov     rax, [rbx]
0x180015ba2  mov     rcx, rbx
0x180015ba5  mov     rax, [rax+8]
0x180015ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bae  mov     rcx, [rbp+57h+var_88]
0x180015bb2  test    rcx, rcx
0x180015bb5  jz      short loc_180015BC7
0x180015bb7  mov     rax, [rcx]
0x180015bba  mov     rax, [rax+10h]
0x180015bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc3  mov     [rbp+57h+var_88], r13
0x180015bc7  mov     rcx, [rbp+57h+var_80]
0x180015bcb  test    rcx, rcx
0x180015bce  jz      short loc_180015BE0
0x180015bd0  mov     rax, [rcx]
0x180015bd3  mov     rax, [rax+10h]
0x180015bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bdc  mov     [rbp+57h+var_80], r13
0x180015be0  mov     rcx, [rbp+57h+arg_10]
0x180015be4  test    rcx, rcx
0x180015be7  jz      short loc_180015BF9
0x180015be9  mov     rax, [rcx]
0x180015bec  mov     rax, [rax+10h]
0x180015bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bf5  mov     [rbp+57h+arg_10], r13
0x180015bf9  mov     rcx, [rbp+57h+var_78]
0x180015bfd  test    rcx, rcx
0x180015c00  jz      short loc_180015C12
0x180015c02  mov     rax, [rcx]
0x180015c05  mov     rax, [rax+10h]
0x180015c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0e  mov     [rbp+57h+var_78], r13
0x180015c12  mov     rcx, [rbp+57h+var_90]
0x180015c16  test    rcx, rcx
0x180015c19  jz      short loc_180015C2B
0x180015c1b  mov     rdx, [rcx]
0x180015c1e  mov     rax, [rdx+10h]
0x180015c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c27  mov     [rbp+57h+var_90], r13
0x180015c2b  lea     rcx, [rbp+57h+var_48]; unsigned __int16 **
0x180015c2f  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180015c34  lea     rcx, [rbp+57h+var_40]; unsigned __int16 **
0x180015c38  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180015c3d  mov     rbx, [rsp+0C0h+arg_8]
0x180015c45  mov     eax, esi
0x180015c47  add     rsp, 90h
0x180015c4e  pop     r15
0x180015c50  pop     r14
0x180015c52  pop     r13
0x180015c54  pop     r12
0x180015c56  pop     rdi
0x180015c57  pop     rsi
0x180015c58  pop     rbp
0x180015c59  retn
```
