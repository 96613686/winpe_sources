# wil::details::ResultStatus::FromResult(long)

- ea: `0x180004ee8`
- end: `0x180004f0c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030c0`
- `0x1800032b4`
- `0x18000819c`
- `0x18000821c`

## callees

- `0x180005b68`

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
0x180004ee8  sub     rsp, 28h
0x180004eec  mov     r8, rcx
0x180004eef  mov     [rcx], edx
0x180004ef1  mov     ecx, edx; this
0x180004ef3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004ef8  mov     [r8+4], eax
0x180004efc  mov     rax, r8
0x180004eff  mov     dword ptr [r8+8], 0
0x180004f07  add     rsp, 28h
0x180004f0b  retn
```
