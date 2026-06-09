# _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x1400050c8`
- end: `0x140005131`
- name: `??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005bd4`

## callees

- `0x1400022ec`
- `0x140002318`
- `0x140002f40`
- `0x1400050c8`

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
      return tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)byte_14001ED3D, v2, 0, 2u, &v4);
  }
  return result;
}

```

## disassembly

```asm
0x1400050c8  sub     rsp, 68h
0x1400050cc  mov     rax, cs:__security_cookie
0x1400050d3  xor     rax, rsp
0x1400050d6  mov     [rsp+68h+var_18], rax
0x1400050db  mov     eax, [rcx]
0x1400050dd  mov     r8, rdx
0x1400050e0  mov     r10, rcx
0x1400050e3  cmp     eax, 5
0x1400050e6  jbe     short loc_14000511F
0x1400050e8  mov     rdx, 400000000000h
0x1400050f2  call    _tlgKeywordOn
0x1400050f7  test    al, al
0x1400050f9  jz      short loc_14000511F
0x1400050fb  lea     rax, [rsp+68h+var_38]
0x140005100  xor     r9d, r9d
0x140005103  mov     [rsp+68h+var_40], rax
0x140005108  lea     rdx, byte_14001ED3D
0x14000510f  mov     rcx, r10
0x140005112  mov     [rsp+68h+var_48], 2
0x14000511a  call    _tlgWriteTransfer_EventWriteTransfer
0x14000511f  mov     rcx, [rsp+68h+var_18]
0x140005124  xor     rcx, rsp; StackCookie
0x140005127  call    __security_check_cookie
0x14000512c  add     rsp, 68h
0x140005130  retn
```
