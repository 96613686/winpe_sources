# pcache1Alloc

- ea: `0x18000b0dc`
- end: `0x18000b20e`
- name: `pcache1Alloc`
- size: `306`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x1800084bc`
- `0x18000b2b0`
- `0x180020e14`
- `0x18005d4a0`
- `0x180081bdc`

## callees

- `0x180009f00`
- `0x18000b0dc`
- `0x18000b220`
- `0x18000bd90`
- `0x18000cc20`
- `0x180047150`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall pcache1Alloc(int a1)
{
  __int64 v1; // rdi
  __int64 v2; // rax
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rdx
  unsigned int v9; // r8d

  v1 = a1;
  if ( a1 > dword_1800B5CAC )
    goto LABEL_2;
  sqlite3_mutex_enter(qword_1800B5CC8);
  v3 = qword_1800B5CD0;
  if ( qword_1800B5CD0 )
  {
    qword_1800B5CD0 = *(_QWORD *)qword_1800B5CD0;
    dword_1800B5CDC = --dword_1800B5CD8 < dword_1800B5CB4;
    sqlite3StatusHighwater(7, (unsigned int)v1);
    sqlite3StatusUp(v9, v9);
  }
  sqlite3_mutex_leave(qword_1800B5CC8);
  if ( !v3 )
  {
LABEL_2:
    v2 = sqlite3Malloc(v1);
    v3 = v2;
    if ( v2 )
    {
      v4 = ((__int64 (__fastcall *)(__int64))xmmword_1800B5668)(v2);
      v5 = qword_1800B5CC8;
      v6 = v4;
      if ( qword_1800B5CC8 )
      {
        ((void (*)(void))xmmword_1800B56B0)();
        v5 = qword_1800B5CC8;
      }
      if ( v1 > qword_1800B5BC8 )
        qword_1800B5BC8 = v1;
      v7 = v6 + qword_1800B5B50;
      qword_1800B5B50 += v6;
      if ( qword_1800B5B50 > qword_1800B5BA0 )
        qword_1800B5BA0 = v7;
      if ( v5 )
        ((void (*)(void))xmmword_1800B56C0)();
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000b0dc  mov     [rsp+arg_0], rbx
0x18000b0e1  mov     [rsp+arg_8], rsi
0x18000b0e6  push    rdi
0x18000b0e7  sub     rsp, 20h
0x18000b0eb  movsxd  rdi, ecx
0x18000b0ee  cmp     edi, cs:dword_1800B5CAC
0x18000b0f4  jle     loc_18000B1AB
0x18000b0fa  mov     rcx, rdi
0x18000b0fd  call    sqlite3Malloc
0x18000b102  mov     rbx, rax
0x18000b105  test    rax, rax
0x18000b108  jz      short loc_18000B186
0x18000b10a  mov     rcx, rax
0x18000b10d  mov     rax, qword ptr cs:xmmword_1800B5668
0x18000b114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b119  mov     rcx, cs:qword_1800B5CC8
0x18000b120  movsxd  rsi, eax
0x18000b123  test    rcx, rcx
0x18000b126  jz      short loc_18000B13B
0x18000b128  mov     rax, qword ptr cs:xmmword_1800B56B0
0x18000b12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b134  mov     rcx, cs:qword_1800B5CC8
0x18000b13b  cmp     rdi, cs:qword_1800B5BC8
0x18000b142  jg      short loc_18000B1A2
0x18000b144  mov     rdx, cs:qword_1800B5B50
0x18000b14b  add     rdx, rsi
0x18000b14e  cmp     rdx, cs:qword_1800B5BA0
0x18000b155  mov     cs:qword_1800B5B50, rdx
0x18000b15c  jg      short loc_18000B199
0x18000b15e  test    rcx, rcx
0x18000b161  jz      short loc_18000B186
0x18000b163  mov     rax, qword ptr cs:xmmword_1800B56C0
0x18000b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16f  jmp     short loc_18000B186
0x18000b171  mov     rcx, cs:qword_1800B5CC8
0x18000b178  call    sqlite3_mutex_leave
0x18000b17d  test    rbx, rbx
0x18000b180  jz      loc_18000B0FA
0x18000b186  mov     rsi, [rsp+28h+arg_8]
0x18000b18b  mov     rax, rbx
0x18000b18e  mov     rbx, [rsp+28h+arg_0]
0x18000b193  add     rsp, 20h
0x18000b197  pop     rdi
0x18000b198  retn
0x18000b199  mov     cs:qword_1800B5BA0, rdx
0x18000b1a0  jmp     short loc_18000B15E
0x18000b1a2  mov     cs:qword_1800B5BC8, rdi
0x18000b1a9  jmp     short loc_18000B144
0x18000b1ab  mov     rcx, cs:qword_1800B5CC8
0x18000b1b2  call    sqlite3_mutex_enter
0x18000b1b7  mov     rbx, cs:qword_1800B5CD0
0x18000b1be  test    rbx, rbx
0x18000b1c1  jz      short loc_18000B171
0x18000b1c3  mov     rax, [rbx]
0x18000b1c6  mov     r8d, 1
0x18000b1cc  mov     edx, cs:dword_1800B5CD8
0x18000b1d2  mov     cs:qword_1800B5CD0, rax
0x18000b1d9  sub     edx, r8d
0x18000b1dc  xor     eax, eax
0x18000b1de  mov     cs:dword_1800B5CD8, edx
0x18000b1e4  cmp     edx, cs:dword_1800B5CB4
0x18000b1ea  lea     ecx, [r8+6]
0x18000b1ee  mov     edx, edi
0x18000b1f0  setl    al
0x18000b1f3  mov     cs:dword_1800B5CDC, eax
0x18000b1f9  call    sqlite3StatusHighwater
0x18000b1fe  mov     ecx, r8d
0x18000b201  mov     edx, r8d
0x18000b204  call    sqlite3StatusUp
0x18000b209  jmp     loc_18000B171
```
