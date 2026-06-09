# McTemplateK0z_EtwWriteTransfer

- ea: `0x140015898`
- end: `0x140015913`
- name: `McTemplateK0z_EtwWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400153c4`

## callees

- `0x14000a14c`
- `0x140015898`
- `0x140015af0`

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
0x140015898  sub     rsp, 68h
0x14001589c  mov     rax, cs:__security_cookie
0x1400158a3  xor     rax, rsp
0x1400158a6  mov     [rsp+68h+var_18], rax
0x1400158ab  xor     r11d, r11d
0x1400158ae  test    r9, r9
0x1400158b1  jz      short loc_1400158CA
0x1400158b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400158b7  inc     rax
0x1400158ba  cmp     [r9+rax*2], r11w
0x1400158bf  jnz     short loc_1400158B7
0x1400158c1  lea     eax, ds:2[rax*2]
0x1400158c8  jmp     short loc_1400158CF
0x1400158ca  mov     eax, 0Ah
0x1400158cf  test    r9, r9
0x1400158d2  mov     [rsp+68h+var_20], eax
0x1400158d6  lea     r10, aNull; "NULL"
0x1400158dd  mov     [rsp+68h+var_1C], r11d
0x1400158e2  cmovz   r9, r10
0x1400158e6  lea     rax, [rsp+68h+var_38]
0x1400158eb  mov     [rsp+68h+var_28], r9
0x1400158f0  mov     r9d, 2
0x1400158f6  mov     [rsp+68h+var_48], rax
0x1400158fb  call    McGenEventWrite_EtwWriteTransfer
0x140015900  mov     rcx, [rsp+68h+var_18]
0x140015905  xor     rcx, rsp; StackCookie
0x140015908  call    __security_check_cookie
0x14001590d  add     rsp, 68h
0x140015911  retn
```
