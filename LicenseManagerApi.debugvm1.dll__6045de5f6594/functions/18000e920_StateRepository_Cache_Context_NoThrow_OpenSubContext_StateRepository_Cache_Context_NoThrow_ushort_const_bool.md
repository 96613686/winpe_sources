# StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,bool &)

- ea: `0x18000e920`
- end: `0x18000e9bb`
- name: `?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGAEA_N@Z`
- size: `155`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, struct StateRepository::Cache::Context_NoThrow *, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800073e8`
- `0x18000e71c`

## callees

- `0x1800052a8`
- `0x18000e920`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000e95a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000e95a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e97e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000e97e`

## string_xrefs

- `0x18000e98b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::OpenSubContext(
        StateRepository::Cache::Context_NoThrow *this,
        struct StateRepository::Cache::Context_NoThrow *a2,
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
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)a2, a3, 0, &v11);
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
      (wil::details::in1diag3 *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (wil::details *)(unsigned int)v6,
      v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e920  mov     r11, rsp
0x18000e923  mov     [r11+8], rbx
0x18000e927  mov     [r11+10h], rsi
0x18000e92b  push    rdi
0x18000e92c  sub     rsp, 40h
0x18000e930  mov     r10, rdx
0x18000e933  mov     [r11-28h], rcx
0x18000e937  mov     rax, r8
0x18000e93a  mov     qword ptr [r11-20h], 0
0x18000e942  mov     rsi, r9
0x18000e945  mov     [rsp+48h+var_18], 1
0x18000e94a  mov     rdi, rcx
0x18000e94d  lea     r9, [r11-20h]
0x18000e951  mov     rcx, [r10]
0x18000e954  xor     r8d, r8d
0x18000e957  mov     rdx, rax
0x18000e95a  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000e960  cmp     [rsp+48h+var_18], 0
0x18000e965  mov     ebx, eax
0x18000e967  jz      short loc_18000E984
0x18000e969  mov     rdx, [rsp+48h+var_28]
0x18000e96e  mov     rax, [rsp+48h+var_20]
0x18000e973  mov     rcx, [rdx]
0x18000e976  mov     [rdx], rax
0x18000e979  test    rcx, rcx
0x18000e97c  jz      short loc_18000E984
0x18000e97e  call    cs:__imp_SRCacheContext_Close
0x18000e984  test    ebx, ebx
0x18000e986  jns     short loc_18000E99E
0x18000e988  mov     r8d, ebx; wil::details *
0x18000e98b  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e992  mov     ecx, 1B0h; this
0x18000e997  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000e99c  jmp     short loc_18000E9A9
0x18000e99e  cmp     qword ptr [rdi], 0
0x18000e9a2  setnz   al
0x18000e9a5  xor     ebx, ebx
0x18000e9a7  mov     [rsi], al
0x18000e9a9  mov     rsi, [rsp+48h+arg_8]
0x18000e9ae  mov     eax, ebx
0x18000e9b0  mov     rbx, [rsp+48h+arg_0]
0x18000e9b5  add     rsp, 40h
0x18000e9b9  pop     rdi
0x18000e9ba  retn
```
