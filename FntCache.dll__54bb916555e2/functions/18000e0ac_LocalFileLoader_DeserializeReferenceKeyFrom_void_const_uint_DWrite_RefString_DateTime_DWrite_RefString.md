# LocalFileLoader::DeserializeReferenceKeyFrom(void const *,uint,DWrite::RefString *,DateTime *,DWrite::RefString *)

- ea: `0x18000e0ac`
- end: `0x18000e32d`
- name: `?DeserializeReferenceKeyFrom@LocalFileLoader@@SAXPEBXIPEAVRefString@DWrite@@PEAVDateTime@@1@Z`
- size: `641`
- prototype: `void __fastcall(const void *, unsigned int, struct DWrite::RefString *, struct DateTime *, struct DWrite::RefString *)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000da8c`
- `0x1800268c0`
- `0x1800b48e0`
- `0x1800b49a0`
- `0x1800b4a60`
- `0x1800b4e90`

## callees

- `0x18000bc70`
- `0x18000e0ac`
- `0x18000e920`
- `0x18000ee1c`
- `0x1800217ac`
- `0x180028c50`
- `0x18002bf90`
- `0x1800ab0aa`
- `0x1800b4790`
- `0x1800b4890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e234`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e234`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e129`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e1f0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e129`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e1f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LocalFileLoader::DeserializeReferenceKeyFrom(
        _QWORD *a1,
        __int64 a2,
        struct DWrite::RefString::Data **a3,
        struct DateTime *a4,
        void **a5)
{
  _QWORD *v7; // rdi
  __int64 v8; // rbx
  const wchar_t *v9; // rdi
  bool v10; // zf
  unsigned int v11; // edx
  size_t v12; // rbx
  size_t v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  size_t v16; // rsi
  const wchar_t *v17; // rbx
  size_t v18; // rdi
  __int64 v19; // rcx
  struct DWrite::RefString::Data *v20; // rbx
  struct DWrite::RefString::Data *v21; // rcx
  unsigned __int64 v22; // rsi
  const wchar_t *v23; // rdi
  unsigned int v24; // ecx
  size_t v25; // rbx
  size_t v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  struct DWrite::RefString::Data *v29; // rbx
  void **v30; // rsi
  struct DWrite::RefString::Data *v31; // rbx
  _QWORD *v32; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v33; // [rsp+28h] [rbp-28h]
  __int64 v34; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-18h]
  const wchar_t *v36; // [rsp+40h] [rbp-10h]
  size_t v37; // [rsp+48h] [rbp-8h]
  struct DWrite::RefString::Data *v38; // [rsp+70h] [rbp+20h] BYREF
  struct DWrite::RefString::Data *v39; // [rsp+88h] [rbp+38h] BYREF

  v7 = a1;
  v32 = a1;
  v33 = a2;
  if ( a4 )
  {
    if ( (unsigned int)a2 < 8 )
      goto LABEL_23;
    if ( a1 )
    {
      v8 = *a1;
    }
    else
    {
      v8 = 0;
      *(_DWORD *)_o__errno(0, a2, a3) = 22;
      invalid_parameter_noinfo();
      LODWORD(a2) = v33;
      v7 = v32;
    }
    *(_QWORD *)a4 = v8;
  }
  if ( (unsigned int)a2 < 8 )
    goto LABEL_23;
  v9 = (const wchar_t *)(v7 + 1);
  v32 = v9;
  v10 = (_DWORD)a2 == 8;
  v11 = a2 - 8;
  v33 = v11;
  if ( v10 || (v11 & 1) != 0 )
  {
    Exception::Exception((Exception *)&v34, -2003283961, 0);
    v35 = &v32;
    LogAndThrow<MalformedKeyException>(&v34, 0x72646C6C636CLL, 760);
  }
  if ( ((unsigned __int8)v9 & 1) != 0 )
    goto LABEL_23;
  v12 = (unsigned __int64)v11 >> 1;
  v13 = wcsnlen(v9, v12);
  v16 = v13;
  if ( v13 >= v12 )
  {
    Exception::Exception((Exception *)&v34, -2003283961, 0);
    v35 = &v32;
    LogAndThrow<MalformedKeyException>(&v34, 0x72646C6C636CLL, 770);
  }
  if ( a3 )
  {
    if ( v13 && *v9 == 42 )
    {
      v17 = v9 + 1;
      v18 = v13 - 1;
      v19 = *(_QWORD *)GetFontsDirectory(&v39);
      v34 = v19 + 8;
      v35 = (_QWORD *)*(unsigned int *)(v19 + 4);
      v36 = v17;
      v37 = v18;
      DWrite::RefString::RefString(&v38, (__int64)&v34);
      v20 = v38;
      _InterlockedIncrement((volatile signed __int32 *)v38);
      DWrite::RefString::DecrementRef(*a3);
      *a3 = v20;
      DWrite::RefString::DecrementRef(v20);
      v21 = v39;
    }
    else
    {
      v29 = DWrite::RefString::NewData(v9, v13, v14, v15);
      v38 = v29;
      DWrite::RefString::operator=((void **)a3, (volatile signed __int32 **)&v38);
      v21 = v29;
    }
    DWrite::RefString::DecrementRef(v21);
  }
  v22 = 2 * v16 + 2;
  if ( v22 > v33 )
    goto LABEL_23;
  v23 = (const wchar_t *)((char *)v32 + v22);
  v32 = (_QWORD *)((char *)v32 + v22);
  v24 = v33 - v22;
  v33 = v24;
  if ( !v24 )
    return;
  if ( ((unsigned __int8)v23 & 1) != 0 )
LABEL_23:
    CheckedPtr<unsigned char const,FailAsExceptionPolicy<MalformedKeyException>,unsigned int>::FailOutOfRange(&v32);
  v25 = (unsigned __int64)v24 >> 1;
  v26 = wcsnlen(v23, v25);
  if ( v26 >= v25 )
  {
    Exception::Exception((Exception *)&v34, -2003283961, 0);
    v35 = &v32;
    LogAndThrow<MalformedKeyException>(&v34, 0x72646C6C636CLL, 800);
  }
  v30 = a5;
  if ( a5 )
  {
    v31 = DWrite::RefString::NewData(v23, v26, v27, v28);
    v38 = v31;
    DWrite::RefString::operator=(v30, (volatile signed __int32 **)&v38);
    DWrite::RefString::DecrementRef(v31);
  }
}

```

## disassembly

```asm
0x18000e0ac  mov     [rsp-18h+arg_8], rbx
0x18000e0b1  mov     [rsp-18h+arg_10], rsi
0x18000e0b6  push    rbp
0x18000e0b7  push    rdi
0x18000e0b8  push    r14
0x18000e0ba  mov     rbp, rsp
0x18000e0bd  sub     rsp, 50h
0x18000e0c1  mov     rsi, r9
0x18000e0c4  mov     r14, r8
0x18000e0c7  mov     rdi, rcx
0x18000e0ca  mov     [rbp+var_30], rcx
0x18000e0ce  mov     [rbp+var_28], edx
0x18000e0d1  test    r9, r9
0x18000e0d4  jz      short loc_18000E0EE
0x18000e0d6  cmp     edx, 8
0x18000e0d9  jb      loc_18000E278
0x18000e0df  test    rcx, rcx
0x18000e0e2  jz      loc_18000E232
0x18000e0e8  mov     rbx, [rcx]
0x18000e0eb  mov     [rsi], rbx
0x18000e0ee  cmp     edx, 8
0x18000e0f1  jb      loc_18000E278
0x18000e0f7  add     rdi, 8
0x18000e0fb  mov     [rbp+var_30], rdi
0x18000e0ff  add     edx, 0FFFFFFF8h
0x18000e102  mov     [rbp+var_28], edx
0x18000e105  jz      loc_18000E2FA
0x18000e10b  test    dl, 1
0x18000e10e  jnz     loc_18000E2FA
0x18000e114  test    dil, 1
0x18000e118  jnz     loc_18000E278
0x18000e11e  mov     ebx, edx
0x18000e120  shr     rbx, 1
0x18000e123  mov     rdx, rbx; MaxCount
0x18000e126  mov     rcx, rdi; Source
0x18000e129  call    cs:__imp_wcsnlen
0x18000e12f  mov     rsi, rax
0x18000e132  cmp     rax, rbx
0x18000e135  jnb     loc_18000E282
0x18000e13b  test    r14, r14
0x18000e13e  jz      short loc_18000E1B1
0x18000e140  test    rax, rax
0x18000e143  jz      loc_18000E251
0x18000e149  cmp     word ptr [rdi], 2Ah ; '*'
0x18000e14d  jnz     loc_18000E251
0x18000e153  lea     rbx, [rdi+2]
0x18000e157  lea     rdi, [rax-1]
0x18000e15b  lea     rcx, [rbp+arg_18]
0x18000e15f  call    ?GetFontsDirectory@@YA?AVRefString@DWrite@@XZ; GetFontsDirectory(void)
0x18000e164  nop
0x18000e165  mov     rcx, [rax]
0x18000e168  lea     rax, [rcx+8]
0x18000e16c  mov     [rbp+var_20], rax
0x18000e170  mov     eax, [rcx+4]
0x18000e173  mov     [rbp+var_18], rax
0x18000e177  mov     [rbp+var_10], rbx
0x18000e17b  mov     [rbp+var_8], rdi
0x18000e17f  lea     rdx, [rbp+var_20]
0x18000e183  lea     rcx, [rbp+arg_0]
0x18000e187  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x18000e18c  nop
0x18000e18d  mov     rbx, [rbp+arg_0]
0x18000e191  lock inc dword ptr [rbx]
0x18000e194  mov     rcx, [r14]; struct DWrite::RefString::Data *
0x18000e197  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000e19c  mov     [r14], rbx
0x18000e19f  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18000e1a2  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000e1a7  nop
0x18000e1a8  mov     rcx, [rbp+arg_18]; struct DWrite::RefString::Data *
0x18000e1ac  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000e1b1  lea     rsi, ds:2[rsi*2]
0x18000e1b9  mov     ecx, [rbp+var_28]
0x18000e1bc  cmp     rsi, rcx
0x18000e1bf  ja      loc_18000E278
0x18000e1c5  mov     rdi, [rbp+var_30]
0x18000e1c9  add     rdi, rsi
0x18000e1cc  mov     [rbp+var_30], rdi
0x18000e1d0  sub     ecx, esi
0x18000e1d2  mov     [rbp+var_28], ecx
0x18000e1d5  jz      loc_18000E2E5
0x18000e1db  test    dil, 1
0x18000e1df  jnz     loc_18000E278
0x18000e1e5  mov     ebx, ecx
0x18000e1e7  shr     rbx, 1
0x18000e1ea  mov     rdx, rbx; MaxCount
0x18000e1ed  mov     rcx, rdi; Source
0x18000e1f0  call    cs:__imp_wcsnlen
0x18000e1f6  cmp     rax, rbx
0x18000e1f9  jb      loc_18000E2B5
0x18000e1ff  xor     r8d, r8d; unsigned int
0x18000e202  mov     edx, 88985007h; int
0x18000e207  lea     rcx, [rbp+var_20]; this
0x18000e20b  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18000e210  lea     rax, [rbp+var_30]
0x18000e214  mov     [rbp+var_18], rax
0x18000e218  mov     rdx, 72646C6C636Ch
0x18000e222  mov     r8d, 320h
0x18000e228  lea     rcx, [rbp+var_20]
0x18000e22c  call    ??$LogAndThrow@VMalformedKeyException@@@@YAXAEBVMalformedKeyException@@VEventTag@@I@Z; LogAndThrow<MalformedKeyException>(MalformedKeyException const &,EventTag,uint)
0x18000e232  xor     ebx, ebx
0x18000e234  call    cs:__imp__o__errno
0x18000e23a  mov     dword ptr [rax], 16h
0x18000e240  call    _invalid_parameter_noinfo
0x18000e245  mov     edx, [rbp+var_28]
0x18000e248  mov     rdi, [rbp+var_30]
0x18000e24c  jmp     loc_18000E0EB
0x18000e251  mov     rdx, rsi; unsigned __int64
0x18000e254  mov     rcx, rdi; Src
0x18000e257  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x18000e25c  mov     rbx, rax
0x18000e25f  mov     [rbp+arg_0], rax
0x18000e263  lea     rdx, [rbp+arg_0]
0x18000e267  mov     rcx, r14
0x18000e26a  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18000e26f  nop
0x18000e270  mov     rcx, rbx
0x18000e273  jmp     loc_18000E1AC
0x18000e278  lea     rcx, [rbp+var_30]
0x18000e27c  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VMalformedKeyException@@@@I@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<MalformedKeyException>,uint>::FailOutOfRange(void)
0x18000e282  xor     r8d, r8d; unsigned int
0x18000e285  mov     edx, 88985007h; int
0x18000e28a  lea     rcx, [rbp+var_20]; this
0x18000e28e  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18000e293  lea     rax, [rbp+var_30]
0x18000e297  mov     [rbp+var_18], rax
0x18000e29b  mov     rdx, 72646C6C636Ch
0x18000e2a5  mov     r8d, 302h
0x18000e2ab  lea     rcx, [rbp+var_20]
0x18000e2af  call    ??$LogAndThrow@VMalformedKeyException@@@@YAXAEBVMalformedKeyException@@VEventTag@@I@Z; LogAndThrow<MalformedKeyException>(MalformedKeyException const &,EventTag,uint)
0x18000e2b5  mov     rsi, [rbp+arg_20]
0x18000e2b9  test    rsi, rsi
0x18000e2bc  jz      short loc_18000E2E5
0x18000e2be  mov     rdx, rax; unsigned __int64
0x18000e2c1  mov     rcx, rdi; Src
0x18000e2c4  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x18000e2c9  mov     rbx, rax
0x18000e2cc  mov     [rbp+arg_0], rax
0x18000e2d0  lea     rdx, [rbp+arg_0]
0x18000e2d4  mov     rcx, rsi
0x18000e2d7  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x18000e2dc  nop
0x18000e2dd  mov     rcx, rbx; struct DWrite::RefString::Data *
0x18000e2e0  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000e2e5  lea     r11, [rsp+50h+var_s0]
0x18000e2ea  mov     rbx, [r11+28h]
0x18000e2ee  mov     rsi, [r11+30h]
0x18000e2f2  mov     rsp, r11
0x18000e2f5  pop     r14
0x18000e2f7  pop     rdi
0x18000e2f8  pop     rbp
0x18000e2f9  retn
0x18000e2fa  xor     r8d, r8d; unsigned int
0x18000e2fd  mov     edx, 88985007h; int
0x18000e302  lea     rcx, [rbp+var_20]; this
0x18000e306  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18000e30b  lea     rax, [rbp+var_30]
0x18000e30f  mov     [rbp+var_18], rax
0x18000e313  mov     rdx, 72646C6C636Ch
0x18000e31d  mov     r8d, 2F8h
0x18000e323  lea     rcx, [rbp+var_20]
0x18000e327  call    ??$LogAndThrow@VMalformedKeyException@@@@YAXAEBVMalformedKeyException@@VEventTag@@I@Z; LogAndThrow<MalformedKeyException>(MalformedKeyException const &,EventTag,uint)
```
