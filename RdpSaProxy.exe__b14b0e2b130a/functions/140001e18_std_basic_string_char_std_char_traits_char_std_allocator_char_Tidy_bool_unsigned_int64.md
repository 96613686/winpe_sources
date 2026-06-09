# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x140001e18`
- end: `0x140001e70`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `88`
- prototype: `void __fastcall(void **, char, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000587a`

## callees

- `0x140001531`
- `0x140001e18`
- `0x140002516`

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
0x140001e18  mov     [rsp+arg_0], rbx
0x140001e1d  mov     [rsp+arg_8], rsi
0x140001e22  push    rdi
0x140001e23  sub     rsp, 20h
0x140001e27  mov     rdi, r8
0x140001e2a  mov     rbx, rcx
0x140001e2d  test    dl, dl
0x140001e2f  jz      short loc_140001E50
0x140001e31  cmp     qword ptr [rcx+18h], 10h
0x140001e36  jb      short loc_140001E50
0x140001e38  mov     rsi, [rcx]
0x140001e3b  test    r8, r8
0x140001e3e  jz      short loc_140001E48
0x140001e40  mov     rdx, rsi; Src
0x140001e43  call    memcpy_0
0x140001e48  mov     rcx, rsi; void *
0x140001e4b  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x140001e50  mov     rsi, [rsp+28h+arg_8]
0x140001e55  mov     qword ptr [rbx+18h], 0Fh
0x140001e5d  mov     [rbx+10h], rdi
0x140001e61  mov     byte ptr [rdi+rbx], 0
0x140001e65  mov     rbx, [rsp+28h+arg_0]
0x140001e6a  add     rsp, 20h
0x140001e6e  pop     rdi
0x140001e6f  retn
```
