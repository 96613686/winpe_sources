# McTemplateU0z_EventWriteTransfer

- ea: `0x140007c64`
- end: `0x140007cde`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000740c`
- `0x1400074d4`
- `0x14000759c`
- `0x14000767c`
- `0x14000775c`

## callees

- `0x140006d70`
- `0x140007c64`
- `0x14001a8d0`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x140007c64  sub     rsp, 68h
0x140007c68  mov     rax, cs:__security_cookie
0x140007c6f  xor     rax, rsp
0x140007c72  mov     [rsp+68h+var_18], rax
0x140007c77  xor     r9d, r9d
0x140007c7a  test    r8, r8
0x140007c7d  jz      short loc_140007C96
0x140007c7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007c83  inc     rax
0x140007c86  cmp     [r8+rax*2], r9w
0x140007c8b  jnz     short loc_140007C83
0x140007c8d  lea     eax, ds:2[rax*2]
0x140007c94  jmp     short loc_140007C9B
0x140007c96  mov     eax, 0Ah
0x140007c9b  test    r8, r8
0x140007c9e  mov     [rsp+68h+var_20], eax
0x140007ca2  lea     rcx, aNull; "NULL"
0x140007ca9  mov     [rsp+68h+var_1C], r9d
0x140007cae  cmovz   r8, rcx
0x140007cb2  lea     rax, [rsp+68h+var_38]
0x140007cb7  mov     r9d, 2
0x140007cbd  mov     [rsp+68h+var_28], r8
0x140007cc2  mov     [rsp+68h+var_48], rax
0x140007cc7  call    McGenEventWrite_EventWriteTransfer
0x140007ccc  mov     rcx, [rsp+68h+var_18]
0x140007cd1  xor     rcx, rsp; StackCookie
0x140007cd4  call    __security_check_cookie
0x140007cd9  add     rsp, 68h
0x140007cdd  retn
```
