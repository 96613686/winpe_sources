# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180008798`
- end: `0x180008801`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008b90`

## callees

- `0x180001008`
- `0x1800019ac`
- `0x180008798`
- `0x18000f0a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteActivityAutoStop<70368744177664,5>(ULONG *a1)
{
  ULONG result; // eax
  const GUID *v2; // r8
  __int64 v3; // r10
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF

  result = *a1;
  if ( *a1 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL);
    if ( (_BYTE)result )
      return tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)byte_180014861, v2, 0, 2u, &v4);
  }
  return result;
}

```

## disassembly

```asm
0x180008798  sub     rsp, 68h
0x18000879c  mov     rax, cs:__security_cookie
0x1800087a3  xor     rax, rsp
0x1800087a6  mov     [rsp+68h+var_18], rax
0x1800087ab  mov     eax, [rcx]
0x1800087ad  mov     r8, rdx
0x1800087b0  mov     r10, rcx
0x1800087b3  cmp     eax, 5
0x1800087b6  jbe     short loc_1800087EF
0x1800087b8  mov     rdx, 400000000000h
0x1800087c2  call    _tlgKeywordOn
0x1800087c7  test    al, al
0x1800087c9  jz      short loc_1800087EF
0x1800087cb  lea     rax, [rsp+68h+var_38]
0x1800087d0  xor     r9d, r9d
0x1800087d3  mov     [rsp+68h+var_40], rax
0x1800087d8  lea     rdx, byte_180014861
0x1800087df  mov     rcx, r10
0x1800087e2  mov     [rsp+68h+var_48], 2
0x1800087ea  call    _tlgWriteTransfer_EventWriteTransfer
0x1800087ef  mov     rcx, [rsp+68h+var_18]
0x1800087f4  xor     rcx, rsp; StackCookie
0x1800087f7  call    __security_check_cookie
0x1800087fc  add     rsp, 68h
0x180008800  retn
```
