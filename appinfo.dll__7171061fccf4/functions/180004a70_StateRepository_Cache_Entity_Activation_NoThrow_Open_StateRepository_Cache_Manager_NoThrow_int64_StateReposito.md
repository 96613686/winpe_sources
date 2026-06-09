# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180004a70`
- end: `0x180004ca9`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `569`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001177c`

## callees

- `0x180004a70`
- `0x180004cb0`
- `0x18000720c`
- `0x18000b840`
- `0x18000dee0`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004c0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004c6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004c0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004c6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004af4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004b43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004b89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004c82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004af4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004b43`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004b89`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004c82`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180004ad0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180004ad0`

## string_xrefs

- `0x180004b20`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180004b63`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180004bed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180004b05`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // r14d
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v20 = &v19;
  v22 = 1;
  v19 = 0;
  v21 = 0;
  v8 = SRCacheContext_Open(v4, L"Activation\\Data", 0, &v21);
  if ( v22 )
  {
    v9 = *v20;
    *v20 = v21;
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
      v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v18);
LABEL_6:
    v10 = v19;
    v19 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !v19 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)0x80670012LL,
      v17);
    v12 = v19;
    v19 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return 2154233874LL;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  if ( v8 < 0 )
  {
    v13 = 395;
    goto LABEL_15;
  }
  v17 = v5;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v27);
  if ( v8 < 0 )
  {
    v13 = 396;
    goto LABEL_15;
  }
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v19,
         L"Activation\\Data");
  if ( v8 < 0 )
  {
    v13 = 398;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v17);
    v14 = v23;
    v23 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_6;
  }
  v15 = v23;
  v23 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x180004a70  push    rbp
0x180004a72  push    rbx
0x180004a73  push    rsi
0x180004a74  push    rdi
0x180004a75  push    r14
0x180004a77  push    r15
0x180004a79  lea     rbp, [rsp-188h]
0x180004a81  sub     rsp, 288h
0x180004a88  mov     rax, cs:__security_cookie
0x180004a8f  xor     rax, rsp
0x180004a92  mov     [rbp+1B0h+var_40], rax
0x180004a99  mov     rcx, [rcx]
0x180004a9c  lea     rax, [rsp+2B0h+var_280]
0x180004aa1  mov     r14, r9
0x180004aa4  mov     [rsp+2B0h+var_278], rax
0x180004aa9  mov     rsi, r8
0x180004aac  mov     [rsp+2B0h+var_268], 1
0x180004ab1  mov     rdi, rdx
0x180004ab4  lea     r9, [rsp+2B0h+var_270]
0x180004ab9  xor     r15d, r15d
0x180004abc  lea     rdx, aActivationData; "Activation\\Data"
0x180004ac3  xor     r8d, r8d
0x180004ac6  mov     [rsp+2B0h+var_280], r15
0x180004acb  mov     [rsp+2B0h+var_270], r15
0x180004ad0  call    cs:__imp_SRCacheContext_Open
0x180004ad6  mov     ebx, eax
0x180004ad8  cmp     [rsp+2B0h+var_268], r15b
0x180004add  jz      short loc_180004AFA
0x180004adf  mov     r8, [rsp+2B0h+var_278]
0x180004ae4  mov     rdx, [rsp+2B0h+var_270]
0x180004ae9  mov     rcx, [r8]
0x180004aec  mov     [r8], rdx
0x180004aef  test    rcx, rcx
0x180004af2  jz      short loc_180004AFA
0x180004af4  call    cs:__imp_SRCacheContext_Close
0x180004afa  test    ebx, ebx
0x180004afc  jns     short loc_180004B50
0x180004afe  mov     rcx, [rbp+1B8h]; this
0x180004b05  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004b0c  mov     r9d, ebx; char *
0x180004b0f  mov     edx, 18Ch; void *
0x180004b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b19  mov     rcx, [rbp+1B8h]; this
0x180004b20  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004b27  mov     r9d, ebx; char *
0x180004b2a  mov     edx, 187h; void *
0x180004b2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b34  mov     rcx, [rsp+2B0h+var_280]
0x180004b39  mov     [rsp+2B0h+var_280], r15
0x180004b3e  test    rcx, rcx
0x180004b41  jz      short loc_180004B49
0x180004b43  call    cs:__imp_SRCacheContext_Close
0x180004b49  mov     eax, ebx
0x180004b4b  jmp     loc_180004C8A
0x180004b50  cmp     [rsp+2B0h+var_280], r15
0x180004b55  setnz   al
0x180004b58  test    al, al
0x180004b5a  jnz     short loc_180004B99
0x180004b5c  mov     rcx, [rbp+1B8h]; this
0x180004b63  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004b6a  mov     r9d, 80670012h; char *
0x180004b70  mov     edx, 188h; void *
0x180004b75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b7a  mov     rcx, [rsp+2B0h+var_280]
0x180004b7f  mov     [rsp+2B0h+var_280], r15
0x180004b84  test    rcx, rcx
0x180004b87  jz      short loc_180004B8F
0x180004b89  call    cs:__imp_SRCacheContext_Close
0x180004b8f  mov     eax, 80670012h
0x180004b94  jmp     loc_180004C8A
0x180004b99  xor     edx, edx; Val
0x180004b9b  mov     [rsp+2B0h+var_260], r15
0x180004ba0  mov     r8d, 200h; Size
0x180004ba6  lea     rcx, [rsp+2B0h+var_258]; void *
0x180004bab  call    memset_0
0x180004bb0  lea     rax, [rsp+2B0h+var_258]
0x180004bb5  mov     [rbp+1B0h+var_58], r15
0x180004bbc  mov     rdx, rdi; unsigned __int64
0x180004bbf  mov     [rbp+1B0h+var_48], rax
0x180004bc6  lea     rcx, [rsp+2B0h+var_260]; this
0x180004bcb  mov     [rbp+1B0h+var_50], 100h
0x180004bd6  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180004bdb  mov     ebx, eax
0x180004bdd  test    eax, eax
0x180004bdf  jns     short loc_180004C1A
0x180004be1  mov     edx, 18Bh; void *
0x180004be6  mov     rcx, [rbp+1B8h]; this
0x180004bed  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004bf4  mov     r9d, ebx; char *
0x180004bf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004bfc  mov     rcx, [rsp+2B0h+var_260]
0x180004c01  mov     [rsp+2B0h+var_260], r15
0x180004c06  test    rcx, rcx
0x180004c09  jz      loc_180004B34
0x180004c0f  call    cs:__imp_SRCache_Free
0x180004c15  jmp     loc_180004B34
0x180004c1a  mov     r8, [rbp+1B0h+var_48]
0x180004c21  lea     rdx, [rsp+2B0h+var_280]
0x180004c26  mov     rcx, rsi
0x180004c29  mov     qword ptr [rsp+2B0h+var_290], r14
0x180004c2e  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180004c33  mov     ebx, eax
0x180004c35  test    eax, eax
0x180004c37  jns     short loc_180004C40
0x180004c39  mov     edx, 18Ch
0x180004c3e  jmp     short loc_180004BE6
0x180004c40  lea     rdx, aActivationData; "Activation\\Data"
0x180004c47  lea     rcx, [rsp+2B0h+var_280]; this
0x180004c4c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180004c51  mov     ebx, eax
0x180004c53  test    eax, eax
0x180004c55  jns     short loc_180004C5E
0x180004c57  mov     edx, 18Eh
0x180004c5c  jmp     short loc_180004BE6
0x180004c5e  mov     rcx, [rsp+2B0h+var_260]
0x180004c63  mov     [rsp+2B0h+var_260], r15
0x180004c68  test    rcx, rcx
0x180004c6b  jz      short loc_180004C73
0x180004c6d  call    cs:__imp_SRCache_Free
0x180004c73  mov     rcx, [rsp+2B0h+var_280]
0x180004c78  mov     [rsp+2B0h+var_280], r15
0x180004c7d  test    rcx, rcx
0x180004c80  jz      short loc_180004C88
0x180004c82  call    cs:__imp_SRCacheContext_Close
0x180004c88  xor     eax, eax
0x180004c8a  mov     rcx, [rbp+1B0h+var_40]
0x180004c91  xor     rcx, rsp; StackCookie
0x180004c94  call    __security_check_cookie
0x180004c99  add     rsp, 288h
0x180004ca0  pop     r15
0x180004ca2  pop     r14
0x180004ca4  pop     rdi
0x180004ca5  pop     rsi
0x180004ca6  pop     rbx
0x180004ca7  pop     rbp
0x180004ca8  retn
```
