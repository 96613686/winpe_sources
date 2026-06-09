# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000bdec`
- end: `0x18000bea6`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006320`
- `0x18000d060`
- `0x180011fb0`

## callees

- `0x180004d70`
- `0x18000bdec`
- `0x180013700`

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
  int v8; // ecx
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
    v8 = 2 * v7 + 2;
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
  return McGenEventWrite_EventWriteTransfer(userpnp_Context, a2, (__int64)a3, 3u, &v11);
}

```

## disassembly

```asm
0x18000bdec  push    rbx
0x18000bdee  sub     rsp, 70h
0x18000bdf2  mov     rax, cs:__security_cookie
0x18000bdf9  xor     rax, rsp
0x18000bdfc  mov     [rsp+78h+var_18], rax
0x18000be01  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000be05  xor     r11d, r11d
0x18000be08  mov     r10, rdx
0x18000be0b  mov     edx, 0Ah
0x18000be10  test    r8, r8
0x18000be13  jz      short loc_18000BE2B
0x18000be15  mov     rcx, rax
0x18000be18  inc     rcx
0x18000be1b  cmp     [r8+rcx*2], r11w
0x18000be20  jnz     short loc_18000BE18
0x18000be22  lea     ecx, ds:2[rcx*2]
0x18000be29  jmp     short loc_18000BE2D
0x18000be2b  mov     ecx, edx
0x18000be2d  test    r8, r8
0x18000be30  mov     [rsp+78h+var_30], ecx
0x18000be34  lea     rbx, aNull; "NULL"
0x18000be3b  mov     [rsp+78h+var_2C], r11d
0x18000be40  cmovz   r8, rbx
0x18000be44  mov     [rsp+78h+var_38], r8
0x18000be49  test    r9, r9
0x18000be4c  jz      short loc_18000BE62
0x18000be4e  inc     rax
0x18000be51  cmp     [r9+rax*2], r11w
0x18000be56  jnz     short loc_18000BE4E
0x18000be58  lea     edx, ds:2[rax*2]
0x18000be5f  test    r9, r9
0x18000be62  cmovz   r9, rbx
0x18000be66  mov     [rsp+78h+var_20], edx
0x18000be6a  mov     [rsp+78h+var_28], r9
0x18000be6f  lea     rax, [rsp+78h+var_48]
0x18000be74  mov     r9d, 3
0x18000be7a  mov     [rsp+78h+var_1C], r11d
0x18000be7f  mov     rdx, r10
0x18000be82  mov     [rsp+78h+var_58], rax
0x18000be87  lea     rcx, userpnp_Context
0x18000be8e  call    McGenEventWrite_EventWriteTransfer
0x18000be93  mov     rcx, [rsp+78h+var_18]
0x18000be98  xor     rcx, rsp; StackCookie
0x18000be9b  call    __security_check_cookie
0x18000bea0  add     rsp, 70h
0x18000bea4  pop     rbx
0x18000bea5  retn
```
