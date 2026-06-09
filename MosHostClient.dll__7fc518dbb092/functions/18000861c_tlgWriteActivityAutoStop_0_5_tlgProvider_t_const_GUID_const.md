# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000861c`
- end: `0x18000866c`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f30`

## callees

- `0x18000163c`
- `0x180002550`
- `0x18000861c`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 5 )
    return tlgWriteTransfer_EventWriteTransfer(a1, &dword_180017E04, a2, 0, 2, v3);
  return result;
}

```

## disassembly

```asm
0x18000861c  sub     rsp, 68h
0x180008620  mov     rax, cs:__security_cookie
0x180008627  xor     rax, rsp
0x18000862a  mov     [rsp+68h+var_18], rax
0x18000862f  mov     eax, [rcx]
0x180008631  cmp     eax, 5
0x180008634  jbe     short loc_18000865A
0x180008636  lea     rax, [rsp+68h+var_38]
0x18000863b  mov     r8, rdx
0x18000863e  mov     [rsp+68h+var_40], rax
0x180008643  lea     rdx, dword_180017E04
0x18000864a  xor     r9d, r9d
0x18000864d  mov     [rsp+68h+var_48], 2
0x180008655  call    _tlgWriteTransfer_EventWriteTransfer
0x18000865a  mov     rcx, [rsp+68h+var_18]
0x18000865f  xor     rcx, rsp; StackCookie
0x180008662  call    __security_check_cookie
0x180008667  add     rsp, 68h
0x18000866b  retn
```
