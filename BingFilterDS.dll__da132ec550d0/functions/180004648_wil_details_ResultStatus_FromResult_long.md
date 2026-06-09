# wil::details::ResultStatus::FromResult(long)

- ea: `0x180004648`
- end: `0x18000466c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fc8`
- `0x1800031bc`
- `0x180007e10`
- `0x180007e90`

## callees

- `0x180005188`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStatus::FromResult(unsigned int *a1, unsigned int a2)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 result; // rax

  *a1 = a2;
  v2 = wil::details::HrToNtStatus((wil::details *)a2, a2);
  *(_DWORD *)(v3 + 4) = v2;
  result = v3;
  *(_DWORD *)(v3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180004648  sub     rsp, 28h
0x18000464c  mov     r8, rcx
0x18000464f  mov     [rcx], edx
0x180004651  mov     ecx, edx; this
0x180004653  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004658  mov     [r8+4], eax
0x18000465c  mov     rax, r8
0x18000465f  mov     dword ptr [r8+8], 0
0x180004667  add     rsp, 28h
0x18000466b  retn
```
