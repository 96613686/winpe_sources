# McTemplateU0zq_EventWriteTransfer

- ea: `0x1800067bc`
- end: `0x180006851`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `149`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800061a0`
- `0x1800062dc`

## callees

- `0x180006764`
- `0x1800067bc`
- `0x18000aa50`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x1800067bc  mov     [rsp+arg_18], r9d
0x1800067c1  sub     rsp, 78h
0x1800067c5  mov     rax, cs:__security_cookie
0x1800067cc  xor     rax, rsp
0x1800067cf  mov     [rsp+78h+var_18], rax
0x1800067d4  xor     r9d, r9d
0x1800067d7  test    r8, r8
0x1800067da  jz      short loc_1800067F3
0x1800067dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800067e0  inc     rax
0x1800067e3  cmp     [r8+rax*2], r9w
0x1800067e8  jnz     short loc_1800067E0
0x1800067ea  lea     eax, ds:2[rax*2]
0x1800067f1  jmp     short loc_1800067F8
0x1800067f3  mov     eax, 0Ah
0x1800067f8  mov     [rsp+78h+var_30], eax
0x1800067fc  lea     rcx, aNull; "NULL"
0x180006803  lea     rax, [rsp+78h+arg_18]
0x18000680b  mov     [rsp+78h+var_2C], r9d
0x180006810  test    r8, r8
0x180006813  mov     [rsp+78h+var_28], rax
0x180006818  lea     rax, [rsp+78h+var_48]
0x18000681d  mov     [rsp+78h+var_20], 4
0x180006826  cmovz   r8, rcx
0x18000682a  mov     [rsp+78h+var_58], rax
0x18000682f  mov     r9d, 3
0x180006835  mov     [rsp+78h+var_38], r8
0x18000683a  call    McGenEventWrite_EventWriteTransfer
0x18000683f  mov     rcx, [rsp+78h+var_18]
0x180006844  xor     rcx, rsp; StackCookie
0x180006847  call    __security_check_cookie
0x18000684c  add     rsp, 78h
0x180006850  retn
```
