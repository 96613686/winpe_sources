# McTemplateU0s_EventWriteTransfer

- ea: `0x140011980`
- end: `0x1400119fc`
- name: `McTemplateU0s_EventWriteTransfer`
- size: `124`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008bf4`
- `0x1400090d4`

## callees

- `0x140002930`
- `0x1400117fc`
- `0x140011980`

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
0x140011980  sub     rsp, 68h
0x140011984  mov     rax, cs:__security_cookie
0x14001198b  xor     rax, rsp
0x14001198e  mov     [rsp+68h+var_18], rax
0x140011993  test    r8, r8
0x140011996  jz      short loc_1400119AA
0x140011998  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001199c  inc     rax
0x14001199f  cmp     byte ptr [r8+rax], 0
0x1400119a4  jnz     short loc_14001199C
0x1400119a6  inc     eax
0x1400119a8  jmp     short loc_1400119AF
0x1400119aa  mov     eax, 5
0x1400119af  test    r8, r8
0x1400119b2  mov     [rsp+68h+var_20], eax
0x1400119b6  lea     rcx, aNull; "NULL"
0x1400119bd  mov     [rsp+68h+var_1C], 0
0x1400119c5  cmovz   r8, rcx
0x1400119c9  lea     rax, [rsp+68h+var_38]
0x1400119ce  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x1400119d5  mov     [rsp+68h+var_28], r8
0x1400119da  mov     r9d, 2
0x1400119e0  mov     [rsp+68h+var_48], rax
0x1400119e5  call    McGenEventWrite_EventWriteTransfer
0x1400119ea  mov     rcx, [rsp+68h+var_18]
0x1400119ef  xor     rcx, rsp; StackCookie
0x1400119f2  call    __security_check_cookie
0x1400119f7  add     rsp, 68h
0x1400119fb  retn
```
