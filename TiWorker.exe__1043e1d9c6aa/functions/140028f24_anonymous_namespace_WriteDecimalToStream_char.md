# _anonymous_namespace_::WriteDecimalToStream_char_

- ea: `0x140028f24`
- end: `0x140028f8f`
- name: `_anonymous_namespace_::WriteDecimalToStream_char_`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400294b0`
- `0x140029ef0`

## callees

- `0x140002310`
- `0x140002e10`
- `0x140028f24`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_char_(__int64 a1, char *a2)
{
  int result; // eax
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  result = snprintf_s(Buffer, 5u, 0xFFFFFFFFFFFFFFFFuLL, "%d", *a2);
  if ( (unsigned __int64)result <= 5 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x140028f24  push    rbx
0x140028f26  sub     rsp, 40h
0x140028f2a  mov     rax, cs:__security_cookie
0x140028f31  xor     rax, rsp
0x140028f34  mov     [rsp+48h+var_10], rax
0x140028f39  movsx   eax, byte ptr [rdx]
0x140028f3c  lea     r9, aD; "%d"
0x140028f43  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028f47  mov     [rsp+48h+var_28], eax
0x140028f4b  mov     rbx, rcx
0x140028f4e  lea     rcx, [rsp+48h+Buffer]; Buffer
0x140028f53  lea     edx, [r8+6]; BufferCount
0x140028f57  call    _snprintf_s
0x140028f5c  movsxd  rdx, eax
0x140028f5f  cmp     rdx, 5
0x140028f63  ja      short loc_140028F7C
0x140028f65  mov     rax, [rbx]
0x140028f68  lea     r8, [rsp+48h+Buffer]
0x140028f6d  mov     rcx, rbx
0x140028f70  mov     rax, [rax+118h]
0x140028f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028f7c  mov     rcx, [rsp+48h+var_10]
0x140028f81  xor     rcx, rsp; StackCookie
0x140028f84  call    __security_check_cookie
0x140028f89  add     rsp, 40h
0x140028f8d  pop     rbx
0x140028f8e  retn
```
