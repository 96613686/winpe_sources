# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Become_small(void)

- ea: `0x1800222c4`
- end: `0x18002232c`
- name: `?_Become_small@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ`
- size: `104`
- prototype: `void __fastcall(const void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022590`
- `0x180023030`

## callees

- `0x180002cc0`
- `0x180008833`
- `0x1800222c4`

## pseudocode

```c
void __fastcall std::string::_Become_small(const void **a1)
{
  _BYTE *v1; // rbx
  _BYTE *v3; // rcx

  v1 = *a1;
  memcpy_0(a1, *a1, (size_t)a1[2] + 1);
  if ( (unsigned __int64)a1[3] + 1 < 0x1000 )
  {
    v3 = v1;
  }
  else
  {
    v3 = (_BYTE *)*((_QWORD *)v1 - 1);
    if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
      __fastfail(5u);
  }
  operator delete(v3);
  a1[3] = (const void *)15;
}

```

## disassembly

```asm
0x1800222c4  mov     [rsp+arg_0], rbx
0x1800222c9  push    rdi
0x1800222ca  sub     rsp, 20h
0x1800222ce  mov     rbx, [rcx]
0x1800222d1  mov     rdi, rcx
0x1800222d4  mov     r8, [rcx+10h]
0x1800222d8  mov     rdx, rbx; Src
0x1800222db  inc     r8; Size
0x1800222de  call    memcpy_0
0x1800222e3  mov     rdx, [rdi+18h]
0x1800222e7  inc     rdx; unsigned __int64
0x1800222ea  cmp     rdx, 1000h
0x1800222f1  jb      short loc_180022311
0x1800222f3  mov     rcx, [rbx-8]
0x1800222f7  sub     rbx, rcx
0x1800222fa  sub     rbx, 8
0x1800222fe  cmp     rbx, 1Fh
0x180022302  ja      short loc_18002230A
0x180022304  add     rdx, 27h ; '''
0x180022308  jmp     short loc_180022314
0x18002230a  mov     ecx, 5
0x18002230f  int     29h; Win8: RtlFailFast(ecx)
0x180022311  mov     rcx, rbx; void *
0x180022314  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022319  mov     rbx, [rsp+28h+arg_0]
0x18002231e  mov     qword ptr [rdi+18h], 0Fh
0x180022326  add     rsp, 20h
0x18002232a  pop     rdi
0x18002232b  retn
```
