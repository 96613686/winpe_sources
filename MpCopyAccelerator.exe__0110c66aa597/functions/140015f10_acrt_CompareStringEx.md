# __acrt_CompareStringEx

- ea: `0x140015f10`
- end: `0x140015fd1`
- name: `__acrt_CompareStringEx`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001bf98`

## callees

- `0x140015cc8`
- `0x140015f10`
- `0x1400160fc`
- `0x140024c80`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140015fb6`
- `KERNEL32!CompareStringW` at `0x140015fb6`

## pseudocode

```c
int __fastcall _acrt_CompareStringEx(
        __int64 a1,
        DWORD a2,
        const WCHAR *a3,
        unsigned int a4,
        const WCHAR *lpString2,
        int cchCount2,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 (__fastcall *CompareString)(__int64, _QWORD, const WCHAR *, _QWORD, const WCHAR *, int, __int64, __int64, __int64); // rax
  LCID v15; // eax

  CompareString = (__int64 (__fastcall *)(__int64, _QWORD, const WCHAR *, _QWORD, const WCHAR *, int, __int64, __int64, __int64))try_get_CompareStringEx();
  if ( CompareString )
    return CompareString(a1, a2, a3, a4, lpString2, cchCount2, a7, a8, a9);
  v15 = _acrt_LocaleNameToLCID(a1, 0);
  return CompareStringW(v15, a2, a3, a4, lpString2, cchCount2);
}

```

## disassembly

```asm
0x140015f10  mov     [rsp+arg_0], rbx
0x140015f15  mov     [rsp+arg_8], rbp
0x140015f1a  mov     [rsp+arg_10], rsi
0x140015f1f  push    rdi
0x140015f20  sub     rsp, 50h
0x140015f24  mov     ebx, r9d
0x140015f27  mov     rdi, r8
0x140015f2a  mov     esi, edx
0x140015f2c  mov     rbp, rcx
0x140015f2f  call    try_get_CompareStringEx
0x140015f34  test    rax, rax
0x140015f37  jz      short loc_140015F8A
0x140015f39  mov     r10, [rsp+58h+arg_40]
0x140015f41  mov     r9d, ebx
0x140015f44  mov     r8, [rsp+58h+arg_30]
0x140015f4c  mov     edx, esi
0x140015f4e  mov     ecx, [rsp+58h+arg_28]
0x140015f55  mov     [rsp+58h+var_18], r10
0x140015f5a  mov     r10, [rsp+58h+arg_38]
0x140015f62  mov     [rsp+58h+var_20], r10
0x140015f67  mov     [rsp+58h+var_28], r8
0x140015f6c  mov     r8, rdi
0x140015f6f  mov     [rsp+58h+cchCount2], ecx
0x140015f73  mov     rcx, [rsp+58h+arg_20]
0x140015f7b  mov     [rsp+58h+lpString2], rcx
0x140015f80  mov     rcx, rbp
0x140015f83  call    _guard_dispatch_icall
0x140015f88  jmp     short loc_140015FBC
0x140015f8a  xor     edx, edx
0x140015f8c  mov     rcx, rbp
0x140015f8f  call    __acrt_LocaleNameToLCID
0x140015f94  mov     ecx, eax; Locale
0x140015f96  mov     r9d, ebx; cchCount1
0x140015f99  mov     eax, [rsp+58h+arg_28]
0x140015fa0  mov     r8, rdi; lpString1
0x140015fa3  mov     [rsp+58h+cchCount2], eax; cchCount2
0x140015fa7  mov     edx, esi; dwCmpFlags
0x140015fa9  mov     rax, [rsp+58h+arg_20]
0x140015fb1  mov     [rsp+58h+lpString2], rax; lpString2
0x140015fb6  call    cs:__imp_CompareStringW
0x140015fbc  mov     rbx, [rsp+58h+arg_0]
0x140015fc1  mov     rbp, [rsp+58h+arg_8]
0x140015fc6  mov     rsi, [rsp+58h+arg_10]
0x140015fcb  add     rsp, 50h
0x140015fcf  pop     rdi
0x140015fd0  retn
```
