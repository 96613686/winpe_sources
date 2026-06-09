# StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800352a8`
- end: `0x18003547e`
- name: `?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `470`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002d548`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e960`
- `0x1800352a8`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035335`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035450`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035335`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035450`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800353d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035435`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800353d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035435`

## string_xrefs

- `0x180035317`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800353af`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

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
0x1800352a8  push    rbp
0x1800352aa  push    rbx
0x1800352ab  push    rsi
0x1800352ac  push    rdi
0x1800352ad  push    r14
0x1800352af  push    r15
0x1800352b1  lea     rbp, [rsp-178h]
0x1800352b9  sub     rsp, 278h
0x1800352c0  mov     rax, cs:__security_cookie
0x1800352c7  xor     rax, rsp
0x1800352ca  mov     [rbp+1A0h+var_40], rax
0x1800352d1  mov     r14, rdx
0x1800352d4  lea     rax, [rsp+2A0h+var_270]
0x1800352d9  mov     rdx, rcx
0x1800352dc  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800352e1  mov     rdi, r8
0x1800352e4  lea     rcx, [rsp+2A0h+var_268]
0x1800352e9  xor     r15d, r15d
0x1800352ec  lea     r8, aPackagefamilyD; "PackageFamily\\Data"
0x1800352f3  mov     rsi, r9
0x1800352f6  mov     [rsp+2A0h+var_268], r15
0x1800352fb  mov     byte ptr [rsp+2A0h+var_270], r15b
0x180035300  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180035305  mov     ebx, eax
0x180035307  test    eax, eax
0x180035309  jns     short loc_180035348
0x18003530b  mov     edx, 101h; void *
0x180035310  mov     rcx, [rbp+1A8h]; this
0x180035317  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003531e  mov     r9d, ebx; char *
0x180035321  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035326  mov     rcx, [rsp+2A0h+var_268]
0x18003532b  mov     [rsp+2A0h+var_268], r15
0x180035330  test    rcx, rcx
0x180035333  jz      short loc_180035341
0x180035335  call    cs:__imp_SRCacheContext_Close
0x18003533c  nop     dword ptr [rax+rax+00h]
0x180035341  mov     eax, ebx
0x180035343  jmp     loc_18003545E
0x180035348  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x18003534d  jnz     short loc_18003535B
0x18003534f  mov     ebx, 80670012h
0x180035354  mov     edx, 102h
0x180035359  jmp     short loc_180035310
0x18003535b  xor     edx, edx; Val
0x18003535d  mov     [rsp+2A0h+var_260], r15
0x180035362  mov     r8d, 200h; Size
0x180035368  lea     rcx, [rsp+2A0h+var_258]; void *
0x18003536d  call    memset_0
0x180035372  lea     rax, [rsp+2A0h+var_258]
0x180035377  mov     [rbp+1A0h+var_58], r15
0x18003537e  mov     rdx, r14; unsigned __int64
0x180035381  mov     [rbp+1A0h+var_48], rax
0x180035388  lea     rcx, [rsp+2A0h+var_260]; this
0x18003538d  mov     [rbp+1A0h+var_50], 100h
0x180035398  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18003539d  mov     ebx, eax
0x18003539f  test    eax, eax
0x1800353a1  jns     short loc_1800353E2
0x1800353a3  mov     edx, 105h; void *
0x1800353a8  mov     rcx, [rbp+1A8h]; this
0x1800353af  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800353b6  mov     r9d, ebx; char *
0x1800353b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800353be  mov     rcx, [rsp+2A0h+var_260]
0x1800353c3  mov     [rsp+2A0h+var_260], r15
0x1800353c8  test    rcx, rcx
0x1800353cb  jz      loc_180035326
0x1800353d1  call    cs:__imp_SRCache_Free
0x1800353d8  nop     dword ptr [rax+rax+00h]
0x1800353dd  jmp     loc_180035326
0x1800353e2  mov     r8, [rbp+1A0h+var_48]
0x1800353e9  lea     rdx, [rsp+2A0h+var_268]
0x1800353ee  mov     rcx, rdi
0x1800353f1  mov     qword ptr [rsp+2A0h+var_280], rsi
0x1800353f6  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800353fb  mov     ebx, eax
0x1800353fd  test    eax, eax
0x1800353ff  jns     short loc_180035408
0x180035401  mov     edx, 106h
0x180035406  jmp     short loc_1800353A8
0x180035408  lea     rdx, aPackagefamilyD; "PackageFamily\\Data"
0x18003540f  lea     rcx, [rsp+2A0h+var_268]; this
0x180035414  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180035419  mov     ebx, eax
0x18003541b  test    eax, eax
0x18003541d  jns     short loc_180035426
0x18003541f  mov     edx, 108h
0x180035424  jmp     short loc_1800353A8
0x180035426  mov     rcx, [rsp+2A0h+var_260]
0x18003542b  mov     [rsp+2A0h+var_260], r15
0x180035430  test    rcx, rcx
0x180035433  jz      short loc_180035441
0x180035435  call    cs:__imp_SRCache_Free
0x18003543c  nop     dword ptr [rax+rax+00h]
0x180035441  mov     rcx, [rsp+2A0h+var_268]
0x180035446  mov     [rsp+2A0h+var_268], r15
0x18003544b  test    rcx, rcx
0x18003544e  jz      short loc_18003545C
0x180035450  call    cs:__imp_SRCacheContext_Close
0x180035457  nop     dword ptr [rax+rax+00h]
0x18003545c  xor     eax, eax
0x18003545e  mov     rcx, [rbp+1A0h+var_40]
0x180035465  xor     rcx, rsp; StackCookie
0x180035468  call    __security_check_cookie
0x18003546d  add     rsp, 278h
0x180035474  pop     r15
0x180035476  pop     r14
0x180035478  pop     rdi
0x180035479  pop     rsi
0x18003547a  pop     rbx
0x18003547b  pop     rbp
0x18003547c  retn
```
