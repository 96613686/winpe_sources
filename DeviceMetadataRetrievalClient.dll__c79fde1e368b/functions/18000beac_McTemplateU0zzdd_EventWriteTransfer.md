# McTemplateU0zzdd_EventWriteTransfer

- ea: `0x18000beac`
- end: `0x18000bf94`
- name: `McTemplateU0zzdd_EventWriteTransfer`
- size: `232`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *, const wchar_t *, char, char)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180006904`
- `0x18000b7a0`
- `0x18000cc50`
- `0x18000dabc`

## callees

- `0x180004d70`
- `0x18000beac`
- `0x180013700`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzdd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-9h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v17; // [rsp+50h] [rbp+7h]
  int v18; // [rsp+58h] [rbp+Fh]
  int v19; // [rsp+5Ch] [rbp+13h]
  char *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  char *v22; // [rsp+70h] [rbp+27h]
  __int64 v23; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v15 = v10;
  v16 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v14 = a3;
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v8 = 2 * v6 + 2;
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = L"NULL";
  v18 = v8;
  v17 = a4;
  v20 = &a5;
  v19 = 0;
  v22 = &a6;
  v21 = 4;
  v23 = 4;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)userpnp_Context, a2, (__int64)a3, 5u, &v13);
}

```

## disassembly

```asm
0x18000beac  mov     [rsp-8+arg_0], rbx
0x18000beb1  push    rbp
0x18000beb2  lea     rbp, [rsp-47h]
0x18000beb7  sub     rsp, 90h
0x18000bebe  mov     rax, cs:__security_cookie
0x18000bec5  xor     rax, rsp
0x18000bec8  mov     [rbp+47h+var_10], rax
0x18000becc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bed0  xor     r11d, r11d
0x18000bed3  mov     r10, rdx
0x18000bed6  mov     edx, 0Ah
0x18000bedb  test    r8, r8
0x18000bede  jz      short loc_18000BEF6
0x18000bee0  mov     rcx, rax
0x18000bee3  inc     rcx
0x18000bee6  cmp     [r8+rcx*2], r11w
0x18000beeb  jnz     short loc_18000BEE3
0x18000beed  lea     ecx, ds:2[rcx*2]
0x18000bef4  jmp     short loc_18000BEF8
0x18000bef6  mov     ecx, edx
0x18000bef8  test    r8, r8
0x18000befb  mov     [rbp+47h+var_48], ecx
0x18000befe  lea     rbx, aNull; "NULL"
0x18000bf05  mov     [rbp+47h+var_44], r11d
0x18000bf09  cmovz   r8, rbx
0x18000bf0d  mov     [rbp+47h+var_50], r8
0x18000bf11  test    r9, r9
0x18000bf14  jz      short loc_18000BF2A
0x18000bf16  inc     rax
0x18000bf19  cmp     [r9+rax*2], r11w
0x18000bf1e  jnz     short loc_18000BF16
0x18000bf20  lea     edx, ds:2[rax*2]
0x18000bf27  test    r9, r9
0x18000bf2a  cmovz   r9, rbx
0x18000bf2e  mov     [rbp+47h+var_38], edx
0x18000bf31  lea     rax, [rbp+47h+arg_20]
0x18000bf35  mov     [rbp+47h+var_40], r9
0x18000bf39  mov     [rbp+47h+var_30], rax
0x18000bf3d  lea     rcx, userpnp_Context
0x18000bf44  lea     rax, [rbp+47h+arg_28]
0x18000bf48  mov     [rbp+47h+var_34], r11d
0x18000bf4c  mov     [rbp+47h+var_20], rax
0x18000bf50  mov     r9d, 5
0x18000bf56  lea     rax, [rbp+47h+var_60]
0x18000bf5a  mov     [rbp+47h+var_28], 4
0x18000bf62  mov     rdx, r10
0x18000bf65  mov     [rsp+90h+var_70], rax
0x18000bf6a  mov     [rbp+47h+var_18], 4
0x18000bf72  call    McGenEventWrite_EventWriteTransfer
0x18000bf77  mov     rcx, [rbp+47h+var_10]
0x18000bf7b  xor     rcx, rsp; StackCookie
0x18000bf7e  call    __security_check_cookie
0x18000bf83  mov     rbx, [rsp+90h+arg_0]
0x18000bf8b  add     rsp, 90h
0x18000bf92  pop     rbp
0x18000bf93  retn
```
