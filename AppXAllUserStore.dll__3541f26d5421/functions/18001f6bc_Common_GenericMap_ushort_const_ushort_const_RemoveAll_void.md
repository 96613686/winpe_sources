# Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)

- ea: `0x18001f6bc`
- end: `0x18001f731`
- name: `?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ`
- size: `117`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ec88`
- `0x180021f34`
- `0x18004bb6c`
- `0x18004be74`
- `0x18004ce10`

## callees

- `0x18001f6bc`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001f6f7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18001f6f7`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18001f6df`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18001f6df`

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
0x18001f6bc  mov     [rsp+arg_8], rbx
0x18001f6c1  mov     [rsp+arg_10], rsi
0x18001f6c6  push    rdi
0x18001f6c7  sub     rsp, 20h
0x18001f6cb  mov     rbx, rcx
0x18001f6ce  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x18001f6d3  mov     [rsp+28h+RestartKey], 0
0x18001f6dc  mov     rcx, rbx; Table
0x18001f6df  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18001f6e5  test    rax, rax
0x18001f6e8  jz      short loc_18001F721
0x18001f6ea  mov     rdi, [rax]
0x18001f6ed  mov     rdx, rax; Buffer
0x18001f6f0  mov     rsi, [rax+8]
0x18001f6f4  mov     rcx, rbx; Table
0x18001f6f7  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001f6fd  mov     rax, [rbx+68h]
0x18001f701  test    rax, rax
0x18001f704  jz      short loc_18001F70E
0x18001f706  mov     rcx, rdi
0x18001f709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f70e  mov     rax, [rbx+70h]
0x18001f712  test    rax, rax
0x18001f715  jz      short loc_18001F6CE
0x18001f717  mov     rcx, rsi
0x18001f71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f71f  jmp     short loc_18001F6CE
0x18001f721  mov     rbx, [rsp+28h+arg_8]
0x18001f726  mov     rsi, [rsp+28h+arg_10]
0x18001f72b  add     rsp, 20h
0x18001f72f  pop     rdi
0x18001f730  retn
```
