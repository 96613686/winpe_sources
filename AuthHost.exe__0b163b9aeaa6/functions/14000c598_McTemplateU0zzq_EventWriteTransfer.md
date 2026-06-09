# McTemplateU0zzq_EventWriteTransfer

- ea: `0x14000c598`
- end: `0x14000c661`
- name: `McTemplateU0zzq_EventWriteTransfer`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000abe0`

## callees

- `0x140006748`
- `0x14000c598`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-48h]
  int v13; // [rsp+48h] [rbp-40h]
  int v14; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v15; // [rsp+50h] [rbp-38h]
  int v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+5Ch] [rbp-2Ch]
  char *v18; // [rsp+60h] [rbp-28h]
  __int64 v19; // [rsp+68h] [rbp-20h]

  v5 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
  }
  else
  {
    v8 = 10;
  }
  v13 = v8;
  v14 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v12 = a3;
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v6 = 2 * v5 + 2;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = L"NULL";
  v16 = v6;
  v15 = a4;
  v18 = &a5;
  v17 = 0;
  v19 = 4;
  return McGenEventWrite_EventWriteTransfer(
           v8,
           (const EVENT_DESCRIPTOR *)NavigateRedirectedEvent,
           (__int64)a3,
           4u,
           &v11);
}

```

## disassembly

```asm
0x14000c598  sub     rsp, 88h
0x14000c59f  mov     rax, cs:__security_cookie
0x14000c5a6  xor     rax, rsp
0x14000c5a9  mov     [rsp+88h+var_18], rax
0x14000c5ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c5b2  xor     r10d, r10d
0x14000c5b5  mov     edx, 0Ah
0x14000c5ba  test    r8, r8
0x14000c5bd  jz      short loc_14000C5D5
0x14000c5bf  mov     rcx, rax
0x14000c5c2  inc     rcx
0x14000c5c5  cmp     [r8+rcx*2], r10w
0x14000c5ca  jnz     short loc_14000C5C2
0x14000c5cc  lea     ecx, ds:2[rcx*2]
0x14000c5d3  jmp     short loc_14000C5D7
0x14000c5d5  mov     ecx, edx
0x14000c5d7  test    r8, r8
0x14000c5da  mov     [rsp+88h+var_40], ecx
0x14000c5de  lea     r11, aNull_0; "NULL"
0x14000c5e5  mov     [rsp+88h+var_3C], r10d
0x14000c5ea  cmovz   r8, r11
0x14000c5ee  mov     [rsp+88h+var_48], r8
0x14000c5f3  test    r9, r9
0x14000c5f6  jz      short loc_14000C60C
0x14000c5f8  inc     rax
0x14000c5fb  cmp     [r9+rax*2], r10w
0x14000c600  jnz     short loc_14000C5F8
0x14000c602  lea     edx, ds:2[rax*2]
0x14000c609  test    r9, r9
0x14000c60c  cmovz   r9, r11
0x14000c610  mov     [rsp+88h+var_30], edx
0x14000c614  lea     rax, [rsp+88h+arg_20]
0x14000c61c  mov     [rsp+88h+var_38], r9
0x14000c621  mov     [rsp+88h+var_28], rax
0x14000c626  lea     rdx, NavigateRedirectedEvent
0x14000c62d  mov     r9d, 4
0x14000c633  mov     [rsp+88h+var_2C], r10d
0x14000c638  lea     rax, [rsp+88h+var_58]
0x14000c63d  mov     [rsp+88h+var_20], r9
0x14000c642  mov     [rsp+88h+var_68], rax
0x14000c647  call    McGenEventWrite_EventWriteTransfer
0x14000c64c  mov     rcx, [rsp+88h+var_18]
0x14000c651  xor     rcx, rsp; StackCookie
0x14000c654  call    __security_check_cookie
0x14000c659  add     rsp, 88h
0x14000c660  retn
```
