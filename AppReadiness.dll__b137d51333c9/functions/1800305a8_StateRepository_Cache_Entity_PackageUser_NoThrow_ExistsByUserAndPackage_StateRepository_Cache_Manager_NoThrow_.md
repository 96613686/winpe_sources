# StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)

- ea: `0x1800305a8`
- end: `0x18003090c`
- name: `?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z`
- size: `868`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18004da98`
- `0x18005ac6c`

## callees

- `0x180019780`
- `0x18001ffa0`
- `0x18002108c`
- `0x18002f59c`
- `0x1800305a8`
- `0x180030914`
- `0x18003e210`
- `0x18003eca8`
- `0x18005a610`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800307ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800307ea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180030643`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180030643`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800306a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030849`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800308bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800308e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800306a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030849`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800308bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800308e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003073b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800308d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003073b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800308d0`

## string_xrefs

- `0x180030768`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180030660`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180030807`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800305f1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180030680`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180030719`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`
- `0x180030827`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        bool *a4)
{
  __int64 v7; // rdx
  int IsEmpty; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  char v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+258h] [rbp+158h]
  __int64 v31; // [rsp+260h] [rbp+160h]
  _BYTE *v32; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a4 = 0;
  if ( !a2 )
  {
    v7 = 153;
LABEL_3:
    IsEmpty = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v22);
    return (unsigned int)IsEmpty;
  }
  if ( !a3 )
  {
    v7 = 154;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a1;
  v25 = &v23;
  v23 = 0;
  v26 = 0;
  v27 = 1;
  IsEmpty = SRCacheContext_Open(v10, L"PackageUser\\Index\\UserAndPackage", 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v22);
    v11 = 158;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      v22);
LABEL_10:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return (unsigned int)IsEmpty;
  }
  if ( !v23 )
  {
    IsEmpty = -2140733422;
    v11 = 159;
    goto LABEL_9;
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v30 = 0;
  v32 = v29;
  v31 = 256;
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a2);
  if ( IsEmpty < 0 )
  {
    v14 = 162;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      v22);
LABEL_17:
    v15 = v28;
    v28 = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_10;
  }
  v16 = StateRepository::Cache::Key_NoThrow::EnsureCapacity((StateRepository::Cache::Key_NoThrow *)&v28, v30 + 2, v13);
  IsEmpty = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)(unsigned int)v16,
      v22);
    v14 = 163;
    goto LABEL_16;
  }
  *(_DWORD *)&v32[2 * v30++] = 94;
  IsEmpty = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v28, a3);
  if ( IsEmpty < 0 )
  {
    v14 = 164;
    goto LABEL_16;
  }
  v25 = &v24;
  v24 = 0;
  v26 = 0;
  v27 = 1;
  IsEmpty = SRCacheContext_OpenSubContext(v23, v32, 0, &v26);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v25);
  if ( IsEmpty < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)IsEmpty,
      v22);
    v17 = 168;
    goto LABEL_25;
  }
  if ( v24 )
  {
    LOBYTE(v22) = 0;
    IsEmpty = StateRepository::Cache::Context_NoThrow::IsEmpty(
                (StateRepository::Cache::Context_NoThrow *)&v24,
                (bool *)&v22);
    if ( IsEmpty < 0 )
    {
      v17 = 172;
      goto LABEL_25;
    }
    *a4 = (_BYTE)v22 == 0;
  }
  IsEmpty = StateRepository::Cache::Context_NoThrow::AddToCache(
              (StateRepository::Cache::Context_NoThrow *)&v23,
              L"PackageUser\\Index\\UserAndPackage");
  if ( IsEmpty < 0 )
  {
    v17 = 176;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageUser.hpp",
      (const char *)(unsigned int)IsEmpty,
      v22);
    v18 = v24;
    v24 = 0;
    if ( v18 )
      SRCacheContext_Close(v18);
    goto LABEL_17;
  }
  v19 = v24;
  v24 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  v20 = v28;
  v28 = 0;
  if ( v20 )
    SRCache_Free();
  v21 = v23;
  v23 = 0;
  if ( v21 )
    SRCacheContext_Close(v21);
  return 0;
}

```

## disassembly

```asm
0x1800305a8  push    rbp
0x1800305aa  push    rbx
0x1800305ab  push    rsi
0x1800305ac  push    rdi
0x1800305ad  push    r14
0x1800305af  push    r15
0x1800305b1  lea     rbp, [rsp-188h]
0x1800305b9  sub     rsp, 288h
0x1800305c0  mov     rax, cs:__security_cookie
0x1800305c7  xor     rax, rsp
0x1800305ca  mov     [rbp+1B0h+var_40], rax
0x1800305d1  xor     r15d, r15d
0x1800305d4  mov     rsi, r9
0x1800305d7  mov     [r9], r15b
0x1800305da  mov     rdi, r8
0x1800305dd  mov     r14, rdx
0x1800305e0  test    rdx, rdx
0x1800305e3  jnz     short loc_18003060C
0x1800305e5  mov     edx, 99h; void *
0x1800305ea  mov     rcx, [rbp+1B8h]; this
0x1800305f1  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800305f8  mov     ebx, 80070057h
0x1800305fd  mov     r9d, ebx; char *
0x180030600  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030605  mov     eax, ebx
0x180030607  jmp     loc_1800308ED
0x18003060c  test    rdi, rdi
0x18003060f  jnz     short loc_180030618
0x180030611  mov     edx, 9Ah
0x180030616  jmp     short loc_1800305EA
0x180030618  mov     rcx, [rcx]
0x18003061b  lea     rax, [rsp+2B0h+var_288]
0x180030620  lea     r9, [rsp+2B0h+var_270]
0x180030625  mov     [rsp+2B0h+var_278], rax
0x18003062a  xor     r8d, r8d
0x18003062d  mov     [rsp+2B0h+var_288], r15
0x180030632  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x180030639  mov     [rsp+2B0h+var_270], r15
0x18003063e  mov     [rsp+2B0h+var_268], 1
0x180030643  call    cs:__imp_SRCacheContext_Open
0x180030649  lea     rcx, [rsp+2B0h+var_278]
0x18003064e  mov     ebx, eax
0x180030650  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180030655  test    ebx, ebx
0x180030657  jns     short loc_1800306AD
0x180030659  mov     rcx, [rbp+1B8h]; this
0x180030660  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030667  mov     r9d, ebx; char *
0x18003066a  mov     edx, 18Ch; void *
0x18003066f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030674  mov     edx, 9Eh; void *
0x180030679  mov     rcx, [rbp+1B8h]; this
0x180030680  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030687  mov     r9d, ebx; char *
0x18003068a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003068f  mov     rcx, [rsp+2B0h+var_288]
0x180030694  mov     [rsp+2B0h+var_288], r15
0x180030699  test    rcx, rcx
0x18003069c  jz      loc_180030605
0x1800306a2  call    cs:__imp_SRCacheContext_Close
0x1800306a8  jmp     loc_180030605
0x1800306ad  cmp     [rsp+2B0h+var_288], r15
0x1800306b2  setnz   al
0x1800306b5  test    al, al
0x1800306b7  jnz     short loc_1800306C5
0x1800306b9  mov     ebx, 80670012h
0x1800306be  mov     edx, 9Fh
0x1800306c3  jmp     short loc_180030679
0x1800306c5  xor     edx, edx; Val
0x1800306c7  mov     [rsp+2B0h+var_260], r15
0x1800306cc  mov     r8d, 200h; Size
0x1800306d2  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800306d7  call    memset_0
0x1800306dc  lea     rax, [rsp+2B0h+var_258]
0x1800306e1  mov     [rbp+1B0h+var_58], r15
0x1800306e8  mov     rdx, r14; unsigned __int64
0x1800306eb  mov     [rbp+1B0h+var_48], rax
0x1800306f2  lea     rcx, [rsp+2B0h+var_260]; this
0x1800306f7  mov     [rbp+1B0h+var_50], 100h
0x180030702  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180030707  mov     ebx, eax
0x180030709  test    eax, eax
0x18003070b  jns     short loc_180030746
0x18003070d  mov     edx, 0A2h; void *
0x180030712  mov     rcx, [rbp+1B8h]; this
0x180030719  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030720  mov     r9d, ebx; char *
0x180030723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030728  mov     rcx, [rsp+2B0h+var_260]
0x18003072d  mov     [rsp+2B0h+var_260], r15
0x180030732  test    rcx, rcx
0x180030735  jz      loc_18003068F
0x18003073b  call    cs:__imp_SRCache_Free
0x180030741  jmp     loc_18003068F
0x180030746  mov     rdx, [rbp+1B0h+var_58]
0x18003074d  lea     rcx, [rsp+2B0h+var_260]; this
0x180030752  add     rdx, 2; unsigned __int64
0x180030756  call    ?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z; StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)
0x18003075b  mov     ebx, eax
0x18003075d  test    eax, eax
0x18003075f  jns     short loc_180030783
0x180030761  mov     rcx, [rbp+1B8h]; this
0x180030768  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003076f  mov     r9d, eax; char *
0x180030772  mov     edx, 16Dh; void *
0x180030777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003077c  mov     edx, 0A3h
0x180030781  jmp     short loc_180030712
0x180030783  mov     r8, [rbp+1B0h+var_58]
0x18003078a  mov     rdx, rdi; unsigned __int64
0x18003078d  mov     rcx, [rbp+1B0h+var_48]
0x180030794  mov     dword ptr [rcx+r8*2], 5Eh ; '^'
0x18003079c  lea     rcx, [rsp+2B0h+var_260]; this
0x1800307a1  inc     [rbp+1B0h+var_58]
0x1800307a8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800307ad  mov     ebx, eax
0x1800307af  test    eax, eax
0x1800307b1  jns     short loc_1800307BD
0x1800307b3  mov     edx, 0A4h
0x1800307b8  jmp     loc_180030712
0x1800307bd  mov     rdx, [rbp+1B0h+var_48]
0x1800307c4  lea     rax, [rsp+2B0h+var_280]
0x1800307c9  mov     rcx, [rsp+2B0h+var_288]
0x1800307ce  lea     r9, [rsp+2B0h+var_270]
0x1800307d3  xor     r8d, r8d
0x1800307d6  mov     [rsp+2B0h+var_278], rax
0x1800307db  mov     [rsp+2B0h+var_280], r15
0x1800307e0  mov     [rsp+2B0h+var_270], r15
0x1800307e5  mov     [rsp+2B0h+var_268], 1
0x1800307ea  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800307f0  lea     rcx, [rsp+2B0h+var_278]
0x1800307f5  mov     ebx, eax
0x1800307f7  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800307fc  test    ebx, ebx
0x1800307fe  jns     short loc_180030854
0x180030800  mov     rcx, [rbp+1B8h]; this
0x180030807  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003080e  mov     r9d, ebx; char *
0x180030811  mov     edx, 1B0h; void *
0x180030816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003081b  mov     edx, 0A8h; void *
0x180030820  mov     rcx, [rbp+1B8h]; this
0x180030827  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003082e  mov     r9d, ebx; char *
0x180030831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030836  mov     rcx, [rsp+2B0h+var_280]
0x18003083b  mov     [rsp+2B0h+var_280], r15
0x180030840  test    rcx, rcx
0x180030843  jz      loc_180030728
0x180030849  call    cs:__imp_SRCacheContext_Close
0x18003084f  jmp     loc_180030728
0x180030854  cmp     [rsp+2B0h+var_280], r15
0x180030859  setnz   al
0x18003085c  test    al, al
0x18003085e  jz      short loc_18003088B
0x180030860  lea     rdx, [rsp+2B0h+var_290]; bool *
0x180030865  mov     byte ptr [rsp+2B0h+var_290], r15b
0x18003086a  lea     rcx, [rsp+2B0h+var_280]; this
0x18003086f  call    ?IsEmpty@Context_NoThrow@Cache@StateRepository@@QEAAJAEA_N@Z; StateRepository::Cache::Context_NoThrow::IsEmpty(bool &)
0x180030874  mov     ebx, eax
0x180030876  test    eax, eax
0x180030878  jns     short loc_180030881
0x18003087a  mov     edx, 0ACh
0x18003087f  jmp     short loc_180030820
0x180030881  cmp     byte ptr [rsp+2B0h+var_290], r15b
0x180030886  setz    al
0x180030889  mov     [rsi], al
0x18003088b  lea     rdx, aPackageuserInd; "PackageUser\\Index\\UserAndPackage"
0x180030892  lea     rcx, [rsp+2B0h+var_288]; this
0x180030897  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18003089c  mov     ebx, eax
0x18003089e  test    eax, eax
0x1800308a0  jns     short loc_1800308AC
0x1800308a2  mov     edx, 0B0h
0x1800308a7  jmp     loc_180030820
0x1800308ac  mov     rcx, [rsp+2B0h+var_280]
0x1800308b1  mov     [rsp+2B0h+var_280], r15
0x1800308b6  test    rcx, rcx
0x1800308b9  jz      short loc_1800308C1
0x1800308bb  call    cs:__imp_SRCacheContext_Close
0x1800308c1  mov     rcx, [rsp+2B0h+var_260]
0x1800308c6  mov     [rsp+2B0h+var_260], r15
0x1800308cb  test    rcx, rcx
0x1800308ce  jz      short loc_1800308D6
0x1800308d0  call    cs:__imp_SRCache_Free
0x1800308d6  mov     rcx, [rsp+2B0h+var_288]
0x1800308db  mov     [rsp+2B0h+var_288], r15
0x1800308e0  test    rcx, rcx
0x1800308e3  jz      short loc_1800308EB
0x1800308e5  call    cs:__imp_SRCacheContext_Close
0x1800308eb  xor     eax, eax
0x1800308ed  mov     rcx, [rbp+1B0h+var_40]
0x1800308f4  xor     rcx, rsp; StackCookie
0x1800308f7  call    __security_check_cookie
0x1800308fc  add     rsp, 288h
0x180030903  pop     r15
0x180030905  pop     r14
0x180030907  pop     rdi
0x180030908  pop     rsi
0x180030909  pop     rbx
0x18003090a  pop     rbp
0x18003090b  retn
```
