# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180004748`
- end: `0x1800047ba`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800058f0`

## callees

- `0x180001a4c`
- `0x180002300`
- `0x180004748`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, &byte_1800150BF, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004748  sub     rsp, 68h
0x18000474c  mov     rax, cs:__security_cookie
0x180004753  xor     rax, rsp
0x180004756  mov     [rsp+68h+var_18], rax
0x18000475b  mov     eax, [rcx]
0x18000475d  mov     r8, rdx
0x180004760  cmp     eax, 5
0x180004763  jbe     short loc_1800047A8
0x180004765  mov     rdx, [rcx+18h]
0x180004769  mov     r9, 400000000000h
0x180004773  mov     rax, [rcx+10h]
0x180004777  test    r9, rax
0x18000477a  jz      short loc_1800047A8
0x18000477c  mov     rax, rdx
0x18000477f  and     rax, r9
0x180004782  cmp     rax, rdx
0x180004785  jnz     short loc_1800047A8
0x180004787  lea     rax, [rsp+68h+var_38]
0x18000478c  xor     r9d, r9d
0x18000478f  mov     [rsp+68h+var_40], rax
0x180004794  lea     rdx, byte_1800150BF
0x18000479b  mov     [rsp+68h+var_48], 2
0x1800047a3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800047a8  mov     rcx, [rsp+68h+var_18]
0x1800047ad  xor     rcx, rsp; StackCookie
0x1800047b0  call    __security_check_cookie
0x1800047b5  add     rsp, 68h
0x1800047b9  retn
```
