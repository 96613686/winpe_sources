# McTemplateU0zzd_EventWriteTransfer

- ea: `0x14001309c`
- end: `0x140013167`
- name: `McTemplateU0zzd_EventWriteTransfer`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a5e0`
- `0x14000d898`

## callees

- `0x140006d70`
- `0x14001309c`
- `0x14001a8d0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-48h]
  int v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  char *v19; // [rsp+60h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-20h]

  v5 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v9 = 10;
  }
  v14 = v9;
  v15 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v13 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v7 = 2 * v5 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v20 = 4;
  v18 = 0;
  return McGenEventWrite_EventWriteTransfer(v9, a2, (__int64)a3, 4u, &v12);
}

```

## disassembly

```asm
0x14001309c  push    rbx
0x14001309e  sub     rsp, 80h
0x1400130a5  mov     rax, cs:__security_cookie
0x1400130ac  xor     rax, rsp
0x1400130af  mov     [rsp+88h+var_18], rax
0x1400130b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400130b8  xor     r11d, r11d
0x1400130bb  mov     r10, rdx
0x1400130be  mov     edx, 0Ah
0x1400130c3  test    r8, r8
0x1400130c6  jz      short loc_1400130DE
0x1400130c8  mov     rcx, rax
0x1400130cb  inc     rcx
0x1400130ce  cmp     [r8+rcx*2], r11w
0x1400130d3  jnz     short loc_1400130CB
0x1400130d5  lea     ecx, ds:2[rcx*2]
0x1400130dc  jmp     short loc_1400130E0
0x1400130de  mov     ecx, edx
0x1400130e0  test    r8, r8
0x1400130e3  mov     [rsp+88h+var_40], ecx
0x1400130e7  lea     rbx, aNull; "NULL"
0x1400130ee  mov     [rsp+88h+var_3C], r11d
0x1400130f3  cmovz   r8, rbx
0x1400130f7  mov     [rsp+88h+var_48], r8
0x1400130fc  test    r9, r9
0x1400130ff  jz      short loc_140013115
0x140013101  inc     rax
0x140013104  cmp     [r9+rax*2], r11w
0x140013109  jnz     short loc_140013101
0x14001310b  lea     edx, ds:2[rax*2]
0x140013112  test    r9, r9
0x140013115  cmovz   r9, rbx
0x140013119  mov     [rsp+88h+var_30], edx
0x14001311d  lea     rax, [rsp+88h+arg_20]
0x140013125  mov     [rsp+88h+var_38], r9
0x14001312a  mov     [rsp+88h+var_28], rax
0x14001312f  mov     r9d, 4
0x140013135  lea     rax, [rsp+88h+var_58]
0x14001313a  mov     [rsp+88h+var_20], r9
0x14001313f  mov     rdx, r10
0x140013142  mov     [rsp+88h+var_68], rax
0x140013147  mov     [rsp+88h+var_2C], r11d
0x14001314c  call    McGenEventWrite_EventWriteTransfer
0x140013151  mov     rcx, [rsp+88h+var_18]
0x140013156  xor     rcx, rsp; StackCookie
0x140013159  call    __security_check_cookie
0x14001315e  add     rsp, 80h
0x140013165  pop     rbx
0x140013166  retn
```
