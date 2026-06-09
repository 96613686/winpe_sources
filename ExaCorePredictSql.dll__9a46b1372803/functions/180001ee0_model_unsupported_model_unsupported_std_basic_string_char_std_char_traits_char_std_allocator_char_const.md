# model_unsupported::model_unsupported(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180001ee0`
- end: `0x180001f35`
- name: `??0model_unsupported@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001ee0`

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x180001f1c`
- `VCRUNTIME140!__std_exception_copy` at `0x180001f1c`

## pseudocode

```c
_QWORD *__fastcall model_unsupported::model_unsupported(_QWORD *a1, _QWORD *a2)
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
  *a1 = &model_unsupported::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180001ee0  push    rbx
0x180001ee2  sub     rsp, 30h
0x180001ee6  cmp     qword ptr [rdx+18h], 10h
0x180001eeb  mov     rax, rdx
0x180001eee  mov     rbx, rcx
0x180001ef1  jb      short loc_180001EF6
0x180001ef3  mov     rax, [rdx]
0x180001ef6  lea     rdx, [rbx+8]
0x180001efa  mov     [rsp+38h+var_18], rax
0x180001eff  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180001f06  mov     [rsp+38h+var_10], 1
0x180001f0b  mov     [rbx], rcx
0x180001f0e  xor     ecx, ecx
0x180001f10  mov     [rdx], rcx
0x180001f13  mov     [rdx+8], rcx
0x180001f17  lea     rcx, [rsp+38h+var_18]
0x180001f1c  call    cs:__imp___std_exception_copy
0x180001f22  lea     rax, ??_7model_unsupported@@6B@; const model_unsupported::`vftable'
0x180001f29  mov     [rbx], rax
0x180001f2c  mov     rax, rbx
0x180001f2f  add     rsp, 30h
0x180001f33  pop     rbx
0x180001f34  retn
```
