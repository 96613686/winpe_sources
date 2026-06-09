# wil::details::ResultStatus::FromResult(long)

- ea: `0x18000574c`
- end: `0x180005770`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032d8`
- `0x180003360`
- `0x18000353c`
- `0x1800035a0`
- `0x180003f04`

## callees

- `0x1800060f0`

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
0x18000574c  sub     rsp, 28h
0x180005750  mov     r8, rcx
0x180005753  mov     [rcx], edx
0x180005755  mov     ecx, edx; this
0x180005757  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000575c  mov     [r8+4], eax
0x180005760  mov     rax, r8
0x180005763  mov     dword ptr [r8+8], 0
0x18000576b  add     rsp, 28h
0x18000576f  retn
```
