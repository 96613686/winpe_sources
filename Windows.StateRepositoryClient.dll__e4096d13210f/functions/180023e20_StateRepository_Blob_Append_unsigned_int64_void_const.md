# StateRepository::Blob::Append(unsigned __int64,void const *)

- ea: `0x180023e20`
- end: `0x180023ece`
- name: `?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z`
- size: `174`
- prototype: `__int64 __fastcall(StateRepository::Blob *__hidden this, unsigned __int64, const void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800254c8`
- `0x1800258d8`

## callees

- `0x1800075e4`
- `0x18000c58c`
- `0x180023e20`
- `0x180023f58`
- `0x180026690`

## string_xrefs

- `0x180023e41`: `onecore\base\appmodel\staterepository\dataaccesslayer\blob.cpp`
- `0x180023e6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\blob.cpp`
- `0x180023e96`: `onecore\base\appmodel\staterepository\dataaccesslayer\blob.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Blob::Append(StateRepository::Blob *this, unsigned __int64 a2, const void *Src)
{
  int v6; // eax
  unsigned int v7; // esi
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 && !Src )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\blob.cpp",
      (const char *)0x80070057LL,
      v9);
  v6 = StateRepository::Blob::GrowCapacity(this, a2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( a2 > *((_QWORD *)this + 2) - *((_QWORD *)this + 1) )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\blob.cpp",
        (const char *)0x8000FFFFLL,
        v9);
    memcpy_0((void *)(*(_QWORD *)this + *((_QWORD *)this + 1)), Src, a2);
    *((_QWORD *)this + 1) += a2;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\blob.cpp",
      (const char *)(unsigned int)v6,
      v9);
    return v7;
  }
}

```

## disassembly

```asm
0x180023e20  push    rbx
0x180023e22  push    rbp
0x180023e23  push    rsi
0x180023e24  push    rdi
0x180023e25  sub     rsp, 28h
0x180023e29  mov     rbp, r8
0x180023e2c  mov     rdi, rdx
0x180023e2f  mov     rbx, rcx
0x180023e32  test    rdx, rdx
0x180023e35  jz      short loc_180023E56
0x180023e37  test    r8, r8
0x180023e3a  jnz     short loc_180023E56
0x180023e3c  mov     rcx, [rsp+48h]; this
0x180023e41  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x180023e48  mov     r9d, 80070057h; char *
0x180023e4e  lea     edx, [rbp+29h]; void *
0x180023e51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023e56  mov     rdx, rdi; unsigned __int64
0x180023e59  mov     rcx, rbx; this
0x180023e5c  call    ?GrowCapacity@Blob@StateRepository@@QEAAJ_K@Z; StateRepository::Blob::GrowCapacity(unsigned __int64)
0x180023e61  mov     esi, eax
0x180023e63  test    eax, eax
0x180023e65  jns     short loc_180023E84
0x180023e67  mov     rcx, [rsp+48h]; this
0x180023e6c  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x180023e73  mov     r9d, eax; char *
0x180023e76  mov     edx, 2Bh ; '+'; void *
0x180023e7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e80  mov     eax, esi
0x180023e82  jmp     short loc_180023EC5
0x180023e84  mov     rax, [rbx+10h]
0x180023e88  sub     rax, [rbx+8]
0x180023e8c  cmp     rdi, rax
0x180023e8f  jbe     short loc_180023EAD
0x180023e91  mov     rcx, [rsp+48h]; this
0x180023e96  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x180023e9d  mov     r9d, 8000FFFFh; char *
0x180023ea3  mov     edx, 2Ch ; ','; void *
0x180023ea8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023ead  mov     rcx, [rbx+8]
0x180023eb1  mov     r8, rdi; Size
0x180023eb4  add     rcx, [rbx]; void *
0x180023eb7  mov     rdx, rbp; Src
0x180023eba  call    memcpy_0
0x180023ebf  add     [rbx+8], rdi
0x180023ec3  xor     eax, eax
0x180023ec5  add     rsp, 28h
0x180023ec9  pop     rdi
0x180023eca  pop     rsi
0x180023ecb  pop     rbp
0x180023ecc  pop     rbx
0x180023ecd  retn
```
