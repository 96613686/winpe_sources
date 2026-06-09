# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180035484`
- end: `0x180035734`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `688`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180029c54`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e960`
- `0x180035484`
- `0x1800444ba`
- `0x1800444e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800354f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003555f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800355ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800356ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800354f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003555f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800355ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800356ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035633`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800356c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800356e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035633`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800356c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800356e4`

## string_xrefs

- `0x1800354c8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18003553c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180035580`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180035611`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18003569d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(
        StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !a3 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v12);
    return v5;
  }
  v7 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v7 )
    SRCacheContext_Close(v7);
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  v14 = 0;
  LOBYTE(v13) = 0;
  v8 = StateRepository::Cache::Context_NoThrow::Open(&v14, a2, L"Application\\Index\\Package");
  v9 = v8;
  if ( v8 >= 0 )
  {
    v5 = -2140733422;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)0x80670012LL,
      (int)&v13);
    v11 = v14;
    v14 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
    (const char *)(unsigned int)v8,
    (int)&v13);
  v10 = v14;
  v14 = 0;
  if ( v10 )
    SRCacheContext_Close(v10);
  return v9;
}

```

## disassembly

```asm
0x180035484  mov     [rsp-8+arg_18], rbx
0x180035489  push    rbp
0x18003548a  push    rsi
0x18003548b  push    rdi
0x18003548c  push    r14
0x18003548e  push    r15
0x180035490  lea     rbp, [rsp-170h]
0x180035498  sub     rsp, 270h
0x18003549f  mov     rax, cs:__security_cookie
0x1800354a6  xor     rax, rsp
0x1800354a9  mov     [rbp+190h+var_30], rax
0x1800354b0  xor     r15d, r15d
0x1800354b3  mov     r14, r8
0x1800354b6  mov     rsi, rdx
0x1800354b9  mov     rbx, rcx
0x1800354bc  test    r8, r8
0x1800354bf  jnz     short loc_1800354E8
0x1800354c1  mov     rcx, [rbp+198h]; this
0x1800354c8  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800354cf  mov     ebx, 80070057h
0x1800354d4  mov     edx, 3DFh; void *
0x1800354d9  mov     r9d, ebx; char *
0x1800354dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800354e1  mov     eax, ebx
0x1800354e3  jmp     loc_18003570D
0x1800354e8  mov     rcx, [rcx]
0x1800354eb  mov     [rbx], r15
0x1800354ee  test    rcx, rcx
0x1800354f1  jz      short loc_1800354FF
0x1800354f3  call    cs:__imp_SRCacheContext_Close
0x1800354fa  nop     dword ptr [rax+rax+00h]
0x1800354ff  lea     rax, [rsp+290h+var_260]
0x180035504  mov     [rbx+8], r15d
0x180035508  lea     r8, aApplicationInd; "Application\\Index\\Package"
0x18003550f  mov     qword ptr [rsp+290h+var_270], rax; int
0x180035514  mov     rdx, rsi
0x180035517  mov     [rbx+10h], r15
0x18003551b  lea     rcx, [rsp+290h+var_258]
0x180035520  mov     [rsp+290h+var_258], r15
0x180035525  mov     byte ptr [rsp+290h+var_260], r15b
0x18003552a  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18003552f  mov     edi, eax
0x180035531  test    eax, eax
0x180035533  jns     short loc_180035572
0x180035535  mov     rcx, [rbp+198h]; this
0x18003553c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035543  mov     r9d, eax; char *
0x180035546  mov     edx, 3E5h; void *
0x18003554b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035550  mov     rcx, [rsp+290h+var_258]
0x180035555  mov     [rsp+290h+var_258], r15
0x18003555a  test    rcx, rcx
0x18003555d  jz      short loc_18003556B
0x18003555f  call    cs:__imp_SRCacheContext_Close
0x180035566  nop     dword ptr [rax+rax+00h]
0x18003556b  mov     eax, edi
0x18003556d  jmp     loc_18003570D
0x180035572  cmp     byte ptr [rsp+290h+var_260], r15b
0x180035577  jnz     short loc_1800355BD
0x180035579  mov     rcx, [rbp+198h]; this
0x180035580  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035587  mov     ebx, 80670012h
0x18003558c  mov     edx, 3E6h; void *
0x180035591  mov     r9d, ebx; char *
0x180035594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035599  mov     rcx, [rsp+290h+var_258]
0x18003559e  mov     [rsp+290h+var_258], r15
0x1800355a3  test    rcx, rcx
0x1800355a6  jz      loc_1800354E1
0x1800355ac  call    cs:__imp_SRCacheContext_Close
0x1800355b3  nop     dword ptr [rax+rax+00h]
0x1800355b8  jmp     loc_1800354E1
0x1800355bd  xor     edx, edx; Val
0x1800355bf  mov     [rsp+290h+var_250], r15
0x1800355c4  mov     r8d, 200h; Size
0x1800355ca  lea     rcx, [rsp+290h+var_248]; void *
0x1800355cf  call    memset_0
0x1800355d4  lea     rax, [rsp+290h+var_248]
0x1800355d9  mov     [rbp+190h+var_48], r15
0x1800355e0  mov     rdx, r14; unsigned __int64
0x1800355e3  mov     [rbp+190h+var_38], rax
0x1800355ea  lea     rcx, [rsp+290h+var_250]; this
0x1800355ef  mov     [rbp+190h+var_40], 100h
0x1800355fa  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800355ff  mov     edi, eax
0x180035601  test    eax, eax
0x180035603  jns     short loc_180035644
0x180035605  mov     edx, 3E9h; void *
0x18003560a  mov     rcx, [rbp+198h]; this
0x180035611  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035618  mov     r9d, edi; char *
0x18003561b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035620  mov     rcx, [rsp+290h+var_250]
0x180035625  mov     [rsp+290h+var_250], r15
0x18003562a  test    rcx, rcx
0x18003562d  jz      loc_180035550
0x180035633  call    cs:__imp_SRCache_Free
0x18003563a  nop     dword ptr [rax+rax+00h]
0x18003563f  jmp     loc_180035550
0x180035644  mov     r8, [rbp+190h+var_38]
0x18003564b  lea     rax, [rsp+290h+var_260]
0x180035650  lea     rdx, [rsp+290h+var_258]
0x180035655  mov     qword ptr [rsp+290h+var_270], rax; int
0x18003565a  mov     rcx, rbx
0x18003565d  mov     byte ptr [rsp+290h+var_260], r15b
0x180035662  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180035667  mov     edi, eax
0x180035669  test    eax, eax
0x18003566b  jns     short loc_180035674
0x18003566d  mov     edx, 3ECh
0x180035672  jmp     short loc_18003560A
0x180035674  cmp     byte ptr [rsp+290h+var_260], r15b
0x180035679  jz      short loc_18003567F
0x18003567b  mov     [rbx+10h], rsi
0x18003567f  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x180035686  lea     rcx, [rsp+290h+var_258]; this
0x18003568b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180035690  mov     ebx, eax
0x180035692  test    eax, eax
0x180035694  jns     short loc_1800356D5
0x180035696  mov     rcx, [rbp+198h]; this
0x18003569d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800356a4  mov     r9d, eax; char *
0x1800356a7  mov     edx, 3F2h; void *
0x1800356ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800356b1  mov     rcx, [rsp+290h+var_250]
0x1800356b6  mov     [rsp+290h+var_250], r15
0x1800356bb  test    rcx, rcx
0x1800356be  jz      loc_180035599
0x1800356c4  call    cs:__imp_SRCache_Free
0x1800356cb  nop     dword ptr [rax+rax+00h]
0x1800356d0  jmp     loc_180035599
0x1800356d5  mov     rcx, [rsp+290h+var_250]
0x1800356da  mov     [rsp+290h+var_250], r15
0x1800356df  test    rcx, rcx
0x1800356e2  jz      short loc_1800356F0
0x1800356e4  call    cs:__imp_SRCache_Free
0x1800356eb  nop     dword ptr [rax+rax+00h]
0x1800356f0  mov     rcx, [rsp+290h+var_258]
0x1800356f5  mov     [rsp+290h+var_258], r15
0x1800356fa  test    rcx, rcx
0x1800356fd  jz      short loc_18003570B
0x1800356ff  call    cs:__imp_SRCacheContext_Close
0x180035706  nop     dword ptr [rax+rax+00h]
0x18003570b  xor     eax, eax
0x18003570d  mov     rcx, [rbp+190h+var_30]
0x180035714  xor     rcx, rsp; StackCookie
0x180035717  call    __security_check_cookie
0x18003571c  mov     rbx, [rsp+290h+arg_18]
0x180035724  add     rsp, 270h
0x18003572b  pop     r15
0x18003572d  pop     r14
0x18003572f  pop     rdi
0x180035730  pop     rsi
0x180035731  pop     rbp
0x180035732  retn
```
