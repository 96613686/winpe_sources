# StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)

- ea: `0x18000b840`
- end: `0x18000b8e3`
- name: `?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z`
- size: `163`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a70`
- `0x18001d56c`
- `0x18001d7f0`
- `0x18001ddf0`
- `0x18001e0b0`

## callees

- `0x18000720c`
- `0x18000b840`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b874`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000b874`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b898`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000b898`

## string_xrefs

- `0x18000b8c2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::OpenSubContext(
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
  v6 = SRCacheContext_OpenSubContext(*a2, a3, 0, &v10);
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
      (void *)0x1B0,
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
0x18000b840  mov     [rsp+arg_0], rbx
0x18000b845  push    rdi
0x18000b846  sub     rsp, 40h
0x18000b84a  mov     r10, rdx
0x18000b84d  mov     qword ptr [rsp+48h+var_28], rcx; int
0x18000b852  mov     rax, r8
0x18000b855  mov     [rsp+48h+var_20], 0
0x18000b85e  mov     rbx, rcx
0x18000b861  mov     [rsp+48h+var_18], 1
0x18000b866  lea     r9, [rsp+48h+var_20]
0x18000b86b  xor     r8d, r8d
0x18000b86e  mov     rcx, [r10]
0x18000b871  mov     rdx, rax
0x18000b874  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000b87a  cmp     [rsp+48h+var_18], 0
0x18000b87f  mov     edi, eax
0x18000b881  jz      short loc_18000B89E
0x18000b883  mov     r8, qword ptr [rsp+48h+var_28]
0x18000b888  mov     rdx, [rsp+48h+var_20]
0x18000b88d  mov     rcx, [r8]
0x18000b890  mov     [r8], rdx
0x18000b893  test    rcx, rcx
0x18000b896  jz      short loc_18000B89E
0x18000b898  call    cs:__imp_SRCacheContext_Close
0x18000b89e  test    edi, edi
0x18000b8a0  js      short loc_18000B8BD
0x18000b8a2  cmp     qword ptr [rbx], 0
0x18000b8a6  mov     rax, [rsp+48h+arg_20]
0x18000b8ab  setnz   cl
0x18000b8ae  mov     [rax], cl
0x18000b8b0  xor     eax, eax
0x18000b8b2  mov     rbx, [rsp+48h+arg_0]
0x18000b8b7  add     rsp, 40h
0x18000b8bb  pop     rdi
0x18000b8bc  retn
0x18000b8bd  mov     rcx, [rsp+48h]; this
0x18000b8c2  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000b8c9  mov     r9d, edi; char *
0x18000b8cc  mov     edx, 1B0h; void *
0x18000b8d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8d6  mov     rbx, [rsp+48h+arg_0]
0x18000b8db  mov     eax, edi
0x18000b8dd  add     rsp, 40h
0x18000b8e1  pop     rdi
0x18000b8e2  retn
```
