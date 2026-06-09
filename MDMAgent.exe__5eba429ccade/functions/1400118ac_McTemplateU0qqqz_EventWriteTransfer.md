# McTemplateU0qqqz_EventWriteTransfer

- ea: `0x1400118ac`
- end: `0x140011979`
- name: `McTemplateU0qqqz_EventWriteTransfer`
- size: `205`
- prototype: `ULONG __fastcall(__int64, __int64, int, int, char, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f1f8`

## callees

- `0x140002930`
- `0x1400117fc`
- `0x1400118ac`

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
0x1400118ac  mov     [rsp-8+arg_18], r9d
0x1400118b1  mov     [rsp-8+arg_10], r8d
0x1400118b6  push    rbp
0x1400118b7  lea     rbp, [rsp-47h]
0x1400118bc  sub     rsp, 90h
0x1400118c3  mov     rax, cs:__security_cookie
0x1400118ca  xor     rax, rsp
0x1400118cd  mov     [rbp+47h+var_10], rax
0x1400118d1  mov     rcx, [rbp+47h+arg_28]
0x1400118d5  lea     rax, [rbp+47h+arg_10]
0x1400118d9  mov     [rbp+47h+var_50], rax
0x1400118dd  xor     r8d, r8d
0x1400118e0  mov     [rbp+47h+var_48], 4
0x1400118e8  lea     rax, [rbp+47h+arg_18]
0x1400118ec  mov     [rbp+47h+var_40], rax
0x1400118f0  lea     rax, [rbp+47h+arg_20]
0x1400118f4  mov     [rbp+47h+var_30], rax
0x1400118f8  mov     [rbp+47h+var_38], 4
0x140011900  mov     [rbp+47h+var_28], 4
0x140011908  test    rcx, rcx
0x14001190b  jz      short loc_140011924
0x14001190d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011911  inc     rax
0x140011914  cmp     [rcx+rax*2], r8w
0x140011919  jnz     short loc_140011911
0x14001191b  lea     eax, ds:2[rax*2]
0x140011922  jmp     short loc_140011929
0x140011924  mov     eax, 0Ah
0x140011929  test    rcx, rcx
0x14001192c  mov     [rbp+47h+var_18], eax
0x14001192f  lea     rdx, aNull_0; "NULL"
0x140011936  mov     [rbp+47h+var_14], r8d
0x14001193a  cmovz   rcx, rdx
0x14001193e  lea     rax, [rbp+47h+var_60]
0x140011942  mov     [rbp+47h+var_20], rcx
0x140011946  lea     rdx, ScheduleEnrollmentCertRenewSessionStart
0x14001194d  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x140011954  mov     [rsp+90h+var_70], rax
0x140011959  mov     r9d, 5
0x14001195f  call    McGenEventWrite_EventWriteTransfer
0x140011964  mov     rcx, [rbp+47h+var_10]
0x140011968  xor     rcx, rsp; StackCookie
0x14001196b  call    __security_check_cookie
0x140011970  add     rsp, 90h
0x140011977  pop     rbp
0x140011978  retn
```
