# CMetadataRDFReaderWriter::ApplyItemToDOM(RDFItem *,int)

- ea: `0x180015c60`
- end: `0x180015f95`
- name: `?ApplyItemToDOM@CMetadataRDFReaderWriter@@IEAAJPEAVRDFItem@@H@Z`
- size: `821`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002aa0`
- `0x180017d40`

## callees

- `0x180014334`
- `0x1800153b8`
- `0x180015c60`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::ApplyItemToDOM(CMetadataRDFReaderWriter *this, struct RDFItem *a2, int a3)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // r15
  int ValueAsBSTR; // eax
  int v8; // ebx
  int v9; // ecx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rax
  int v12; // eax
  bool v13; // zf
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+58h] BYREF

  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a2 + 2);
  v21 = 0;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  v17 = 0;
  v18 = 0;
  ValueAsBSTR = CMetadataRDFReaderWriter::EnsureDOM(this);
  v8 = ValueAsBSTR;
  if ( ValueAsBSTR < 0 )
  {
LABEL_2:
    if ( !g_doStackCaptures )
      goto LABEL_44;
    goto LABEL_3;
  }
  v10 = *((_QWORD *)a2 + 2);
  if ( v10 && ((*((_BYTE *)a2 + 8) & 4) == 0 || (*((_BYTE *)a2 + 8) & 8) == 0) )
  {
    ValueAsBSTR = Item::GetValueAsBSTR(a2, &v18, 0);
    v8 = ValueAsBSTR;
    if ( ValueAsBSTR < 0 )
      goto LABEL_2;
    v11 = **v3;
    if ( (*((_BYTE *)a2 + 8) & 0x10) != 0 )
    {
      ValueAsBSTR = v11(v3, &IID_IXMLDOMAttribute, &v17);
      v8 = ValueAsBSTR;
      if ( ValueAsBSTR < 0 )
        goto LABEL_2;
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v17 + 216LL))(v17, v18);
      v12 = g_doStackCaptures;
      if ( v8 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_44;
LABEL_16:
        v9 = v8;
        goto LABEL_17;
      }
      if ( v8 )
        goto LABEL_14;
      goto LABEL_42;
    }
    ValueAsBSTR = v11(v3, &IID_IXMLDOMElement, &v20);
    v8 = ValueAsBSTR;
    if ( ValueAsBSTR < 0 )
      goto LABEL_2;
    ValueAsBSTR = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v20 + 216LL))(v20, v18);
    v8 = ValueAsBSTR;
    if ( ValueAsBSTR < 0 )
      goto LABEL_2;
    if ( ValueAsBSTR )
    {
LABEL_21:
      v13 = g_doStackCaptures == 0;
LABEL_15:
      v8 = -2147467259;
      if ( v13 )
        goto LABEL_44;
      goto LABEL_16;
    }
    ValueAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD, struct RDFItem *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)this + 376LL))(
                    this,
                    *((_QWORD *)this + 23),
                    a2,
                    v3);
LABEL_23:
    v8 = ValueAsBSTR;
    if ( ValueAsBSTR < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_44;
      goto LABEL_3;
    }
LABEL_42:
    if ( a3 )
      *((_DWORD *)a2 + 2) &= ~1u;
    goto LABEL_44;
  }
  ValueAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct RDFItem *, _QWORD, __int64 *, int))(*(_QWORD *)this + 328LL))(
                  this,
                  a2,
                  *((_QWORD *)this + 23),
                  &v21,
                  a3);
  v8 = ValueAsBSTR;
  if ( ValueAsBSTR < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_44;
LABEL_3:
    v9 = ValueAsBSTR;
LABEL_17:
    DoStackCapture(v9);
    goto LABEL_44;
  }
  if ( !v10 )
  {
    ValueAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD, __int64, _QWORD, struct RDFItem *))(*(_QWORD *)this + 320LL))(
                    this,
                    *((_QWORD *)this + 23),
                    v21,
                    *((_QWORD *)this + 24),
                    a2);
    goto LABEL_23;
  }
  if ( v21 == v10 )
    goto LABEL_42;
  ValueAsBSTR = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 88LL))(v10, &v22);
  v8 = ValueAsBSTR;
  if ( ValueAsBSTR < 0 )
    goto LABEL_2;
  if ( ValueAsBSTR )
    goto LABEL_21;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v22 + 152LL))(v22, v21, v10, &v19);
  v12 = g_doStackCaptures;
  if ( v8 >= 0 )
  {
    if ( v8 )
    {
LABEL_14:
      v13 = v12 == 0;
      goto LABEL_15;
    }
    v14 = *((_QWORD *)a2 + 2);
    v15 = v21;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)a2 + 2) = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    goto LABEL_42;
  }
  if ( g_doStackCaptures )
    goto LABEL_16;
LABEL_44:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015c60  mov     [rsp-38h+arg_0], rbx
0x180015c65  push    rbp
0x180015c66  push    rsi
0x180015c67  push    rdi
0x180015c68  push    r12
0x180015c6a  push    r13
0x180015c6c  push    r14
0x180015c6e  push    r15
0x180015c70  mov     rbp, rsp
0x180015c73  sub     rsp, 50h
0x180015c77  mov     r15, [rdx+10h]
0x180015c7b  xor     r13d, r13d
0x180015c7e  mov     [rbp+arg_8], r13
0x180015c82  mov     r12d, r8d
0x180015c85  mov     [rbp+arg_18], r13
0x180015c89  mov     rdi, rdx
0x180015c8c  mov     [rbp+var_10], r13
0x180015c90  mov     r14, rcx
0x180015c93  mov     [rbp+var_8], r13
0x180015c97  mov     [rbp+var_20], r13
0x180015c9b  mov     [rbp+var_18], r13
0x180015c9f  call    ?EnsureDOM@CMetadataRDFReaderWriter@@IEAAJXZ; CMetadataRDFReaderWriter::EnsureDOM(void)
0x180015ca4  mov     ebx, eax
0x180015ca6  test    eax, eax
0x180015ca8  jns     short loc_180015CBE
0x180015caa  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015cb1  jz      loc_180015F02
0x180015cb7  mov     ecx, eax
0x180015cb9  jmp     loc_180015D59
0x180015cbe  mov     rsi, [rdi+10h]
0x180015cc2  test    rsi, rsi
0x180015cc5  jz      loc_180015DEC
0x180015ccb  test    byte ptr [rdi+8], 4
0x180015ccf  jz      short loc_180015CDB
0x180015cd1  test    byte ptr [rdi+8], 8
0x180015cd5  jnz     loc_180015DEC
0x180015cdb  xor     r8d, r8d; int
0x180015cde  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180015ce2  mov     rcx, rdi; this
0x180015ce5  call    ?GetValueAsBSTR@Item@@QEAAJPEAPEAGH@Z; Item::GetValueAsBSTR(ushort * *,int)
0x180015cea  mov     ebx, eax
0x180015cec  test    eax, eax
0x180015cee  js      short loc_180015CAA
0x180015cf0  test    byte ptr [rdi+8], 10h
0x180015cf4  mov     rcx, r15
0x180015cf7  mov     rax, [r15]
0x180015cfa  mov     rax, [rax]
0x180015cfd  jz      short loc_180015D63
0x180015cff  lea     r8, [rbp+var_20]
0x180015d03  lea     rdx, IID_IXMLDOMAttribute
0x180015d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d0f  mov     ebx, eax
0x180015d11  test    eax, eax
0x180015d13  js      short loc_180015CAA
0x180015d15  mov     rcx, [rbp+var_20]
0x180015d19  mov     rdx, [rbp+var_18]
0x180015d1d  mov     rax, [rcx]
0x180015d20  mov     rax, [rax+0D8h]
0x180015d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d2c  mov     ebx, eax
0x180015d2e  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180015d34  test    ebx, ebx
0x180015d36  jns     short loc_180015D44
0x180015d38  test    eax, eax
0x180015d3a  jnz     short loc_180015D57
0x180015d3c  test    ebx, ebx
0x180015d3e  js      loc_180015F02
0x180015d44  jz      loc_180015EF9
0x180015d4a  test    eax, eax
0x180015d4c  mov     ebx, 80004005h
0x180015d51  jz      loc_180015F02
0x180015d57  mov     ecx, ebx; int
0x180015d59  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180015d5e  jmp     loc_180015F02
0x180015d63  lea     r8, [rbp+var_8]
0x180015d67  lea     rdx, IID_IXMLDOMElement
0x180015d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d73  mov     ebx, eax
0x180015d75  test    eax, eax
0x180015d77  js      loc_180015CAA
0x180015d7d  mov     rcx, [rbp+var_8]
0x180015d81  mov     rdx, [rbp+var_18]
0x180015d85  mov     rax, [rcx]
0x180015d88  mov     rax, [rax+0D8h]
0x180015d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d94  mov     ebx, eax
0x180015d96  test    eax, eax
0x180015d98  js      loc_180015CAA
0x180015d9e  jz      short loc_180015DA9
0x180015da0  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015da7  jmp     short loc_180015D4C
0x180015da9  mov     rax, [r14]
0x180015dac  mov     r9, r15
0x180015daf  mov     rdx, [r14+0B8h]
0x180015db6  mov     r8, rdi
0x180015db9  mov     rcx, r14
0x180015dbc  mov     rax, [rax+178h]
0x180015dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dc8  mov     ebx, eax
0x180015dca  test    eax, eax
0x180015dcc  jns     loc_180015EF9
0x180015dd2  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015dd9  jnz     loc_180015CB7
0x180015ddf  test    eax, eax
0x180015de1  jns     loc_180015EF9
0x180015de7  jmp     loc_180015F02
0x180015dec  mov     rax, [r14]
0x180015def  lea     r9, [rbp+arg_8]
0x180015df3  mov     r8, [r14+0B8h]
0x180015dfa  mov     rdx, rdi
0x180015dfd  mov     rcx, r14
0x180015e00  mov     dword ptr [rsp+50h+var_30], r12d
0x180015e05  mov     rax, [rax+148h]
0x180015e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e11  mov     ebx, eax
0x180015e13  test    eax, eax
0x180015e15  jns     short loc_180015E2C
0x180015e17  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180015e1e  jnz     loc_180015CB7
0x180015e24  test    eax, eax
0x180015e26  js      loc_180015F02
0x180015e2c  test    rsi, rsi
0x180015e2f  jnz     short loc_180015E5F
0x180015e31  mov     rax, [r14]
0x180015e34  mov     rcx, r14
0x180015e37  mov     r9, [r14+0C0h]
0x180015e3e  mov     r8, [rbp+arg_8]
0x180015e42  mov     rdx, [r14+0B8h]
0x180015e49  mov     rax, [rax+140h]
0x180015e50  mov     [rsp+50h+var_30], rdi
0x180015e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e5a  jmp     loc_180015DC8
0x180015e5f  cmp     [rbp+arg_8], rsi
0x180015e63  jz      loc_180015EF9
0x180015e69  mov     rax, [rsi]
0x180015e6c  lea     rdx, [rbp+arg_18]
0x180015e70  mov     rcx, rsi
0x180015e73  mov     rax, [rax+58h]
0x180015e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7c  mov     ebx, eax
0x180015e7e  test    eax, eax
0x180015e80  js      loc_180015CAA
0x180015e86  jnz     loc_180015DA0
0x180015e8c  mov     rcx, [rbp+arg_18]
0x180015e90  lea     r9, [rbp+var_10]
0x180015e94  mov     rdx, [rbp+arg_8]
0x180015e98  mov     r8, rsi
0x180015e9b  mov     rax, [rcx]
0x180015e9e  mov     rax, [rax+98h]
0x180015ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eaa  mov     ebx, eax
0x180015eac  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180015eb2  test    ebx, ebx
0x180015eb4  jns     short loc_180015EC2
0x180015eb6  test    eax, eax
0x180015eb8  jnz     loc_180015D57
0x180015ebe  test    ebx, ebx
0x180015ec0  js      short loc_180015F02
0x180015ec2  jnz     loc_180015D4A
0x180015ec8  mov     rcx, [rdi+10h]
0x180015ecc  mov     rsi, [rbp+arg_8]
0x180015ed0  test    rcx, rcx
0x180015ed3  jz      short loc_180015EE1
0x180015ed5  mov     rax, [rcx]
0x180015ed8  mov     rax, [rax+10h]
0x180015edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ee1  mov     [rdi+10h], rsi
0x180015ee5  test    rsi, rsi
0x180015ee8  jz      short loc_180015EF9
0x180015eea  mov     rax, [rsi]
0x180015eed  mov     rcx, rsi
0x180015ef0  mov     rax, [rax+8]
0x180015ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef9  test    r12d, r12d
0x180015efc  jz      short loc_180015F02
0x180015efe  and     dword ptr [rdi+8], 0FFFFFFFEh
0x180015f02  mov     rcx, [rbp+arg_8]
0x180015f06  test    rcx, rcx
0x180015f09  jz      short loc_180015F1B
0x180015f0b  mov     rax, [rcx]
0x180015f0e  mov     rax, [rax+10h]
0x180015f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f17  mov     [rbp+arg_8], r13
0x180015f1b  mov     rcx, [rbp+arg_18]
0x180015f1f  test    rcx, rcx
0x180015f22  jz      short loc_180015F34
0x180015f24  mov     rax, [rcx]
0x180015f27  mov     rax, [rax+10h]
0x180015f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f30  mov     [rbp+arg_18], r13
0x180015f34  mov     rcx, [rbp+var_10]
0x180015f38  test    rcx, rcx
0x180015f3b  jz      short loc_180015F4D
0x180015f3d  mov     rax, [rcx]
0x180015f40  mov     rax, [rax+10h]
0x180015f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f49  mov     [rbp+var_10], r13
0x180015f4d  mov     rcx, [rbp+var_20]
0x180015f51  test    rcx, rcx
0x180015f54  jz      short loc_180015F66
0x180015f56  mov     rax, [rcx]
0x180015f59  mov     rax, [rax+10h]
0x180015f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f62  mov     [rbp+var_20], r13
0x180015f66  mov     rcx, [rbp+var_8]
0x180015f6a  test    rcx, rcx
0x180015f6d  jz      short loc_180015F7B
0x180015f6f  mov     rdx, [rcx]
0x180015f72  mov     rax, [rdx+10h]
0x180015f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f7b  mov     eax, ebx
0x180015f7d  mov     rbx, [rsp+50h+arg_0]
0x180015f85  add     rsp, 50h
0x180015f89  pop     r15
0x180015f8b  pop     r14
0x180015f8d  pop     r13
0x180015f8f  pop     r12
0x180015f91  pop     rdi
0x180015f92  pop     rsi
0x180015f93  pop     rbp
0x180015f94  retn
```
