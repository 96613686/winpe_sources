# UnionFs::UfsUnionCtx::PrepareForUse(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::UfsScratchMappingTable &,UnionFs::StackEventTracer &,_GUID const *)

- ea: `0x140062e54`
- end: `0x14006333b`
- name: `?PrepareForUse@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEBU_GUID@@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *__hidden this, const struct UFS_MSG_CREATE_CONFIG_UNION *, unsigned int, struct UnionFs::UfsScratchMappingTable *, struct UnionFs::StackEventTracer *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005f20c`
- `0x14005f4e4`

## callees

- `0x140001b64`
- `0x1400038e8`
- `0x140006e40`
- `0x140050d78`
- `0x140056ac4`
- `0x140056afc`
- `0x14005de90`
- `0x14005e200`
- `0x14005e46c`
- `0x14005f03c`
- `0x140061880`
- `0x140062e54`
- `0x1400636bc`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x140063007`
- `ntoskrnl!KeInitializeSemaphore` at `0x140063007`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140062f90`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140062f90`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140062fab`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140062fab`

## string_xrefs

- `0x140063032`: `PUSH: Configuring union`
- `0x1400631af`: `PUSH: Adding root node to path cache`
- `0x14006329a`: `PUSH: Inserting config tombstones`

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
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, qword_140099888, 0, 0, 9);
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
        (unsigned int)&dword_140099644,
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
0x140062e54  push    rbp
0x140062e56  push    rbx
0x140062e57  push    rsi
0x140062e58  push    rdi
0x140062e59  push    r12
0x140062e5b  push    r13
0x140062e5d  push    r14
0x140062e5f  push    r15
0x140062e61  lea     rbp, [rsp-58h]
0x140062e66  sub     rsp, 158h
0x140062e6d  mov     rax, cs:__security_cookie
0x140062e74  xor     rax, rsp
0x140062e77  mov     [rbp+90h+var_50], rax
0x140062e7b  mov     eax, cs:dword_14009E178
0x140062e81  lea     r11, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x140062e88  mov     rbx, [rbp+90h+arg_20]
0x140062e8f  mov     r13, r9
0x140062e92  mov     r15, [rbp+90h+arg_28]
0x140062e99  mov     r9d, 4
0x140062e9f  mov     r12d, r8d
0x140062ea2  mov     r14, rdx
0x140062ea5  lea     r8, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x140062eac  mov     rdi, rcx
0x140062eaf  mov     r10d, 100h
0x140062eb5  cmp     eax, r9d
0x140062eb8  jbe     loc_140062F86
0x140062ebe  mov     rcx, cs:qword_14009E190
0x140062ec5  mov     rax, cs:qword_14009E188
0x140062ecc  test    r10, rax
0x140062ecf  jz      loc_140062F86
0x140062ed5  mov     rax, rcx
0x140062ed8  and     rax, r10
0x140062edb  cmp     rax, rcx
0x140062ede  jnz     loc_140062F86
0x140062ee4  mov     eax, [rdx+0Ch]
0x140062ee7  lea     rcx, [rsp+190h+var_128]
0x140062eec  mov     dword ptr [rsp+190h+var_128], eax
0x140062ef0  mov     eax, [rdx+4]
0x140062ef3  lea     rdx, qword_140099888
0x140062efa  mov     [rsp+190h+var_130], eax
0x140062efe  lea     rax, [rdi+8]
0x140062f02  mov     [rbp+90h+var_80], rax
0x140062f06  lea     rax, [rsp+190h+var_12C]
0x140062f0b  mov     [rbp+90h+var_90], rax
0x140062f0f  lea     rax, aPreparingNewUn; "Preparing new union for use"
0x140062f16  mov     [rbp+90h+var_60], rcx
0x140062f1a  lea     rcx, [rsp+190h+var_130]
0x140062f1f  mov     [rbp+90h+var_C0], rax
0x140062f23  lea     rax, [rbp+90h+var_E0]
0x140062f27  mov     [rbp+90h+var_58], r9
0x140062f2b  mov     [rbp+90h+var_70], rcx
0x140062f2f  lea     rcx, dword_14009E178
0x140062f36  mov     [rbp+90h+var_68], r9
0x140062f3a  mov     [rbp+90h+var_88], r9
0x140062f3e  xor     r9d, r9d
0x140062f41  mov     [rbp+90h+var_B0], r8
0x140062f45  xor     r8d, r8d
0x140062f48  mov     [rsp+190h+var_168], rax; char *
0x140062f4d  mov     dword ptr [rsp+190h+var_170], 9
0x140062f55  mov     [rsp+190h+var_12C], 0B49h
0x140062f5d  mov     [rbp+90h+var_78], 10h
0x140062f65  mov     [rbp+90h+var_A0], r11
0x140062f69  mov     [rbp+90h+var_98], 29h ; ')'
0x140062f71  mov     [rbp+90h+var_A8], 24h ; '$'
0x140062f79  mov     [rbp+90h+var_B8], 1Ch
0x140062f81  call    _tlgWriteTransfer_EtwWriteTransfer
0x140062f86  mov     edx, 63754655h; PoolTag
0x140062f8b  mov     ecx, 200h; PoolType
0x140062f90  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140062f97  nop     dword ptr [rax+rax+00h]
0x140062f9c  mov     rcx, [rdi+130h]; RunRefCacheAware
0x140062fa3  mov     rsi, rax
0x140062fa6  test    rcx, rcx
0x140062fa9  jz      short loc_140062FB7
0x140062fab  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140062fb2  nop     dword ptr [rax+rax+00h]
0x140062fb7  mov     [rdi+130h], rsi
0x140062fbe  test    rsi, rsi
0x140062fc1  jnz     short loc_140062FF6
0x140062fc3  mov     rdx, rbx; int
0x140062fc6  lea     rax, aOriginAllocati_75; "ORIGIN: Allocating rundown"
0x140062fcd  mov     ebx, 0C000009Ah
0x140062fd2  mov     [rsp+190h+var_170], rax; char *
0x140062fd7  mov     ecx, ebx; this
0x140062fd9  lea     r9, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x140062fe0  mov     r8, 3F200200B52h; struct UnionFs::StackEventTracer *
0x140062fea  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062fef  mov     eax, ebx
0x140062ff1  jmp     loc_14006331A
0x140062ff6  mov     eax, 1
0x140062ffb  lea     rcx, [rdi+138h]; Semaphore
0x140063002  mov     r8d, eax; Limit
0x140063005  mov     edx, eax; Count
0x140063007  call    cs:__imp_KeInitializeSemaphore
0x14006300e  nop     dword ptr [rax+rax+00h]
0x140063013  mov     r9, rbx; struct UnionFs::StackEventTracer *
0x140063016  mov     [rsp+190h+var_170], r15; struct _GUID *
0x14006301b  mov     r8d, r12d; unsigned int
0x14006301e  mov     rdx, r14; struct UFS_MSG_CREATE_CONFIG_UNION *
0x140063021  mov     rcx, rdi; this
0x140063024  call    ?AddScratchAndLayers@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@PEBU_GUID@@@Z; UnionFs::UfsUnionCtx::AddScratchAndLayers(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &,_GUID const *)
0x140063029  xor     r15d, r15d
0x14006302c  mov     esi, eax
0x14006302e  test    eax, eax
0x140063030  jns     short loc_140063060
0x140063032  lea     rax, aPushConfigurin; "PUSH: Configuring union"
0x140063039  mov     r8, 4100200B5Dh; struct UnionFs::StackEventTracer *
0x140063043  mov     rdx, rbx; int
0x140063046  lea     r9, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x14006304d  mov     [rsp+190h+var_170], rax; char *
0x140063052  mov     ecx, esi; this
0x140063054  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063059  mov     eax, esi
0x14006305b  jmp     loc_14006331A
0x140063060  mov     rax, [rdi+30h]
0x140063064  mov     rcx, [rax]
0x140063067  mov     rax, [rcx+10h]
0x14006306b  movups  xmm0, xmmword ptr [rax]
0x14006306e  mov     eax, cs:dword_14009E178
0x140063074  movdqu  [rbp+90h+var_F0], xmm0
0x140063079  cmp     eax, 4
0x14006307c  jbe     loc_14006315E
0x140063082  mov     rcx, cs:qword_14009E190
0x140063089  mov     edx, 100h
0x14006308e  mov     rax, cs:qword_14009E188
0x140063095  test    rdx, rax
0x140063098  jz      loc_14006315E
0x14006309e  mov     rax, rcx
0x1400630a1  and     rax, rdx
0x1400630a4  cmp     rax, rcx
0x1400630a7  jnz     loc_14006315E
0x1400630ad  cmp     qword ptr [rbp+90h+var_F0+8], r15
0x1400630b1  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x1400630b8  lea     rax, [rbp+90h+var_F0]
0x1400630bc  mov     [rsp+190h+var_130], 0B65h
0x1400630c4  cmovz   rax, rcx
0x1400630c8  lea     rdx, dword_140099644
0x1400630cf  mov     [rsp+190h+var_128], rax
0x1400630d4  mov     rax, [rdi+20h]
0x1400630d8  mov     [rbp+90h+var_110], rax
0x1400630dc  mov     eax, [rdi+1Ch]
0x1400630df  mov     [rsp+190h+var_12C], eax
0x1400630e3  lea     rax, [rdi+8]
0x1400630e7  mov     [rbp+90h+var_108], rax
0x1400630eb  lea     rax, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x1400630f2  mov     [rbp+90h+var_100], rax
0x1400630f6  lea     rax, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x1400630fd  mov     qword ptr [rbp+90h+var_F8], rax
0x140063101  lea     rax, aNewUnionScratc; "New union scratch root"
0x140063108  mov     [rsp+190h+var_120], rax
0x14006310d  lea     rax, [rsp+190h+var_128]
0x140063112  mov     [rsp+190h+var_138], rax
0x140063117  lea     rax, [rbp+90h+var_110]
0x14006311b  mov     [rsp+190h+var_140], rax
0x140063120  lea     rax, [rsp+190h+var_12C]
0x140063125  mov     [rsp+190h+var_148], rax
0x14006312a  lea     rax, [rbp+90h+var_108]
0x14006312e  mov     [rsp+190h+var_150], rax
0x140063133  lea     rax, [rsp+190h+var_130]
0x140063138  mov     [rsp+190h+var_158], rax
0x14006313d  lea     rax, [rbp+90h+var_100]
0x140063141  mov     [rsp+190h+var_160], rax
0x140063146  lea     rax, [rbp+90h+var_F8]
0x14006314a  mov     [rsp+190h+var_168], rax; char *
0x14006314f  lea     rax, [rsp+190h+var_120]
0x140063154  mov     [rsp+190h+var_170], rax
0x140063159  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14006315e  mov     rax, [rdi]
0x140063161  lock inc dword ptr [rax+8]
0x140063165  mov     rax, [rdi]
0x140063168  lea     rdx, [rsp+190h+var_120]
0x14006316d  mov     r8, rbx
0x140063170  mov     [rsp+190h+var_118], rax
0x140063175  mov     [rsp+190h+var_120], rdi
0x14006317a  call    ?AddUnionToGlobalMap@UnionFsFilter@UnionFs@@QEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::AddUnionToGlobalMap(utl::shared_ptr<UnionFs::UfsUnionCtx>,UnionFs::StackEventTracer &)
0x14006317f  mov     esi, eax
0x140063181  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x140063184  test    eax, eax
0x140063186  jns     short loc_14006319E
0x140063188  lea     rax, aPushStoringUni; "PUSH: Storing union context on lookup t"...
0x14006318f  mov     r8, 24B00200B6Ch
0x140063199  jmp     loc_140063046
0x14006319e  mov     rcx, rdi; this
0x1400631a1  call    ?AddRootNodeToPathCache@UfsUnionCtx@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::AddRootNodeToPathCache(UnionFs::StackEventTracer &)
0x1400631a6  mov     esi, eax
0x1400631a8  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x1400631ab  test    eax, eax
0x1400631ad  jns     short loc_1400631F0
0x1400631af  lea     rax, aPushAddingRoot_0; "PUSH: Adding root node to path cache"
0x1400631b6  mov     r8, 47D00200B76h; struct UnionFs::StackEventTracer *
0x1400631c0  lea     r9, aUnionfsUfsunio_8; "UnionFs::UfsUnionCtx::PrepareForUse"
0x1400631c7  mov     [rsp+190h+var_170], rax; char *
0x1400631cc  mov     ecx, esi; this
0x1400631ce  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400631d3  lea     r9, [rbp+90h+var_E0]
0x1400631d7  mov     [rbp+90h+var_70], r15
0x1400631db  mov     r8, rbx
0x1400631de  mov     edx, 4
0x1400631e3  mov     rcx, rdi; struct UnionFs::UfsUnionCtx *
0x1400631e6  call    ?RemoveUnion@UfsUnionCtx@UnionFs@@QEAAJW4RemoveUnionReason@12@AEAVStackEventTracer@2@V?$function@$$A6AJAEAVUfsUnionCtx@UnionFs@@PEA_NAEAVStackEventTracer@2@@Z@wistd@@@Z; UnionFs::UfsUnionCtx::RemoveUnion(UnionFs::UfsUnionCtx::RemoveUnionReason,UnionFs::StackEventTracer &,wistd::function<long (UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)>)
0x1400631eb  jmp     loc_140063059
0x1400631f0  mov     rcx, rdi; this
0x1400631f3  call    ?AddRootNodeToEaTable@UfsUnionCtx@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::AddRootNodeToEaTable(UnionFs::StackEventTracer &)
0x1400631f8  mov     esi, eax
0x1400631fa  test    eax, eax
0x1400631fc  jns     short loc_140063214
0x1400631fe  lea     rax, aPushAddingRoot; "PUSH: Adding root node to EA table"
0x140063205  mov     r8, 56100200B7Ch
0x14006320f  mov     rdx, rbx
0x140063212  jmp     short loc_1400631C0
0x140063214  mov     eax, [r14+4]
0x140063218  mov     r8, rbx; struct UnionFs::StackEventTracer *
0x14006321b  mov     rdx, rdi; struct UnionFs::UfsUnionCtx *
0x14006321e  test    al, 1
0x140063220  jnz     short loc_140063251
0x140063222  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140063229  mov     rcx, [rax+78h]
0x14006322d  mov     rax, [rcx]
0x140063230  mov     rax, [rax]
0x140063233  call    _guard_dispatch_icall
0x140063238  mov     esi, eax
0x14006323a  test    eax, eax
0x14006323c  jns     short loc_1400632B0
0x14006323e  lea     rax, aPushRestoringP; "PUSH: Restoring persisted tombstones."
0x140063245  mov     r8, 1400200B84h
0x14006324f  jmp     short loc_14006320F
0x140063251  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140063258  xor     r9d, r9d; bool
0x14006325b  mov     rcx, [rcx+78h]; this
0x14006325f  call    ?ClearPersistedPayloadFile@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile(UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &,bool)
0x140063264  mov     esi, eax
0x140063266  test    eax, eax
0x140063268  jns     short loc_14006327D
0x14006326a  lea     rax, aPushClearingPe_2; "PUSH: Clearing persisted tombstones"
0x140063271  mov     r8, 1A00200B8Dh
0x14006327b  jmp     short loc_14006320F
0x14006327d  cmp     [r14+0Ch], r15d
0x140063281  jbe     short loc_1400632B0
0x140063283  mov     r9, rbx; struct UnionFs::StackEventTracer *
0x140063286  mov     r8d, r12d; unsigned int
0x140063289  mov     rdx, r14; struct UFS_MSG_CREATE_CONFIG_UNION *
0x14006328c  mov     rcx, rdi; this
0x14006328f  call    ?InsertTombstonesFromConfig@UfsUnionCtx@UnionFs@@AEAAJAEBUUFS_MSG_CREATE_CONFIG_UNION@@KAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::InsertTombstonesFromConfig(UFS_MSG_CREATE_CONFIG_UNION const &,ulong,UnionFs::StackEventTracer &)
0x140063294  mov     esi, eax
0x140063296  test    eax, eax
0x140063298  jns     short loc_1400632B0
0x14006329a  lea     rax, aPushInsertingC; "PUSH: Inserting config tombstones"
0x1400632a1  mov     r8, 1B00200B95h
0x1400632ab  jmp     loc_14006320F
0x1400632b0  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400632b7  mov     r8, rbx
0x1400632ba  mov     rdx, rdi
0x1400632bd  mov     rcx, [rax+80h]
0x1400632c4  mov     rax, [rcx]
0x1400632c7  mov     rax, [rax]
0x1400632ca  call    _guard_dispatch_icall
0x1400632cf  mov     esi, eax
0x1400632d1  test    eax, eax
0x1400632d3  jns     short loc_1400632EB
0x1400632d5  lea     rax, aPushRestoringP_0; "PUSH: Restoring persisted EA payloads."
0x1400632dc  mov     r8, 67500200B9Dh
0x1400632e6  jmp     loc_14006320F
0x1400632eb  xor     r9d, r9d; bool
0x1400632ee  mov     r8, rbx; struct UnionFs::StackEventTracer *
0x1400632f1  mov     rdx, r13; struct UnionFs::UfsScratchMappingTable *
0x1400632f4  mov     rcx, rdi; this
0x1400632f7  call    ?AddScratchToMappingTable@UfsUnionCtx@UnionFs@@AEAAJAEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsUnionCtx::AddScratchToMappingTable(UnionFs::UfsScratchMappingTable &,UnionFs::StackEventTracer &,bool)
0x1400632fc  mov     esi, eax
0x1400632fe  test    eax, eax
0x140063300  jns     short loc_140063318
0x140063302  lea     rax, aPushAddingNewU; "PUSH: Adding new union scratch to mappi"...
0x140063309  mov     r8, 24C00200BA4h
0x140063313  jmp     loc_14006320F
0x140063318  xor     eax, eax
0x14006331a  mov     rcx, [rbp+90h+var_50]
0x14006331e  xor     rcx, rsp; StackCookie
0x140063321  call    __security_check_cookie
0x140063326  add     rsp, 158h
0x14006332d  pop     r15
0x14006332f  pop     r14
0x140063331  pop     r13
0x140063333  pop     r12
0x140063335  pop     rdi
0x140063336  pop     rsi
0x140063337  pop     rbx
0x140063338  pop     rbp
0x140063339  retn
```
