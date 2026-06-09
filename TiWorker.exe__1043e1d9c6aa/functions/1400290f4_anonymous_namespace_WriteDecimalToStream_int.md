# _anonymous_namespace_::WriteDecimalToStream_int_

- ea: `0x1400290f4`
- end: `0x14002915e`
- name: `_anonymous_namespace_::WriteDecimalToStream_int_`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029530`
- `0x140029f70`

## callees

- `0x140002310`
- `0x140002e10`
- `0x1400290f4`
- `0x14002b010`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteDecimalToStream_int_(__int64 a1, _DWORD *a2)
{
  int result; // eax
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  result = snprintf_s(Buffer, 0xDu, 0xFFFFFFFFFFFFFFFFuLL, "%d", *a2);
  if ( (unsigned __int64)result <= 0xD )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)a1 + 280LL))(a1, result, Buffer);
  return result;
}

```

## disassembly

```asm
0x1400290f4  push    rbx
0x1400290f6  sub     rsp, 50h
0x1400290fa  mov     rax, cs:__security_cookie
0x140029101  xor     rax, rsp
0x140029104  mov     [rsp+58h+var_18], rax
0x140029109  mov     eax, [rdx]
0x14002910b  lea     r9, aD; "%d"
0x140029112  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140029116  mov     [rsp+58h+var_38], eax
0x14002911a  mov     rbx, rcx
0x14002911d  lea     rcx, [rsp+58h+Buffer]; Buffer
0x140029122  lea     edx, [r8+0Eh]; BufferCount
0x140029126  call    _snprintf_s
0x14002912b  movsxd  rdx, eax
0x14002912e  cmp     rdx, 0Dh
0x140029132  ja      short loc_14002914B
0x140029134  mov     rax, [rbx]
0x140029137  lea     r8, [rsp+58h+Buffer]
0x14002913c  mov     rcx, rbx
0x14002913f  mov     rax, [rax+118h]
0x140029146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002914b  mov     rcx, [rsp+58h+var_18]
0x140029150  xor     rcx, rsp; StackCookie
0x140029153  call    __security_check_cookie
0x140029158  add     rsp, 50h
0x14002915c  pop     rbx
0x14002915d  retn
```
