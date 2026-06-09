# IIsSchema::PropNameWToId(ushort const *,ulong *)

- ea: `0x18001b5ac`
- end: `0x18001b5e4`
- name: `?PropNameWToId@IIsSchema@@QEAAJPEBGPEAK@Z`
- size: `56`
- prototype: `__int64 __fastcall(IIsSchema *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180008340`
- `0x1800085a0`
- `0x18000c11c`
- `0x18000c800`
- `0x18000c870`
- `0x18000c8e0`
- `0x18000c950`
- `0x18000ca00`
- `0x18000caf0`
- `0x18000cb60`
- `0x18000cbd0`
- `0x18000cc90`
- `0x18000cce0`
- `0x180015b1c`
- `0x180019f14`

## callees

- `0x18001a0c8`
- `0x18001b5ac`

## pseudocode

```c
__int64 __fastcall IIsSchema::PropNameWToId(IIsSchema *this, const unsigned __int16 *a2, unsigned int *a3)
{
  _QWORD *v4; // rax
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  v4 = StrMap::Find((IIsSchema *)((char *)this + 32), a2, &v6);
  if ( !v4 )
    return 2147504134LL;
  *a3 = *((_DWORD *)v4 + 2);
  return 0;
}

```

## disassembly

```asm
0x18001b5ac  push    rbx
0x18001b5ae  sub     rsp, 20h
0x18001b5b2  mov     rbx, r8
0x18001b5b5  mov     [rsp+28h+arg_0], 0
0x18001b5bd  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18001b5c2  add     rcx, 20h ; ' '; this
0x18001b5c6  call    ?Find@StrMap@@QEBAPEAXPEBGPEAK@Z; StrMap::Find(ushort const *,ulong *)
0x18001b5cb  test    rax, rax
0x18001b5ce  jnz     short loc_18001B5D7
0x18001b5d0  mov     eax, 80005006h
0x18001b5d5  jmp     short loc_18001B5DE
0x18001b5d7  mov     eax, [rax+8]
0x18001b5da  mov     [rbx], eax
0x18001b5dc  xor     eax, eax
0x18001b5de  add     rsp, 20h
0x18001b5e2  pop     rbx
0x18001b5e3  retn
```
