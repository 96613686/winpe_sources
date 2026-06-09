# parquet::Comparator::Make(parquet::Type::type,parquet::SortOrder::type,int)

- ea: `0x180080c30`
- end: `0x1800812c4`
- name: `?Make@Comparator@parquet@@SA?AV?$shared_ptr@VComparator@parquet@@@std@@W4type@Type@2@W45SortOrder@2@H@Z`
- size: `1684`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180080b30`

## callees

- `0x18001d210`
- `0x180035cd0`
- `0x180050ea0`
- `0x180080c30`
- `0x1802f0fb0`
- `0x18030c3f0`
- `0x18032b080`

## string_xrefs

- `0x180081284`: `Signed Compare not implemented`
- `0x180081244`: `Unsigned Compare not implemented`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall parquet::Comparator::Make(__int64 *a1, int a2, int a3, int a4)
{
  _DWORD *v6; // rax
  _DWORD *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rcx
  _DWORD *v11; // rax
  __int64 v12; // rcx
  void **v13; // rax
  __int64 v14; // rcx
  _DWORD *v15; // rax
  _DWORD *v16; // rax
  _DWORD *v17; // rax
  _DWORD *v18; // rax
  _DWORD *v19; // rax
  _DWORD *v20; // rax
  __int64 v21; // rcx
  void **v22; // rax
  __int64 v23; // rcx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  _DWORD *v28; // rax
  _DWORD *v29; // rax
  _DWORD *v30; // rax
  _DWORD *v31; // rax
  _DWORD *v32; // rax
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-48h] BYREF

  if ( !a3 )
  {
    switch ( a2 )
    {
      case 0:
        v6 = operator new(0x30u);
        v7 = v6;
        v8 = 0;
        if ( v6 )
        {
          v6[2] = 1;
          v6[3] = 1;
          *(_QWORD *)v6 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<0>>>::`vftable';
          *((_QWORD *)v6 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<0>>::`vbtable';
          *((_QWORD *)v6 + 5) = &parquet::TypedComparator<parquet::PhysicalType<0>>::`vftable';
          *(_QWORD *)((char *)v6 + *(int *)(*((_QWORD *)v6 + 2) + 4LL) + 16) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<0>>::`vftable';
          v9 = *(int *)(*((_QWORD *)v6 + 2) + 4LL);
          *(_DWORD *)((char *)v6 + v9 + 12) = v9 - 24;
          v6[6] = -1;
        }
        else
        {
          v7 = 0;
        }
        *a1 = 0;
        a1[1] = 0;
        if ( v7 != (_DWORD *)-16LL )
          v8 = (__int64)v7 + *(int *)(*((_QWORD *)v7 + 2) + 4LL) + 16;
        goto LABEL_8;
      case 1:
        v11 = operator new(0x30u);
        v7 = v11;
        v8 = 0;
        if ( !v11 )
          goto LABEL_12;
        v11[2] = 1;
        v11[3] = 1;
        *(_QWORD *)v11 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<1>>>::`vftable';
        *((_QWORD *)v11 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<1>>::`vbtable';
        *((_QWORD *)v11 + 5) = &parquet::TypedComparator<parquet::PhysicalType<1>>::`vftable';
        v12 = *(int *)(*((_QWORD *)v11 + 2) + 4LL);
        v13 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<1>>::`vftable';
        goto LABEL_11;
      case 2:
        v15 = operator new(0x30u);
        v7 = v15;
        v8 = 0;
        if ( !v15 )
          goto LABEL_12;
        v15[2] = 1;
        v15[3] = 1;
        *(_QWORD *)v15 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<2>>>::`vftable';
        *((_QWORD *)v15 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<2>>::`vbtable';
        *((_QWORD *)v15 + 5) = &parquet::TypedComparator<parquet::PhysicalType<2>>::`vftable';
        v12 = *(int *)(*((_QWORD *)v15 + 2) + 4LL);
        v13 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<2>>::`vftable';
        goto LABEL_11;
      case 3:
        v16 = operator new(0x30u);
        v7 = v16;
        v8 = 0;
        if ( !v16 )
          goto LABEL_12;
        v16[2] = 1;
        v16[3] = 1;
        *(_QWORD *)v16 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<3>>>::`vftable';
        *((_QWORD *)v16 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<3>>::`vbtable';
        *((_QWORD *)v16 + 5) = &parquet::TypedComparator<parquet::PhysicalType<3>>::`vftable';
        v12 = *(int *)(*((_QWORD *)v16 + 2) + 4LL);
        v13 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<3>>::`vftable';
        goto LABEL_11;
      case 4:
        v17 = operator new(0x30u);
        v7 = v17;
        v8 = 0;
        if ( !v17 )
          goto LABEL_12;
        v17[2] = 1;
        v17[3] = 1;
        *(_QWORD *)v17 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<4>>>::`vftable';
        *((_QWORD *)v17 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<4>>::`vbtable';
        *((_QWORD *)v17 + 5) = &parquet::TypedComparator<parquet::PhysicalType<4>>::`vftable';
        v12 = *(int *)(*((_QWORD *)v17 + 2) + 4LL);
        v13 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<4>>::`vftable';
        goto LABEL_11;
      case 5:
        v18 = operator new(0x30u);
        v7 = v18;
        v8 = 0;
        if ( !v18 )
          goto LABEL_12;
        v18[2] = 1;
        v18[3] = 1;
        *(_QWORD *)v18 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<5>>>::`vftable';
        *((_QWORD *)v18 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<5>>::`vbtable';
        *((_QWORD *)v18 + 5) = &parquet::TypedComparator<parquet::PhysicalType<5>>::`vftable';
        v12 = *(int *)(*((_QWORD *)v18 + 2) + 4LL);
        v13 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<5>>::`vftable';
        goto LABEL_11;
      case 6:
        v19 = operator new(0x30u);
        v7 = v19;
        v8 = 0;
        if ( !v19 )
          goto LABEL_12;
        v19[2] = 1;
        v19[3] = 1;
        *(_QWORD *)v19 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<6>>>::`vftable';
        *((_QWORD *)v19 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<6>>::`vbtable';
        *((_QWORD *)v19 + 5) = &parquet::TypedComparator<parquet::PhysicalType<6>>::`vftable';
        v12 = *(int *)(*((_QWORD *)v19 + 2) + 4LL);
        v13 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<6>>::`vftable';
        goto LABEL_11;
      case 7:
        v20 = operator new(0x30u);
        v7 = v20;
        v8 = 0;
        if ( !v20 )
          goto LABEL_12;
        v20[2] = 1;
        v20[3] = 1;
        *(_QWORD *)v20 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<7>>>::`vftable';
        *((_QWORD *)v20 + 2) = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<7>>::`vbtable';
        *((_QWORD *)v20 + 5) = &parquet::TypedComparator<parquet::PhysicalType<7>>::`vftable';
        v21 = *(int *)(*((_QWORD *)v20 + 2) + 4LL);
        v22 = &parquet::TypedComparatorImpl<1,parquet::PhysicalType<7>>::`vftable';
        goto LABEL_27;
      default:
        std::string::string(pExceptionObject, "Signed Compare not implemented");
        parquet::ParquetException::NYI(pExceptionObject);
    }
  }
  if ( a3 != 1 )
  {
    parquet::ParquetException::ParquetException((parquet::ParquetException *)pExceptionObject, "UNKNOWN Sort Order");
    throw (parquet::ParquetException *)pExceptionObject;
  }
  v24 = a2 - 1;
  if ( !v24 )
  {
    v32 = operator new(0x30u);
    v7 = v32;
    v8 = 0;
    if ( v32 )
    {
      v32[2] = 1;
      v32[3] = 1;
      *(_QWORD *)v32 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<1>>>::`vftable';
      *((_QWORD *)v32 + 2) = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<1>>::`vbtable';
      *((_QWORD *)v32 + 5) = &parquet::TypedComparator<parquet::PhysicalType<1>>::`vftable';
      v12 = *(int *)(*((_QWORD *)v32 + 2) + 4LL);
      v13 = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<1>>::`vftable';
      goto LABEL_11;
    }
    goto LABEL_12;
  }
  v25 = v24 - 1;
  if ( !v25 )
  {
    v31 = operator new(0x30u);
    v7 = v31;
    v8 = 0;
    if ( v31 )
    {
      v31[2] = 1;
      v31[3] = 1;
      *(_QWORD *)v31 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<2>>>::`vftable';
      *((_QWORD *)v31 + 2) = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<2>>::`vbtable';
      *((_QWORD *)v31 + 5) = &parquet::TypedComparator<parquet::PhysicalType<2>>::`vftable';
      v12 = *(int *)(*((_QWORD *)v31 + 2) + 4LL);
      v13 = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<2>>::`vftable';
      goto LABEL_11;
    }
    goto LABEL_12;
  }
  v26 = v25 - 1;
  if ( !v26 )
  {
    v30 = operator new(0x30u);
    v7 = v30;
    v8 = 0;
    if ( v30 )
    {
      v30[2] = 1;
      v30[3] = 1;
      *(_QWORD *)v30 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<3>>>::`vftable';
      *((_QWORD *)v30 + 2) = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<3>>::`vbtable';
      *((_QWORD *)v30 + 5) = &parquet::TypedComparator<parquet::PhysicalType<3>>::`vftable';
      v12 = *(int *)(*((_QWORD *)v30 + 2) + 4LL);
      v13 = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<3>>::`vftable';
      goto LABEL_11;
    }
LABEL_12:
    v7 = 0;
    goto LABEL_13;
  }
  v27 = v26 - 3;
  if ( !v27 )
  {
    v29 = operator new(0x30u);
    v7 = v29;
    v8 = 0;
    if ( v29 )
    {
      v29[2] = 1;
      v29[3] = 1;
      *(_QWORD *)v29 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<6>>>::`vftable';
      *((_QWORD *)v29 + 2) = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<6>>::`vbtable';
      *((_QWORD *)v29 + 5) = &parquet::TypedComparator<parquet::PhysicalType<6>>::`vftable';
      v12 = *(int *)(*((_QWORD *)v29 + 2) + 4LL);
      v13 = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<6>>::`vftable';
LABEL_11:
      *(_QWORD *)((char *)v7 + v12 + 16) = v13;
      v14 = *(int *)(*((_QWORD *)v7 + 2) + 4LL);
      *(_DWORD *)((char *)v7 + v14 + 12) = v14 - 24;
      v7[6] = -1;
      goto LABEL_13;
    }
    goto LABEL_12;
  }
  if ( v27 != 1 )
  {
    std::string::string(pExceptionObject, "Unsigned Compare not implemented");
    parquet::ParquetException::NYI(pExceptionObject);
  }
  v28 = operator new(0x30u);
  v7 = v28;
  v8 = 0;
  if ( !v28 )
    goto LABEL_12;
  v28[2] = 1;
  v28[3] = 1;
  *(_QWORD *)v28 = &std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<7>>>::`vftable';
  *((_QWORD *)v28 + 2) = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<7>>::`vbtable';
  *((_QWORD *)v28 + 5) = &parquet::TypedComparator<parquet::PhysicalType<7>>::`vftable';
  v21 = *(int *)(*((_QWORD *)v28 + 2) + 4LL);
  v22 = &parquet::TypedComparatorImpl<0,parquet::PhysicalType<7>>::`vftable';
LABEL_27:
  *(_QWORD *)((char *)v7 + v21 + 16) = v22;
  v23 = *(int *)(*((_QWORD *)v7 + 2) + 4LL);
  *(_DWORD *)((char *)v7 + v23 + 12) = v23 - 24;
  v7[6] = a4;
LABEL_13:
  *a1 = 0;
  a1[1] = 0;
  if ( v7 != (_DWORD *)-16LL )
    v8 = (__int64)v7 + *(int *)(*((_QWORD *)v7 + 2) + 4LL) + 16;
LABEL_8:
  *a1 = v8;
  a1[1] = (__int64)v7;
  return a1;
}

```

## disassembly

```asm
0x180080c30  push    rdi
0x180080c32  sub     rsp, 70h
0x180080c36  mov     [rsp+78h+var_50], 0FFFFFFFFFFFFFFFEh
0x180080c3f  mov     [rsp+78h+arg_8], rbx
0x180080c47  mov     rax, cs:__security_cookie
0x180080c4e  xor     rax, rsp
0x180080c51  mov     [rsp+78h+var_10], rax
0x180080c56  mov     edi, r9d
0x180080c59  mov     rbx, rcx
0x180080c5c  mov     [rsp+78h+var_58], rcx
0x180080c61  test    r8d, r8d
0x180080c64  jnz     loc_180081032
0x180080c6a  cmp     edx, 7; switch 8 cases
0x180080c6d  ja      def_180080C87; jumptable 0000000180080C87 default case
0x180080c73  movsxd  rax, edx
0x180080c76  lea     rdx, cs:180000000h
0x180080c7d  mov     ecx, ds:(jpt_180080C87 - 180000000h)[rdx+rax*4]
0x180080c84  add     rcx, rdx
0x180080c87  jmp     rcx; switch jump
0x180080c89  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 0
0x180080c8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080c93  mov     r9, rax
0x180080c96  mov     [rsp+78h+var_58], rax
0x180080c9b  xor     r8d, r8d
0x180080c9e  test    rax, rax
0x180080ca1  jz      short loc_180080CFF
0x180080ca3  mov     dword ptr [rax+8], 1
0x180080caa  mov     dword ptr [rax+0Ch], 1
0x180080cb1  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$0A@@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<0>>>::`vftable'
0x180080cb8  mov     [r9], rax
0x180080cbb  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$0A@@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<0>>::`vbtable'
0x180080cc2  mov     [r9+10h], rax
0x180080cc6  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$0A@@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<0>>::`vftable'
0x180080ccd  mov     [r9+28h], rax
0x180080cd1  mov     rax, [r9+10h]
0x180080cd5  movsxd  rcx, dword ptr [rax+4]
0x180080cd9  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$0A@@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<0>>::`vftable'
0x180080ce0  mov     [rcx+r9+10h], rax
0x180080ce5  mov     rax, [r9+10h]
0x180080ce9  movsxd  rcx, dword ptr [rax+4]
0x180080ced  lea     edx, [rcx-18h]
0x180080cf0  mov     [rcx+r9+0Ch], edx
0x180080cf5  mov     dword ptr [r9+18h], 0FFFFFFFFh
0x180080cfd  jmp     short loc_180080D02
0x180080cff  mov     r9, r8
0x180080d02  lea     rax, [r9+10h]
0x180080d06  mov     [rbx], r8
0x180080d09  mov     [rbx+8], r8
0x180080d0d  test    rax, rax
0x180080d10  jz      short loc_180080D1C
0x180080d12  mov     rcx, [rax]
0x180080d15  movsxd  r8, dword ptr [rcx+4]
0x180080d19  add     r8, rax
0x180080d1c  mov     [rbx], r8
0x180080d1f  mov     [rbx+8], r9
0x180080d23  mov     rax, rbx
0x180080d26  mov     rcx, [rsp+78h+var_10]
0x180080d2b  xor     rcx, rsp; StackCookie
0x180080d2e  call    __security_check_cookie
0x180080d33  mov     rbx, [rsp+78h+arg_8]
0x180080d3b  add     rsp, 70h
0x180080d3f  pop     rdi
0x180080d40  retn
0x180080d41  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 1
0x180080d46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080d4b  mov     r9, rax
0x180080d4e  mov     [rsp+78h+var_58], rax
0x180080d53  xor     r8d, r8d
0x180080d56  test    rax, rax
0x180080d59  jz      short loc_180080DB7
0x180080d5b  mov     dword ptr [rax+8], 1
0x180080d62  mov     dword ptr [rax+0Ch], 1
0x180080d69  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$00@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<1>>>::`vftable'
0x180080d70  mov     [r9], rax
0x180080d73  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$00@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<1>>::`vbtable'
0x180080d7a  mov     [r9+10h], rax
0x180080d7e  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$00@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<1>>::`vftable'
0x180080d85  mov     [r9+28h], rax
0x180080d89  mov     rax, [r9+10h]
0x180080d8d  movsxd  rcx, dword ptr [rax+4]
0x180080d91  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$00@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<1>>::`vftable'
0x180080d98  mov     [rcx+r9+10h], rax
0x180080d9d  mov     rax, [r9+10h]
0x180080da1  movsxd  rcx, dword ptr [rax+4]
0x180080da5  lea     edx, [rcx-18h]
0x180080da8  mov     [rcx+r9+0Ch], edx
0x180080dad  mov     dword ptr [r9+18h], 0FFFFFFFFh
0x180080db5  jmp     short loc_180080DBA
0x180080db7  mov     r9, r8
0x180080dba  lea     rcx, [r9+10h]
0x180080dbe  mov     [rbx], r8
0x180080dc1  mov     [rbx+8], r8
0x180080dc5  test    rcx, rcx
0x180080dc8  jz      loc_180080D1C
0x180080dce  mov     rax, [rcx]
0x180080dd1  movsxd  r8, dword ptr [rax+4]
0x180080dd5  add     r8, rcx
0x180080dd8  jmp     loc_180080D1C
0x180080ddd  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 2
0x180080de2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080de7  mov     r9, rax
0x180080dea  mov     [rsp+78h+var_58], rax
0x180080def  xor     r8d, r8d
0x180080df2  test    rax, rax
0x180080df5  jz      short loc_180080DB7
0x180080df7  mov     dword ptr [rax+8], 1
0x180080dfe  mov     dword ptr [rax+0Ch], 1
0x180080e05  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$01@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<2>>>::`vftable'
0x180080e0c  mov     [r9], rax
0x180080e0f  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$01@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<2>>::`vbtable'
0x180080e16  mov     [r9+10h], rax
0x180080e1a  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$01@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<2>>::`vftable'
0x180080e21  mov     [r9+28h], rax
0x180080e25  mov     rax, [r9+10h]
0x180080e29  movsxd  rcx, dword ptr [rax+4]
0x180080e2d  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$01@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<2>>::`vftable'
0x180080e34  jmp     loc_180080D98
0x180080e39  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 3
0x180080e3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080e43  mov     r9, rax
0x180080e46  mov     [rsp+78h+var_58], rax
0x180080e4b  xor     r8d, r8d
0x180080e4e  test    rax, rax
0x180080e51  jz      loc_180080DB7
0x180080e57  mov     dword ptr [rax+8], 1
0x180080e5e  mov     dword ptr [rax+0Ch], 1
0x180080e65  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$02@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<3>>>::`vftable'
0x180080e6c  mov     [r9], rax
0x180080e6f  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$02@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<3>>::`vbtable'
0x180080e76  mov     [r9+10h], rax
0x180080e7a  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$02@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<3>>::`vftable'
0x180080e81  mov     [r9+28h], rax
0x180080e85  mov     rax, [r9+10h]
0x180080e89  movsxd  rcx, dword ptr [rax+4]
0x180080e8d  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$02@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<3>>::`vftable'
0x180080e94  jmp     loc_180080D98
0x180080e99  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 4
0x180080e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080ea3  mov     r9, rax
0x180080ea6  mov     [rsp+78h+var_58], rax
0x180080eab  xor     r8d, r8d
0x180080eae  test    rax, rax
0x180080eb1  jz      loc_180080DB7
0x180080eb7  mov     dword ptr [rax+8], 1
0x180080ebe  mov     dword ptr [rax+0Ch], 1
0x180080ec5  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$03@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<4>>>::`vftable'
0x180080ecc  mov     [r9], rax
0x180080ecf  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$03@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<4>>::`vbtable'
0x180080ed6  mov     [r9+10h], rax
0x180080eda  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$03@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<4>>::`vftable'
0x180080ee1  mov     [r9+28h], rax
0x180080ee5  mov     rax, [r9+10h]
0x180080ee9  movsxd  rcx, dword ptr [rax+4]
0x180080eed  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$03@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<4>>::`vftable'
0x180080ef4  jmp     loc_180080D98
0x180080ef9  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 5
0x180080efe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080f03  mov     r9, rax
0x180080f06  mov     [rsp+78h+var_58], rax
0x180080f0b  xor     r8d, r8d
0x180080f0e  test    rax, rax
0x180080f11  jz      loc_180080DB7
0x180080f17  mov     dword ptr [rax+8], 1
0x180080f1e  mov     dword ptr [rax+0Ch], 1
0x180080f25  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$04@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<5>>>::`vftable'
0x180080f2c  mov     [r9], rax
0x180080f2f  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$04@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<5>>::`vbtable'
0x180080f36  mov     [r9+10h], rax
0x180080f3a  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$04@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<5>>::`vftable'
0x180080f41  mov     [r9+28h], rax
0x180080f45  mov     rax, [r9+10h]
0x180080f49  movsxd  rcx, dword ptr [rax+4]
0x180080f4d  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$04@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<5>>::`vftable'
0x180080f54  jmp     loc_180080D98
0x180080f59  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 6
0x180080f5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080f63  mov     r9, rax
0x180080f66  mov     [rsp+78h+var_58], rax
0x180080f6b  xor     r8d, r8d
0x180080f6e  test    rax, rax
0x180080f71  jz      loc_180080DB7
0x180080f77  mov     dword ptr [rax+8], 1
0x180080f7e  mov     dword ptr [rax+0Ch], 1
0x180080f85  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$05@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<6>>>::`vftable'
0x180080f8c  mov     [r9], rax
0x180080f8f  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$05@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<6>>::`vbtable'
0x180080f96  mov     [r9+10h], rax
0x180080f9a  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$05@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<6>>::`vftable'
0x180080fa1  mov     [r9+28h], rax
0x180080fa5  mov     rax, [r9+10h]
0x180080fa9  movsxd  rcx, dword ptr [rax+4]
0x180080fad  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$05@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<6>>::`vftable'
0x180080fb4  jmp     loc_180080D98
0x180080fb9  mov     ecx, 30h ; '0'; jumptable 0000000180080C87 case 7
0x180080fbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080fc3  mov     r9, rax
0x180080fc6  mov     [rsp+78h+var_58], rax
0x180080fcb  xor     r8d, r8d
0x180080fce  test    rax, rax
0x180080fd1  jz      loc_180080DB7
0x180080fd7  mov     dword ptr [rax+8], 1
0x180080fde  mov     dword ptr [rax+0Ch], 1
0x180080fe5  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$00U?$PhysicalType@$06@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<1,parquet::PhysicalType<7>>>::`vftable'
0x180080fec  mov     [r9], rax
0x180080fef  lea     rax, ??_8?$TypedComparatorImpl@$00U?$PhysicalType@$06@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<7>>::`vbtable'
0x180080ff6  mov     [r9+10h], rax
0x180080ffa  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$06@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<7>>::`vftable'
0x180081001  mov     [r9+28h], rax
0x180081005  mov     rax, [r9+10h]
0x180081009  movsxd  rcx, dword ptr [rax+4]
0x18008100d  lea     rax, ??_7?$TypedComparatorImpl@$00U?$PhysicalType@$06@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<1,parquet::PhysicalType<7>>::`vftable'
0x180081014  mov     [rcx+r9+10h], rax
0x180081019  mov     rax, [r9+10h]
0x18008101d  movsxd  rcx, dword ptr [rax+4]
0x180081021  lea     edx, [rcx-18h]
0x180081024  mov     [rcx+r9+0Ch], edx
0x180081029  mov     [r9+18h], edi
0x18008102d  jmp     loc_180080DBA
0x180081032  cmp     r8d, 1
0x180081036  jnz     loc_180081261
0x18008103c  sub     edx, r8d
0x18008103f  jz      loc_1800811E4
0x180081045  sub     edx, r8d
0x180081048  jz      loc_180081184
0x18008104e  sub     edx, r8d
0x180081051  jz      loc_180081124
0x180081057  sub     edx, 3
0x18008105a  jz      short loc_1800810C4
0x18008105c  cmp     edx, r8d
0x18008105f  jnz     loc_180081244
0x180081065  lea     ecx, [r8+2Fh]; Size
0x180081069  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008106e  mov     r9, rax
0x180081071  mov     [rsp+78h+var_58], rax
0x180081076  xor     r8d, r8d
0x180081079  test    rax, rax
0x18008107c  jz      loc_180080DB7
0x180081082  mov     dword ptr [rax+8], 1
0x180081089  mov     dword ptr [rax+0Ch], 1
0x180081090  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$0A@U?$PhysicalType@$06@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<7>>>::`vftable'
0x180081097  mov     [r9], rax
0x18008109a  lea     rax, ??_8?$TypedComparatorImpl@$0A@U?$PhysicalType@$06@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<7>>::`vbtable'
0x1800810a1  mov     [r9+10h], rax
0x1800810a5  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$06@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<7>>::`vftable'
0x1800810ac  mov     [r9+28h], rax
0x1800810b0  mov     rax, [r9+10h]
0x1800810b4  movsxd  rcx, dword ptr [rax+4]
0x1800810b8  lea     rax, ??_7?$TypedComparatorImpl@$0A@U?$PhysicalType@$06@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<7>>::`vftable'
0x1800810bf  jmp     loc_180081014
0x1800810c4  mov     ecx, 30h ; '0'; Size
0x1800810c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800810ce  mov     r9, rax
0x1800810d1  mov     [rsp+78h+var_58], rax
0x1800810d6  xor     r8d, r8d
0x1800810d9  test    rax, rax
0x1800810dc  jz      loc_180080DB7
0x1800810e2  mov     dword ptr [rax+8], 1
0x1800810e9  mov     dword ptr [rax+0Ch], 1
0x1800810f0  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$0A@U?$PhysicalType@$05@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<6>>>::`vftable'
0x1800810f7  mov     [r9], rax
0x1800810fa  lea     rax, ??_8?$TypedComparatorImpl@$0A@U?$PhysicalType@$05@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<6>>::`vbtable'
0x180081101  mov     [r9+10h], rax
0x180081105  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$05@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<6>>::`vftable'
0x18008110c  mov     [r9+28h], rax
0x180081110  mov     rax, [r9+10h]
0x180081114  movsxd  rcx, dword ptr [rax+4]
0x180081118  lea     rax, ??_7?$TypedComparatorImpl@$0A@U?$PhysicalType@$05@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<6>>::`vftable'
0x18008111f  jmp     loc_180080D98
0x180081124  mov     ecx, 30h ; '0'; Size
0x180081129  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008112e  mov     r9, rax
0x180081131  mov     [rsp+78h+var_58], rax
0x180081136  xor     r8d, r8d
0x180081139  test    rax, rax
0x18008113c  jz      loc_180080DB7
0x180081142  mov     dword ptr [rax+8], 1
0x180081149  mov     dword ptr [rax+0Ch], 1
0x180081150  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$0A@U?$PhysicalType@$02@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<3>>>::`vftable'
0x180081157  mov     [r9], rax
0x18008115a  lea     rax, ??_8?$TypedComparatorImpl@$0A@U?$PhysicalType@$02@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<3>>::`vbtable'
0x180081161  mov     [r9+10h], rax
0x180081165  lea     rax, ??_7?$TypedComparator@U?$PhysicalType@$02@parquet@@@parquet@@6B@; const parquet::TypedComparator<parquet::PhysicalType<3>>::`vftable'
0x18008116c  mov     [r9+28h], rax
0x180081170  mov     rax, [r9+10h]
0x180081174  movsxd  rcx, dword ptr [rax+4]
0x180081178  lea     rax, ??_7?$TypedComparatorImpl@$0A@U?$PhysicalType@$02@parquet@@@parquet@@6B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<3>>::`vftable'
0x18008117f  jmp     loc_180080D98
0x180081184  mov     ecx, 30h ; '0'; Size
0x180081189  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008118e  mov     r9, rax
0x180081191  mov     [rsp+78h+var_58], rax
0x180081196  xor     r8d, r8d
0x180081199  test    rax, rax
0x18008119c  jz      loc_180080DB7
0x1800811a2  mov     dword ptr [rax+8], 1
0x1800811a9  mov     dword ptr [rax+0Ch], 1
0x1800811b0  lea     rax, ??_7?$_Ref_count_obj@V?$TypedComparatorImpl@$0A@U?$PhysicalType@$01@parquet@@@parquet@@@std@@6B@; const std::_Ref_count_obj<parquet::TypedComparatorImpl<0,parquet::PhysicalType<2>>>::`vftable'
0x1800811b7  mov     [r9], rax
0x1800811ba  lea     rax, ??_8?$TypedComparatorImpl@$0A@U?$PhysicalType@$01@parquet@@@parquet@@7B@; const parquet::TypedComparatorImpl<0,parquet::PhysicalType<2>>::`vbtable'
0x1800811c1  mov     [r9+10h], rax
  ... truncated ...
```
