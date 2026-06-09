# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1800057e8`
- end: `0x18000585a`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `114`
- prototype: ``
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
int __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(__int64 a1, const GUID *a2)
{
  __int64 v2; // rax
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  LODWORD(v2) = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 > 5u )
  {
    v2 = *(_QWORD *)(a1 + 16);
    if ( (v2 & 0x200000000000LL) != 0 )
    {
      LODWORD(v2) = 0;
      if ( (*(_QWORD *)(a1 + 24) & 0x200000000000LL) == *(_QWORD *)(a1 + 24) )
        LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(a1, (unsigned __int8 *)word_18001129A, a2, 0, 2u, &v4);
    }
  }
  return v2;
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
