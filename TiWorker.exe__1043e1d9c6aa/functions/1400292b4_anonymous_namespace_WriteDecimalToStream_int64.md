# _anonymous_namespace_::WriteDecimalToStream___int64_

- ea: `0x1400292b4`
- end: `0x140029320`
- name: `_anonymous_namespace_::WriteDecimalToStream___int64_`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029c80`
- `0x140029ff0`

## callees

- `0x140002310`
- `0x140002e10`
- `0x1400292b4`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream___int64_(__int64 a1, _QWORD *a2)
{
  int result; // eax
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  result = snprintf_s(Buffer, 0x18u, 0xFFFFFFFFFFFFFFFFuLL, "%I64d", *a2);
  if ( (unsigned __int64)result <= 0x18 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x1400292b4  push    rbx
0x1400292b6  sub     rsp, 50h
0x1400292ba  mov     rax, cs:__security_cookie
0x1400292c1  xor     rax, rsp
0x1400292c4  mov     [rsp+58h+var_10], rax
0x1400292c9  mov     rax, [rdx]
0x1400292cc  lea     r9, aI64d; "%I64d"
0x1400292d3  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400292d7  mov     [rsp+58h+var_38], rax
0x1400292dc  mov     rbx, rcx
0x1400292df  lea     rcx, [rsp+58h+Buffer]; Buffer
0x1400292e4  lea     edx, [r8+19h]; BufferCount
0x1400292e8  call    _snprintf_s
0x1400292ed  movsxd  rdx, eax
0x1400292f0  cmp     rdx, 18h
0x1400292f4  ja      short loc_14002930D
0x1400292f6  mov     rax, [rbx]
0x1400292f9  lea     r8, [rsp+58h+Buffer]
0x1400292fe  mov     rcx, rbx
0x140029301  mov     rax, [rax+118h]
0x140029308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002930d  mov     rcx, [rsp+58h+var_10]
0x140029312  xor     rcx, rsp; StackCookie
0x140029315  call    __security_check_cookie
0x14002931a  add     rsp, 50h
0x14002931e  pop     rbx
0x14002931f  retn
```
