# __acrt_CompareStringEx

- ea: `0x18000d66c`
- end: `0x18000d72d`
- name: `__acrt_CompareStringEx`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a4d8`
- `0x18001ab7c`

## callees

- `0x18000c92c`
- `0x18000d66c`
- `0x18000de60`
- `0x180060430`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000d712`
- `KERNEL32!CompareStringW` at `0x18000d712`

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
0x18000d66c  mov     [rsp+arg_0], rbx
0x18000d671  mov     [rsp+arg_8], rbp
0x18000d676  mov     [rsp+arg_10], rsi
0x18000d67b  push    rdi
0x18000d67c  sub     rsp, 50h
0x18000d680  mov     ebx, r9d
0x18000d683  mov     rdi, r8
0x18000d686  mov     esi, edx
0x18000d688  mov     rbp, rcx
0x18000d68b  call    try_get_CompareStringEx
0x18000d690  test    rax, rax
0x18000d693  jz      short loc_18000D6E6
0x18000d695  mov     r10, [rsp+58h+arg_40]
0x18000d69d  mov     r9d, ebx
0x18000d6a0  mov     r8, [rsp+58h+arg_30]
0x18000d6a8  mov     edx, esi
0x18000d6aa  mov     ecx, [rsp+58h+arg_28]
0x18000d6b1  mov     [rsp+58h+var_18], r10
0x18000d6b6  mov     r10, [rsp+58h+arg_38]
0x18000d6be  mov     [rsp+58h+var_20], r10
0x18000d6c3  mov     [rsp+58h+var_28], r8
0x18000d6c8  mov     r8, rdi
0x18000d6cb  mov     [rsp+58h+cchCount2], ecx
0x18000d6cf  mov     rcx, [rsp+58h+arg_20]
0x18000d6d7  mov     [rsp+58h+lpString2], rcx
0x18000d6dc  mov     rcx, rbp
0x18000d6df  call    _guard_dispatch_icall
0x18000d6e4  jmp     short loc_18000D718
0x18000d6e6  xor     edx, edx
0x18000d6e8  mov     rcx, rbp
0x18000d6eb  call    __acrt_LocaleNameToLCID
0x18000d6f0  mov     ecx, eax; Locale
0x18000d6f2  mov     r9d, ebx; cchCount1
0x18000d6f5  mov     eax, [rsp+58h+arg_28]
0x18000d6fc  mov     r8, rdi; lpString1
0x18000d6ff  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18000d703  mov     edx, esi; dwCmpFlags
0x18000d705  mov     rax, [rsp+58h+arg_20]
0x18000d70d  mov     [rsp+58h+lpString2], rax; lpString2
0x18000d712  call    cs:__imp_CompareStringW
0x18000d718  mov     rbx, [rsp+58h+arg_0]
0x18000d71d  mov     rbp, [rsp+58h+arg_8]
0x18000d722  mov     rsi, [rsp+58h+arg_10]
0x18000d727  add     rsp, 50h
0x18000d72b  pop     rdi
0x18000d72c  retn
```
