# McTemplateU0zq_EventWriteTransfer

- ea: `0x14000c4f8`
- end: `0x14000c592`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b840`

## callees

- `0x140006748`
- `0x14000c4f8`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)NavigateHttpErrorEvent,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x14000c4f8  mov     [rsp+arg_18], r9d
0x14000c4fd  sub     rsp, 78h
0x14000c501  mov     rax, cs:__security_cookie
0x14000c508  xor     rax, rsp
0x14000c50b  mov     [rsp+78h+var_18], rax
0x14000c510  xor     edx, edx
0x14000c512  test    r8, r8
0x14000c515  jz      short loc_14000C52E
0x14000c517  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c51b  inc     rax
0x14000c51e  cmp     [r8+rax*2], dx
0x14000c523  jnz     short loc_14000C51B
0x14000c525  lea     eax, ds:2[rax*2]
0x14000c52c  jmp     short loc_14000C533
0x14000c52e  mov     eax, 0Ah
0x14000c533  mov     [rsp+78h+var_30], eax
0x14000c537  lea     rcx, aNull_0; "NULL"
0x14000c53e  lea     rax, [rsp+78h+arg_18]
0x14000c546  mov     [rsp+78h+var_2C], edx
0x14000c54a  test    r8, r8
0x14000c54d  mov     [rsp+78h+var_28], rax
0x14000c552  lea     rax, [rsp+78h+var_48]
0x14000c557  mov     [rsp+78h+var_20], 4
0x14000c560  cmovz   r8, rcx
0x14000c564  mov     [rsp+78h+var_58], rax
0x14000c569  mov     r9d, 3
0x14000c56f  mov     [rsp+78h+var_38], r8
0x14000c574  lea     rdx, NavigateHttpErrorEvent
0x14000c57b  call    McGenEventWrite_EventWriteTransfer
0x14000c580  mov     rcx, [rsp+78h+var_18]
0x14000c585  xor     rcx, rsp; StackCookie
0x14000c588  call    __security_check_cookie
0x14000c58d  add     rsp, 78h
0x14000c591  retn
```
