# McTemplateU0qqqz_EventWriteTransfer

- ea: `0x180011c10`
- end: `0x180011cde`
- name: `McTemplateU0qqqz_EventWriteTransfer`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eb90`

## callees

- `0x180001c60`
- `0x180011b54`
- `0x180011c10`

## pseudocode

```c
ULONG __fastcall McTemplateU0qqqz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-19h] BYREF
  int *v11; // [rsp+40h] [rbp-9h]
  __int64 v12; // [rsp+48h] [rbp-1h]
  int *v13; // [rsp+50h] [rbp+7h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v17; // [rsp+70h] [rbp+27h]
  int v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+7Ch] [rbp+33h]
  int v20; // [rsp+B0h] [rbp+67h] BYREF
  int v21; // [rsp+B8h] [rbp+6Fh] BYREF

  v21 = a4;
  v20 = a3;
  v6 = a6;
  v11 = &v20;
  v12 = 4;
  v13 = &v21;
  v15 = &a5;
  v14 = 4;
  v16 = 4;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v18 = v8;
  v19 = 0;
  if ( !a6 )
    v6 = L"NULL";
  v17 = v6;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)ScheduleEnrollmentCertRenewSessionStart,
           0,
           5u,
           &v10);
}

```

## disassembly

```asm
0x180011c10  mov     [rsp-8+arg_18], r9d
0x180011c15  mov     [rsp-8+arg_10], r8d
0x180011c1a  push    rbp
0x180011c1b  lea     rbp, [rsp-47h]
0x180011c20  sub     rsp, 90h
0x180011c27  mov     rax, cs:__security_cookie
0x180011c2e  xor     rax, rsp
0x180011c31  mov     [rbp+47h+var_10], rax
0x180011c35  mov     rcx, [rbp+47h+arg_28]
0x180011c39  lea     rax, [rbp+47h+arg_10]
0x180011c3d  mov     [rbp+47h+var_50], rax
0x180011c41  xor     r8d, r8d
0x180011c44  mov     [rbp+47h+var_48], 4
0x180011c4c  lea     rax, [rbp+47h+arg_18]
0x180011c50  mov     [rbp+47h+var_40], rax
0x180011c54  lea     rax, [rbp+47h+arg_20]
0x180011c58  mov     [rbp+47h+var_30], rax
0x180011c5c  mov     [rbp+47h+var_38], 4
0x180011c64  mov     [rbp+47h+var_28], 4
0x180011c6c  test    rcx, rcx
0x180011c6f  jz      short loc_180011C88
0x180011c71  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011c75  inc     rax
0x180011c78  cmp     [rcx+rax*2], r8w
0x180011c7d  jnz     short loc_180011C75
0x180011c7f  lea     eax, ds:2[rax*2]
0x180011c86  jmp     short loc_180011C8D
0x180011c88  mov     eax, 0Ah
0x180011c8d  test    rcx, rcx
0x180011c90  mov     [rbp+47h+var_18], eax
0x180011c93  lea     rdx, aNull_0; "NULL"
0x180011c9a  mov     [rbp+47h+var_14], r8d
0x180011c9e  cmovz   rcx, rdx
0x180011ca2  lea     rax, [rbp+47h+var_60]
0x180011ca6  mov     [rbp+47h+var_20], rcx
0x180011caa  lea     rdx, ScheduleEnrollmentCertRenewSessionStart
0x180011cb1  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180011cb8  mov     [rsp+90h+var_70], rax
0x180011cbd  mov     r9d, 5
0x180011cc3  call    McGenEventWrite_EventWriteTransfer
0x180011cc8  mov     rcx, [rbp+47h+var_10]
0x180011ccc  xor     rcx, rsp; StackCookie
0x180011ccf  call    __security_check_cookie
0x180011cd4  add     rsp, 90h
0x180011cdb  pop     rbp
0x180011cdc  retn
```
