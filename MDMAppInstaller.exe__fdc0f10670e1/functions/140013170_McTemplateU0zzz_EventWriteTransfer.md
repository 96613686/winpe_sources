# McTemplateU0zzz_EventWriteTransfer

- ea: `0x140013170`
- end: `0x140013263`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a5e0`
- `0x14000d134`
- `0x14000d898`

## callees

- `0x140006d70`
- `0x140013170`
- `0x14001a8d0`

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
0x140013170  push    rbx
0x140013172  sub     rsp, 80h
0x140013179  mov     rax, cs:__security_cookie
0x140013180  xor     rax, rsp
0x140013183  mov     [rsp+88h+var_18], rax
0x140013188  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001318c  xor     r11d, r11d
0x14001318f  mov     r10, rdx
0x140013192  mov     edx, 0Ah
0x140013197  test    r8, r8
0x14001319a  jz      short loc_1400131B2
0x14001319c  mov     rcx, rax
0x14001319f  inc     rcx
0x1400131a2  cmp     [r8+rcx*2], r11w
0x1400131a7  jnz     short loc_14001319F
0x1400131a9  lea     ecx, ds:2[rcx*2]
0x1400131b0  jmp     short loc_1400131B4
0x1400131b2  mov     ecx, edx
0x1400131b4  test    r8, r8
0x1400131b7  mov     [rsp+88h+var_40], ecx
0x1400131bb  lea     rbx, aNull; "NULL"
0x1400131c2  mov     [rsp+88h+var_3C], r11d
0x1400131c7  cmovz   r8, rbx
0x1400131cb  mov     [rsp+88h+var_48], r8
0x1400131d0  test    r9, r9
0x1400131d3  jz      short loc_1400131EB
0x1400131d5  mov     rcx, rax
0x1400131d8  inc     rcx
0x1400131db  cmp     [r9+rcx*2], r11w
0x1400131e0  jnz     short loc_1400131D8
0x1400131e2  lea     ecx, ds:2[rcx*2]
0x1400131e9  jmp     short loc_1400131ED
0x1400131eb  mov     ecx, edx
0x1400131ed  test    r9, r9
0x1400131f0  mov     [rsp+88h+var_30], ecx
0x1400131f4  mov     rcx, [rsp+88h+arg_20]
0x1400131fc  cmovz   r9, rbx
0x140013200  mov     [rsp+88h+var_2C], r11d
0x140013205  mov     [rsp+88h+var_38], r9
0x14001320a  test    rcx, rcx
0x14001320d  jz      short loc_140013223
0x14001320f  inc     rax
0x140013212  cmp     [rcx+rax*2], r11w
0x140013217  jnz     short loc_14001320F
0x140013219  lea     edx, ds:2[rax*2]
0x140013220  test    rcx, rcx
0x140013223  cmovz   rcx, rbx
0x140013227  mov     [rsp+88h+var_20], edx
0x14001322b  lea     rax, [rsp+88h+var_58]
0x140013230  mov     [rsp+88h+var_28], rcx
0x140013235  mov     rdx, r10
0x140013238  mov     [rsp+88h+var_68], rax
0x14001323d  mov     r9d, 4
0x140013243  mov     [rsp+88h+var_1C], r11d
0x140013248  call    McGenEventWrite_EventWriteTransfer
0x14001324d  mov     rcx, [rsp+88h+var_18]
0x140013252  xor     rcx, rsp; StackCookie
0x140013255  call    __security_check_cookie
0x14001325a  add     rsp, 80h
0x140013261  pop     rbx
0x140013262  retn
```
