# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180064204`
- end: `0x18006451f`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `795`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180064150`

## callees

- `0x18001a140`
- `0x18002c8d0`
- `0x180064204`
- `0x1800862f0`
- `0x180086f7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800643a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800643eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800643a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800643eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064286`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064341`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006438d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800643b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064400`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064286`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064341`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18006438d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800643b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064400`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180064483`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180064262`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180064262`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18006442a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18006442a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006431d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18006431d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006436e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18006436e`

## string_xrefs

- `0x180064441`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180064495`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800644dc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180064501`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18006425b`: `User\Index\UserSid`
- `0x180064367`: `User\Index\UserSid`
- `0x1800643c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180064461`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800644c1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  int *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  char v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+258h] [rbp+158h]
  __int64 v33; // [rsp+260h] [rbp+160h]
  _BYTE *v34; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v29 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v25 = 0;
  v27 = v25;
  v28 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v28);
  if ( v29 )
  {
    v7 = v28;
    v8 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v8 )
      SRCacheContext_Close(v8, v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v24 = 185;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v25[0]);
LABEL_23:
    v20 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    if ( v20 )
      SRCacheContext_Close(v20, v18);
    return v6;
  }
  if ( !*(_QWORD *)v25 )
  {
    v6 = -2140733422;
    v24 = 186;
    goto LABEL_32;
  }
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v32 = 0;
  v34 = v31;
  v33 = 256;
  v9 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v30, a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v9,
      v25[0]);
LABEL_21:
    v19 = v30;
    v30 = 0;
    if ( v19 )
      SRCache_Free();
    goto LABEL_23;
  }
  v27 = (int *)&v26;
  v26 = 0;
  v28 = 0;
  v29 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v25, v34, 0, &v28);
  if ( v29 )
  {
    v10 = v28;
    v11 = *(_QWORD *)v27;
    *(_QWORD *)v27 = v28;
    if ( v11 )
      SRCacheContext_Close(v11, v10);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v25[0]);
    v22 = 193;
    goto LABEL_28;
  }
  if ( v26 )
  {
    v21 = SRCacheContext_EnumerateData(v26, 0, a3);
    v6 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v21,
        v25[0]);
      v22 = 196;
      goto LABEL_28;
    }
  }
  v12 = SRCacheContext_AddToCache(*(_QWORD *)v25, L"User\\Index\\UserSid");
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v12,
      v25[0]);
    v22 = 199;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v25[0]);
    v23 = v26;
    v26 = 0;
    if ( v23 )
      SRCacheContext_Close(v23, v18);
    goto LABEL_21;
  }
  v14 = v26;
  v26 = 0;
  if ( v14 )
    SRCacheContext_Close(v14, v13);
  v15 = v30;
  v30 = 0;
  if ( v15 )
    SRCache_Free();
  v16 = *(_QWORD *)v25;
  *(_QWORD *)v25 = 0;
  if ( v16 )
    SRCacheContext_Close(v16, v13);
  return 0;
}

```

## disassembly

```asm
0x180064204  push    rbp
0x180064206  push    rbx
0x180064207  push    rsi
0x180064208  push    rdi
0x180064209  push    r14
0x18006420b  lea     rbp, [rsp-180h]
0x180064213  sub     rsp, 280h
0x18006421a  mov     rax, cs:__security_cookie
0x180064221  xor     rax, rsp
0x180064224  mov     [rbp+1A0h+var_30], rax
0x18006422b  xor     r14d, r14d
0x18006422e  mov     [rsp+2A0h+var_260], 1
0x180064233  mov     [r8], r14
0x180064236  lea     rax, [rsp+2A0h+var_280]
0x18006423b  mov     rcx, [rcx]
0x18006423e  lea     r9, [rsp+2A0h+var_268]
0x180064243  mov     rdi, r8
0x180064246  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18006424b  mov     rsi, rdx
0x18006424e  mov     [rsp+2A0h+var_270], rax
0x180064253  xor     r8d, r8d
0x180064256  mov     [rsp+2A0h+var_268], r14
0x18006425b  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x180064262  call    cs:__imp_SRCacheContext_Open
0x180064268  mov     ebx, eax
0x18006426a  cmp     [rsp+2A0h+var_260], r14b
0x18006426f  jz      short loc_18006428C
0x180064271  mov     r8, [rsp+2A0h+var_270]
0x180064276  mov     rdx, [rsp+2A0h+var_268]
0x18006427b  mov     rcx, [r8]
0x18006427e  mov     [r8], rdx
0x180064281  test    rcx, rcx
0x180064284  jz      short loc_18006428C
0x180064286  call    cs:__imp_SRCacheContext_Close
0x18006428c  test    ebx, ebx
0x18006428e  js      loc_18006448E
0x180064294  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180064299  setnz   al
0x18006429c  test    al, al
0x18006429e  jz      loc_1800644B0
0x1800642a4  xor     edx, edx; Val
0x1800642a6  mov     [rsp+2A0h+var_250], r14
0x1800642ab  mov     r8d, 200h; Size
0x1800642b1  lea     rcx, [rsp+2A0h+var_248]; void *
0x1800642b6  call    memset_0
0x1800642bb  lea     rax, [rsp+2A0h+var_248]
0x1800642c0  mov     [rbp+1A0h+var_48], r14
0x1800642c7  mov     rdx, rsi; unsigned __int16 *
0x1800642ca  mov     [rbp+1A0h+var_38], rax
0x1800642d1  lea     rcx, [rsp+2A0h+var_250]; this
0x1800642d6  mov     [rbp+1A0h+var_40], 100h
0x1800642e1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800642e6  mov     ebx, eax
0x1800642e8  test    eax, eax
0x1800642ea  js      loc_1800643C1
0x1800642f0  mov     rdx, [rbp+1A0h+var_38]
0x1800642f7  lea     rax, [rsp+2A0h+var_278]
0x1800642fc  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180064301  lea     r9, [rsp+2A0h+var_268]
0x180064306  xor     r8d, r8d
0x180064309  mov     [rsp+2A0h+var_270], rax
0x18006430e  mov     [rsp+2A0h+var_278], r14
0x180064313  mov     [rsp+2A0h+var_268], r14
0x180064318  mov     [rsp+2A0h+var_260], 1
0x18006431d  call    cs:__imp_SRCacheContext_OpenSubContext
0x180064323  mov     ebx, eax
0x180064325  cmp     [rsp+2A0h+var_260], r14b
0x18006432a  jz      short loc_180064347
0x18006432c  mov     r8, [rsp+2A0h+var_270]
0x180064331  mov     rdx, [rsp+2A0h+var_268]
0x180064336  mov     rcx, [r8]
0x180064339  mov     [r8], rdx
0x18006433c  test    rcx, rcx
0x18006433f  jz      short loc_180064347
0x180064341  call    cs:__imp_SRCacheContext_Close
0x180064347  test    ebx, ebx
0x180064349  js      loc_1800644D5
0x18006434f  mov     rcx, [rsp+2A0h+var_278]
0x180064354  test    rcx, rcx
0x180064357  setnz   al
0x18006435a  test    al, al
0x18006435c  jnz     loc_180064425
0x180064362  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180064367  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18006436e  call    cs:__imp_SRCacheContext_AddToCache
0x180064374  mov     ebx, eax
0x180064376  test    eax, eax
0x180064378  js      loc_1800644FA
0x18006437e  mov     rcx, [rsp+2A0h+var_278]
0x180064383  mov     [rsp+2A0h+var_278], r14
0x180064388  test    rcx, rcx
0x18006438b  jz      short loc_180064393
0x18006438d  call    cs:__imp_SRCacheContext_Close
0x180064393  mov     rcx, [rsp+2A0h+var_250]
0x180064398  mov     [rsp+2A0h+var_250], r14
0x18006439d  test    rcx, rcx
0x1800643a0  jz      short loc_1800643A8
0x1800643a2  call    cs:__imp_SRCache_Free
0x1800643a8  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800643ad  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800643b2  test    rcx, rcx
0x1800643b5  jz      short loc_1800643BD
0x1800643b7  call    cs:__imp_SRCacheContext_Close
0x1800643bd  xor     eax, eax
0x1800643bf  jmp     short loc_180064408
0x1800643c1  mov     rcx, [rbp+1A8h]; this
0x1800643c8  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800643cf  mov     r9d, ebx; char *
0x1800643d2  mov     edx, 0BDh; void *
0x1800643d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800643dc  mov     rcx, [rsp+2A0h+var_250]
0x1800643e1  mov     [rsp+2A0h+var_250], r14
0x1800643e6  test    rcx, rcx
0x1800643e9  jz      short loc_1800643F1
0x1800643eb  call    cs:__imp_SRCache_Free
0x1800643f1  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800643f6  mov     qword ptr [rsp+2A0h+var_280], r14
0x1800643fb  test    rcx, rcx
0x1800643fe  jz      short loc_180064406
0x180064400  call    cs:__imp_SRCacheContext_Close
0x180064406  mov     eax, ebx
0x180064408  mov     rcx, [rbp+1A0h+var_30]
0x18006440f  xor     rcx, rsp; StackCookie
0x180064412  call    __security_check_cookie
0x180064417  add     rsp, 280h
0x18006441e  pop     r14
0x180064420  pop     rdi
0x180064421  pop     rsi
0x180064422  pop     rbx
0x180064423  pop     rbp
0x180064424  retn
0x180064425  mov     r8, rdi
0x180064428  xor     edx, edx
0x18006442a  call    cs:__imp_SRCacheContext_EnumerateData
0x180064430  mov     ebx, eax
0x180064432  test    eax, eax
0x180064434  jns     loc_180064362
0x18006443a  mov     rcx, [rbp+1A8h]; this
0x180064441  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064448  mov     r9d, eax; char *
0x18006444b  mov     edx, 2A6h; void *
0x180064450  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064455  mov     edx, 0C4h; void *
0x18006445a  mov     rcx, [rbp+1A8h]; this
0x180064461  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064468  mov     r9d, ebx; char *
0x18006446b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064470  mov     rcx, [rsp+2A0h+var_278]
0x180064475  mov     [rsp+2A0h+var_278], r14
0x18006447a  test    rcx, rcx
0x18006447d  jz      loc_1800643DC
0x180064483  call    cs:__imp_SRCacheContext_Close
0x180064489  jmp     loc_1800643DC
0x18006448e  mov     rcx, [rbp+1A8h]; this
0x180064495  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x18006449c  mov     r9d, ebx; char *
0x18006449f  mov     edx, 18Ch; void *
0x1800644a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800644a9  mov     edx, 0B9h
0x1800644ae  jmp     short loc_1800644BA
0x1800644b0  mov     ebx, 80670012h
0x1800644b5  mov     edx, 0BAh; void *
0x1800644ba  mov     rcx, [rbp+1A8h]; this
0x1800644c1  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800644c8  mov     r9d, ebx; char *
0x1800644cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800644d0  jmp     loc_1800643F1
0x1800644d5  mov     rcx, [rbp+1A8h]; this
0x1800644dc  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800644e3  mov     r9d, ebx; char *
0x1800644e6  mov     edx, 1B0h; void *
0x1800644eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800644f0  mov     edx, 0C1h
0x1800644f5  jmp     loc_18006445A
0x1800644fa  mov     rcx, [rbp+1A8h]; this
0x180064501  lea     r8, aOnecorePrivate_12; "onecore\\private\\base\\inc\\appmodel\\"...
0x180064508  mov     r9d, ebx; char *
0x18006450b  mov     edx, 1A6h; void *
0x180064510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064515  mov     edx, 0C7h
0x18006451a  jmp     loc_18006445A
```
