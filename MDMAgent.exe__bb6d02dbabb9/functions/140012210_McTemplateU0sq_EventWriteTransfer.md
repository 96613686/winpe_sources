# McTemplateU0sq_EventWriteTransfer

- ea: `0x140012210`
- end: `0x1400122ac`
- name: `McTemplateU0sq_EventWriteTransfer`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400094e4`

## callees

- `0x1400029c0`
- `0x140011ffc`
- `0x140012210`

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
0x140012210  mov     [rsp+arg_18], r9d
0x140012215  sub     rsp, 78h
0x140012219  mov     rax, cs:__security_cookie
0x140012220  xor     rax, rsp
0x140012223  mov     [rsp+78h+var_18], rax
0x140012228  xor     edx, edx
0x14001222a  test    r8, r8
0x14001222d  jz      short loc_140012240
0x14001222f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012233  inc     rax
0x140012236  cmp     [r8+rax], dl
0x14001223a  jnz     short loc_140012233
0x14001223c  inc     eax
0x14001223e  jmp     short loc_140012245
0x140012240  mov     eax, 5
0x140012245  mov     [rsp+78h+var_30], eax
0x140012249  lea     rcx, aNull; "NULL"
0x140012250  lea     rax, [rsp+78h+arg_18]
0x140012258  mov     [rsp+78h+var_2C], edx
0x14001225c  test    r8, r8
0x14001225f  mov     [rsp+78h+var_28], rax
0x140012264  lea     rax, [rsp+78h+var_48]
0x140012269  mov     [rsp+78h+var_20], 4
0x140012272  cmovz   r8, rcx
0x140012276  mov     [rsp+78h+var_58], rax
0x14001227b  mov     r9d, 3
0x140012281  mov     [rsp+78h+var_38], r8
0x140012286  lea     rdx, LeavingScopeWithFailedResultEvent
0x14001228d  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x140012294  call    McGenEventWrite_EventWriteTransfer
0x140012299  mov     rcx, [rsp+78h+var_18]
0x14001229e  xor     rcx, rsp; StackCookie
0x1400122a1  call    __security_check_cookie
0x1400122a6  add     rsp, 78h
0x1400122aa  retn
```
