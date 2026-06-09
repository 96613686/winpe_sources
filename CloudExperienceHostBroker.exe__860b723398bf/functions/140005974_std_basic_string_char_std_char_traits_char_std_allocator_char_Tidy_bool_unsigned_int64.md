# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x140005974`
- end: `0x1400059cd`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `89`
- prototype: `void __fastcall(void **, char, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400057b0`
- `0x1400058bc`
- `0x140009920`

## callees

- `0x140002226`
- `0x140005974`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400059a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400059a7`

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
0x140005974  mov     [rsp+arg_0], rbx
0x140005979  mov     [rsp+arg_8], rsi
0x14000597e  push    rdi
0x14000597f  sub     rsp, 20h
0x140005983  mov     rdi, r8
0x140005986  mov     rbx, rcx
0x140005989  test    dl, dl
0x14000598b  jz      short loc_1400059AD
0x14000598d  cmp     qword ptr [rcx+18h], 10h
0x140005992  jb      short loc_1400059AD
0x140005994  mov     rsi, [rcx]
0x140005997  test    r8, r8
0x14000599a  jz      short loc_1400059A4
0x14000599c  mov     rdx, rsi; Src
0x14000599f  call    memcpy_0
0x1400059a4  mov     rcx, rsi
0x1400059a7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400059ad  mov     rsi, [rsp+28h+arg_8]
0x1400059b2  mov     qword ptr [rbx+18h], 0Fh
0x1400059ba  mov     [rbx+10h], rdi
0x1400059be  mov     byte ptr [rdi+rbx], 0
0x1400059c2  mov     rbx, [rsp+28h+arg_0]
0x1400059c7  add     rsp, 20h
0x1400059cb  pop     rdi
0x1400059cc  retn
```
