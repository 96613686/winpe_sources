# I_CommitPinToCache

- ea: `0x180029fcc`
- end: `0x18002a019`
- name: `I_CommitPinToCache`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002a368`
- `0x18002a814`

## callees

- `0x180029fcc`
- `0x18002a0d0`

## import_xrefs

- `msvcrt!time` at `0x180029fe5`
- `msvcrt!time` at `0x180029fe5`

## pseudocode

```c
__int64 __fastcall I_CommitPinToCache(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, int a5)
{
  time((time_t *const)(a1 + 40));
  if ( a4 && *(_DWORD *)(a4 + 24) == 1 )
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(a4 + 28);
  *(_DWORD *)(a1 + 32) = a5;
  return I_PinCacheEncryptPin(a1, a2, a3);
}

```

## disassembly

```asm
0x180029fcc  push    rbx
0x180029fce  push    rbp
0x180029fcf  push    rsi
0x180029fd0  push    rdi
0x180029fd1  sub     rsp, 28h
0x180029fd5  mov     rdi, rcx
0x180029fd8  mov     rbx, r9
0x180029fdb  add     rcx, 28h ; '('; Time
0x180029fdf  mov     esi, r8d
0x180029fe2  mov     rbp, rdx
0x180029fe5  call    cs:__imp_time
0x180029feb  test    rbx, rbx
0x180029fee  jz      short loc_180029FFC
0x180029ff0  cmp     dword ptr [rbx+18h], 1
0x180029ff4  jnz     short loc_180029FFC
0x180029ff6  mov     eax, [rbx+1Ch]
0x180029ff9  mov     [rdi+30h], eax
0x180029ffc  mov     eax, [rsp+48h+arg_20]
0x18002a000  mov     r8d, esi
0x18002a003  mov     rdx, rbp
0x18002a006  mov     [rdi+20h], eax
0x18002a009  mov     rcx, rdi
0x18002a00c  add     rsp, 28h
0x18002a010  pop     rdi
0x18002a011  pop     rsi
0x18002a012  pop     rbp
0x18002a013  pop     rbx
0x18002a014  jmp     I_PinCacheEncryptPin
```
