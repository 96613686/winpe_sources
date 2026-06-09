# McTemplateU0zdd_EventWriteTransfer

- ea: `0x140012f38`
- end: `0x140012fd9`
- name: `McTemplateU0zdd_EventWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cd78`

## callees

- `0x140006d70`
- `0x140012f38`
- `0x14001a8d0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zdd_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A8h] [rbp+28h] BYREF

  v16 = a4;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v10 = v6;
  v11 = 0;
  v13 = 4;
  v12 = &v16;
  v15 = 4;
  v14 = &a5;
  if ( !a3 )
    a3 = L"NULL";
  v9 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)AppStatusAlertSendFailure,
           (__int64)a3,
           4u,
           &v8);
}

```

## disassembly

```asm
0x140012f38  mov     [rsp-8+arg_18], r9d
0x140012f3d  push    rbp
0x140012f3e  mov     rbp, rsp
0x140012f41  sub     rsp, 80h
0x140012f48  mov     rax, cs:__security_cookie
0x140012f4f  xor     rax, rsp
0x140012f52  mov     [rbp+var_10], rax
0x140012f56  xor     edx, edx
0x140012f58  test    r8, r8
0x140012f5b  jz      short loc_140012F74
0x140012f5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012f61  inc     rax
0x140012f64  cmp     [r8+rax*2], dx
0x140012f69  jnz     short loc_140012F61
0x140012f6b  lea     eax, ds:2[rax*2]
0x140012f72  jmp     short loc_140012F79
0x140012f74  mov     eax, 0Ah
0x140012f79  mov     [rbp+var_38], eax
0x140012f7c  lea     rcx, aNull; "NULL"
0x140012f83  mov     r9d, 4
0x140012f89  mov     [rbp+var_34], edx
0x140012f8c  lea     rax, [rbp+arg_18]
0x140012f90  mov     [rbp+var_28], r9
0x140012f94  mov     [rbp+var_30], rax
0x140012f98  lea     rdx, AppStatusAlertSendFailure
0x140012f9f  lea     rax, [rbp+arg_20]
0x140012fa3  mov     [rbp+var_18], r9
0x140012fa7  test    r8, r8
0x140012faa  mov     [rbp+var_20], rax
0x140012fae  lea     rax, [rbp+var_50]
0x140012fb2  cmovz   r8, rcx
0x140012fb6  mov     [rsp+80h+var_60], rax
0x140012fbb  mov     [rbp+var_40], r8
0x140012fbf  call    McGenEventWrite_EventWriteTransfer
0x140012fc4  mov     rcx, [rbp+var_10]
0x140012fc8  xor     rcx, rsp; StackCookie
0x140012fcb  call    __security_check_cookie
0x140012fd0  add     rsp, 80h
0x140012fd7  pop     rbp
0x140012fd8  retn
```
