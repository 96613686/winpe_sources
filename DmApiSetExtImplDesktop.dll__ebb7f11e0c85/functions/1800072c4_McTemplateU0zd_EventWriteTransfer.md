# McTemplateU0zd_EventWriteTransfer

- ea: `0x1800072c4`
- end: `0x18000735a`
- name: `McTemplateU0zd_EventWriteTransfer`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006840`

## callees

- `0x180007264`
- `0x1800072c4`
- `0x180009f30`

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
0x1800072c4  mov     [rsp+arg_18], r9d
0x1800072c9  sub     rsp, 78h
0x1800072cd  mov     rax, cs:__security_cookie
0x1800072d4  xor     rax, rsp
0x1800072d7  mov     [rsp+78h+var_18], rax
0x1800072dc  xor     r9d, r9d
0x1800072df  test    r8, r8
0x1800072e2  jz      short loc_1800072FB
0x1800072e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800072e8  inc     rax
0x1800072eb  cmp     [r8+rax*2], r9w
0x1800072f0  jnz     short loc_1800072E8
0x1800072f2  lea     eax, ds:2[rax*2]
0x1800072f9  jmp     short loc_180007300
0x1800072fb  mov     eax, 0Ah
0x180007300  mov     [rsp+78h+var_30], eax
0x180007304  lea     rcx, aNull; "NULL"
0x18000730b  lea     rax, [rsp+78h+arg_18]
0x180007313  mov     [rsp+78h+var_2C], r9d
0x180007318  test    r8, r8
0x18000731b  mov     [rsp+78h+var_28], rax
0x180007320  lea     rax, [rsp+78h+var_48]
0x180007325  mov     [rsp+78h+var_20], 4
0x18000732e  cmovz   r8, rcx
0x180007332  mov     [rsp+78h+var_58], rax
0x180007337  mov     r9d, 3
0x18000733d  mov     [rsp+78h+var_38], r8
0x180007342  call    McGenEventWrite_EventWriteTransfer
0x180007347  mov     rcx, [rsp+78h+var_18]
0x18000734c  xor     rcx, rsp; StackCookie
0x18000734f  call    __security_check_cookie
0x180007354  add     rsp, 78h
0x180007358  retn
```
