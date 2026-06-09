# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800844e4`
- end: `0x1800846a1`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `445`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180084154`

## callees

- `0x180008be0`
- `0x18000b5c0`
- `0x18000cb80`
- `0x18002f830`
- `0x1800304a0`
- `0x18005ae90`
- `0x18005ba40`
- `0x1800844e4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180084571`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008467a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180084571`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18008467a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084607`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084665`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084607`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180084665`

## string_xrefs

- `0x180084553`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800845e5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180084528`: `ApplicationExtension\Data`
- `0x180084638`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  int v6; // esi
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int *v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+248h] [rbp+148h]
  __int64 v21; // [rsp+250h] [rbp+150h]
  _BYTE *v22; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v15 = &v16;
  v6 = (int)a4;
  v17 = 0;
  LOBYTE(v16) = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(&v17, a1, L"ApplicationExtension\\Data");
  if ( v7 < 0 )
  {
    v8 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v7,
      (int)&v16);
LABEL_4:
    v9 = v17;
    v17 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v7;
  }
  if ( !(_BYTE)v16 )
  {
    v7 = -2140733422;
    v8 = 365;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v22 = v19;
  v21 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, a2);
  if ( v7 < 0 )
  {
    v11 = 368;
    goto LABEL_11;
  }
  LODWORD(v15) = v6;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v17, v22);
  if ( v7 < 0 )
  {
    v11 = 369;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         L"ApplicationExtension\\Data");
  if ( v7 < 0 )
  {
    v11 = 371;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v7,
      (int)v15);
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_4;
  }
  v13 = v18;
  v18 = 0;
  if ( v13 )
    SRCache_Free(v13);
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  return 0;
}

```

## disassembly

```asm
0x1800844e4  push    rbp
0x1800844e6  push    rbx
0x1800844e7  push    rsi
0x1800844e8  push    rdi
0x1800844e9  push    r14
0x1800844eb  push    r15
0x1800844ed  lea     rbp, [rsp-178h]
0x1800844f5  sub     rsp, 278h
0x1800844fc  mov     rax, cs:__security_cookie
0x180084503  xor     rax, rsp
0x180084506  mov     [rbp+1A0h+var_40], rax
0x18008450d  mov     r14, rdx
0x180084510  lea     rax, [rsp+2A0h+var_270]
0x180084515  mov     rdx, rcx
0x180084518  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18008451d  mov     rdi, r8
0x180084520  lea     rcx, [rsp+2A0h+var_268]
0x180084525  xor     r15d, r15d
0x180084528  lea     r8, aApplicationext_0; "ApplicationExtension\\Data"
0x18008452f  mov     rsi, r9
0x180084532  mov     [rsp+2A0h+var_268], r15
0x180084537  mov     byte ptr [rsp+2A0h+var_270], r15b
0x18008453c  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180084541  mov     ebx, eax
0x180084543  test    eax, eax
0x180084545  jns     short loc_18008457E
0x180084547  mov     edx, 16Ch; void *
0x18008454c  mov     rcx, [rbp+1A8h]; this
0x180084553  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008455a  mov     r9d, ebx; char *
0x18008455d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084562  mov     rcx, [rsp+2A0h+var_268]
0x180084567  mov     [rsp+2A0h+var_268], r15
0x18008456c  test    rcx, rcx
0x18008456f  jz      short loc_180084577
0x180084571  call    cs:__imp_SRCacheContext_Close
0x180084577  mov     eax, ebx
0x180084579  jmp     loc_180084682
0x18008457e  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x180084583  jnz     short loc_180084591
0x180084585  mov     ebx, 80670012h
0x18008458a  mov     edx, 16Dh
0x18008458f  jmp     short loc_18008454C
0x180084591  xor     edx, edx; Val
0x180084593  mov     [rsp+2A0h+var_260], r15
0x180084598  mov     r8d, 200h; Size
0x18008459e  lea     rcx, [rsp+2A0h+var_258]; void *
0x1800845a3  call    memset_0
0x1800845a8  lea     rax, [rsp+2A0h+var_258]
0x1800845ad  mov     [rbp+1A0h+var_58], r15
0x1800845b4  mov     rdx, r14; unsigned __int64
0x1800845b7  mov     [rbp+1A0h+var_48], rax
0x1800845be  lea     rcx, [rsp+2A0h+var_260]; this
0x1800845c3  mov     [rbp+1A0h+var_50], 100h
0x1800845ce  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800845d3  mov     ebx, eax
0x1800845d5  test    eax, eax
0x1800845d7  jns     short loc_180084612
0x1800845d9  mov     edx, 170h; void *
0x1800845de  mov     rcx, [rbp+1A8h]; this
0x1800845e5  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800845ec  mov     r9d, ebx; char *
0x1800845ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800845f4  mov     rcx, [rsp+2A0h+var_260]
0x1800845f9  mov     [rsp+2A0h+var_260], r15
0x1800845fe  test    rcx, rcx
0x180084601  jz      loc_180084562
0x180084607  call    cs:__imp_SRCache_Free
0x18008460d  jmp     loc_180084562
0x180084612  mov     r8, [rbp+1A0h+var_48]
0x180084619  lea     rdx, [rsp+2A0h+var_268]
0x18008461e  mov     rcx, rdi
0x180084621  mov     qword ptr [rsp+2A0h+var_280], rsi
0x180084626  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18008462b  mov     ebx, eax
0x18008462d  test    eax, eax
0x18008462f  jns     short loc_180084638
0x180084631  mov     edx, 171h
0x180084636  jmp     short loc_1800845DE
0x180084638  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x18008463f  lea     rcx, [rsp+2A0h+var_268]; this
0x180084644  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180084649  mov     ebx, eax
0x18008464b  test    eax, eax
0x18008464d  jns     short loc_180084656
0x18008464f  mov     edx, 173h
0x180084654  jmp     short loc_1800845DE
0x180084656  mov     rcx, [rsp+2A0h+var_260]
0x18008465b  mov     [rsp+2A0h+var_260], r15
0x180084660  test    rcx, rcx
0x180084663  jz      short loc_18008466B
0x180084665  call    cs:__imp_SRCache_Free
0x18008466b  mov     rcx, [rsp+2A0h+var_268]
0x180084670  mov     [rsp+2A0h+var_268], r15
0x180084675  test    rcx, rcx
0x180084678  jz      short loc_180084680
0x18008467a  call    cs:__imp_SRCacheContext_Close
0x180084680  xor     eax, eax
0x180084682  mov     rcx, [rbp+1A0h+var_40]
0x180084689  xor     rcx, rsp; StackCookie
0x18008468c  call    __security_check_cookie
0x180084691  add     rsp, 278h
0x180084698  pop     r15
0x18008469a  pop     r14
0x18008469c  pop     rdi
0x18008469d  pop     rsi
0x18008469e  pop     rbx
0x18008469f  pop     rbp
0x1800846a0  retn
```
