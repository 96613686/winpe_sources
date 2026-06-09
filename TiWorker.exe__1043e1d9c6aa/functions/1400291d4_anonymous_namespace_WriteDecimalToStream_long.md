# _anonymous_namespace_::WriteDecimalToStream_long_

- ea: `0x1400291d4`
- end: `0x14002923e`
- name: `_anonymous_namespace_::WriteDecimalToStream_long_`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029570`
- `0x140029fb0`

## callees

- `0x140002310`
- `0x140002e10`
- `0x1400291d4`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_long_(__int64 a1, _DWORD *a2)
{
  int result; // eax
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  result = snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%ld", *a2);
  if ( (unsigned __int64)result <= 0xD )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x1400291d4  push    rbx
0x1400291d6  sub     rsp, 50h
0x1400291da  mov     rax, cs:__security_cookie
0x1400291e1  xor     rax, rsp
0x1400291e4  mov     [rsp+58h+var_18], rax
0x1400291e9  mov     eax, [rdx]
0x1400291eb  lea     r9, aLd; "%ld"
0x1400291f2  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400291f6  mov     [rsp+58h+var_38], eax
0x1400291fa  mov     rbx, rcx
0x1400291fd  lea     rcx, [rsp+58h+Buffer]; Buffer
0x140029202  lea     edx, [r8+0Eh]; BufferCount
0x140029206  call    _snprintf_s
0x14002920b  movsxd  rdx, eax
0x14002920e  cmp     rdx, 0Dh
0x140029212  ja      short loc_14002922B
0x140029214  mov     rax, [rbx]
0x140029217  lea     r8, [rsp+58h+Buffer]
0x14002921c  mov     rcx, rbx
0x14002921f  mov     rax, [rax+118h]
0x140029226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002922b  mov     rcx, [rsp+58h+var_18]
0x140029230  xor     rcx, rsp; StackCookie
0x140029233  call    __security_check_cookie
0x140029238  add     rsp, 50h
0x14002923c  pop     rbx
0x14002923d  retn
```
