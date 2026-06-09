# McTemplateU0zq_EventWriteTransfer

- ea: `0x1400122b4`
- end: `0x140012356`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010cf0`
- `0x1400112b0`

## callees

- `0x1400029c0`
- `0x140011ffc`
- `0x1400122b4`

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
           (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)DMScheduleAdminPollValues,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x1400122b4  mov     [rsp+arg_18], r9d
0x1400122b9  sub     rsp, 78h
0x1400122bd  mov     rax, cs:__security_cookie
0x1400122c4  xor     rax, rsp
0x1400122c7  mov     [rsp+78h+var_18], rax
0x1400122cc  xor     edx, edx
0x1400122ce  test    r8, r8
0x1400122d1  jz      short loc_1400122EA
0x1400122d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400122d7  inc     rax
0x1400122da  cmp     [r8+rax*2], dx
0x1400122df  jnz     short loc_1400122D7
0x1400122e1  lea     eax, ds:2[rax*2]
0x1400122e8  jmp     short loc_1400122EF
0x1400122ea  mov     eax, 0Ah
0x1400122ef  mov     [rsp+78h+var_30], eax
0x1400122f3  lea     rcx, aNull_0; "NULL"
0x1400122fa  lea     rax, [rsp+78h+arg_18]
0x140012302  mov     [rsp+78h+var_2C], edx
0x140012306  test    r8, r8
0x140012309  mov     [rsp+78h+var_28], rax
0x14001230e  lea     rax, [rsp+78h+var_48]
0x140012313  mov     [rsp+78h+var_20], 4
0x14001231c  cmovz   r8, rcx
0x140012320  mov     [rsp+78h+var_58], rax
0x140012325  mov     r9d, 3
0x14001232b  mov     [rsp+78h+var_38], r8
0x140012330  lea     rdx, DMScheduleAdminPollValues
0x140012337  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x14001233e  call    McGenEventWrite_EventWriteTransfer
0x140012343  mov     rcx, [rsp+78h+var_18]
0x140012348  xor     rcx, rsp; StackCookie
0x14001234b  call    __security_check_cookie
0x140012350  add     rsp, 78h
0x140012354  retn
```
