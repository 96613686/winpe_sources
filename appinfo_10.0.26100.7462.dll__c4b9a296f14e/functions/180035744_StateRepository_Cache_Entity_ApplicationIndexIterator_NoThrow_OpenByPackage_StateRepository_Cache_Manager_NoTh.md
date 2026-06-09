# StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow::OpenByPackage(StateRepository::Cache::Manager_NoThrow &,__int64)

- ea: `0x180035744`
- end: `0x1800359f4`
- name: `?OpenByPackage@ApplicationIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z`
- size: `688`
- prototype: `int(StateRepository::Cache::Entity::ApplicationIndexIterator_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180029d24`

## callees

- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000b430`
- `0x18000e960`
- `0x180035744`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800357b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003581f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003586c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800359bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800357b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003581f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18003586c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800359bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800358f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035984`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800359a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800358f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180035984`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800359a4`

## string_xrefs

- `0x180035788`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800357fc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180035840`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800358d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18003595d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

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
0x180035744  mov     [rsp-8+arg_18], rbx
0x180035749  push    rbp
0x18003574a  push    rsi
0x18003574b  push    rdi
0x18003574c  push    r14
0x18003574e  push    r15
0x180035750  lea     rbp, [rsp-170h]
0x180035758  sub     rsp, 270h
0x18003575f  mov     rax, cs:__security_cookie
0x180035766  xor     rax, rsp
0x180035769  mov     [rbp+190h+var_30], rax
0x180035770  xor     r15d, r15d
0x180035773  mov     r14, r8
0x180035776  mov     rsi, rdx
0x180035779  mov     rbx, rcx
0x18003577c  test    r8, r8
0x18003577f  jnz     short loc_1800357A8
0x180035781  mov     rcx, [rbp+198h]; this
0x180035788  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003578f  mov     ebx, 80070057h
0x180035794  mov     edx, 3DFh; void *
0x180035799  mov     r9d, ebx; char *
0x18003579c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800357a1  mov     eax, ebx
0x1800357a3  jmp     loc_1800359CD
0x1800357a8  mov     rcx, [rcx]
0x1800357ab  mov     [rbx], r15
0x1800357ae  test    rcx, rcx
0x1800357b1  jz      short loc_1800357BF
0x1800357b3  call    cs:__imp_SRCacheContext_Close
0x1800357ba  nop     dword ptr [rax+rax+00h]
0x1800357bf  lea     rax, [rsp+290h+var_260]
0x1800357c4  mov     [rbx+8], r15d
0x1800357c8  lea     r8, aApplicationInd; "Application\\Index\\Package"
0x1800357cf  mov     qword ptr [rsp+290h+var_270], rax; int
0x1800357d4  mov     rdx, rsi
0x1800357d7  mov     [rbx+10h], r15
0x1800357db  lea     rcx, [rsp+290h+var_258]
0x1800357e0  mov     [rsp+290h+var_258], r15
0x1800357e5  mov     byte ptr [rsp+290h+var_260], r15b
0x1800357ea  call    ?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800357ef  mov     edi, eax
0x1800357f1  test    eax, eax
0x1800357f3  jns     short loc_180035832
0x1800357f5  mov     rcx, [rbp+198h]; this
0x1800357fc  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035803  mov     r9d, eax; char *
0x180035806  mov     edx, 3E5h; void *
0x18003580b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035810  mov     rcx, [rsp+290h+var_258]
0x180035815  mov     [rsp+290h+var_258], r15
0x18003581a  test    rcx, rcx
0x18003581d  jz      short loc_18003582B
0x18003581f  call    cs:__imp_SRCacheContext_Close
0x180035826  nop     dword ptr [rax+rax+00h]
0x18003582b  mov     eax, edi
0x18003582d  jmp     loc_1800359CD
0x180035832  cmp     byte ptr [rsp+290h+var_260], r15b
0x180035837  jnz     short loc_18003587D
0x180035839  mov     rcx, [rbp+198h]; this
0x180035840  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035847  mov     ebx, 80670012h
0x18003584c  mov     edx, 3E6h; void *
0x180035851  mov     r9d, ebx; char *
0x180035854  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035859  mov     rcx, [rsp+290h+var_258]
0x18003585e  mov     [rsp+290h+var_258], r15
0x180035863  test    rcx, rcx
0x180035866  jz      loc_1800357A1
0x18003586c  call    cs:__imp_SRCacheContext_Close
0x180035873  nop     dword ptr [rax+rax+00h]
0x180035878  jmp     loc_1800357A1
0x18003587d  xor     edx, edx; Val
0x18003587f  mov     [rsp+290h+var_250], r15
0x180035884  mov     r8d, 200h; Size
0x18003588a  lea     rcx, [rsp+290h+var_248]; void *
0x18003588f  call    memset_0
0x180035894  lea     rax, [rsp+290h+var_248]
0x180035899  mov     [rbp+190h+var_48], r15
0x1800358a0  mov     rdx, r14; unsigned __int64
0x1800358a3  mov     [rbp+190h+var_38], rax
0x1800358aa  lea     rcx, [rsp+290h+var_250]; this
0x1800358af  mov     [rbp+190h+var_40], 100h
0x1800358ba  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800358bf  mov     edi, eax
0x1800358c1  test    eax, eax
0x1800358c3  jns     short loc_180035904
0x1800358c5  mov     edx, 3E9h; void *
0x1800358ca  mov     rcx, [rbp+198h]; this
0x1800358d1  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800358d8  mov     r9d, edi; char *
0x1800358db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358e0  mov     rcx, [rsp+290h+var_250]
0x1800358e5  mov     [rsp+290h+var_250], r15
0x1800358ea  test    rcx, rcx
0x1800358ed  jz      loc_180035810
0x1800358f3  call    cs:__imp_SRCache_Free
0x1800358fa  nop     dword ptr [rax+rax+00h]
0x1800358ff  jmp     loc_180035810
0x180035904  mov     r8, [rbp+190h+var_38]
0x18003590b  lea     rax, [rsp+290h+var_260]
0x180035910  lea     rdx, [rsp+290h+var_258]
0x180035915  mov     qword ptr [rsp+290h+var_270], rax; int
0x18003591a  mov     rcx, rbx
0x18003591d  mov     byte ptr [rsp+290h+var_260], r15b
0x180035922  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180035927  mov     edi, eax
0x180035929  test    eax, eax
0x18003592b  jns     short loc_180035934
0x18003592d  mov     edx, 3ECh
0x180035932  jmp     short loc_1800358CA
0x180035934  cmp     byte ptr [rsp+290h+var_260], r15b
0x180035939  jz      short loc_18003593F
0x18003593b  mov     [rbx+10h], rsi
0x18003593f  lea     rdx, aApplicationInd; "Application\\Index\\Package"
0x180035946  lea     rcx, [rsp+290h+var_258]; this
0x18003594b  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180035950  mov     ebx, eax
0x180035952  test    eax, eax
0x180035954  jns     short loc_180035995
0x180035956  mov     rcx, [rbp+198h]; this
0x18003595d  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180035964  mov     r9d, eax; char *
0x180035967  mov     edx, 3F2h; void *
0x18003596c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035971  mov     rcx, [rsp+290h+var_250]
0x180035976  mov     [rsp+290h+var_250], r15
0x18003597b  test    rcx, rcx
0x18003597e  jz      loc_180035859
0x180035984  call    cs:__imp_SRCache_Free
0x18003598b  nop     dword ptr [rax+rax+00h]
0x180035990  jmp     loc_180035859
0x180035995  mov     rcx, [rsp+290h+var_250]
0x18003599a  mov     [rsp+290h+var_250], r15
0x18003599f  test    rcx, rcx
0x1800359a2  jz      short loc_1800359B0
0x1800359a4  call    cs:__imp_SRCache_Free
0x1800359ab  nop     dword ptr [rax+rax+00h]
0x1800359b0  mov     rcx, [rsp+290h+var_258]
0x1800359b5  mov     [rsp+290h+var_258], r15
0x1800359ba  test    rcx, rcx
0x1800359bd  jz      short loc_1800359CB
0x1800359bf  call    cs:__imp_SRCacheContext_Close
0x1800359c6  nop     dword ptr [rax+rax+00h]
0x1800359cb  xor     eax, eax
0x1800359cd  mov     rcx, [rbp+190h+var_30]
0x1800359d4  xor     rcx, rsp; StackCookie
0x1800359d7  call    __security_check_cookie
0x1800359dc  mov     rbx, [rsp+290h+arg_18]
0x1800359e4  add     rsp, 270h
0x1800359eb  pop     r15
0x1800359ed  pop     r14
0x1800359ef  pop     rdi
0x1800359f0  pop     rsi
0x1800359f1  pop     rbp
0x1800359f2  retn
```
