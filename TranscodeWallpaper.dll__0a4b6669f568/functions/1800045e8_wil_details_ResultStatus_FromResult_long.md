# wil::details::ResultStatus::FromResult(long)

- ea: `0x1800045e8`
- end: `0x18000460c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003040`
- `0x180003234`
- `0x180007234`

## callees

- `0x18000501c`

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
0x1800045e8  sub     rsp, 28h
0x1800045ec  mov     r8, rcx
0x1800045ef  mov     [rcx], edx
0x1800045f1  mov     ecx, edx; this
0x1800045f3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800045f8  mov     [r8+4], eax
0x1800045fc  mov     rax, r8
0x1800045ff  mov     dword ptr [r8+8], 0
0x180004607  add     rsp, 28h
0x18000460b  retn
```
