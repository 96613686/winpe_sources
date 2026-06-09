# dllmain_raw

- ea: `0x180004278`
- end: `0x1800042cc`
- name: `dllmain_raw`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004180`

## callees

- `0x180004278`
- `0x180004498`

## pseudocode

```c
__int64 __fastcall dllmain_raw(__int64 a1, unsigned int a2, __int64 a3)
{
  if ( pRawDllMain )
    return ((__int64 (__fastcall *)(__int64, _QWORD, __int64))pRawDllMain)(a1, a2, a3);
  else
    return 1;
}

```

## disassembly

```asm
0x180004278  mov     [rsp+arg_0], rbx
0x18000427d  mov     [rsp+arg_8], rbp
0x180004282  mov     [rsp+arg_10], rsi
0x180004287  push    rdi
0x180004288  sub     rsp, 20h
0x18000428c  mov     rbx, cs:_pRawDllMain
0x180004293  mov     rdi, r8
0x180004296  mov     esi, edx
0x180004298  mov     rbp, rcx
0x18000429b  test    rbx, rbx
0x18000429e  jnz     short loc_1800042A5
0x1800042a0  lea     eax, [rbx+1]
0x1800042a3  jmp     short loc_1800042B7
0x1800042a5  mov     rcx, rbx; Target
0x1800042a8  call    _guard_check_icall
0x1800042ad  mov     r8, rdi
0x1800042b0  mov     edx, esi
0x1800042b2  mov     rcx, rbp
0x1800042b5  call    rbx ; _pRawDllMain
0x1800042b7  mov     rbx, [rsp+28h+arg_0]
0x1800042bc  mov     rbp, [rsp+28h+arg_8]
0x1800042c1  mov     rsi, [rsp+28h+arg_10]
0x1800042c6  add     rsp, 20h
0x1800042ca  pop     rdi
0x1800042cb  retn
```
