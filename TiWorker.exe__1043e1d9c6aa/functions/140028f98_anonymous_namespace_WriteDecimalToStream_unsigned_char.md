# _anonymous_namespace_::WriteDecimalToStream_unsigned_char_

- ea: `0x140028f98`
- end: `0x140029003`
- name: `_anonymous_namespace_::WriteDecimalToStream_unsigned_char_`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400294d0`
- `0x140029f10`

## callees

- `0x140002310`
- `0x140002e10`
- `0x140028f98`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_unsigned_char_(__int64 a1, unsigned __int8 *a2)
{
  int result; // eax
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  result = snprintf_s(Buffer, 5u, 0xFFFFFFFFFFFFFFFFuLL, "%u", *a2);
  if ( (unsigned __int64)result <= 5 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x140028f98  push    rbx
0x140028f9a  sub     rsp, 40h
0x140028f9e  mov     rax, cs:__security_cookie
0x140028fa5  xor     rax, rsp
0x140028fa8  mov     [rsp+48h+var_10], rax
0x140028fad  movzx   eax, byte ptr [rdx]
0x140028fb0  lea     r9, aU; "%u"
0x140028fb7  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140028fbb  mov     [rsp+48h+var_28], eax
0x140028fbf  mov     rbx, rcx
0x140028fc2  lea     rcx, [rsp+48h+Buffer]; Buffer
0x140028fc7  lea     edx, [r8+6]; BufferCount
0x140028fcb  call    _snprintf_s
0x140028fd0  movsxd  rdx, eax
0x140028fd3  cmp     rdx, 5
0x140028fd7  ja      short loc_140028FF0
0x140028fd9  mov     rax, [rbx]
0x140028fdc  lea     r8, [rsp+48h+Buffer]
0x140028fe1  mov     rcx, rbx
0x140028fe4  mov     rax, [rax+118h]
0x140028feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028ff0  mov     rcx, [rsp+48h+var_10]
0x140028ff5  xor     rcx, rsp; StackCookie
0x140028ff8  call    __security_check_cookie
0x140028ffd  add     rsp, 40h
0x140029001  pop     rbx
0x140029002  retn
```
