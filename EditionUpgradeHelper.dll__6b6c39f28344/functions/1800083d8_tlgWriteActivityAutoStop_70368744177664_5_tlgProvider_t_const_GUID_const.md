# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1800083d8`
- end: `0x18000844a`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026940`

## callees

- `0x18000108c`
- `0x1800018e0`
- `0x1800083d8`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x400000000000LL) != 0 )
    {
      result = v4 & 0x400000000000LL;
      if ( (v4 & 0x400000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_18002C2E9, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800083d8  sub     rsp, 68h
0x1800083dc  mov     rax, cs:__security_cookie
0x1800083e3  xor     rax, rsp
0x1800083e6  mov     [rsp+68h+var_18], rax
0x1800083eb  mov     eax, [rcx]
0x1800083ed  mov     r8, rdx
0x1800083f0  cmp     eax, 5
0x1800083f3  jbe     short loc_180008438
0x1800083f5  mov     rdx, [rcx+18h]
0x1800083f9  mov     r9, 400000000000h
0x180008403  mov     rax, [rcx+10h]
0x180008407  test    r9, rax
0x18000840a  jz      short loc_180008438
0x18000840c  mov     rax, rdx
0x18000840f  and     rax, r9
0x180008412  cmp     rax, rdx
0x180008415  jnz     short loc_180008438
0x180008417  lea     rax, [rsp+68h+var_38]
0x18000841c  xor     r9d, r9d
0x18000841f  mov     [rsp+68h+var_40], rax
0x180008424  lea     rdx, byte_18002C2E9
0x18000842b  mov     [rsp+68h+var_48], 2
0x180008433  call    _tlgWriteTransfer_EventWriteTransfer
0x180008438  mov     rcx, [rsp+68h+var_18]
0x18000843d  xor     rcx, rsp; StackCookie
0x180008440  call    __security_check_cookie
0x180008445  add     rsp, 68h
0x180008449  retn
```
