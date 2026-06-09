# DllEntryPoint

- ea: `0x180011320`
- end: `0x180011397`
- name: `DllEntryPoint`
- size: `119`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001103c`
- `0x180011320`
- `0x180011454`
- `0x18006ccc0`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  __int64 v3; // rbp
  unsigned __int64 v7; // rax
  int v8; // ebx

  v3 = (unsigned int)dword_180088678;
  if ( fdwReason == 1 )
  {
    v7 = __rdtsc();
    LODWORD(v7) = v7 & 0x7FFFFFFF;
    qword_180089020 = v7;
    if ( (int)sub_18001103C() < 0 )
    {
      sub_180011454();
      return 0;
    }
    dword_180089850 = fdwReason;
  }
  v8 = ((__int64 (__fastcall *)(HINSTANCE, _QWORD, LPVOID))(v3 + 0x180000000LL))(hinstDLL, fdwReason, lpReserved);
  if ( !fdwReason )
    sub_180011454();
  return v8;
}

```

## disassembly

```asm
0x180011320  push    rbx
0x180011322  push    rbp
0x180011323  push    rsi
0x180011324  push    rdi
0x180011325  sub     rsp, 28h
0x180011329  mov     ebp, cs:dword_180088678
0x18001132f  mov     rbx, r8
0x180011332  mov     edi, edx
0x180011334  mov     rsi, rcx
0x180011337  cmp     edx, 1
0x18001133a  jnz     short loc_18001135F
0x18001133c  rdtsc
0x18001133e  shl     rdx, 20h
0x180011342  or      rax, rdx
0x180011345  btr     eax, 1Fh
0x180011349  mov     cs:qword_180089020, rax
0x180011350  call    sub_18001103C
0x180011355  test    eax, eax
0x180011357  js      short loc_18001138E
0x180011359  mov     cs:dword_180089850, edi
0x18001135f  lea     rax, cs:180000000h
0x180011366  mov     r8, rbx
0x180011369  add     rax, rbp
0x18001136c  mov     edx, edi
0x18001136e  mov     rcx, rsi
0x180011371  call    cs:__guard_dispatch_icall_fptr
0x180011377  mov     ebx, eax
0x180011379  test    edi, edi
0x18001137b  jnz     short loc_180011382
0x18001137d  call    sub_180011454
0x180011382  mov     eax, ebx
0x180011384  add     rsp, 28h
0x180011388  pop     rdi
0x180011389  pop     rsi
0x18001138a  pop     rbp
0x18001138b  pop     rbx
0x18001138c  retn
0x18001138e  call    sub_180011454
0x180011393  xor     ebx, ebx
0x180011395  jmp     short loc_180011382
```
