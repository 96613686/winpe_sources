# RunServicesInProc

- ea: `0x180005980`
- end: `0x180005995`
- name: `RunServicesInProc`
- size: `21`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005980`

## pseudocode

```c
__int64 __fastcall RunServicesInProc(int *a1)
{
  __int64 result; // rax

  if ( !a1 )
    return (unsigned int)dword_180011908;
  result = (unsigned int)*a1;
  dword_180011908 = *a1;
  return result;
}

```

## disassembly

```asm
0x180005980  test    rcx, rcx
0x180005983  jz      short loc_18000598E
0x180005985  mov     eax, [rcx]
0x180005987  mov     cs:dword_180011908, eax
0x18000598d  retn
0x18000598e  mov     eax, cs:dword_180011908
0x180005994  retn
```
