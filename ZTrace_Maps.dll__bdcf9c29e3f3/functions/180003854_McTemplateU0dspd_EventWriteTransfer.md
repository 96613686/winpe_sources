# McTemplateU0dspd_EventWriteTransfer

- ea: `0x180003854`
- end: `0x180003903`
- name: `McTemplateU0dspd_EventWriteTransfer`
- size: `175`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, int, const char *, char, char)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800027d4`
- `0x1800028d4`
- `0x180002a54`

## callees

- `0x180001730`
- `0x18000375c`
- `0x180003854`

## pseudocode

```c
ULONG __fastcall McTemplateU0dspd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        const char *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-19h] BYREF
  int *v10; // [rsp+40h] [rbp-9h]
  __int64 v11; // [rsp+48h] [rbp-1h]
  const char *v12; // [rsp+50h] [rbp+7h]
  int v13; // [rsp+58h] [rbp+Fh]
  int v14; // [rsp+5Ch] [rbp+13h]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  char *v17; // [rsp+70h] [rbp+27h]
  __int64 v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+B0h] [rbp+67h] BYREF

  v19 = a3;
  v11 = 4;
  v10 = &v19;
  if ( a4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a4[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  v13 = v7;
  v14 = 0;
  v16 = 8;
  v15 = &a5;
  if ( !a4 )
    a4 = "NULL";
  v12 = a4;
  v17 = &a6;
  v18 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", a2, 0, 5u, &v9);
}

```

## disassembly

```asm
0x180003854  mov     [rsp-8+arg_10], r8d
0x180003859  push    rbp
0x18000385a  lea     rbp, [rsp-47h]
0x18000385f  sub     rsp, 90h
0x180003866  mov     rax, cs:__security_cookie
0x18000386d  xor     rax, rsp
0x180003870  mov     [rbp+47h+var_10], rax
0x180003874  xor     r8d, r8d
0x180003877  mov     [rbp+47h+var_48], 4
0x18000387f  lea     rax, [rbp+47h+arg_10]
0x180003883  mov     [rbp+47h+var_50], rax
0x180003887  lea     r10d, [r8+5]
0x18000388b  test    r9, r9
0x18000388e  jz      short loc_1800038A1
0x180003890  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003894  inc     rax
0x180003897  cmp     [r9+rax], r8b
0x18000389b  jnz     short loc_180003894
0x18000389d  inc     eax
0x18000389f  jmp     short loc_1800038A4
0x1800038a1  mov     eax, r10d
0x1800038a4  mov     [rbp+47h+var_38], eax
0x1800038a7  lea     rcx, aNull; "NULL"
0x1800038ae  test    r9, r9
0x1800038b1  mov     [rbp+47h+var_34], r8d
0x1800038b5  lea     rax, [rbp+47h+arg_20]
0x1800038b9  mov     [rbp+47h+var_28], 8
0x1800038c1  mov     [rbp+47h+var_30], rax
0x1800038c5  cmovz   r9, rcx
0x1800038c9  lea     rax, [rbp+47h+arg_28]
0x1800038cd  mov     [rbp+47h+var_40], r9
0x1800038d1  mov     [rbp+47h+var_20], rax
0x1800038d5  mov     r9d, r10d
0x1800038d8  lea     rax, [rbp+47h+var_60]
0x1800038dc  mov     [rbp+47h+var_18], 4
0x1800038e4  mov     [rsp+90h+var_70], rax
0x1800038e9  call    McGenEventWrite_EventWriteTransfer
0x1800038ee  mov     rcx, [rbp+47h+var_10]
0x1800038f2  xor     rcx, rsp; StackCookie
0x1800038f5  call    __security_check_cookie
0x1800038fa  add     rsp, 90h
0x180003901  pop     rbp
0x180003902  retn
```
