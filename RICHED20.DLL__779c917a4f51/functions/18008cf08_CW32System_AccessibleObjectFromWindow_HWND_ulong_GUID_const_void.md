# CW32System::AccessibleObjectFromWindow(HWND__ *,ulong,_GUID const &,void * *)

- ea: `0x18008cf08`
- end: `0x18008cf6a`
- name: `?AccessibleObjectFromWindow@CW32System@@SAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(HWND, unsigned int, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180061d4c`
- `0x180062990`
- `0x180062b70`
- `0x180062ea0`
- `0x180063370`
- `0x1800633d0`

## callees

- `0x18008cf08`
- `0x1800907ac`
- `0x180092010`

## string_xrefs

- `0x18008cf28`: `AccessibleObjectFromWindow`

## pseudocode

```c
__int64 __fastcall CW32System::AccessibleObjectFromWindow(HWND a1, unsigned int a2, const struct _GUID *a3, void **a4)
{
  __int64 (__fastcall *v4)(HWND, _QWORD, const struct _GUID *, void **); // rax

  v4 = (__int64 (__fastcall *)(HWND, _QWORD, const struct _GUID *, void **))qword_1800A44B0;
  if ( qword_1800A44B0 )
    return v4(a1, a2, a3, a4);
  SetProcAddr((FARPROC *)&qword_1800A44B0, 2, "AccessibleObjectFromWindow");
  v4 = (__int64 (__fastcall *)(HWND, _QWORD, const struct _GUID *, void **))qword_1800A44B0;
  if ( qword_1800A44B0 )
    return v4(a1, a2, a3, a4);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x18008cf08  push    rbx
0x18008cf0a  push    rbp
0x18008cf0b  push    rsi
0x18008cf0c  push    rdi
0x18008cf0d  sub     rsp, 38h
0x18008cf11  mov     rax, cs:qword_1800A44B0
0x18008cf18  mov     rbx, r9
0x18008cf1b  mov     rdi, r8
0x18008cf1e  mov     esi, edx
0x18008cf20  mov     rbp, rcx
0x18008cf23  test    rax, rax
0x18008cf26  jnz     short loc_18008CF51
0x18008cf28  lea     r8, aAccessibleobje; "AccessibleObjectFromWindow"
0x18008cf2f  lea     edx, [rax+2]
0x18008cf32  lea     rcx, qword_1800A44B0
0x18008cf39  call    SetProcAddr
0x18008cf3e  mov     rax, cs:qword_1800A44B0
0x18008cf45  test    rax, rax
0x18008cf48  jnz     short loc_18008CF51
0x18008cf4a  mov     eax, 80004002h
0x18008cf4f  jmp     short loc_18008CF61
0x18008cf51  mov     r9, rbx
0x18008cf54  mov     r8, rdi
0x18008cf57  mov     edx, esi
0x18008cf59  mov     rcx, rbp
0x18008cf5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf61  add     rsp, 38h
0x18008cf65  pop     rdi
0x18008cf66  pop     rsi
0x18008cf67  pop     rbp
0x18008cf68  pop     rbx
0x18008cf69  retn
```
