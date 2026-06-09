# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1800057e8`
- end: `0x18000585a`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005b50`

## callees

- `0x1800018dc`
- `0x1800057e8`
- `0x18000c990`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, word_18001129A, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800057e8  sub     rsp, 68h
0x1800057ec  mov     rax, cs:__security_cookie
0x1800057f3  xor     rax, rsp
0x1800057f6  mov     [rsp+68h+var_18], rax
0x1800057fb  mov     eax, [rcx]
0x1800057fd  mov     r8, rdx
0x180005800  cmp     eax, 5
0x180005803  jbe     short loc_180005848
0x180005805  mov     rdx, [rcx+18h]
0x180005809  mov     r9, 200000000000h
0x180005813  mov     rax, [rcx+10h]
0x180005817  test    r9, rax
0x18000581a  jz      short loc_180005848
0x18000581c  mov     rax, rdx
0x18000581f  and     rax, r9
0x180005822  cmp     rax, rdx
0x180005825  jnz     short loc_180005848
0x180005827  lea     rax, [rsp+68h+var_38]
0x18000582c  xor     r9d, r9d
0x18000582f  mov     [rsp+68h+var_40], rax
0x180005834  lea     rdx, word_18001129A
0x18000583b  mov     [rsp+68h+var_48], 2
0x180005843  call    _tlgWriteTransfer_EventWriteTransfer
0x180005848  mov     rcx, [rsp+68h+var_18]
0x18000584d  xor     rcx, rsp; StackCookie
0x180005850  call    __security_check_cookie
0x180005855  add     rsp, 68h
0x180005859  retn
```
