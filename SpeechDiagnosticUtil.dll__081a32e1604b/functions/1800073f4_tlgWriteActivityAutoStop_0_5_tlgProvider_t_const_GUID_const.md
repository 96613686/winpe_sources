# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1800073f4`
- end: `0x180007445`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007588`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800073f4`

## pseudocode

```c
ULONG __fastcall _tlgWriteActivityAutoStop<0,5>(ULONG *a1, const GUID *a2)
{
  ULONG result; // eax
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( *a1 > 5 )
    return tlgWriteTransfer_EventWriteTransfer((__int64)a1, (unsigned __int8 *)qword_180015C38, a2, 0, 2u, &v3);
  return result;
}

```

## disassembly

```asm
0x1800073f4  sub     rsp, 68h
0x1800073f8  mov     rax, cs:__security_cookie
0x1800073ff  xor     rax, rsp
0x180007402  mov     [rsp+68h+var_18], rax
0x180007407  mov     eax, [rcx]
0x180007409  cmp     eax, 5
0x18000740c  jbe     short loc_180007432
0x18000740e  lea     rax, [rsp+68h+var_38]
0x180007413  mov     r8, rdx
0x180007416  mov     [rsp+68h+var_40], rax
0x18000741b  lea     rdx, qword_180015C38
0x180007422  xor     r9d, r9d
0x180007425  mov     [rsp+68h+var_48], 2
0x18000742d  call    _tlgWriteTransfer_EventWriteTransfer
0x180007432  mov     rcx, [rsp+68h+var_18]
0x180007437  xor     rcx, rsp; StackCookie
0x18000743a  call    __security_check_cookie
0x18000743f  add     rsp, 68h
0x180007443  retn
```
