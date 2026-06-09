# CMicrodomBuilder::ProduceStringTable(_LBLOB *)

- ea: `0x180015b30`
- end: `0x180015f6d`
- name: `?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z`
- size: `1085`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800148d4`

## callees

- `0x180009820`
- `0x180015b30`
- `0x180015f74`
- `0x18001ad3c`
- `0x18001f840`
- `0x1800217cc`
- `0x180026e18`
- `0x18002d2b0`
- `0x180062944`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180015ddf`
- `ntdll!RtlRaiseStatus` at `0x180015ddf`

## string_xrefs

- `0x180015df5`: `onecore\base\xml\udom_builder.cpp`
- `0x180015e70`: `onecore\base\xml\udom_builder.cpp`
- `0x180015ec5`: `onecore\base\xml\udom_builder.cpp`
- `0x180015f25`: `onecore\base\xml\udom_builder.cpp`
- `0x180015eeb`: `BUCL::Rtl::QuickSort(Pairs, CompareStringSlot)`
- `0x180015f4b`: `BUCL::Rtl::ConvertInteger( ((ULONG_PTR)pvWriteCursor) - ((ULONG_PTR)pHeader), pHeader->TotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ProduceStringTable(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  _QWORD *v2; // rax
  _QWORD *v4; // rdx
  _QWORD *v5; // rdi
  _QWORD *v6; // rbx
  unsigned __int64 v7; // rsi
  _QWORD *v8; // r15
  unsigned __int64 v9; // r13
  __int64 Elements; // rax
  _QWORD *v11; // r9
  __int64 v12; // r8
  _QWORD *i; // rcx
  __int64 v14; // rcx
  char *v15; // rdx
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // r9
  _QWORD *j; // rcx
  char *v20; // r14
  __int64 v21; // r12
  unsigned __int64 v22; // rbx
  char *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // rax
  struct _LBLOB *v26; // rdx
  int v27; // eax
  unsigned __int64 v28; // rbx
  int v29; // eax
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // r8
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned __int64 v36; // [rsp+20h] [rbp-50h] BYREF
  const char *v37; // [rsp+28h] [rbp-48h] BYREF
  const char *v38; // [rsp+30h] [rbp-40h]
  __int64 v39; // [rsp+38h] [rbp-38h]
  const char *v40; // [rsp+40h] [rbp-30h]
  __int64 v41; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v42; // [rsp+50h] [rbp-20h]
  struct _LBLOB *v43; // [rsp+58h] [rbp-18h]
  int v44; // [rsp+60h] [rbp-10h] BYREF

  v2 = (_QWORD *)*((_QWORD *)this + 2);
  v43 = a2;
  v4 = &v2[4 * *((_QWORD *)this + 4)];
  v44 = 0;
  while ( 1 )
  {
    v5 = 0;
    v6 = 0;
    if ( v2 >= v4 )
      break;
    v5 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 != v2 )
    {
      v6 = v2;
      break;
    }
    v2 += 4;
  }
  v7 = *((_QWORD *)this + 5);
  v8 = 0;
  v9 = 0;
  v41 = 0;
  v42 = 0;
  if ( v7 )
  {
    Elements = Windows::VectorTraits<CMicrodomBuilder::StringTablePair>::AllocateElements(v7);
    if ( !Elements )
    {
      v39 = 454;
      v37 = "onecore\\base\\xml\\udom_builder.cpp";
      v38 = "CMicrodomBuilder::ProduceStringTable";
      v40 = "Pairs.Allocate(m_StringTable.GetEntryCount())";
      v33 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
              &v44,
              &v37);
      Windows::Auto<Windows::Vector<_LUTF8_STRING>>::~Auto<Windows::Vector<_LUTF8_STRING>>(&v41);
      return v33;
    }
    v8 = (_QWORD *)Elements;
    v41 = Elements;
    v9 = v7;
    v42 = v7;
  }
  v11 = (_QWORD *)*((_QWORD *)this + 2);
  v12 = 0;
  for ( i = v11; i < &v11[4 * *((_QWORD *)this + 4)]; i += 4 )
  {
    if ( (_QWORD *)*i != i )
    {
      v6 = i;
      v5 = (_QWORD *)*i;
      break;
    }
  }
  v14 = ((char *)i - (char *)v11) >> 5;
  while ( v6 )
  {
    v15 = (char *)&v8[2 * v12];
    if ( v5 == v6 )
    {
      *(_DWORD *)v15 = MEMORY[0x40];
      v16 = 0;
    }
    else
    {
      *(_DWORD *)v15 = *((_DWORD *)v5 + 16);
      v16 = v5;
    }
    *((_QWORD *)v15 + 1) = v16 + 5;
    v17 = (_QWORD *)*v5;
    v5 = v17;
    if ( v17 )
    {
      if ( v17 != v6 )
        goto LABEL_24;
      v5 = 0;
    }
    v18 = *((_QWORD *)this + 2);
    v6 = 0;
    for ( j = (_QWORD *)(v18 + 32 * (v14 + 1)); (unsigned __int64)j < v18 + 32LL * *((_QWORD *)this + 4); j += 4 )
    {
      if ( (_QWORD *)*j != j )
      {
        v6 = j;
        v5 = (_QWORD *)*j;
        break;
      }
    }
    v14 = ((__int64)j - v18) >> 5;
LABEL_24:
    ++v12;
  }
  BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,CMicrodomBuilder::StringTablePair,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &)>(
    &v36,
    v8,
    (__int64)(16 * v9) >> 4);
  if ( (v36 & 0x80000000) != 0LL )
  {
    v39 = 462;
    v37 = "onecore\\base\\xml\\udom_builder.cpp";
    v38 = "CMicrodomBuilder::ProduceStringTable";
    v40 = "BUCL::Rtl::QuickSort(Pairs, CompareStringSlot)";
    v34 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v44,
            &v37,
            (unsigned int)v36);
    Windows::Auto<Windows::Vector<_LUTF8_STRING>>::~Auto<Windows::Vector<_LUTF8_STRING>>(&v41);
    return v34;
  }
  else
  {
    v20 = (char *)(*((_QWORD *)v43 + 2) + *(_QWORD *)v43);
    v21 = *((_QWORD *)v43 + 2) + *((_QWORD *)v43 + 1);
    v22 = 0;
    v23 = v20 + 12;
    while ( v22 < v9 )
    {
      v24 = v8[2 * v22 + 1];
      if ( (unsigned __int64)(v21 - (_QWORD)v23) <= *(_QWORD *)v24 )
        goto LABEL_43;
      memmove(v23, *(const void **)(v24 + 16), *(_QWORD *)v24);
      v25 = *(_QWORD *)v8[2 * v22 + 1];
      v23[v25] = 0;
      v23 += v25 + 1;
      ++v22;
    }
    v26 = v43;
    *(_QWORD *)v43 = &v23[-*((_QWORD *)v43 + 2)];
    v27 = 0;
    v36 = 0;
    if ( v9 > 0xFFFFFFFF )
    {
      HIDWORD(v36) = -1073741675;
    }
    else
    {
      v27 = v9;
      LODWORD(v36) = v9;
      if ( v9 == (unsigned int)v9 )
        HIDWORD(v36) = 0;
      else
        HIDWORD(v36) = -1073741595;
    }
    v28 = HIDWORD(v36);
    *((_DWORD *)v20 + 2) = v27;
    if ( (v28 & 0x80000000) != 0LL )
    {
      v39 = 491;
      v37 = "onecore\\base\\xml\\udom_builder.cpp";
      v38 = "CMicrodomBuilder::ProduceStringTable";
      v40 = "BUCL::Rtl::ConvertInteger(Pairs.Length, pHeader->TotalCount)";
      RtlReportErrorOrigination(&v37, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v28);
      if ( v8 )
        operator delete(v8);
      return (unsigned int)v28;
    }
    else
    {
      v29 = 0;
      v30 = v23 - v20;
      v36 = 0;
      if ( v30 > 0xFFFFFFFF )
      {
        HIDWORD(v36) = -1073741675;
      }
      else
      {
        v29 = v30;
        LODWORD(v36) = v30;
        if ( v30 == (unsigned int)v30 )
          HIDWORD(v36) = 0;
        else
          HIDWORD(v36) = -1073741595;
      }
      v31 = HIDWORD(v36);
      *((_DWORD *)v20 + 1) = v29;
      if ( (v31 & 0x80000000) != 0LL )
      {
        v39 = 496;
        v37 = "onecore\\base\\xml\\udom_builder.cpp";
        v38 = "CMicrodomBuilder::ProduceStringTable";
        v40 = "BUCL::Rtl::ConvertInteger( ((ULONG_PTR)pvWriteCursor) - ((ULONG_PTR)pHeader), pHeader->TotalSize)";
        v35 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v44,
                &v37,
                v31);
        Windows::Auto<Windows::Vector<_LUTF8_STRING>>::~Auto<Windows::Vector<_LUTF8_STRING>>(&v41);
        return v35;
      }
      else
      {
        *(_DWORD *)v20 = 1884513357;
        if ( *(_QWORD *)v26 > *((_QWORD *)v26 + 1) )
LABEL_43:
          RtlRaiseStatus(-1073741595);
        if ( v8 )
          operator delete(v8);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180015b30  push    rbp
0x180015b32  push    rbx
0x180015b33  push    rsi
0x180015b34  push    rdi
0x180015b35  push    r13
0x180015b37  push    r14
0x180015b39  push    r15
0x180015b3b  mov     rbp, rsp
0x180015b3e  sub     rsp, 70h
0x180015b42  mov     rax, cs:__security_cookie
0x180015b49  xor     rax, rsp
0x180015b4c  mov     [rbp+var_8], rax
0x180015b50  mov     rax, [rcx+10h]
0x180015b54  mov     r14, rcx
0x180015b57  mov     [rbp+var_18], rdx
0x180015b5b  mov     rdx, [rcx+20h]
0x180015b5f  shl     rdx, 5
0x180015b63  add     rdx, rax
0x180015b66  mov     [rbp+var_10], 0
0x180015b6d  xor     edi, edi
0x180015b6f  xor     ebx, ebx
0x180015b71  cmp     rax, rdx
0x180015b74  jnb     short loc_180015B85
0x180015b76  mov     rdi, [rax]
0x180015b79  cmp     rdi, rax
0x180015b7c  jz      loc_180015C7B
0x180015b82  mov     rbx, rax
0x180015b85  mov     rsi, [rcx+28h]
0x180015b89  xor     r15d, r15d
0x180015b8c  xor     r13d, r13d
0x180015b8f  mov     [rbp+var_28], r15
0x180015b93  mov     [rbp+var_20], r13
0x180015b97  test    rsi, rsi
0x180015b9a  jz      loc_180015E66
0x180015ba0  mov     rcx, rsi
0x180015ba3  call    ?AllocateElements@?$VectorTraits@UStringTablePair@CMicrodomBuilder@@@Windows@@SAPEAUStringTablePair@CMicrodomBuilder@@_K@Z; Windows::VectorTraits<CMicrodomBuilder::StringTablePair>::AllocateElements(unsigned __int64)
0x180015ba8  test    rax, rax
0x180015bab  jz      loc_180015E70
0x180015bb1  mov     r15, rax
0x180015bb4  mov     [rbp+var_28], rax
0x180015bb8  mov     r13, rsi
0x180015bbb  mov     [rbp+var_20], rsi
0x180015bbf  test    rax, rax
0x180015bc2  jz      loc_180015E70
0x180015bc8  mov     r9, [r14+10h]
0x180015bcc  xor     r8d, r8d
0x180015bcf  mov     rax, [r14+20h]
0x180015bd3  mov     rcx, r9
0x180015bd6  shl     rax, 5
0x180015bda  add     rax, r9
0x180015bdd  cmp     rcx, rax
0x180015be0  jnb     short loc_180015BF4
0x180015be2  mov     rdx, [rcx]
0x180015be5  cmp     rdx, rcx
0x180015be8  jz      loc_180015E45
0x180015bee  mov     rbx, rcx
0x180015bf1  mov     rdi, rdx
0x180015bf4  sub     rcx, r9
0x180015bf7  sar     rcx, 5
0x180015bfb  nop     dword ptr [rax+rax+00h]
0x180015c00  test    rbx, rbx
0x180015c03  jz      short loc_180015C84
0x180015c05  mov     rax, r8
0x180015c08  add     rax, rax
0x180015c0b  lea     rdx, [r15+rax*8]
0x180015c0f  cmp     rdi, rbx
0x180015c12  jnz     loc_180015EB8
0x180015c18  mov     eax, ds:40h
0x180015c1f  mov     [rdx], eax
0x180015c21  xor     eax, eax
0x180015c23  add     rax, 28h ; '('
0x180015c27  mov     [rdx+8], rax
0x180015c2b  mov     rax, [rdi]
0x180015c2e  mov     rdi, rax
0x180015c31  test    rax, rax
0x180015c34  jz      short loc_180015C3D
0x180015c36  cmp     rax, rbx
0x180015c39  jnz     short loc_180015C76
0x180015c3b  xor     edi, edi
0x180015c3d  mov     r9, [r14+10h]
0x180015c41  xor     ebx, ebx
0x180015c43  mov     rax, [r14+20h]
0x180015c47  inc     rcx
0x180015c4a  shl     rcx, 5
0x180015c4e  add     rcx, r9
0x180015c51  shl     rax, 5
0x180015c55  add     rax, r9
0x180015c58  cmp     rcx, rax
0x180015c5b  jnb     short loc_180015C6F
0x180015c5d  mov     rdx, [rcx]
0x180015c60  cmp     rdx, rcx
0x180015c63  jz      loc_180015DEC
0x180015c69  mov     rbx, rcx
0x180015c6c  mov     rdi, rdx
0x180015c6f  sub     rcx, r9
0x180015c72  sar     rcx, 5
0x180015c76  inc     r8
0x180015c79  jmp     short loc_180015C00
0x180015c7b  add     rax, 20h ; ' '
0x180015c7f  jmp     loc_180015B6D
0x180015c84  mov     r8, r13
0x180015c87  lea     rcx, [rbp+var_50]
0x180015c8b  shl     r8, 4
0x180015c8f  mov     rdx, r15
0x180015c92  sar     r8, 4
0x180015c96  call    ??$QuickSort@VCCallDisposition@Rtl@BUCL@@_KUStringTablePair@CMicrodomBuilder@@P6A?AU?$ComparisonResultKind@VCCallDisposition@Rtl@BUCL@@@Implementation@3@AEBU45@0@Z@Implementation@BUCL@@YA?AVCCallDisposition@Rtl@1@PEAUStringTablePair@CMicrodomBuilder@@_KP6A?AU?$ComparisonResultKind@VCCallDisposition@Rtl@BUCL@@@01@AEBU45@2@Z@Z; BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,CMicrodomBuilder::StringTablePair,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &)>(CMicrodomBuilder::StringTablePair *,unsigned __int64,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &))
0x180015c9b  mov     r8d, dword ptr [rbp+var_50]
0x180015c9f  test    r8d, r8d
0x180015ca2  js      loc_180015EC5
0x180015ca8  mov     rdx, [rbp+var_18]
0x180015cac  mov     [rsp+70h+arg_10], r12
0x180015cb4  mov     r14, [rdx]
0x180015cb7  add     r14, [rdx+10h]
0x180015cbb  mov     r12, [rdx+8]
0x180015cbf  add     r12, [rdx+10h]
0x180015cc3  xor     ebx, ebx
0x180015cc5  lea     rdi, [r14+0Ch]
0x180015cc9  cmp     rbx, r13
0x180015ccc  jnb     short loc_180015D0E
0x180015cce  mov     rsi, rbx
0x180015cd1  mov     rax, r12
0x180015cd4  add     rsi, rsi
0x180015cd7  sub     rax, rdi
0x180015cda  mov     rdx, [r15+rsi*8+8]
0x180015cdf  mov     r8, [rdx]; Size
0x180015ce2  cmp     rax, r8
0x180015ce5  jbe     loc_180015DDA
0x180015ceb  mov     rdx, [rdx+10h]; Src
0x180015cef  mov     rcx, rdi; void *
0x180015cf2  call    memmove
0x180015cf7  mov     rax, [r15+rsi*8+8]
0x180015cfc  mov     rax, [rax]
0x180015cff  mov     byte ptr [rax+rdi], 0
0x180015d03  inc     rdi
0x180015d06  add     rdi, rax
0x180015d09  inc     rbx
0x180015d0c  jmp     short loc_180015CC9
0x180015d0e  mov     rdx, [rbp+var_18]
0x180015d12  mov     rax, rdi
0x180015d15  mov     r8d, 0FFFFFFFFh
0x180015d1b  sub     rax, [rdx+10h]
0x180015d1f  mov     [rdx], rax
0x180015d22  xor     eax, eax
0x180015d24  mov     [rbp+var_50], rax
0x180015d28  cmp     r13, r8
0x180015d2b  ja      loc_180015E4E
0x180015d31  mov     eax, r13d
0x180015d34  mov     dword ptr [rbp+var_50], eax
0x180015d37  cmp     r13, rax
0x180015d3a  jnz     loc_180015F0D
0x180015d40  mov     dword ptr [rbp+var_50+4], 0
0x180015d47  mov     rbx, [rbp+var_50]
0x180015d4b  shr     rbx, 20h
0x180015d4f  mov     [r14+8], eax
0x180015d53  test    ebx, ebx
0x180015d55  js      loc_180015DF5
0x180015d5b  xor     eax, eax
0x180015d5d  sub     rdi, r14
0x180015d60  mov     [rbp+var_50], rax
0x180015d64  cmp     rdi, r8
0x180015d67  ja      loc_180015E5A
0x180015d6d  mov     eax, edi
0x180015d6f  mov     dword ptr [rbp+var_50], eax
0x180015d72  cmp     rdi, rax
0x180015d75  jnz     loc_180015F19
0x180015d7b  mov     dword ptr [rbp+var_50+4], 0
0x180015d82  mov     r8, [rbp+var_50]
0x180015d86  shr     r8, 20h
0x180015d8a  mov     [r14+4], eax
0x180015d8e  test    r8d, r8d
0x180015d91  js      loc_180015F25
0x180015d97  mov     dword ptr [r14], 7053644Dh
0x180015d9e  mov     rax, [rdx+8]
0x180015da2  cmp     [rdx], rax
0x180015da5  ja      short loc_180015DDA
0x180015da7  test    r15, r15
0x180015daa  jz      short loc_180015DB4
0x180015dac  mov     rcx, r15; Block
0x180015daf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015db4  xor     eax, eax
0x180015db6  mov     r12, [rsp+70h+arg_10]
0x180015dbe  mov     rcx, [rbp+var_8]
0x180015dc2  xor     rcx, rsp; StackCookie
0x180015dc5  call    __security_check_cookie
0x180015dca  add     rsp, 70h
0x180015dce  pop     r15
0x180015dd0  pop     r14
0x180015dd2  pop     r13
0x180015dd4  pop     rdi
0x180015dd5  pop     rsi
0x180015dd6  pop     rbx
0x180015dd7  pop     rbp
0x180015dd8  retn
0x180015dda  mov     ecx, 0C00000E5h; Status
0x180015ddf  call    cs:__imp_RtlRaiseStatus
0x180015de6  nop     dword ptr [rax+rax+00h]
0x180015deb  int     3; Trap to Debugger
0x180015dec  add     rcx, 20h ; ' '
0x180015df0  jmp     loc_180015C58
0x180015df5  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015dfc  mov     [rbp+var_38], 1EBh
0x180015e04  mov     [rbp+var_48], rax
0x180015e08  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180015e0f  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x180015e16  mov     r8d, ebx
0x180015e19  mov     [rbp+var_40], rax
0x180015e1d  lea     rcx, [rbp+var_48]
0x180015e21  lea     rax, aBuclRtlConvert; "BUCL::Rtl::ConvertInteger(Pairs.Length,"...
0x180015e28  mov     [rbp+var_30], rax
0x180015e2c  call    RtlReportErrorOrigination
0x180015e31  test    r15, r15
0x180015e34  jz      short loc_180015E3E
0x180015e36  mov     rcx, r15; Block
0x180015e39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015e3e  mov     eax, ebx
0x180015e40  jmp     loc_180015DB6
0x180015e45  add     rcx, 20h ; ' '
0x180015e49  jmp     loc_180015BDD
0x180015e4e  mov     dword ptr [rbp+var_50+4], 0C0000095h
0x180015e55  jmp     loc_180015D47
0x180015e5a  mov     dword ptr [rbp+var_50+4], 0C0000095h
0x180015e61  jmp     loc_180015D82
0x180015e66  mov     eax, 8
0x180015e6b  jmp     loc_180015BBF
0x180015e70  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015e77  mov     [rbp+var_38], 1C6h
0x180015e7f  mov     [rbp+var_48], rax
0x180015e83  lea     rdx, [rbp+var_48]
0x180015e87  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x180015e8e  mov     [rbp+var_40], rax
0x180015e92  lea     rcx, [rbp+var_10]
0x180015e96  lea     rax, aPairsAllocateM; "Pairs.Allocate(m_StringTable.GetEntryCo"...
0x180015e9d  mov     [rbp+var_30], rax
0x180015ea1  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180015ea6  lea     rcx, [rbp+var_28]
0x180015eaa  mov     ebx, eax
0x180015eac  call    ??1?$Auto@U?$Vector@U_LUTF8_STRING@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<_LUTF8_STRING>>::~Auto<Windows::Vector<_LUTF8_STRING>>(void)
0x180015eb1  mov     eax, ebx
0x180015eb3  jmp     loc_180015DBE
0x180015eb8  mov     eax, [rdi+40h]
0x180015ebb  mov     [rdx], eax
0x180015ebd  mov     rax, rdi
0x180015ec0  jmp     loc_180015C23
0x180015ec5  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015ecc  mov     [rbp+var_38], 1CEh
0x180015ed4  mov     [rbp+var_48], rax
0x180015ed8  lea     rdx, [rbp+var_48]
0x180015edc  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x180015ee3  mov     [rbp+var_40], rax
0x180015ee7  lea     rcx, [rbp+var_10]
0x180015eeb  lea     rax, aBuclRtlQuickso; "BUCL::Rtl::QuickSort(Pairs, CompareStri"...
0x180015ef2  mov     [rbp+var_30], rax
0x180015ef6  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180015efb  lea     rcx, [rbp+var_28]
0x180015eff  mov     ebx, eax
0x180015f01  call    ??1?$Auto@U?$Vector@U_LUTF8_STRING@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<_LUTF8_STRING>>::~Auto<Windows::Vector<_LUTF8_STRING>>(void)
0x180015f06  mov     eax, ebx
0x180015f08  jmp     loc_180015DBE
0x180015f0d  mov     dword ptr [rbp+var_50+4], 0C00000E5h
0x180015f14  jmp     loc_180015D47
0x180015f19  mov     dword ptr [rbp+var_50+4], 0C00000E5h
0x180015f20  jmp     loc_180015D82
0x180015f25  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180015f2c  mov     [rbp+var_38], 1F0h
0x180015f34  mov     [rbp+var_48], rax
0x180015f38  lea     rdx, [rbp+var_48]
0x180015f3c  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x180015f43  mov     [rbp+var_40], rax
0x180015f47  lea     rcx, [rbp+var_10]
0x180015f4b  lea     rax, aBuclRtlConvert_6; "BUCL::Rtl::ConvertInteger( ((ULONG_PTR)"...
0x180015f52  mov     [rbp+var_30], rax
0x180015f56  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180015f5b  lea     rcx, [rbp+var_28]
0x180015f5f  mov     ebx, eax
0x180015f61  call    ??1?$Auto@U?$Vector@U_LUTF8_STRING@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<_LUTF8_STRING>>::~Auto<Windows::Vector<_LUTF8_STRING>>(void)
0x180015f66  mov     eax, ebx
0x180015f68  jmp     loc_180015DB6
```
