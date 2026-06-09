# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180035568`
- end: `0x18003573e`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `470`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002d618`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e960`
- `0x180035568`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800355f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035710`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800355f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035710`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035691`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800356f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035691`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800356f5`

## string_xrefs

- `0x1800355d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18003566f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

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
0x180035568  push    rbp
0x18003556a  push    rbx
0x18003556b  push    rsi
0x18003556c  push    rdi
0x18003556d  push    r14
0x18003556f  push    r15
0x180035571  lea     rbp, [rsp-178h]
0x180035579  sub     rsp, 278h
0x180035580  mov     rax, cs:__security_cookie
0x180035587  xor     rax, rsp
0x18003558a  mov     [rbp+1A0h+var_40], rax
0x180035591  mov     r14, rdx
0x180035594  lea     rax, [rsp+2A0h+var_270]
0x180035599  mov     rdx, rcx
0x18003559c  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800355a1  mov     rdi, r8
0x1800355a4  lea     rcx, [rsp+2A0h+var_268]
0x1800355a9  xor     r15d, r15d
0x1800355ac  lea     r8, aPackagefamilyD; "PackageFamily\\Data"
0x1800355b3  mov     rsi, r9
0x1800355b6  mov     [rsp+2A0h+var_268], r15
0x1800355bb  mov     byte ptr [rsp+2A0h+var_270], r15b
0x1800355c0  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800355c5  mov     ebx, eax
0x1800355c7  test    eax, eax
0x1800355c9  jns     short loc_180035608
0x1800355cb  mov     edx, 101h; void *
0x1800355d0  mov     rcx, [rbp+1A8h]; this
0x1800355d7  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800355de  mov     r9d, ebx; char *
0x1800355e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800355e6  mov     rcx, [rsp+2A0h+var_268]
0x1800355eb  mov     [rsp+2A0h+var_268], r15
0x1800355f0  test    rcx, rcx
0x1800355f3  jz      short loc_180035601
0x1800355f5  call    cs:__imp_SRCacheContext_Close
0x1800355fc  nop     dword ptr [rax+rax+00h]
0x180035601  mov     eax, ebx
0x180035603  jmp     loc_18003571E
0x180035608  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x18003560d  jnz     short loc_18003561B
0x18003560f  mov     ebx, 80670012h
0x180035614  mov     edx, 102h
0x180035619  jmp     short loc_1800355D0
0x18003561b  xor     edx, edx; Val
0x18003561d  mov     [rsp+2A0h+var_260], r15
0x180035622  mov     r8d, 200h; Size
0x180035628  lea     rcx, [rsp+2A0h+var_258]; void *
0x18003562d  call    memset_0
0x180035632  lea     rax, [rsp+2A0h+var_258]
0x180035637  mov     [rbp+1A0h+var_58], r15
0x18003563e  mov     rdx, r14; unsigned __int64
0x180035641  mov     [rbp+1A0h+var_48], rax
0x180035648  lea     rcx, [rsp+2A0h+var_260]; this
0x18003564d  mov     [rbp+1A0h+var_50], 100h
0x180035658  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18003565d  mov     ebx, eax
0x18003565f  test    eax, eax
0x180035661  jns     short loc_1800356A2
0x180035663  mov     edx, 105h; void *
0x180035668  mov     rcx, [rbp+1A8h]; this
0x18003566f  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035676  mov     r9d, ebx; char *
0x180035679  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003567e  mov     rcx, [rsp+2A0h+var_260]
0x180035683  mov     [rsp+2A0h+var_260], r15
0x180035688  test    rcx, rcx
0x18003568b  jz      loc_1800355E6
0x180035691  call    cs:__imp_SRCache_Free
0x180035698  nop     dword ptr [rax+rax+00h]
0x18003569d  jmp     loc_1800355E6
0x1800356a2  mov     r8, [rbp+1A0h+var_48]
0x1800356a9  lea     rdx, [rsp+2A0h+var_268]
0x1800356ae  mov     rcx, rdi
0x1800356b1  mov     qword ptr [rsp+2A0h+var_280], rsi
0x1800356b6  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800356bb  mov     ebx, eax
0x1800356bd  test    eax, eax
0x1800356bf  jns     short loc_1800356C8
0x1800356c1  mov     edx, 106h
0x1800356c6  jmp     short loc_180035668
0x1800356c8  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x1800356cf  lea     rcx, [rsp+2A0h+var_268]; this
0x1800356d4  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800356d9  mov     ebx, eax
0x1800356db  test    eax, eax
0x1800356dd  jns     short loc_1800356E6
0x1800356df  mov     edx, 108h
0x1800356e4  jmp     short loc_180035668
0x1800356e6  mov     rcx, [rsp+2A0h+var_260]
0x1800356eb  mov     [rsp+2A0h+var_260], r15
0x1800356f0  test    rcx, rcx
0x1800356f3  jz      short loc_180035701
0x1800356f5  call    cs:__imp_SRCache_Free
0x1800356fc  nop     dword ptr [rax+rax+00h]
0x180035701  mov     rcx, [rsp+2A0h+var_268]
0x180035706  mov     [rsp+2A0h+var_268], r15
0x18003570b  test    rcx, rcx
0x18003570e  jz      short loc_18003571C
0x180035710  call    cs:__imp_SRCacheContext_Close
0x180035717  nop     dword ptr [rax+rax+00h]
0x18003571c  xor     eax, eax
0x18003571e  mov     rcx, [rbp+1A0h+var_40]
0x180035725  xor     rcx, rsp; StackCookie
0x180035728  call    __security_check_cookie
0x18003572d  add     rsp, 278h
0x180035734  pop     r15
0x180035736  pop     r14
0x180035738  pop     rdi
0x180035739  pop     rsi
0x18003573a  pop     rbx
0x18003573b  pop     rbp
0x18003573c  retn
```
