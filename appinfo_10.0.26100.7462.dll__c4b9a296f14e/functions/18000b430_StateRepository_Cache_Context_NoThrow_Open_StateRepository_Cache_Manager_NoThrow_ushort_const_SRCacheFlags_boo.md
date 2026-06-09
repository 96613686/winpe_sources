# StateRepository::Cache::Context_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,ushort const *,SRCacheFlags,bool &)

- ea: `0x18000b430`
- end: `0x18000b4d7`
- name: `?Open@Context_NoThrow@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@23@PEBGW4SRCacheFlags@@AEA_N@Z`
- size: `167`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d8f8`
- `0x18003538c`
- `0x180035568`
- `0x180035744`

## callees

- `0x180007c78`
- `0x18000b430`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b464`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000b464`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b48e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b48e`

## string_xrefs

- `0x18000b4bf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::Open(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  int v6; // edi
  __int64 v7; // rcx
  __int64 v10; // [rsp+28h] [rbp-20h] BYREF
  char v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v10 = 0;
  v11 = 1;
  v6 = SRCacheContext_Open(*a2, a3, 0, &v10);
  if ( v11 )
  {
    v7 = *a1;
    *a1 = v10;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      (int)a1);
    return (unsigned int)v6;
  }
  else
  {
    *a5 = *a1 != 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18000b430  mov     [rsp+arg_0], rbx
0x18000b435  push    rdi
0x18000b436  sub     rsp, 40h
0x18000b43a  mov     rax, rdx
0x18000b43d  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18000b442  mov     r10, r8
0x18000b445  mov     [rsp+48h+var_20], 0
0x18000b44e  mov     rbx, rcx
0x18000b451  mov     [rsp+48h+var_18], 1
0x18000b456  lea     r9, [rsp+48h+var_20]
0x18000b45b  xor     r8d, r8d
0x18000b45e  mov     rcx, [rax]
0x18000b461  mov     rdx, r10
0x18000b464  call    cs:__imp_SRCacheContext_Open
0x18000b46b  nop     dword ptr [rax+rax+00h]
0x18000b470  cmp     [rsp+48h+var_18], 0
0x18000b475  mov     edi, eax
0x18000b477  jz      short loc_18000B49A
0x18000b479  mov     r8, qword ptr [rsp+48h+var_28]
0x18000b47e  mov     rdx, [rsp+48h+var_20]
0x18000b483  mov     rcx, [r8]
0x18000b486  mov     [r8], rdx
0x18000b489  test    rcx, rcx
0x18000b48c  jz      short loc_18000B49A
0x18000b48e  call    cs:__imp_SRCacheContext_Close
0x18000b495  nop     dword ptr [rax+rax+00h]
0x18000b49a  test    edi, edi
0x18000b49c  js      short loc_18000B4BA
0x18000b49e  cmp     qword ptr [rbx], 0
0x18000b4a2  mov     rax, [rsp+48h+arg_20]
0x18000b4a7  setnz   cl
0x18000b4aa  mov     [rax], cl
0x18000b4ac  xor     eax, eax
0x18000b4ae  mov     rbx, [rsp+48h+arg_0]
0x18000b4b3  add     rsp, 40h
0x18000b4b7  pop     rdi
0x18000b4b8  retn
0x18000b4ba  mov     rcx, [rsp+48h]; this
0x18000b4bf  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b4c6  mov     r9d, edi; char *
0x18000b4c9  mov     edx, 18Ch; void *
0x18000b4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4d3  mov     eax, edi
0x18000b4d5  jmp     short loc_18000B4AE
```
