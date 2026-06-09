# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800047f4`
- end: `0x180004a62`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `622`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800046a4`

## callees

- `0x1800047f4`
- `0x180004cb0`
- `0x18000720c`
- `0x18000dee0`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180004993`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180004993`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004965`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004a1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004965`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004a1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000487b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800048ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800049b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004a34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000487b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800048ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800049b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004a34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180004857`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180004857`

## string_xrefs

- `0x180004843`: `ApplicationExtension\Data`
- `0x1800049e9`: `ApplicationExtension\Data`
- `0x18000488c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800049c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800048ac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180004943`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  char v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+248h] [rbp+148h]
  __int64 v25; // [rsp+250h] [rbp+150h]
  _BYTE *v26; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v19 = v18;
  v21 = 1;
  *(_QWORD *)v18 = 0;
  v20 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v20);
  if ( v21 )
  {
    v9 = *(_QWORD *)v19;
    *(_QWORD *)v19 = v20;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v10 = 364;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
LABEL_7:
    v11 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v18 )
  {
    v8 = -2140733422;
    v10 = 365;
    goto LABEL_6;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a2);
  if ( v8 < 0 )
  {
    v13 = 368;
    goto LABEL_14;
  }
  v19 = (int *)a3;
  v20 = 0;
  v21 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v18, v26, 0, &v20);
  if ( v21 )
  {
    v15 = *(_QWORD *)v19;
    *(_QWORD *)v19 = v20;
    if ( v15 )
      SRCacheContext_Close(v15);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v13 = 369;
    goto LABEL_14;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v13 = 371;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v14 = v22;
    v22 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_7;
  }
  v16 = v22;
  v22 = 0;
  if ( v16 )
    SRCache_Free(v16);
  v17 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x1800047f4  mov     [rsp-8+arg_10], rbx
0x1800047f9  push    rbp
0x1800047fa  push    rsi
0x1800047fb  push    rdi
0x1800047fc  push    r14
0x1800047fe  push    r15
0x180004800  lea     rbp, [rsp-170h]
0x180004808  sub     rsp, 270h
0x18000480f  mov     rax, cs:__security_cookie
0x180004816  xor     rax, rsp
0x180004819  mov     [rbp+190h+var_30], rax
0x180004820  mov     rcx, [rcx]
0x180004823  lea     rax, [rsp+290h+var_270]
0x180004828  mov     r14, r9
0x18000482b  mov     [rsp+290h+var_268], rax
0x180004830  mov     rdi, r8
0x180004833  mov     [rsp+290h+var_258], 1
0x180004838  mov     rsi, rdx
0x18000483b  lea     r9, [rsp+290h+var_260]
0x180004840  xor     r15d, r15d
0x180004843  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x18000484a  xor     r8d, r8d
0x18000484d  mov     qword ptr [rsp+290h+var_270], r15; int
0x180004852  mov     [rsp+290h+var_260], r15
0x180004857  call    cs:__imp_SRCacheContext_Open
0x18000485d  mov     ebx, eax
0x18000485f  cmp     [rsp+290h+var_258], r15b
0x180004864  jz      short loc_180004881
0x180004866  mov     r8, [rsp+290h+var_268]
0x18000486b  mov     rdx, [rsp+290h+var_260]
0x180004870  mov     rcx, [r8]
0x180004873  mov     [r8], rdx
0x180004876  test    rcx, rcx
0x180004879  jz      short loc_180004881
0x18000487b  call    cs:__imp_SRCacheContext_Close
0x180004881  test    ebx, ebx
0x180004883  jns     short loc_1800048D7
0x180004885  mov     rcx, [rbp+198h]; this
0x18000488c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004893  mov     r9d, ebx; char *
0x180004896  mov     edx, 18Ch; void *
0x18000489b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048a0  mov     edx, 16Ch; void *
0x1800048a5  mov     rcx, [rbp+198h]; this
0x1800048ac  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800048b3  mov     r9d, ebx; char *
0x1800048b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048bb  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800048c0  mov     qword ptr [rsp+290h+var_270], r15
0x1800048c5  test    rcx, rcx
0x1800048c8  jz      short loc_1800048D0
0x1800048ca  call    cs:__imp_SRCacheContext_Close
0x1800048d0  mov     eax, ebx
0x1800048d2  jmp     loc_180004A3C
0x1800048d7  cmp     qword ptr [rsp+290h+var_270], r15
0x1800048dc  setnz   al
0x1800048df  test    al, al
0x1800048e1  jnz     short loc_1800048EF
0x1800048e3  mov     ebx, 80670012h
0x1800048e8  mov     edx, 16Dh
0x1800048ed  jmp     short loc_1800048A5
0x1800048ef  xor     edx, edx; Val
0x1800048f1  mov     [rsp+290h+var_250], r15
0x1800048f6  mov     r8d, 200h; Size
0x1800048fc  lea     rcx, [rsp+290h+var_248]; void *
0x180004901  call    memset_0
0x180004906  lea     rax, [rsp+290h+var_248]
0x18000490b  mov     [rbp+190h+var_48], r15
0x180004912  mov     rdx, rsi; unsigned __int64
0x180004915  mov     [rbp+190h+var_38], rax
0x18000491c  lea     rcx, [rsp+290h+var_250]; this
0x180004921  mov     [rbp+190h+var_40], 100h
0x18000492c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180004931  mov     ebx, eax
0x180004933  test    eax, eax
0x180004935  jns     short loc_180004970
0x180004937  mov     edx, 170h; void *
0x18000493c  mov     rcx, [rbp+198h]; this
0x180004943  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000494a  mov     r9d, ebx; char *
0x18000494d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004952  mov     rcx, [rsp+290h+var_250]
0x180004957  mov     [rsp+290h+var_250], r15
0x18000495c  test    rcx, rcx
0x18000495f  jz      loc_1800048BB
0x180004965  call    cs:__imp_SRCache_Free
0x18000496b  jmp     loc_1800048BB
0x180004970  mov     rdx, [rbp+190h+var_38]
0x180004977  lea     r9, [rsp+290h+var_260]
0x18000497c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180004981  xor     r8d, r8d
0x180004984  mov     [rsp+290h+var_268], rdi
0x180004989  mov     [rsp+290h+var_260], r15
0x18000498e  mov     [rsp+290h+var_258], 1
0x180004993  call    cs:__imp_SRCacheContext_OpenSubContext
0x180004999  mov     ebx, eax
0x18000499b  cmp     [rsp+290h+var_258], r15b
0x1800049a0  jz      short loc_1800049BD
0x1800049a2  mov     r8, [rsp+290h+var_268]
0x1800049a7  mov     rdx, [rsp+290h+var_260]
0x1800049ac  mov     rcx, [r8]
0x1800049af  mov     [r8], rdx
0x1800049b2  test    rcx, rcx
0x1800049b5  jz      short loc_1800049BD
0x1800049b7  call    cs:__imp_SRCacheContext_Close
0x1800049bd  test    ebx, ebx
0x1800049bf  jns     short loc_1800049E6
0x1800049c1  mov     rcx, [rbp+198h]; this
0x1800049c8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800049cf  mov     r9d, ebx; char *
0x1800049d2  mov     edx, 1B0h; void *
0x1800049d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049dc  mov     edx, 171h
0x1800049e1  jmp     loc_18000493C
0x1800049e6  cmp     [rdi], r15
0x1800049e9  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800049f0  lea     rcx, [rsp+290h+var_270]; this
0x1800049f5  setnz   al
0x1800049f8  mov     [r14], al
0x1800049fb  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180004a00  mov     ebx, eax
0x180004a02  test    eax, eax
0x180004a04  jns     short loc_180004A10
0x180004a06  mov     edx, 173h
0x180004a0b  jmp     loc_18000493C
0x180004a10  mov     rcx, [rsp+290h+var_250]
0x180004a15  mov     [rsp+290h+var_250], r15
0x180004a1a  test    rcx, rcx
0x180004a1d  jz      short loc_180004A25
0x180004a1f  call    cs:__imp_SRCache_Free
0x180004a25  mov     rcx, qword ptr [rsp+290h+var_270]
0x180004a2a  mov     qword ptr [rsp+290h+var_270], r15
0x180004a2f  test    rcx, rcx
0x180004a32  jz      short loc_180004A3A
0x180004a34  call    cs:__imp_SRCacheContext_Close
0x180004a3a  xor     eax, eax
0x180004a3c  mov     rcx, [rbp+190h+var_30]
0x180004a43  xor     rcx, rsp; StackCookie
0x180004a46  call    __security_check_cookie
0x180004a4b  mov     rbx, [rsp+290h+arg_10]
0x180004a53  add     rsp, 270h
0x180004a5a  pop     r15
0x180004a5c  pop     r14
0x180004a5e  pop     rdi
0x180004a5f  pop     rsi
0x180004a60  pop     rbp
0x180004a61  retn
```
