# StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,bool &)

- ea: `0x18007a43c`
- end: `0x18007a4dc`
- name: `?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEB_WAEA_N@Z`
- size: `160`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const wchar_t *, bool *)`
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
- `0x18007a43c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007a476`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18007a476`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a49a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18007a49a`

## string_xrefs

- `0x18007a4a9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::Open(
        StateRepository::Cache::Context_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
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
  v6 = SRCacheContext_Open(*(_QWORD *)a2, a3, 0, &v10);
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
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      (int)this);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007a43c  mov     r11, rsp
0x18007a43f  mov     [r11+8], rbx
0x18007a443  mov     [r11+10h], rsi
0x18007a447  push    rdi
0x18007a448  sub     rsp, 40h
0x18007a44c  mov     r10, rdx
0x18007a44f  mov     [r11-28h], rcx
0x18007a453  mov     rax, r8
0x18007a456  mov     qword ptr [r11-20h], 0
0x18007a45e  mov     rsi, r9
0x18007a461  mov     [rsp+48h+var_18], 1
0x18007a466  mov     rdi, rcx
0x18007a469  lea     r9, [r11-20h]
0x18007a46d  mov     rcx, [r10]
0x18007a470  xor     r8d, r8d
0x18007a473  mov     rdx, rax
0x18007a476  call    cs:__imp_SRCacheContext_Open
0x18007a47c  cmp     [rsp+48h+var_18], 0
0x18007a481  mov     ebx, eax
0x18007a483  jz      short loc_18007A4A0
0x18007a485  mov     rdx, [rsp+48h+var_28]
0x18007a48a  mov     rax, [rsp+48h+var_20]
0x18007a48f  mov     rcx, [rdx]
0x18007a492  mov     [rdx], rax
0x18007a495  test    rcx, rcx
0x18007a498  jz      short loc_18007A4A0
0x18007a49a  call    cs:__imp_SRCacheContext_Close
0x18007a4a0  test    ebx, ebx
0x18007a4a2  jns     short loc_18007A4BF
0x18007a4a4  mov     rcx, [rsp+48h]; this
0x18007a4a9  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18007a4b0  mov     r9d, ebx; char *
0x18007a4b3  mov     edx, 18Ch; void *
0x18007a4b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a4bd  jmp     short loc_18007A4CA
0x18007a4bf  cmp     qword ptr [rdi], 0
0x18007a4c3  setnz   al
0x18007a4c6  xor     ebx, ebx
0x18007a4c8  mov     [rsi], al
0x18007a4ca  mov     rsi, [rsp+48h+arg_8]
0x18007a4cf  mov     eax, ebx
0x18007a4d1  mov     rbx, [rsp+48h+arg_0]
0x18007a4d6  add     rsp, 40h
0x18007a4da  pop     rdi
0x18007a4db  retn
```
