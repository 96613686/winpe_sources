# McTemplateU0zz_EtwEventWriteTransfer

- ea: `0x180007bc0`
- end: `0x180007c7b`
- name: `McTemplateU0zz_EtwEventWriteTransfer`
- size: `187`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *, const wchar_t *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002560`
- `0x18000caa0`
- `0x18000d51c`
- `0x1800148fc`
- `0x180015c94`
- `0x180016b9c`

## callees

- `0x180007bc0`
- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0zz_EtwEventWriteTransfer(__int64 a1, int a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v5; // rdx
  int v6; // ecx
  __int64 v7; // rax
  int v8; // eax
  bool v9; // zf
  _BYTE v11[16]; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v15; // [rsp+50h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+5Ch] [rbp-1Ch]

  v5 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      v9 = a3[++v7] == 0;
    while ( !v9 );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v13 = v8;
  if ( !a3 )
    a3 = L"NULL";
  v12 = a3;
  v14 = 0;
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      v9 = a4[++v5] == 0;
    while ( !v9 );
    v6 = 2 * v5 + 2;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = L"NULL";
  v17 = 0;
  v15 = a4;
  v16 = v6;
  return McGenEventWrite_EtwEventWriteTransfer(v6, a2, (_DWORD)a3, 3, (__int64)v11);
}

```

## disassembly

```asm
0x180007bc0  sub     rsp, 78h
0x180007bc4  mov     rax, cs:__security_cookie
0x180007bcb  xor     rax, rsp
0x180007bce  mov     [rsp+78h+var_18], rax
0x180007bd3  mov     r10, rdx
0x180007bd6  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180007bdd  mov     ecx, 0Ah
0x180007be2  test    r8, r8
0x180007be5  jz      short loc_180007C06
0x180007be7  mov     rax, rdx
0x180007bea  nop     word ptr [rax+rax+00h]
0x180007bf0  cmp     word ptr [r8+rax*2+2], 0
0x180007bf7  lea     rax, [rax+1]
0x180007bfb  jnz     short loc_180007BF0
0x180007bfd  lea     eax, ds:2[rax*2]
0x180007c04  jmp     short loc_180007C08
0x180007c06  mov     eax, ecx
0x180007c08  test    r8, r8
0x180007c0b  mov     [rsp+78h+var_30], eax
0x180007c0f  lea     r11, aNull_1; "NULL"
0x180007c16  cmovz   r8, r11
0x180007c1a  xor     eax, eax
0x180007c1c  mov     [rsp+78h+var_38], r8
0x180007c21  mov     [rsp+78h+var_2C], eax
0x180007c25  test    r9, r9
0x180007c28  jz      short loc_180007C40
0x180007c2a  cmp     [r9+rdx*2+2], ax
0x180007c30  lea     rdx, [rdx+1]
0x180007c34  jnz     short loc_180007C2A
0x180007c36  lea     ecx, ds:2[rdx*2]
0x180007c3d  test    r9, r9
0x180007c40  cmovz   r9, r11
0x180007c44  mov     [rsp+78h+var_1C], eax
0x180007c48  mov     [rsp+78h+var_28], r9
0x180007c4d  lea     rax, [rsp+78h+var_48]
0x180007c52  mov     r9d, 3
0x180007c58  mov     [rsp+78h+var_20], ecx
0x180007c5c  mov     rdx, r10
0x180007c5f  mov     [rsp+78h+var_58], rax
0x180007c64  call    McGenEventWrite_EtwEventWriteTransfer
0x180007c69  mov     rcx, [rsp+78h+var_18]
0x180007c6e  xor     rcx, rsp; StackCookie
0x180007c71  call    __security_check_cookie
0x180007c76  add     rsp, 78h
0x180007c7a  retn
```
