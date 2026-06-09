# McTemplateU0dzs_EventWriteTransfer

- ea: `0x18001ad0c`
- end: `0x18001add7`
- name: `McTemplateU0dzs_EventWriteTransfer`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a8c0`
- `0x18001aac0`

## callees

- `0x180001520`
- `0x180006560`
- `0x18001ad0c`

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
0x18001ad0c  mov     [rsp-8+arg_10], r8d
0x18001ad11  push    rbp
0x18001ad12  mov     rbp, rsp
0x18001ad15  sub     rsp, 80h
0x18001ad1c  mov     rax, cs:__security_cookie
0x18001ad23  xor     rax, rsp
0x18001ad26  mov     [rbp+var_10], rax
0x18001ad2a  lea     rax, [rbp+arg_10]
0x18001ad2e  xor     r10d, r10d
0x18001ad31  mov     [rbp+var_40], rax
0x18001ad35  mov     r11d, 4
0x18001ad3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ad3f  mov     [rbp+var_38], r11
0x18001ad43  test    r9, r9
0x18001ad46  jz      short loc_18001AD5E
0x18001ad48  mov     rcx, rax
0x18001ad4b  inc     rcx
0x18001ad4e  cmp     [r9+rcx*2], r10w
0x18001ad53  jnz     short loc_18001AD4B
0x18001ad55  lea     ecx, ds:2[rcx*2]
0x18001ad5c  jmp     short loc_18001AD63
0x18001ad5e  mov     ecx, 0Ah
0x18001ad63  test    r9, r9
0x18001ad66  mov     [rbp+var_28], ecx
0x18001ad69  mov     rcx, [rbp+arg_20]
0x18001ad6d  lea     r8, aNull_0; "NULL"
0x18001ad74  cmovz   r9, r8
0x18001ad78  mov     [rbp+var_24], r10d
0x18001ad7c  mov     [rbp+var_30], r9
0x18001ad80  test    rcx, rcx
0x18001ad83  jz      short loc_18001AD92
0x18001ad85  inc     rax
0x18001ad88  cmp     [rcx+rax], r10b
0x18001ad8c  jnz     short loc_18001AD85
0x18001ad8e  inc     eax
0x18001ad90  jmp     short loc_18001AD97
0x18001ad92  mov     eax, 5
0x18001ad97  test    rcx, rcx
0x18001ad9a  mov     [rbp+var_18], eax
0x18001ad9d  lea     r8, aNull; "NULL"
0x18001ada4  mov     [rbp+var_14], r10d
0x18001ada8  cmovz   rcx, r8
0x18001adac  lea     rax, [rbp+var_50]
0x18001adb0  mov     r9d, r11d
0x18001adb3  mov     [rbp+var_20], rcx
0x18001adb7  mov     [rsp+80h+var_60], rax
0x18001adbc  call    McGenEventWrite_EventWriteTransfer
0x18001adc1  mov     rcx, [rbp+var_10]
0x18001adc5  xor     rcx, rsp; StackCookie
0x18001adc8  call    __security_check_cookie
0x18001adcd  add     rsp, 80h
0x18001add4  pop     rbp
0x18001add5  retn
```
