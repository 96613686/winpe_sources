# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180002f5c`
- end: `0x180002fce`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003048`

## callees

- `0x1800018dc`
- `0x180002f5c`
- `0x180007c90`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_18000AFB9, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002f5c  sub     rsp, 68h
0x180002f60  mov     rax, cs:__security_cookie
0x180002f67  xor     rax, rsp
0x180002f6a  mov     [rsp+68h+var_18], rax
0x180002f6f  mov     eax, [rcx]
0x180002f71  mov     r8, rdx
0x180002f74  cmp     eax, 5
0x180002f77  jbe     short loc_180002FBC
0x180002f79  mov     rdx, [rcx+18h]
0x180002f7d  mov     r9, 200000000000h
0x180002f87  mov     rax, [rcx+10h]
0x180002f8b  test    r9, rax
0x180002f8e  jz      short loc_180002FBC
0x180002f90  mov     rax, rdx
0x180002f93  and     rax, r9
0x180002f96  cmp     rax, rdx
0x180002f99  jnz     short loc_180002FBC
0x180002f9b  lea     rax, [rsp+68h+var_38]
0x180002fa0  xor     r9d, r9d
0x180002fa3  mov     [rsp+68h+var_40], rax
0x180002fa8  lea     rdx, byte_18000AFB9
0x180002faf  mov     [rsp+68h+var_48], 2
0x180002fb7  call    _tlgWriteTransfer_EventWriteTransfer
0x180002fbc  mov     rcx, [rsp+68h+var_18]
0x180002fc1  xor     rcx, rsp; StackCookie
0x180002fc4  call    __security_check_cookie
0x180002fc9  add     rsp, 68h
0x180002fcd  retn
```
