# _anonymous_namespace_::WriteDecimalToStream_unsigned___int64_

- ea: `0x140029328`
- end: `0x140029394`
- name: `_anonymous_namespace_::WriteDecimalToStream_unsigned___int64_`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029ca0`
- `0x14002a010`

## callees

- `0x140002310`
- `0x140002e10`
- `0x140029328`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_unsigned___int64_(__int64 a1, _QWORD *a2)
{
  int result; // eax
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  result = snprintf_s(Buffer, 0x18u, 0xFFFFFFFFFFFFFFFFuLL, "%I64u", *a2);
  if ( (unsigned __int64)result <= 0x18 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x140029328  push    rbx
0x14002932a  sub     rsp, 50h
0x14002932e  mov     rax, cs:__security_cookie
0x140029335  xor     rax, rsp
0x140029338  mov     [rsp+58h+var_10], rax
0x14002933d  mov     rax, [rdx]
0x140029340  lea     r9, aI64u; "%I64u"
0x140029347  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002934b  mov     [rsp+58h+var_38], rax
0x140029350  mov     rbx, rcx
0x140029353  lea     rcx, [rsp+58h+Buffer]; Buffer
0x140029358  lea     edx, [r8+19h]; BufferCount
0x14002935c  call    _snprintf_s
0x140029361  movsxd  rdx, eax
0x140029364  cmp     rdx, 18h
0x140029368  ja      short loc_140029381
0x14002936a  mov     rax, [rbx]
0x14002936d  lea     r8, [rsp+58h+Buffer]
0x140029372  mov     rcx, rbx
0x140029375  mov     rax, [rax+118h]
0x14002937c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029381  mov     rcx, [rsp+58h+var_10]
0x140029386  xor     rcx, rsp; StackCookie
0x140029389  call    __security_check_cookie
0x14002938e  add     rsp, 50h
0x140029392  pop     rbx
0x140029393  retn
```
