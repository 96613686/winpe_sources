# std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(std::tr1::shared_ptr<IRegistryKey> &&)

- ea: `0x1800201ec`
- end: `0x180020217`
- name: `??0?$shared_ptr@VIRegistryKey@@@tr1@std@@QEAA@$$QEAV012@@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180020198`
- `0x1800211a8`

## callees

- `0x1800201ec`

## pseudocode

```c
__int64 *__fastcall std::tr1::shared_ptr<IRegistryKey>::shared_ptr<IRegistryKey>(__int64 *a1, __int64 *a2)
{
  __int64 v2; // r8

  *a1 = 0;
  a1[1] = 0;
  if ( a1 != a2 )
  {
    a1[1] = a2[1];
    a2[1] = 0;
    v2 = *a1;
    *a1 = *a2;
    *a2 = v2;
  }
  return a1;
}

```

## disassembly

```asm
0x1800201ec  xor     r8d, r8d
0x1800201ef  mov     [rcx], r8
0x1800201f2  mov     [rcx+8], r8
0x1800201f6  cmp     rcx, rdx
0x1800201f9  jz      short loc_180020213
0x1800201fb  mov     rax, [rdx+8]
0x1800201ff  mov     [rcx+8], rax
0x180020203  mov     [rdx+8], r8
0x180020207  mov     rax, [rdx]
0x18002020a  mov     r8, [rcx]
0x18002020d  mov     [rcx], rax
0x180020210  mov     [rdx], r8
0x180020213  mov     rax, rcx
0x180020216  retn
```
