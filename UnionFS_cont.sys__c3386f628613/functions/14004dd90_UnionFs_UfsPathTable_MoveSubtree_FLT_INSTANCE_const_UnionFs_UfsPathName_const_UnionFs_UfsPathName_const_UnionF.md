# UnionFs::UfsPathTable::MoveSubtree(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::MoveSubtreeFlags)

- ea: `0x14004dd90`
- end: `0x14004e1f5`
- name: `?MoveSubtree@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@W4MoveSubtreeFlags@2@@Z`
- size: `1125`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x140023b7c`
- `0x14002c9f0`

## callees

- `0x140002878`
- `0x14000f7fc`
- `0x140023084`
- `0x140046510`
- `0x1400480c4`
- `0x14004c58c`
- `0x14004dd90`
- `0x140056ac4`
- `0x140056afc`
- `0x140079a6c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14004df52`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dfdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e0de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e18f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e1c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004df52`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dfdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e0de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e18f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004e1c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004df5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dfe7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e0ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e19b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e1d2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004df5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dfe7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e0ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e19b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e1d2`

## string_xrefs

- `0x14004de62`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004dde0`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004df2b`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004dfb1`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004e0aa`: `UnionFs::UfsPathTable::MoveSubtree`
- `0x14004de6d`: `MoveSubtree`
- `0x14004dfa0`: `ORIGIN: Subtree to move starts at root node`

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
      (unsigned int)byte_140097BCD,
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
0x14004dd90  push    rbp
0x14004dd92  push    rbx
0x14004dd93  push    rsi
0x14004dd94  push    rdi
0x14004dd95  push    r12
0x14004dd97  push    r13
0x14004dd99  push    r14
0x14004dd9b  push    r15
0x14004dd9d  lea     rbp, [rsp-28h]
0x14004dda2  sub     rsp, 128h
0x14004dda9  xor     edi, edi
0x14004ddab  mov     r12, r9
0x14004ddae  test    byte ptr [rbp+60h+arg_28], 1
0x14004ddb5  mov     r14, r8
0x14004ddb8  mov     r13, rdx
0x14004ddbb  mov     r15, rcx
0x14004ddbe  mov     ebx, edi
0x14004ddc0  jnz     short loc_14004DDD5
0x14004ddc2  lea     rdx, [rcx+20h]
0x14004ddc6  lea     rcx, [rsp+160h+var_110]
0x14004ddcb  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14004ddd0  mov     rbx, [rsp+160h+var_110]
0x14004ddd5  movups  xmm0, xmmword ptr [r14+28h]
0x14004ddda  mov     eax, cs:dword_14009E178
0x14004dde0  lea     rdx, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004dde7  movups  xmm1, xmmword ptr [r12+28h]
0x14004dded  movdqu  [rbp+60h+var_58], xmm0
0x14004ddf2  movdqu  [rbp+60h+var_68], xmm1
0x14004ddf7  cmp     eax, 5
0x14004ddfa  jbe     loc_14004DEB7
0x14004de00  mov     rcx, cs:qword_14009E190
0x14004de07  mov     rax, cs:qword_14009E188
0x14004de0e  test    al, 10h
0x14004de10  jz      loc_14004DEB7
0x14004de16  mov     rax, rcx
0x14004de19  and     eax, 10h
0x14004de1c  cmp     rax, rcx
0x14004de1f  jnz     loc_14004DEB7
0x14004de25  cmp     qword ptr [rbp+60h+var_68+8], rdi
0x14004de29  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14004de30  mov     [rbp+60h+var_78], rdx
0x14004de34  lea     rax, [rbp+60h+var_68]
0x14004de38  cmovz   rax, rcx
0x14004de3c  mov     [rbp+60h+arg_28], 0C5Bh
0x14004de46  cmp     qword ptr [rbp+60h+var_58+8], rdi
0x14004de4a  lea     rdx, byte_140097BCD
0x14004de51  mov     [rsp+160h+var_110], rax
0x14004de56  lea     rax, [rbp+60h+var_58]
0x14004de5a  cmovz   rax, rcx
0x14004de5e  mov     [rbp+60h+var_88], rax
0x14004de62  lea     rax, aOnecoreBaseFsU_10; "onecore\\base\\fs\\unionfs\\sys\\pathta"...
0x14004de69  mov     [rbp+60h+var_80], rax
0x14004de6d  lea     rax, aMovesubtree; "MoveSubtree"
0x14004de74  mov     [rbp+60h+var_70], rax
0x14004de78  lea     rax, [rsp+160h+var_110]
0x14004de7d  mov     [rsp+160h+var_118], rax
0x14004de82  lea     rax, [rbp+60h+var_88]
0x14004de86  mov     [rsp+160h+var_120], rax
0x14004de8b  lea     rax, [rbp+60h+arg_28]
0x14004de92  mov     [rsp+160h+var_128], rax
0x14004de97  lea     rax, [rbp+60h+var_80]
0x14004de9b  mov     qword ptr [rsp+160h+var_130], rax
0x14004dea0  lea     rax, [rbp+60h+var_78]
0x14004dea4  mov     [rsp+160h+var_138], rax
0x14004dea9  lea     rax, [rbp+60h+var_70]
0x14004dead  mov     [rsp+160h+var_140], rax
0x14004deb2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14004deb7  mov     [rsp+160h+var_128], rdi; __int64
0x14004debc  xorps   xmm2, xmm2
0x14004debf  movd    eax, xmm2
0x14004dec3  xorps   xmm0, xmm0
0x14004dec6  movdqa  xmmword ptr [rbp+60h+var_E0], xmm2
0x14004decb  xorps   xmm1, xmm1
0x14004dece  mov     [rbp+60h+var_B0], rdi
0x14004ded2  xor     r9d, r9d; int
0x14004ded5  or      eax, 2
0x14004ded8  mov     [rbp+60h+var_A8], rdi
0x14004dedc  mov     rdi, [rbp+60h+arg_20]
0x14004dee3  mov     r8, r14; int
0x14004dee6  mov     dword ptr [rbp+60h+var_E0], eax
0x14004dee9  mov     rdx, r13; int
0x14004deec  lea     rax, [rbp+60h+var_E0]
0x14004def0  mov     [rsp+160h+var_130], 1; int
0x14004def8  mov     [rsp+160h+var_138], rdi; char *
0x14004defd  mov     rcx, r15; int
0x14004df00  mov     [rsp+160h+var_140], rax; __int64
0x14004df05  movdqa  [rbp+60h+var_D0], xmm0
0x14004df0a  movdqa  [rbp+60h+var_C0], xmm1
0x14004df0f  call    ?Lookup@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupFlags@2@AEAULookupResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAV?$function@$$A6AJAEBVUfsInstanceTierNode@UnionFs@@AEBVUfsPathTierNode@2@PEA_NAEAU?$pair@AEAV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAV12@@utl@@AEAVStackEventTracer@2@@Z@wistd@@@Z; UnionFs::UfsPathTable::Lookup(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupFlags,UnionFs::LookupResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,wistd::function<long (UnionFs::UfsInstanceTierNode const &,UnionFs::UfsPathTierNode const &,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)> *)
0x14004df14  mov     esi, eax
0x14004df16  test    eax, eax
0x14004df18  jns     short loc_14004DF71
0x14004df1a  lea     rax, aPushLookingUpS_0; "PUSH: Looking up subtree"
0x14004df21  mov     r8, 31800140C68h; struct UnionFs::StackEventTracer *
0x14004df2b  lea     r9, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004df32  mov     [rsp+160h+var_140], rax; char *
0x14004df37  mov     rdx, rdi; int
0x14004df3a  mov     ecx, esi; this
0x14004df3c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004df41  lea     rcx, [rbp+60h+var_E0]; this
0x14004df45  call    ??1LookupResults@UnionFs@@QEAA@XZ; UnionFs::LookupResults::~LookupResults(void)
0x14004df4a  test    rbx, rbx
0x14004df4d  jz      short loc_14004DF6A
0x14004df4f  mov     rcx, rbx; Resource
0x14004df52  call    cs:__imp_ExReleaseResourceLite
0x14004df59  nop     dword ptr [rax+rax+00h]
0x14004df5e  call    cs:__imp_KeLeaveCriticalRegion
0x14004df65  nop     dword ptr [rax+rax+00h]
0x14004df6a  mov     eax, esi
0x14004df6c  jmp     loc_14004E1E0
0x14004df71  cmp     dword ptr [rbp+60h+var_B0], 1
0x14004df75  jnz     loc_14004E1B5
0x14004df7b  mov     r8, qword ptr [rbp+60h+var_C0+8]
0x14004df7f  xor     esi, esi
0x14004df81  cmp     [r8+78h], rsi
0x14004df85  jbe     short loc_14004DF9A
0x14004df87  lea     rax, aOriginDependen; "ORIGIN: Dependent union count > 0"
0x14004df8e  mov     r8, 47400140C72h
0x14004df98  jmp     short loc_14004DFB1
0x14004df9a  test    byte ptr [rbp+60h+var_E0+8], 8
0x14004df9e  jz      short loc_14004DFFD
0x14004dfa0  lea     rax, aOriginSubtreeT; "ORIGIN: Subtree to move starts at root "...
0x14004dfa7  mov     r8, 48D00140C79h; struct UnionFs::StackEventTracer *
0x14004dfb1  lea     r9, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004dfb8  mov     [rsp+160h+var_140], rax; char *
0x14004dfbd  mov     rdx, rdi; int
0x14004dfc0  mov     ecx, 0C0ED000Bh; this
0x14004dfc5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004dfca  lea     rcx, [rbp+60h+var_E0]; this
0x14004dfce  call    ??1LookupResults@UnionFs@@QEAA@XZ; UnionFs::LookupResults::~LookupResults(void)
0x14004dfd3  test    rbx, rbx
0x14004dfd6  jz      short loc_14004DFF3
0x14004dfd8  mov     rcx, rbx; Resource
0x14004dfdb  call    cs:__imp_ExReleaseResourceLite
0x14004dfe2  nop     dword ptr [rax+rax+00h]
0x14004dfe7  call    cs:__imp_KeLeaveCriticalRegion
0x14004dfee  nop     dword ptr [rax+rax+00h]
0x14004dff3  mov     eax, 0C0ED000Bh
0x14004dff8  jmp     loc_14004E1E0
0x14004dffd  movzx   ecx, word ptr [r12]
0x14004e002  movzx   edx, word ptr [r14]
0x14004e006  movzx   eax, cx
0x14004e009  sub     ax, dx
0x14004e00c  cmp     dx, cx
0x14004e00f  mov     rdx, [r8+30h]
0x14004e013  sbb     cx, cx
0x14004e016  and     cx, ax
0x14004e019  mov     rax, [r8+38h]
0x14004e01d  test    rax, rax
0x14004e020  jz      short loc_14004E026
0x14004e022  lock inc dword ptr [rax+8]
0x14004e026  mov     [rbp+60h+var_98], rax
0x14004e02a  lea     r9, [rbp+60h+var_D0]
0x14004e02e  xor     eax, eax
0x14004e030  mov     [rsp+160h+var_120], rsi
0x14004e035  mov     [rsp+160h+var_E7], eax
0x14004e039  xorps   xmm0, xmm0
0x14004e03c  mov     [rsp+160h+var_E3], ax
0x14004e041  mov     r8, r12
0x14004e044  mov     [rsp+160h+var_E1], al
0x14004e048  lea     rax, [rbp+60h+var_A0]
0x14004e04c  mov     [rsp+160h+var_128], rax
0x14004e051  lea     rax, [rsp+160h+var_108]
0x14004e056  mov     [rsp+160h+var_130], 1
0x14004e05e  mov     [rbp+60h+var_A0], rdx
0x14004e062  mov     rdx, r13
0x14004e065  mov     [rbp+60h+var_90], cx
0x14004e069  mov     rcx, r15
0x14004e06c  mov     [rsp+160h+var_138], rdi; char *
0x14004e071  mov     [rsp+160h+var_140], rax
0x14004e076  mov     [rsp+160h+var_108], rsi
0x14004e07b  movdqu  xmmword ptr [rsp+160h+Resource], xmm0
0x14004e081  mov     [rsp+160h+var_F0], rsi
0x14004e086  mov     [rsp+160h+var_E8], sil
0x14004e08b  call    ?InsertPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAU?$pair@V?$shared_ptr@VUfsPathTree@UnionFs@@@utl@@G@6@PEAUInsertOptionalParams@2@@Z; UnionFs::UfsPathTable::InsertPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,utl::pair<utl::shared_ptr<UnionFs::UfsPathTree>,ushort> *,UnionFs::InsertOptionalParams *)
0x14004e090  xor     r12d, r12d
0x14004e093  mov     esi, eax
0x14004e095  test    eax, eax
0x14004e097  jns     short loc_14004E10D
0x14004e099  lea     rax, aPushFailedToIn; "PUSH: Failed to insert payload"
0x14004e0a0  mov     r8, 31900140C95h; struct UnionFs::StackEventTracer *
0x14004e0aa  lea     r9, aUnionfsUfspath_61; "UnionFs::UfsPathTable::MoveSubtree"
0x14004e0b1  mov     [rsp+160h+var_140], rax; char *
0x14004e0b6  mov     rdx, rdi; int
0x14004e0b9  mov     ecx, esi; this
0x14004e0bb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e0c0  mov     rcx, [rsp+160h+var_F0]; this
0x14004e0c5  test    rcx, rcx
0x14004e0c8  jz      short loc_14004E0CF
0x14004e0ca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e0cf  mov     rcx, [rsp+160h+Resource]; Resource
0x14004e0d4  mov     [rsp+160h+Resource], r12
0x14004e0d9  test    rcx, rcx
0x14004e0dc  jz      short loc_14004E0F6
0x14004e0de  call    cs:__imp_ExReleaseResourceLite
0x14004e0e5  nop     dword ptr [rax+rax+00h]
0x14004e0ea  call    cs:__imp_KeLeaveCriticalRegion
0x14004e0f1  nop     dword ptr [rax+rax+00h]
0x14004e0f6  mov     rcx, [rbp+60h+var_98]; this
0x14004e0fa  test    rcx, rcx
0x14004e0fd  jz      loc_14004DF41
0x14004e103  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e108  jmp     loc_14004DF41
0x14004e10d  mov     rax, qword ptr [rbp+60h+var_C0+8]
0x14004e111  cmp     [rax+30h], r12
0x14004e115  jz      short loc_14004E12D
0x14004e117  mov     rcx, [rax+38h]; this
0x14004e11b  mov     [rax+30h], r12
0x14004e11f  mov     [rax+38h], r12
0x14004e123  test    rcx, rcx
0x14004e126  jz      short loc_14004E12D
0x14004e128  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e12d  mov     rax, qword ptr [rbp+60h+var_C0+8]
0x14004e131  cmp     [rax+40h], r12
0x14004e135  jnz     short loc_14004E171
0x14004e137  mov     [rsp+160h+var_138], r12
0x14004e13c  mov     r9, rdi
0x14004e13f  mov     r8, r14
0x14004e142  mov     dword ptr [rsp+160h+var_140], 10h
0x14004e14a  mov     rdx, r13
0x14004e14d  mov     rcx, r15
0x14004e150  call    ?Delete@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEBVUfsUnionCtx@2@@Z; UnionFs::UfsPathTable::Delete(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::UfsUnionCtx const *)
0x14004e155  mov     esi, eax
0x14004e157  test    eax, eax
0x14004e159  jns     short loc_14004E171
0x14004e15b  lea     rax, aPushPruningEmp; "PUSH: Pruning empty node"
0x14004e162  mov     r8, 5DA00140CA5h
0x14004e16c  jmp     loc_14004E0AA
0x14004e171  mov     rcx, [rsp+160h+var_F0]; this
0x14004e176  test    rcx, rcx
0x14004e179  jz      short loc_14004E180
0x14004e17b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e180  mov     rcx, [rsp+160h+Resource]; Resource
0x14004e185  mov     [rsp+160h+Resource], r12
0x14004e18a  test    rcx, rcx
0x14004e18d  jz      short loc_14004E1A7
0x14004e18f  call    cs:__imp_ExReleaseResourceLite
0x14004e196  nop     dword ptr [rax+rax+00h]
0x14004e19b  call    cs:__imp_KeLeaveCriticalRegion
0x14004e1a2  nop     dword ptr [rax+rax+00h]
0x14004e1a7  mov     rcx, [rbp+60h+var_98]; this
0x14004e1ab  test    rcx, rcx
0x14004e1ae  jz      short loc_14004E1B5
0x14004e1b0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004e1b5  lea     rcx, [rbp+60h+var_E0]; this
0x14004e1b9  call    ??1LookupResults@UnionFs@@QEAA@XZ; UnionFs::LookupResults::~LookupResults(void)
0x14004e1be  test    rbx, rbx
0x14004e1c1  jz      short loc_14004E1DE
0x14004e1c3  mov     rcx, rbx; Resource
0x14004e1c6  call    cs:__imp_ExReleaseResourceLite
0x14004e1cd  nop     dword ptr [rax+rax+00h]
0x14004e1d2  call    cs:__imp_KeLeaveCriticalRegion
0x14004e1d9  nop     dword ptr [rax+rax+00h]
0x14004e1de  xor     eax, eax
0x14004e1e0  add     rsp, 128h
0x14004e1e7  pop     r15
0x14004e1e9  pop     r14
0x14004e1eb  pop     r13
0x14004e1ed  pop     r12
0x14004e1ef  pop     rdi
0x14004e1f0  pop     rsi
0x14004e1f1  pop     rbx
0x14004e1f2  pop     rbp
0x14004e1f3  retn
```
