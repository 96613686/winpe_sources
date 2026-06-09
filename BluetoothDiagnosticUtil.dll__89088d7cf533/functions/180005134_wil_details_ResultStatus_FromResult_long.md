# wil::details::ResultStatus::FromResult(long)

- ea: `0x180005134`
- end: `0x180005159`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `37`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f48`
- `0x18000214c`
- `0x1800021b0`

## callees

- `0x180005bc4`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStatus::FromResult(unsigned int *a1, unsigned int a2)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 result; // rax

  *a1 = a2;
  v2 = wil::details::HrToNtStatus((wil::details *)a2);
  *(_DWORD *)(v3 + 4) = v2;
  result = v3;
  *(_DWORD *)(v3 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180005134  sub     rsp, 28h
0x180005138  mov     r8, rcx
0x18000513b  mov     [rcx], edx
0x18000513d  mov     ecx, edx; this
0x18000513f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005144  mov     [r8+4], eax
0x180005148  mov     rax, r8
0x18000514b  mov     dword ptr [r8+8], 0
0x180005153  add     rsp, 28h
0x180005157  retn
```
