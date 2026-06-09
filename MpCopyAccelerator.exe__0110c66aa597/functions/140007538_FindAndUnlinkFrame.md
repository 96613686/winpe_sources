# _FindAndUnlinkFrame

- ea: `0x140007538`
- end: `0x14000758b`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000a360`
- `0x14000a550`

## callees

- `0x140007538`
- `0x140007fc0`
- `0x140013658`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
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
0x140007538  mov     [rsp+arg_0], rbx
0x14000753d  push    rdi
0x14000753e  sub     rsp, 20h
0x140007542  mov     rdi, rcx
0x140007545  call    __vcrt_getptd
0x14000754a  cmp     rdi, [rax+58h]
0x14000754e  jnz     short loc_140007585
0x140007550  call    __vcrt_getptd
0x140007555  mov     rdx, [rax+58h]
0x140007559  test    rdx, rdx
0x14000755c  jz      short loc_140007585
0x14000755e  mov     rbx, [rdx+8]
0x140007562  cmp     rdi, rdx
0x140007565  jz      short loc_140007571
0x140007567  mov     rdx, rbx
0x14000756a  test    rbx, rbx
0x14000756d  jz      short loc_140007585
0x14000756f  jmp     short loc_14000755E
0x140007571  call    __vcrt_getptd
0x140007576  mov     [rax+58h], rbx
0x14000757a  mov     rbx, [rsp+28h+arg_0]
0x14000757f  add     rsp, 20h
0x140007583  pop     rdi
0x140007584  retn
0x140007585  call    abort
```
