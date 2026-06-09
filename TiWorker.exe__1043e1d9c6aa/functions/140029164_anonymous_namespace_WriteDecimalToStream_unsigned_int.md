# _anonymous_namespace_::WriteDecimalToStream_unsigned_int_

- ea: `0x140029164`
- end: `0x1400291ce`
- name: `_anonymous_namespace_::WriteDecimalToStream_unsigned_int_`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029550`
- `0x140029f90`

## callees

- `0x140002310`
- `0x140002e10`
- `0x140029164`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_unsigned_int_(__int64 a1, _DWORD *a2)
{
  int result; // eax
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  result = snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%u", *a2);
  if ( (unsigned __int64)result <= 0xD )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x140029164  push    rbx
0x140029166  sub     rsp, 50h
0x14002916a  mov     rax, cs:__security_cookie
0x140029171  xor     rax, rsp
0x140029174  mov     [rsp+58h+var_18], rax
0x140029179  mov     eax, [rdx]
0x14002917b  lea     r9, aU; "%u"
0x140029182  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140029186  mov     [rsp+58h+var_38], eax
0x14002918a  mov     rbx, rcx
0x14002918d  lea     rcx, [rsp+58h+Buffer]; Buffer
0x140029192  lea     edx, [r8+0Eh]; BufferCount
0x140029196  call    _snprintf_s
0x14002919b  movsxd  rdx, eax
0x14002919e  cmp     rdx, 0Dh
0x1400291a2  ja      short loc_1400291BB
0x1400291a4  mov     rax, [rbx]
0x1400291a7  lea     r8, [rsp+58h+Buffer]
0x1400291ac  mov     rcx, rbx
0x1400291af  mov     rax, [rax+118h]
0x1400291b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400291bb  mov     rcx, [rsp+58h+var_18]
0x1400291c0  xor     rcx, rsp; StackCookie
0x1400291c3  call    __security_check_cookie
0x1400291c8  add     rsp, 50h
0x1400291cc  pop     rbx
0x1400291cd  retn
```
