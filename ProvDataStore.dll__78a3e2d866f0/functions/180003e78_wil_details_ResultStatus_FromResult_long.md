# wil::details::ResultStatus::FromResult(long)

- ea: `0x180003e78`
- end: `0x180003e9c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027e4`
- `0x1800029d8`
- `0x180008058`
- `0x1800109d0`

## callees

- `0x1800049b8`

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
0x180003e78  sub     rsp, 28h
0x180003e7c  mov     r8, rcx
0x180003e7f  mov     [rcx], edx
0x180003e81  mov     ecx, edx; this
0x180003e83  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003e88  mov     [r8+4], eax
0x180003e8c  mov     rax, r8
0x180003e8f  mov     dword ptr [r8+8], 0
0x180003e97  add     rsp, 28h
0x180003e9b  retn
```
