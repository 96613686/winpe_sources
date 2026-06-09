# McTemplateU0zjzz_EventWriteTransfer

- ea: `0x18000f120`
- end: `0x18000f22d`
- name: `McTemplateU0zjzz_EventWriteTransfer`
- size: `269`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const wchar_t *, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800083e0`
- `0x18000f120`
- `0x18001bcf0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zjzz_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        __int64 a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v9; // r10d
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-29h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-19h]
  int v20; // [rsp+48h] [rbp-11h]
  int v21; // [rsp+4Ch] [rbp-Dh]
  __int64 v22; // [rsp+50h] [rbp-9h]
  __int64 v23; // [rsp+58h] [rbp-1h]
  const wchar_t *v24; // [rsp+60h] [rbp+7h]
  int v25; // [rsp+68h] [rbp+Fh]
  int v26; // [rsp+6Ch] [rbp+13h]
  const wchar_t *v27; // [rsp+70h] [rbp+17h]
  int v28; // [rsp+78h] [rbp+1Fh]
  int v29; // [rsp+7Ch] [rbp+23h]

  v6 = -1;
  v9 = 10;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v20 = v11;
  v12 = a5;
  if ( !a3 )
    a3 = L"NULL";
  v21 = 0;
  v19 = a3;
  v22 = a4;
  v23 = 16;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  v25 = v14;
  v26 = 0;
  if ( !a5 )
    v12 = L"NULL";
  v24 = v12;
  v15 = a6;
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v9 = 2 * v6 + 2;
    v16 = a6 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v28 = v9;
  v27 = v15;
  v29 = 0;
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 5u, &v18);
}

```

## disassembly

```asm
0x18000f120  mov     [rsp-8+arg_10], rbx
0x18000f125  push    rbp
0x18000f126  push    rsi
0x18000f127  push    rdi
0x18000f128  lea     rbp, [rsp-37h]
0x18000f12d  sub     rsp, 90h
0x18000f134  mov     rax, cs:__security_cookie
0x18000f13b  xor     rax, rsp
0x18000f13e  mov     [rbp+47h+var_20], rax
0x18000f142  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f146  xor     edi, edi
0x18000f148  mov     rbx, rdx
0x18000f14b  mov     r11, rcx
0x18000f14e  mov     r10d, 0Ah
0x18000f154  test    r8, r8
0x18000f157  jz      short loc_18000F16F
0x18000f159  mov     rcx, rax
0x18000f15c  inc     rcx
0x18000f15f  cmp     [r8+rcx*2], di
0x18000f164  jnz     short loc_18000F15C
0x18000f166  lea     ecx, ds:2[rcx*2]
0x18000f16d  jmp     short loc_18000F172
0x18000f16f  mov     ecx, r10d
0x18000f172  test    r8, r8
0x18000f175  mov     [rbp+47h+var_58], ecx
0x18000f178  mov     rcx, [rbp+47h+arg_20]
0x18000f17c  lea     rsi, aNull; "NULL"
0x18000f183  cmovz   r8, rsi
0x18000f187  mov     [rbp+47h+var_54], edi
0x18000f18a  mov     [rbp+47h+var_60], r8
0x18000f18e  mov     [rbp+47h+var_50], r9
0x18000f192  mov     [rbp+47h+var_48], 10h
0x18000f19a  test    rcx, rcx
0x18000f19d  jz      short loc_18000F1B4
0x18000f19f  mov     rdx, rax
0x18000f1a2  inc     rdx
0x18000f1a5  cmp     [rcx+rdx*2], di
0x18000f1a9  jnz     short loc_18000F1A2
0x18000f1ab  lea     edx, ds:2[rdx*2]
0x18000f1b2  jmp     short loc_18000F1B7
0x18000f1b4  mov     edx, r10d
0x18000f1b7  test    rcx, rcx
0x18000f1ba  mov     [rbp+47h+var_38], edx
0x18000f1bd  mov     [rbp+47h+var_34], edi
0x18000f1c0  cmovz   rcx, rsi
0x18000f1c4  mov     [rbp+47h+var_40], rcx
0x18000f1c8  mov     rcx, [rbp+47h+arg_28]
0x18000f1cc  test    rcx, rcx
0x18000f1cf  jz      short loc_18000F1E5
0x18000f1d1  inc     rax
0x18000f1d4  cmp     [rcx+rax*2], di
0x18000f1d8  jnz     short loc_18000F1D1
0x18000f1da  lea     r10d, ds:2[rax*2]
0x18000f1e2  test    rcx, rcx
0x18000f1e5  cmovz   rcx, rsi
0x18000f1e9  mov     [rbp+47h+var_28], r10d
0x18000f1ed  mov     [rbp+47h+var_30], rcx
0x18000f1f1  lea     rax, [rbp+47h+var_70]
0x18000f1f5  mov     rcx, r11
0x18000f1f8  mov     [rbp+47h+var_24], edi
0x18000f1fb  mov     r9d, 5
0x18000f201  mov     [rsp+0A0h+var_80], rax
0x18000f206  mov     rdx, rbx
0x18000f209  call    McGenEventWrite_EventWriteTransfer
0x18000f20e  mov     rcx, [rbp+47h+var_20]
0x18000f212  xor     rcx, rsp; StackCookie
0x18000f215  call    __security_check_cookie
0x18000f21a  mov     rbx, [rsp+0A0h+arg_10]
0x18000f222  add     rsp, 90h
0x18000f229  pop     rdi
0x18000f22a  pop     rsi
0x18000f22b  pop     rbp
0x18000f22c  retn
```
