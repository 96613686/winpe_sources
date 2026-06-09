# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000ec9c`
- end: `0x18000ed0e`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022c90`

## callees

- `0x180001008`
- `0x180001ac0`
- `0x18000ec9c`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_18002B09B, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ec9c  sub     rsp, 68h
0x18000eca0  mov     rax, cs:__security_cookie
0x18000eca7  xor     rax, rsp
0x18000ecaa  mov     [rsp+68h+var_18], rax
0x18000ecaf  mov     eax, [rcx]
0x18000ecb1  mov     r8, rdx
0x18000ecb4  cmp     eax, 5
0x18000ecb7  jbe     short loc_18000ECFC
0x18000ecb9  mov     rdx, [rcx+18h]
0x18000ecbd  mov     r9, 400000000000h
0x18000ecc7  mov     rax, [rcx+10h]
0x18000eccb  test    r9, rax
0x18000ecce  jz      short loc_18000ECFC
0x18000ecd0  mov     rax, rdx
0x18000ecd3  and     rax, r9
0x18000ecd6  cmp     rax, rdx
0x18000ecd9  jnz     short loc_18000ECFC
0x18000ecdb  lea     rax, [rsp+68h+var_38]
0x18000ece0  xor     r9d, r9d
0x18000ece3  mov     [rsp+68h+var_40], rax
0x18000ece8  lea     rdx, byte_18002B09B
0x18000ecef  mov     [rsp+68h+var_48], 2
0x18000ecf7  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ecfc  mov     rcx, [rsp+68h+var_18]
0x18000ed01  xor     rcx, rsp; StackCookie
0x18000ed04  call    __security_check_cookie
0x18000ed09  add     rsp, 68h
0x18000ed0d  retn
```
