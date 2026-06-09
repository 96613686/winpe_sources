# bad_model::bad_model(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180001d50`
- end: `0x180001da5`
- name: `??0bad_model@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a00`

## callees

- `0x180001d50`

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180001d8c`
- `VCRUNTIME140!__std_exception_copy` at `0x180001d8c`

## pseudocode

```c
_QWORD *__fastcall bad_model::bad_model(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rax
  _QWORD *v5; // [rsp+20h] [rbp-18h] BYREF
  char v6; // [rsp+28h] [rbp-10h]

  v2 = a2;
  if ( a2[3] >= 0x10u )
    v2 = (_QWORD *)*a2;
  v5 = v2;
  v6 = 1;
  *a1 = &std::exception::`vftable';
  a1[1] = 0;
  a1[2] = 0;
  __std_exception_copy(&v5);
  *a1 = &bad_model::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180001d50  push    rbx
0x180001d52  sub     rsp, 30h
0x180001d56  cmp     qword ptr [rdx+18h], 10h
0x180001d5b  mov     rax, rdx
0x180001d5e  mov     rbx, rcx
0x180001d61  jb      short loc_180001D66
0x180001d63  mov     rax, [rdx]
0x180001d66  lea     rdx, [rbx+8]
0x180001d6a  mov     [rsp+38h+var_18], rax
0x180001d6f  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180001d76  mov     [rsp+38h+var_10], 1
0x180001d7b  mov     [rbx], rcx
0x180001d7e  xor     ecx, ecx
0x180001d80  mov     [rdx], rcx
0x180001d83  mov     [rdx+8], rcx
0x180001d87  lea     rcx, [rsp+38h+var_18]
0x180001d8c  call    cs:__imp___std_exception_copy
0x180001d92  lea     rax, ??_7bad_model@@6B@; const bad_model::`vftable'
0x180001d99  mov     [rbx], rax
0x180001d9c  mov     rax, rbx
0x180001d9f  add     rsp, 30h
0x180001da3  pop     rbx
0x180001da4  retn
```
