# BampCreateProcessCallback

- ea: `0x140012420`
- end: `0x140012449`
- name: `BampCreateProcessCallback`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140012420`
- `0x140012450`
- `0x140012530`

## pseudocode

```c
__int64 __fastcall BampCreateProcessCallback(_DWORD *a1, __int64 a2, __int64 a3)
{
  if ( a3 && *(_QWORD *)(a3 + 48) )
    return BampThrottlingRegisterProcessEx(a1, *(_QWORD *)(a3 + 16), a3, 0);
  else
    return BampThrottlingOnProcessTerminated();
}

```

## disassembly

```asm
0x140012420  sub     rsp, 28h
0x140012424  test    r8, r8
0x140012427  jnz     short loc_140012434
0x140012429  call    BampThrottlingOnProcessTerminated
0x14001242e  add     rsp, 28h
0x140012432  retn
0x140012434  cmp     qword ptr [r8+30h], 0
0x140012439  jz      short loc_140012429
0x14001243b  mov     rdx, [r8+10h]
0x14001243f  xor     r9d, r9d
0x140012442  call    BampThrottlingRegisterProcessEx
0x140012447  jmp     short loc_14001242E
```
