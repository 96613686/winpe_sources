# McTemplateU0sspd_EventWriteTransfer

- ea: `0x1800039d4`
- end: `0x180003aa7`
- name: `McTemplateU0sspd_EventWriteTransfer`
- size: `211`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, const char *, char, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000258c`
- `0x180002bd4`

## callees

- `0x180001730`
- `0x18000375c`
- `0x1800039d4`

## pseudocode

```c
ULONG __fastcall McTemplateU0sspd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        const char *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-19h] BYREF
  const char *v12; // [rsp+40h] [rbp-9h]
  int v13; // [rsp+48h] [rbp-1h]
  int v14; // [rsp+4Ch] [rbp+3h]
  const char *v15; // [rsp+50h] [rbp+7h]
  int v16; // [rsp+58h] [rbp+Fh]
  int v17; // [rsp+5Ch] [rbp+13h]
  char *v18; // [rsp+60h] [rbp+17h]
  __int64 v19; // [rsp+68h] [rbp+1Fh]
  char *v20; // [rsp+70h] [rbp+27h]
  __int64 v21; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = (unsigned int)(v7 + 1);
  }
  else
  {
    v8 = 5;
  }
  v13 = v8;
  v14 = 0;
  if ( !a3 )
    a3 = "NULL";
  v12 = a3;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v9 = v6 + 1;
  }
  else
  {
    v9 = 5;
  }
  v16 = v9;
  v17 = 0;
  v18 = &a5;
  if ( !a4 )
    a4 = "NULL";
  v15 = a4;
  v20 = &a6;
  v19 = 8;
  v21 = 4;
  return McGenEventWrite_EventWriteTransfer(v8, a2, (__int64)a3, 5u, &v11);
}

```

## disassembly

```asm
0x1800039d4  mov     [rsp-8+arg_0], rbx
0x1800039d9  push    rbp
0x1800039da  lea     rbp, [rsp-47h]
0x1800039df  sub     rsp, 90h
0x1800039e6  mov     rax, cs:__security_cookie
0x1800039ed  xor     rax, rsp
0x1800039f0  mov     [rbp+47h+var_10], rax
0x1800039f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800039f8  xor     r10d, r10d
0x1800039fb  mov     r11d, 5
0x180003a01  test    r8, r8
0x180003a04  jz      short loc_180003A16
0x180003a06  mov     rcx, rax
0x180003a09  inc     rcx
0x180003a0c  cmp     [r8+rcx], r10b
0x180003a10  jnz     short loc_180003A09
0x180003a12  inc     ecx
0x180003a14  jmp     short loc_180003A19
0x180003a16  mov     ecx, r11d
0x180003a19  test    r8, r8
0x180003a1c  mov     [rbp+47h+var_48], ecx
0x180003a1f  lea     rbx, aNull; "NULL"
0x180003a26  mov     [rbp+47h+var_44], r10d
0x180003a2a  cmovz   r8, rbx
0x180003a2e  mov     [rbp+47h+var_50], r8
0x180003a32  test    r9, r9
0x180003a35  jz      short loc_180003A44
0x180003a37  inc     rax
0x180003a3a  cmp     [r9+rax], r10b
0x180003a3e  jnz     short loc_180003A37
0x180003a40  inc     eax
0x180003a42  jmp     short loc_180003A47
0x180003a44  mov     eax, r11d
0x180003a47  mov     [rbp+47h+var_38], eax
0x180003a4a  test    r9, r9
0x180003a4d  lea     rax, [rbp+47h+arg_20]
0x180003a51  mov     [rbp+47h+var_34], r10d
0x180003a55  mov     [rbp+47h+var_30], rax
0x180003a59  cmovz   r9, rbx
0x180003a5d  lea     rax, [rbp+47h+arg_28]
0x180003a61  mov     [rbp+47h+var_40], r9
0x180003a65  mov     [rbp+47h+var_20], rax
0x180003a69  mov     r9d, r11d
0x180003a6c  lea     rax, [rbp+47h+var_60]
0x180003a70  mov     [rbp+47h+var_28], 8
0x180003a78  mov     [rsp+90h+var_70], rax
0x180003a7d  mov     [rbp+47h+var_18], 4
0x180003a85  call    McGenEventWrite_EventWriteTransfer
0x180003a8a  mov     rcx, [rbp+47h+var_10]
0x180003a8e  xor     rcx, rsp; StackCookie
0x180003a91  call    __security_check_cookie
0x180003a96  mov     rbx, [rsp+90h+arg_0]
0x180003a9e  add     rsp, 90h
0x180003aa5  pop     rbp
0x180003aa6  retn
```
