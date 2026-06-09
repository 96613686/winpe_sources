# std::_Move<HrtfDataDesc *,HrtfDataDesc *>(HrtfDataDesc *,HrtfDataDesc *,HrtfDataDesc *)

- ea: `0x180003f6c`
- end: `0x180004058`
- name: `??$_Move@PEAUHrtfDataDesc@@PEAU1@@std@@YAPEAUHrtfDataDesc@@PEAU1@00@Z`
- size: `236`
- prototype: `_DWORD *__fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800078e4`

## callees

- `0x180003f6c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003fb0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003fb0`
- `msvcrt!_aligned_free` at `0x180003ff3`
- `msvcrt!_aligned_free` at `0x180003ff3`

## pseudocode

```c
_DWORD *__fastcall std::_Move<HrtfDataDesc *,HrtfDataDesc *>(__int64 a1, __int64 a2, _DWORD *a3)
{
  _DWORD *v3; // r14
  __int64 v5; // rsi
  _QWORD *v6; // r15
  _DWORD *v7; // rdi
  _DWORD *v8; // rbx
  _QWORD *v9; // rbp

  v3 = a3;
  v5 = a1;
  if ( a1 != a2 )
  {
    v6 = (_QWORD *)(a1 + 8);
    v7 = a3 + 2;
    v8 = a3 + 8;
    do
    {
      *v3 = *(_DWORD *)v5;
      if ( v7 != (_DWORD *)v6 )
      {
        if ( *(_QWORD *)v7 )
        {
          operator delete(*(void **)v7);
          *(_QWORD *)v7 = 0;
          *((_QWORD *)v7 + 1) = 0;
          *((_QWORD *)v7 + 2) = 0;
        }
        *(_QWORD *)v7 = *v6;
        *((_QWORD *)v7 + 1) = v6[1];
        *((_QWORD *)v7 + 2) = v6[2];
        *v6 = 0;
        v6[1] = 0;
        v6[2] = 0;
      }
      v9 = (_QWORD *)(v5 + 32);
      if ( v8 != (_DWORD *)(v5 + 32) )
      {
        if ( *(_QWORD *)v8 )
        {
          _aligned_free(*(void **)v8);
          *(_QWORD *)v8 = 0;
          *((_QWORD *)v8 + 1) = 0;
          *((_QWORD *)v8 + 2) = 0;
        }
        *(_QWORD *)v8 = *v9;
        *((_QWORD *)v8 + 1) = *(_QWORD *)(v5 + 40);
        *((_QWORD *)v8 + 2) = *(_QWORD *)(v5 + 48);
        *v9 = 0;
        *(_QWORD *)(v5 + 40) = 0;
        *(_QWORD *)(v5 + 48) = 0;
      }
      v3 += 14;
      v5 += 56;
      v6 += 7;
      v7 += 14;
      v8 += 14;
    }
    while ( v5 != a2 );
  }
  return v3;
}

```

## disassembly

```asm
0x180003f6c  push    rbx
0x180003f6e  push    rbp
0x180003f6f  push    rsi
0x180003f70  push    rdi
0x180003f71  push    r12
0x180003f73  push    r13
0x180003f75  push    r14
0x180003f77  push    r15
0x180003f79  sub     rsp, 28h
0x180003f7d  mov     r14, r8
0x180003f80  mov     r12, rdx
0x180003f83  mov     rsi, rcx
0x180003f86  cmp     rcx, rdx
0x180003f89  jz      loc_180004044
0x180003f8f  lea     r15, [rcx+8]
0x180003f93  xor     r13d, r13d
0x180003f96  lea     rdi, [r8+8]
0x180003f9a  lea     rbx, [r8+20h]
0x180003f9e  mov     eax, [rsi]
0x180003fa0  mov     [r14], eax
0x180003fa3  cmp     rdi, r15
0x180003fa6  jz      short loc_180003FE2
0x180003fa8  mov     rcx, [rdi]
0x180003fab  test    rcx, rcx
0x180003fae  jz      short loc_180003FC1
0x180003fb0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003fb6  mov     [rdi], r13
0x180003fb9  mov     [rdi+8], r13
0x180003fbd  mov     [rdi+10h], r13
0x180003fc1  mov     rax, [r15]
0x180003fc4  mov     [rdi], rax
0x180003fc7  mov     rax, [r15+8]
0x180003fcb  mov     [rdi+8], rax
0x180003fcf  mov     rax, [r15+10h]
0x180003fd3  mov     [rdi+10h], rax
0x180003fd7  mov     [r15], r13
0x180003fda  mov     [r15+8], r13
0x180003fde  mov     [r15+10h], r13
0x180003fe2  lea     rbp, [rsi+20h]
0x180003fe6  cmp     rbx, rbp
0x180003fe9  jz      short loc_180004027
0x180003feb  mov     rcx, [rbx]; Block
0x180003fee  test    rcx, rcx
0x180003ff1  jz      short loc_180004004
0x180003ff3  call    cs:__imp__aligned_free
0x180003ff9  mov     [rbx], r13
0x180003ffc  mov     [rbx+8], r13
0x180004000  mov     [rbx+10h], r13
0x180004004  mov     rax, [rbp+0]
0x180004008  mov     [rbx], rax
0x18000400b  mov     rax, [rbp+8]
0x18000400f  mov     [rbx+8], rax
0x180004013  mov     rax, [rbp+10h]
0x180004017  mov     [rbx+10h], rax
0x18000401b  mov     [rbp+0], r13
0x18000401f  mov     [rbp+8], r13
0x180004023  mov     [rbp+10h], r13
0x180004027  add     r14, 38h ; '8'
0x18000402b  add     rsi, 38h ; '8'
0x18000402f  add     r15, 38h ; '8'
0x180004033  add     rdi, 38h ; '8'
0x180004037  add     rbx, 38h ; '8'
0x18000403b  cmp     rsi, r12
0x18000403e  jnz     loc_180003F9E
0x180004044  mov     rax, r14
0x180004047  add     rsp, 28h
0x18000404b  pop     r15
0x18000404d  pop     r14
0x18000404f  pop     r13
0x180004051  pop     r12
0x180004053  pop     rdi
0x180004054  pop     rsi
0x180004055  pop     rbp
0x180004056  pop     rbx
0x180004057  retn
```
