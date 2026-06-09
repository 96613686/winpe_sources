# McTemplateU0dzs_EventWriteTransfer

- ea: `0x18001a7c0`
- end: `0x18001a88a`
- name: `McTemplateU0dzs_EventWriteTransfer`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a39c`
- `0x18001a588`

## callees

- `0x180001520`
- `0x1800064f0`
- `0x18001a7c0`

## pseudocode

```c
ULONG __fastcall McTemplateU0dzs_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        const wchar_t *a4,
        const char *a5)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ecx
  const char *v8; // rcx
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-50h] BYREF
  int *v12; // [rsp+40h] [rbp-40h]
  __int64 v13; // [rsp+48h] [rbp-38h]
  const wchar_t *v14; // [rsp+50h] [rbp-30h]
  int v15; // [rsp+58h] [rbp-28h]
  int v16; // [rsp+5Ch] [rbp-24h]
  const char *v17; // [rsp+60h] [rbp-20h]
  int v18; // [rsp+68h] [rbp-18h]
  int v19; // [rsp+6Ch] [rbp-14h]
  int v20; // [rsp+A0h] [rbp+20h] BYREF

  v20 = a3;
  v12 = &v20;
  v5 = -1;
  v13 = 4;
  if ( a4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v15 = v7;
  v8 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v16 = 0;
  v14 = a4;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v9 = v5 + 1;
  }
  else
  {
    v9 = 5;
  }
  v18 = v9;
  v19 = 0;
  if ( !a5 )
    v8 = "NULL";
  v17 = v8;
  return McGenEventWrite_EventWriteTransfer((__int64)v8, a2, (__int64)"NULL", 4u, &v11);
}

```

## disassembly

```asm
0x18001a7c0  mov     [rsp-8+arg_10], r8d
0x18001a7c5  push    rbp
0x18001a7c6  mov     rbp, rsp
0x18001a7c9  sub     rsp, 80h
0x18001a7d0  mov     rax, cs:__security_cookie
0x18001a7d7  xor     rax, rsp
0x18001a7da  mov     [rbp+var_10], rax
0x18001a7de  lea     rax, [rbp+arg_10]
0x18001a7e2  xor     r10d, r10d
0x18001a7e5  mov     [rbp+var_40], rax
0x18001a7e9  mov     r11d, 4
0x18001a7ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a7f3  mov     [rbp+var_38], r11
0x18001a7f7  test    r9, r9
0x18001a7fa  jz      short loc_18001A812
0x18001a7fc  mov     rcx, rax
0x18001a7ff  inc     rcx
0x18001a802  cmp     [r9+rcx*2], r10w
0x18001a807  jnz     short loc_18001A7FF
0x18001a809  lea     ecx, ds:2[rcx*2]
0x18001a810  jmp     short loc_18001A817
0x18001a812  mov     ecx, 0Ah
0x18001a817  test    r9, r9
0x18001a81a  mov     [rbp+var_28], ecx
0x18001a81d  mov     rcx, [rbp+arg_20]
0x18001a821  lea     r8, aNull_0; "NULL"
0x18001a828  cmovz   r9, r8
0x18001a82c  mov     [rbp+var_24], r10d
0x18001a830  mov     [rbp+var_30], r9
0x18001a834  test    rcx, rcx
0x18001a837  jz      short loc_18001A846
0x18001a839  inc     rax
0x18001a83c  cmp     [rcx+rax], r10b
0x18001a840  jnz     short loc_18001A839
0x18001a842  inc     eax
0x18001a844  jmp     short loc_18001A84B
0x18001a846  mov     eax, 5
0x18001a84b  test    rcx, rcx
0x18001a84e  mov     [rbp+var_18], eax
0x18001a851  lea     r8, aNull; "NULL"
0x18001a858  mov     [rbp+var_14], r10d
0x18001a85c  cmovz   rcx, r8
0x18001a860  lea     rax, [rbp+var_50]
0x18001a864  mov     r9d, r11d
0x18001a867  mov     [rbp+var_20], rcx
0x18001a86b  mov     [rsp+80h+var_60], rax
0x18001a870  call    McGenEventWrite_EventWriteTransfer
0x18001a875  mov     rcx, [rbp+var_10]
0x18001a879  xor     rcx, rsp; StackCookie
0x18001a87c  call    __security_check_cookie
0x18001a881  add     rsp, 80h
0x18001a888  pop     rbp
0x18001a889  retn
```
