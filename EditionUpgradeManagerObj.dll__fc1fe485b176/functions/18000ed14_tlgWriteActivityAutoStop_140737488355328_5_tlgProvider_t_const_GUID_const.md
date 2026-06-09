# _tlgWriteActivityAutoStop<140737488355328,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000ed14`
- end: `0x18000ed86`
- name: `??$_tlgWriteActivityAutoStop@$0IAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022cd0`

## callees

- `0x180001008`
- `0x180001ac0`
- `0x18000ed14`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<140737488355328,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x800000000000LL) != 0 )
    {
      result = v4 & 0x800000000000LL;
      if ( (v4 & 0x800000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, &byte_18002B06F, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ed14  sub     rsp, 68h
0x18000ed18  mov     rax, cs:__security_cookie
0x18000ed1f  xor     rax, rsp
0x18000ed22  mov     [rsp+68h+var_18], rax
0x18000ed27  mov     eax, [rcx]
0x18000ed29  mov     r8, rdx
0x18000ed2c  cmp     eax, 5
0x18000ed2f  jbe     short loc_18000ED74
0x18000ed31  mov     rdx, [rcx+18h]
0x18000ed35  mov     r9, 800000000000h
0x18000ed3f  mov     rax, [rcx+10h]
0x18000ed43  test    r9, rax
0x18000ed46  jz      short loc_18000ED74
0x18000ed48  mov     rax, rdx
0x18000ed4b  and     rax, r9
0x18000ed4e  cmp     rax, rdx
0x18000ed51  jnz     short loc_18000ED74
0x18000ed53  lea     rax, [rsp+68h+var_38]
0x18000ed58  xor     r9d, r9d
0x18000ed5b  mov     [rsp+68h+var_40], rax
0x18000ed60  lea     rdx, byte_18002B06F
0x18000ed67  mov     [rsp+68h+var_48], 2
0x18000ed6f  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ed74  mov     rcx, [rsp+68h+var_18]
0x18000ed79  xor     rcx, rsp; StackCookie
0x18000ed7c  call    __security_check_cookie
0x18000ed81  add     rsp, 68h
0x18000ed85  retn
```
