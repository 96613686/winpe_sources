# wil::cloud_store::unmarshal<Windows::Data::Nlm::NlmSignature>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)

- ea: `0x180004050`
- end: `0x180004531`
- name: `??$unmarshal@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z`
- size: `1249`
- prototype: `__int64 __fastcall(__int64, __int64 *, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004540`

## callees

- `0x180002784`
- `0x1800039e0`
- `0x180003d6c`
- `0x180004050`
- `0x180019d80`
- `0x18002e2d0`
- `0x18003071c`
- `0x180031d04`
- `0x180041010`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::unmarshal<Windows::Data::Nlm::NlmSignature>(__int64 a1, __int64 *a2, char a3)
{
  __int64 v5; // rsi
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rdi
  _WORD *v14; // r12
  unsigned int v15; // r13d
  volatile signed __int32 *v16; // r15
  bond *v17; // rcx
  __int64 v18; // rdx
  __int16 v19; // ax
  const char *v20; // r9
  volatile signed __int32 *v21; // rbx
  __int64 v23; // [rsp+28h] [rbp-140h] BYREF
  __int64 *v24; // [rsp+30h] [rbp-138h] BYREF
  __int64 v25; // [rsp+38h] [rbp-130h] BYREF
  char v26; // [rsp+40h] [rbp-128h]
  bond *v27; // [rsp+48h] [rbp-120h]
  bond *v28; // [rsp+50h] [rbp-118h] BYREF
  volatile signed __int32 *v29; // [rsp+58h] [rbp-110h]
  _WORD *v30; // [rsp+60h] [rbp-108h]
  unsigned int v31; // [rsp+68h] [rbp-100h]
  int v32; // [rsp+70h] [rbp-F8h]
  __int16 v33; // [rsp+78h] [rbp-F0h]
  _QWORD v34[3]; // [rsp+80h] [rbp-E8h] BYREF
  unsigned int v35; // [rsp+98h] [rbp-D0h]
  int v36; // [rsp+A0h] [rbp-C8h]
  __int16 v37; // [rsp+A8h] [rbp-C0h]
  bond **v38; // [rsp+B0h] [rbp-B8h] BYREF
  volatile signed __int32 *v39; // [rsp+B8h] [rbp-B0h]
  bond *v40; // [rsp+D0h] [rbp-98h]
  volatile signed __int32 *v41; // [rsp+D8h] [rbp-90h]
  _WORD *v42; // [rsp+E0h] [rbp-88h]
  unsigned int v43; // [rsp+E8h] [rbp-80h]
  int v44; // [rsp+F0h] [rbp-78h]
  __int128 v45; // [rsp+F8h] [rbp-70h]
  __int128 v46; // [rsp+108h] [rbp-60h]
  bond **v47; // [rsp+118h] [rbp-50h]
  __int16 v48; // [rsp+120h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]
  int v51; // [rsp+178h] [rbp+10h] BYREF
  __int64 v52; // [rsp+188h] [rbp+20h] BYREF

  v5 = a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)(a1 + 24) = 1;
  *(_BYTE *)(a1 + 32) = 1;
  v51 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*a2 + 72))(a2, &v51);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v6,
      1);
  *(_DWORD *)(v5 + 28) = v51 == 1;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 64))(a2, v5 + 8);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x691,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v7,
      1);
  if ( (a3 & 3) != 0 )
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
      (__int64 *)(v5 + 16),
      (__int64)a2);
  else
    *(_BYTE *)(v5 + 32) = 0;
  v23 = 0;
  v8 = *a2;
  v24 = &v23;
  v25 = 0;
  v26 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 56))(a2, &v25);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69F,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v9,
      1);
  if ( v26 )
  {
    v10 = *v24;
    *v24 = v25;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v23;
  if ( v23 )
  {
    v52 = v23;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
    v12 = wil::cloud_store::buffer_to_blob(&v38, &v52);
    v27 = *(bond **)v12;
    v40 = v27;
    v13 = *(volatile signed __int32 **)(v12 + 8);
    v41 = v13;
    if ( v13 )
      _InterlockedIncrement(v13 + 2);
    v14 = *(_WORD **)(v12 + 16);
    v42 = v14;
    v15 = *(_DWORD *)(v12 + 24);
    v43 = v15;
    v44 = 0;
    v16 = v39;
    if ( v39 )
    {
      if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v17 = v27;
      v34[0] = v27;
      v34[1] = v13;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      v34[2] = v14;
      v35 = v15;
      v36 = 0;
      v37 = 1;
      v18 = 2;
      if ( v15 < 2 )
        bond::InputBuffer::EofException((bond::InputBuffer *)v34, 2u);
      v36 = 2;
      if ( v15 - 2 < 2 )
        bond::InputBuffer::EofException((bond::InputBuffer *)v34, 2u);
      v19 = v14[1];
      v37 = v19;
      v36 = 4;
      if ( (unsigned __int16)v19 > 2u || *v14 != 16963 )
        bond::UnknownProtocolException(v17);
      v28 = v17;
      v29 = v13;
      if ( v13 )
        _InterlockedIncrement(v13 + 2);
      v30 = v14;
      v31 = v15;
      v32 = 4;
      v33 = v19;
      v27 = (bond *)&v28;
      v45 = 0;
      v46 = 0;
      v47 = &v28;
      v48 = 0;
      v25 = v5;
      v38 = &v28;
      LOBYTE(v39) = 0;
      if ( v19 == 2 )
      {
        LODWORD(v52) = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>((__int64)&v28, (int *)&v52);
      }
      LOWORD(v24) = -1;
      bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&private: static bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>>(
        (bond::InputBuffer **)&v38,
        v18,
        (__int64)&v24);
      v21 = v29;
      if ( v29 )
      {
        if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
        }
      }
      *(_BYTE *)(v5 + 24) = 0;
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &bond::Exception `RTTI Type Descriptor', 0) )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x6B2,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
          v20);
        *(_BYTE *)(a1 + 25) = 1;
        v5 = a1;
        v13 = v41;
        __eh34_try_continuation(0, &bond::Exception `RTTI Type Descriptor', &loc_180004515);
      }
    }
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    v11 = v23;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return v5;
}

```

## disassembly

```asm
0x180004050  mov     r11, rsp
0x180004053  mov     [r11+8], rcx
0x180004057  push    rbx
0x180004058  push    rsi
0x180004059  push    rdi
0x18000405a  push    r12
0x18000405c  push    r13
0x18000405e  push    r14
0x180004060  push    r15
0x180004062  sub     rsp, 130h
0x180004069  mov     edi, r8d
0x18000406c  mov     rbx, rdx
0x18000406f  mov     rsi, rcx
0x180004072  xor     r14d, r14d
0x180004075  mov     [rsp+168h+var_148], r14d
0x18000407a  mov     [rcx], r14
0x18000407d  mov     [rcx+10h], r14
0x180004081  mov     word ptr [rcx+18h], 1
0x180004087  mov     byte ptr [rcx+20h], 1
0x18000408b  mov     r15d, 1
0x180004091  mov     [rsp+168h+var_148], r15d; int
0x180004096  mov     [r11+10h], r14d
0x18000409a  mov     rax, [rdx]
0x18000409d  lea     rdx, [r11+10h]
0x1800040a1  mov     rcx, rbx
0x1800040a4  mov     rax, [rax+48h]
0x1800040a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ad  mov     rcx, [rsp+168h]; this
0x1800040b5  test    eax, eax
0x1800040b7  js      loc_180004499
0x1800040bd  cmp     [rsp+168h+arg_8], r15d
0x1800040c5  jz      loc_180004480
0x1800040cb  mov     eax, r14d
0x1800040ce  mov     [rsi+1Ch], eax
0x1800040d1  mov     rax, [rbx]
0x1800040d4  lea     rdx, [rsi+8]
0x1800040d8  mov     rcx, rbx
0x1800040db  mov     rax, [rax+40h]
0x1800040df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e4  mov     rcx, [rsp+168h]; this
0x1800040ec  test    eax, eax
0x1800040ee  js      loc_1800044AE
0x1800040f4  test    dil, 3
0x1800040f8  jnz     loc_180004488
0x1800040fe  mov     byte ptr [rsi+20h], 0
0x180004102  mov     [rsp+168h+var_140], r14
0x180004107  mov     rax, [rbx]
0x18000410a  lea     rcx, [rsp+168h+var_140]
0x18000410f  mov     [rsp+168h+var_138], rcx
0x180004114  mov     [rsp+168h+var_130], r14
0x180004119  mov     [rsp+168h+var_128], 1
0x18000411e  lea     rdx, [rsp+168h+var_130]
0x180004123  mov     rcx, rbx
0x180004126  mov     rax, [rax+38h]
0x18000412a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000412f  mov     rcx, [rsp+168h]; this
0x180004137  test    eax, eax
0x180004139  js      loc_1800044C3
0x18000413f  cmp     [rsp+168h+var_128], 0
0x180004144  jz      short loc_180004168
0x180004146  mov     rdx, [rsp+168h+var_130]
0x18000414b  mov     rax, [rsp+168h+var_138]
0x180004150  mov     rcx, [rax]
0x180004153  mov     [rax], rdx
0x180004156  test    rcx, rcx
0x180004159  jz      short loc_180004168
0x18000415b  mov     rax, [rcx]
0x18000415e  mov     rax, [rax+10h]
0x180004162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004167  nop
0x180004168  mov     rbx, [rsp+168h+var_140]
0x18000416d  test    rbx, rbx
0x180004170  jz      loc_18000444F
0x180004176  mov     [rsp+168h+arg_18], rbx
0x18000417e  mov     rax, [rbx]
0x180004181  mov     rcx, rbx
0x180004184  mov     rax, [rax+8]
0x180004188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000418d  nop
0x18000418e  lea     rdx, [rsp+168h+arg_18]
0x180004196  lea     rcx, [rsp+168h+var_B8]
0x18000419e  call    ?buffer_to_blob@cloud_store@wil@@CA?AVblob@bond@@AEBV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@2@@Z; wil::cloud_store::buffer_to_blob(wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy> const &)
0x1800041a3  mov     rcx, [rax]
0x1800041a6  mov     [rsp+168h+var_120], rcx
0x1800041ab  mov     [rsp+168h+var_98], rcx
0x1800041b3  mov     rdi, [rax+8]
0x1800041b7  mov     [rsp+168h+var_90], rdi
0x1800041bf  test    rdi, rdi
0x1800041c2  jz      short loc_1800041C8
0x1800041c4  lock inc dword ptr [rdi+8]
0x1800041c8  mov     r12, [rax+10h]
0x1800041cc  mov     [rsp+168h+var_88], r12
0x1800041d4  mov     r13d, [rax+18h]
0x1800041d8  mov     [rsp+168h+var_80], r13d
0x1800041e0  mov     [rsp+168h+var_78], r14d
0x1800041e8  mov     r15, [rsp+168h+var_B0]
0x1800041f0  mov     r14d, 0FFFFFFFFh
0x1800041f6  test    r15, r15
0x1800041f9  jz      short loc_180004236
0x1800041fb  mov     eax, r14d
0x1800041fe  lock xadd [r15+8], eax
0x180004204  cmp     eax, 1
0x180004207  jnz     short loc_180004236
0x180004209  mov     rax, [r15]
0x18000420c  mov     rcx, r15
0x18000420f  mov     rax, [rax+8]
0x180004213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004218  mov     eax, r14d
0x18000421b  lock xadd [r15+0Ch], eax
0x180004221  cmp     eax, 1
0x180004224  jnz     short loc_180004236
0x180004226  mov     rax, [r15]
0x180004229  mov     rcx, r15
0x18000422c  mov     rax, [rax+10h]
0x180004230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004235  nop
0x180004236  test    rbx, rbx
0x180004239  jz      short loc_18000424B
0x18000423b  mov     rax, [rbx]
0x18000423e  mov     rcx, rbx
0x180004241  mov     rax, [rax+10h]
0x180004245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000424a  nop
0x18000424b  mov     rcx, [rsp+168h+var_120]; this
0x180004250  mov     [rsp+168h+var_E8], rcx
0x180004258  mov     [rsp+168h+var_E0], rdi
0x180004260  test    rdi, rdi
0x180004263  jz      short loc_180004269
0x180004265  lock inc dword ptr [rdi+8]
0x180004269  mov     [rsp+168h+var_D8], r12
0x180004271  mov     [rsp+168h+var_D0], r13d
0x180004279  mov     [rsp+168h+var_C8], 0
0x180004284  mov     eax, 1
0x180004289  mov     [rsp+168h+var_C0], ax
0x180004291  mov     edx, 2; unsigned int
0x180004296  cmp     r13d, edx
0x180004299  jb      loc_1800044D8
0x18000429f  mov     [rsp+168h+var_C8], edx
0x1800042a6  lea     eax, [r13-2]
0x1800042aa  cmp     eax, edx
0x1800042ac  jb      loc_1800044E5
0x1800042b2  movzx   eax, word ptr [r12+2]
0x1800042b8  mov     [rsp+168h+var_C0], ax
0x1800042c0  mov     [rsp+168h+var_C8], 4
0x1800042cb  mov     r8d, 4243h
0x1800042d1  cmp     ax, dx
0x1800042d4  ja      loc_18000447A
0x1800042da  cmp     [r12], r8w
0x1800042df  jnz     loc_18000447A
0x1800042e5  mov     [rsp+168h+var_118], rcx
0x1800042ea  mov     [rsp+168h+var_110], rdi
0x1800042ef  test    rdi, rdi
0x1800042f2  jz      short loc_1800042F8
0x1800042f4  lock inc dword ptr [rdi+8]
0x1800042f8  mov     [rsp+168h+var_108], r12
0x1800042fd  mov     [rsp+168h+var_100], r13d
0x180004302  mov     [rsp+168h+var_F8], 4
0x18000430a  mov     [rsp+168h+var_F0], ax
0x18000430f  lea     rcx, [rsp+168h+var_118]
0x180004314  mov     [rsp+168h+var_120], rcx
0x180004319  xorps   xmm0, xmm0
0x18000431c  movdqu  [rsp+168h+var_70], xmm0
0x180004325  xorps   xmm1, xmm1
0x180004328  movdqu  [rsp+168h+var_60], xmm1
0x180004331  lea     rcx, [rsp+168h+var_118]
0x180004336  mov     [rsp+168h+var_50], rcx
0x18000433e  mov     [rsp+168h+var_48], 0
0x180004348  mov     [rsp+168h+var_130], rsi
0x18000434d  lea     rcx, [rsp+168h+var_118]
0x180004352  mov     [rsp+168h+var_B8], rcx
0x18000435a  mov     byte ptr [rsp+168h+var_B0], 0
0x180004362  cmp     dx, ax
0x180004365  jz      loc_1800044F3
0x18000436b  mov     eax, 0FFFFh
0x180004370  mov     word ptr [rsp+168h+var_138], ax
0x180004375  lea     r8, [rsp+168h+var_138]
0x18000437a  lea     rcx, [rsp+168h+var_B8]
0x180004382  call    ??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UNlmSignature@Nlm@Data@Windows@@_K$0A@$1?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UNlmSignature@Nlm@Data@Windows@@_K$0A@$1?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEBV?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,boost::mpl::l_end>> const &,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>> const &)
0x180004387  nop
0x180004388  mov     rbx, [rsp+168h+var_110]
0x18000438d  test    rbx, rbx
0x180004390  jz      short loc_1800043CB
0x180004392  mov     eax, r14d
0x180004395  lock xadd [rbx+8], eax
0x18000439a  cmp     eax, 1
0x18000439d  jnz     short loc_1800043CB
0x18000439f  mov     rax, [rbx]
0x1800043a2  mov     rcx, rbx
0x1800043a5  mov     rax, [rax+8]
0x1800043a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ae  mov     eax, r14d
0x1800043b1  lock xadd [rbx+0Ch], eax
0x1800043b6  cmp     eax, 1
0x1800043b9  jnz     short loc_1800043CB
0x1800043bb  mov     rax, [rbx]
0x1800043be  mov     rcx, rbx
0x1800043c1  mov     rax, [rax+10h]
0x1800043c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ca  nop
0x1800043cb  mov     byte ptr [rsi+18h], 0
0x1800043cf  test    rdi, rdi
0x1800043d2  jz      short loc_18000440D
0x1800043d4  mov     eax, r14d
0x1800043d7  lock xadd [rdi+8], eax
0x1800043dc  cmp     eax, 1
0x1800043df  jnz     short loc_18000440D
0x1800043e1  mov     rax, [rdi]
0x1800043e4  mov     rcx, rdi
0x1800043e7  mov     rax, [rax+8]
0x1800043eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f0  mov     eax, r14d
0x1800043f3  lock xadd [rdi+0Ch], eax
0x1800043f8  cmp     eax, 1
0x1800043fb  jnz     short loc_18000440D
0x1800043fd  mov     rax, [rdi]
0x180004400  mov     rcx, rdi
0x180004403  mov     rax, [rax+10h]
0x180004407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000440c  nop
0x18000440d  test    rdi, rdi
0x180004410  jz      short loc_18000444A
0x180004412  mov     eax, r14d
0x180004415  lock xadd [rdi+8], eax
0x18000441a  cmp     eax, 1
0x18000441d  jnz     short loc_18000444A
0x18000441f  mov     rax, [rdi]
0x180004422  mov     rcx, rdi
0x180004425  mov     rax, [rax+8]
0x180004429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000442e  lock xadd [rdi+0Ch], r14d
0x180004434  cmp     r14d, 1
0x180004438  jnz     short loc_18000444A
0x18000443a  mov     rax, [rdi]
0x18000443d  mov     rcx, rdi
0x180004440  mov     rax, [rax+10h]
0x180004444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004449  nop
0x18000444a  mov     rbx, [rsp+168h+var_140]
0x18000444f  test    rbx, rbx
0x180004452  jz      short loc_180004464
0x180004454  mov     rax, [rbx]
0x180004457  mov     rcx, rbx
0x18000445a  mov     rax, [rax+10h]
0x18000445e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004463  nop
0x180004464  mov     rax, rsi
0x180004467  add     rsp, 130h
0x18000446e  pop     r15
0x180004470  pop     r14
0x180004472  pop     r13
0x180004474  pop     r12
0x180004476  pop     rdi
0x180004477  pop     rsi
0x180004478  pop     rbx
0x180004479  retn
0x18000447a  call    ?UnknownProtocolException@bond@@YAXXZ; bond::UnknownProtocolException(void)
0x180004480  mov     eax, r15d
0x180004483  jmp     loc_1800040CE
0x180004488  lea     rcx, [rsi+10h]
0x18000448c  mov     rdx, rbx
0x18000448f  call    ??4?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(Windows::Internal::Storage::Cloud::ICloudStoreData *)
0x180004494  jmp     loc_180004102
0x180004499  mov     r9d, eax; char *
0x18000449c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800044a3  mov     edx, 685h; void *
0x1800044a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800044ae  mov     r9d, eax; char *
0x1800044b1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800044b8  mov     edx, 691h; void *
0x1800044bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800044c3  mov     r9d, eax; char *
0x1800044c6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800044cd  mov     edx, 69Fh; void *
0x1800044d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800044d8  lea     rcx, [rsp+168h+var_E8]; this
0x1800044e0  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x1800044e5  lea     rcx, [rsp+168h+var_E8]; this
0x1800044ed  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x1800044f3  mov     dword ptr [rsp+168h+arg_18], 0
0x1800044fe  lea     rdx, [rsp+168h+arg_18]
0x180004506  lea     rcx, [rsp+168h+var_118]
0x18000450b  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180004510  jmp     loc_18000436B
0x180004515  mov     r14d, 0FFFFFFFFh
0x18000451b  mov     rsi, [rsp+168h+arg_0]
0x180004523  mov     rdi, [rsp+168h+var_90]
0x18000452b  jmp     loc_18000440D
```
