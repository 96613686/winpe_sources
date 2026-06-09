# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180013fbc`
- end: `0x18001400c`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800142cc`

## callees

- `0x18000163c`
- `0x180013fbc`
- `0x18002bca0`

## pseudocode

```c
ULONG __fastcall _tlgWriteActivityAutoStop<0,5>(ULONG *a1, const GUID *a2)
{
  ULONG result; // eax
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( *a1 > 5 )
    return tlgWriteTransfer_EventWriteTransfer((__int64)a1, (unsigned __int8 *)word_180036822, a2, 0, 2u, &v3);
  return result;
}

```

## disassembly

```asm
0x180013fbc  sub     rsp, 68h
0x180013fc0  mov     rax, cs:__security_cookie
0x180013fc7  xor     rax, rsp
0x180013fca  mov     [rsp+68h+var_18], rax
0x180013fcf  mov     eax, [rcx]
0x180013fd1  cmp     eax, 5
0x180013fd4  jbe     short loc_180013FFA
0x180013fd6  lea     rax, [rsp+68h+var_38]
0x180013fdb  mov     r8, rdx
0x180013fde  mov     [rsp+68h+var_40], rax
0x180013fe3  lea     rdx, word_180036822
0x180013fea  xor     r9d, r9d
0x180013fed  mov     [rsp+68h+var_48], 2
0x180013ff5  call    _tlgWriteTransfer_EventWriteTransfer
0x180013ffa  mov     rcx, [rsp+68h+var_18]
0x180013fff  xor     rcx, rsp; StackCookie
0x180014002  call    __security_check_cookie
0x180014007  add     rsp, 68h
0x18001400b  retn
```
