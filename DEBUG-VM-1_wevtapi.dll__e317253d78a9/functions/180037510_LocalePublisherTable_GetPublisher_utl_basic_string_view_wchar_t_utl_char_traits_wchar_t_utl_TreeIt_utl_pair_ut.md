# LocalePublisherTable::GetPublisher(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::_TreeIt<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>> &)

- ea: `0x180037510`
- end: `0x1800377b0`
- name: `?GetPublisher@LocalePublisherTable@@IEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAV?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@3@@Z`
- size: `672`
- prototype: `__int64 __fastcall(LocalePublisherTable::_PublisherRecord *this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017ef4`
- `0x180028418`

## callees

- `0x180003ed0`
- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x18000a724`
- `0x18000c374`
- `0x1800137f0`
- `0x180023548`
- `0x18003609c`
- `0x1800363e0`
- `0x180036dc0`
- `0x180037510`
- `0x1800377b8`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800375aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800375aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall LocalePublisherTable::GetPublisher(
        LocalePublisherTable::_PublisherRecord **this,
        __int64 *a2,
        __int64 *a3)
{
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned int v13; // r14d
  LocalePublisherTable::_PublisherRecord *v14; // r10
  __int64 v15; // r9
  __int64 v16; // r9
  LocalePublisherTable::_PublisherRecord *v17; // r10
  int v18; // eax
  LocalePublisherTable::_PublisherRecord *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h]
  __int128 v22; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-29h] BYREF
  __int128 pExceptionObject; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]
  int v26; // [rsp+88h] [rbp+Fh]
  int v27; // [rsp+8Ch] [rbp+13h]
  int v28; // [rsp+90h] [rbp+17h]
  unsigned int v29; // [rsp+E0h] [rbp+67h] BYREF

  Buffer::Buffer((Buffer *)v23, 0, 0, 1);
  v6 = (char *)(this + 40);
  if ( this[42] == (LocalePublisherTable::_PublisherRecord *)(this + 40) )
  {
    *a3 = (__int64)v6;
  }
  else
  {
    v7 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
           this + 40,
           a2);
    *a3 = v7;
    if ( (char *)v7 != v6 )
    {
      v8 = a2[1];
      v9 = *(_QWORD *)(v7 + 24);
      v10 = (*(_QWORD *)(v7 + 32) - v9) >> 1;
      if ( (v8 | (unsigned __int64)v10) > 0x7FFFFFFF )
        __int2c();
      v11 = 2;
      if ( v9 )
        v11 = *(_QWORD *)(v7 + 24);
      v12 = 2;
      if ( *a2 )
        v12 = *a2;
      if ( CompareStringOrdinal((LPCWCH)v12, v8, (LPCWCH)v11, v10, 1) != 1 )
        goto LABEL_28;
    }
  }
  v13 = 0;
  do
  {
    ++v13;
    Buffer::SetCurrentIndex((Buffer *)v23, 0);
    v29 = 0;
    if ( !RecordCache::GetRecord(this[44], v13, (struct Buffer *)v23, &v29) )
    {
      if ( !v29 )
      {
        Buffer::~Buffer((Buffer *)v23);
        return 0;
      }
      Buffer::SetSize((Buffer *)v23, v29);
      if ( !RecordCache::GetRecord(this[44], v13, (struct Buffer *)v23, &v29) )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
        }
        pExceptionObject = 0;
        v25 = 0;
        v26 = 1168;
        v27 = -1;
        v28 = 1104;
        throw (EvtException *)&pExceptionObject;
      }
    }
    Buffer::SetCurrentIndex((Buffer *)v23, 0);
    LocalePublisherTable::_PublisherRecord::Deserialize(
      (LocalePublisherTable::_PublisherRecord *)this,
      (struct Buffer *)v23);
    v14 = *this;
    v15 = (this[1] - *this) >> 1;
    v22 = *(_OWORD *)a2;
    v20 = v14;
    v21 = v15;
  }
  while ( !(unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v20, &v22) );
  v20 = v17;
  v21 = v16;
  v18 = MakeOrThrowOOM(&pExceptionObject, &v20);
  *a3 = *(_QWORD *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,LocalePublisherTable::_PublisherRecord>(
                     (int)this + 320,
                     (unsigned int)&v22,
                     *a3,
                     v18,
                     (__int64)this);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&pExceptionObject);
  if ( !*a3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
    }
    pExceptionObject = 0;
    v25 = 0;
    v26 = 14;
    v27 = -1;
    v28 = 1119;
    throw (EvtException *)&pExceptionObject;
  }
LABEL_28:
  Buffer::~Buffer((Buffer *)v23);
  return 1;
}

```

## disassembly

```asm
0x180037510  push    rbp
0x180037512  push    rbx
0x180037513  push    rsi
0x180037514  push    rdi
0x180037515  push    r14
0x180037517  push    r15
0x180037519  lea     rbp, [rsp-2Fh]
0x18003751e  sub     rsp, 0A8h
0x180037525  mov     rdi, r8
0x180037528  mov     r15, rdx
0x18003752b  mov     rsi, rcx
0x18003752e  mov     r9b, 1; bool
0x180037531  xor     r8d, r8d; unsigned int
0x180037534  xor     edx, edx; unsigned __int8 *
0x180037536  lea     rcx, [rbp+57h+var_80]; this
0x18003753a  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x18003753f  nop
0x180037540  lea     rbx, [rsi+140h]
0x180037547  mov     r14d, 2
0x18003754d  cmp     [rbx+10h], rbx
0x180037551  jnz     short loc_180037558
0x180037553  mov     [rdi], rbx
0x180037556  jmp     short loc_1800375B9
0x180037558  mov     rdx, r15
0x18003755b  mov     rcx, rbx
0x18003755e  call    ??$_LowerBoundNonEmpty@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180037563  mov     [rdi], rax
0x180037566  cmp     rax, rbx
0x180037569  jz      short loc_1800375B9
0x18003756b  mov     rdx, [r15+8]; cchCount1
0x18003756f  mov     rcx, [rax+18h]
0x180037573  mov     r9, [rax+20h]
0x180037577  sub     r9, rcx
0x18003757a  sar     r9, 1; cchCount2
0x18003757d  mov     rax, r9
0x180037580  or      rax, rdx
0x180037583  cmp     rax, 7FFFFFFFh
0x180037589  jbe     short loc_18003758D
0x18003758b  int     2Ch; Windows NT - assertion failure
0x18003758d  mov     r8, r14
0x180037590  test    rcx, rcx
0x180037593  cmovnz  r8, rcx; lpString2
0x180037597  mov     rcx, r14
0x18003759a  cmp     qword ptr [r15], 0
0x18003759e  cmovnz  rcx, [r15]; lpString1
0x1800375a2  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x1800375aa  call    cs:__imp_CompareStringOrdinal
0x1800375b0  cmp     eax, 1
0x1800375b3  jnz     loc_180037795
0x1800375b9  xor     r14d, r14d
0x1800375bc  inc     r14d
0x1800375bf  xor     edx, edx; unsigned int
0x1800375c1  lea     rcx, [rbp+57h+var_80]; this
0x1800375c5  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800375ca  mov     [rbp+57h+arg_0], 0
0x1800375d1  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800375d5  lea     r8, [rbp+57h+var_80]; struct Buffer *
0x1800375d9  mov     edx, r14d; unsigned int
0x1800375dc  mov     rcx, [rsi+160h]; this
0x1800375e3  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x1800375e8  test    al, al
0x1800375ea  jnz     short loc_18003761F
0x1800375ec  mov     edx, [rbp+57h+arg_0]; unsigned int
0x1800375ef  test    edx, edx
0x1800375f1  jz      loc_180037788
0x1800375f7  lea     rcx, [rbp+57h+var_80]; this
0x1800375fb  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x180037600  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180037604  lea     r8, [rbp+57h+var_80]; struct Buffer *
0x180037608  mov     edx, r14d; unsigned int
0x18003760b  mov     rcx, [rsi+160h]; this
0x180037612  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x180037617  test    al, al
0x180037619  jz      loc_18003771A
0x18003761f  xor     edx, edx; unsigned int
0x180037621  lea     rcx, [rbp+57h+var_80]; this
0x180037625  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x18003762a  lea     rdx, [rbp+57h+var_80]; struct Buffer *
0x18003762e  mov     rcx, rsi; this
0x180037631  call    ?Deserialize@_PublisherRecord@LocalePublisherTable@@QEAAXAEAVBuffer@@@Z; LocalePublisherTable::_PublisherRecord::Deserialize(Buffer &)
0x180037636  mov     r10, [rsi]
0x180037639  mov     r9, [rsi+8]
0x18003763d  sub     r9, r10
0x180037640  sar     r9, 1
0x180037643  movaps  xmm0, xmmword ptr [r15]
0x180037647  movdqa  [rbp+57h+var_90], xmm0
0x18003764c  mov     [rbp+57h+var_A0], r10
0x180037650  mov     [rbp+57h+var_98], r9
0x180037654  lea     rdx, [rbp+57h+var_90]
0x180037658  lea     rcx, [rbp+57h+var_A0]
0x18003765c  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180037661  test    al, al
0x180037663  jz      loc_1800375BC
0x180037669  mov     [rbp+57h+var_A0], r10
0x18003766d  mov     [rbp+57h+var_98], r9
0x180037671  lea     rdx, [rbp+57h+var_A0]
0x180037675  lea     rcx, [rbp+57h+pExceptionObject]
0x180037679  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18003767e  mov     qword ptr [rsp+0D0h+bIgnoreCase], rsi
0x180037683  mov     r9, rax
0x180037686  mov     r8, [rdi]
0x180037689  lea     rdx, [rbp+57h+var_90]
0x18003768d  mov     rcx, rbx
0x180037690  call    ??$_TryEmplace@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@2@$0A@@utl@@IEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@utl@@_N@1@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@1@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAU_PublisherRecord@LocalePublisherTable@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,LocalePublisherTable::_PublisherRecord>(utl::_TreeNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,LocalePublisherTable::_PublisherRecord &&)
0x180037695  mov     rcx, [rax]
0x180037698  mov     [rdi], rcx
0x18003769b  lea     rcx, [rbp+57h+pExceptionObject]
0x18003769f  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800376a4  cmp     qword ptr [rdi], 0
0x1800376a8  jnz     loc_180037795
0x1800376ae  lea     rax, WPP_GLOBAL_Control
0x1800376b5  mov     ebx, 0Eh
0x1800376ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376c1  cmp     rcx, rax
0x1800376c4  jz      short loc_1800376E8
0x1800376c6  test    byte ptr [rcx+1Ch], 1
0x1800376ca  jz      short loc_1800376E8
0x1800376cc  cmp     byte ptr [rcx+19h], 2
0x1800376d0  jb      short loc_1800376E8
0x1800376d2  lea     edx, [rbx+24h]
0x1800376d5  mov     r9d, ebx
0x1800376d8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800376df  mov     rcx, [rcx+10h]
0x1800376e3  call    WPP_SF_D
0x1800376e8  xorps   xmm0, xmm0
0x1800376eb  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800376f0  mov     [rbp+57h+var_50], 0
0x1800376f8  mov     [rbp+57h+var_48], ebx
0x1800376fb  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x180037702  mov     [rbp+57h+var_40], 45Fh
0x180037709  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037710  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180037714  call    _CxxThrowException_0
0x18003771a  lea     rax, WPP_GLOBAL_Control
0x180037721  mov     ebx, 490h
0x180037726  mov     rcx, cs:WPP_GLOBAL_Control
0x18003772d  cmp     rcx, rax
0x180037730  jz      short loc_180037756
0x180037732  test    byte ptr [rcx+1Ch], 1
0x180037736  jz      short loc_180037756
0x180037738  cmp     byte ptr [rcx+19h], 2
0x18003773c  jb      short loc_180037756
0x18003773e  mov     edx, 31h ; '1'
0x180037743  mov     r9d, ebx
0x180037746  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x18003774d  mov     rcx, [rcx+10h]
0x180037751  call    WPP_SF_D
0x180037756  xorps   xmm0, xmm0
0x180037759  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18003775e  mov     [rbp+57h+var_50], 0
0x180037766  mov     [rbp+57h+var_48], ebx
0x180037769  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x180037770  mov     [rbp+57h+var_40], 450h
0x180037777  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003777e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180037782  call    _CxxThrowException_0
0x180037788  lea     rcx, [rbp+57h+var_80]; this
0x18003778c  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x180037791  xor     al, al
0x180037793  jmp     short loc_1800377A0
0x180037795  lea     rcx, [rbp+57h+var_80]; this
0x180037799  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003779e  mov     al, 1
0x1800377a0  add     rsp, 0A8h
0x1800377a7  pop     r15
0x1800377a9  pop     r14
0x1800377ab  pop     rdi
0x1800377ac  pop     rsi
0x1800377ad  pop     rbx
0x1800377ae  pop     rbp
0x1800377af  retn
```
