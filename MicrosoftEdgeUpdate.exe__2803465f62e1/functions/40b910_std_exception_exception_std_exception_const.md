# std::exception::exception(std::exception const &)

- ea: `0x40b910`
- end: `0x40b93c`
- name: `??0exception@std@@QAE@ABV01@@Z`
- size: `44`
- prototype: `std::exception *__thiscall(std::exception *this, const struct std::exception *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x40b890`
- `0x40b8d0`
- `0x40c2a0`
- `0x40c2e0`
- `0x40c300`

## callees

- `0x40d3c1`

## pseudocode

```c
std::exception *__thiscall std::exception::exception(std::exception *this, const struct std::exception *a2)
{
  *(_DWORD *)this = &std::exception::`vftable';
  *((_DWORD *)this + 1) = 0;
  *((_DWORD *)this + 2) = 0;
  __std_exception_copy((char *)a2 + 4, (char *)this + 4);
  return this;
}

```

## disassembly

```asm
0x40b910  push    ebp
0x40b911  mov     ebp, esp
0x40b913  push    esi
0x40b914  mov     esi, ecx
0x40b916  lea     eax, [esi+4]
0x40b919  mov     dword ptr [esi], offset ??_7exception@std@@6B@
0x40b91f  and     dword ptr [eax], 0
0x40b922  and     dword ptr [eax+4], 0
0x40b926  push    eax
0x40b927  mov     eax, [ebp+arg_0]
0x40b92a  add     eax, 4
0x40b92d  push    eax
0x40b92e  call    ___std_exception_copy
0x40b933  pop     ecx
0x40b934  pop     ecx
0x40b935  mov     eax, esi
0x40b937  pop     esi
0x40b938  pop     ebp
0x40b939  retn    4
```
