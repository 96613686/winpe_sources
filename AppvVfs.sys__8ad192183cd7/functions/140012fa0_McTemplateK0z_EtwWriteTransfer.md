# McTemplateK0z_EtwWriteTransfer

- ea: `0x140012fa0`
- end: `0x14001301b`
- name: `McTemplateK0z_EtwWriteTransfer`
- size: `123`
- prototype: `NTSTATUS __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const GUID *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012acc`

## callees

- `0x140001030`
- `0x140012fa0`
- `0x140013b00`

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
0x140012fa0  sub     rsp, 68h
0x140012fa4  mov     rax, cs:__security_cookie
0x140012fab  xor     rax, rsp
0x140012fae  mov     [rsp+68h+var_18], rax
0x140012fb3  xor     r11d, r11d
0x140012fb6  test    r9, r9
0x140012fb9  jz      short loc_140012FD2
0x140012fbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012fbf  inc     rax
0x140012fc2  cmp     [r9+rax*2], r11w
0x140012fc7  jnz     short loc_140012FBF
0x140012fc9  lea     eax, ds:2[rax*2]
0x140012fd0  jmp     short loc_140012FD7
0x140012fd2  mov     eax, 0Ah
0x140012fd7  test    r9, r9
0x140012fda  mov     [rsp+68h+var_20], eax
0x140012fde  lea     r10, aNull; "NULL"
0x140012fe5  mov     [rsp+68h+var_1C], r11d
0x140012fea  cmovz   r9, r10
0x140012fee  lea     rax, [rsp+68h+var_38]
0x140012ff3  mov     [rsp+68h+var_28], r9
0x140012ff8  mov     r9d, 2
0x140012ffe  mov     [rsp+68h+var_48], rax
0x140013003  call    McGenEventWrite_EtwWriteTransfer
0x140013008  mov     rcx, [rsp+68h+var_18]
0x14001300d  xor     rcx, rsp; StackCookie
0x140013010  call    __security_check_cookie
0x140013015  add     rsp, 68h
0x140013019  retn
```
