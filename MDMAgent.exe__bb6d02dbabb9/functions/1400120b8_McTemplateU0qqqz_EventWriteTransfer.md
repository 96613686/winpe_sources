# McTemplateU0qqqz_EventWriteTransfer

- ea: `0x1400120b8`
- end: `0x140012186`
- name: `McTemplateU0qqqz_EventWriteTransfer`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f9a4`

## callees

- `0x1400029c0`
- `0x140011ffc`
- `0x1400120b8`

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
0x1400120b8  mov     [rsp-8+arg_18], r9d
0x1400120bd  mov     [rsp-8+arg_10], r8d
0x1400120c2  push    rbp
0x1400120c3  lea     rbp, [rsp-47h]
0x1400120c8  sub     rsp, 90h
0x1400120cf  mov     rax, cs:__security_cookie
0x1400120d6  xor     rax, rsp
0x1400120d9  mov     [rbp+47h+var_10], rax
0x1400120dd  mov     rcx, [rbp+47h+arg_28]
0x1400120e1  lea     rax, [rbp+47h+arg_10]
0x1400120e5  mov     [rbp+47h+var_50], rax
0x1400120e9  xor     r8d, r8d
0x1400120ec  mov     [rbp+47h+var_48], 4
0x1400120f4  lea     rax, [rbp+47h+arg_18]
0x1400120f8  mov     [rbp+47h+var_40], rax
0x1400120fc  lea     rax, [rbp+47h+arg_20]
0x140012100  mov     [rbp+47h+var_30], rax
0x140012104  mov     [rbp+47h+var_38], 4
0x14001210c  mov     [rbp+47h+var_28], 4
0x140012114  test    rcx, rcx
0x140012117  jz      short loc_140012130
0x140012119  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001211d  inc     rax
0x140012120  cmp     [rcx+rax*2], r8w
0x140012125  jnz     short loc_14001211D
0x140012127  lea     eax, ds:2[rax*2]
0x14001212e  jmp     short loc_140012135
0x140012130  mov     eax, 0Ah
0x140012135  test    rcx, rcx
0x140012138  mov     [rbp+47h+var_18], eax
0x14001213b  lea     rdx, aNull_0; "NULL"
0x140012142  mov     [rbp+47h+var_14], r8d
0x140012146  cmovz   rcx, rdx
0x14001214a  lea     rax, [rbp+47h+var_60]
0x14001214e  mov     [rbp+47h+var_20], rcx
0x140012152  lea     rdx, ScheduleEnrollmentCertRenewSessionStart
0x140012159  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x140012160  mov     [rsp+90h+var_70], rax
0x140012165  mov     r9d, 5
0x14001216b  call    McGenEventWrite_EventWriteTransfer
0x140012170  mov     rcx, [rbp+47h+var_10]
0x140012174  xor     rcx, rsp; StackCookie
0x140012177  call    __security_check_cookie
0x14001217c  add     rsp, 90h
0x140012183  pop     rbp
0x140012184  retn
```
