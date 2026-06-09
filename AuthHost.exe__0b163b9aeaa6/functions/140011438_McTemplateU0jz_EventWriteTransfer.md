# McTemplateU0jz_EventWriteTransfer

- ea: `0x140011438`
- end: `0x1400114c0`
- name: `McTemplateU0jz_EventWriteTransfer`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010900`
- `0x14001121c`

## callees

- `0x140006748`
- `0x140011438`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0jz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  __int64 v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v8 = a3;
  v9 = 16;
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
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, 0, 3u, &v7);
}

```

## disassembly

```asm
0x140011438  sub     rsp, 78h
0x14001143c  mov     rax, cs:__security_cookie
0x140011443  xor     rax, rsp
0x140011446  mov     [rsp+78h+var_18], rax
0x14001144b  mov     [rsp+78h+var_38], r8
0x140011450  xor     r8d, r8d
0x140011453  mov     [rsp+78h+var_30], 10h
0x14001145c  test    r9, r9
0x14001145f  jz      short loc_140011478
0x140011461  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011465  inc     rax
0x140011468  cmp     [r9+rax*2], r8w
0x14001146d  jnz     short loc_140011465
0x14001146f  lea     eax, ds:2[rax*2]
0x140011476  jmp     short loc_14001147D
0x140011478  mov     eax, 0Ah
0x14001147d  test    r9, r9
0x140011480  mov     [rsp+78h+var_20], eax
0x140011484  lea     rcx, aNull_0; "NULL"
0x14001148b  mov     [rsp+78h+var_1C], r8d
0x140011490  cmovz   r9, rcx
0x140011494  lea     rax, [rsp+78h+var_48]
0x140011499  mov     [rsp+78h+var_28], r9
0x14001149e  mov     r9d, 3
0x1400114a4  mov     [rsp+78h+var_58], rax
0x1400114a9  call    McGenEventWrite_EventWriteTransfer
0x1400114ae  mov     rcx, [rsp+78h+var_18]
0x1400114b3  xor     rcx, rsp; StackCookie
0x1400114b6  call    __security_check_cookie
0x1400114bb  add     rsp, 78h
0x1400114bf  retn
```
