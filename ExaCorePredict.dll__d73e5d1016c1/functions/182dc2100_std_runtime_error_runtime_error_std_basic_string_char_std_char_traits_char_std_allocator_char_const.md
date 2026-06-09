# std::runtime_error::runtime_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x182dc2100`
- end: `0x182dc2171`
- name: `??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `113`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x182dc2020`
- `0x182dc2090`
- `0x182dc3080`
- `0x182dc3140`
- `0x182dc3510`
- `0x182dc8bd0`
- `0x182dc9100`
- `0x1832c3040`
- `0x1832c3230`
- `0x1832c3370`
- `0x1832c3410`
- `0x1832c4da0`
- `0x1832c5f90`
- `0x1832c66f0`
- `0x1832c7b20`
- `0x1832c7fe0`
- `0x1832cdcd0`

## callees

- `0x182dc2100`
- `0x1832ce3b0`

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x182dc214b`
- `VCRUNTIME140!__std_exception_copy` at `0x182dc214b`

## pseudocode

```c
_QWORD *__fastcall std::runtime_error::runtime_error(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rax
  _QWORD *v5; // [rsp+20h] [rbp-28h] BYREF
  char v6; // [rsp+28h] [rbp-20h]

  v2 = a2;
  if ( a2[3] >= 0x10u )
    v2 = (_QWORD *)*a2;
  v5 = v2;
  v6 = 1;
  *a1 = &std::exception::`vftable';
  a1[1] = 0;
  a1[2] = 0;
  __std_exception_copy(&v5);
  *a1 = &std::runtime_error::`vftable';
  return a1;
}

```

## disassembly

```asm
0x182dc2100  push    rbx
0x182dc2102  sub     rsp, 40h
0x182dc2106  mov     rax, cs:__security_cookie
0x182dc210d  xor     rax, rsp
0x182dc2110  mov     [rsp+48h+var_18], rax
0x182dc2115  cmp     qword ptr [rdx+18h], 10h
0x182dc211a  mov     rax, rdx
0x182dc211d  mov     rbx, rcx
0x182dc2120  jb      short loc_182DC2125
0x182dc2122  mov     rax, [rdx]
0x182dc2125  lea     rdx, [rbx+8]
0x182dc2129  mov     [rsp+48h+var_28], rax
0x182dc212e  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x182dc2135  mov     [rsp+48h+var_20], 1
0x182dc213a  mov     [rbx], rcx
0x182dc213d  xor     ecx, ecx
0x182dc213f  mov     [rdx], rcx
0x182dc2142  mov     [rdx+8], rcx
0x182dc2146  lea     rcx, [rsp+48h+var_28]
0x182dc214b  call    cs:__imp___std_exception_copy
0x182dc2151  lea     rax, ??_7runtime_error@std@@6B@; const std::runtime_error::`vftable'
0x182dc2158  mov     [rbx], rax
0x182dc215b  mov     rax, rbx
0x182dc215e  mov     rcx, [rsp+48h+var_18]
0x182dc2163  xor     rcx, rsp; StackCookie
0x182dc2166  call    __security_check_cookie
0x182dc216b  add     rsp, 40h
0x182dc216f  pop     rbx
0x182dc2170  retn
```
