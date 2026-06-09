# McTemplateU0sq_EventWriteTransfer

- ea: `0x18000c27c`
- end: `0x18000c30b`
- name: `McTemplateU0sq_EventWriteTransfer`
- size: `143`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180018337`
- `0x18001840f`
- `0x1800184f9`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x18000c27c`

## pseudocode

```c
ULONG __fastcall McTemplateU0sq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const char *v8; // [rsp+40h] [rbp-38h]
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
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = "NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x18000c27c  mov     [rsp+arg_18], r9d
0x18000c281  sub     rsp, 78h
0x18000c285  mov     rax, cs:__security_cookie
0x18000c28c  xor     rax, rsp
0x18000c28f  mov     [rsp+78h+var_18], rax
0x18000c294  xor     r9d, r9d
0x18000c297  test    r8, r8
0x18000c29a  jz      short loc_18000C2AD
0x18000c29c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c2a0  inc     rax
0x18000c2a3  cmp     [r8+rax], r9b
0x18000c2a7  jnz     short loc_18000C2A0
0x18000c2a9  inc     eax
0x18000c2ab  jmp     short loc_18000C2B2
0x18000c2ad  mov     eax, 5
0x18000c2b2  mov     [rsp+78h+var_30], eax
0x18000c2b6  lea     rcx, aNull; "NULL"
0x18000c2bd  lea     rax, [rsp+78h+arg_18]
0x18000c2c5  mov     [rsp+78h+var_2C], r9d
0x18000c2ca  test    r8, r8
0x18000c2cd  mov     [rsp+78h+var_28], rax
0x18000c2d2  lea     rax, [rsp+78h+var_48]
0x18000c2d7  mov     [rsp+78h+var_20], 4
0x18000c2e0  cmovz   r8, rcx
0x18000c2e4  mov     [rsp+78h+var_58], rax
0x18000c2e9  mov     r9d, 3
0x18000c2ef  mov     [rsp+78h+var_38], r8
0x18000c2f4  call    McGenEventWrite_EventWriteTransfer
0x18000c2f9  mov     rcx, [rsp+78h+var_18]
0x18000c2fe  xor     rcx, rsp; StackCookie
0x18000c301  call    __security_check_cookie
0x18000c306  add     rsp, 78h
0x18000c30a  retn
```
