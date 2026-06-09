# McTemplateK0zjxzz_EtwWriteTransfer

- ea: `0x140007a78`
- end: `0x140007b7e`
- name: `McTemplateK0zjxzz_EtwWriteTransfer`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000782c`

## callees

- `0x140007a10`
- `0x140007a78`
- `0x140007d00`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zjxzz_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        __int64 a5,
        char a6,
        const char *a7,
        const char *a8)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // eax
  const char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  const char *v15; // rax
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-39h] BYREF
  const char *v19; // [rsp+40h] [rbp-29h]
  int v20; // [rsp+48h] [rbp-21h]
  int v21; // [rsp+4Ch] [rbp-1Dh]
  __int64 v22; // [rsp+50h] [rbp-19h]
  __int64 v23; // [rsp+58h] [rbp-11h]
  char *v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+68h] [rbp-1h]
  const char *v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  int v28; // [rsp+7Ch] [rbp+13h]
  const char *v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+88h] [rbp+1Fh]
  int v31; // [rsp+8Ch] [rbp+23h]

  v8 = -1;
  v9 = 10;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a4[2 * v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v20 = v11;
  v22 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = &a6;
  v12 = a7;
  v19 = a4;
  v21 = 0;
  v23 = 16;
  v25 = 8;
  if ( a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&a7[2 * v13] );
    v14 = (unsigned int)(2 * v13 + 2);
  }
  else
  {
    v14 = 10;
  }
  v27 = v14;
  v28 = 0;
  if ( !a7 )
    v12 = L"NULL";
  v26 = v12;
  v15 = a8;
  v16 = a8 == 0;
  if ( a8 )
  {
    do
      ++v8;
    while ( *(_WORD *)&a8[2 * v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v16 = a8 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v30 = v9;
  v29 = v15;
  v31 = 0;
  return McGenEventWrite_EtwWriteTransfer(v8, v14, v9, (__int64)a4, &v18);
}

```

## disassembly

```asm
0x140007a78  push    rbp
0x140007a7a  lea     rbp, [rsp-37h]
0x140007a7f  sub     rsp, 0A0h
0x140007a86  mov     rax, cs:__security_cookie
0x140007a8d  xor     rax, rsp
0x140007a90  mov     [rbp+37h+var_10], rax
0x140007a94  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140007a98  xor     r10d, r10d
0x140007a9b  mov     r8d, 0Ah
0x140007aa1  test    r9, r9
0x140007aa4  jz      short loc_140007ABC
0x140007aa6  mov     rax, rcx
0x140007aa9  inc     rax
0x140007aac  cmp     [r9+rax*2], r10w
0x140007ab1  jnz     short loc_140007AA9
0x140007ab3  lea     eax, ds:2[rax*2]
0x140007aba  jmp     short loc_140007ABF
0x140007abc  mov     eax, r8d
0x140007abf  mov     [rbp+37h+var_58], eax
0x140007ac2  lea     r11, aNull_0; "NULL"
0x140007ac9  mov     rax, [rbp+37h+arg_20]
0x140007acd  test    r9, r9
0x140007ad0  mov     [rbp+37h+var_50], rax
0x140007ad4  lea     rax, [rbp+37h+arg_28]
0x140007ad8  cmovz   r9, r11; int
0x140007adc  mov     [rbp+37h+var_40], rax
0x140007ae0  mov     rax, [rbp+37h+arg_30]
0x140007ae4  mov     [rbp+37h+var_60], r9
0x140007ae8  mov     [rbp+37h+var_54], r10d
0x140007aec  mov     [rbp+37h+var_48], 10h
0x140007af4  mov     [rbp+37h+var_38], 8
0x140007afc  test    rax, rax
0x140007aff  jz      short loc_140007B17
0x140007b01  mov     rdx, rcx
0x140007b04  inc     rdx
0x140007b07  cmp     [rax+rdx*2], r10w
0x140007b0c  jnz     short loc_140007B04
0x140007b0e  lea     edx, ds:2[rdx*2]
0x140007b15  jmp     short loc_140007B1A
0x140007b17  mov     edx, r8d; int
0x140007b1a  test    rax, rax
0x140007b1d  mov     [rbp+37h+var_28], edx
0x140007b20  mov     [rbp+37h+var_24], r10d
0x140007b24  cmovz   rax, r11
0x140007b28  mov     [rbp+37h+var_30], rax
0x140007b2c  mov     rax, [rbp+37h+arg_38]
0x140007b30  test    rax, rax
0x140007b33  jz      short loc_140007B4A
0x140007b35  inc     rcx; int
0x140007b38  cmp     [rax+rcx*2], r10w
0x140007b3d  jnz     short loc_140007B35
0x140007b3f  lea     r8d, ds:2[rcx*2]; int
0x140007b47  test    rax, rax
0x140007b4a  cmovz   rax, r11
0x140007b4e  mov     [rbp+37h+var_18], r8d
0x140007b52  mov     [rbp+37h+var_20], rax
0x140007b56  lea     rax, [rbp+37h+var_70]
0x140007b5a  mov     [rsp+0A0h+var_80], rax; PEVENT_DATA_DESCRIPTOR
0x140007b5f  mov     [rbp+37h+var_14], r10d
0x140007b63  call    McGenEventWrite_EtwWriteTransfer
0x140007b68  mov     rcx, [rbp+37h+var_10]
0x140007b6c  xor     rcx, rsp; StackCookie
0x140007b6f  call    __security_check_cookie
0x140007b74  add     rsp, 0A0h
0x140007b7b  pop     rbp
0x140007b7c  retn
```
