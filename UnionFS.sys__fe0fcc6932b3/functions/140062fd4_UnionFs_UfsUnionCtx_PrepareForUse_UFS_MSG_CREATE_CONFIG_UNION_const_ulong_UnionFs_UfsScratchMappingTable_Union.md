# UnionFs::UfsUnionCtx::PrepareForUse(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::UfsScratchMappingTable &,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x140062fd4`
- end: `0x1400634bb`
- name: `?PrepareForUse@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::UfsScratchMappingTable *, struct UnionFs::StackEventTracer *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005f38c`
- `0x14005f664`

## callees

- `0x140001b64`
- `0x1400038e8`
- `0x140006e40`
- `0x140050ef8`
- `0x140056c44`
- `0x140056c7c`
- `0x14005e010`
- `0x14005e380`
- `0x14005e5ec`
- `0x14005f1bc`
- `0x140061a00`
- `0x140062fd4`
- `0x14006383c`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x140063187`
- `ntoskrnl!KeInitializeSemaphore` at `0x140063187`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140063110`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140063110`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14006312b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14006312b`

## string_xrefs

- `0x1400631b2`: `PUSH: Configuring union`
- `0x14006332f`: `PUSH: Adding root node to path cache`
- `0x14006341a`: `PUSH: Inserting config tombstones`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::PrepareForUse(
        UnionFs::UfsUnionCtx *this,
        const struct UFS_MSG_CREATE_CONFIG_UNION *a2,
        unsigned int a3,
        struct UnionFs::UfsScratchMappingTable *a4,
        struct UnionFs::StackEventTracer *a5,
        const struct _GUID *a6)
{
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v11; // rcx
  PEX_RUNDOWN_REF_CACHE_AWARE v12; // rsi
  int inserted; // esi
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rax
  __int64 v18; // r8
  int v19; // edx
  __int64 v20; // rcx
  const struct _UNICODE_STRING *v21; // rax
  int v22; // edx
  const char *v23; // rax
  __int64 v24; // r8
  const char *v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch] BYREF
  const struct _UNICODE_STRING *v28; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  char *v31; // [rsp+88h] [rbp-78h] BYREF
  const char *v32; // [rsp+90h] [rbp-70h] BYREF
  char v33[8]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v34; // [rsp+A0h] [rbp-60h] BYREF
  char v35[32]; // [rsp+B0h] [rbp-50h] BYREF
  const char *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  const char *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  const char *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  int *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  char *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  int *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  const struct _UNICODE_STRING **v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]

  if ( (unsigned int)dword_14009E178 > 4
    && (qword_14009E188 & 0x100) != 0
    && (qword_14009E190 & 0x100) == qword_14009E190 )
  {
    LODWORD(v28) = *((_DWORD *)a2 + 3);
    v26 = *((_DWORD *)a2 + 1);
    v44 = (char *)this + 8;
    v42 = &v27;
    v48 = &v28;
    v36 = "Preparing new union for use";
    v49 = 4;
    v46 = &v26;
    v47 = 4;
    v43 = 4;
    v38 = "UnionFs::UfsUnionCtx::PrepareForUse";
    v25 = v35;
    v27 = 2889;
    v45 = 16;
    v40 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
    v41 = 41;
    v39 = 36;
    v37 = 28;
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, qword_140099908, 0, 0, 9);
  }
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x63754655u);
  v11 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 38);
  v12 = CacheAwareRundownProtection;
  if ( v11 )
    ExFreeCacheAwareRundownProtection(v11);
  *((_QWORD *)this + 38) = v12;
  if ( !v12 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a5,
      (struct UnionFs::StackEventTracer *)0x3F200200B52LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::PrepareForUse",
      "ORIGIN: Allocating rundown",
      v25);
    return 3221225626LL;
  }
  KeInitializeSemaphore((PRKSEMAPHORE)((char *)this + 312), 1, 1);
  inserted = UnionFs::UfsUnionCtx::AddScratchAndLayers(this, a2, a3, a5, a6);
  if ( inserted < 0 )
  {
    v17 = "PUSH: Configuring union";
    v18 = 0x4100200B5DLL;
    v19 = (int)a5;
LABEL_11:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inserted,
      v19,
      (struct UnionFs::StackEventTracer *)v18,
      (unsigned __int64)"UnionFs::UfsUnionCtx::PrepareForUse",
      v17,
      v25);
    return (unsigned int)inserted;
  }
  v20 = **((_QWORD **)this + 6);
  v34 = *(_OWORD *)*(_QWORD *)(v20 + 16);
  if ( (unsigned int)dword_14009E178 > 4 )
  {
    v20 = qword_14009E190;
    if ( (qword_14009E188 & 0x100) != 0 && (qword_14009E190 & 0x100) == qword_14009E190 )
    {
      v21 = (const struct _UNICODE_STRING *)&v34;
      v26 = 2917;
      if ( !*((_QWORD *)&v34 + 1) )
        v21 = &FsTlEmptyUnicodeString;
      v28 = v21;
      v30 = *((_QWORD *)this + 4);
      v27 = *((_DWORD *)this + 7);
      v31 = (char *)this + 8;
      v32 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
      *(_QWORD *)v33 = "UnionFs::UfsUnionCtx::PrepareForUse";
      v29[0] = "New union scratch root";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (unsigned int)&FsTlEmptyUnicodeString,
        (unsigned int)&dword_1400996C4,
        v15,
        v16,
        (__int64)v29,
        (__int64)v33,
        (__int64)&v32,
        (__int64)&v26,
        (__int64)&v31,
        (__int64)&v27,
        (__int64)&v30,
        (__int64)&v28);
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)this + 8LL));
  v29[1] = *(_QWORD *)this;
  v29[0] = this;
  inserted = UnionFs::UnionFsFilter::AddUnionToGlobalMap(v20, v29, a5);
  v19 = (int)a5;
  if ( inserted < 0 )
  {
    v17 = "PUSH: Storing union context on lookup table";
    v18 = 0x24B00200B6CLL;
    goto LABEL_11;
  }
  inserted = UnionFs::UfsUnionCtx::AddRootNodeToPathCache(this, a5);
  v22 = (int)a5;
  if ( inserted < 0 )
  {
    v23 = "PUSH: Adding root node to path cache";
    v24 = 0x47D00200B76LL;
LABEL_23:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inserted,
      v22,
      (struct UnionFs::StackEventTracer *)v24,
      (unsigned __int64)"UnionFs::UfsUnionCtx::PrepareForUse",
      v23,
      v25);
    v46 = 0;
    UnionFs::UfsUnionCtx::RemoveUnion(this, 4, a5, (__int64)v35);
    return (unsigned int)inserted;
  }
  inserted = UnionFs::UfsUnionCtx::AddRootNodeToEaTable(this, a5);
  if ( inserted < 0 )
  {
    v23 = "PUSH: Adding root node to EA table";
    v24 = 0x56100200B7CLL;
LABEL_26:
    v22 = (int)a5;
    goto LABEL_23;
  }
  if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
  {
    inserted = UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile(
                 *((UnionFs::UfsPersistenceManager **)UnionFs::g_FilterState + 15),
                 this,
                 a5,
                 0);
    if ( inserted < 0 )
    {
      v23 = "PUSH: Clearing persisted tombstones";
      v24 = 0x1A00200B8DLL;
      goto LABEL_26;
    }
    if ( *((_DWORD *)a2 + 3) )
    {
      inserted = UnionFs::UfsUnionCtx::InsertTombstonesFromConfig(this, a2, a3, a5);
      if ( inserted < 0 )
      {
        v23 = "PUSH: Inserting config tombstones";
        v24 = 0x1B00200B95LL;
        goto LABEL_26;
      }
    }
  }
  else
  {
    inserted = (***((__int64 (__fastcall ****)(_QWORD, UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *))UnionFs::g_FilterState
                  + 15))(
                 *((_QWORD *)UnionFs::g_FilterState + 15),
                 this,
                 a5);
    if ( inserted < 0 )
    {
      v23 = "PUSH: Restoring persisted tombstones.";
      v24 = 0x1400200B84LL;
      goto LABEL_26;
    }
  }
  inserted = (***((__int64 (__fastcall ****)(_QWORD, UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *))UnionFs::g_FilterState
                + 16))(
               *((_QWORD *)UnionFs::g_FilterState + 16),
               this,
               a5);
  if ( inserted < 0 )
  {
    v23 = "PUSH: Restoring persisted EA payloads.";
    v24 = 0x67500200B9DLL;
    goto LABEL_26;
  }
  inserted = UnionFs::UfsUnionCtx::AddScratchToMappingTable(this, a4, a5, 0);
  if ( inserted < 0 )
  {
    v23 = "PUSH: Adding new union scratch to mapping table";
    v24 = 0x24C00200BA4LL;
    goto LABEL_26;
  }
  return 0;
}

```

## disassembly

```asm
0x140062fd4  push    rbp
0x140062fd6  push    rbx
0x140062fd7  push    rsi
0x140062fd8  push    rdi
0x140062fd9  push    r12
0x140062fdb  push    r13
0x140062fdd  push    r14
0x140062fdf  push    r15
0x140062fe1  lea     rbp, [rsp-58h]
0x140062fe6  sub     rsp, 158h
0x140062fed  mov     rax, cs:__security_cookie
0x140062ff4  xor     rax, rsp
0x140062ff7  mov     [rbp+90h+var_50], rax
0x140062ffb  mov     eax, cs:dword_14009E178
0x140063001  lea     r11, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x140063008  mov     rbx, [rbp+90h+arg_20]
0x14006300f  mov     r13, r9
0x140063012  mov     r15, [rbp+90h+arg_28]
0x140063019  mov     r9d, 4
0x14006301f  mov     r12d, r8d
0x140063022  mov     r14, rdx
0x140063025  lea     r8, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x14006302c  mov     rdi, rcx
0x14006302f  mov     r10d, 100h
0x140063035  cmp     eax, r9d
0x140063038  jbe     loc_140063106
0x14006303e  mov     rcx, cs:qword_14009E190
0x140063045  mov     rax, cs:qword_14009E188
0x14006304c  test    r10, rax
0x14006304f  jz      loc_140063106
0x140063055  mov     rax, rcx
0x140063058  and     rax, r10
0x14006305b  cmp     rax, rcx
0x14006305e  jnz     loc_140063106
0x140063064  mov     eax, [rdx+0Ch]
0x140063067  lea     rcx, [rsp+190h+var_128]
0x14006306c  mov     dword ptr [rsp+190h+var_128], eax
0x140063070  mov     eax, [rdx+4]
0x140063073  lea     rdx, qword_140099908
0x14006307a  mov     [rsp+190h+var_130], eax
0x14006307e  lea     rax, [rdi+8]
0x140063082  mov     [rbp+90h+var_80], rax
0x140063086  lea     rax, [rsp+190h+var_12C]
0x14006308b  mov     [rbp+90h+var_90], rax
0x14006308f  lea     rax, aPreparingNewUn; "Preparing new union for use"
0x140063096  mov     [rbp+90h+var_60], rcx
0x14006309a  lea     rcx, [rsp+190h+var_130]
0x14006309f  mov     [rbp+90h+var_C0], rax
0x1400630a3  lea     rax, [rbp+90h+var_E0]
0x1400630a7  mov     [rbp+90h+var_58], r9
0x1400630ab  mov     [rbp+90h+var_70], rcx
0x1400630af  lea     rcx, dword_14009E178
0x1400630b6  mov     [rbp+90h+var_68], r9
0x1400630ba  mov     [rbp+90h+var_88], r9
0x1400630be  xor     r9d, r9d
0x1400630c1  mov     [rbp+90h+var_B0], r8
0x1400630c5  xor     r8d, r8d
0x1400630c8  mov     [rsp+190h+var_168], rax; char *
0x1400630cd  mov     dword ptr [rsp+190h+var_170], 9
0x1400630d5  mov     [rsp+190h+var_12C], 0B49h
0x1400630dd  mov     [rbp+90h+var_78], 10h
0x1400630e5  mov     [rbp+90h+var_A0], r11
0x1400630e9  mov     [rbp+90h+var_98], 29h ; ')'
0x1400630f1  mov     [rbp+90h+var_A8], 24h ; '$'
0x1400630f9  mov     [rbp+90h+var_B8], 1Ch
0x140063101  call    _tlgWriteTransfer_EtwWriteTransfer
0x140063106  mov     edx, 63754655h; PoolTag
0x14006310b  mov     ecx, 200h; PoolType
0x140063110  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140063117  nop     dword ptr [rax+rax+00h]
0x14006311c  mov     rcx, [rdi+130h]; RunRefCacheAware
0x140063123  mov     rsi, rax
0x140063126  test    rcx, rcx
0x140063129  jz      short loc_140063137
0x14006312b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140063132  nop     dword ptr [rax+rax+00h]
0x140063137  mov     [rdi+130h], rsi
0x14006313e  test    rsi, rsi
0x140063141  jnz     short loc_140063176
0x140063143  mov     rdx, rbx; int
0x140063146  lea     rax, aOriginAllocati_76; "ORIGIN: Allocating rundown"
0x14006314d  mov     ebx, 0C000009Ah
0x140063152  mov     [rsp+190h+var_170], rax; char *
0x140063157  mov     ecx, ebx; this
0x140063159  lea     r9, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x140063160  mov     r8, 3F200200B52h; struct UnionFs::StackEventTracer *
0x14006316a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006316f  mov     eax, ebx
0x140063171  jmp     loc_14006349A
0x140063176  mov     eax, 1
0x14006317b  lea     rcx, [rdi+138h]; Semaphore
0x140063182  mov     r8d, eax; Limit
0x140063185  mov     edx, eax; Count
0x140063187  call    cs:__imp_KeInitializeSemaphore
0x14006318e  nop     dword ptr [rax+rax+00h]
0x140063193  mov     r9, rbx; struct UnionFs::StackEventTracer *
0x140063196  mov     [rsp+190h+var_170], r15; struct _GUID *
0x14006319b  mov     r8d, r12d; unsigned int
0x14006319e  mov     rdx, r14; struct UFS_MSG_CREATE_CONFIG_UNION *
0x1400631a1  mov     rcx, rdi; this
0x1400631a4  call    ?AddScratchAndLayers@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@PEBU_GUID@@@Z; UnionFs::UfsUnionCtx::AddScratchAndLayers(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &,_GUID const *)
0x1400631a9  xor     r15d, r15d
0x1400631ac  mov     esi, eax
0x1400631ae  test    eax, eax
0x1400631b0  jns     short loc_1400631E0
0x1400631b2  lea     rax, aPushConfigurin; "PUSH: Configuring union"
0x1400631b9  mov     r8, 4100200B5Dh; struct UnionFs::StackEventTracer *
0x1400631c3  mov     rdx, rbx; int
0x1400631c6  lea     r9, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x1400631cd  mov     [rsp+190h+var_170], rax; char *
0x1400631d2  mov     ecx, esi; this
0x1400631d4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400631d9  mov     eax, esi
0x1400631db  jmp     loc_14006349A
0x1400631e0  mov     rax, [rdi+30h]
0x1400631e4  mov     rcx, [rax]
0x1400631e7  mov     rax, [rcx+10h]
0x1400631eb  movups  xmm0, xmmword ptr [rax]
0x1400631ee  mov     eax, cs:dword_14009E178
0x1400631f4  movdqu  [rbp+90h+var_F0], xmm0
0x1400631f9  cmp     eax, 4
0x1400631fc  jbe     loc_1400632DE
0x140063202  mov     rcx, cs:qword_14009E190
0x140063209  mov     edx, 100h
0x14006320e  mov     rax, cs:qword_14009E188
0x140063215  test    rdx, rax
0x140063218  jz      loc_1400632DE
0x14006321e  mov     rax, rcx
0x140063221  and     rax, rdx
0x140063224  cmp     rax, rcx
0x140063227  jnz     loc_1400632DE
0x14006322d  cmp     qword ptr [rbp+90h+var_F0+8], r15
0x140063231  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x140063238  lea     rax, [rbp+90h+var_F0]
0x14006323c  mov     [rsp+190h+var_130], 0B65h
0x140063244  cmovz   rax, rcx
0x140063248  lea     rdx, dword_1400996C4
0x14006324f  mov     [rsp+190h+var_128], rax
0x140063254  mov     rax, [rdi+20h]
0x140063258  mov     [rbp+90h+var_110], rax
0x14006325c  mov     eax, [rdi+1Ch]
0x14006325f  mov     [rsp+190h+var_12C], eax
0x140063263  lea     rax, [rdi+8]
0x140063267  mov     [rbp+90h+var_108], rax
0x14006326b  lea     rax, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x140063272  mov     [rbp+90h+var_100], rax
0x140063276  lea     rax, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x14006327d  mov     qword ptr [rbp+90h+var_F8], rax
0x140063281  lea     rax, aNewUnionScratc; "New union scratch root"
0x140063288  mov     [rsp+190h+var_120], rax
0x14006328d  lea     rax, [rsp+190h+var_128]
0x140063292  mov     [rsp+190h+var_138], rax
0x140063297  lea     rax, [rbp+90h+var_110]
0x14006329b  mov     [rsp+190h+var_140], rax
0x1400632a0  lea     rax, [rsp+190h+var_12C]
0x1400632a5  mov     [rsp+190h+var_148], rax
0x1400632aa  lea     rax, [rbp+90h+var_108]
0x1400632ae  mov     [rsp+190h+var_150], rax
0x1400632b3  lea     rax, [rsp+190h+var_130]
0x1400632b8  mov     [rsp+190h+var_158], rax
0x1400632bd  lea     rax, [rbp+90h+var_100]
0x1400632c1  mov     [rsp+190h+var_160], rax
0x1400632c6  lea     rax, [rbp+90h+var_F8]
0x1400632ca  mov     [rsp+190h+var_168], rax; char *
0x1400632cf  lea     rax, [rsp+190h+var_120]
0x1400632d4  mov     [rsp+190h+var_170], rax
0x1400632d9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x1400632de  mov     rax, [rdi]
0x1400632e1  lock inc dword ptr [rax+8]
0x1400632e5  mov     rax, [rdi]
0x1400632e8  lea     rdx, [rsp+190h+var_120]
0x1400632ed  mov     r8, rbx
0x1400632f0  mov     [rsp+190h+var_118], rax
0x1400632f5  mov     [rsp+190h+var_120], rdi
0x1400632fa  call    ?AddUnionToGlobalMap@UnionFsFilter@UnionFs@@QEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::AddUnionToGlobalMap(utl::shared_ptr<UnionFs::UfsUnionCtx>,UnionFs::StackEventTracer &)
0x1400632ff  mov     esi, eax
0x140063301  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x140063304  test    eax, eax
0x140063306  jns     short loc_14006331E
0x140063308  lea     rax, aPushStoringUni; "PUSH: Storing union context on lookup t"...
0x14006330f  mov     r8, 24B00200B6Ch
0x140063319  jmp     loc_1400631C6
0x14006331e  mov     rcx, rdi; this
0x140063321  call    ?AddRootNodeToPathCache@UfsUnionCtx@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::AddRootNodeToPathCache(UnionFs::StackEventTracer &)
0x140063326  mov     esi, eax
0x140063328  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x14006332b  test    eax, eax
0x14006332d  jns     short loc_140063370
0x14006332f  lea     rax, aPushAddingRoot_0; "PUSH: Adding root node to path cache"
0x140063336  mov     r8, 47D00200B76h; struct UnionFs::StackEventTracer *
0x140063340  lea     r9, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x140063347  mov     [rsp+190h+var_170], rax; char *
0x14006334c  mov     ecx, esi; this
0x14006334e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063353  lea     r9, [rbp+90h+var_E0]
0x140063357  mov     [rbp+90h+var_70], r15
0x14006335b  mov     r8, rbx
0x14006335e  mov     edx, 4
0x140063363  mov     rcx, rdi; struct UnionFs::UfsUnionCtx *
0x140063366  call    ?RemoveUnion@UfsUnionCtx@UnionFs@@QEAAJW4RemoveUnionReason@12@AEAVStackEventTracer@2@V?$function@$$A6AJAEAVUfsUnionCtx@UnionFs@@PEA_NAEAVStackEventTracer@2@@Z@wistd@@@Z; UnionFs::UfsUnionCtx::RemoveUnion(UnionFs::UfsUnionCtx::RemoveUnionReason,UnionFs::StackEventTracer &,wistd::function<long (UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)>)
0x14006336b  jmp     loc_1400631D9
0x140063370  mov     rcx, rdi; this
0x140063373  call    ?AddRootNodeToEaTable@UfsUnionCtx@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::AddRootNodeToEaTable(UnionFs::StackEventTracer &)
0x140063378  mov     esi, eax
0x14006337a  test    eax, eax
0x14006337c  jns     short loc_140063394
0x14006337e  lea     rax, aPushAddingRoot; "PUSH: Adding root node to EA table"
0x140063385  mov     r8, 56100200B7Ch
0x14006338f  mov     rdx, rbx
0x140063392  jmp     short loc_140063340
0x140063394  mov     eax, [r14+4]
0x140063398  mov     r8, rbx; struct UnionFs::StackEventTracer *
0x14006339b  mov     rdx, rdi; struct UnionFs::UfsUnionCtx *
0x14006339e  test    al, 1
0x1400633a0  jnz     short loc_1400633D1
0x1400633a2  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400633a9  mov     rcx, [rax+78h]
0x1400633ad  mov     rax, [rcx]
0x1400633b0  mov     rax, [rax]
0x1400633b3  call    _guard_dispatch_icall
0x1400633b8  mov     esi, eax
0x1400633ba  test    eax, eax
0x1400633bc  jns     short loc_140063430
0x1400633be  lea     rax, aPushRestoringP; "PUSH: Restoring persisted tombstones."
0x1400633c5  mov     r8, 1400200B84h
0x1400633cf  jmp     short loc_14006338F
0x1400633d1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400633d8  xor     r9d, r9d; bool
0x1400633db  mov     rcx, [rcx+78h]; this
0x1400633df  call    ?ClearPersistedPayloadFile@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile(UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &,bool)
0x1400633e4  mov     esi, eax
0x1400633e6  test    eax, eax
0x1400633e8  jns     short loc_1400633FD
0x1400633ea  lea     rax, aPushClearingPe_2; "PUSH: Clearing persisted tombstones"
0x1400633f1  mov     r8, 1A00200B8Dh
0x1400633fb  jmp     short loc_14006338F
0x1400633fd  cmp     [r14+0Ch], r15d
0x140063401  jbe     short loc_140063430
0x140063403  mov     r9, rbx; struct UnionFs::StackEventTracer *
0x140063406  mov     r8d, r12d; unsigned int
0x140063409  mov     rdx, r14; struct UFS_MSG_CREATE_CONFIG_UNION *
0x14006340c  mov     rcx, rdi; this
0x14006340f  call    ?InsertTombstonesFromConfig@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::InsertTombstonesFromConfig(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &)
0x140063414  mov     esi, eax
0x140063416  test    eax, eax
0x140063418  jns     short loc_140063430
0x14006341a  lea     rax, aPushInsertingC; "PUSH: Inserting config tombstones"
0x140063421  mov     r8, 1B00200B95h
0x14006342b  jmp     loc_14006338F
0x140063430  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140063437  mov     r8, rbx
0x14006343a  mov     rdx, rdi
0x14006343d  mov     rcx, [rax+80h]
0x140063444  mov     rax, [rcx]
0x140063447  mov     rax, [rax]
0x14006344a  call    _guard_dispatch_icall
0x14006344f  mov     esi, eax
0x140063451  test    eax, eax
0x140063453  jns     short loc_14006346B
0x140063455  lea     rax, aPushRestoringP_0; "PUSH: Restoring persisted EA payloads."
0x14006345c  mov     r8, 67500200B9Dh
0x140063466  jmp     loc_14006338F
0x14006346b  xor     r9d, r9d; bool
0x14006346e  mov     r8, rbx; struct UnionFs::StackEventTracer *
0x140063471  mov     rdx, r13; struct UnionFs::UfsScratchMappingTable *
0x140063474  mov     rcx, rdi; this
0x140063477  call    ?AddScratchToMappingTable@UfsUnionCtx@UnionFs@@AEAAJAEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsUnionCtx::AddScratchToMappingTable(UnionFs::UfsScratchMappingTable &,UnionFs::StackEventTracer &,bool)
0x14006347c  mov     esi, eax
0x14006347e  test    eax, eax
0x140063480  jns     short loc_140063498
0x140063482  lea     rax, aPushAddingNewU; "PUSH: Adding new union scratch to mappi"...
0x140063489  mov     r8, 24C00200BA4h
0x140063493  jmp     loc_14006338F
0x140063498  xor     eax, eax
0x14006349a  mov     rcx, [rbp+90h+var_50]
0x14006349e  xor     rcx, rsp; StackCookie
0x1400634a1  call    __security_check_cookie
0x1400634a6  add     rsp, 158h
0x1400634ad  pop     r15
0x1400634af  pop     r14
0x1400634b1  pop     r13
0x1400634b3  pop     r12
0x1400634b5  pop     rdi
0x1400634b6  pop     rsi
0x1400634b7  pop     rbx
0x1400634b8  pop     rbp
0x1400634b9  retn
```
