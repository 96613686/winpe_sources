# McTemplateU0dsd_EventWriteTransfer

- ea: `0x1800037b4`
- end: `0x18000384d`
- name: `McTemplateU0dsd_EventWriteTransfer`
- size: `153`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, int, const char *, char)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800027d4`
- `0x1800028d4`
- `0x180002a54`
- `0x180003360`

## callees

- `0x180001730`
- `0x18000375c`
- `0x1800037b4`

## pseudocode

```c
ULONG __fastcall McTemplateU0dsd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        const char *a4,
        char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  int *v9; // [rsp+40h] [rbp-40h]
  __int64 v10; // [rsp+48h] [rbp-38h]
  const char *v11; // [rsp+50h] [rbp-30h]
  int v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+5Ch] [rbp-24h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A0h] [rbp+20h] BYREF

  v16 = a3;
  v9 = &v16;
  v10 = 4;
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v12 = v6;
  v13 = 0;
  if ( !a4 )
    a4 = "NULL";
  v15 = 4;
  v11 = a4;
  v14 = &a5;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, 0, 4u, &v8);
}

```

## disassembly

```asm
0x1800037b4  mov     [rsp-8+arg_10], r8d
0x1800037b9  push    rbp
0x1800037ba  mov     rbp, rsp
0x1800037bd  sub     rsp, 80h
0x1800037c4  mov     rax, cs:__security_cookie
0x1800037cb  xor     rax, rsp
0x1800037ce  mov     [rbp+var_10], rax
0x1800037d2  xor     r8d, r8d
0x1800037d5  lea     rax, [rbp+arg_10]
0x1800037d9  mov     [rbp+var_40], rax
0x1800037dd  mov     r10d, 4
0x1800037e3  mov     [rbp+var_38], r10
0x1800037e7  test    r9, r9
0x1800037ea  jz      short loc_1800037FD
0x1800037ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800037f0  inc     rax
0x1800037f3  cmp     [r9+rax], r8b
0x1800037f7  jnz     short loc_1800037F0
0x1800037f9  inc     eax
0x1800037fb  jmp     short loc_180003802
0x1800037fd  mov     eax, 5
0x180003802  test    r9, r9
0x180003805  mov     [rbp+var_28], eax
0x180003808  lea     rcx, aNull; "NULL"
0x18000380f  mov     [rbp+var_24], r8d
0x180003813  cmovz   r9, rcx
0x180003817  mov     [rbp+var_18], r10
0x18000381b  lea     rax, [rbp+arg_20]
0x18000381f  mov     [rbp+var_30], r9
0x180003823  mov     [rbp+var_20], rax
0x180003827  mov     r9d, r10d
0x18000382a  lea     rax, [rbp+var_50]
0x18000382e  mov     [rsp+80h+var_60], rax
0x180003833  call    McGenEventWrite_EventWriteTransfer
0x180003838  mov     rcx, [rbp+var_10]
0x18000383c  xor     rcx, rsp; StackCookie
0x18000383f  call    __security_check_cookie
0x180003844  add     rsp, 80h
0x18000384b  pop     rbp
0x18000384c  retn
```
