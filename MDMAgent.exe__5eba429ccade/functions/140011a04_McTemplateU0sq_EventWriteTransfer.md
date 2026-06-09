# McTemplateU0sq_EventWriteTransfer

- ea: `0x140011a04`
- end: `0x140011a9f`
- name: `McTemplateU0sq_EventWriteTransfer`
- size: `155`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400090fc`

## callees

- `0x140002930`
- `0x1400117fc`
- `0x140011a04`

## pseudocode

```c
ULONG __fastcall McTemplateU0sq_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)LeavingScopeWithFailedResultEvent,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x140011a04  mov     [rsp+arg_18], r9d
0x140011a09  sub     rsp, 78h
0x140011a0d  mov     rax, cs:__security_cookie
0x140011a14  xor     rax, rsp
0x140011a17  mov     [rsp+78h+var_18], rax
0x140011a1c  xor     edx, edx
0x140011a1e  test    r8, r8
0x140011a21  jz      short loc_140011A34
0x140011a23  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011a27  inc     rax
0x140011a2a  cmp     [r8+rax], dl
0x140011a2e  jnz     short loc_140011A27
0x140011a30  inc     eax
0x140011a32  jmp     short loc_140011A39
0x140011a34  mov     eax, 5
0x140011a39  mov     [rsp+78h+var_30], eax
0x140011a3d  lea     rcx, aNull; "NULL"
0x140011a44  lea     rax, [rsp+78h+arg_18]
0x140011a4c  mov     [rsp+78h+var_2C], edx
0x140011a50  test    r8, r8
0x140011a53  mov     [rsp+78h+var_28], rax
0x140011a58  lea     rax, [rsp+78h+var_48]
0x140011a5d  mov     [rsp+78h+var_20], 4
0x140011a66  cmovz   r8, rcx
0x140011a6a  mov     [rsp+78h+var_58], rax
0x140011a6f  mov     r9d, 3
0x140011a75  mov     [rsp+78h+var_38], r8
0x140011a7a  lea     rdx, LeavingScopeWithFailedResultEvent
0x140011a81  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x140011a88  call    McGenEventWrite_EventWriteTransfer
0x140011a8d  mov     rcx, [rsp+78h+var_18]
0x140011a92  xor     rcx, rsp; StackCookie
0x140011a95  call    __security_check_cookie
0x140011a9a  add     rsp, 78h
0x140011a9e  retn
```
