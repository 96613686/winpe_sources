# CBasicTopLexicon::ReadUserData(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)

- ea: `0x18006b554`
- end: `0x18006b72a`
- name: `?ReadUserData@CBasicTopLexicon@@IEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z`
- size: `470`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003b120`
- `0x18003b8d0`

## callees

- `0x180003edc`
- `0x180005160`
- `0x180005190`
- `0x18001a07c`
- `0x18001a0d8`
- `0x180032118`
- `0x18003757c`
- `0x18003b120`
- `0x18003b2cc`
- `0x18003dfcc`
- `0x18006a198`
- `0x18006b554`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 *__fastcall CBasicTopLexicon::ReadUserData(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  CUserData *v7; // rbx
  int v8; // r15d
  unsigned __int8 v9; // al
  int v10; // r13d
  CUserData *v11; // rax
  CUserData *v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // eax
  const VARIANTARG *v17; // rdi
  VARIANTARG *v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rdi
  CUserData *v21; // rdi
  CUserData *v23; // [rsp+38h] [rbp-40h] BYREF
  __int64 v24[3]; // [rsp+40h] [rbp-38h] BYREF
  VARIANTARG v25; // [rsp+58h] [rbp-20h] BYREF
  volatile signed __int32 *v27; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+60h]

  v28 = a4;
  v24[1] = -2;
  v4 = a4;
  v23 = 0;
  *a2 = 0;
  v7 = 0;
  v24[0] = 0;
  v8 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3);
  v10 = v9;
  if ( v9 )
  {
    do
    {
      v11 = (CUserData *)operator new(0x38u);
      v24[2] = (__int64)v11;
      if ( v11 )
        v12 = CUserData::CUserData(v11);
      else
        v12 = 0;
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v23);
      v23 = v12;
      v13 = CBasicTopLexicon::ReadStringFrom(a1, &v27, a3, v4);
      v14 = _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->((__int64 *)&v23);
      _bstr_t::operator=(v14 + 16, v13);
      _bstr_t::_Free(&v27, v15);
      v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 64LL))(a3);
      v17 = (const VARIANTARG *)CBasicTopLexicon::ReadObjectFrom(a1, &v25, a3, v16, v28);
      v18 = (VARIANTARG *)_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->((__int64 *)&v23);
      _variant_t::operator=(v18 + 1, v17);
      _variant_t::~_variant_t(&v25);
      if ( !*a2 && v12 )
      {
        *a2 = (__int64)v12;
        _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(a2);
      }
      if ( v7 )
      {
        v19 = (__int64 *)(_com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(v24)
                        + 48);
        v20 = *v19;
        if ( (CUserData *)*v19 != v12 )
        {
          *v19 = (__int64)v12;
          _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v19);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      if ( v7 != v12 )
      {
        v21 = v7;
        v7 = v12;
        v24[0] = (__int64)v12;
        _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v24);
        if ( v21 )
          (*(void (__fastcall **)(CUserData *))(*(_QWORD *)v21 + 16LL))(v21);
      }
      ++v8;
      v4 = v28;
    }
    while ( v8 < v10 );
  }
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v24);
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v23);
  return a2;
}

```

## disassembly

```asm
0x18006b554  mov     [rsp-40h+arg_18], r9
0x18006b559  mov     [rsp-40h+arg_8], rdx
0x18006b55e  mov     [rsp-40h+arg_0], rcx
0x18006b563  push    rbp
0x18006b564  push    rbx
0x18006b565  push    rsi
0x18006b566  push    rdi
0x18006b567  push    r12
0x18006b569  push    r13
0x18006b56b  push    r14
0x18006b56d  push    r15
0x18006b56f  mov     rbp, rsp
0x18006b572  sub     rsp, 78h
0x18006b576  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18006b57e  mov     rdi, r9
0x18006b581  mov     r12, r8
0x18006b584  mov     r14, rdx
0x18006b587  mov     [rbp+var_48], 0
0x18006b58e  mov     [rbp+var_40], 0
0x18006b596  mov     qword ptr [rdx], 0
0x18006b59d  mov     [rbp+var_48], 1
0x18006b5a4  xor     ebx, ebx
0x18006b5a6  mov     [rbp+var_38], rbx
0x18006b5aa  xor     r15d, r15d
0x18006b5ad  mov     rax, [r8]
0x18006b5b0  mov     rcx, r8
0x18006b5b3  mov     rax, [rax+18h]
0x18006b5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5bc  movzx   r13d, al
0x18006b5c0  test    al, al
0x18006b5c2  jz      loc_18006B702
0x18006b5c8  mov     ecx, 38h ; '8'; Size
0x18006b5cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b5d2  mov     [rbp+var_28], rax
0x18006b5d6  test    rax, rax
0x18006b5d9  jz      short loc_18006B5E8
0x18006b5db  mov     rcx, rax; this
0x18006b5de  call    ??0CUserData@@QEAA@XZ; CUserData::CUserData(void)
0x18006b5e3  mov     rsi, rax
0x18006b5e6  jmp     short loc_18006B5EA
0x18006b5e8  xor     esi, esi
0x18006b5ea  lea     rcx, [rbp+var_40]
0x18006b5ee  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18006b5f3  mov     [rbp+var_40], rsi
0x18006b5f7  mov     r9, rdi
0x18006b5fa  mov     r8, r12
0x18006b5fd  lea     rdx, [rbp+arg_10]
0x18006b601  mov     rcx, [rbp+arg_0]
0x18006b605  call    ?ReadStringFrom@CBasicTopLexicon@@IEBA?AV_bstr_t@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadStringFrom(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18006b60a  mov     rdi, rax
0x18006b60d  lea     rcx, [rbp+var_40]
0x18006b611  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18006b616  lea     rcx, [rax+10h]
0x18006b61a  mov     rdx, rdi
0x18006b61d  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18006b622  nop
0x18006b623  lea     rcx, [rbp+arg_10]; this
0x18006b627  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006b62c  mov     rax, [r12]
0x18006b630  mov     rcx, r12
0x18006b633  mov     rax, [rax+40h]
0x18006b637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b63c  mov     r9d, eax
0x18006b63f  mov     rax, [rbp+arg_18]
0x18006b643  mov     [rsp+78h+var_58], rax
0x18006b648  mov     r8, r12
0x18006b64b  lea     rdx, [rbp+var_20]
0x18006b64f  mov     rcx, [rbp+arg_0]
0x18006b653  call    ?ReadObjectFrom@CBasicTopLexicon@@IEBA?AV_variant_t@@AEAVByteSliceStream@@W4LexOpCode@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadObjectFrom(ByteSliceStream &,LexOpCode,CBasicTopLexicon::ReadStateData &)
0x18006b658  mov     rdi, rax
0x18006b65b  lea     rcx, [rbp+var_40]
0x18006b65f  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18006b664  lea     rcx, [rax+18h]
0x18006b668  mov     rdx, rdi
0x18006b66b  call    ??4_variant_t@@QEAAAEAV0@AEBV0@@Z; _variant_t::operator=(_variant_t const &)
0x18006b670  nop
0x18006b671  lea     rcx, [rbp+var_20]; this
0x18006b675  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006b67a  cmp     qword ptr [r14], 0
0x18006b67e  jnz     short loc_18006B690
0x18006b680  test    rsi, rsi
0x18006b683  jz      short loc_18006B690
0x18006b685  mov     [r14], rsi
0x18006b688  mov     rcx, r14
0x18006b68b  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18006b690  test    rbx, rbx
0x18006b693  jz      short loc_18006B6C6
0x18006b695  lea     rcx, [rbp+var_38]
0x18006b699  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18006b69e  lea     rcx, [rax+30h]
0x18006b6a2  mov     rdi, [rcx]
0x18006b6a5  cmp     rdi, rsi
0x18006b6a8  jz      short loc_18006B6C6
0x18006b6aa  mov     [rcx], rsi
0x18006b6ad  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18006b6b2  test    rdi, rdi
0x18006b6b5  jz      short loc_18006B6C6
0x18006b6b7  mov     rax, [rdi]
0x18006b6ba  mov     rcx, rdi
0x18006b6bd  mov     rax, [rax+10h]
0x18006b6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6c6  cmp     rbx, rsi
0x18006b6c9  jz      short loc_18006B6F2
0x18006b6cb  mov     rdi, rbx
0x18006b6ce  mov     rbx, rsi
0x18006b6d1  mov     [rbp+var_38], rbx
0x18006b6d5  lea     rcx, [rbp+var_38]
0x18006b6d9  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x18006b6de  test    rdi, rdi
0x18006b6e1  jz      short loc_18006B6F2
0x18006b6e3  mov     rax, [rdi]
0x18006b6e6  mov     rcx, rdi
0x18006b6e9  mov     rax, [rax+10h]
0x18006b6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6f2  inc     r15d
0x18006b6f5  cmp     r15d, r13d
0x18006b6f8  mov     rdi, [rbp+arg_18]
0x18006b6fc  jl      loc_18006B5C8
0x18006b702  lea     rcx, [rbp+var_38]
0x18006b706  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18006b70b  nop
0x18006b70c  lea     rcx, [rbp+var_40]
0x18006b710  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18006b715  mov     rax, r14
0x18006b718  add     rsp, 78h
0x18006b71c  pop     r15
0x18006b71e  pop     r14
0x18006b720  pop     r13
0x18006b722  pop     r12
0x18006b724  pop     rdi
0x18006b725  pop     rsi
0x18006b726  pop     rbx
0x18006b727  pop     rbp
0x18006b728  retn
```
