# _anonymous_namespace_::WriteDecimalToStream_short_

- ea: `0x14002900c`
- end: `0x140029077`
- name: `_anonymous_namespace_::WriteDecimalToStream_short_`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400294f0`
- `0x140029f30`

## callees

- `0x140002310`
- `0x140002e10`
- `0x14002900c`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_short_(__int64 a1, __int16 *a2)
{
  int result; // eax
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  result = snprintf_s(Buffer, 8u, 0xFFFFFFFFFFFFFFFFuLL, "%d", *a2);
  if ( (unsigned __int64)result <= 8 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x14002900c  push    rbx
0x14002900e  sub     rsp, 40h
0x140029012  mov     rax, cs:__security_cookie
0x140029019  xor     rax, rsp
0x14002901c  mov     [rsp+48h+var_10], rax
0x140029021  movsx   eax, word ptr [rdx]
0x140029024  lea     r9, aD; "%d"
0x14002902b  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002902f  mov     [rsp+48h+var_28], eax
0x140029033  mov     rbx, rcx
0x140029036  lea     rcx, [rsp+48h+Buffer]; Buffer
0x14002903b  lea     edx, [r8+9]; BufferCount
0x14002903f  call    _snprintf_s
0x140029044  movsxd  rdx, eax
0x140029047  cmp     rdx, 8
0x14002904b  ja      short loc_140029064
0x14002904d  mov     rax, [rbx]
0x140029050  lea     r8, [rsp+48h+Buffer]
0x140029055  mov     rcx, rbx
0x140029058  mov     rax, [rax+118h]
0x14002905f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029064  mov     rcx, [rsp+48h+var_10]
0x140029069  xor     rcx, rsp; StackCookie
0x14002906c  call    __security_check_cookie
0x140029071  add     rsp, 40h
0x140029075  pop     rbx
0x140029076  retn
```
