# StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)

- ea: `0x1800173d4`
- end: `0x180017493`
- name: `?Get@PkgExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z`
- size: `191`
- prototype: `int __high(enum StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags, struct StateRepository::Cache::Entity::PkgExtension_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001757c`

## callees

- `0x1800075e4`
- `0x180009f64`
- `0x1800173d4`
- `0x18001749c`

## string_xrefs

- `0x180017419`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017432`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017470`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtensionIndexIterator_NoThrow::Get(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  bool v4; // zf
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // edi
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v19; // [rsp+68h] [rbp+10h] BYREF

  v19 = a2;
  v4 = *(_QWORD *)a1 == 0;
  *a4 = 0;
  if ( v4 )
    return 0;
  v8 = *(unsigned int *)(a1 + 8);
  v19 = 0;
  v9 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)a1, v8, &v19);
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F7,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v9,
      v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)v11,
      v16);
    return v11;
  }
  if ( !v19 )
    return 0;
  v13 = StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(
          *(struct StateRepository::Cache::Manager_NoThrow **)(a1 + 16),
          v19,
          v10,
          a3,
          a4);
  v14 = v13;
  if ( v13 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x214,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
    (const char *)(unsigned int)v13,
    v17);
  return v14;
}

```

## disassembly

```asm
0x1800173d4  mov     [rsp+arg_8], rdx
0x1800173d9  push    rbx
0x1800173da  push    rbp
0x1800173db  push    rsi
0x1800173dc  push    rdi
0x1800173dd  sub     rsp, 38h
0x1800173e1  cmp     qword ptr [rcx], 0
0x1800173e5  mov     rsi, r9
0x1800173e8  mov     rbp, r8
0x1800173eb  mov     byte ptr [r9], 0
0x1800173ef  mov     rbx, rcx
0x1800173f2  jz      loc_180017488
0x1800173f8  mov     edx, [rcx+8]; int
0x1800173fb  lea     r8, [rsp+58h+arg_8]; __int64 *
0x180017400  mov     [rsp+58h+arg_8], 0
0x180017409  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18001740e  mov     edi, eax
0x180017410  test    eax, eax
0x180017412  jns     short loc_18001744A
0x180017414  mov     rcx, [rsp+58h]; this
0x180017419  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017420  mov     r9d, eax; char *
0x180017423  mov     edx, 1F7h; void *
0x180017428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001742d  mov     rcx, [rsp+58h]; this
0x180017432  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017439  mov     r9d, edi; char *
0x18001743c  mov     edx, 20Fh; void *
0x180017441  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017446  mov     eax, edi
0x180017448  jmp     short loc_18001748A
0x18001744a  mov     rdx, [rsp+58h+arg_8]
0x18001744f  test    rdx, rdx
0x180017452  jz      short loc_180017488
0x180017454  mov     rcx, [rbx+10h]
0x180017458  mov     r9, rbp
0x18001745b  mov     qword ptr [rsp+58h+var_38], rsi; int
0x180017460  call    ?Get@PkgExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x180017465  mov     ebx, eax
0x180017467  test    eax, eax
0x180017469  jns     short loc_180017488
0x18001746b  mov     rcx, [rsp+58h]; this
0x180017470  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017477  mov     r9d, eax; char *
0x18001747a  mov     edx, 214h; void *
0x18001747f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017484  mov     eax, ebx
0x180017486  jmp     short loc_18001748A
0x180017488  xor     eax, eax
0x18001748a  add     rsp, 38h
0x18001748e  pop     rdi
0x18001748f  pop     rsi
0x180017490  pop     rbp
0x180017491  pop     rbx
0x180017492  retn
```
