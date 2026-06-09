# AVIStreamStart

- ea: `0x1800086a0`
- end: `0x180008707`
- name: `AVIStreamStart`
- size: `103`
- prototype: `LONG __stdcall(PAVISTREAM pavi)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fe0`
- `0x1800034e4`
- `0x180003968`
- `0x180005470`
- `0x180011010`
- `0x180011190`
- `0x180011944`
- `0x180013d70`
- `0x180015880`
- `0x180015e7c`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180018010`

## pseudocode

```c
LONG __stdcall AVIStreamStart(PAVISTREAM pavi)
{
  _BYTE v3[28]; // [rsp+20h] [rbp-E8h] BYREF
  LONG v4; // [rsp+3Ch] [rbp-CCh]

  memset_0(v3, 0, 0xCCu);
  ((void (__fastcall *)(PAVISTREAM, _BYTE *, __int64))pavi->lpVtbl->Info)(pavi, v3, 204);
  return v4;
}

```

## disassembly

```asm
0x1800086a0  push    rbx
0x1800086a2  sub     rsp, 100h
0x1800086a9  mov     rax, cs:__security_cookie
0x1800086b0  xor     rax, rsp
0x1800086b3  mov     [rsp+108h+var_18], rax
0x1800086bb  mov     rbx, rcx
0x1800086be  xor     edx, edx; Val
0x1800086c0  lea     rcx, [rsp+108h+var_E8]; void *
0x1800086c5  mov     r8d, 0CCh; Size
0x1800086cb  call    memset_0
0x1800086d0  mov     rax, [rbx]
0x1800086d3  lea     rdx, [rsp+108h+var_E8]
0x1800086d8  mov     r8d, 0CCh
0x1800086de  mov     rcx, rbx
0x1800086e1  mov     rax, [rax+20h]
0x1800086e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ea  mov     eax, [rsp+108h+var_CC]
0x1800086ee  mov     rcx, [rsp+108h+var_18]
0x1800086f6  xor     rcx, rsp; StackCookie
0x1800086f9  call    __security_check_cookie
0x1800086fe  add     rsp, 100h
0x180008705  pop     rbx
0x180008706  retn
```
