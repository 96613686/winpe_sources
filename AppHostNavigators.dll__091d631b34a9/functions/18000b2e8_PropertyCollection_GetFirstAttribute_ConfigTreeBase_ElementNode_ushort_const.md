# PropertyCollection::GetFirstAttribute(ConfigTreeBase *,ElementNode *,ushort const *)

- ea: `0x18000b2e8`
- end: `0x18000b353`
- name: `?GetFirstAttribute@PropertyCollection@@QEAAPEAVPropertyNode@@PEAVConfigTreeBase@@PEAVElementNode@@PEBG@Z`
- size: `107`
- prototype: `struct PropertyNode *(PropertyCollection *__hidden this, struct ConfigTreeBase *, struct ElementNode *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b2d0`
- `0x18000c09c`

## callees

- `0x18000b2e8`
- `0x18000bc0c`
- `0x1800112e4`
- `0x180014010`

## pseudocode

```c
const unsigned __int16 **__fastcall PropertyCollection::GetFirstAttribute(
        PropertyCollection *this,
        ConfigSystemContext **a2,
        struct IUnknown *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 **v8; // r9

  if ( !*(_QWORD *)this )
    PropertyCollection::InitializePropertyCollection(this, a2, a3);
  if ( !*(_QWORD *)this )
    return 0;
  if ( NavigationNodeBase::IsWildCardName(a4) || v8[2] == a4 )
    return v8;
  return (const unsigned __int16 **)(*((__int64 (__fastcall **)(const unsigned __int16 **, ConfigSystemContext **, const unsigned __int16 *))*v8
                                     + 5))(
                                      v8,
                                      a2,
                                      a4);
}

```

## disassembly

```asm
0x18000b2e8  mov     [rsp+arg_0], rbx
0x18000b2ed  mov     [rsp+arg_8], rsi
0x18000b2f2  push    rdi
0x18000b2f3  sub     rsp, 20h
0x18000b2f7  cmp     qword ptr [rcx], 0
0x18000b2fb  mov     rdi, r9
0x18000b2fe  mov     rsi, rdx
0x18000b301  mov     rbx, rcx
0x18000b304  jnz     short loc_18000B30B
0x18000b306  call    ?InitializePropertyCollection@PropertyCollection@@AEAAXPEAVConfigTreeBase@@PEAVElementNode@@@Z; PropertyCollection::InitializePropertyCollection(ConfigTreeBase *,ElementNode *)
0x18000b30b  mov     r9, [rbx]
0x18000b30e  test    r9, r9
0x18000b311  jnz     short loc_18000B317
0x18000b313  xor     eax, eax
0x18000b315  jmp     short loc_18000B343
0x18000b317  mov     rcx, rdi; unsigned __int16 *
0x18000b31a  call    ?IsWildCardName@NavigationNodeBase@@SA_NPEBG@Z; NavigationNodeBase::IsWildCardName(ushort const *)
0x18000b31f  test    al, al
0x18000b321  jnz     short loc_18000B340
0x18000b323  cmp     [r9+10h], rdi
0x18000b327  jz      short loc_18000B340
0x18000b329  mov     rax, [r9]
0x18000b32c  mov     r8, rdi
0x18000b32f  mov     rdx, rsi
0x18000b332  mov     rcx, r9
0x18000b335  mov     rax, [rax+28h]
0x18000b339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b33e  jmp     short loc_18000B343
0x18000b340  mov     rax, r9
0x18000b343  mov     rbx, [rsp+28h+arg_0]
0x18000b348  mov     rsi, [rsp+28h+arg_8]
0x18000b34d  add     rsp, 20h
0x18000b351  pop     rdi
0x18000b352  retn
```
