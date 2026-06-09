# Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)

- ea: `0x18002bf34`
- end: `0x18002bfa9`
- name: `?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ`
- size: `117`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b4ec`

## callees

- `0x18002bf34`
- `0x18002f010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002bf6f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002bf6f`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002bf57`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002bf57`

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
0x18002bf34  mov     [rsp+arg_8], rbx
0x18002bf39  mov     [rsp+arg_10], rsi
0x18002bf3e  push    rdi
0x18002bf3f  sub     rsp, 20h
0x18002bf43  mov     rbx, rcx
0x18002bf46  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x18002bf4b  mov     [rsp+28h+RestartKey], 0
0x18002bf54  mov     rcx, rbx; Table
0x18002bf57  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18002bf5d  test    rax, rax
0x18002bf60  jz      short loc_18002BF99
0x18002bf62  mov     rdi, [rax]
0x18002bf65  mov     rdx, rax; Buffer
0x18002bf68  mov     rsi, [rax+8]
0x18002bf6c  mov     rcx, rbx; Table
0x18002bf6f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002bf75  mov     rax, [rbx+68h]
0x18002bf79  test    rax, rax
0x18002bf7c  jz      short loc_18002BF86
0x18002bf7e  mov     rcx, rdi
0x18002bf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf86  mov     rax, [rbx+70h]
0x18002bf8a  test    rax, rax
0x18002bf8d  jz      short loc_18002BF46
0x18002bf8f  mov     rcx, rsi
0x18002bf92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf97  jmp     short loc_18002BF46
0x18002bf99  mov     rbx, [rsp+28h+arg_8]
0x18002bf9e  mov     rsi, [rsp+28h+arg_10]
0x18002bfa3  add     rsp, 20h
0x18002bfa7  pop     rdi
0x18002bfa8  retn
```
