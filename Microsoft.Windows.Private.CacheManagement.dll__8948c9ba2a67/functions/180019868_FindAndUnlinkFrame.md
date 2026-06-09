# _FindAndUnlinkFrame

- ea: `0x180019868`
- end: `0x1800198bb`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b510`

## callees

- `0x1800162ce`
- `0x180019868`
- `0x18001a008`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort_0();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x180019868  mov     [rsp+arg_0], rbx
0x18001986d  push    rdi
0x18001986e  sub     rsp, 20h
0x180019872  mov     rdi, rcx
0x180019875  call    __vcrt_getptd
0x18001987a  cmp     rdi, [rax+58h]
0x18001987e  jnz     short loc_1800198B5
0x180019880  call    __vcrt_getptd
0x180019885  mov     rdx, [rax+58h]
0x180019889  test    rdx, rdx
0x18001988c  jz      short loc_1800198B5
0x18001988e  mov     rbx, [rdx+8]
0x180019892  cmp     rdi, rdx
0x180019895  jz      short loc_1800198A1
0x180019897  mov     rdx, rbx
0x18001989a  test    rbx, rbx
0x18001989d  jz      short loc_1800198B5
0x18001989f  jmp     short loc_18001988E
0x1800198a1  call    __vcrt_getptd
0x1800198a6  mov     [rax+58h], rbx
0x1800198aa  mov     rbx, [rsp+28h+arg_0]
0x1800198af  add     rsp, 20h
0x1800198b3  pop     rdi
0x1800198b4  retn
0x1800198b5  call    abort_0
```
