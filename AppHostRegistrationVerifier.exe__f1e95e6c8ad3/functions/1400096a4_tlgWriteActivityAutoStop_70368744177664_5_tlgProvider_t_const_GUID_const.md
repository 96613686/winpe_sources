# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400096a4`
- end: `0x14000970d`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009e9c`

## callees

- `0x140001b4c`
- `0x140001b78`
- `0x140002210`
- `0x1400096a4`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // r8
  __int64 v4; // r10
  _BYTE v5[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL, a2);
    if ( (_BYTE)result )
      return tlgWriteTransfer_EventWriteTransfer(v4, byte_140015919, v3, 0, 2, v5);
  }
  return result;
}

```

## disassembly

```asm
0x1400096a4  sub     rsp, 68h
0x1400096a8  mov     rax, cs:__security_cookie
0x1400096af  xor     rax, rsp
0x1400096b2  mov     [rsp+68h+var_18], rax
0x1400096b7  mov     eax, [rcx]
0x1400096b9  mov     r8, rdx
0x1400096bc  mov     r10, rcx
0x1400096bf  cmp     eax, 5
0x1400096c2  jbe     short loc_1400096FB
0x1400096c4  mov     rdx, 400000000000h
0x1400096ce  call    _tlgKeywordOn
0x1400096d3  test    al, al
0x1400096d5  jz      short loc_1400096FB
0x1400096d7  lea     rax, [rsp+68h+var_38]
0x1400096dc  xor     r9d, r9d
0x1400096df  mov     [rsp+68h+var_40], rax
0x1400096e4  lea     rdx, byte_140015919
0x1400096eb  mov     rcx, r10
0x1400096ee  mov     [rsp+68h+var_48], 2
0x1400096f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1400096fb  mov     rcx, [rsp+68h+var_18]
0x140009700  xor     rcx, rsp; StackCookie
0x140009703  call    __security_check_cookie
0x140009708  add     rsp, 68h
0x14000970c  retn
```
