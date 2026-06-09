# UnionFs::UfsPathTable::MoveSubtree(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::MoveSubtreeFlags)

- ea: `0x14004df10`
- end: `0x14004e375`
- name: `?MoveSubtree@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@W4MoveSubtreeFlags@2@@Z`
- size: `1125`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x140023c1c`
- `0x14002ca90`

## callees

- `0x140002878`
- `0x14000f81c`
- `0x140023124`
- `0x140046690`
- `0x140048244`
- `0x14004c70c`
- `0x14004df10`
- `0x140056c44`
- `0x140056c7c`
- `0x140079d8c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14004e0d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e15b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e25e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e30f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e346`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e0d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e15b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e25e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e30f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e346`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e0de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e167`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e26a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e31b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e352`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e0de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e167`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e26a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e31b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e352`

## string_xrefs

- `0x14004dfe2`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004df60`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004e0ab`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004e131`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004e22a`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004dfed`: `MoveSubtree`
- `0x14004e120`: `ORIGIN: Subtree to move starts at root node`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::MoveSubtree(
        int *a1,
        FsFltWil::Details *a2,
        __int64 a3,
        __int64 a4,
        struct UnionFs::StackEventTracer *a5,
        int a6)
{
  struct _ERESOURCE *v10; // rbx
  __int128 v11; // xmm1
  const struct _UNICODE_STRING *v12; // rax
  const struct _UNICODE_STRING *v13; // rax
  int inserted; // esi
  const char *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int16 v19; // cx
  volatile signed __int32 *v20; // rax
  const char *v21; // rax
  __int64 v22; // r8
  struct _ERESOURCE *v23; // rcx
  __int64 v24; // rax
  utl::_RefCountBase *v25; // rcx
  struct _ERESOURCE *v26; // rcx
  struct UnionFs::StackEventTracer *v27; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v28; // [rsp+28h] [rbp-D8h]
  struct _ERESOURCE *v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  PERESOURCE Resource[2]; // [rsp+60h] [rbp-A0h]
  utl::_RefCountBase *v32; // [rsp+70h] [rbp-90h]
  char v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+79h] [rbp-87h]
  __int16 v35; // [rsp+7Dh] [rbp-83h]
  char v36; // [rsp+7Fh] [rbp-81h]
  __int64 v37[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int64 v42; // [rsp+C0h] [rbp-40h] BYREF
  utl::_RefCountBase *v43; // [rsp+C8h] [rbp-38h]
  __int16 v44; // [rsp+D0h] [rbp-30h]
  const struct _UNICODE_STRING *v45; // [rsp+D8h] [rbp-28h] BYREF
  const char *v46; // [rsp+E0h] [rbp-20h] BYREF
  const char *v47; // [rsp+E8h] [rbp-18h] BYREF
  const char *v48; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v49; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v50; // [rsp+108h] [rbp+8h] BYREF

  v10 = 0;
  if ( (a6 & 1) == 0 )
  {
    FsFltWil::AcquireResourceExclusive(&v29, a1 + 8);
    v10 = v29;
  }
  v11 = *(_OWORD *)(a4 + 40);
  v50 = *(_OWORD *)(a3 + 40);
  v49 = v11;
  if ( (unsigned int)dword_14009E178 > 5 && (qword_14009E188 & 0x10) != 0 && (qword_14009E190 & 0x10) == qword_14009E190 )
  {
    v47 = "UnionFs::UfsPathTable::MoveSubtree";
    v12 = (const struct _UNICODE_STRING *)&v49;
    if ( !*((_QWORD *)&v49 + 1) )
      v12 = &FsTlEmptyUnicodeString;
    a6 = 3163;
    v29 = (struct _ERESOURCE *)v12;
    v13 = (const struct _UNICODE_STRING *)&v50;
    if ( !*((_QWORD *)&v50 + 1) )
      v13 = &FsTlEmptyUnicodeString;
    v45 = v13;
    v46 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
    v48 = "MoveSubtree";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>>(
      (unsigned int)&FsTlEmptyUnicodeString,
      (unsigned int)byte_140097C4D,
      a3,
      a4,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&a6,
      (__int64)&v45,
      (__int64)&v29);
  }
  *(_OWORD *)v37 = 0;
  v40 = 0;
  v41 = 0;
  LODWORD(v37[0]) = _mm_cvtsi128_si32((__m128i)0LL) | 2;
  v38 = 0;
  v39 = 0;
  inserted = UnionFs::UfsPathTable::Lookup((int)a1, (int)a2, a3, 0, (__int64)v37, a5, 1, 0);
  if ( inserted < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inserted,
      (int)a5,
      (struct UnionFs::StackEventTracer *)0x31800140C68LL,
      (unsigned __int64)"UnionFs::UfsPathTable::MoveSubtree",
      "PUSH: Looking up subtree",
      (const char *)v27);
LABEL_13:
    UnionFs::LookupResults::~LookupResults((UnionFs::LookupResults *)v37);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return (unsigned int)inserted;
  }
  if ( (_DWORD)v40 == 1 )
  {
    if ( *(_QWORD *)(*((_QWORD *)&v39 + 1) + 120LL) )
    {
      v16 = "ORIGIN: Dependent union count > 0";
      v17 = 0x47400140C72LL;
LABEL_21:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0ED000BLL,
        (int)a5,
        (struct UnionFs::StackEventTracer *)v17,
        (unsigned __int64)"UnionFs::UfsPathTable::MoveSubtree",
        v16,
        (const char *)v27);
      UnionFs::LookupResults::~LookupResults((UnionFs::LookupResults *)v37);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
      return 3236757515LL;
    }
    if ( (v37[1] & 8) != 0 )
    {
      v16 = "ORIGIN: Subtree to move starts at root node";
      v17 = 0x48D00140C79LL;
      goto LABEL_21;
    }
    v18 = *(_QWORD *)(*((_QWORD *)&v39 + 1) + 48LL);
    v19 = *(_WORD *)a3 < *(_WORD *)a4 ? *(_WORD *)a4 - *(_WORD *)a3 : 0;
    v20 = *(volatile signed __int32 **)(*((_QWORD *)&v39 + 1) + 56LL);
    if ( v20 )
      _InterlockedIncrement(v20 + 2);
    v43 = (utl::_RefCountBase *)v20;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v42 = v18;
    v44 = v19;
    v30 = 0;
    *(_OWORD *)Resource = 0;
    v32 = 0;
    v33 = 0;
    inserted = UnionFs::UfsPathTable::InsertPriv(
                 a1,
                 a2,
                 (UnionFs::Utils *)a4,
                 (__int64 *)&v38,
                 &v30,
                 a5,
                 1u,
                 (__int64)&v42,
                 0);
    if ( inserted < 0 )
    {
      v21 = "PUSH: Failed to insert payload";
      v22 = 0x31900140C95LL;
LABEL_28:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inserted,
        (int)a5,
        (struct UnionFs::StackEventTracer *)v22,
        (unsigned __int64)"UnionFs::UfsPathTable::MoveSubtree",
        v21,
        (const char *)v28);
      if ( v32 )
        utl::_RefCountBase::_DecStrong(v32);
      v23 = Resource[0];
      Resource[0] = 0;
      if ( v23 )
      {
        ExReleaseResourceLite(v23);
        KeLeaveCriticalRegion();
      }
      if ( v43 )
        utl::_RefCountBase::_DecStrong(v43);
      goto LABEL_13;
    }
    v24 = *((_QWORD *)&v39 + 1);
    if ( *(_QWORD *)(*((_QWORD *)&v39 + 1) + 48LL) )
    {
      v25 = *(utl::_RefCountBase **)(*((_QWORD *)&v39 + 1) + 56LL);
      *(_QWORD *)(*((_QWORD *)&v39 + 1) + 48LL) = 0;
      *(_QWORD *)(v24 + 56) = 0;
      if ( v25 )
        utl::_RefCountBase::_DecStrong(v25);
    }
    if ( !*(_QWORD *)(*((_QWORD *)&v39 + 1) + 64LL) )
    {
      inserted = UnionFs::UfsPathTable::Delete(
                   (UnionFs::UfsPathTable *)a1,
                   (__int64)a2,
                   (const char *)a3,
                   (__int64)a5,
                   16,
                   0);
      if ( inserted < 0 )
      {
        v21 = "PUSH: Pruning empty node";
        v22 = 0x5DA00140CA5LL;
        goto LABEL_28;
      }
    }
    if ( v32 )
      utl::_RefCountBase::_DecStrong(v32);
    v26 = Resource[0];
    Resource[0] = 0;
    if ( v26 )
    {
      ExReleaseResourceLite(v26);
      KeLeaveCriticalRegion();
    }
    if ( v43 )
      utl::_RefCountBase::_DecStrong(v43);
  }
  UnionFs::LookupResults::~LookupResults((UnionFs::LookupResults *)v37);
  if ( v10 )
  {
    ExReleaseResourceLite(v10);
    KeLeaveCriticalRegion();
  }
  return 0;
}

```

## disassembly

```asm
0x14004df10  push    rbp
0x14004df12  push    rbx
0x14004df13  push    rsi
0x14004df14  push    rdi
0x14004df15  push    r12
0x14004df17  push    r13
0x14004df19  push    r14
0x14004df1b  push    r15
0x14004df1d  lea     rbp, [rsp-28h]
0x14004df22  sub     rsp, 128h
0x14004df29  xor     edi, edi
0x14004df2b  mov     r12, r9
0x14004df2e  test    byte ptr [rbp+60h+arg_28], 1
0x14004df35  mov     r14, r8
0x14004df38  mov     r13, rdx
0x14004df3b  mov     r15, rcx
0x14004df3e  mov     ebx, edi
0x14004df40  jnz     short loc_14004DF55
0x14004df42  lea     rdx, [rcx+20h]
0x14004df46  lea     rcx, [rsp+160h+var_110]
0x14004df4b  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14004df50  mov     rbx, [rsp+160h+var_110]
0x14004df55  movups  xmm0, xmmword ptr [r14+28h]
0x14004df5a  mov     eax, cs:dword_14009E178
0x14004df60  lea     rdx, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004df67  movups  xmm1, xmmword ptr [r12+28h]
0x14004df6d  movdqu  [rbp+60h+var_58], xmm0
0x14004df72  movdqu  [rbp+60h+var_68], xmm1
0x14004df77  cmp     eax, 5
0x14004df7a  jbe     loc_14004E037
0x14004df80  mov     rcx, cs:qword_14009E190
0x14004df87  mov     rax, cs:qword_14009E188
0x14004df8e  test    al, 10h
0x14004df90  jz      loc_14004E037
0x14004df96  mov     rax, rcx
0x14004df99  and     eax, 10h
0x14004df9c  cmp     rax, rcx
0x14004df9f  jnz     loc_14004E037
0x14004dfa5  cmp     qword ptr [rbp+60h+var_68+8], rdi
0x14004dfa9  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14004dfb0  mov     [rbp+60h+var_78], rdx
0x14004dfb4  lea     rax, [rbp+60h+var_68]
0x14004dfb8  cmovz   rax, rcx
0x14004dfbc  mov     [rbp+60h+arg_28], 0C5Bh
0x14004dfc6  cmp     qword ptr [rbp+60h+var_58+8], rdi
0x14004dfca  lea     rdx, byte_140097C4D
0x14004dfd1  mov     [rsp+160h+var_110], rax
0x14004dfd6  lea     rax, [rbp+60h+var_58]
0x14004dfda  cmovz   rax, rcx
0x14004dfde  mov     [rbp+60h+var_88], rax
0x14004dfe2  lea     rax, aOnecoreBaseFsU_10; "onecore\\base\\fs\\unionfs\\sys\\pathta"...
0x14004dfe9  mov     [rbp+60h+var_80], rax
0x14004dfed  lea     rax, aMovesubtree; "MoveSubtree"
0x14004dff4  mov     [rbp+60h+var_70], rax
0x14004dff8  lea     rax, [rsp+160h+var_110]
0x14004dffd  mov     [rsp+160h+var_118], rax
0x14004e002  lea     rax, [rbp+60h+var_88]
0x14004e006  mov     [rsp+160h+var_120], rax
0x14004e00b  lea     rax, [rbp+60h+arg_28]
0x14004e012  mov     [rsp+160h+var_128], rax
0x14004e017  lea     rax, [rbp+60h+var_80]
0x14004e01b  mov     qword ptr [rsp+160h+var_130], rax
0x14004e020  lea     rax, [rbp+60h+var_78]
0x14004e024  mov     [rsp+160h+var_138], rax
0x14004e029  lea     rax, [rbp+60h+var_70]
0x14004e02d  mov     [rsp+160h+var_140], rax
0x14004e032  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14004e037  mov     [rsp+160h+var_128], rdi; __int64
0x14004e03c  xorps   xmm2, xmm2
0x14004e03f  movd    eax, xmm2
0x14004e043  xorps   xmm0, xmm0
0x14004e046  movdqa  xmmword ptr [rbp+60h+var_E0], xmm2
0x14004e04b  xorps   xmm1, xmm1
0x14004e04e  mov     [rbp+60h+var_B0], rdi
0x14004e052  xor     r9d, r9d; int
0x14004e055  or      eax, 2
0x14004e058  mov     [rbp+60h+var_A8], rdi
0x14004e05c  mov     rdi, [rbp+60h+arg_20]
0x14004e063  mov     r8, r14; int
0x14004e066  mov     dword ptr [rbp+60h+var_E0], eax
0x14004e069  mov     rdx, r13; int
0x14004e06c  lea     rax, [rbp+60h+var_E0]
0x14004e070  mov     [rsp+160h+var_130], 1; int
0x14004e078  mov     [rsp+160h+var_138], rdi; char *
0x14004e07d  mov     rcx, r15; int
0x14004e080  mov     [rsp+160h+var_140], rax; __int64
0x14004e085  movdqa  [rbp+60h+var_D0], xmm0
0x14004e08a  movdqa  [rbp+60h+var_C0], xmm1
0x14004e08f  call    ?Lookup@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupFlags@2@AEAULookupResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAV?$function@$$A6AJAEBVUfsInstanceTierNode@UnionFs@@AEBVUfsPathTierNode@2@PEA_NAEAU?$pair@AEAV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAV12@@utl@@AEAVStackEventTracer@2@@Z@wistd@@@Z; UnionFs::UfsPathTable::Lookup(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupFlags,UnionFs::LookupResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,wistd::function<long (UnionFs::UfsInstanceTierNode const &,UnionFs::UfsPathTierNode const &,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)> *)
0x14004e094  mov     esi, eax
0x14004e096  test    eax, eax
0x14004e098  jns     short loc_14004E0F1
0x14004e09a  lea     rax, aPushLookingUpS_0; "PUSH: Looking up subtree"
0x14004e0a1  mov     r8, 31800140C68h; struct UnionFs::StackEventTracer *
0x14004e0ab  lea     r9, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004e0b2  mov     [rsp+160h+var_140], rax; char *
0x14004e0b7  mov     rdx, rdi; int
0x14004e0ba  mov     ecx, esi; this
0x14004e0bc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e0c1  lea     rcx, [rbp+60h+var_E0]; this
0x14004e0c5  call    ??1LookupResults@UnionFs@@QEAA@XZ; UnionFs::LookupResults::~LookupResults(void)
0x14004e0ca  test    rbx, rbx
0x14004e0cd  jz      short loc_14004E0EA
0x14004e0cf  mov     rcx, rbx; Resource
0x14004e0d2  call    cs:__imp_ExReleaseResourceLite
0x14004e0d9  nop     dword ptr [rax+rax+00h]
0x14004e0de  call    cs:__imp_KeLeaveCriticalRegion
0x14004e0e5  nop     dword ptr [rax+rax+00h]
0x14004e0ea  mov     eax, esi
0x14004e0ec  jmp     loc_14004E360
0x14004e0f1  cmp     dword ptr [rbp+60h+var_B0], 1
0x14004e0f5  jnz     loc_14004E335
0x14004e0fb  mov     r8, qword ptr [rbp+60h+var_C0+8]
0x14004e0ff  xor     esi, esi
0x14004e101  cmp     [r8+78h], rsi
0x14004e105  jbe     short loc_14004E11A
0x14004e107  lea     rax, aOriginDependen; "ORIGIN: Dependent union count > 0"
0x14004e10e  mov     r8, 47400140C72h
0x14004e118  jmp     short loc_14004E131
0x14004e11a  test    byte ptr [rbp+60h+var_E0+8], 8
0x14004e11e  jz      short loc_14004E17D
0x14004e120  lea     rax, aOriginSubtreeT; "ORIGIN: Subtree to move starts at root "...
0x14004e127  mov     r8, 48D00140C79h; struct UnionFs::StackEventTracer *
0x14004e131  lea     r9, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004e138  mov     [rsp+160h+var_140], rax; char *
0x14004e13d  mov     rdx, rdi; int
0x14004e140  mov     ecx, 0C0ED000Bh; this
0x14004e145  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e14a  lea     rcx, [rbp+60h+var_E0]; this
0x14004e14e  call    ??1LookupResults@UnionFs@@QEAA@XZ; UnionFs::LookupResults::~LookupResults(void)
0x14004e153  test    rbx, rbx
0x14004e156  jz      short loc_14004E173
0x14004e158  mov     rcx, rbx; Resource
0x14004e15b  call    cs:__imp_ExReleaseResourceLite
0x14004e162  nop     dword ptr [rax+rax+00h]
0x14004e167  call    cs:__imp_KeLeaveCriticalRegion
0x14004e16e  nop     dword ptr [rax+rax+00h]
0x14004e173  mov     eax, 0C0ED000Bh
0x14004e178  jmp     loc_14004E360
0x14004e17d  movzx   ecx, word ptr [r12]
0x14004e182  movzx   edx, word ptr [r14]
0x14004e186  movzx   eax, cx
0x14004e189  sub     ax, dx
0x14004e18c  cmp     dx, cx
0x14004e18f  mov     rdx, [r8+30h]
0x14004e193  sbb     cx, cx
0x14004e196  and     cx, ax
0x14004e199  mov     rax, [r8+38h]
0x14004e19d  test    rax, rax
0x14004e1a0  jz      short loc_14004E1A6
0x14004e1a2  lock inc dword ptr [rax+8]
0x14004e1a6  mov     [rbp+60h+var_98], rax
0x14004e1aa  lea     r9, [rbp+60h+var_D0]
0x14004e1ae  xor     eax, eax
0x14004e1b0  mov     [rsp+160h+var_120], rsi
0x14004e1b5  mov     [rsp+160h+var_E7], eax
0x14004e1b9  xorps   xmm0, xmm0
0x14004e1bc  mov     [rsp+160h+var_E3], ax
0x14004e1c1  mov     r8, r12
0x14004e1c4  mov     [rsp+160h+var_E1], al
0x14004e1c8  lea     rax, [rbp+60h+var_A0]
0x14004e1cc  mov     [rsp+160h+var_128], rax
0x14004e1d1  lea     rax, [rsp+160h+var_108]
0x14004e1d6  mov     [rsp+160h+var_130], 1
0x14004e1de  mov     [rbp+60h+var_A0], rdx
0x14004e1e2  mov     rdx, r13
0x14004e1e5  mov     [rbp+60h+var_90], cx
0x14004e1e9  mov     rcx, r15
0x14004e1ec  mov     [rsp+160h+var_138], rdi; char *
0x14004e1f1  mov     [rsp+160h+var_140], rax
0x14004e1f6  mov     [rsp+160h+var_108], rsi
0x14004e1fb  movdqu  xmmword ptr [rsp+160h+Resource], xmm0
0x14004e201  mov     [rsp+160h+var_F0], rsi
0x14004e206  mov     [rsp+160h+var_E8], sil
0x14004e20b  call    ?InsertPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAU?$pair@V?$shared_ptr@VUfsPathTree@UnionFs@@@utl@@G@6@PEAUInsertOptionalParams@2@@Z; UnionFs::UfsPathTable::InsertPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,utl::pair<utl::shared_ptr<UnionFs::UfsPathTree>,ushort> *,UnionFs::InsertOptionalParams *)
0x14004e210  xor     r12d, r12d
0x14004e213  mov     esi, eax
0x14004e215  test    eax, eax
0x14004e217  jns     short loc_14004E28D
0x14004e219  lea     rax, aPushFailedToIn; "PUSH: Failed to insert payload"
0x14004e220  mov     r8, 31900140C95h; struct UnionFs::StackEventTracer *
0x14004e22a  lea     r9, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004e231  mov     [rsp+160h+var_140], rax; char *
0x14004e236  mov     rdx, rdi; int
0x14004e239  mov     ecx, esi; this
0x14004e23b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e240  mov     rcx, [rsp+160h+var_F0]; this
0x14004e245  test    rcx, rcx
0x14004e248  jz      short loc_14004E24F
0x14004e24a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e24f  mov     rcx, [rsp+160h+Resource]; Resource
0x14004e254  mov     [rsp+160h+Resource], r12
0x14004e259  test    rcx, rcx
0x14004e25c  jz      short loc_14004E276
0x14004e25e  call    cs:__imp_ExReleaseResourceLite
0x14004e265  nop     dword ptr [rax+rax+00h]
0x14004e26a  call    cs:__imp_KeLeaveCriticalRegion
0x14004e271  nop     dword ptr [rax+rax+00h]
0x14004e276  mov     rcx, [rbp+60h+var_98]; this
0x14004e27a  test    rcx, rcx
0x14004e27d  jz      loc_14004E0C1
0x14004e283  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e288  jmp     loc_14004E0C1
0x14004e28d  mov     rax, qword ptr [rbp+60h+var_C0+8]
0x14004e291  cmp     [rax+30h], r12
0x14004e295  jz      short loc_14004E2AD
0x14004e297  mov     rcx, [rax+38h]; this
0x14004e29b  mov     [rax+30h], r12
0x14004e29f  mov     [rax+38h], r12
0x14004e2a3  test    rcx, rcx
0x14004e2a6  jz      short loc_14004E2AD
0x14004e2a8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e2ad  mov     rax, qword ptr [rbp+60h+var_C0+8]
0x14004e2b1  cmp     [rax+40h], r12
0x14004e2b5  jnz     short loc_14004E2F1
0x14004e2b7  mov     [rsp+160h+var_138], r12
0x14004e2bc  mov     r9, rdi
0x14004e2bf  mov     r8, r14
0x14004e2c2  mov     dword ptr [rsp+160h+var_140], 10h
0x14004e2ca  mov     rdx, r13
0x14004e2cd  mov     rcx, r15
0x14004e2d0  call    ?Delete@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEBVUfsUnionCtx@2@@Z; UnionFs::UfsPathTable::Delete(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::UfsUnionCtx const *)
0x14004e2d5  mov     esi, eax
0x14004e2d7  test    eax, eax
0x14004e2d9  jns     short loc_14004E2F1
0x14004e2db  lea     rax, aPushPruningEmp; "PUSH: Pruning empty node"
0x14004e2e2  mov     r8, 5DA00140CA5h
0x14004e2ec  jmp     loc_14004E22A
0x14004e2f1  mov     rcx, [rsp+160h+var_F0]; this
0x14004e2f6  test    rcx, rcx
0x14004e2f9  jz      short loc_14004E300
0x14004e2fb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e300  mov     rcx, [rsp+160h+Resource]; Resource
0x14004e305  mov     [rsp+160h+Resource], r12
0x14004e30a  test    rcx, rcx
0x14004e30d  jz      short loc_14004E327
0x14004e30f  call    cs:__imp_ExReleaseResourceLite
0x14004e316  nop     dword ptr [rax+rax+00h]
0x14004e31b  call    cs:__imp_KeLeaveCriticalRegion
0x14004e322  nop     dword ptr [rax+rax+00h]
0x14004e327  mov     rcx, [rbp+60h+var_98]; this
0x14004e32b  test    rcx, rcx
0x14004e32e  jz      short loc_14004E335
0x14004e330  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e335  lea     rcx, [rbp+60h+var_E0]; this
0x14004e339  call    ??1LookupResults@UnionFs@@QEAA@XZ; UnionFs::LookupResults::~LookupResults(void)
0x14004e33e  test    rbx, rbx
0x14004e341  jz      short loc_14004E35E
0x14004e343  mov     rcx, rbx; Resource
0x14004e346  call    cs:__imp_ExReleaseResourceLite
0x14004e34d  nop     dword ptr [rax+rax+00h]
0x14004e352  call    cs:__imp_KeLeaveCriticalRegion
0x14004e359  nop     dword ptr [rax+rax+00h]
0x14004e35e  xor     eax, eax
0x14004e360  add     rsp, 128h
0x14004e367  pop     r15
0x14004e369  pop     r14
0x14004e36b  pop     r13
0x14004e36d  pop     r12
0x14004e36f  pop     rdi
0x14004e370  pop     rsi
0x14004e371  pop     rbx
0x14004e372  pop     rbp
0x14004e373  retn
```
