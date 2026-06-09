# wil::details::ResultStatus::FromResult(long)

- ea: `0x180004488`
- end: `0x1800044ac`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030a4`
- `0x180003298`
- `0x180007334`
- `0x1800073ac`
- `0x180007438`

## callees

- `0x180004ebc`

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
0x180004488  sub     rsp, 28h
0x18000448c  mov     r8, rcx
0x18000448f  mov     [rcx], edx
0x180004491  mov     ecx, edx; this
0x180004493  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004498  mov     [r8+4], eax
0x18000449c  mov     rax, r8
0x18000449f  mov     dword ptr [r8+8], 0
0x1800044a7  add     rsp, 28h
0x1800044ab  retn
```
