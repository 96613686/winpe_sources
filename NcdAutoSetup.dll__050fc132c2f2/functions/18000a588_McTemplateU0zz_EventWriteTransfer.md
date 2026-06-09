# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000a588`
- end: `0x18000a63b`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800094c8`
- `0x18000fe40`

## callees

- `0x18000a4b0`
- `0x18000a588`
- `0x180013840`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v15; // [rsp+50h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
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
      ++v4;
    while ( a4[v4] );
    v6 = 2 * v4 + 2;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = L"NULL";
  v16 = v6;
  v15 = a4;
  v17 = 0;
  return McGenEventWrite_EventWriteTransfer(v8, a2, (__int64)a3, 3u, &v11);
}

```

## disassembly

```asm
0x18000a588  push    rbx
0x18000a58a  sub     rsp, 70h
0x18000a58e  mov     rax, cs:__security_cookie
0x18000a595  xor     rax, rsp
0x18000a598  mov     [rsp+78h+var_18], rax
0x18000a59d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a5a1  xor     r11d, r11d
0x18000a5a4  mov     r10, rdx
0x18000a5a7  mov     edx, 0Ah
0x18000a5ac  test    r8, r8
0x18000a5af  jz      short loc_18000A5C7
0x18000a5b1  mov     rcx, rax
0x18000a5b4  inc     rcx
0x18000a5b7  cmp     [r8+rcx*2], r11w
0x18000a5bc  jnz     short loc_18000A5B4
0x18000a5be  lea     ecx, ds:2[rcx*2]
0x18000a5c5  jmp     short loc_18000A5C9
0x18000a5c7  mov     ecx, edx
0x18000a5c9  test    r8, r8
0x18000a5cc  mov     [rsp+78h+var_30], ecx
0x18000a5d0  lea     rbx, aNull_1; "NULL"
0x18000a5d7  mov     [rsp+78h+var_2C], r11d
0x18000a5dc  cmovz   r8, rbx
0x18000a5e0  mov     [rsp+78h+var_38], r8
0x18000a5e5  test    r9, r9
0x18000a5e8  jz      short loc_18000A5FE
0x18000a5ea  inc     rax
0x18000a5ed  cmp     [r9+rax*2], r11w
0x18000a5f2  jnz     short loc_18000A5EA
0x18000a5f4  lea     edx, ds:2[rax*2]
0x18000a5fb  test    r9, r9
0x18000a5fe  cmovz   r9, rbx
0x18000a602  mov     [rsp+78h+var_20], edx
0x18000a606  mov     [rsp+78h+var_28], r9
0x18000a60b  lea     rax, [rsp+78h+var_48]
0x18000a610  mov     r9d, 3
0x18000a616  mov     [rsp+78h+var_1C], r11d
0x18000a61b  mov     rdx, r10
0x18000a61e  mov     [rsp+78h+var_58], rax
0x18000a623  call    McGenEventWrite_EventWriteTransfer
0x18000a628  mov     rcx, [rsp+78h+var_18]
0x18000a62d  xor     rcx, rsp; StackCookie
0x18000a630  call    __security_check_cookie
0x18000a635  add     rsp, 70h
0x18000a639  pop     rbx
0x18000a63a  retn
```
