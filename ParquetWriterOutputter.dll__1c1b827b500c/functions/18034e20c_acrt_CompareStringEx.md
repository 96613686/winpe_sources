# __acrt_CompareStringEx

- ea: `0x18034e20c`
- end: `0x18034e2fb`
- name: `__acrt_CompareStringEx`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180356da8`

## callees

- `0x180023c50`
- `0x18034e06c`
- `0x18034e20c`
- `0x18034ea04`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18034e2da`
- `KERNEL32!CompareStringW` at `0x18034e2da`

## string_xrefs

- `0x18034e22d`: `CompareStringEx`
- `0x18034e23e`: `CompareStringEx`

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
  FARPROC function_0; // rbx
  LCID v15; // eax

  function_0 = try_get_function_0(1u, "CompareStringEx", (unsigned int *)L"\a", (unsigned int *)"CompareStringEx");
  if ( function_0 )
    return ((__int64 (__fastcall *)(__int64, _QWORD, const WCHAR *, _QWORD, const WCHAR *, int, __int64, __int64, __int64))function_0)(
             a1,
             a2,
             a3,
             a4,
             lpString2,
             cchCount2,
             a7,
             a8,
             a9);
  v15 = _acrt_LocaleNameToLCID(a1, 0);
  return CompareStringW(v15, a2, a3, a4, lpString2, cchCount2);
}

```

## disassembly

```asm
0x18034e20c  mov     rax, rsp
0x18034e20f  mov     [rax+8], rbx
0x18034e213  mov     [rax+10h], rbp
0x18034e217  mov     [rax+18h], rsi
0x18034e21b  mov     [rax+20h], rdi
0x18034e21f  push    r14
0x18034e221  sub     rsp, 50h
0x18034e225  mov     edi, r9d
0x18034e228  mov     rsi, r8
0x18034e22b  mov     ebp, edx
0x18034e22d  lea     r9, aComparestringe_0
0x18034e234  mov     r14, rcx
0x18034e237  lea     r8, asc_180402FC0
0x18034e23e  lea     rdx, aComparestringe_0
0x18034e245  mov     ecx, 1
0x18034e24a  call    try_get_function_0
0x18034e24f  mov     rbx, rax
0x18034e252  test    rax, rax
0x18034e255  jz      short loc_18034E2AE
0x18034e257  mov     rcx, rax; this
0x18034e25a  call    cs:__guard_check_icall_fptr
0x18034e260  mov     rcx, [rsp+58h+arg_40]
0x18034e268  mov     r9d, edi
0x18034e26b  mov     rax, [rsp+58h+arg_20]
0x18034e273  mov     r8, rsi
0x18034e276  mov     [rsp+58h+var_18], rcx
0x18034e27b  mov     edx, ebp
0x18034e27d  mov     rcx, [rsp+58h+arg_38]
0x18034e285  mov     [rsp+58h+var_20], rcx
0x18034e28a  mov     rcx, [rsp+58h+arg_30]
0x18034e292  mov     [rsp+58h+var_28], rcx
0x18034e297  mov     ecx, [rsp+58h+arg_28]
0x18034e29e  mov     [rsp+58h+cchCount2], ecx
0x18034e2a2  mov     rcx, r14
0x18034e2a5  mov     [rsp+58h+lpString2], rax
0x18034e2aa  call    rbx
0x18034e2ac  jmp     short loc_18034E2E0
0x18034e2ae  xor     edx, edx
0x18034e2b0  mov     rcx, r14
0x18034e2b3  call    __acrt_LocaleNameToLCID
0x18034e2b8  mov     ecx, eax; Locale
0x18034e2ba  mov     r9d, edi; cchCount1
0x18034e2bd  mov     eax, [rsp+58h+arg_28]
0x18034e2c4  mov     r8, rsi; lpString1
0x18034e2c7  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18034e2cb  mov     edx, ebp; dwCmpFlags
0x18034e2cd  mov     rax, [rsp+58h+arg_20]
0x18034e2d5  mov     [rsp+58h+lpString2], rax; lpString2
0x18034e2da  call    cs:__imp_CompareStringW
0x18034e2e0  mov     rbx, [rsp+58h+arg_0]
0x18034e2e5  mov     rbp, [rsp+58h+arg_8]
0x18034e2ea  mov     rsi, [rsp+58h+arg_10]
0x18034e2ef  mov     rdi, [rsp+58h+arg_18]
0x18034e2f4  add     rsp, 50h
0x18034e2f8  pop     r14
0x18034e2fa  retn
```
