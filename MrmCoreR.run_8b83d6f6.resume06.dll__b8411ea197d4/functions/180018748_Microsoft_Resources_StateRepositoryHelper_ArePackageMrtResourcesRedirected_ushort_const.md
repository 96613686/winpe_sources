# Microsoft::Resources::StateRepositoryHelper::ArePackageMrtResourcesRedirected(ushort const *)

- ea: `0x180018748`
- end: `0x18001892e`
- name: `?ArePackageMrtResourcesRedirected@StateRepositoryHelper@Resources@Microsoft@@SA_NPEBG@Z`
- size: `486`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180018748`
- `0x1800194e8`
- `0x180019694`
- `0x180019aac`
- `0x180019e3c`
- `0x18001a6d4`
- `0x18002c8d0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800187cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800188c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800187cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180018804`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800188c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018897`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018913`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018897`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018913`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800187ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800187ab`

## string_xrefs

- `0x1800188e1`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800188f4`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x1800187d6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
bool __fastcall Microsoft::Resources::StateRepositoryHelper::ArePackageMrtResourcesRedirected(
        const unsigned __int16 *a1)
{
  int v2; // ebx
  __int64 v3; // rcx
  const char *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  bool v8; // si
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool AreMrtResourcesRedirected; // bl
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // [rsp+20h] [rbp-59h] BYREF
  __int64 *v19; // [rsp+28h] [rbp-51h]
  __int64 v20; // [rsp+30h] [rbp-49h] BYREF
  char v21; // [rsp+38h] [rbp-41h]
  __int128 v22; // [rsp+40h] [rbp-39h] BYREF
  __int64 v23; // [rsp+50h] [rbp-29h]
  __int128 v24; // [rsp+58h] [rbp-21h]
  __int64 v25; // [rsp+68h] [rbp-11h]
  __int64 v26; // [rsp+70h] [rbp-9h]
  __int64 v27; // [rsp+78h] [rbp-1h]
  __int128 v28; // [rsp+80h] [rbp+7h]
  int v29; // [rsp+90h] [rbp+17h]
  __int64 v30; // [rsp+98h] [rbp+1Fh]
  __int64 v31; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  bool v33; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v34; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v35; // [rsp+F8h] [rbp+7Fh] BYREF

  v21 = 1;
  v35 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v24 = 0;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v19 = &v35;
  v20 = 0;
  v2 = SRCacheManager_Open(0, &v20);
  if ( v21 )
  {
    v3 = *v19;
    *v19 = v20;
    if ( v3 )
      SRCacheManager_Close();
  }
  if ( v2 < 0 )
  {
    v4 = "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp";
    v5 = 165;
LABEL_6:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v5, (unsigned int)v4, (const char *)(unsigned int)v2, v18);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v22);
    v6 = v35;
    v35 = 0;
    if ( v6 )
      SRCacheManager_Close();
    return 0;
  }
  v33 = 0;
  v18 = 0;
  v8 = 0;
  v2 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v35,
         a1,
         &v18);
  if ( v2 < 0 )
  {
    v5 = 1165;
    goto LABEL_22;
  }
  v9 = v18;
  if ( v18 )
  {
    v34 = 0;
    v10 = StateRepository::Cache::Entity::Package_NoThrow::Open(
            (struct StateRepository::Cache::Manager_NoThrow *)&v35,
            v18,
            (struct StateRepository::Cache::Context_NoThrow *)&v34,
            &v33);
    v2 = v10;
    if ( v10 < 0 )
    {
      v17 = 1110;
    }
    else
    {
      v8 = v33;
      if ( !v33
        || (v10 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v34, &v22, 264, v9),
            v2 = v10,
            v10 >= 0) )
      {
        v12 = v34;
        v34 = 0;
        if ( v12 )
          SRCacheContext_Close(v12, v11);
        goto LABEL_16;
      }
      v17 = 1115;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)v10,
      v18);
    v16 = v34;
    v34 = 0;
    if ( v16 )
      SRCacheContext_Close(v16, v15);
    v5 = 1168;
LABEL_22:
    v4 = "onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp";
    goto LABEL_6;
  }
LABEL_16:
  AreMrtResourcesRedirected = 0;
  if ( v8 )
    AreMrtResourcesRedirected = StateRepository::Cache::Entity::Package_NoThrow::GetAreMrtResourcesRedirected((StateRepository::Cache::Entity::Package_NoThrow *)&v22);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v22);
  v14 = v35;
  v35 = 0;
  if ( v14 )
    SRCacheManager_Close();
  return AreMrtResourcesRedirected;
}

```

## disassembly

```asm
0x180018748  push    rbp
0x18001874a  push    rbx
0x18001874b  push    rsi
0x18001874c  push    rdi
0x18001874d  push    r14
0x18001874f  lea     rbp, [rsp-37h]
0x180018754  sub     rsp, 0B0h
0x18001875b  xor     r14d, r14d
0x18001875e  mov     [rbp+57h+var_98], 1
0x180018762  xorps   xmm0, xmm0
0x180018765  mov     [rbp+57h+arg_18], r14
0x180018769  mov     rdi, rcx
0x18001876c  movdqa  [rbp+57h+var_90], xmm0
0x180018771  xorps   xmm1, xmm1
0x180018774  mov     [rbp+57h+var_80], r14
0x180018778  lea     rax, [rbp+57h+arg_18]
0x18001877c  mov     [rbp+57h+var_68], r14
0x180018780  xor     ecx, ecx
0x180018782  mov     [rbp+57h+var_60], r14
0x180018786  lea     rdx, [rbp+57h+var_A0]
0x18001878a  mov     [rbp+57h+var_58], r14
0x18001878e  movups  [rbp+57h+var_78], xmm1
0x180018792  mov     [rbp+57h+var_40], r14d
0x180018796  movdqa  [rbp+57h+var_50], xmm0
0x18001879b  mov     [rbp+57h+var_38], r14
0x18001879f  mov     [rbp+57h+var_30], r14
0x1800187a3  mov     [rbp+57h+var_A8], rax
0x1800187a7  mov     [rbp+57h+var_A0], r14
0x1800187ab  call    cs:__imp_SRCacheManager_Open
0x1800187b1  mov     ebx, eax
0x1800187b3  cmp     [rbp+57h+var_98], r14b
0x1800187b7  jz      short loc_1800187D2
0x1800187b9  mov     r8, [rbp+57h+var_A8]
0x1800187bd  mov     rdx, [rbp+57h+var_A0]
0x1800187c1  mov     rcx, [r8]
0x1800187c4  mov     [r8], rdx
0x1800187c7  test    rcx, rcx
0x1800187ca  jz      short loc_1800187D2
0x1800187cc  call    cs:__imp_SRCacheManager_Close
0x1800187d2  test    ebx, ebx
0x1800187d4  jns     short loc_180018811
0x1800187d6  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800187dd  mov     edx, 0A5h; void *
0x1800187e2  mov     rcx, [rbp+5Fh]; this
0x1800187e6  mov     r9d, ebx; char *
0x1800187e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187ee  lea     rcx, [rbp+57h+var_90]; this
0x1800187f2  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800187f7  mov     rcx, [rbp+57h+arg_18]
0x1800187fb  mov     [rbp+57h+arg_18], r14
0x1800187ff  test    rcx, rcx
0x180018802  jz      short loc_18001880A
0x180018804  call    cs:__imp_SRCacheManager_Close
0x18001880a  xor     al, al
0x18001880c  jmp     loc_1800188CE
0x180018811  lea     r8, [rbp+57h+var_B0]; __int64 *
0x180018815  mov     [rbp+57h+arg_8], r14b
0x180018819  mov     rdx, rdi; unsigned __int16 *
0x18001881c  mov     [rbp+57h+var_B0], r14
0x180018820  lea     rcx, [rbp+57h+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x180018824  mov     sil, r14b
0x180018827  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18001882c  mov     ebx, eax
0x18001882e  test    eax, eax
0x180018830  js      loc_1800188DC
0x180018836  mov     rdi, [rbp+57h+var_B0]
0x18001883a  test    rdi, rdi
0x18001883d  jz      short loc_18001889D
0x18001883f  lea     r9, [rbp+57h+arg_8]; bool *
0x180018843  mov     [rbp+57h+arg_10], r14
0x180018847  lea     r8, [rbp+57h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18001884b  mov     rdx, rdi; __int64
0x18001884e  lea     rcx, [rbp+57h+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x180018852  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180018857  mov     ebx, eax
0x180018859  test    eax, eax
0x18001885b  js      loc_180018920
0x180018861  mov     sil, [rbp+57h+arg_8]
0x180018865  test    sil, sil
0x180018868  jz      short loc_18001888A
0x18001886a  mov     r9, rdi
0x18001886d  lea     rdx, [rbp+57h+var_90]
0x180018871  mov     r8d, 108h
0x180018877  lea     rcx, [rbp+57h+arg_10]
0x18001887b  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180018880  mov     ebx, eax
0x180018882  test    eax, eax
0x180018884  js      loc_180018927
0x18001888a  mov     rcx, [rbp+57h+arg_10]
0x18001888e  mov     [rbp+57h+arg_10], r14
0x180018892  test    rcx, rcx
0x180018895  jz      short loc_18001889D
0x180018897  call    cs:__imp_SRCacheContext_Close
0x18001889d  mov     bl, r14b
0x1800188a0  test    sil, sil
0x1800188a3  jz      short loc_1800188B0
0x1800188a5  lea     rcx, [rbp+57h+var_90]; this
0x1800188a9  call    ?GetAreMrtResourcesRedirected@Package_NoThrow@Entity@Cache@StateRepository@@QEBA_NXZ; StateRepository::Cache::Entity::Package_NoThrow::GetAreMrtResourcesRedirected(void)
0x1800188ae  mov     bl, al
0x1800188b0  lea     rcx, [rbp+57h+var_90]; this
0x1800188b4  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800188b9  mov     rcx, [rbp+57h+arg_18]
0x1800188bd  mov     [rbp+57h+arg_18], r14
0x1800188c1  test    rcx, rcx
0x1800188c4  jz      short loc_1800188CC
0x1800188c6  call    cs:__imp_SRCacheManager_Close
0x1800188cc  mov     al, bl
0x1800188ce  add     rsp, 0B0h
0x1800188d5  pop     r14
0x1800188d7  pop     rdi
0x1800188d8  pop     rsi
0x1800188d9  pop     rbx
0x1800188da  pop     rbp
0x1800188db  retn
0x1800188dc  mov     edx, 48Dh
0x1800188e1  lea     rdi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800188e8  mov     r8, rdi
0x1800188eb  jmp     loc_1800187E2
0x1800188f0  mov     rcx, [rbp+5Fh]; this
0x1800188f4  lea     rdi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800188fb  mov     r8, rdi; unsigned int
0x1800188fe  mov     r9d, eax; char *
0x180018901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018906  mov     rcx, [rbp+57h+arg_10]
0x18001890a  mov     [rbp+57h+arg_10], r14
0x18001890e  test    rcx, rcx
0x180018911  jz      short loc_180018919
0x180018913  call    cs:__imp_SRCacheContext_Close
0x180018919  mov     edx, 490h
0x18001891e  jmp     short loc_1800188E8
0x180018920  mov     edx, 456h; void *
0x180018925  jmp     short loc_1800188F0
0x180018927  mov     edx, 45Bh
0x18001892c  jmp     short loc_1800188F0
```
