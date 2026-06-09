# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x140003210`
- end: `0x140003282`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003900`
- `0x1400059ac`

## callees

- `0x140001130`
- `0x140003210`
- `0x14000ded0`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    v4 = *((_QWORD *)a1 + 3);
    result = *((_QWORD *)a1 + 2);
    if ( (result & 0x200000000000LL) != 0 )
    {
      result = v4 & 0x200000000000LL;
      if ( (v4 & 0x200000000000LL) == v4 )
        return tlgWriteTransfer_EventWriteTransfer(a1, &word_1400133E6, a2, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003210  sub     rsp, 68h
0x140003214  mov     rax, cs:__security_cookie
0x14000321b  xor     rax, rsp
0x14000321e  mov     [rsp+68h+var_18], rax
0x140003223  mov     eax, [rcx]
0x140003225  mov     r8, rdx
0x140003228  cmp     eax, 5
0x14000322b  jbe     short loc_140003270
0x14000322d  mov     rdx, [rcx+18h]
0x140003231  mov     r9, 200000000000h
0x14000323b  mov     rax, [rcx+10h]
0x14000323f  test    r9, rax
0x140003242  jz      short loc_140003270
0x140003244  mov     rax, rdx
0x140003247  and     rax, r9
0x14000324a  cmp     rax, rdx
0x14000324d  jnz     short loc_140003270
0x14000324f  lea     rax, [rsp+68h+var_38]
0x140003254  xor     r9d, r9d
0x140003257  mov     [rsp+68h+var_40], rax
0x14000325c  lea     rdx, word_1400133E6
0x140003263  mov     [rsp+68h+var_48], 2
0x14000326b  call    _tlgWriteTransfer_EventWriteTransfer
0x140003270  mov     rcx, [rsp+68h+var_18]
0x140003275  xor     rcx, rsp; StackCookie
0x140003278  call    __security_check_cookie
0x14000327d  add     rsp, 68h
0x140003281  retn
```
