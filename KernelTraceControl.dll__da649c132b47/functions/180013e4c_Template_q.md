# Template_q

- ea: `0x180013e4c`
- end: `0x180013e9d`
- name: `Template_q`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d00`
- `0x1800153f0`

## callees

- `0x180026e30`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180013e85`
- `ADVAPI32!EventWrite` at `0x180013e85`

## pseudocode

```c
ULONG __fastcall Template_q(__int64 a1, const EVENT_DESCRIPTOR *a2, int a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+60h] [rbp+18h] BYREF

  v5 = a3;
  v4.Ptr = (ULONGLONG)&v5;
  v4.Reserved = 0;
  v4.Size = 4;
  return EventWrite(0, a2, 1u, &v4);
}

```

## disassembly

```asm
0x180013e4c  mov     r11, rsp
0x180013e4f  mov     [r11+18h], r8d
0x180013e53  sub     rsp, 48h
0x180013e57  mov     rax, cs:__security_cookie
0x180013e5e  xor     rax, rsp
0x180013e61  mov     [rsp+48h+var_10], rax
0x180013e66  xor     ecx, ecx; RegHandle
0x180013e68  lea     rax, [r11+18h]
0x180013e6c  mov     [r11-28h], rax
0x180013e70  lea     r9, [r11-28h]; UserData
0x180013e74  and     [rsp+48h+var_1C], 0
0x180013e79  mov     [rsp+48h+var_20], 4
0x180013e81  lea     r8d, [rcx+1]; UserDataCount
0x180013e85  call    cs:__imp_EventWrite
0x180013e8b  mov     rcx, [rsp+48h+var_10]
0x180013e90  xor     rcx, rsp; StackCookie
0x180013e93  call    __security_check_cookie
0x180013e98  add     rsp, 48h
0x180013e9c  retn
```
