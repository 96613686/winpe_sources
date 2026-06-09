# wil::details::ResultStatus::FromResult(long)

- ea: `0x180003de8`
- end: `0x180003e0c`
- name: `?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z`
- size: `36`
- prototype: `static struct wil::details::ResultStatus __high(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a9c`
- `0x180002c84`
- `0x180006734`
- `0x1800067a4`

## callees

- `0x180004800`

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
0x180003de8  sub     rsp, 28h
0x180003dec  mov     r8, rcx
0x180003def  mov     [rcx], edx
0x180003df1  mov     ecx, edx; this
0x180003df3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003df8  mov     [r8+4], eax
0x180003dfc  mov     rax, r8
0x180003dff  mov     dword ptr [r8+8], 0
0x180003e07  add     rsp, 28h
0x180003e0b  retn
```
