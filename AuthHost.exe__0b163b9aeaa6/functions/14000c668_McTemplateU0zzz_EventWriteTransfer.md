# McTemplateU0zzz_EventWriteTransfer

- ea: `0x14000c668`
- end: `0x14000c75b`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400097b0`
- `0x140009988`

## callees

- `0x140006748`
- `0x14000c668`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  bool v13; // zf
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-48h]
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v19; // [rsp+50h] [rbp-38h]
  int v20; // [rsp+58h] [rbp-30h]
  int v21; // [rsp+5Ch] [rbp-2Ch]
  const wchar_t *v22; // [rsp+60h] [rbp-28h]
  int v23; // [rsp+68h] [rbp-20h]
  int v24; // [rsp+6Ch] [rbp-1Ch]

  v5 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v17 = v9;
  v18 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v16 = a3;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v20 = v11;
  v12 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v21 = 0;
  v19 = a4;
  v13 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v7 = 2 * v5 + 2;
    v13 = a5 == 0;
  }
  if ( v13 )
    v12 = L"NULL";
  v23 = v7;
  v22 = v12;
  v24 = 0;
  return McGenEventWrite_EventWriteTransfer((__int64)v12, a2, (__int64)a3, 4u, &v15);
}

```

## disassembly

```asm
0x14000c668  push    rbx
0x14000c66a  sub     rsp, 80h
0x14000c671  mov     rax, cs:__security_cookie
0x14000c678  xor     rax, rsp
0x14000c67b  mov     [rsp+88h+var_18], rax
0x14000c680  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c684  xor     r11d, r11d
0x14000c687  mov     r10, rdx
0x14000c68a  mov     edx, 0Ah
0x14000c68f  test    r8, r8
0x14000c692  jz      short loc_14000C6AA
0x14000c694  mov     rcx, rax
0x14000c697  inc     rcx
0x14000c69a  cmp     [r8+rcx*2], r11w
0x14000c69f  jnz     short loc_14000C697
0x14000c6a1  lea     ecx, ds:2[rcx*2]
0x14000c6a8  jmp     short loc_14000C6AC
0x14000c6aa  mov     ecx, edx
0x14000c6ac  test    r8, r8
0x14000c6af  mov     [rsp+88h+var_40], ecx
0x14000c6b3  lea     rbx, aNull_0; "NULL"
0x14000c6ba  mov     [rsp+88h+var_3C], r11d
0x14000c6bf  cmovz   r8, rbx
0x14000c6c3  mov     [rsp+88h+var_48], r8
0x14000c6c8  test    r9, r9
0x14000c6cb  jz      short loc_14000C6E3
0x14000c6cd  mov     rcx, rax
0x14000c6d0  inc     rcx
0x14000c6d3  cmp     [r9+rcx*2], r11w
0x14000c6d8  jnz     short loc_14000C6D0
0x14000c6da  lea     ecx, ds:2[rcx*2]
0x14000c6e1  jmp     short loc_14000C6E5
0x14000c6e3  mov     ecx, edx
0x14000c6e5  test    r9, r9
0x14000c6e8  mov     [rsp+88h+var_30], ecx
0x14000c6ec  mov     rcx, [rsp+88h+arg_20]
0x14000c6f4  cmovz   r9, rbx
0x14000c6f8  mov     [rsp+88h+var_2C], r11d
0x14000c6fd  mov     [rsp+88h+var_38], r9
0x14000c702  test    rcx, rcx
0x14000c705  jz      short loc_14000C71B
0x14000c707  inc     rax
0x14000c70a  cmp     [rcx+rax*2], r11w
0x14000c70f  jnz     short loc_14000C707
0x14000c711  lea     edx, ds:2[rax*2]
0x14000c718  test    rcx, rcx
0x14000c71b  cmovz   rcx, rbx
0x14000c71f  mov     [rsp+88h+var_20], edx
0x14000c723  lea     rax, [rsp+88h+var_58]
0x14000c728  mov     [rsp+88h+var_28], rcx
0x14000c72d  mov     rdx, r10
0x14000c730  mov     [rsp+88h+var_68], rax
0x14000c735  mov     r9d, 4
0x14000c73b  mov     [rsp+88h+var_1C], r11d
0x14000c740  call    McGenEventWrite_EventWriteTransfer
0x14000c745  mov     rcx, [rsp+88h+var_18]
0x14000c74a  xor     rcx, rsp; StackCookie
0x14000c74d  call    __security_check_cookie
0x14000c752  add     rsp, 80h
0x14000c759  pop     rbx
0x14000c75a  retn
```
