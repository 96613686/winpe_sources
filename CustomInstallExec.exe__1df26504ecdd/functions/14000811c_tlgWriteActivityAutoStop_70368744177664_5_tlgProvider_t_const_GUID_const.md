# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x14000811c`
- end: `0x140008185`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned int *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140008374`

## callees

- `0x14000258c`
- `0x1400025b8`
- `0x1400033b0`
- `0x14000811c`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v5; // r8
  __int64 v6; // r10
  _BYTE v7[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL, a2, a4);
    if ( (_BYTE)result )
      return tlgWriteTransfer_EventWriteTransfer(v6, byte_140012725, v5, 0, 2, v7);
  }
  return result;
}

```

## disassembly

```asm
0x14000811c  sub     rsp, 68h
0x140008120  mov     rax, cs:__security_cookie
0x140008127  xor     rax, rsp
0x14000812a  mov     [rsp+68h+var_18], rax
0x14000812f  mov     eax, [rcx]
0x140008131  mov     r8, rdx
0x140008134  mov     r10, rcx
0x140008137  cmp     eax, 5
0x14000813a  jbe     short loc_140008173
0x14000813c  mov     rdx, 400000000000h
0x140008146  call    _tlgKeywordOn
0x14000814b  test    al, al
0x14000814d  jz      short loc_140008173
0x14000814f  lea     rax, [rsp+68h+var_38]
0x140008154  xor     r9d, r9d
0x140008157  mov     [rsp+68h+var_40], rax
0x14000815c  lea     rdx, byte_140012725
0x140008163  mov     rcx, r10
0x140008166  mov     [rsp+68h+var_48], 2
0x14000816e  call    _tlgWriteTransfer_EventWriteTransfer
0x140008173  mov     rcx, [rsp+68h+var_18]
0x140008178  xor     rcx, rsp; StackCookie
0x14000817b  call    __security_check_cookie
0x140008180  add     rsp, 68h
0x140008184  retn
```
