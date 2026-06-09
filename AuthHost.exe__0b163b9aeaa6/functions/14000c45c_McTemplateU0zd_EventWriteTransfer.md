# McTemplateU0zd_EventWriteTransfer

- ea: `0x14000c45c`
- end: `0x14000c4f1`
- name: `McTemplateU0zd_EventWriteTransfer`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b840`
- `0x140011aa4`
- `0x140012500`

## callees

- `0x140006748`
- `0x14000c45c`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0zd_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
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
0x14000c45c  mov     [rsp+arg_18], r9d
0x14000c461  sub     rsp, 78h
0x14000c465  mov     rax, cs:__security_cookie
0x14000c46c  xor     rax, rsp
0x14000c46f  mov     [rsp+78h+var_18], rax
0x14000c474  xor     r9d, r9d
0x14000c477  test    r8, r8
0x14000c47a  jz      short loc_14000C493
0x14000c47c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c480  inc     rax
0x14000c483  cmp     [r8+rax*2], r9w
0x14000c488  jnz     short loc_14000C480
0x14000c48a  lea     eax, ds:2[rax*2]
0x14000c491  jmp     short loc_14000C498
0x14000c493  mov     eax, 0Ah
0x14000c498  mov     [rsp+78h+var_30], eax
0x14000c49c  lea     rcx, aNull_0; "NULL"
0x14000c4a3  lea     rax, [rsp+78h+arg_18]
0x14000c4ab  mov     [rsp+78h+var_2C], r9d
0x14000c4b0  test    r8, r8
0x14000c4b3  mov     [rsp+78h+var_28], rax
0x14000c4b8  lea     rax, [rsp+78h+var_48]
0x14000c4bd  mov     [rsp+78h+var_20], 4
0x14000c4c6  cmovz   r8, rcx
0x14000c4ca  mov     [rsp+78h+var_58], rax
0x14000c4cf  mov     r9d, 3
0x14000c4d5  mov     [rsp+78h+var_38], r8
0x14000c4da  call    McGenEventWrite_EventWriteTransfer
0x14000c4df  mov     rcx, [rsp+78h+var_18]
0x14000c4e4  xor     rcx, rsp; StackCookie
0x14000c4e7  call    __security_check_cookie
0x14000c4ec  add     rsp, 78h
0x14000c4f0  retn
```
