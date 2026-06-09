# DllCanUnloadNow

- ea: `0x180009cb0`
- end: `0x180009cd9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(qword_18001B960 + 24LL))(&qword_18001B960) != 0;
}

```

## disassembly

```asm
0x180009cb0  sub     rsp, 28h
0x180009cb4  mov     rax, cs:qword_18001B960
0x180009cbb  lea     rcx, qword_18001B960
0x180009cc2  mov     rax, [rax+18h]
0x180009cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ccb  xor     ecx, ecx
0x180009ccd  test    eax, eax
0x180009ccf  setnz   cl
0x180009cd2  mov     eax, ecx
0x180009cd4  add     rsp, 28h
0x180009cd8  retn
```
