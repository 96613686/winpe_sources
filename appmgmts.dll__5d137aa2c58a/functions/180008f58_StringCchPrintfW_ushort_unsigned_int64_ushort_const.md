# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180008f58`
- end: `0x180008fdb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `34`
- callee_count: `2`
- tags: ``

## callers

- `0x1800060fc`
- `0x180007ea4`
- `0x18000b7e8`
- `0x18000c6a0`
- `0x18000d11c`
- `0x18000d1f4`
- `0x18000d2d8`
- `0x18000d44c`
- `0x18000d524`
- `0x18000d5fc`
- `0x18000d734`
- `0x180012fbc`
- `0x180014d7c`
- `0x180015120`
- `0x18001af7c`
- `0x18001b1a0`
- `0x18001cb90`
- `0x18001d240`
- `0x18001ed14`
- `0x18001f570`
- `0x18001f800`
- `0x18001fa10`
- `0x180020180`
- `0x1800208c4`
- `0x180021b70`
- `0x180021dd0`
- `0x180022940`
- `0x180023050`
- `0x180023330`
- `0x180023cdc`
- `0x180024e04`
- `0x180026f3c`
- `0x18002a57c`
- `0x18002ab7c`

## callees

- `0x180002030`
- `0x180008f58`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180008f58  mov     [rsp+arg_10], r8
0x180008f5d  mov     qword ptr [rsp+Args], r9
0x180008f62  push    rbx
0x180008f63  push    rdi
0x180008f64  sub     rsp, 38h
0x180008f68  mov     rax, rdx
0x180008f6b  mov     rdi, rcx
0x180008f6e  test    rdx, rdx
0x180008f71  jz      short loc_180008FC3
0x180008f73  cmp     rax, 7FFFFFFFh
0x180008f79  jbe     short loc_180008F82
0x180008f7b  mov     edx, 80070057h
0x180008f80  jmp     short loc_180008FCD
0x180008f82  lea     rbx, [rdx-1]
0x180008f86  mov     [rsp+48h+var_28], 0
0x180008f8f  mov     rdx, rbx; BufferCount
0x180008f92  lea     r9, [rsp+48h+Args]; Args
0x180008f97  call    _vsnwprintf
0x180008f9c  test    eax, eax
0x180008f9e  js      short loc_180008FB6
0x180008fa0  cdqe
0x180008fa2  cmp     rax, rbx
0x180008fa5  ja      short loc_180008FB6
0x180008fa7  xor     edx, edx
0x180008fa9  cmp     rax, rbx
0x180008fac  jnz     short loc_180008FD2
0x180008fae  xor     eax, eax
0x180008fb0  mov     [rdi+rbx*2], ax
0x180008fb4  jmp     short loc_180008FD2
0x180008fb6  xor     eax, eax
0x180008fb8  mov     edx, 8007007Ah
0x180008fbd  mov     [rdi+rbx*2], ax
0x180008fc1  jmp     short loc_180008FD2
0x180008fc3  mov     edx, 80070057h
0x180008fc8  test    rax, rax
0x180008fcb  jz      short loc_180008FD2
0x180008fcd  xor     ecx, ecx
0x180008fcf  mov     [rdi], cx
0x180008fd2  mov     eax, edx
0x180008fd4  add     rsp, 38h
0x180008fd8  pop     rdi
0x180008fd9  pop     rbx
0x180008fda  retn
```
