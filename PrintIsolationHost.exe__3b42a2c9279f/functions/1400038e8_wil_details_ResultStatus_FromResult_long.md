# wil::details::ResultStatus::FromResult(long)

- ea: `0x1400038e8`
- end: `0x14000390c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400027d4`
- `0x1400029a0`

## callees

- `0x14000430c`

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
0x1400038e8  sub     rsp, 28h
0x1400038ec  mov     r8, rcx
0x1400038ef  mov     [rcx], edx
0x1400038f1  mov     ecx, edx; this
0x1400038f3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400038f8  mov     [r8+4], eax
0x1400038fc  mov     rax, r8
0x1400038ff  mov     dword ptr [r8+8], 0
0x140003907  add     rsp, 28h
0x14000390b  retn
```
