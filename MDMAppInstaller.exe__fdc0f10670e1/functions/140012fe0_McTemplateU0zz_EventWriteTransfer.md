# McTemplateU0zz_EventWriteTransfer

- ea: `0x140012fe0`
- end: `0x140013093`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a5e0`
- `0x14000e6cc`

## callees

- `0x140006d70`
- `0x140012fe0`
- `0x14001a8d0`

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
0x140012fe0  push    rbx
0x140012fe2  sub     rsp, 70h
0x140012fe6  mov     rax, cs:__security_cookie
0x140012fed  xor     rax, rsp
0x140012ff0  mov     [rsp+78h+var_18], rax
0x140012ff5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012ff9  xor     r11d, r11d
0x140012ffc  mov     r10, rdx
0x140012fff  mov     edx, 0Ah
0x140013004  test    r8, r8
0x140013007  jz      short loc_14001301F
0x140013009  mov     rcx, rax
0x14001300c  inc     rcx
0x14001300f  cmp     [r8+rcx*2], r11w
0x140013014  jnz     short loc_14001300C
0x140013016  lea     ecx, ds:2[rcx*2]
0x14001301d  jmp     short loc_140013021
0x14001301f  mov     ecx, edx
0x140013021  test    r8, r8
0x140013024  mov     [rsp+78h+var_30], ecx
0x140013028  lea     rbx, aNull; "NULL"
0x14001302f  mov     [rsp+78h+var_2C], r11d
0x140013034  cmovz   r8, rbx
0x140013038  mov     [rsp+78h+var_38], r8
0x14001303d  test    r9, r9
0x140013040  jz      short loc_140013056
0x140013042  inc     rax
0x140013045  cmp     [r9+rax*2], r11w
0x14001304a  jnz     short loc_140013042
0x14001304c  lea     edx, ds:2[rax*2]
0x140013053  test    r9, r9
0x140013056  cmovz   r9, rbx
0x14001305a  mov     [rsp+78h+var_20], edx
0x14001305e  mov     [rsp+78h+var_28], r9
0x140013063  lea     rax, [rsp+78h+var_48]
0x140013068  mov     r9d, 3
0x14001306e  mov     [rsp+78h+var_1C], r11d
0x140013073  mov     rdx, r10
0x140013076  mov     [rsp+78h+var_58], rax
0x14001307b  call    McGenEventWrite_EventWriteTransfer
0x140013080  mov     rcx, [rsp+78h+var_18]
0x140013085  xor     rcx, rsp; StackCookie
0x140013088  call    __security_check_cookie
0x14001308d  add     rsp, 70h
0x140013091  pop     rbx
0x140013092  retn
```
