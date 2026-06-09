# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x1400071a4`
- end: `0x1400071fd`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `89`
- prototype: `void __fastcall(void **, char, size_t)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000332c`
- `0x140006da0`
- `0x140007018`
- `0x140008130`
- `0x140009856`
- `0x140009c07`

## callees

- `0x140001dd6`
- `0x1400071a4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400071d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400071d7`

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
0x1400071a4  mov     [rsp+arg_0], rbx
0x1400071a9  mov     [rsp+arg_8], rsi
0x1400071ae  push    rdi
0x1400071af  sub     rsp, 20h
0x1400071b3  mov     rdi, r8
0x1400071b6  mov     rbx, rcx
0x1400071b9  test    dl, dl
0x1400071bb  jz      short loc_1400071DD
0x1400071bd  cmp     qword ptr [rcx+18h], 10h
0x1400071c2  jb      short loc_1400071DD
0x1400071c4  mov     rsi, [rcx]
0x1400071c7  test    r8, r8
0x1400071ca  jz      short loc_1400071D4
0x1400071cc  mov     rdx, rsi; Src
0x1400071cf  call    memcpy_0
0x1400071d4  mov     rcx, rsi
0x1400071d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400071dd  mov     rsi, [rsp+28h+arg_8]
0x1400071e2  mov     qword ptr [rbx+18h], 0Fh
0x1400071ea  mov     [rbx+10h], rdi
0x1400071ee  mov     byte ptr [rdi+rbx], 0
0x1400071f2  mov     rbx, [rsp+28h+arg_0]
0x1400071f7  add     rsp, 20h
0x1400071fb  pop     rdi
0x1400071fc  retn
```
