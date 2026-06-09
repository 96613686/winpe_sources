# McTemplateU0sq_EventWriteTransfer

- ea: `0x180011d68`
- end: `0x180011e04`
- name: `McTemplateU0sq_EventWriteTransfer`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800077a0`

## callees

- `0x180001c60`
- `0x180011b54`
- `0x180011d68`

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
0x180011d68  mov     [rsp+arg_18], r9d
0x180011d6d  sub     rsp, 78h
0x180011d71  mov     rax, cs:__security_cookie
0x180011d78  xor     rax, rsp
0x180011d7b  mov     [rsp+78h+var_18], rax
0x180011d80  xor     edx, edx
0x180011d82  test    r8, r8
0x180011d85  jz      short loc_180011D98
0x180011d87  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011d8b  inc     rax
0x180011d8e  cmp     [r8+rax], dl
0x180011d92  jnz     short loc_180011D8B
0x180011d94  inc     eax
0x180011d96  jmp     short loc_180011D9D
0x180011d98  mov     eax, 5
0x180011d9d  mov     [rsp+78h+var_30], eax
0x180011da1  lea     rcx, aNull; "NULL"
0x180011da8  lea     rax, [rsp+78h+arg_18]
0x180011db0  mov     [rsp+78h+var_2C], edx
0x180011db4  test    r8, r8
0x180011db7  mov     [rsp+78h+var_28], rax
0x180011dbc  lea     rax, [rsp+78h+var_48]
0x180011dc1  mov     [rsp+78h+var_20], 4
0x180011dca  cmovz   r8, rcx
0x180011dce  mov     [rsp+78h+var_58], rax
0x180011dd3  mov     r9d, 3
0x180011dd9  mov     [rsp+78h+var_38], r8
0x180011dde  lea     rdx, LeavingScopeWithFailedResultEvent
0x180011de5  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180011dec  call    McGenEventWrite_EventWriteTransfer
0x180011df1  mov     rcx, [rsp+78h+var_18]
0x180011df6  xor     rcx, rsp; StackCookie
0x180011df9  call    __security_check_cookie
0x180011dfe  add     rsp, 78h
0x180011e02  retn
```
