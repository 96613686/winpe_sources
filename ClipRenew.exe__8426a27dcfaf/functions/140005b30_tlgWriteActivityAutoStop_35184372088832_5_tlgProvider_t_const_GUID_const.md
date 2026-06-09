# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140005b30`
- end: `0x140005ba2`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013730`

## callees

- `0x140001498`
- `0x140005b30`
- `0x1400134a0`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_140016DFB, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140005b30  sub     rsp, 68h
0x140005b34  mov     rax, cs:__security_cookie
0x140005b3b  xor     rax, rsp
0x140005b3e  mov     [rsp+68h+var_18], rax
0x140005b43  mov     eax, [rcx]
0x140005b45  mov     r8, rdx
0x140005b48  cmp     eax, 5
0x140005b4b  jbe     short loc_140005B90
0x140005b4d  mov     rdx, [rcx+18h]
0x140005b51  mov     r9, 200000000000h
0x140005b5b  mov     rax, [rcx+10h]
0x140005b5f  test    r9, rax
0x140005b62  jz      short loc_140005B90
0x140005b64  mov     rax, rdx
0x140005b67  and     rax, r9
0x140005b6a  cmp     rax, rdx
0x140005b6d  jnz     short loc_140005B90
0x140005b6f  lea     rax, [rsp+68h+var_38]
0x140005b74  xor     r9d, r9d
0x140005b77  mov     [rsp+68h+var_40], rax
0x140005b7c  lea     rdx, byte_140016DFB
0x140005b83  mov     [rsp+68h+var_48], 2
0x140005b8b  call    _tlgWriteTransfer_EventWriteTransfer
0x140005b90  mov     rcx, [rsp+68h+var_18]
0x140005b95  xor     rcx, rsp; StackCookie
0x140005b98  call    __security_check_cookie
0x140005b9d  add     rsp, 68h
0x140005ba1  retn
```
