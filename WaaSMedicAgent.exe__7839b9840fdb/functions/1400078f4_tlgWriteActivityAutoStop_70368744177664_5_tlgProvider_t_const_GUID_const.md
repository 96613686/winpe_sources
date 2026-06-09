# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400078f4`
- end: `0x140007966`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ab0`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x1400078f4`

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
        return tlgWriteTransfer_EventWriteTransfer(a1, byte_1400199BD, a2, 0, 2, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400078f4  sub     rsp, 68h
0x1400078f8  mov     rax, cs:__security_cookie
0x1400078ff  xor     rax, rsp
0x140007902  mov     [rsp+68h+var_18], rax
0x140007907  mov     eax, [rcx]
0x140007909  mov     r8, rdx
0x14000790c  cmp     eax, 5
0x14000790f  jbe     short loc_140007954
0x140007911  mov     rdx, [rcx+18h]
0x140007915  mov     r9, 400000000000h
0x14000791f  mov     rax, [rcx+10h]
0x140007923  test    r9, rax
0x140007926  jz      short loc_140007954
0x140007928  mov     rax, rdx
0x14000792b  and     rax, r9
0x14000792e  cmp     rax, rdx
0x140007931  jnz     short loc_140007954
0x140007933  lea     rax, [rsp+68h+var_38]
0x140007938  xor     r9d, r9d
0x14000793b  mov     [rsp+68h+var_40], rax
0x140007940  lea     rdx, byte_1400199BD
0x140007947  mov     [rsp+68h+var_48], 2
0x14000794f  call    _tlgWriteTransfer_EventWriteTransfer
0x140007954  mov     rcx, [rsp+68h+var_18]
0x140007959  xor     rcx, rsp; StackCookie
0x14000795c  call    __security_check_cookie
0x140007961  add     rsp, 68h
0x140007965  retn
```
