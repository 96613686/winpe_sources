# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000d928`
- end: `0x18000d99a`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dd54`

## callees

- `0x180001bdc`
- `0x180002bc0`
- `0x18000d928`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_180015075, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d928  sub     rsp, 68h
0x18000d92c  mov     rax, cs:__security_cookie
0x18000d933  xor     rax, rsp
0x18000d936  mov     [rsp+68h+var_18], rax
0x18000d93b  mov     eax, [rcx]
0x18000d93d  mov     r8, rdx
0x18000d940  cmp     eax, 5
0x18000d943  jbe     short loc_18000D988
0x18000d945  mov     rdx, [rcx+18h]
0x18000d949  mov     r9, 400000000000h
0x18000d953  mov     rax, [rcx+10h]
0x18000d957  test    r9, rax
0x18000d95a  jz      short loc_18000D988
0x18000d95c  mov     rax, rdx
0x18000d95f  and     rax, r9
0x18000d962  cmp     rax, rdx
0x18000d965  jnz     short loc_18000D988
0x18000d967  lea     rax, [rsp+68h+var_38]
0x18000d96c  xor     r9d, r9d
0x18000d96f  mov     [rsp+68h+var_40], rax
0x18000d974  lea     rdx, byte_180015075
0x18000d97b  mov     [rsp+68h+var_48], 2
0x18000d983  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d988  mov     rcx, [rsp+68h+var_18]
0x18000d98d  xor     rcx, rsp; StackCookie
0x18000d990  call    __security_check_cookie
0x18000d995  add     rsp, 68h
0x18000d999  retn
```
