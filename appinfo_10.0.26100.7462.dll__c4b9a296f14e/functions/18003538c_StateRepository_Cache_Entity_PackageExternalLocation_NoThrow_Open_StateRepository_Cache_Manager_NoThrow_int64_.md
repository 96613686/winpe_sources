# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18003538c`
- end: `0x180035562`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `470`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002d4e8`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e960`
- `0x18003538c`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035419`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035534`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035419`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035534`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800354b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035519`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800354b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035519`

## string_xrefs

- `0x1800353fb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x180035493`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
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
  v7 = StateRepository::Cache::Context_NoThrow::Open(&v19, a1, L"PackageExternalLocation\\Data");
  if ( v7 < 0 )
  {
    v8 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
    v8 = 251;
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
    v11 = 254;
    goto LABEL_11;
  }
  LODWORD(v17) = v6;
  v7 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v24);
  if ( v7 < 0 )
  {
    v11 = 255;
    goto LABEL_11;
  }
  v7 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v19,
         L"PackageExternalLocation\\Data");
  if ( v7 < 0 )
  {
    v11 = 257;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
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
0x18003538c  push    rbp
0x18003538e  push    rbx
0x18003538f  push    rsi
0x180035390  push    rdi
0x180035391  push    r14
0x180035393  push    r15
0x180035395  lea     rbp, [rsp-178h]
0x18003539d  sub     rsp, 278h
0x1800353a4  mov     rax, cs:__security_cookie
0x1800353ab  xor     rax, rsp
0x1800353ae  mov     [rbp+1A0h+var_40], rax
0x1800353b5  mov     r14, rdx
0x1800353b8  lea     rax, [rsp+2A0h+var_270]
0x1800353bd  mov     rdx, rcx
0x1800353c0  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800353c5  mov     rdi, r8
0x1800353c8  lea     rcx, [rsp+2A0h+var_268]
0x1800353cd  xor     r15d, r15d
0x1800353d0  lea     r8, aPackageexterna; "PackageExternalLocation\\Data"
0x1800353d7  mov     rsi, r9
0x1800353da  mov     [rsp+2A0h+var_268], r15
0x1800353df  mov     byte ptr [rsp+2A0h+var_270], r15b
0x1800353e4  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800353e9  mov     ebx, eax
0x1800353eb  test    eax, eax
0x1800353ed  jns     short loc_18003542C
0x1800353ef  mov     edx, 0FAh; void *
0x1800353f4  mov     rcx, [rbp+1A8h]; this
0x1800353fb  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035402  mov     r9d, ebx; char *
0x180035405  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003540a  mov     rcx, [rsp+2A0h+var_268]
0x18003540f  mov     [rsp+2A0h+var_268], r15
0x180035414  test    rcx, rcx
0x180035417  jz      short loc_180035425
0x180035419  call    cs:__imp_SRCacheContext_Close
0x180035420  nop     dword ptr [rax+rax+00h]
0x180035425  mov     eax, ebx
0x180035427  jmp     loc_180035542
0x18003542c  cmp     byte ptr [rsp+2A0h+var_270], r15b
0x180035431  jnz     short loc_18003543F
0x180035433  mov     ebx, 80670012h
0x180035438  mov     edx, 0FBh
0x18003543d  jmp     short loc_1800353F4
0x18003543f  xor     edx, edx; Val
0x180035441  mov     [rsp+2A0h+var_260], r15
0x180035446  mov     r8d, 200h; Size
0x18003544c  lea     rcx, [rsp+2A0h+var_258]; void *
0x180035451  call    memset_0
0x180035456  lea     rax, [rsp+2A0h+var_258]
0x18003545b  mov     [rbp+1A0h+var_58], r15
0x180035462  mov     rdx, r14; unsigned __int64
0x180035465  mov     [rbp+1A0h+var_48], rax
0x18003546c  lea     rcx, [rsp+2A0h+var_260]; this
0x180035471  mov     [rbp+1A0h+var_50], 100h
0x18003547c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180035481  mov     ebx, eax
0x180035483  test    eax, eax
0x180035485  jns     short loc_1800354C6
0x180035487  mov     edx, 0FEh; void *
0x18003548c  mov     rcx, [rbp+1A8h]; this
0x180035493  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003549a  mov     r9d, ebx; char *
0x18003549d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800354a2  mov     rcx, [rsp+2A0h+var_260]
0x1800354a7  mov     [rsp+2A0h+var_260], r15
0x1800354ac  test    rcx, rcx
0x1800354af  jz      loc_18003540A
0x1800354b5  call    cs:__imp_SRCache_Free
0x1800354bc  nop     dword ptr [rax+rax+00h]
0x1800354c1  jmp     loc_18003540A
0x1800354c6  mov     r8, [rbp+1A0h+var_48]
0x1800354cd  lea     rdx, [rsp+2A0h+var_268]
0x1800354d2  mov     rcx, rdi
0x1800354d5  mov     qword ptr [rsp+2A0h+var_280], rsi
0x1800354da  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800354df  mov     ebx, eax
0x1800354e1  test    eax, eax
0x1800354e3  jns     short loc_1800354EC
0x1800354e5  mov     edx, 0FFh
0x1800354ea  jmp     short loc_18003548C
0x1800354ec  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x1800354f3  lea     rcx, [rsp+2A0h+var_268]; this
0x1800354f8  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800354fd  mov     ebx, eax
0x1800354ff  test    eax, eax
0x180035501  jns     short loc_18003550A
0x180035503  mov     edx, 101h
0x180035508  jmp     short loc_18003548C
0x18003550a  mov     rcx, [rsp+2A0h+var_260]
0x18003550f  mov     [rsp+2A0h+var_260], r15
0x180035514  test    rcx, rcx
0x180035517  jz      short loc_180035525
0x180035519  call    cs:__imp_SRCache_Free
0x180035520  nop     dword ptr [rax+rax+00h]
0x180035525  mov     rcx, [rsp+2A0h+var_268]
0x18003552a  mov     [rsp+2A0h+var_268], r15
0x18003552f  test    rcx, rcx
0x180035532  jz      short loc_180035540
0x180035534  call    cs:__imp_SRCacheContext_Close
0x18003553b  nop     dword ptr [rax+rax+00h]
0x180035540  xor     eax, eax
0x180035542  mov     rcx, [rbp+1A0h+var_40]
0x180035549  xor     rcx, rsp; StackCookie
0x18003554c  call    __security_check_cookie
0x180035551  add     rsp, 278h
0x180035558  pop     r15
0x18003555a  pop     r14
0x18003555c  pop     rdi
0x18003555d  pop     rsi
0x18003555e  pop     rbx
0x18003555f  pop     rbp
0x180035560  retn
```
