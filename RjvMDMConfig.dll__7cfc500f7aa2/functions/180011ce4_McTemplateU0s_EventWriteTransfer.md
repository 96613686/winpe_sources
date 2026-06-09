# McTemplateU0s_EventWriteTransfer

- ea: `0x180011ce4`
- end: `0x180011d61`
- name: `McTemplateU0s_EventWriteTransfer`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000707c`
- `0x180007778`

## callees

- `0x180001c60`
- `0x180011b54`
- `0x180011ce4`

## pseudocode

```c
ULONG __fastcall McTemplateU0s_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const char *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180011ce4  sub     rsp, 68h
0x180011ce8  mov     rax, cs:__security_cookie
0x180011cef  xor     rax, rsp
0x180011cf2  mov     [rsp+68h+var_18], rax
0x180011cf7  test    r8, r8
0x180011cfa  jz      short loc_180011D0E
0x180011cfc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011d00  inc     rax
0x180011d03  cmp     byte ptr [r8+rax], 0
0x180011d08  jnz     short loc_180011D00
0x180011d0a  inc     eax
0x180011d0c  jmp     short loc_180011D13
0x180011d0e  mov     eax, 5
0x180011d13  test    r8, r8
0x180011d16  mov     [rsp+68h+var_20], eax
0x180011d1a  lea     rcx, aNull; "NULL"
0x180011d21  mov     [rsp+68h+var_1C], 0
0x180011d29  cmovz   r8, rcx
0x180011d2d  lea     rax, [rsp+68h+var_38]
0x180011d32  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180011d39  mov     [rsp+68h+var_28], r8
0x180011d3e  mov     r9d, 2
0x180011d44  mov     [rsp+68h+var_48], rax
0x180011d49  call    McGenEventWrite_EventWriteTransfer
0x180011d4e  mov     rcx, [rsp+68h+var_18]
0x180011d53  xor     rcx, rsp; StackCookie
0x180011d56  call    __security_check_cookie
0x180011d5b  add     rsp, 68h
0x180011d5f  retn
```
