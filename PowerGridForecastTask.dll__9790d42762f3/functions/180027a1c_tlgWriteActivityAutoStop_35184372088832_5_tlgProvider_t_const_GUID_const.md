# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180027a1c`
- end: `0x180027a8e`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027d38`

## callees

- `0x180001c7c`
- `0x180027a1c`
- `0x1800350e0`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_18003E319, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027a1c  sub     rsp, 68h
0x180027a20  mov     rax, cs:__security_cookie
0x180027a27  xor     rax, rsp
0x180027a2a  mov     [rsp+68h+var_18], rax
0x180027a2f  mov     eax, [rcx]
0x180027a31  mov     r8, rdx
0x180027a34  cmp     eax, 5
0x180027a37  jbe     short loc_180027A7C
0x180027a39  mov     rdx, [rcx+18h]
0x180027a3d  mov     r9, 200000000000h
0x180027a47  mov     rax, [rcx+10h]
0x180027a4b  test    r9, rax
0x180027a4e  jz      short loc_180027A7C
0x180027a50  mov     rax, rdx
0x180027a53  and     rax, r9
0x180027a56  cmp     rax, rdx
0x180027a59  jnz     short loc_180027A7C
0x180027a5b  lea     rax, [rsp+68h+var_38]
0x180027a60  xor     r9d, r9d
0x180027a63  mov     [rsp+68h+var_40], rax
0x180027a68  lea     rdx, byte_18003E319
0x180027a6f  mov     [rsp+68h+var_48], 2
0x180027a77  call    _tlgWriteTransfer_EventWriteTransfer
0x180027a7c  mov     rcx, [rsp+68h+var_18]
0x180027a81  xor     rcx, rsp; StackCookie
0x180027a84  call    __security_check_cookie
0x180027a89  add     rsp, 68h
0x180027a8d  retn
```
