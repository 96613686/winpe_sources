# McTemplateU0sqz_EventWriteTransfer

- ea: `0x180008390`
- end: `0x180008457`
- name: `McTemplateU0sqz_EventWriteTransfer`
- size: `199`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007978`

## callees

- `0x180001cb0`
- `0x180006f28`
- `0x180008390`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        int a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ecx
  const wchar_t *v8; // rcx
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-50h] BYREF
  const char *v12; // [rsp+40h] [rbp-40h]
  int v13; // [rsp+48h] [rbp-38h]
  int v14; // [rsp+4Ch] [rbp-34h]
  int *v15; // [rsp+50h] [rbp-30h]
  __int64 v16; // [rsp+58h] [rbp-28h]
  const wchar_t *v17; // [rsp+60h] [rbp-20h]
  int v18; // [rsp+68h] [rbp-18h]
  int v19; // [rsp+6Ch] [rbp-14h]
  int v20; // [rsp+A8h] [rbp+28h] BYREF

  v20 = a4;
  v5 = -1;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  v13 = v7;
  v14 = 0;
  v15 = &v20;
  v8 = a5;
  if ( !a3 )
    a3 = "NULL";
  v12 = a3;
  v16 = 4;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v9 = 2 * v5 + 2;
  }
  else
  {
    v9 = 10;
  }
  v18 = v9;
  v19 = 0;
  if ( !a5 )
    v8 = L"NULL";
  v17 = v8;
  return McGenEventWrite_EventWriteTransfer((__int64)v8, a2, (__int64)L"NULL", 4u, &v11);
}

```

## disassembly

```asm
0x180008390  mov     [rsp-8+arg_18], r9d
0x180008395  push    rbp
0x180008396  mov     rbp, rsp
0x180008399  sub     rsp, 80h
0x1800083a0  mov     rax, cs:__security_cookie
0x1800083a7  xor     rax, rsp
0x1800083aa  mov     [rbp+var_10], rax
0x1800083ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800083b2  xor     r10d, r10d
0x1800083b5  test    r8, r8
0x1800083b8  jz      short loc_1800083CA
0x1800083ba  mov     rcx, rax
0x1800083bd  inc     rcx
0x1800083c0  cmp     [r8+rcx], r10b
0x1800083c4  jnz     short loc_1800083BD
0x1800083c6  inc     ecx
0x1800083c8  jmp     short loc_1800083CF
0x1800083ca  mov     ecx, 5
0x1800083cf  lea     r9, aNull; "NULL"
0x1800083d6  mov     [rbp+var_38], ecx
0x1800083d9  lea     rcx, [rbp+arg_18]
0x1800083dd  mov     [rbp+var_34], r10d
0x1800083e1  test    r8, r8
0x1800083e4  mov     [rbp+var_30], rcx
0x1800083e8  mov     rcx, [rbp+arg_20]
0x1800083ec  cmovz   r8, r9
0x1800083f0  mov     r9d, 4
0x1800083f6  mov     [rbp+var_40], r8
0x1800083fa  mov     [rbp+var_28], r9
0x1800083fe  test    rcx, rcx
0x180008401  jz      short loc_180008416
0x180008403  inc     rax
0x180008406  cmp     [rcx+rax*2], r10w
0x18000840b  jnz     short loc_180008403
0x18000840d  lea     eax, ds:2[rax*2]
0x180008414  jmp     short loc_18000841B
0x180008416  mov     eax, 0Ah
0x18000841b  test    rcx, rcx
0x18000841e  mov     [rbp+var_18], eax
0x180008421  lea     r8, aNull_0; "NULL"
0x180008428  mov     [rbp+var_14], r10d
0x18000842c  cmovz   rcx, r8
0x180008430  lea     rax, [rbp+var_50]
0x180008434  mov     [rbp+var_20], rcx
0x180008438  mov     [rsp+80h+var_60], rax
0x18000843d  call    McGenEventWrite_EventWriteTransfer
0x180008442  mov     rcx, [rbp+var_10]
0x180008446  xor     rcx, rsp; StackCookie
0x180008449  call    __security_check_cookie
0x18000844e  add     rsp, 80h
0x180008455  pop     rbp
0x180008456  retn
```
