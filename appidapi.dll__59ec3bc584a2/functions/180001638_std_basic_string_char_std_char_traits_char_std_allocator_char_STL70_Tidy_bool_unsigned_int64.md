# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Tidy(bool,unsigned __int64)

- ea: `0x180001638`
- end: `0x18000169c`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000115c`
- `0x1800012b8`
- `0x1800096e7`

## callees

- `0x180001098`
- `0x180001638`
- `0x180001f12`

## pseudocode

```c
void __fastcall std::string::_Tidy(__int64 a1, char a2, rsize_t a3)
{
  void **v5; // rcx
  void *v6; // rsi

  if ( a2 && *(_QWORD *)(a1 + 32) >= 0x10u )
  {
    v5 = (void **)(a1 + 8);
    v6 = *v5;
    if ( a3 )
      memcpy_s_0(v5, 0x10u, *v5, a3);
    operator delete(v6);
  }
  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = a3;
  *(_BYTE *)(a3 + a1 + 8) = 0;
}

```

## disassembly

```asm
0x180001638  mov     [rsp+arg_0], rbx
0x18000163d  mov     [rsp+arg_8], rsi
0x180001642  push    rdi
0x180001643  sub     rsp, 20h
0x180001647  mov     rdi, r8
0x18000164a  mov     rbx, rcx
0x18000164d  test    dl, dl
0x18000164f  jz      short loc_18000167B
0x180001651  mov     edx, 10h; DestinationSize
0x180001656  cmp     [rcx+20h], rdx
0x18000165a  jb      short loc_18000167B
0x18000165c  add     rcx, 8; Destination
0x180001660  mov     rsi, [rcx]
0x180001663  test    r8, r8
0x180001666  jz      short loc_180001673
0x180001668  mov     r9, r8; SourceSize
0x18000166b  mov     r8, rsi; Source
0x18000166e  call    memcpy_s_0
0x180001673  mov     rcx, rsi; Block
0x180001676  call    ??3@YAXPEAX@Z
0x18000167b  mov     rsi, [rsp+28h+arg_8]
0x180001680  mov     qword ptr [rbx+20h], 0Fh
0x180001688  mov     [rbx+18h], rdi
0x18000168c  mov     byte ptr [rdi+rbx+8], 0
0x180001691  mov     rbx, [rsp+28h+arg_0]
0x180001696  add     rsp, 20h
0x18000169a  pop     rdi
0x18000169b  retn
```
