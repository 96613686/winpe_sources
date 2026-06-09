# StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)

- ea: `0x1800093b0`
- end: `0x180009461`
- name: `?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z`
- size: `177`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800052b0`
- `0x18002ee48`
- `0x18003501c`
- `0x1800351f8`
- `0x1800353d4`

## callees

- `0x180007c78`
- `0x1800093b0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000940e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000940e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800093e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800093e4`

## string_xrefs

- `0x18000943f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x1800093b0  mov     [rsp+arg_0], rbx
0x1800093b5  push    rdi
0x1800093b6  sub     rsp, 40h
0x1800093ba  mov     rax, rdx
0x1800093bd  mov     qword ptr [rsp+48h+var_28], rcx; int
0x1800093c2  mov     r10, r8
0x1800093c5  mov     [rsp+48h+var_20], 0
0x1800093ce  mov     rbx, rcx
0x1800093d1  mov     [rsp+48h+var_18], 1
0x1800093d6  lea     r9, [rsp+48h+var_20]
0x1800093db  xor     r8d, r8d
0x1800093de  mov     rcx, [rax]
0x1800093e1  mov     rdx, r10
0x1800093e4  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800093eb  nop     dword ptr [rax+rax+00h]
0x1800093f0  cmp     [rsp+48h+var_18], 0
0x1800093f5  mov     edi, eax
0x1800093f7  jz      short loc_18000941A
0x1800093f9  mov     r8, qword ptr [rsp+48h+var_28]
0x1800093fe  mov     rdx, [rsp+48h+var_20]
0x180009403  mov     rcx, [r8]
0x180009406  mov     [r8], rdx
0x180009409  test    rcx, rcx
0x18000940c  jz      short loc_18000941A
0x18000940e  call    cs:__imp_SRCacheContext_Close
0x180009415  nop     dword ptr [rax+rax+00h]
0x18000941a  test    edi, edi
0x18000941c  js      short loc_18000943A
0x18000941e  cmp     qword ptr [rbx], 0
0x180009422  mov     rax, [rsp+48h+arg_20]
0x180009427  setnz   cl
0x18000942a  mov     [rax], cl
0x18000942c  xor     eax, eax
0x18000942e  mov     rbx, [rsp+48h+arg_0]
0x180009433  add     rsp, 40h
0x180009437  pop     rdi
0x180009438  retn
0x18000943a  mov     rcx, [rsp+48h]; this
0x18000943f  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009446  mov     r9d, edi; char *
0x180009449  mov     edx, 1B0h; void *
0x18000944e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009453  mov     rbx, [rsp+48h+arg_0]
0x180009458  mov     eax, edi
0x18000945a  add     rsp, 40h
0x18000945e  pop     rdi
0x18000945f  retn
```
