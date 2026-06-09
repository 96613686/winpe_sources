# DavHttpOpenRequestW

- ea: `0x180029bec`
- end: `0x180029c3e`
- name: `DavHttpOpenRequestW`
- size: `82`
- prototype: `__int64 __fastcall(void *, void *, const WCHAR *, __int64, int, int, int, DWORD, __int64, int *, int, __int64, _QWORD *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045e8`
- `0x1800049bc`
- `0x180007e10`
- `0x18000d9e4`
- `0x180017624`
- `0x18001832c`
- `0x1800196d0`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001dfc0`
- `0x18001f190`
- `0x180020c1c`
- `0x180021008`
- `0x180023360`
- `0x180024190`

## callees

- `0x18002986c`

## pseudocode

```c
__int64 __fastcall DavHttpOpenRequestW(
        void *a1,
        void *a2,
        const WCHAR *a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        DWORD a8,
        __int64 a9,
        int *a10,
        int a11,
        __int64 a12,
        _QWORD *a13)
{
  __int64 v14; // [rsp+28h] [rbp-50h]
  __int64 v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+38h] [rbp-40h]
  __int64 v17; // [rsp+48h] [rbp-30h]

  return DavHttpOpenRequest2(a1, a2, a3, a4, 0, v14, v15, v16, a8, v17, a10, a11, (__int64)pBypassServerNames, a13);
}

```

## disassembly

```asm
0x180029bec  sub     rsp, 78h
0x180029bf0  mov     rax, [rsp+78h+arg_60]
0x180029bf8  mov     r10, cs:pBypassServerNames
0x180029bff  mov     [rsp+78h+var_10], rax
0x180029c04  mov     eax, [rsp+78h+arg_50]
0x180029c0b  mov     [rsp+78h+var_18], r10
0x180029c10  mov     [rsp+78h+var_20], eax
0x180029c14  mov     rax, [rsp+78h+arg_48]
0x180029c1c  mov     [rsp+78h+var_28], rax
0x180029c21  mov     eax, [rsp+78h+arg_38]
0x180029c28  mov     [rsp+78h+var_38], eax
0x180029c2c  mov     [rsp+78h+var_58], 0
0x180029c34  call    DavHttpOpenRequest2
0x180029c39  add     rsp, 78h
0x180029c3d  retn
```
