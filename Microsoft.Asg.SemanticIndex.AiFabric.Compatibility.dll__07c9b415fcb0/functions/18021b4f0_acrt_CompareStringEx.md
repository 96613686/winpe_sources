# __acrt_CompareStringEx

- ea: `0x18021b4f0`
- end: `0x18021b5b1`
- name: `__acrt_CompareStringEx`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1802286cc`

## callees

- `0x18021b200`
- `0x18021b4f0`
- `0x18021baf4`
- `0x180242160`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18021b596`
- `KERNEL32!CompareStringW` at `0x18021b596`

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
0x18021b4f0  mov     [rsp+arg_0], rbx
0x18021b4f5  mov     [rsp+arg_8], rbp
0x18021b4fa  mov     [rsp+arg_10], rsi
0x18021b4ff  push    rdi
0x18021b500  sub     rsp, 50h
0x18021b504  mov     ebx, r9d
0x18021b507  mov     rdi, r8
0x18021b50a  mov     esi, edx
0x18021b50c  mov     rbp, rcx
0x18021b50f  call    try_get_CompareStringEx
0x18021b514  test    rax, rax
0x18021b517  jz      short loc_18021B56A
0x18021b519  mov     r10, [rsp+58h+arg_40]
0x18021b521  mov     r9d, ebx
0x18021b524  mov     r8, [rsp+58h+arg_30]
0x18021b52c  mov     edx, esi
0x18021b52e  mov     ecx, [rsp+58h+arg_28]
0x18021b535  mov     [rsp+58h+var_18], r10
0x18021b53a  mov     r10, [rsp+58h+arg_38]
0x18021b542  mov     [rsp+58h+var_20], r10
0x18021b547  mov     [rsp+58h+var_28], r8
0x18021b54c  mov     r8, rdi
0x18021b54f  mov     [rsp+58h+cchCount2], ecx
0x18021b553  mov     rcx, [rsp+58h+arg_20]
0x18021b55b  mov     [rsp+58h+lpString2], rcx
0x18021b560  mov     rcx, rbp
0x18021b563  call    _guard_dispatch_icall
0x18021b568  jmp     short loc_18021B59C
0x18021b56a  xor     edx, edx
0x18021b56c  mov     rcx, rbp
0x18021b56f  call    __acrt_LocaleNameToLCID
0x18021b574  mov     ecx, eax; Locale
0x18021b576  mov     r9d, ebx; cchCount1
0x18021b579  mov     eax, [rsp+58h+arg_28]
0x18021b580  mov     r8, rdi; lpString1
0x18021b583  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18021b587  mov     edx, esi; dwCmpFlags
0x18021b589  mov     rax, [rsp+58h+arg_20]
0x18021b591  mov     [rsp+58h+lpString2], rax; lpString2
0x18021b596  call    cs:__imp_CompareStringW
0x18021b59c  mov     rbx, [rsp+58h+arg_0]
0x18021b5a1  mov     rbp, [rsp+58h+arg_8]
0x18021b5a6  mov     rsi, [rsp+58h+arg_10]
0x18021b5ab  add     rsp, 50h
0x18021b5af  pop     rdi
0x18021b5b0  retn
```
