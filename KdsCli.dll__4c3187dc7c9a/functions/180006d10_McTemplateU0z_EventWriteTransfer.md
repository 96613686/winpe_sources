# McTemplateU0z_EventWriteTransfer

- ea: `0x180006d10`
- end: `0x180006d8a`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004a00`
- `0x180007354`

## callees

- `0x180001630`
- `0x180006cb8`
- `0x180006d10`

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
0x180006d10  sub     rsp, 68h
0x180006d14  mov     rax, cs:__security_cookie
0x180006d1b  xor     rax, rsp
0x180006d1e  mov     [rsp+68h+var_18], rax
0x180006d23  xor     r9d, r9d
0x180006d26  test    r8, r8
0x180006d29  jz      short loc_180006D42
0x180006d2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006d2f  inc     rax
0x180006d32  cmp     [r8+rax*2], r9w
0x180006d37  jnz     short loc_180006D2F
0x180006d39  lea     eax, ds:2[rax*2]
0x180006d40  jmp     short loc_180006D47
0x180006d42  mov     eax, 0Ah
0x180006d47  test    r8, r8
0x180006d4a  mov     [rsp+68h+var_20], eax
0x180006d4e  lea     rcx, aNull_0; "NULL"
0x180006d55  mov     [rsp+68h+var_1C], r9d
0x180006d5a  cmovz   r8, rcx
0x180006d5e  lea     rax, [rsp+68h+var_38]
0x180006d63  mov     r9d, 2
0x180006d69  mov     [rsp+68h+var_28], r8
0x180006d6e  mov     [rsp+68h+var_48], rax
0x180006d73  call    McGenEventWrite_EventWriteTransfer
0x180006d78  mov     rcx, [rsp+68h+var_18]
0x180006d7d  xor     rcx, rsp; StackCookie
0x180006d80  call    __security_check_cookie
0x180006d85  add     rsp, 68h
0x180006d89  retn
```
