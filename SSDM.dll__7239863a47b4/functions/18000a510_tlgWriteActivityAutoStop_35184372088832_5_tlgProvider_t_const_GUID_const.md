# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000a510`
- end: `0x18000a582`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a5fc`

## callees

- `0x18000163c`
- `0x18000a510`
- `0x18000e990`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x200000000000LL) != 0 )
    {
      result = v4 & 0x200000000000LL;
      if ( (v4 & 0x200000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, &word_180017A6E, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a510  sub     rsp, 68h
0x18000a514  mov     rax, cs:__security_cookie
0x18000a51b  xor     rax, rsp
0x18000a51e  mov     [rsp+68h+var_18], rax
0x18000a523  mov     eax, [rcx]
0x18000a525  mov     r8, rdx
0x18000a528  cmp     eax, 5
0x18000a52b  jbe     short loc_18000A570
0x18000a52d  mov     rdx, [rcx+18h]
0x18000a531  mov     r9, 200000000000h
0x18000a53b  mov     rax, [rcx+10h]
0x18000a53f  test    r9, rax
0x18000a542  jz      short loc_18000A570
0x18000a544  mov     rax, rdx
0x18000a547  and     rax, r9
0x18000a54a  cmp     rax, rdx
0x18000a54d  jnz     short loc_18000A570
0x18000a54f  lea     rax, [rsp+68h+var_38]
0x18000a554  xor     r9d, r9d
0x18000a557  mov     [rsp+68h+var_40], rax
0x18000a55c  lea     rdx, word_180017A6E
0x18000a563  mov     [rsp+68h+var_48], 2
0x18000a56b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a570  mov     rcx, [rsp+68h+var_18]
0x18000a575  xor     rcx, rsp; StackCookie
0x18000a578  call    __security_check_cookie
0x18000a57d  add     rsp, 68h
0x18000a581  retn
```
