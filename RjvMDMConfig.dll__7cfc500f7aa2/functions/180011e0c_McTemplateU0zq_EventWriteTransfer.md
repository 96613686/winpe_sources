# McTemplateU0zq_EventWriteTransfer

- ea: `0x180011e0c`
- end: `0x180011eae`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010340`
- `0x180010804`

## callees

- `0x180001c60`
- `0x180011b54`
- `0x180011e0c`

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
0x180011e0c  mov     [rsp+arg_18], r9d
0x180011e11  sub     rsp, 78h
0x180011e15  mov     rax, cs:__security_cookie
0x180011e1c  xor     rax, rsp
0x180011e1f  mov     [rsp+78h+var_18], rax
0x180011e24  xor     edx, edx
0x180011e26  test    r8, r8
0x180011e29  jz      short loc_180011E42
0x180011e2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011e2f  inc     rax
0x180011e32  cmp     [r8+rax*2], dx
0x180011e37  jnz     short loc_180011E2F
0x180011e39  lea     eax, ds:2[rax*2]
0x180011e40  jmp     short loc_180011E47
0x180011e42  mov     eax, 0Ah
0x180011e47  mov     [rsp+78h+var_30], eax
0x180011e4b  lea     rcx, aNull_0; "NULL"
0x180011e52  lea     rax, [rsp+78h+arg_18]
0x180011e5a  mov     [rsp+78h+var_2C], edx
0x180011e5e  test    r8, r8
0x180011e61  mov     [rsp+78h+var_28], rax
0x180011e66  lea     rax, [rsp+78h+var_48]
0x180011e6b  mov     [rsp+78h+var_20], 4
0x180011e74  cmovz   r8, rcx
0x180011e78  mov     [rsp+78h+var_58], rax
0x180011e7d  mov     r9d, 3
0x180011e83  mov     [rsp+78h+var_38], r8
0x180011e88  lea     rdx, DMScheduleAdminPollValues
0x180011e8f  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180011e96  call    McGenEventWrite_EventWriteTransfer
0x180011e9b  mov     rcx, [rsp+78h+var_18]
0x180011ea0  xor     rcx, rsp; StackCookie
0x180011ea3  call    __security_check_cookie
0x180011ea8  add     rsp, 78h
0x180011eac  retn
```
