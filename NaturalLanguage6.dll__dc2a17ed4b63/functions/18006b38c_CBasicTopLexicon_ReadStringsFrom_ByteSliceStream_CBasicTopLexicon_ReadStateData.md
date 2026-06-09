# CBasicTopLexicon::ReadStringsFrom(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)

- ea: `0x18006b38c`
- end: `0x18006b54e`
- name: `?ReadStringsFrom@CBasicTopLexicon@@IEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003b120`

## callees

- `0x180003edc`
- `0x180005160`
- `0x180005190`
- `0x18001a0d8`
- `0x180032118`
- `0x18003757c`
- `0x18003b2cc`
- `0x18003dfcc`
- `0x180041364`
- `0x18006a198`
- `0x18006b38c`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 *__fastcall CBasicTopLexicon::ReadStringsFrom(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v7; // rsi
  int v8; // r12d
  int v9; // r15d
  CUserData *v10; // rbx
  unsigned int v11; // edx
  CUserData *v12; // rax
  CUserData *v13; // rsi
  const VARIANTARG *v14; // rdi
  VARIANTARG *v15; // rax
  unsigned int v16; // edx
  __int64 *v17; // rcx
  __int64 v18; // rdi
  CUserData *v19; // rdi
  CUserData *v21; // [rsp+28h] [rbp-40h] BYREF
  __int64 v22[3]; // [rsp+30h] [rbp-38h] BYREF
  VARIANTARG v23; // [rsp+48h] [rbp-20h] BYREF
  volatile signed __int32 *v25; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+60h]

  v26 = a4;
  v22[1] = -2;
  v4 = a4;
  v7 = a1;
  v8 = 0;
  v9 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3);
  v22[0] = 0;
  *a2 = 0;
  v10 = 0;
  v21 = 0;
  while ( v8 < v9 || (_BYTE)v9 == 0xFF )
  {
    CBasicTopLexicon::ReadStringFrom(v7, &v25, a3, v4);
    if ( (!v25 || !*(_QWORD *)v25) && (_BYTE)v9 == 0xFF )
    {
      _bstr_t::_Free(&v25, v11);
      break;
    }
    v12 = (CUserData *)operator new(0x38u);
    v22[2] = (__int64)v12;
    if ( v12 )
      v13 = CUserData::CUserData(v12);
    else
      v13 = 0;
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v22);
    v22[0] = (__int64)v13;
    v14 = (const VARIANTARG *)_variant_t::_variant_t((_variant_t *)&v23, (const struct _bstr_t *)&v25);
    v15 = (VARIANTARG *)_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(v22);
    _variant_t::operator=(v15 + 1, v14);
    _variant_t::~_variant_t(&v23);
    if ( !*a2 && v13 )
    {
      *a2 = (__int64)v13;
      _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(a2);
    }
    if ( v10 )
    {
      v17 = (__int64 *)(_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->((__int64 *)&v21)
                      + 48);
      v18 = *v17;
      if ( (CUserData *)*v17 != v13 )
      {
        *v17 = (__int64)v13;
        _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v17);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    if ( v10 != v13 )
    {
      v19 = v10;
      v10 = v13;
      v21 = v13;
      _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef((__int64 *)&v21);
      if ( v19 )
        (*(void (__fastcall **)(CUserData *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    _bstr_t::_Free(&v25, v16);
    ++v8;
    v4 = v26;
    v7 = a1;
  }
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v21);
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v22);
  return a2;
}

```

## disassembly

```asm
0x18006b38c  mov     [rsp-40h+arg_18], r9
0x18006b391  mov     [rsp-40h+arg_8], rdx
0x18006b396  mov     [rsp-40h+arg_0], rcx
0x18006b39b  push    rbp
0x18006b39c  push    rbx
0x18006b39d  push    rsi
0x18006b39e  push    rdi
0x18006b39f  push    r12
0x18006b3a1  push    r13
0x18006b3a3  push    r14
0x18006b3a5  push    r15
0x18006b3a7  mov     rbp, rsp
0x18006b3aa  sub     rsp, 68h
0x18006b3ae  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18006b3b6  mov     rdi, r9
0x18006b3b9  mov     r13, r8
0x18006b3bc  mov     r14, rdx
0x18006b3bf  mov     rsi, rcx
0x18006b3c2  xor     r12d, r12d
0x18006b3c5  mov     [rbp+var_48], r12d
0x18006b3c9  mov     rax, [r8]
0x18006b3cc  mov     rcx, r8
0x18006b3cf  mov     rax, [rax+18h]
0x18006b3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3d8  movzx   r15d, al
0x18006b3dc  mov     [rbp+var_38], r12
0x18006b3e0  mov     [r14], r12
0x18006b3e3  mov     [rbp+var_48], 1
0x18006b3ea  mov     ebx, r12d
0x18006b3ed  mov     [rbp+var_40], rbx
0x18006b3f1  cmp     r12d, r15d
0x18006b3f4  jl      short loc_18006B400
0x18006b3f6  cmp     r15b, 0FFh
0x18006b3fa  jnz     loc_18006B526
0x18006b400  mov     r9, rdi
0x18006b403  mov     r8, r13
0x18006b406  lea     rdx, [rbp+arg_10]
0x18006b40a  mov     rcx, rsi
0x18006b40d  call    ?ReadStringFrom@CBasicTopLexicon@@IEBA?AV_bstr_t@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadStringFrom(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18006b412  nop
0x18006b413  mov     rax, [rbp+arg_10]
0x18006b417  test    rax, rax
0x18006b41a  jz      short loc_18006B422
0x18006b41c  cmp     qword ptr [rax], 0
0x18006b420  jnz     short loc_18006B42C
0x18006b422  cmp     r15b, 0FFh
0x18006b426  jz      loc_18006B51C
0x18006b42c  mov     ecx, 38h ; '8'; Size
0x18006b431  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b436  mov     [rbp+var_28], rax
0x18006b43a  test    rax, rax
0x18006b43d  jz      short loc_18006B44C
0x18006b43f  mov     rcx, rax; this
0x18006b442  call    ??0CUserData@@QEAA@XZ; CUserData::CUserData(void)
0x18006b447  mov     rsi, rax
0x18006b44a  jmp     short loc_18006B44E
0x18006b44c  xor     esi, esi
0x18006b44e  lea     rcx, [rbp+var_38]
0x18006b452  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18006b457  mov     [rbp+var_38], rsi
0x18006b45b  lea     rdx, [rbp+arg_10]; struct _bstr_t *
0x18006b45f  lea     rcx, [rbp+var_20]; this
0x18006b463  call    ??0_variant_t@@QEAA@AEBV_bstr_t@@@Z; _variant_t::_variant_t(_bstr_t const &)
0x18006b468  mov     rdi, rax
0x18006b46b  lea     rcx, [rbp+var_38]
0x18006b46f  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18006b474  lea     rcx, [rax+18h]
0x18006b478  mov     rdx, rdi
0x18006b47b  call    ??4_variant_t@@QEAAAEAV0@AEBV0@@Z; _variant_t::operator=(_variant_t const &)
0x18006b480  nop
0x18006b481  lea     rcx, [rbp+var_20]; this
0x18006b485  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006b48a  cmp     qword ptr [r14], 0
0x18006b48e  jnz     short loc_18006B4A0
0x18006b490  test    rsi, rsi
0x18006b493  jz      short loc_18006B4A0
0x18006b495  mov     [r14], rsi
0x18006b498  mov     rcx, r14
0x18006b49b  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18006b4a0  test    rbx, rbx
0x18006b4a3  jz      short loc_18006B4D6
0x18006b4a5  lea     rcx, [rbp+var_40]
0x18006b4a9  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18006b4ae  lea     rcx, [rax+30h]
0x18006b4b2  mov     rdi, [rcx]
0x18006b4b5  cmp     rdi, rsi
0x18006b4b8  jz      short loc_18006B4D6
0x18006b4ba  mov     [rcx], rsi
0x18006b4bd  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18006b4c2  test    rdi, rdi
0x18006b4c5  jz      short loc_18006B4D6
0x18006b4c7  mov     rax, [rdi]
0x18006b4ca  mov     rcx, rdi
0x18006b4cd  mov     rax, [rax+10h]
0x18006b4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4d6  cmp     rbx, rsi
0x18006b4d9  jz      short loc_18006B503
0x18006b4db  mov     rdi, rbx
0x18006b4de  mov     rbx, rsi
0x18006b4e1  mov     [rbp+var_40], rbx
0x18006b4e5  lea     rcx, [rbp+var_40]
0x18006b4e9  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18006b4ee  test    rdi, rdi
0x18006b4f1  jz      short loc_18006B503
0x18006b4f3  mov     rax, [rdi]
0x18006b4f6  mov     rcx, rdi
0x18006b4f9  mov     rax, [rax+10h]
0x18006b4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b502  nop
0x18006b503  lea     rcx, [rbp+arg_10]; this
0x18006b507  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006b50c  inc     r12d
0x18006b50f  mov     rdi, [rbp+arg_18]
0x18006b513  mov     rsi, [rbp+arg_0]
0x18006b517  jmp     loc_18006B3F1
0x18006b51c  lea     rcx, [rbp+arg_10]; this
0x18006b520  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006b525  nop
0x18006b526  lea     rcx, [rbp+var_40]
0x18006b52a  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18006b52f  nop
0x18006b530  lea     rcx, [rbp+var_38]
0x18006b534  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18006b539  mov     rax, r14
0x18006b53c  add     rsp, 68h
0x18006b540  pop     r15
0x18006b542  pop     r14
0x18006b544  pop     r13
0x18006b546  pop     r12
0x18006b548  pop     rdi
0x18006b549  pop     rsi
0x18006b54a  pop     rbx
0x18006b54b  pop     rbp
0x18006b54c  retn
```
