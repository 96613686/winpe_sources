# CBasicTopLexicon::ReadObjectFrom(ByteSliceStream &,LexOpCode,CBasicTopLexicon::ReadStateData &)

- ea: `0x18003b120`
- end: `0x18003b2c6`
- name: `?ReadObjectFrom@CBasicTopLexicon@@IEBA?AV_variant_t@@AEAVByteSliceStream@@W4LexOpCode@@AEAUReadStateData@1@@Z`
- size: `422`
- prototype: `struct _variant_t __high(struct ByteSliceStream *, enum LexOpCode, struct CBasicTopLexicon::ReadStateData *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18006b554`

## callees

- `0x180005160`
- `0x18001a0d8`
- `0x18002cea0`
- `0x180030c5c`
- `0x180035640`
- `0x18003b120`
- `0x18003b2cc`
- `0x18003ed6c`
- `0x18006b1d4`
- `0x18006b38c`
- `0x18006b554`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_WORD *__fastcall CBasicTopLexicon::ReadObjectFrom(__int64 a1, _WORD *a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // xmm0_8
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  int v11; // r9d
  int v12; // r9d
  __int64 *UserData; // rax
  struct IUnknown *v14; // rdx
  bool v15; // r8
  struct IUnknown **IntListFrom; // rax
  struct IUnknown *v17; // rdx
  bool v18; // r8
  struct IUnknown **StringsFrom; // rax
  struct IUnknown *v20; // rdx
  bool v21; // r8
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  unsigned int v24; // edx
  volatile signed __int32 *v26[2]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+38h] [rbp-48h] BYREF
  const void *retaddr; // [rsp+88h] [rbp+8h]

  v26[1] = (volatile signed __int32 *)-2LL;
  v7 = a4 - 30;
  if ( !v7 )
  {
    *a2 = 11;
    a2[4] = -1;
    return a2;
  }
  v8 = v7 - 3;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 40LL))(a3);
      *a2 = 3;
      *((_DWORD *)a2 + 2) = v22;
      return a2;
    }
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 3;
        if ( v12 )
        {
          if ( v12 != 1 )
          {
            CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
            throw (CNLException *)pExceptionObject;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 56LL))(a3);
          *a2 = 5;
          *((_QWORD *)a2 + 1) = v5;
          return a2;
        }
        UserData = CBasicTopLexicon::ReadUserData(a1, (__int64 *)v26, a3, a5);
        v14 = (struct IUnknown *)*UserData;
        *UserData = 0;
        _variant_t::_variant_t((_variant_t *)a2, v14, v15);
      }
      else
      {
        IntListFrom = (struct IUnknown **)CBasicTopLexicon::ReadIntListFrom(a1, v26);
        v17 = *IntListFrom;
        *IntListFrom = 0;
        _variant_t::_variant_t((_variant_t *)a2, v17, v18);
      }
    }
    else
    {
      StringsFrom = (struct IUnknown **)CBasicTopLexicon::ReadStringsFrom(a1, v26, a3, a5, 0);
      v20 = *StringsFrom;
      *StringsFrom = 0;
      _variant_t::_variant_t((_variant_t *)a2, v20, v21);
    }
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)v26);
    return a2;
  }
  v23 = *(const unsigned __int16 **)CBasicTopLexicon::ReadStringFrom(a1, v26, a3, a5);
  if ( v23 )
    v23 = *(const unsigned __int16 **)v23;
  _variant_t::_variant_t((_variant_t *)a2, v23);
  _bstr_t::_Free(v26, v24);
  return a2;
}

```

## disassembly

```asm
0x18003b120  mov     rax, rsp
0x18003b123  mov     [rax+10h], rdx
0x18003b127  push    rbp
0x18003b128  mov     rbp, rsp
0x18003b12b  sub     rsp, 80h
0x18003b132  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18003b13a  mov     [rax+8], rbx
0x18003b13e  mov     [rax+18h], rsi
0x18003b142  mov     rbx, rdx
0x18003b145  mov     [rbp+var_60], 0
0x18003b14c  sub     r9d, 1Eh
0x18003b150  jz      loc_18003B29B
0x18003b156  mov     esi, 3
0x18003b15b  sub     r9d, esi
0x18003b15e  jz      loc_18003B268
0x18003b164  sub     r9d, 1
0x18003b168  jz      loc_18003B251
0x18003b16e  sub     r9d, 1
0x18003b172  jz      loc_18003B228
0x18003b178  sub     r9d, 1
0x18003b17c  jz      loc_18003B203
0x18003b182  sub     r9d, esi
0x18003b185  jz      short loc_18003B1CE
0x18003b187  cmp     r9d, 1
0x18003b18b  jz      short loc_18003B1B0
0x18003b18d  mov     r8, [rbp+8]; void *
0x18003b191  mov     edx, 80004005h; int
0x18003b196  lea     rcx, [rbp+pExceptionObject]; this
0x18003b19a  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003b19f  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003b1a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003b1aa  call    _CxxThrowException_0
0x18003b1b0  mov     rax, [r8]
0x18003b1b3  mov     rcx, r8
0x18003b1b6  mov     rax, [rax+38h]
0x18003b1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1bf  mov     word ptr [rbx], 5
0x18003b1c4  movsd   qword ptr [rbx+8], xmm0
0x18003b1c9  jmp     loc_18003B2A6
0x18003b1ce  mov     r9, [rbp+arg_20]
0x18003b1d2  lea     rdx, [rbp+var_58]
0x18003b1d6  call    ?ReadUserData@CBasicTopLexicon@@IEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadUserData(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18003b1db  nop
0x18003b1dc  mov     rdx, [rax]; struct IUnknown *
0x18003b1df  mov     qword ptr [rax], 0
0x18003b1e6  mov     rcx, rbx; this
0x18003b1e9  call    ??0_variant_t@@QEAA@PEAUIUnknown@@_N@Z; _variant_t::_variant_t(IUnknown *,bool)
0x18003b1ee  mov     [rbp+var_60], 1
0x18003b1f5  lea     rcx, [rbp+var_58]
0x18003b1f9  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x18003b1fe  jmp     loc_18003B2AD
0x18003b203  lea     rdx, [rbp+var_58]
0x18003b207  call    ?ReadIntListFrom@CBasicTopLexicon@@IEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadIntListFrom(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18003b20c  nop
0x18003b20d  mov     rdx, [rax]; struct IUnknown *
0x18003b210  mov     qword ptr [rax], 0
0x18003b217  mov     rcx, rbx; this
0x18003b21a  call    ??0_variant_t@@QEAA@PEAUIUnknown@@_N@Z; _variant_t::_variant_t(IUnknown *,bool)
0x18003b21f  mov     [rbp+var_60], 1
0x18003b226  jmp     short loc_18003B1F5
0x18003b228  mov     r9, [rbp+arg_20]
0x18003b22c  lea     rdx, [rbp+var_58]
0x18003b230  call    ?ReadStringsFrom@CBasicTopLexicon@@IEBA?AV?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadStringsFrom(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18003b235  nop
0x18003b236  mov     rdx, [rax]; struct IUnknown *
0x18003b239  mov     qword ptr [rax], 0
0x18003b240  mov     rcx, rbx; this
0x18003b243  call    ??0_variant_t@@QEAA@PEAUIUnknown@@_N@Z; _variant_t::_variant_t(IUnknown *,bool)
0x18003b248  mov     [rbp+var_60], 1
0x18003b24f  jmp     short loc_18003B1F5
0x18003b251  mov     rax, [r8]
0x18003b254  mov     rcx, r8
0x18003b257  mov     rax, [rax+28h]
0x18003b25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b260  mov     [rbx], si
0x18003b263  mov     [rbx+8], eax
0x18003b266  jmp     short loc_18003B2A6
0x18003b268  mov     r9, [rbp+arg_20]
0x18003b26c  lea     rdx, [rbp+var_58]
0x18003b270  call    ?ReadStringFrom@CBasicTopLexicon@@IEBA?AV_bstr_t@@AEAVByteSliceStream@@AEAUReadStateData@1@@Z; CBasicTopLexicon::ReadStringFrom(ByteSliceStream &,CBasicTopLexicon::ReadStateData &)
0x18003b275  nop
0x18003b276  mov     rdx, [rax]
0x18003b279  test    rdx, rdx
0x18003b27c  jz      short loc_18003B281
0x18003b27e  mov     rdx, [rdx]; unsigned __int16 *
0x18003b281  mov     rcx, rbx; this
0x18003b284  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18003b289  mov     [rbp+var_60], 1
0x18003b290  lea     rcx, [rbp+var_58]; this
0x18003b294  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003b299  jmp     short loc_18003B2AD
0x18003b29b  mov     word ptr [rdx], 0Bh
0x18003b2a0  mov     word ptr [rdx+8], 0FFFFh
0x18003b2a6  mov     [rbp+var_60], 1
0x18003b2ad  mov     rax, rbx
0x18003b2b0  lea     r11, [rsp+80h+var_s0]
0x18003b2b8  mov     rbx, [r11+10h]
0x18003b2bc  mov     rsi, [r11+20h]
0x18003b2c0  mov     rsp, r11
0x18003b2c3  pop     rbp
0x18003b2c4  retn
```
