# McTemplateU0zz_EventWriteTransfer

- ea: `0x1400067a0`
- end: `0x140006853`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400055d0`
- `0x1400097b0`
- `0x14000ad80`

## callees

- `0x140006748`
- `0x1400067a0`
- `0x140012f60`

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
0x1400067a0  push    rbx
0x1400067a2  sub     rsp, 70h
0x1400067a6  mov     rax, cs:__security_cookie
0x1400067ad  xor     rax, rsp
0x1400067b0  mov     [rsp+78h+var_18], rax
0x1400067b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400067b9  xor     r11d, r11d
0x1400067bc  mov     r10, rdx
0x1400067bf  mov     edx, 0Ah
0x1400067c4  test    r8, r8
0x1400067c7  jz      short loc_1400067DF
0x1400067c9  mov     rcx, rax
0x1400067cc  inc     rcx
0x1400067cf  cmp     [r8+rcx*2], r11w
0x1400067d4  jnz     short loc_1400067CC
0x1400067d6  lea     ecx, ds:2[rcx*2]
0x1400067dd  jmp     short loc_1400067E1
0x1400067df  mov     ecx, edx
0x1400067e1  test    r8, r8
0x1400067e4  mov     [rsp+78h+var_30], ecx
0x1400067e8  lea     rbx, aNull_0; "NULL"
0x1400067ef  mov     [rsp+78h+var_2C], r11d
0x1400067f4  cmovz   r8, rbx
0x1400067f8  mov     [rsp+78h+var_38], r8
0x1400067fd  test    r9, r9
0x140006800  jz      short loc_140006816
0x140006802  inc     rax
0x140006805  cmp     [r9+rax*2], r11w
0x14000680a  jnz     short loc_140006802
0x14000680c  lea     edx, ds:2[rax*2]
0x140006813  test    r9, r9
0x140006816  cmovz   r9, rbx
0x14000681a  mov     [rsp+78h+var_20], edx
0x14000681e  mov     [rsp+78h+var_28], r9
0x140006823  lea     rax, [rsp+78h+var_48]
0x140006828  mov     r9d, 3
0x14000682e  mov     [rsp+78h+var_1C], r11d
0x140006833  mov     rdx, r10
0x140006836  mov     [rsp+78h+var_58], rax
0x14000683b  call    McGenEventWrite_EventWriteTransfer
0x140006840  mov     rcx, [rsp+78h+var_18]
0x140006845  xor     rcx, rsp; StackCookie
0x140006848  call    __security_check_cookie
0x14000684d  add     rsp, 70h
0x140006851  pop     rbx
0x140006852  retn
```
