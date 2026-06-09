# McTemplateU0zqqz_EventWriteTransfer

- ea: `0x18000c46c`
- end: `0x18000c550`
- name: `McTemplateU0zqqz_EventWriteTransfer`
- size: `228`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bf80`
- `0x18000c040`
- `0x18000c158`

## callees

- `0x18000c390`
- `0x18000c46c`
- `0x18001b340`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        int a4,
        char a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-9h]
  int v16; // [rsp+48h] [rbp-1h]
  int v17; // [rsp+4Ch] [rbp+3h]
  int *v18; // [rsp+50h] [rbp+7h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  char *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  int v25; // [rsp+B8h] [rbp+6Fh] BYREF

  v25 = a4;
  v6 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v16 = v10;
  v17 = 0;
  v18 = &v25;
  v19 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v20 = &a5;
  v11 = a6;
  v15 = a3;
  v21 = 4;
  v12 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v8 = 2 * v6 + 2;
    v12 = a6 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v23 = v8;
  v22 = v11;
  v24 = 0;
  return McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWSPHONE_DATASHARING_Context, a2, (__int64)a3, 5u, &v14);
}

```

## disassembly

```asm
0x18000c46c  mov     [rsp-8+arg_18], r9d
0x18000c471  push    rbp
0x18000c472  lea     rbp, [rsp-47h]
0x18000c477  sub     rsp, 90h
0x18000c47e  mov     rax, cs:__security_cookie
0x18000c485  xor     rax, rsp
0x18000c488  mov     [rbp+47h+var_10], rax
0x18000c48c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c490  xor     r9d, r9d
0x18000c493  mov     r10, rdx
0x18000c496  mov     edx, 0Ah
0x18000c49b  test    r8, r8
0x18000c49e  jz      short loc_18000C4B6
0x18000c4a0  mov     rcx, rax
0x18000c4a3  inc     rcx
0x18000c4a6  cmp     [r8+rcx*2], r9w
0x18000c4ab  jnz     short loc_18000C4A3
0x18000c4ad  lea     ecx, ds:2[rcx*2]
0x18000c4b4  jmp     short loc_18000C4B8
0x18000c4b6  mov     ecx, edx
0x18000c4b8  mov     [rbp+47h+var_48], ecx
0x18000c4bb  lea     r11, aNull; "NULL"
0x18000c4c2  lea     rcx, [rbp+47h+arg_18]
0x18000c4c6  mov     [rbp+47h+var_44], r9d
0x18000c4ca  mov     [rbp+47h+var_40], rcx
0x18000c4ce  test    r8, r8
0x18000c4d1  lea     rcx, [rbp+47h+arg_20]
0x18000c4d5  mov     [rbp+47h+var_38], 4
0x18000c4dd  cmovz   r8, r11
0x18000c4e1  mov     [rbp+47h+var_30], rcx
0x18000c4e5  mov     rcx, [rbp+47h+arg_28]
0x18000c4e9  mov     [rbp+47h+var_50], r8
0x18000c4ed  mov     [rbp+47h+var_28], 4
0x18000c4f5  test    rcx, rcx
0x18000c4f8  jz      short loc_18000C50E
0x18000c4fa  inc     rax
0x18000c4fd  cmp     [rcx+rax*2], r9w
0x18000c502  jnz     short loc_18000C4FA
0x18000c504  lea     edx, ds:2[rax*2]
0x18000c50b  test    rcx, rcx
0x18000c50e  cmovz   rcx, r11
0x18000c512  mov     [rbp+47h+var_18], edx
0x18000c515  mov     [rbp+47h+var_20], rcx
0x18000c519  lea     rax, [rbp+47h+var_60]
0x18000c51d  mov     [rbp+47h+var_14], r9d
0x18000c521  lea     rcx, MICROSOFT_WINDOWSPHONE_DATASHARING_Context
0x18000c528  mov     r9d, 5
0x18000c52e  mov     [rsp+90h+var_70], rax
0x18000c533  mov     rdx, r10
0x18000c536  call    McGenEventWrite_EventWriteTransfer
0x18000c53b  mov     rcx, [rbp+47h+var_10]
0x18000c53f  xor     rcx, rsp; StackCookie
0x18000c542  call    __security_check_cookie
0x18000c547  add     rsp, 90h
0x18000c54e  pop     rbp
0x18000c54f  retn
```
