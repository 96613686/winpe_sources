# CMetadataXMPAltReaderWriter::AddAttributesToNode(IXMLDOMDocument *,RDFItem *,IXMLDOMNode *)

- ea: `0x180022e10`
- end: `0x180022f91`
- name: `?AddAttributesToNode@CMetadataXMPAltReaderWriter@@MEAAJPEAUIXMLDOMDocument@@PEAVRDFItem@@PEAUIXMLDOMNode@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, struct IXMLDOMDocument *, struct RDFItem *, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180004500`
- `0x1800171c4`
- `0x180022e10`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022e59`
- `OLEAUT32!__imp_SysAllocString` at `0x180022e59`

## string_xrefs

- `0x180022e52`: `xml:lang`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::AddAttributesToNode(
        CMetadataXMPAltReaderWriter *this,
        struct IXMLDOMDocument *a2,
        struct RDFItem *a3,
        struct IXMLDOMNode *a4)
{
  __int64 v4; // rax
  int v8; // ebx
  unsigned __int16 *v9; // rax
  bool v10; // zf
  int v11; // eax
  int v12; // ecx
  __int64 v14; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v16[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v17; // [rsp+80h] [rbp+38h] BYREF

  v4 = *(_QWORD *)this;
  v14 = 0;
  v15 = 0;
  v16[0] = 0;
  v8 = 0;
  if ( !(*(unsigned int (__fastcall **)(CMetadataXMPAltReaderWriter *))(v4 + 272))(this) )
  {
    v9 = SysAllocString(L"xml:lang");
    v17 = v9;
    if ( !v9 )
    {
      v8 = -2147024882;
LABEL_4:
      v10 = g_doStackCaptures == 0;
      goto LABEL_20;
    }
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 *, __int64 *))a2->lpVtbl->createAttribute)(
            a2,
            v9,
            &v14);
    v8 = v11;
    if ( v11 < 0 )
    {
LABEL_6:
      if ( g_doStackCaptures )
      {
        v12 = v11;
LABEL_22:
        DoStackCapture(v12);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
    if ( !v11 )
    {
      v11 = (*(__int64 (__fastcall **)(struct RDFItem *, _QWORD *))(*(_QWORD *)a3 + 32LL))(a3, v16);
      v8 = v11;
      if ( v11 < 0 )
        goto LABEL_6;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 216LL))(v14, v16[0]);
      v8 = v11;
      if ( v11 < 0 )
        goto LABEL_6;
      if ( !v11 )
      {
        v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a4->lpVtbl->get_attributes)(a4, &v15);
        v8 = v11;
        if ( v11 < 0 )
          goto LABEL_6;
        if ( !v11 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v15 + 64LL))(v15, v14, 0);
          if ( v8 < 0 )
          {
            if ( !g_doStackCaptures )
              goto LABEL_23;
            goto LABEL_21;
          }
          if ( !v8 )
          {
LABEL_23:
            FreeBSTR(&v17);
            goto LABEL_24;
          }
          v8 = -2147467259;
          v10 = g_doStackCaptures == 0;
LABEL_20:
          if ( !v10 )
          {
LABEL_21:
            v12 = v8;
            goto LABEL_22;
          }
          goto LABEL_23;
        }
      }
    }
    v8 = -2147467259;
    goto LABEL_4;
  }
LABEL_24:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022e10  push    rbp
0x180022e12  push    rbx
0x180022e13  push    rsi
0x180022e14  push    rdi
0x180022e15  push    r14
0x180022e17  push    r15
0x180022e19  mov     rbp, rsp
0x180022e1c  sub     rsp, 48h
0x180022e20  mov     rax, [rcx]
0x180022e23  xor     r15d, r15d
0x180022e26  mov     rsi, r9
0x180022e29  mov     [rbp+var_28], r15
0x180022e2d  mov     rdi, r8
0x180022e30  mov     [rbp+var_20], r15
0x180022e34  mov     r14, rdx
0x180022e37  mov     [rbp+var_18], r15
0x180022e3b  mov     rax, [rax+110h]
0x180022e42  mov     ebx, r15d
0x180022e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e4a  test    eax, eax
0x180022e4c  jnz     loc_180022F54
0x180022e52  lea     rcx, psz; "xml:lang"
0x180022e59  call    cs:__imp_SysAllocString
0x180022e5f  mov     [rbp+arg_0], rax
0x180022e63  test    rax, rax
0x180022e66  jnz     short loc_180022E79
0x180022e68  mov     ebx, 8007000Eh
0x180022e6d  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180022e74  jmp     loc_180022F42
0x180022e79  mov     rcx, [r14]
0x180022e7c  lea     r8, [rbp+var_28]
0x180022e80  mov     rdx, rax
0x180022e83  mov     r9, [rcx+1A8h]
0x180022e8a  mov     rcx, r14
0x180022e8d  mov     rax, r9
0x180022e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e95  mov     ebx, eax
0x180022e97  test    eax, eax
0x180022e99  jns     short loc_180022EAF
0x180022e9b  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180022ea2  jz      loc_180022F4B
0x180022ea8  mov     ecx, eax
0x180022eaa  jmp     loc_180022F46
0x180022eaf  jz      short loc_180022EB8
0x180022eb1  mov     ebx, 80004005h
0x180022eb6  jmp     short loc_180022E6D
0x180022eb8  mov     rax, [rdi]
0x180022ebb  lea     rdx, [rbp+var_18]
0x180022ebf  mov     rcx, rdi
0x180022ec2  mov     rax, [rax+20h]
0x180022ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ecb  mov     ebx, eax
0x180022ecd  test    eax, eax
0x180022ecf  js      short loc_180022E9B
0x180022ed1  mov     rcx, [rbp+var_28]
0x180022ed5  mov     rdx, [rbp+var_18]
0x180022ed9  mov     rax, [rcx]
0x180022edc  mov     rax, [rax+0D8h]
0x180022ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ee8  mov     ebx, eax
0x180022eea  test    eax, eax
0x180022eec  js      short loc_180022E9B
0x180022eee  jnz     short loc_180022EB1
0x180022ef0  mov     rax, [rsi]
0x180022ef3  lea     rdx, [rbp+var_20]
0x180022ef7  mov     rcx, rsi
0x180022efa  mov     rax, [rax+88h]
0x180022f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f06  mov     ebx, eax
0x180022f08  test    eax, eax
0x180022f0a  js      short loc_180022E9B
0x180022f0c  jnz     short loc_180022EB1
0x180022f0e  mov     rcx, [rbp+var_20]
0x180022f12  xor     r8d, r8d
0x180022f15  mov     rdx, [rbp+var_28]
0x180022f19  mov     rax, [rcx]
0x180022f1c  mov     rax, [rax+40h]
0x180022f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f25  mov     ebx, eax
0x180022f27  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180022f2d  test    ebx, ebx
0x180022f2f  jns     short loc_180022F39
0x180022f31  test    eax, eax
0x180022f33  jnz     short loc_180022F44
0x180022f35  test    ebx, ebx
0x180022f37  js      short loc_180022F4B
0x180022f39  jz      short loc_180022F4B
0x180022f3b  mov     ebx, 80004005h
0x180022f40  test    eax, eax
0x180022f42  jz      short loc_180022F4B
0x180022f44  mov     ecx, ebx; int
0x180022f46  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022f4b  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x180022f4f  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180022f54  mov     rcx, [rbp+var_28]
0x180022f58  test    rcx, rcx
0x180022f5b  jz      short loc_180022F6D
0x180022f5d  mov     rax, [rcx]
0x180022f60  mov     rax, [rax+10h]
0x180022f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f69  mov     [rbp+var_28], r15
0x180022f6d  mov     rcx, [rbp+var_20]
0x180022f71  test    rcx, rcx
0x180022f74  jz      short loc_180022F82
0x180022f76  mov     rdx, [rcx]
0x180022f79  mov     rax, [rdx+10h]
0x180022f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f82  mov     eax, ebx
0x180022f84  add     rsp, 48h
0x180022f88  pop     r15
0x180022f8a  pop     r14
0x180022f8c  pop     rdi
0x180022f8d  pop     rsi
0x180022f8e  pop     rbx
0x180022f8f  pop     rbp
0x180022f90  retn
```
