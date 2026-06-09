# Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)

- ea: `0x140012dbc`
- end: `0x140012e31`
- name: `?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ`
- size: `117`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002dfc`

## callees

- `0x140012dbc`
- `0x140014010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x140012df7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x140012df7`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140012ddf`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x140012ddf`

## pseudocode

```c
__int64 *__fastcall Common::GenericMap<unsigned short const *,unsigned short const *>::RemoveAll(PRTL_AVL_TABLE Table)
{
  __int64 *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  struct _RTL_BALANCED_LINKS *Parent; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rax
  PVOID RestartKey; // [rsp+30h] [rbp+8h] BYREF

  while ( 1 )
  {
    RestartKey = 0;
    result = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(Table, &RestartKey);
    if ( !result )
      break;
    v3 = *result;
    v4 = result[1];
    RtlDeleteElementGenericTableAvl(Table, result);
    Parent = Table[1].BalancedRoot.Parent;
    if ( Parent )
      ((void (__fastcall *)(__int64))Parent)(v3);
    LeftChild = Table[1].BalancedRoot.LeftChild;
    if ( LeftChild )
      ((void (__fastcall *)(__int64))LeftChild)(v4);
  }
  return result;
}

```

## disassembly

```asm
0x140012dbc  mov     [rsp+arg_8], rbx
0x140012dc1  mov     [rsp+arg_10], rsi
0x140012dc6  push    rdi
0x140012dc7  sub     rsp, 20h
0x140012dcb  mov     rbx, rcx
0x140012dce  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x140012dd3  mov     [rsp+28h+RestartKey], 0
0x140012ddc  mov     rcx, rbx; Table
0x140012ddf  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x140012de5  test    rax, rax
0x140012de8  jz      short loc_140012E21
0x140012dea  mov     rdi, [rax]
0x140012ded  mov     rdx, rax; Buffer
0x140012df0  mov     rsi, [rax+8]
0x140012df4  mov     rcx, rbx; Table
0x140012df7  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140012dfd  mov     rax, [rbx+68h]
0x140012e01  test    rax, rax
0x140012e04  jz      short loc_140012E0E
0x140012e06  mov     rcx, rdi
0x140012e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e0e  mov     rax, [rbx+70h]
0x140012e12  test    rax, rax
0x140012e15  jz      short loc_140012DCE
0x140012e17  mov     rcx, rsi
0x140012e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e1f  jmp     short loc_140012DCE
0x140012e21  mov     rbx, [rsp+28h+arg_8]
0x140012e26  mov     rsi, [rsp+28h+arg_10]
0x140012e2b  add     rsp, 20h
0x140012e2f  pop     rdi
0x140012e30  retn
```
