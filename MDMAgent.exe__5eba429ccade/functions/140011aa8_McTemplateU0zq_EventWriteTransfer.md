# McTemplateU0zq_EventWriteTransfer

- ea: `0x140011aa8`
- end: `0x140011b49`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400104c0`
- `0x140010a68`

## callees

- `0x140002930`
- `0x1400117fc`
- `0x140011aa8`

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
0x140011aa8  mov     [rsp+arg_18], r9d
0x140011aad  sub     rsp, 78h
0x140011ab1  mov     rax, cs:__security_cookie
0x140011ab8  xor     rax, rsp
0x140011abb  mov     [rsp+78h+var_18], rax
0x140011ac0  xor     edx, edx
0x140011ac2  test    r8, r8
0x140011ac5  jz      short loc_140011ADE
0x140011ac7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011acb  inc     rax
0x140011ace  cmp     [r8+rax*2], dx
0x140011ad3  jnz     short loc_140011ACB
0x140011ad5  lea     eax, ds:2[rax*2]
0x140011adc  jmp     short loc_140011AE3
0x140011ade  mov     eax, 0Ah
0x140011ae3  mov     [rsp+78h+var_30], eax
0x140011ae7  lea     rcx, aNull_0; "NULL"
0x140011aee  lea     rax, [rsp+78h+arg_18]
0x140011af6  mov     [rsp+78h+var_2C], edx
0x140011afa  test    r8, r8
0x140011afd  mov     [rsp+78h+var_28], rax
0x140011b02  lea     rax, [rsp+78h+var_48]
0x140011b07  mov     [rsp+78h+var_20], 4
0x140011b10  cmovz   r8, rcx
0x140011b14  mov     [rsp+78h+var_58], rax
0x140011b19  mov     r9d, 3
0x140011b1f  mov     [rsp+78h+var_38], r8
0x140011b24  lea     rdx, DMScheduleAdminPollValues
0x140011b2b  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x140011b32  call    McGenEventWrite_EventWriteTransfer
0x140011b37  mov     rcx, [rsp+78h+var_18]
0x140011b3c  xor     rcx, rsp; StackCookie
0x140011b3f  call    __security_check_cookie
0x140011b44  add     rsp, 78h
0x140011b48  retn
```
