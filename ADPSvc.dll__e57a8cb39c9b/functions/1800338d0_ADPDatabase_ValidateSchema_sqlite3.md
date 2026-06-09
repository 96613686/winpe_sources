# ADPDatabase::ValidateSchema(sqlite3 *)

- ea: `0x1800338d0`
- end: `0x180033db2`
- name: `?ValidateSchema@ADPDatabase@@AEAAXPEAUsqlite3@@@Z`
- size: `1250`
- prototype: `void __fastcall(ADPDatabase *__hidden this, struct sqlite3 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180033350`

## callees

- `0x180001008`
- `0x180002250`
- `0x1800026f0`
- `0x1800033b0`
- `0x1800034e6`
- `0x180003516`
- `0x180005290`
- `0x18000e1d0`
- `0x1800120e4`
- `0x180013830`
- `0x180024d34`
- `0x180025dbc`
- `0x180025e14`
- `0x18002888c`
- `0x18002d764`
- `0x180030658`
- `0x1800338d0`
- `0x18003474c`
- `0x1800347ec`
- `0x180034998`
- `0x180034e10`
- `0x180034e98`
- `0x180092224`
- `0x1800a71b0`
- `0x1800a82b0`
- `0x1800abe70`
- `0x1800ae7e0`

## string_xrefs

- `0x180033d29`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180033d49`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180033d5b`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180033da0`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ADPDatabase::ValidateSchema(ADPDatabase *this, struct sqlite3 *a2)
{
  struct sqlite3 *v2; // r13
  unsigned int v4; // r14d
  _QWORD *v5; // rbx
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v9; // r9
  int v10; // eax
  char **v11; // r12
  __int64 *v12; // rsi
  __int64 v13; // r15
  __int64 v14; // r8
  __int128 *p_Src; // rdi
  char *v16; // rbx
  __int64 v17; // rax
  size_t v18; // rdx
  __int64 v19; // rdi
  __int128 *v20; // rax
  struct sqlite3_stmt *v21; // rbx
  unsigned int i; // r12d
  int v23; // eax
  const char *v24; // r9
  char v25; // al
  __int64 v26; // rcx
  __int64 v27; // rax
  size_t v28; // r13
  unsigned int v29; // edi
  size_t v30; // rsi
  const void *v31; // r12
  __int64 v32; // rax
  struct sqlite3_value *v33; // rbx
  int v34; // r14d
  void **v35; // rdx
  void **v36; // rdx
  char v37; // al
  struct sqlite3 *v38; // rax
  const char *v39; // [rsp+20h] [rbp-E0h]
  char v40; // [rsp+30h] [rbp-D0h]
  char v41; // [rsp+31h] [rbp-CFh]
  int v42; // [rsp+34h] [rbp-CCh]
  unsigned int v43; // [rsp+3Ch] [rbp-C4h]
  struct sqlite3_stmt *v44; // [rsp+40h] [rbp-C0h] BYREF
  char v45[8]; // [rsp+48h] [rbp-B8h] BYREF
  struct sqlite3_stmt *v46; // [rsp+50h] [rbp-B0h] BYREF
  struct sqlite3_stmt *v47; // [rsp+58h] [rbp-A8h]
  __int64 *v48; // [rsp+60h] [rbp-A0h]
  char **v49; // [rsp+68h] [rbp-98h]
  struct sqlite3_value *v50; // [rsp+70h] [rbp-90h]
  size_t Size; // [rsp+78h] [rbp-88h]
  void *Buf1; // [rsp+80h] [rbp-80h]
  struct sqlite3 *v53; // [rsp+88h] [rbp-78h]
  void *pExceptionObject[2]; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+A0h] [rbp-60h]
  _QWORD v56[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *Buf2[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v59; // [rsp+D8h] [rbp-28h]
  __int128 Src; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v61; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v62; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = a2;
  v53 = a2;
  v4 = 0;
  v5 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 16) > 7u )
    v5 = (_QWORD *)*v5;
  v6 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v6 > 5u )
  {
    *(_QWORD *)v45 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (__int64)v6,
      (__int64)&word_180100606,
      v7,
      v8,
      (const wchar_t **)v45);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DatabaseValidation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DatabaseValidation>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      v9);
  v10 = *((_DWORD *)this + 34);
  if ( v10 )
  {
    if ( v10 == 1 )
    {
      v11 = &off_18010E710;
      v12 = qword_18010E720;
    }
    else
    {
      if ( v10 != 2 )
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
          "Invalid database name!",
          v39);
      v11 = &off_18010E738;
      v12 = qword_18010E748;
    }
  }
  else
  {
    v11 = &off_18010E6E8;
    v12 = qword_18010E6F8;
  }
  v49 = v11;
  v48 = v12;
  unique_sqlite3_transaction::begin((__int64)&v46, (__int64)v2);
  v13 = 0;
  *(_QWORD *)v45 = 0;
  while ( 1 )
  {
    Src = 0;
    v61 = 0;
    v62 = 0;
    std::string::_Construct<1,char const *>(&Src, "PRAGMA table_info(%s)", (const char *)0x15);
    p_Src = &Src;
    if ( v62 > 0xF )
      p_Src = (__int128 *)Src;
    if ( v61 < 2
      || (v16 = (char *)p_Src + v61,
          v17 = _std_search_1(p_Src, (char *)p_Src + v61, "%s", (const char *)2),
          (char *)v17 == v16) )
    {
      v18 = -1;
    }
    else
    {
      v18 = v17 - (_QWORD)p_Src;
    }
    v19 = 0;
    std::string::_Replace<char>(&Src, v18, v14, *v11, (size_t)v11[1]);
    v20 = &Src;
    if ( v62 > 0xF )
      v20 = (__int128 *)Src;
    v56[0] = v20;
    v56[1] = v61;
    sqlite3_prepare_v2_entire_cpp(&v44, v2, v56);
    v21 = v44;
    v42 = v44 ? *((unsigned __int16 *)v44 + 96) : 0;
    for ( i = 0; ; ++i )
    {
      v43 = i;
      v23 = sqlite3_step(v21);
      if ( v23 == 100 )
      {
        v25 = 1;
      }
      else
      {
        if ( v23 && v23 != 101 )
        {
          v38 = (struct sqlite3 *)sqlite3_db_handle(v21);
          sqlite3_error::sqlite3_error((sqlite3_error *)Buf2, v38);
          sqlite3_error::sqlite3_error(pExceptionObject, Buf2);
          throw (sqlite3_error *)pExceptionObject;
        }
        v25 = 0;
      }
      if ( !v25 )
        break;
      v26 = 32LL * i;
      v27 = v12[v19];
      Buf1 = *(void **)(v26 + v27);
      Size = *(_QWORD *)(v26 + v27 + 8);
      v28 = *(_QWORD *)(v26 + v27 + 24);
      v40 = 0;
      v41 = 0;
      v29 = 0;
      if ( !v42 )
        goto LABEL_55;
      v30 = Size;
      v31 = *(const void **)(v26 + v27 + 16);
      do
      {
        v32 = sqlite3_column_value(v44, v29);
        v33 = (struct sqlite3_value *)sqlite3_value_dup(v32);
        v50 = v33;
        sqlite3_value_cache::sqlite3_value_cache((sqlite3_value_cache *)pExceptionObject, v33);
        v34 = v4 | 3;
        if ( v33 )
          sqlite3ValueFree(v33);
        if ( v55 == 3 )
        {
          *(_OWORD *)Buf2 = 0;
          v58 = 0;
          v59 = 0;
          std::string::_Construct<1,char const *>(Buf2, (const char *)pExceptionObject[0], pExceptionObject[1]);
          v35 = Buf2;
          if ( v59 > 0xF )
            v35 = (void **)Buf2[0];
          if ( v30 == v58 && (!v30 || !memcmp_0(Buf1, v35, v30)) )
          {
            v40 = 1;
          }
          else
          {
            v36 = Buf2;
            if ( v59 > 0xF )
              v36 = (void **)Buf2[0];
            if ( v28 == v58 && (!v28 || !memcmp_0(v31, v36, v28)) )
              v41 = 1;
          }
          std::string::~string((char **)Buf2);
        }
        v4 = v34 & 0xFFFFFFFE;
        if ( pExceptionObject[0] )
          operator delete(pExceptionObject[0]);
        ++v29;
      }
      while ( (int)v29 < v42 );
      v12 = v48;
      v13 = *(_QWORD *)v45;
      i = v43;
      if ( v40 && v41 )
        v37 = 0;
      else
LABEL_55:
        v37 = 1;
      if ( v37 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x19D,
          (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
          v24);
      v21 = v44;
      v19 = 5 * v13;
    }
    if ( i != (v12[v19 + 1] - v12[v19]) >> 5 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
        (const char *)retaddr);
    if ( v44 )
      unique_sqlite3_stmt::release_or_terminate(v44);
    std::string::~string((char **)&Src);
    *(_QWORD *)v45 = ++v13;
    if ( v13 )
      break;
    v11 = v49;
    v2 = v53;
  }
  sqlite3_run_no_result_cpp(v47);
  if ( v46 )
    unique_sqlite3_stmt::release_or_terminate(v46);
  v46 = 0;
  if ( v47 )
    unique_sqlite3_stmt::release_or_terminate(v47);
  v47 = 0;
  unique_sqlite3_transaction::rollback_if_needed_or_terminate((unique_sqlite3_transaction *)&v46);
  if ( v47 )
    unique_sqlite3_stmt::release_or_terminate(v47);
  if ( v46 )
    unique_sqlite3_stmt::release_or_terminate(v46);
}

```

## disassembly

```asm
0x1800338d0  push    rbp
0x1800338d2  push    rbx
0x1800338d3  push    rsi
0x1800338d4  push    rdi
0x1800338d5  push    r12
0x1800338d7  push    r13
0x1800338d9  push    r14
0x1800338db  push    r15
0x1800338dd  lea     rbp, [rsp-18h]
0x1800338e2  sub     rsp, 118h
0x1800338e9  mov     rax, cs:__security_cookie
0x1800338f0  xor     rax, rsp
0x1800338f3  mov     [rbp+50h+var_50], rax
0x1800338f7  mov     r13, rdx
0x1800338fa  mov     [rbp+50h+var_C8], rdx
0x1800338fe  mov     rdi, rcx
0x180033901  xor     r14d, r14d
0x180033904  mov     [rsp+150h+var_118], r14d
0x180033909  lea     rbx, [rcx+68h]
0x18003390d  cmp     qword ptr [rbx+18h], 7
0x180033912  jbe     short loc_180033917
0x180033914  mov     rbx, [rbx]
0x180033917  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x18003391c  mov     rcx, [rax+8]
0x180033920  mov     eax, [rcx]
0x180033922  cmp     eax, 5
0x180033925  jbe     short loc_180033942
0x180033927  mov     qword ptr [rsp+150h+var_108], rbx
0x18003392c  lea     rax, [rsp+150h+var_108]
0x180033931  mov     [rsp+150h+var_130], rax; char *
0x180033936  lea     rdx, word_180100606
0x18003393d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180033942  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DatabaseValidation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DatabaseValidation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DatabaseValidation> `wil::Feature<__WilFeatureTraits_Feature_DatabaseValidation>::GetImpl(void)'::`2'::impl
0x180033949  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DatabaseValidation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DatabaseValidation>::__private_IsEnabled(void)
0x18003394e  test    al, al
0x180033950  setz    al
0x180033953  mov     rcx, [rbp+58h]; this
0x180033957  test    al, al
0x180033959  jnz     loc_180033D5B
0x18003395f  mov     eax, [rdi+88h]
0x180033965  test    eax, eax
0x180033967  jnz     short loc_180033979
0x180033969  lea     r12, off_18010E6E8; "EntityHistory"
0x180033970  lea     rsi, qword_18010E6F8
0x180033977  jmp     short loc_1800339A5
0x180033979  cmp     eax, 1
0x18003397c  jnz     short loc_18003398E
0x18003397e  lea     r12, off_18010E710; "CustomEntities"
0x180033985  lea     rsi, qword_18010E720
0x18003398c  jmp     short loc_1800339A5
0x18003398e  cmp     eax, 2
0x180033991  jnz     loc_180033D3E
0x180033997  lea     r12, off_18010E738; "ActionsCurationPolicies"
0x18003399e  lea     rsi, qword_18010E748
0x1800339a5  mov     [rsp+150h+var_E8], r12
0x1800339aa  mov     [rsp+150h+var_F0], rsi
0x1800339af  mov     rdx, r13
0x1800339b2  lea     rcx, [rsp+150h+var_100]
0x1800339b7  call    ?begin@unique_sqlite3_transaction@@SA?AU1@PEAUsqlite3@@@Z; unique_sqlite3_transaction::begin(sqlite3 *)
0x1800339bc  nop
0x1800339bd  xor     r15d, r15d
0x1800339c0  mov     qword ptr [rsp+150h+var_108], r15
0x1800339c5  xorps   xmm0, xmm0
0x1800339c8  movups  [rbp+50h+Src], xmm0
0x1800339cc  mov     [rbp+50h+var_60], 0
0x1800339d4  mov     [rbp+50h+var_58], 0
0x1800339dc  mov     r8d, 15h
0x1800339e2  lea     rdx, aPragmaTableInf; "PRAGMA table_info(%s)"
0x1800339e9  lea     rcx, [rbp+50h+Src]
0x1800339ed  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800339f2  nop
0x1800339f3  mov     rax, [rbp+50h+var_60]
0x1800339f7  lea     rdi, [rbp+50h+Src]
0x1800339fb  cmp     [rbp+50h+var_58], 0Fh
0x180033a00  cmova   rdi, qword ptr [rbp+50h+Src]
0x180033a05  cmp     rax, 2
0x180033a09  jb      short loc_180033A34
0x180033a0b  lea     rbx, [rax+rdi]
0x180033a0f  mov     r9d, 2
0x180033a15  lea     r8, aS_7; "%s"
0x180033a1c  mov     rdx, rbx
0x180033a1f  mov     rcx, rdi
0x180033a22  call    __std_search_1
0x180033a27  mov     rdx, rax
0x180033a2a  cmp     rax, rbx
0x180033a2d  jz      short loc_180033A34
0x180033a2f  sub     rdx, rdi
0x180033a32  jmp     short loc_180033A38
0x180033a34  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180033a38  lea     rdi, [r15+r15*4]
0x180033a3c  mov     rax, [r12+rdi*8+8]
0x180033a41  mov     [rsp+150h+var_130], rax; Size
0x180033a46  mov     r9, [r12+rdi*8]
0x180033a4a  lea     rcx, [rbp+50h+Src]; Src
0x180033a4e  call    ??$_Replace@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_K_KQEBD0@Z; std::string::_Replace<char>(unsigned __int64,unsigned __int64,char const * const,unsigned __int64)
0x180033a53  lea     rax, [rbp+50h+Src]
0x180033a57  cmp     [rbp+50h+var_58], 0Fh
0x180033a5c  cmova   rax, qword ptr [rbp+50h+Src]
0x180033a61  mov     [rbp+50h+var_A0], rax
0x180033a65  mov     rax, [rbp+50h+var_60]
0x180033a69  mov     [rbp+50h+var_98], rax
0x180033a6d  lea     r8, [rbp+50h+var_A0]
0x180033a71  mov     rdx, r13
0x180033a74  lea     rcx, [rsp+150h+var_110]
0x180033a79  call    ?sqlite3_prepare_v2_entire_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_prepare_v2_entire_cpp(sqlite3 *,std::string_view)
0x180033a7e  nop
0x180033a7f  mov     rbx, [rsp+150h+var_110]
0x180033a84  test    rbx, rbx
0x180033a87  jnz     short loc_180033A8F
0x180033a89  mov     [rsp+150h+var_11C], ebx
0x180033a8d  jmp     short loc_180033A9A
0x180033a8f  movzx   eax, word ptr [rbx+0C0h]
0x180033a96  mov     [rsp+150h+var_11C], eax
0x180033a9a  xor     r12d, r12d
0x180033a9d  mov     [rsp+150h+var_114], r12d
0x180033aa2  mov     rcx, rbx
0x180033aa5  call    sqlite3_step
0x180033aaa  cmp     eax, 64h ; 'd'
0x180033aad  jnz     short loc_180033AB3
0x180033aaf  mov     al, 1
0x180033ab1  jmp     short loc_180033AC2
0x180033ab3  test    eax, eax
0x180033ab5  jz      short loc_180033AC0
0x180033ab7  cmp     eax, 65h ; 'e'
0x180033aba  jnz     loc_180033D6D
0x180033ac0  xor     al, al
0x180033ac2  mov     ecx, r12d
0x180033ac5  test    al, al
0x180033ac7  jz      loc_180033C58
0x180033acd  shl     rcx, 5
0x180033ad1  mov     rax, [rsi+rdi*8]
0x180033ad5  mov     rdx, [rcx+rax]
0x180033ad9  mov     [rbp+50h+Buf1], rdx
0x180033add  mov     rdx, [rcx+rax+8]
0x180033ae2  mov     [rsp+150h+Size], rdx
0x180033ae7  mov     rdx, [rcx+rax+10h]
0x180033aec  mov     r13, [rcx+rax+18h]
0x180033af1  xor     al, al
0x180033af3  mov     [rsp+150h+var_120], al
0x180033af7  xor     cl, cl
0x180033af9  mov     [rsp+150h+var_11F], cl
0x180033afd  xor     edi, edi
0x180033aff  cmp     [rsp+150h+var_11C], edi
0x180033b03  jbe     loc_180033C39
0x180033b09  mov     r15d, [rsp+150h+var_11C]
0x180033b0e  mov     rsi, [rsp+150h+Size]
0x180033b13  mov     r12, rdx
0x180033b16  mov     edx, edi
0x180033b18  mov     rcx, [rsp+150h+var_110]
0x180033b1d  call    sqlite3_column_value
0x180033b22  mov     rcx, rax
0x180033b25  call    sqlite3_value_dup
0x180033b2a  mov     rbx, rax
0x180033b2d  mov     [rsp+150h+var_E0], rax
0x180033b32  or      r14d, 2
0x180033b36  mov     [rsp+150h+var_118], r14d
0x180033b3b  mov     rdx, rax; struct sqlite3_value *
0x180033b3e  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180033b42  call    ??0sqlite3_value_cache@@QEAA@PEAUsqlite3_value@@@Z; sqlite3_value_cache::sqlite3_value_cache(sqlite3_value *)
0x180033b47  or      r14d, 1
0x180033b4b  mov     [rsp+150h+var_118], r14d
0x180033b50  test    rbx, rbx
0x180033b53  jz      short loc_180033B5E
0x180033b55  mov     rcx, rbx
0x180033b58  call    sqlite3ValueFree
0x180033b5d  nop
0x180033b5e  cmp     [rbp+50h+var_B0], 3
0x180033b62  jnz     loc_180033BF6
0x180033b68  xorps   xmm0, xmm0
0x180033b6b  movups  xmmword ptr [rbp+50h+Buf2], xmm0
0x180033b6f  mov     [rbp+50h+var_80], 0
0x180033b77  mov     [rbp+50h+var_78], 0
0x180033b7f  mov     r8, [rbp+50h+var_B8]
0x180033b83  mov     rdx, [rbp+50h+pExceptionObject]
0x180033b87  lea     rcx, [rbp+50h+Buf2]
0x180033b8b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180033b90  lea     rdx, [rbp+50h+Buf2]
0x180033b94  cmp     [rbp+50h+var_78], 0Fh
0x180033b99  cmova   rdx, [rbp+50h+Buf2]; Buf2
0x180033b9e  cmp     rsi, [rbp+50h+var_80]
0x180033ba2  jnz     short loc_180033BC0
0x180033ba4  test    rsi, rsi
0x180033ba7  jz      short loc_180033BB9
0x180033ba9  mov     r8, rsi; Size
0x180033bac  mov     rcx, [rbp+50h+Buf1]; Buf1
0x180033bb0  call    memcmp_0
0x180033bb5  test    eax, eax
0x180033bb7  jnz     short loc_180033BC0
0x180033bb9  mov     [rsp+150h+var_120], 1
0x180033bbe  jmp     short loc_180033BED
0x180033bc0  lea     rdx, [rbp+50h+Buf2]
0x180033bc4  cmp     [rbp+50h+var_78], 0Fh
0x180033bc9  cmova   rdx, [rbp+50h+Buf2]; Buf2
0x180033bce  cmp     r13, [rbp+50h+var_80]
0x180033bd2  jnz     short loc_180033BED
0x180033bd4  test    r13, r13
0x180033bd7  jz      short loc_180033BE8
0x180033bd9  mov     r8, r13; Size
0x180033bdc  mov     rcx, r12; Buf1
0x180033bdf  call    memcmp_0
0x180033be4  test    eax, eax
0x180033be6  jnz     short loc_180033BED
0x180033be8  mov     [rsp+150h+var_11F], 1
0x180033bed  lea     rcx, [rbp+50h+Buf2]
0x180033bf1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033bf6  and     r14d, 0FFFFFFFEh
0x180033bfa  mov     [rsp+150h+var_118], r14d
0x180033bff  mov     rcx, [rbp+50h+pExceptionObject]; void *
0x180033c03  test    rcx, rcx
0x180033c06  jz      short loc_180033C0D
0x180033c08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180033c0d  inc     edi
0x180033c0f  cmp     edi, r15d
0x180033c12  jl      loc_180033B16
0x180033c18  mov     rsi, [rsp+150h+var_F0]
0x180033c1d  mov     r15, qword ptr [rsp+150h+var_108]
0x180033c22  mov     r12d, [rsp+150h+var_114]
0x180033c27  cmp     [rsp+150h+var_120], 0
0x180033c2c  jz      short loc_180033C39
0x180033c2e  cmp     [rsp+150h+var_11F], 0
0x180033c33  jz      short loc_180033C39
0x180033c35  xor     al, al
0x180033c37  jmp     short loc_180033C3B
0x180033c39  mov     al, 1
0x180033c3b  mov     rcx, [rbp+58h]; this
0x180033c3f  test    al, al
0x180033c41  jnz     loc_180033DA0
0x180033c47  inc     r12d
0x180033c4a  mov     rbx, [rsp+150h+var_110]
0x180033c4f  lea     rdi, [r15+r15*4]
0x180033c53  jmp     loc_180033A9D
0x180033c58  mov     r9, [rbp+58h]; char *
0x180033c5c  mov     rax, [rsi+rdi*8+8]
0x180033c61  sub     rax, [rsi+rdi*8]
0x180033c65  sar     rax, 5
0x180033c69  cmp     rcx, rax
0x180033c6c  jnz     loc_180033D29
0x180033c72  mov     rcx, [rsp+150h+var_110]; struct sqlite3_stmt *
0x180033c77  test    rcx, rcx
0x180033c7a  jz      short loc_180033C82
0x180033c7c  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180033c81  nop
0x180033c82  lea     rcx, [rbp+50h+Src]
0x180033c86  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033c8b  inc     r15
0x180033c8e  mov     qword ptr [rsp+150h+var_108], r15
0x180033c93  cmp     r15, 1
0x180033c97  jnb     short loc_180033CA7
0x180033c99  mov     r12, [rsp+150h+var_E8]
0x180033c9e  mov     r13, [rbp+50h+var_C8]
0x180033ca2  jmp     loc_1800339C5
0x180033ca7  mov     rcx, [rsp+150h+var_F8]; struct sqlite3_stmt *
0x180033cac  call    ?sqlite3_run_no_result_cpp@@YAXPEAUsqlite3_stmt@@@Z; sqlite3_run_no_result_cpp(sqlite3_stmt *)
0x180033cb1  mov     rcx, [rsp+150h+var_100]; struct sqlite3_stmt *
0x180033cb6  test    rcx, rcx
0x180033cb9  jz      short loc_180033CC0
0x180033cbb  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180033cc0  mov     [rsp+150h+var_100], 0
0x180033cc9  mov     rcx, [rsp+150h+var_F8]; struct sqlite3_stmt *
0x180033cce  test    rcx, rcx
0x180033cd1  jz      short loc_180033CD8
0x180033cd3  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180033cd8  mov     [rsp+150h+var_F8], 0
0x180033ce1  lea     rcx, [rsp+150h+var_100]; this
0x180033ce6  call    ?rollback_if_needed_or_terminate@unique_sqlite3_transaction@@AEAAXXZ; unique_sqlite3_transaction::rollback_if_needed_or_terminate(void)
0x180033ceb  mov     rcx, [rsp+150h+var_F8]; struct sqlite3_stmt *
0x180033cf0  test    rcx, rcx
0x180033cf3  jz      short loc_180033CFA
0x180033cf5  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180033cfa  mov     rcx, [rsp+150h+var_100]; struct sqlite3_stmt *
0x180033cff  test    rcx, rcx
0x180033d02  jz      short loc_180033D09
0x180033d04  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180033d09  mov     rcx, [rbp+50h+var_50]
0x180033d0d  xor     rcx, rsp; StackCookie
0x180033d10  call    __security_check_cookie
0x180033d15  add     rsp, 118h
0x180033d1c  pop     r15
0x180033d1e  pop     r14
0x180033d20  pop     r13
0x180033d22  pop     r12
0x180033d24  pop     rdi
0x180033d25  pop     rsi
0x180033d26  pop     rbx
0x180033d27  pop     rbp
0x180033d28  retn
0x180033d29  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180033d30  mov     edx, 1A2h; void *
0x180033d35  mov     rcx, r9; this
0x180033d38  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180033d3e  mov     rcx, [rbp+58h]; this
0x180033d42  lea     r9, aInvalidDatabas; "Invalid database name!"
0x180033d49  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180033d50  mov     edx, 178h; void *
0x180033d55  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x180033d5b  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180033d62  mov     edx, 164h; void *
0x180033d67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180033d6d  mov     rcx, rbx
0x180033d70  call    sqlite3_db_handle
  ... truncated ...
```
