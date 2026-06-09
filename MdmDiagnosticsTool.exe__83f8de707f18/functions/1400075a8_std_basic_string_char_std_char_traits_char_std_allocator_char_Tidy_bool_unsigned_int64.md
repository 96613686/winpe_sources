# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x1400075a8`
- end: `0x140007608`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003370`
- `0x14000719c`
- `0x140007414`
- `0x140008694`
- `0x140009e86`
- `0x14000a23c`

## callees

- `0x140001e06`
- `0x1400075a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400075db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400075db`

## pseudocode

```c
void __fastcall std::string::_Tidy(void **a1, char a2, size_t a3)
{
  void *v5; // rsi

  if ( a2 && (unsigned __int64)a1[3] >= 0x10 )
  {
    v5 = *a1;
    if ( a3 )
      memcpy_0(a1, *a1, a3);
    operator delete(v5);
  }
  a1[3] = (void *)15;
  a1[2] = (void *)a3;
  *((_BYTE *)a1 + a3) = 0;
}

```

## disassembly

```asm
0x1400075a8  mov     [rsp+arg_0], rbx
0x1400075ad  mov     [rsp+arg_8], rsi
0x1400075b2  push    rdi
0x1400075b3  sub     rsp, 20h
0x1400075b7  mov     rdi, r8
0x1400075ba  mov     rbx, rcx
0x1400075bd  test    dl, dl
0x1400075bf  jz      short loc_1400075E7
0x1400075c1  cmp     qword ptr [rcx+18h], 10h
0x1400075c6  jb      short loc_1400075E7
0x1400075c8  mov     rsi, [rcx]
0x1400075cb  test    r8, r8
0x1400075ce  jz      short loc_1400075D8
0x1400075d0  mov     rdx, rsi; Src
0x1400075d3  call    memcpy_0
0x1400075d8  mov     rcx, rsi
0x1400075db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400075e2  nop     dword ptr [rax+rax+00h]
0x1400075e7  mov     rsi, [rsp+28h+arg_8]
0x1400075ec  mov     qword ptr [rbx+18h], 0Fh
0x1400075f4  mov     [rbx+10h], rdi
0x1400075f8  mov     byte ptr [rdi+rbx], 0
0x1400075fc  mov     rbx, [rsp+28h+arg_0]
0x140007601  add     rsp, 20h
0x140007605  pop     rdi
0x140007606  retn
```
