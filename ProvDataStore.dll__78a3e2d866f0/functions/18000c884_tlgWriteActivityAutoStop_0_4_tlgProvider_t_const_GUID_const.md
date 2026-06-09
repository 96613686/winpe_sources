# _tlgWriteActivityAutoStop<0,4>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000c884`
- end: `0x18000c8d4`
- name: `??$_tlgWriteActivityAutoStop@$0A@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cb24`
- `0x18000dd4c`

## callees

- `0x1800011c4`
- `0x18000c884`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,4>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[32]; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( (unsigned int)result > 4 )
    return tlgWriteTransfer_EventWriteTransfer(a1, &byte_1800156AF, a2, 0, 2, v3);
  return result;
}

```

## disassembly

```asm
0x18000c884  sub     rsp, 68h
0x18000c888  mov     rax, cs:__security_cookie
0x18000c88f  xor     rax, rsp
0x18000c892  mov     [rsp+68h+var_18], rax
0x18000c897  mov     eax, [rcx]
0x18000c899  cmp     eax, 4
0x18000c89c  jbe     short loc_18000C8C2
0x18000c89e  lea     rax, [rsp+68h+var_38]
0x18000c8a3  mov     r8, rdx
0x18000c8a6  mov     [rsp+68h+var_40], rax
0x18000c8ab  lea     rdx, byte_1800156AF
0x18000c8b2  xor     r9d, r9d
0x18000c8b5  mov     [rsp+68h+var_48], 2
0x18000c8bd  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c8c2  mov     rcx, [rsp+68h+var_18]
0x18000c8c7  xor     rcx, rsp; StackCookie
0x18000c8ca  call    __security_check_cookie
0x18000c8cf  add     rsp, 68h
0x18000c8d3  retn
```
