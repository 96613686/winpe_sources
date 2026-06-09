# McTemplateU0zqqxq_EventWriteTransfer

- ea: `0x180003484`
- end: `0x18000354a`
- name: `McTemplateU0zqqxq_EventWriteTransfer`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800026f4`

## callees

- `0x18000342c`
- `0x180003484`
- `0x180006980`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqqxq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        int a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-31h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-21h]
  int v12; // [rsp+48h] [rbp-19h]
  int v13; // [rsp+4Ch] [rbp-15h]
  int *v14; // [rsp+50h] [rbp-11h]
  __int64 v15; // [rsp+58h] [rbp-9h]
  char *v16; // [rsp+60h] [rbp-1h]
  __int64 v17; // [rsp+68h] [rbp+7h]
  char *v18; // [rsp+70h] [rbp+Fh]
  __int64 v19; // [rsp+78h] [rbp+17h]
  char *v20; // [rsp+80h] [rbp+1Fh]
  __int64 v21; // [rsp+88h] [rbp+27h]
  int v22; // [rsp+C8h] [rbp+67h] BYREF

  v22 = a4;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v12 = v8;
  v13 = 0;
  v14 = &v22;
  v15 = 4;
  v16 = &a5;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v18 = &a6;
  v17 = 4;
  v20 = &a7;
  v19 = 8;
  v21 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 6u, &v10);
}

```

## disassembly

```asm
0x180003484  mov     [rsp-8+arg_18], r9d
0x180003489  push    rbp
0x18000348a  lea     rbp, [rsp-3Fh]
0x18000348f  sub     rsp, 0A0h
0x180003496  mov     rax, cs:__security_cookie
0x18000349d  xor     rax, rsp
0x1800034a0  mov     [rbp+3Fh+var_10], rax
0x1800034a4  xor     r9d, r9d
0x1800034a7  test    r8, r8
0x1800034aa  jz      short loc_1800034C3
0x1800034ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034b0  inc     rax
0x1800034b3  cmp     [r8+rax*2], r9w
0x1800034b8  jnz     short loc_1800034B0
0x1800034ba  lea     eax, ds:2[rax*2]
0x1800034c1  jmp     short loc_1800034C8
0x1800034c3  mov     eax, 0Ah
0x1800034c8  mov     [rbp+3Fh+var_58], eax
0x1800034cb  lea     rcx, aNull; "NULL"
0x1800034d2  lea     rax, [rbp+3Fh+arg_18]
0x1800034d6  mov     [rbp+3Fh+var_54], r9d
0x1800034da  mov     [rbp+3Fh+var_50], rax
0x1800034de  test    r8, r8
0x1800034e1  lea     rax, [rbp+3Fh+arg_20]
0x1800034e5  mov     [rbp+3Fh+var_48], 4
0x1800034ed  mov     [rbp+3Fh+var_40], rax
0x1800034f1  cmovz   r8, rcx
0x1800034f5  lea     rax, [rbp+3Fh+arg_28]
0x1800034f9  mov     [rbp+3Fh+var_60], r8
0x1800034fd  mov     [rbp+3Fh+var_30], rax
0x180003501  mov     r9d, 6
0x180003507  lea     rax, [rbp+3Fh+arg_30]
0x18000350b  mov     [rbp+3Fh+var_38], 4
0x180003513  mov     [rbp+3Fh+var_20], rax
0x180003517  lea     rax, [rbp+3Fh+var_70]
0x18000351b  mov     [rsp+0A0h+var_80], rax
0x180003520  mov     [rbp+3Fh+var_28], 8
0x180003528  mov     [rbp+3Fh+var_18], 4
0x180003530  call    McGenEventWrite_EventWriteTransfer
0x180003535  mov     rcx, [rbp+3Fh+var_10]
0x180003539  xor     rcx, rsp; StackCookie
0x18000353c  call    __security_check_cookie
0x180003541  add     rsp, 0A0h
0x180003548  pop     rbp
0x180003549  retn
```
