# McTemplateU0ssqz_EventWriteTransfer

- ea: `0x180007018`
- end: `0x1800070d2`
- name: `McTemplateU0ssqz_EventWriteTransfer`
- size: `186`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003990`

## callees

- `0x180001cb0`
- `0x180006f28`
- `0x180007018`

## string_xrefs

- `0x180007067`: `TraceServiceStatus`

## pseudocode

```c
ULONG __fastcall McTemplateU0ssqz_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  int v6; // [rsp+30h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+40h] [rbp-19h] BYREF
  const char *v8; // [rsp+50h] [rbp-9h]
  int v9; // [rsp+58h] [rbp-1h]
  int v10; // [rsp+5Ch] [rbp+3h]
  const char *v11; // [rsp+60h] [rbp+7h]
  __int64 v12; // [rsp+68h] [rbp+Fh]
  int *v13; // [rsp+70h] [rbp+17h]
  __int64 v14; // [rsp+78h] [rbp+1Fh]
  const wchar_t *v15; // [rsp+80h] [rbp+27h]
  __int64 v16; // [rsp+88h] [rbp+2Fh]

  v6 = 35;
  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v9 = v4;
  v10 = 0;
  v11 = "TraceServiceStatus";
  v12 = 19;
  v13 = &v6;
  if ( !a3 )
    a3 = "NULL";
  v8 = a3;
  v15 = L"NULL";
  v14 = 4;
  v16 = 10;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, (__int64)a3, 5u, &v7);
}

```

## disassembly

```asm
0x180007018  push    rbp
0x18000701a  lea     rbp, [rsp-47h]
0x18000701f  sub     rsp, 0A0h
0x180007026  mov     rax, cs:__security_cookie
0x18000702d  xor     rax, rsp
0x180007030  mov     [rbp+47h+var_10], rax
0x180007034  xor     r9d, r9d
0x180007037  mov     [rbp+47h+var_70], 23h ; '#'
0x18000703e  mov     r10d, 5
0x180007044  test    r8, r8
0x180007047  jz      short loc_18000705A
0x180007049  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000704d  inc     rax
0x180007050  cmp     [r8+rax], r9b
0x180007054  jnz     short loc_18000704D
0x180007056  inc     eax
0x180007058  jmp     short loc_18000705D
0x18000705a  mov     eax, r10d
0x18000705d  mov     [rbp+47h+var_48], eax
0x180007060  lea     rcx, aNull; "NULL"
0x180007067  lea     rax, aTraceservicest; "TraceServiceStatus"
0x18000706e  mov     [rbp+47h+var_44], r9d
0x180007072  mov     [rbp+47h+var_40], rax
0x180007076  test    r8, r8
0x180007079  lea     rax, [rbp+47h+var_70]
0x18000707d  mov     [rbp+47h+var_38], 13h
0x180007085  mov     [rbp+47h+var_30], rax
0x180007089  cmovz   r8, rcx
0x18000708d  lea     rax, aNull_0; "NULL"
0x180007094  mov     [rbp+47h+var_50], r8
0x180007098  mov     [rbp+47h+var_20], rax
0x18000709c  mov     r9d, r10d
0x18000709f  lea     rax, [rbp+47h+var_60]
0x1800070a3  mov     [rbp+47h+var_28], 4
0x1800070ab  mov     [rsp+0A0h+var_80], rax
0x1800070b0  mov     [rbp+47h+var_18], 0Ah
0x1800070b8  call    McGenEventWrite_EventWriteTransfer
0x1800070bd  mov     rcx, [rbp+47h+var_10]
0x1800070c1  xor     rcx, rsp; StackCookie
0x1800070c4  call    __security_check_cookie
0x1800070c9  add     rsp, 0A0h
0x1800070d0  pop     rbp
0x1800070d1  retn
```
