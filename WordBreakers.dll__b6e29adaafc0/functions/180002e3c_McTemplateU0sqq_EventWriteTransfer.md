# McTemplateU0sqq_EventWriteTransfer

- ea: `0x180002e3c`
- end: `0x180002ed2`
- name: `McTemplateU0sqq_EventWriteTransfer`
- size: `150`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, __int64, char)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002c20`
- `0x180002f00`
- `0x180007280`
- `0x180007460`
- `0x18000ba36`
- `0x18000ba85`

## callees

- `0x180002ddc`
- `0x180002e3c`
- `0x18000b640`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqq_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, __int64 a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  const char *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A8h] [rbp+28h] BYREF

  v16 = a4;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v10 = v6;
  v11 = 0;
  v12 = &v16;
  v13 = 4;
  v14 = &a5;
  if ( !a3 )
    a3 = "NULL";
  v9 = a3;
  v15 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)"NULL", 0, (__int64)a3, a4, &v8);
}

```

## disassembly

```asm
0x180002e3c  mov     [rsp-8+arg_18], r9d
0x180002e41  push    rbp
0x180002e42  mov     rbp, rsp
0x180002e45  sub     rsp, 80h
0x180002e4c  mov     rax, cs:__security_cookie
0x180002e53  xor     rax, rsp
0x180002e56  mov     [rbp+var_10], rax
0x180002e5a  xor     edx, edx; int
0x180002e5c  test    r8, r8
0x180002e5f  jz      short loc_180002E72
0x180002e61  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002e65  inc     rax
0x180002e68  cmp     [r8+rax], dl
0x180002e6c  jnz     short loc_180002E65
0x180002e6e  inc     eax
0x180002e70  jmp     short loc_180002E77
0x180002e72  mov     eax, 5
0x180002e77  mov     [rbp+var_38], eax
0x180002e7a  lea     rcx, aNull; "NULL"
0x180002e81  lea     rax, [rbp+arg_18]
0x180002e85  mov     [rbp+var_34], edx
0x180002e88  mov     [rbp+var_30], rax
0x180002e8c  test    r8, r8
0x180002e8f  lea     rax, [rbp+arg_20]
0x180002e93  mov     [rbp+var_28], 4
0x180002e9b  mov     [rbp+var_20], rax
0x180002e9f  cmovz   r8, rcx; int
0x180002ea3  lea     rax, [rbp+var_50]
0x180002ea7  mov     [rbp+var_40], r8
0x180002eab  mov     [rsp+80h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x180002eb0  mov     [rbp+var_18], 4
0x180002eb8  call    McGenEventWrite_EventWriteTransfer
0x180002ebd  mov     rcx, [rbp+var_10]
0x180002ec1  xor     rcx, rsp; StackCookie
0x180002ec4  call    __security_check_cookie
0x180002ec9  add     rsp, 80h
0x180002ed0  pop     rbp
0x180002ed1  retn
```
