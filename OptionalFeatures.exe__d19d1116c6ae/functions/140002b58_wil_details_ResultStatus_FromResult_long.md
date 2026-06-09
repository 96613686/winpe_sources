# wil::details::ResultStatus::FromResult(long)

- ea: `0x140002b58`
- end: `0x140002b7c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001b50`
- `0x140001d1c`

## callees

- `0x14000357c`

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
0x140002b58  sub     rsp, 28h
0x140002b5c  mov     r8, rcx
0x140002b5f  mov     [rcx], edx
0x140002b61  mov     ecx, edx; this
0x140002b63  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002b68  mov     [r8+4], eax
0x140002b6c  mov     rax, r8
0x140002b6f  mov     dword ptr [r8+8], 0
0x140002b77  add     rsp, 28h
0x140002b7b  retn
```
