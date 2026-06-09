# wil::details::ResultStatus::FromResult(long)

- ea: `0x1800049f8`
- end: `0x180004a1c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002520`
- `0x18000271c`
- `0x180009080`
- `0x1800090e4`
- `0x18000bc20`

## callees

- `0x180005420`

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
0x1800049f8  sub     rsp, 28h
0x1800049fc  mov     r8, rcx
0x1800049ff  mov     [rcx], edx
0x180004a01  mov     ecx, edx; this
0x180004a03  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004a08  mov     [r8+4], eax
0x180004a0c  mov     rax, r8
0x180004a0f  mov     dword ptr [r8+8], 0
0x180004a17  add     rsp, 28h
0x180004a1b  retn
```
