# std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(RegistryKey *)

- ea: `0x180020040`
- end: `0x180020066`
- name: `??$?0VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@PEAVRegistryKey@@@Z`
- size: `38`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010590`
- `0x180010754`
- `0x1800207f0`

## callees

- `0x1800200c8`

## pseudocode

```c
_QWORD *__fastcall std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  std::tr1::shared_ptr<IRegistryKey>::_Resetp<RegistryKey>();
  return a1;
}

```

## disassembly

```asm
0x180020040  push    rbx
0x180020042  sub     rsp, 20h
0x180020046  mov     rbx, rcx
0x180020049  mov     qword ptr [rcx], 0
0x180020050  mov     qword ptr [rcx+8], 0
0x180020058  call    ??$_Resetp@VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@AEAAXPEAVRegistryKey@@@Z; std::tr1::shared_ptr<IRegistryKey>::_Resetp<RegistryKey>(RegistryKey *)
0x18002005d  mov     rax, rbx
0x180020060  add     rsp, 20h
0x180020064  pop     rbx
0x180020065  retn
```
