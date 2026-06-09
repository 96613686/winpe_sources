# McTemplateU0zd_EventWriteTransfer

- ea: `0x140012e98`
- end: `0x140012f32`
- name: `McTemplateU0zd_EventWriteTransfer`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cd78`

## callees

- `0x140006d70`
- `0x140012e98`
- `0x14001a8d0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zd_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
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
           (const EVENT_DESCRIPTOR *)AppStatusAlertSendSuccess,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x140012e98  mov     [rsp+arg_18], r9d
0x140012e9d  sub     rsp, 78h
0x140012ea1  mov     rax, cs:__security_cookie
0x140012ea8  xor     rax, rsp
0x140012eab  mov     [rsp+78h+var_18], rax
0x140012eb0  xor     edx, edx
0x140012eb2  test    r8, r8
0x140012eb5  jz      short loc_140012ECE
0x140012eb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012ebb  inc     rax
0x140012ebe  cmp     [r8+rax*2], dx
0x140012ec3  jnz     short loc_140012EBB
0x140012ec5  lea     eax, ds:2[rax*2]
0x140012ecc  jmp     short loc_140012ED3
0x140012ece  mov     eax, 0Ah
0x140012ed3  mov     [rsp+78h+var_30], eax
0x140012ed7  lea     rcx, aNull; "NULL"
0x140012ede  lea     rax, [rsp+78h+arg_18]
0x140012ee6  mov     [rsp+78h+var_2C], edx
0x140012eea  test    r8, r8
0x140012eed  mov     [rsp+78h+var_28], rax
0x140012ef2  lea     rax, [rsp+78h+var_48]
0x140012ef7  mov     [rsp+78h+var_20], 4
0x140012f00  cmovz   r8, rcx
0x140012f04  mov     [rsp+78h+var_58], rax
0x140012f09  mov     r9d, 3
0x140012f0f  mov     [rsp+78h+var_38], r8
0x140012f14  lea     rdx, AppStatusAlertSendSuccess
0x140012f1b  call    McGenEventWrite_EventWriteTransfer
0x140012f20  mov     rcx, [rsp+78h+var_18]
0x140012f25  xor     rcx, rsp; StackCookie
0x140012f28  call    __security_check_cookie
0x140012f2d  add     rsp, 78h
0x140012f31  retn
```
