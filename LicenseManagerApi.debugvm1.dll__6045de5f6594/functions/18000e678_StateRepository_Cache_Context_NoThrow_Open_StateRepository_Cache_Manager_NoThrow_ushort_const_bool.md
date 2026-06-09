# StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,bool &)

- ea: `0x18000e678`
- end: `0x18000e713`
- name: `?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGAEA_N@Z`
- size: `155`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800073e8`
- `0x18000e71c`

## callees

- `0x1800052a8`
- `0x18000e678`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e6d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e6d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e6b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000e6b2`

## string_xrefs

- `0x18000e6e3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::Open(
        StateRepository::Cache::Context_NoThrow *this,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  int v6; // ebx
  int v7; // r9d
  __int64 v8; // rcx
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF
  char v12; // [rsp+30h] [rbp-18h]

  v11 = 0;
  v12 = 1;
  v6 = SRCacheContext_Open(*(_QWORD *)a2, a3, 0, &v11);
  if ( v12 )
  {
    v8 = *(_QWORD *)this;
    *(_QWORD *)this = v11;
    if ( v8 )
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
      (wil::details::in1diag3 *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (wil::details *)(unsigned int)v6,
      v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e678  mov     r11, rsp
0x18000e67b  mov     [r11+8], rbx
0x18000e67f  mov     [r11+10h], rsi
0x18000e683  push    rdi
0x18000e684  sub     rsp, 40h
0x18000e688  mov     r10, rdx
0x18000e68b  mov     [r11-28h], rcx
0x18000e68f  mov     rax, r8
0x18000e692  mov     qword ptr [r11-20h], 0
0x18000e69a  mov     rsi, r9
0x18000e69d  mov     [rsp+48h+var_18], 1
0x18000e6a2  mov     rdi, rcx
0x18000e6a5  lea     r9, [r11-20h]
0x18000e6a9  mov     rcx, [r10]
0x18000e6ac  xor     r8d, r8d
0x18000e6af  mov     rdx, rax
0x18000e6b2  call    cs:__imp_SRCacheContext_Open
0x18000e6b8  cmp     [rsp+48h+var_18], 0
0x18000e6bd  mov     ebx, eax
0x18000e6bf  jz      short loc_18000E6DC
0x18000e6c1  mov     rdx, [rsp+48h+var_28]
0x18000e6c6  mov     rax, [rsp+48h+var_20]
0x18000e6cb  mov     rcx, [rdx]
0x18000e6ce  mov     [rdx], rax
0x18000e6d1  test    rcx, rcx
0x18000e6d4  jz      short loc_18000E6DC
0x18000e6d6  call    cs:__imp_SRCacheContext_Close
0x18000e6dc  test    ebx, ebx
0x18000e6de  jns     short loc_18000E6F6
0x18000e6e0  mov     r8d, ebx; wil::details *
0x18000e6e3  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e6ea  mov     ecx, 18Ch; this
0x18000e6ef  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000e6f4  jmp     short loc_18000E701
0x18000e6f6  cmp     qword ptr [rdi], 0
0x18000e6fa  setnz   al
0x18000e6fd  xor     ebx, ebx
0x18000e6ff  mov     [rsi], al
0x18000e701  mov     rsi, [rsp+48h+arg_8]
0x18000e706  mov     eax, ebx
0x18000e708  mov     rbx, [rsp+48h+arg_0]
0x18000e70d  add     rsp, 40h
0x18000e711  pop     rdi
0x18000e712  retn
```
