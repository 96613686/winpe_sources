# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x1800353d4`
- end: `0x180035684`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `688`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002b2a4`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000ea20`
- `0x1800353d4`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035614`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035634`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035614`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035634`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035443`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800354af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800354fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003564f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180035443`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800354af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800354fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003564f`

## string_xrefs

- `0x180035418`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18003548c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800354d0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180035561`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800355ed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

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
0x1800353d4  mov     [rsp-8+arg_18], rbx
0x1800353d9  push    rbp
0x1800353da  push    rsi
0x1800353db  push    rdi
0x1800353dc  push    r14
0x1800353de  push    r15
0x1800353e0  lea     rbp, [rsp-170h]
0x1800353e8  sub     rsp, 270h
0x1800353ef  mov     rax, cs:__security_cookie
0x1800353f6  xor     rax, rsp
0x1800353f9  mov     [rbp+190h+var_30], rax
0x180035400  xor     r15d, r15d
0x180035403  mov     r14, r8
0x180035406  mov     rsi, rdx
0x180035409  mov     rbx, rcx
0x18003540c  test    r8, r8
0x18003540f  jnz     short loc_180035438
0x180035411  mov     rcx, [rbp+198h]; this
0x180035418  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003541f  mov     ebx, 80070057h
0x180035424  mov     edx, 3DFh; void *
0x180035429  mov     r9d, ebx; char *
0x18003542c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035431  mov     eax, ebx
0x180035433  jmp     loc_18003565D
0x180035438  mov     rcx, [rcx]
0x18003543b  mov     [rbx], r15
0x18003543e  test    rcx, rcx
0x180035441  jz      short loc_18003544F
0x180035443  call    cs:__imp_SRCacheContext_Close
0x18003544a  nop     dword ptr [rax+rax+00h]
0x18003544f  lea     rax, [rsp+290h+var_260]
0x180035454  mov     [rbx+8], r15d
0x180035458  lea     r8, aApplicationInd; "Application\\Index\\Package"
0x18003545f  mov     qword ptr [rsp+290h+var_270], rax; int
0x180035464  mov     rdx, rsi
0x180035467  mov     [rbx+10h], r15
0x18003546b  lea     rcx, [rsp+290h+var_258]
0x180035470  mov     [rsp+290h+var_258], r15
0x180035475  mov     byte ptr [rsp+290h+var_260], r15b
0x18003547a  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18003547f  mov     edi, eax
0x180035481  test    eax, eax
0x180035483  jns     short loc_1800354C2
0x180035485  mov     rcx, [rbp+198h]; this
0x18003548c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035493  mov     r9d, eax; char *
0x180035496  mov     edx, 3E5h; void *
0x18003549b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800354a0  mov     rcx, [rsp+290h+var_258]
0x1800354a5  mov     [rsp+290h+var_258], r15
0x1800354aa  test    rcx, rcx
0x1800354ad  jz      short loc_1800354BB
0x1800354af  call    cs:__imp_SRCacheContext_Close
0x1800354b6  nop     dword ptr [rax+rax+00h]
0x1800354bb  mov     eax, edi
0x1800354bd  jmp     loc_18003565D
0x1800354c2  cmp     byte ptr [rsp+290h+var_260], r15b
0x1800354c7  jnz     short loc_18003550D
0x1800354c9  mov     rcx, [rbp+198h]; this
0x1800354d0  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800354d7  mov     ebx, 80670012h
0x1800354dc  mov     edx, 3E6h; void *
0x1800354e1  mov     r9d, ebx; char *
0x1800354e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800354e9  mov     rcx, [rsp+290h+var_258]
0x1800354ee  mov     [rsp+290h+var_258], r15
0x1800354f3  test    rcx, rcx
0x1800354f6  jz      loc_180035431
0x1800354fc  call    cs:__imp_SRCacheContext_Close
0x180035503  nop     dword ptr [rax+rax+00h]
0x180035508  jmp     loc_180035431
0x18003550d  xor     edx, edx; Val
0x18003550f  mov     [rsp+290h+var_250], r15
0x180035514  mov     r8d, 200h; Size
0x18003551a  lea     rcx, [rsp+290h+var_248]; void *
0x18003551f  call    memset_0
0x180035524  lea     rax, [rsp+290h+var_248]
0x180035529  mov     [rbp+190h+var_48], r15
0x180035530  mov     rdx, r14; unsigned __int64
0x180035533  mov     [rbp+190h+var_38], rax
0x18003553a  lea     rcx, [rsp+290h+var_250]; this
0x18003553f  mov     [rbp+190h+var_40], 100h
0x18003554a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18003554f  mov     edi, eax
0x180035551  test    eax, eax
0x180035553  jns     short loc_180035594
0x180035555  mov     edx, 3E9h; void *
0x18003555a  mov     rcx, [rbp+198h]; this
0x180035561  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035568  mov     r9d, edi; char *
0x18003556b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035570  mov     rcx, [rsp+290h+var_250]
0x180035575  mov     [rsp+290h+var_250], r15
0x18003557a  test    rcx, rcx
0x18003557d  jz      loc_1800354A0
0x180035583  call    cs:__imp_SRCache_Free
0x18003558a  nop     dword ptr [rax+rax+00h]
0x18003558f  jmp     loc_1800354A0
0x180035594  mov     r8, [rbp+190h+var_38]
0x18003559b  lea     rax, [rsp+290h+var_260]
0x1800355a0  lea     rdx, [rsp+290h+var_258]
0x1800355a5  mov     qword ptr [rsp+290h+var_270], rax; int
0x1800355aa  mov     rcx, rbx
0x1800355ad  mov     byte ptr [rsp+290h+var_260], r15b
0x1800355b2  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800355b7  mov     edi, eax
0x1800355b9  test    eax, eax
0x1800355bb  jns     short loc_1800355C4
0x1800355bd  mov     edx, 3ECh
0x1800355c2  jmp     short loc_18003555A
0x1800355c4  cmp     byte ptr [rsp+290h+var_260], r15b
0x1800355c9  jz      short loc_1800355CF
0x1800355cb  mov     [rbx+10h], rsi
0x1800355cf  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x1800355d6  lea     rcx, [rsp+290h+var_258]; this
0x1800355db  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800355e0  mov     ebx, eax
0x1800355e2  test    eax, eax
0x1800355e4  jns     short loc_180035625
0x1800355e6  mov     rcx, [rbp+198h]; this
0x1800355ed  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800355f4  mov     r9d, eax; char *
0x1800355f7  mov     edx, 3F2h; void *
0x1800355fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035601  mov     rcx, [rsp+290h+var_250]
0x180035606  mov     [rsp+290h+var_250], r15
0x18003560b  test    rcx, rcx
0x18003560e  jz      loc_1800354E9
0x180035614  call    cs:__imp_SRCache_Free
0x18003561b  nop     dword ptr [rax+rax+00h]
0x180035620  jmp     loc_1800354E9
0x180035625  mov     rcx, [rsp+290h+var_250]
0x18003562a  mov     [rsp+290h+var_250], r15
0x18003562f  test    rcx, rcx
0x180035632  jz      short loc_180035640
0x180035634  call    cs:__imp_SRCache_Free
0x18003563b  nop     dword ptr [rax+rax+00h]
0x180035640  mov     rcx, [rsp+290h+var_258]
0x180035645  mov     [rsp+290h+var_258], r15
0x18003564a  test    rcx, rcx
0x18003564d  jz      short loc_18003565B
0x18003564f  call    cs:__imp_SRCacheContext_Close
0x180035656  nop     dword ptr [rax+rax+00h]
0x18003565b  xor     eax, eax
0x18003565d  mov     rcx, [rbp+190h+var_30]
0x180035664  xor     rcx, rsp; StackCookie
0x180035667  call    __security_check_cookie
0x18003566c  mov     rbx, [rsp+290h+arg_18]
0x180035674  add     rsp, 270h
0x18003567b  pop     r15
0x18003567d  pop     r14
0x18003567f  pop     rdi
0x180035680  pop     rsi
0x180035681  pop     rbp
0x180035682  retn
```
