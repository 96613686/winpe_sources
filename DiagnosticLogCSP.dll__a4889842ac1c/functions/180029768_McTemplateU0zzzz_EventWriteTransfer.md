# McTemplateU0zzzz_EventWriteTransfer

- ea: `0x180029768`
- end: `0x180029896`
- name: `McTemplateU0zzzz_EventWriteTransfer`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800274b4`

## callees

- `0x180001b60`
- `0x180029710`
- `0x180029768`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  __int64 v6; // rax
  int v7; // r10d
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // ecx
  const wchar_t *v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  const wchar_t *v15; // rcx
  bool v16; // zf
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-9h]
  int v20; // [rsp+48h] [rbp-1h]
  int v21; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v22; // [rsp+50h] [rbp+7h]
  int v23; // [rsp+58h] [rbp+Fh]
  int v24; // [rsp+5Ch] [rbp+13h]
  const wchar_t *v25; // [rsp+60h] [rbp+17h]
  int v26; // [rsp+68h] [rbp+1Fh]
  int v27; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v28; // [rsp+70h] [rbp+27h]
  int v29; // [rsp+78h] [rbp+2Fh]
  int v30; // [rsp+7Ch] [rbp+33h]

  v6 = -1;
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
  v20 = v9;
  v21 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v19 = a3;
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
  v23 = v11;
  v12 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v24 = 0;
  v22 = a4;
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
  v26 = v14;
  v27 = 0;
  if ( !a5 )
    v12 = L"NULL";
  v25 = v12;
  v15 = a6;
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = 2 * v6 + 2;
    v16 = a6 == 0;
  }
  if ( v16 )
    v15 = L"NULL";
  v29 = v7;
  v28 = v15;
  v30 = 0;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v15,
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_Configuration,
           (__int64)a3,
           5u,
           &v18);
}

```

## disassembly

```asm
0x180029768  mov     [rsp-8+arg_0], rbx
0x18002976d  push    rbp
0x18002976e  lea     rbp, [rsp-47h]
0x180029773  sub     rsp, 90h
0x18002977a  mov     rax, cs:__security_cookie
0x180029781  xor     rax, rsp
0x180029784  mov     [rbp+47h+var_10], rax
0x180029788  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002978c  xor     r11d, r11d
0x18002978f  mov     r10d, 0Ah
0x180029795  test    r8, r8
0x180029798  jz      short loc_1800297B0
0x18002979a  mov     rcx, rax
0x18002979d  inc     rcx
0x1800297a0  cmp     [r8+rcx*2], r11w
0x1800297a5  jnz     short loc_18002979D
0x1800297a7  lea     ecx, ds:2[rcx*2]
0x1800297ae  jmp     short loc_1800297B3
0x1800297b0  mov     ecx, r10d
0x1800297b3  test    r8, r8
0x1800297b6  mov     [rbp+47h+var_48], ecx
0x1800297b9  lea     rbx, aNull; "NULL"
0x1800297c0  mov     [rbp+47h+var_44], r11d
0x1800297c4  cmovz   r8, rbx
0x1800297c8  mov     [rbp+47h+var_50], r8
0x1800297cc  test    r9, r9
0x1800297cf  jz      short loc_1800297E7
0x1800297d1  mov     rcx, rax
0x1800297d4  inc     rcx
0x1800297d7  cmp     [r9+rcx*2], r11w
0x1800297dc  jnz     short loc_1800297D4
0x1800297de  lea     ecx, ds:2[rcx*2]
0x1800297e5  jmp     short loc_1800297EA
0x1800297e7  mov     ecx, r10d
0x1800297ea  test    r9, r9
0x1800297ed  mov     [rbp+47h+var_38], ecx
0x1800297f0  mov     rcx, [rbp+47h+arg_20]
0x1800297f4  cmovz   r9, rbx
0x1800297f8  mov     [rbp+47h+var_34], r11d
0x1800297fc  mov     [rbp+47h+var_40], r9
0x180029800  test    rcx, rcx
0x180029803  jz      short loc_18002981B
0x180029805  mov     rdx, rax
0x180029808  inc     rdx
0x18002980b  cmp     [rcx+rdx*2], r11w
0x180029810  jnz     short loc_180029808
0x180029812  lea     edx, ds:2[rdx*2]
0x180029819  jmp     short loc_18002981E
0x18002981b  mov     edx, r10d
0x18002981e  test    rcx, rcx
0x180029821  mov     [rbp+47h+var_28], edx
0x180029824  mov     [rbp+47h+var_24], r11d
0x180029828  cmovz   rcx, rbx
0x18002982c  mov     [rbp+47h+var_30], rcx
0x180029830  mov     rcx, [rbp+47h+arg_28]
0x180029834  test    rcx, rcx
0x180029837  jz      short loc_18002984E
0x180029839  inc     rax
0x18002983c  cmp     [rcx+rax*2], r11w
0x180029841  jnz     short loc_180029839
0x180029843  lea     r10d, ds:2[rax*2]
0x18002984b  test    rcx, rcx
0x18002984e  cmovz   rcx, rbx
0x180029852  mov     [rbp+47h+var_18], r10d
0x180029856  lea     rax, [rbp+47h+var_60]
0x18002985a  mov     [rbp+47h+var_20], rcx
0x18002985e  mov     r9d, 5
0x180029864  mov     [rsp+90h+var_70], rax
0x180029869  lea     rdx, TraceMerge_NGEN_Configuration
0x180029870  mov     [rbp+47h+var_14], r11d
0x180029874  call    McGenEventWrite_EventWriteTransfer
0x180029879  mov     rcx, [rbp+47h+var_10]
0x18002987d  xor     rcx, rsp; StackCookie
0x180029880  call    __security_check_cookie
0x180029885  mov     rbx, [rsp+90h+arg_0]
0x18002988d  add     rsp, 90h
0x180029894  pop     rbp
0x180029895  retn
```
