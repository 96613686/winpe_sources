# McTemplateK0z_EtwWriteTransfer

- ea: `0x18000fdc0`
- end: `0x18000fe3b`
- name: `McTemplateK0z_EtwWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f78`
- `0x180009434`
- `0x18001b3cc`

## callees

- `0x18000fcb4`
- `0x18000fdc0`
- `0x18001baf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0z_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-28h]
  int v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+4Ch] [rbp-1Ch]

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v8 = a4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 2u, &v7);
}

```

## disassembly

```asm
0x18000fdc0  sub     rsp, 68h
0x18000fdc4  mov     rax, cs:__security_cookie
0x18000fdcb  xor     rax, rsp
0x18000fdce  mov     [rsp+68h+var_18], rax
0x18000fdd3  xor     r11d, r11d
0x18000fdd6  test    r9, r9
0x18000fdd9  jz      short loc_18000FDF2
0x18000fddb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fddf  inc     rax
0x18000fde2  cmp     [r9+rax*2], r11w
0x18000fde7  jnz     short loc_18000FDDF
0x18000fde9  lea     eax, ds:2[rax*2]
0x18000fdf0  jmp     short loc_18000FDF7
0x18000fdf2  mov     eax, 0Ah
0x18000fdf7  test    r9, r9
0x18000fdfa  mov     [rsp+68h+var_20], eax
0x18000fdfe  lea     r10, aNull; "NULL"
0x18000fe05  mov     [rsp+68h+var_1C], r11d
0x18000fe0a  cmovz   r9, r10
0x18000fe0e  lea     rax, [rsp+68h+var_38]
0x18000fe13  mov     [rsp+68h+var_28], r9
0x18000fe18  mov     r9d, 2
0x18000fe1e  mov     [rsp+68h+var_48], rax
0x18000fe23  call    McGenEventWrite_EtwWriteTransfer
0x18000fe28  mov     rcx, [rsp+68h+var_18]
0x18000fe2d  xor     rcx, rsp; StackCookie
0x18000fe30  call    __security_check_cookie
0x18000fe35  add     rsp, 68h
0x18000fe39  retn
```
