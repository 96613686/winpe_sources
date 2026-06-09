# _anonymous_namespace_::WriteDecimalToStream_unsigned_long_

- ea: `0x140029244`
- end: `0x1400292ae`
- name: `_anonymous_namespace_::WriteDecimalToStream_unsigned_long_`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029590`
- `0x140029fd0`

## callees

- `0x140002310`
- `0x140002e10`
- `0x140029244`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_unsigned_long_(__int64 a1, _DWORD *a2)
{
  int result; // eax
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  result = snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%lu", *a2);
  if ( (unsigned __int64)result <= 0xD )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x140029244  push    rbx
0x140029246  sub     rsp, 50h
0x14002924a  mov     rax, cs:__security_cookie
0x140029251  xor     rax, rsp
0x140029254  mov     [rsp+58h+var_18], rax
0x140029259  mov     eax, [rdx]
0x14002925b  lea     r9, aLu; "%lu"
0x140029262  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140029266  mov     [rsp+58h+var_38], eax
0x14002926a  mov     rbx, rcx
0x14002926d  lea     rcx, [rsp+58h+Buffer]; Buffer
0x140029272  lea     edx, [r8+0Eh]; BufferCount
0x140029276  call    _snprintf_s
0x14002927b  movsxd  rdx, eax
0x14002927e  cmp     rdx, 0Dh
0x140029282  ja      short loc_14002929B
0x140029284  mov     rax, [rbx]
0x140029287  lea     r8, [rsp+58h+Buffer]
0x14002928c  mov     rcx, rbx
0x14002928f  mov     rax, [rax+118h]
0x140029296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002929b  mov     rcx, [rsp+58h+var_18]
0x1400292a0  xor     rcx, rsp; StackCookie
0x1400292a3  call    __security_check_cookie
0x1400292a8  add     rsp, 50h
0x1400292ac  pop     rbx
0x1400292ad  retn
```
