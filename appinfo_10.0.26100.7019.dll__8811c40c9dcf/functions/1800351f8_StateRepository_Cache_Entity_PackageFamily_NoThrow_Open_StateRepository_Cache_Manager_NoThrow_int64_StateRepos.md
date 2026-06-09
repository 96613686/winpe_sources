# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800351f8`
- end: `0x1800353ce`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `470`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002eb68`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000ea20`
- `0x1800351f8`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035321`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035385`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035321`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035385`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800353a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800353a0`

## string_xrefs

- `0x180035267`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800352ff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
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
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int *v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v17 = &v18;
  v6 = (int)a4;
  v19 = 0;
  LOBYTE(v18) = 0;
  v7 = StateRepository::Cache::Context_NoThrow::Open(&v19, a1, L"PackageFamily\\Data");
  if ( v7 < 0 )
  {
    v8 = 257;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v7,
      (int)&v18);
LABEL_4:
    v9 = v19;
    v19 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v7;
  }
  if ( !(_BYTE)v18 )
  {
    v7 = -2140733422;
    v8 = 258;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v7 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v7 < 0 )
  {
    v11 = 261;
    goto LABEL_11;
  }
  LODWORD(v17) = v6;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v24);
  if ( v7 < 0 )
  {
    v11 = 262;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v19,
         L"PackageFamily\\Data");
  if ( v7 < 0 )
  {
    v11 = 264;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v7,
      (int)v17);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13, v12);
    goto LABEL_4;
  }
  v15 = v20;
  v20 = 0;
  if ( v15 )
    SRCache_Free(v15, v14);
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x1800351f8  push    rbp
0x1800351fa  push    rbx
0x1800351fb  push    rsi
0x1800351fc  push    rdi
0x1800351fd  push    r14
0x1800351ff  push    r15
0x180035201  lea     rbp, [rsp-178h]
0x180035209  sub     rsp, 278h
0x180035210  mov     rax, cs:__security_cookie
0x180035217  xor     rax, rsp
0x18003521a  mov     [rbp+1A0h+var_40], rax
0x180035221  mov     r14, rdx
0x180035224  lea     rax, [rsp+2A0h+var_270]
0x180035229  mov     rdx, rcx
0x18003522c  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180035231  mov     rdi, r8
0x180035234  lea     rcx, [rsp+2A0h+var_268]
0x180035239  xor     r15d, r15d
0x18003523c  lea     r8, aPackagefamilyD; "PackageFamily\\Data"
0x180035243  mov     rsi, r9
0x180035246  mov     [rsp+2A0h+var_268], r15
0x18003524b  mov     byte ptr [rsp+2A0h+var_270], r15b
0x180035250  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180035255  mov     ebx, eax
0x180035257  test    eax, eax
0x180035259  jns     short loc_180035298
0x18003525b  mov     edx, 101h; void *
0x180035260  mov     rcx, [rbp+1A8h]; this
0x180035267  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003526e  mov     r9d, ebx; char *
0x180035271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035276  mov     rcx, [rsp+2A0h+var_268]
0x18003527b  mov     [rsp+2A0h+var_268], r15
0x180035280  test    rcx, rcx
0x180035283  jz      short loc_180035291
0x180035285  call    cs:__imp_SRCacheContext_Close
0x18003528c  nop     dword ptr [rax+rax+00h]
0x180035291  mov     eax, ebx
0x180035293  jmp     loc_1800353AE
0x180035298  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x18003529d  jnz     short loc_1800352AB
0x18003529f  mov     ebx, 80670012h
0x1800352a4  mov     edx, 102h
0x1800352a9  jmp     short loc_180035260
0x1800352ab  xor     edx, edx; Val
0x1800352ad  mov     [rsp+2A0h+var_260], r15
0x1800352b2  mov     r8d, 200h; Size
0x1800352b8  lea     rcx, [rsp+2A0h+var_258]; void *
0x1800352bd  call    memset_0
0x1800352c2  lea     rax, [rsp+2A0h+var_258]
0x1800352c7  mov     [rbp+1A0h+var_58], r15
0x1800352ce  mov     rdx, r14; unsigned __int64
0x1800352d1  mov     [rbp+1A0h+var_48], rax
0x1800352d8  lea     rcx, [rsp+2A0h+var_260]; this
0x1800352dd  mov     [rbp+1A0h+var_50], 100h
0x1800352e8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800352ed  mov     ebx, eax
0x1800352ef  test    eax, eax
0x1800352f1  jns     short loc_180035332
0x1800352f3  mov     edx, 105h; void *
0x1800352f8  mov     rcx, [rbp+1A8h]; this
0x1800352ff  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035306  mov     r9d, ebx; char *
0x180035309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003530e  mov     rcx, [rsp+2A0h+var_260]
0x180035313  mov     [rsp+2A0h+var_260], r15
0x180035318  test    rcx, rcx
0x18003531b  jz      loc_180035276
0x180035321  call    cs:__imp_SRCache_Free
0x180035328  nop     dword ptr [rax+rax+00h]
0x18003532d  jmp     loc_180035276
0x180035332  mov     r8, [rbp+1A0h+var_48]
0x180035339  lea     rdx, [rsp+2A0h+var_268]
0x18003533e  mov     rcx, rdi
0x180035341  mov     qword ptr [rsp+2A0h+var_280], rsi
0x180035346  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18003534b  mov     ebx, eax
0x18003534d  test    eax, eax
0x18003534f  jns     short loc_180035358
0x180035351  mov     edx, 106h
0x180035356  jmp     short loc_1800352F8
0x180035358  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18003535f  lea     rcx, [rsp+2A0h+var_268]; this
0x180035364  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180035369  mov     ebx, eax
0x18003536b  test    eax, eax
0x18003536d  jns     short loc_180035376
0x18003536f  mov     edx, 108h
0x180035374  jmp     short loc_1800352F8
0x180035376  mov     rcx, [rsp+2A0h+var_260]
0x18003537b  mov     [rsp+2A0h+var_260], r15
0x180035380  test    rcx, rcx
0x180035383  jz      short loc_180035391
0x180035385  call    cs:__imp_SRCache_Free
0x18003538c  nop     dword ptr [rax+rax+00h]
0x180035391  mov     rcx, [rsp+2A0h+var_268]
0x180035396  mov     [rsp+2A0h+var_268], r15
0x18003539b  test    rcx, rcx
0x18003539e  jz      short loc_1800353AC
0x1800353a0  call    cs:__imp_SRCacheContext_Close
0x1800353a7  nop     dword ptr [rax+rax+00h]
0x1800353ac  xor     eax, eax
0x1800353ae  mov     rcx, [rbp+1A0h+var_40]
0x1800353b5  xor     rcx, rsp; StackCookie
0x1800353b8  call    __security_check_cookie
0x1800353bd  add     rsp, 278h
0x1800353c4  pop     r15
0x1800353c6  pop     r14
0x1800353c8  pop     rdi
0x1800353c9  pop     rsi
0x1800353ca  pop     rbx
0x1800353cb  pop     rbp
0x1800353cc  retn
```
