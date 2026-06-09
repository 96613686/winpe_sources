# StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)

- ea: `0x180012c68`
- end: `0x180012d27`
- name: `?Get@AppExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppExtension_NoThrow@234@AEAV6234@AEA_N@Z`
- size: `191`
- prototype: `int __high(enum StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags, struct StateRepository::Cache::Entity::AppExtension_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001384c`

## callees

- `0x1800075e4`
- `0x180009f64`
- `0x180012c68`
- `0x180012d30`

## string_xrefs

- `0x180012cad`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180012cc6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180012d04`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtensionIndexIterator_NoThrow::Get(
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v9,
      v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)v11,
      v16);
    return v11;
  }
  if ( !v19 )
    return 0;
  v13 = StateRepository::Cache::Entity::AppExtension_NoThrow::Get(
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
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
    (const char *)(unsigned int)v13,
    v17);
  return v14;
}

```

## disassembly

```asm
0x180012c68  mov     [rsp+arg_8], rdx
0x180012c6d  push    rbx
0x180012c6e  push    rbp
0x180012c6f  push    rsi
0x180012c70  push    rdi
0x180012c71  sub     rsp, 38h
0x180012c75  cmp     qword ptr [rcx], 0
0x180012c79  mov     rsi, r9
0x180012c7c  mov     rbp, r8
0x180012c7f  mov     byte ptr [r9], 0
0x180012c83  mov     rbx, rcx
0x180012c86  jz      loc_180012D1C
0x180012c8c  mov     edx, [rcx+8]; int
0x180012c8f  lea     r8, [rsp+58h+arg_8]; __int64 *
0x180012c94  mov     [rsp+58h+arg_8], 0
0x180012c9d  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180012ca2  mov     edi, eax
0x180012ca4  test    eax, eax
0x180012ca6  jns     short loc_180012CDE
0x180012ca8  mov     rcx, [rsp+58h]; this
0x180012cad  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180012cb4  mov     r9d, eax; char *
0x180012cb7  mov     edx, 1F7h; void *
0x180012cbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cc1  mov     rcx, [rsp+58h]; this
0x180012cc6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180012ccd  mov     r9d, edi; char *
0x180012cd0  mov     edx, 20Fh; void *
0x180012cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cda  mov     eax, edi
0x180012cdc  jmp     short loc_180012D1E
0x180012cde  mov     rdx, [rsp+58h+arg_8]
0x180012ce3  test    rdx, rdx
0x180012ce6  jz      short loc_180012D1C
0x180012ce8  mov     rcx, [rbx+10h]
0x180012cec  mov     r9, rbp
0x180012cef  mov     qword ptr [rsp+58h+var_38], rsi; int
0x180012cf4  call    ?Get@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)
0x180012cf9  mov     ebx, eax
0x180012cfb  test    eax, eax
0x180012cfd  jns     short loc_180012D1C
0x180012cff  mov     rcx, [rsp+58h]; this
0x180012d04  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180012d0b  mov     r9d, eax; char *
0x180012d0e  mov     edx, 214h; void *
0x180012d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d18  mov     eax, ebx
0x180012d1a  jmp     short loc_180012D1E
0x180012d1c  xor     eax, eax
0x180012d1e  add     rsp, 38h
0x180012d22  pop     rdi
0x180012d23  pop     rsi
0x180012d24  pop     rbp
0x180012d25  pop     rbx
0x180012d26  retn
```
