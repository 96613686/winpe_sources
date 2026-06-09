# McTemplateU0sd_EventWriteTransfer

- ea: `0x180006f80`
- end: `0x18000700f`
- name: `McTemplateU0sd_EventWriteTransfer`
- size: `143`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b84`
- `0x1800061ac`

## callees

- `0x180001cb0`
- `0x180006f28`
- `0x180006f80`

## pseudocode

```c
ULONG __fastcall McTemplateU0sd_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, int a4)
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
0x180006f80  mov     [rsp+arg_18], r9d
0x180006f85  sub     rsp, 78h
0x180006f89  mov     rax, cs:__security_cookie
0x180006f90  xor     rax, rsp
0x180006f93  mov     [rsp+78h+var_18], rax
0x180006f98  xor     r9d, r9d
0x180006f9b  test    r8, r8
0x180006f9e  jz      short loc_180006FB1
0x180006fa0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006fa4  inc     rax
0x180006fa7  cmp     [r8+rax], r9b
0x180006fab  jnz     short loc_180006FA4
0x180006fad  inc     eax
0x180006faf  jmp     short loc_180006FB6
0x180006fb1  mov     eax, 5
0x180006fb6  mov     [rsp+78h+var_30], eax
0x180006fba  lea     rcx, aNull; "NULL"
0x180006fc1  lea     rax, [rsp+78h+arg_18]
0x180006fc9  mov     [rsp+78h+var_2C], r9d
0x180006fce  test    r8, r8
0x180006fd1  mov     [rsp+78h+var_28], rax
0x180006fd6  lea     rax, [rsp+78h+var_48]
0x180006fdb  mov     [rsp+78h+var_20], 4
0x180006fe4  cmovz   r8, rcx
0x180006fe8  mov     [rsp+78h+var_58], rax
0x180006fed  mov     r9d, 3
0x180006ff3  mov     [rsp+78h+var_38], r8
0x180006ff8  call    McGenEventWrite_EventWriteTransfer
0x180006ffd  mov     rcx, [rsp+78h+var_18]
0x180007002  xor     rcx, rsp; StackCookie
0x180007005  call    __security_check_cookie
0x18000700a  add     rsp, 78h
0x18000700e  retn
```
