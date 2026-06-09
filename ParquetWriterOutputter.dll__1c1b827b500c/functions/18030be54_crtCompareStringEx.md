# __crtCompareStringEx

- ea: `0x18030be54`
- end: `0x18030bef0`
- name: `__crtCompareStringEx`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18030ba8c`
- `0x18030c07c`

## callees

- `0x18030be54`
- `0x18030bef0`
- `0x180358070`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18030beda`
- `KERNEL32!CompareStringW` at `0x18030beda`

## pseudocode

```c
int __fastcall _crtCompareStringEx(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        int a4,
        const WCHAR *lpString2,
        int cchCount2)
{
  DWORD v8; // esi
  LCID v10; // eax

  v8 = a2;
  if ( _security_cookie != qword_1804C6828 )
    return ((__int64 (__fastcall *)(__int64, __int64, const WCHAR *))(_security_cookie ^ qword_1804C6828))(a1, a2, a3);
  v10 = _crtDownlevelLocaleNameToLCID();
  return CompareStringW(v10, v8, a3, a4, lpString2, cchCount2);
}

```

## disassembly

```asm
0x18030be54  mov     r11, rsp
0x18030be57  mov     [r11+8], rbx
0x18030be5b  mov     [r11+10h], rsi
0x18030be5f  push    rdi
0x18030be60  sub     rsp, 50h
0x18030be64  mov     rax, cs:qword_1804C6828
0x18030be6b  mov     ebx, r9d
0x18030be6e  xor     rax, cs:__security_cookie
0x18030be75  mov     rdi, r8
0x18030be78  mov     esi, edx
0x18030be7a  mov     r10, rcx
0x18030be7d  jz      short loc_18030BEB3
0x18030be7f  mov     r8d, [rsp+58h+arg_28]
0x18030be87  xor     ecx, ecx
0x18030be89  mov     [r11-18h], rcx
0x18030be8d  mov     [r11-20h], rcx
0x18030be91  mov     [r11-28h], rcx
0x18030be95  mov     rcx, [rsp+58h+arg_20]
0x18030be9d  mov     [r11-30h], r8d
0x18030bea1  mov     r8, rdi
0x18030bea4  mov     [r11-38h], rcx
0x18030bea8  mov     rcx, r10
0x18030beab  call    cs:__guard_dispatch_icall_fptr
0x18030beb1  jmp     short loc_18030BEE0
0x18030beb3  call    __crtDownlevelLocaleNameToLCID
0x18030beb8  mov     ecx, eax; Locale
0x18030beba  mov     r9d, ebx; cchCount1
0x18030bebd  mov     eax, [rsp+58h+arg_28]
0x18030bec4  mov     r8, rdi; lpString1
0x18030bec7  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18030becb  mov     edx, esi; dwCmpFlags
0x18030becd  mov     rax, [rsp+58h+arg_20]
0x18030bed5  mov     [rsp+58h+lpString2], rax; lpString2
0x18030beda  call    cs:__imp_CompareStringW
0x18030bee0  mov     rbx, [rsp+58h+arg_0]
0x18030bee5  mov     rsi, [rsp+58h+arg_8]
0x18030beea  add     rsp, 50h
0x18030beee  pop     rdi
0x18030beef  retn
```
