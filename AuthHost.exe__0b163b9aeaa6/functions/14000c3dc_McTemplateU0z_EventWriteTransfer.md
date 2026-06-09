# McTemplateU0z_EventWriteTransfer

- ea: `0x14000c3dc`
- end: `0x14000c456`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140009dd0`
- `0x140009e50`
- `0x14000a210`
- `0x14000a330`
- `0x14000a950`
- `0x140010900`
- `0x140011aa4`
- `0x140012500`

## callees

- `0x140006748`
- `0x14000c3dc`
- `0x140012f60`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x14000c3dc  sub     rsp, 68h
0x14000c3e0  mov     rax, cs:__security_cookie
0x14000c3e7  xor     rax, rsp
0x14000c3ea  mov     [rsp+68h+var_18], rax
0x14000c3ef  xor     r9d, r9d
0x14000c3f2  test    r8, r8
0x14000c3f5  jz      short loc_14000C40E
0x14000c3f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c3fb  inc     rax
0x14000c3fe  cmp     [r8+rax*2], r9w
0x14000c403  jnz     short loc_14000C3FB
0x14000c405  lea     eax, ds:2[rax*2]
0x14000c40c  jmp     short loc_14000C413
0x14000c40e  mov     eax, 0Ah
0x14000c413  test    r8, r8
0x14000c416  mov     [rsp+68h+var_20], eax
0x14000c41a  lea     rcx, aNull_0; "NULL"
0x14000c421  mov     [rsp+68h+var_1C], r9d
0x14000c426  cmovz   r8, rcx
0x14000c42a  lea     rax, [rsp+68h+var_38]
0x14000c42f  mov     r9d, 2
0x14000c435  mov     [rsp+68h+var_28], r8
0x14000c43a  mov     [rsp+68h+var_48], rax
0x14000c43f  call    McGenEventWrite_EventWriteTransfer
0x14000c444  mov     rcx, [rsp+68h+var_18]
0x14000c449  xor     rcx, rsp; StackCookie
0x14000c44c  call    __security_check_cookie
0x14000c451  add     rsp, 68h
0x14000c455  retn
```
