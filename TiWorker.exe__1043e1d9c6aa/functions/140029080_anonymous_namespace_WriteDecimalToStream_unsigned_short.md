# _anonymous_namespace_::WriteDecimalToStream_unsigned_short_

- ea: `0x140029080`
- end: `0x1400290eb`
- name: `_anonymous_namespace_::WriteDecimalToStream_unsigned_short_`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029510`
- `0x140029f50`

## callees

- `0x140002310`
- `0x140002e10`
- `0x140029080`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_unsigned_short_(__int64 a1, unsigned __int16 *a2)
{
  int result; // eax
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  result = snprintf_s(Buffer, 8u, 0xFFFFFFFFFFFFFFFFuLL, "%u", *a2);
  if ( (unsigned __int64)result <= 8 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x140029080  push    rbx
0x140029082  sub     rsp, 40h
0x140029086  mov     rax, cs:__security_cookie
0x14002908d  xor     rax, rsp
0x140029090  mov     [rsp+48h+var_10], rax
0x140029095  movzx   eax, word ptr [rdx]
0x140029098  lea     r9, aU; "%u"
0x14002909f  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400290a3  mov     [rsp+48h+var_28], eax
0x1400290a7  mov     rbx, rcx
0x1400290aa  lea     rcx, [rsp+48h+Buffer]; Buffer
0x1400290af  lea     edx, [r8+9]; BufferCount
0x1400290b3  call    _snprintf_s
0x1400290b8  movsxd  rdx, eax
0x1400290bb  cmp     rdx, 8
0x1400290bf  ja      short loc_1400290D8
0x1400290c1  mov     rax, [rbx]
0x1400290c4  lea     r8, [rsp+48h+Buffer]
0x1400290c9  mov     rcx, rbx
0x1400290cc  mov     rax, [rax+118h]
0x1400290d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400290d8  mov     rcx, [rsp+48h+var_10]
0x1400290dd  xor     rcx, rsp; StackCookie
0x1400290e0  call    __security_check_cookie
0x1400290e5  add     rsp, 40h
0x1400290e9  pop     rbx
0x1400290ea  retn
```
