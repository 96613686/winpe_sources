# wil::details::ResultStatus::FromResult(long)

- ea: `0x180004758`
- end: `0x18000477c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000247c`
- `0x180002678`
- `0x180008ea4`
- `0x18000db90`

## callees

- `0x180005180`

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
0x180004758  sub     rsp, 28h
0x18000475c  mov     r8, rcx
0x18000475f  mov     [rcx], edx
0x180004761  mov     ecx, edx; this
0x180004763  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004768  mov     [r8+4], eax
0x18000476c  mov     rax, r8
0x18000476f  mov     dword ptr [r8+8], 0
0x180004777  add     rsp, 28h
0x18000477b  retn
```
