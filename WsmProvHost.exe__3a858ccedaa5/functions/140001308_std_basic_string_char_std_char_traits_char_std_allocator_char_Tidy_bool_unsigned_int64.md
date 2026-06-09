# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x140001308`
- end: `0x140001360`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `88`
- prototype: `void __fastcall(void **, char, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140004454`

## callees

- `0x140001308`
- `0x140001eb6`
- `0x140002d64`

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
0x140001308  mov     [rsp+arg_0], rbx
0x14000130d  mov     [rsp+arg_8], rsi
0x140001312  push    rdi
0x140001313  sub     rsp, 20h
0x140001317  mov     rdi, r8
0x14000131a  mov     rbx, rcx
0x14000131d  test    dl, dl
0x14000131f  jz      short loc_140001340
0x140001321  cmp     qword ptr [rcx+18h], 10h
0x140001326  jb      short loc_140001340
0x140001328  mov     rsi, [rcx]
0x14000132b  test    r8, r8
0x14000132e  jz      short loc_140001338
0x140001330  mov     rdx, rsi; Src
0x140001333  call    memcpy_0
0x140001338  mov     rcx, rsi; void *
0x14000133b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001340  mov     rsi, [rsp+28h+arg_8]
0x140001345  mov     qword ptr [rbx+18h], 0Fh
0x14000134d  mov     [rbx+10h], rdi
0x140001351  mov     byte ptr [rdi+rbx], 0
0x140001355  mov     rbx, [rsp+28h+arg_0]
0x14000135a  add     rsp, 20h
0x14000135e  pop     rdi
0x14000135f  retn
```
