# __acrt_CompareStringEx

- ea: `0x18000cf0c`
- end: `0x18000cfcd`
- name: `__acrt_CompareStringEx`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019d78`
- `0x18001a41c`

## callees

- `0x18000c1cc`
- `0x18000cf0c`
- `0x18000d700`
- `0x180060150`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000cfb2`
- `KERNEL32!CompareStringW` at `0x18000cfb2`

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
0x18000cf0c  mov     [rsp+arg_0], rbx
0x18000cf11  mov     [rsp+arg_8], rbp
0x18000cf16  mov     [rsp+arg_10], rsi
0x18000cf1b  push    rdi
0x18000cf1c  sub     rsp, 50h
0x18000cf20  mov     ebx, r9d
0x18000cf23  mov     rdi, r8
0x18000cf26  mov     esi, edx
0x18000cf28  mov     rbp, rcx
0x18000cf2b  call    try_get_CompareStringEx
0x18000cf30  test    rax, rax
0x18000cf33  jz      short loc_18000CF86
0x18000cf35  mov     r10, [rsp+58h+arg_40]
0x18000cf3d  mov     r9d, ebx
0x18000cf40  mov     r8, [rsp+58h+arg_30]
0x18000cf48  mov     edx, esi
0x18000cf4a  mov     ecx, [rsp+58h+arg_28]
0x18000cf51  mov     [rsp+58h+var_18], r10
0x18000cf56  mov     r10, [rsp+58h+arg_38]
0x18000cf5e  mov     [rsp+58h+var_20], r10
0x18000cf63  mov     [rsp+58h+var_28], r8
0x18000cf68  mov     r8, rdi
0x18000cf6b  mov     [rsp+58h+cchCount2], ecx
0x18000cf6f  mov     rcx, [rsp+58h+arg_20]
0x18000cf77  mov     [rsp+58h+lpString2], rcx
0x18000cf7c  mov     rcx, rbp
0x18000cf7f  call    _guard_dispatch_icall
0x18000cf84  jmp     short loc_18000CFB8
0x18000cf86  xor     edx, edx
0x18000cf88  mov     rcx, rbp
0x18000cf8b  call    __acrt_LocaleNameToLCID
0x18000cf90  mov     ecx, eax; Locale
0x18000cf92  mov     r9d, ebx; cchCount1
0x18000cf95  mov     eax, [rsp+58h+arg_28]
0x18000cf9c  mov     r8, rdi; lpString1
0x18000cf9f  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18000cfa3  mov     edx, esi; dwCmpFlags
0x18000cfa5  mov     rax, [rsp+58h+arg_20]
0x18000cfad  mov     [rsp+58h+lpString2], rax; lpString2
0x18000cfb2  call    cs:__imp_CompareStringW
0x18000cfb8  mov     rbx, [rsp+58h+arg_0]
0x18000cfbd  mov     rbp, [rsp+58h+arg_8]
0x18000cfc2  mov     rsi, [rsp+58h+arg_10]
0x18000cfc7  add     rsp, 50h
0x18000cfcb  pop     rdi
0x18000cfcc  retn
```
