# AVIStreamLength

- ea: `0x180008350`
- end: `0x1800083c3`
- name: `AVIStreamLength`
- size: `115`
- prototype: `LONG __stdcall(PAVISTREAM pavi)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fe0`
- `0x180005470`
- `0x180011594`
- `0x180011944`
- `0x180011a64`
- `0x180015880`
- `0x180015e7c`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180018010`

## pseudocode

```c
LONG __stdcall AVIStreamLength(PAVISTREAM pavi)
{
  int v2; // eax
  LONG v3; // ecx
  _BYTE v5[32]; // [rsp+20h] [rbp-E8h] BYREF
  LONG v6; // [rsp+40h] [rbp-C8h]

  memset_0(v5, 0, 0xCCu);
  v2 = ((__int64 (__fastcall *)(PAVISTREAM, _BYTE *, __int64))pavi->lpVtbl->Info)(pavi, v5, 204);
  v3 = v6;
  if ( v2 )
    return 1;
  return v3;
}

```

## disassembly

```asm
0x180008350  push    rbx
0x180008352  sub     rsp, 100h
0x180008359  mov     rax, cs:__security_cookie
0x180008360  xor     rax, rsp
0x180008363  mov     [rsp+108h+var_18], rax
0x18000836b  mov     rbx, rcx
0x18000836e  xor     edx, edx; Val
0x180008370  lea     rcx, [rsp+108h+var_E8]; void *
0x180008375  mov     r8d, 0CCh; Size
0x18000837b  call    memset_0
0x180008380  mov     rax, [rbx]
0x180008383  lea     rdx, [rsp+108h+var_E8]
0x180008388  mov     r8d, 0CCh
0x18000838e  mov     rcx, rbx
0x180008391  mov     rax, [rax+20h]
0x180008395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000839a  mov     ecx, [rsp+108h+var_C8]
0x18000839e  test    eax, eax
0x1800083a0  mov     edx, 1
0x1800083a5  cmovnz  ecx, edx
0x1800083a8  mov     eax, ecx
0x1800083aa  mov     rcx, [rsp+108h+var_18]
0x1800083b2  xor     rcx, rsp; StackCookie
0x1800083b5  call    __security_check_cookie
0x1800083ba  add     rsp, 100h
0x1800083c1  pop     rbx
0x1800083c2  retn
```
