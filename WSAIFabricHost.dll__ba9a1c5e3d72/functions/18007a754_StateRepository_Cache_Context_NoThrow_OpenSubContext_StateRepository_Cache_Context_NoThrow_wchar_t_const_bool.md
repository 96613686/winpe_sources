# StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,wchar_t const *,bool &)

- ea: `0x18007a754`
- end: `0x18007a7f4`
- name: `?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEB_WAEA_N@Z`
- size: `160`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, struct StateRepository::Cache::Context_NoThrow *, const wchar_t *, bool *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800797c8`
- `0x180079a98`
- `0x180079f04`
- `0x18007a4e4`

## callees

- `0x18000b064`
- `0x18007a754`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007a78e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18007a78e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a7b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a7b2`

## string_xrefs

- `0x18007a7c1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::OpenSubContext(
        StateRepository::Cache::Context_NoThrow *this,
        struct StateRepository::Cache::Context_NoThrow *a2,
        const wchar_t *a3,
        bool *a4)
{
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v10; // [rsp+28h] [rbp-20h] BYREF
  char v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v10 = 0;
  v11 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)a2, a3, 0, &v10);
  if ( v11 )
  {
    v7 = *(_QWORD *)this;
    *(_QWORD *)this = v10;
    if ( v7 )
      SRCacheContext_Close();
  }
  if ( v6 >= 0 )
  {
    v6 = 0;
    *a4 = *(_QWORD *)this != 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      (int)this);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007a754  mov     r11, rsp
0x18007a757  mov     [r11+8], rbx
0x18007a75b  mov     [r11+10h], rsi
0x18007a75f  push    rdi
0x18007a760  sub     rsp, 40h
0x18007a764  mov     r10, rdx
0x18007a767  mov     [r11-28h], rcx
0x18007a76b  mov     rax, r8
0x18007a76e  mov     qword ptr [r11-20h], 0
0x18007a776  mov     rsi, r9
0x18007a779  mov     [rsp+48h+var_18], 1
0x18007a77e  mov     rdi, rcx
0x18007a781  lea     r9, [r11-20h]
0x18007a785  mov     rcx, [r10]
0x18007a788  xor     r8d, r8d
0x18007a78b  mov     rdx, rax
0x18007a78e  call    cs:__imp_SRCacheContext_OpenSubContext
0x18007a794  cmp     [rsp+48h+var_18], 0
0x18007a799  mov     ebx, eax
0x18007a79b  jz      short loc_18007A7B8
0x18007a79d  mov     rdx, [rsp+48h+var_28]
0x18007a7a2  mov     rax, [rsp+48h+var_20]
0x18007a7a7  mov     rcx, [rdx]
0x18007a7aa  mov     [rdx], rax
0x18007a7ad  test    rcx, rcx
0x18007a7b0  jz      short loc_18007A7B8
0x18007a7b2  call    cs:__imp_SRCacheContext_Close
0x18007a7b8  test    ebx, ebx
0x18007a7ba  jns     short loc_18007A7D7
0x18007a7bc  mov     rcx, [rsp+48h]; this
0x18007a7c1  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a7c8  mov     r9d, ebx; char *
0x18007a7cb  mov     edx, 1B0h; void *
0x18007a7d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a7d5  jmp     short loc_18007A7E2
0x18007a7d7  cmp     qword ptr [rdi], 0
0x18007a7db  setnz   al
0x18007a7de  xor     ebx, ebx
0x18007a7e0  mov     [rsi], al
0x18007a7e2  mov     rsi, [rsp+48h+arg_8]
0x18007a7e7  mov     eax, ebx
0x18007a7e9  mov     rbx, [rsp+48h+arg_0]
0x18007a7ee  add     rsp, 40h
0x18007a7f2  pop     rdi
0x18007a7f3  retn
```
