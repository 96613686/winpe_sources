# McTemplateU0sqq_EventWriteTransfer

- ea: `0x18001048c`
- end: `0x180010522`
- name: `McTemplateU0sqq_EventWriteTransfer`
- size: `150`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ecc8`
- `0x18000f1a4`
- `0x18000f520`
- `0x18000f964`
- `0x180015b00`
- `0x18001c680`
- `0x18002b7dc`

## callees

- `0x18001042c`
- `0x18001048c`
- `0x18002bca0`

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
0x18001048c  mov     [rsp-8+arg_18], r9d
0x180010491  push    rbp
0x180010492  mov     rbp, rsp
0x180010495  sub     rsp, 80h
0x18001049c  mov     rax, cs:__security_cookie
0x1800104a3  xor     rax, rsp
0x1800104a6  mov     [rbp+var_10], rax
0x1800104aa  xor     edx, edx; int
0x1800104ac  test    r8, r8
0x1800104af  jz      short loc_1800104C2
0x1800104b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800104b5  inc     rax
0x1800104b8  cmp     [r8+rax], dl
0x1800104bc  jnz     short loc_1800104B5
0x1800104be  inc     eax
0x1800104c0  jmp     short loc_1800104C7
0x1800104c2  mov     eax, 5
0x1800104c7  mov     [rbp+var_38], eax
0x1800104ca  lea     rcx, aNull; "NULL"
0x1800104d1  lea     rax, [rbp+arg_18]
0x1800104d5  mov     [rbp+var_34], edx
0x1800104d8  mov     [rbp+var_30], rax
0x1800104dc  test    r8, r8
0x1800104df  lea     rax, [rbp+arg_20]
0x1800104e3  mov     [rbp+var_28], 4
0x1800104eb  mov     [rbp+var_20], rax
0x1800104ef  cmovz   r8, rcx; int
0x1800104f3  lea     rax, [rbp+var_50]
0x1800104f7  mov     [rbp+var_40], r8
0x1800104fb  mov     [rsp+80h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x180010500  mov     [rbp+var_18], 4
0x180010508  call    McGenEventWrite_EventWriteTransfer
0x18001050d  mov     rcx, [rbp+var_10]
0x180010511  xor     rcx, rsp; StackCookie
0x180010514  call    __security_check_cookie
0x180010519  add     rsp, 80h
0x180010520  pop     rbp
0x180010521  retn
```
