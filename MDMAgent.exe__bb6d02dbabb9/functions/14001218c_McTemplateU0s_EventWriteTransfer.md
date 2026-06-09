# McTemplateU0s_EventWriteTransfer

- ea: `0x14001218c`
- end: `0x140012209`
- name: `McTemplateU0s_EventWriteTransfer`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140009004`
- `0x1400094bc`

## callees

- `0x1400029c0`
- `0x140011ffc`
- `0x14001218c`

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
0x14001218c  sub     rsp, 68h
0x140012190  mov     rax, cs:__security_cookie
0x140012197  xor     rax, rsp
0x14001219a  mov     [rsp+68h+var_18], rax
0x14001219f  test    r8, r8
0x1400121a2  jz      short loc_1400121B6
0x1400121a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400121a8  inc     rax
0x1400121ab  cmp     byte ptr [r8+rax], 0
0x1400121b0  jnz     short loc_1400121A8
0x1400121b2  inc     eax
0x1400121b4  jmp     short loc_1400121BB
0x1400121b6  mov     eax, 5
0x1400121bb  test    r8, r8
0x1400121be  mov     [rsp+68h+var_20], eax
0x1400121c2  lea     rcx, aNull; "NULL"
0x1400121c9  mov     [rsp+68h+var_1C], 0
0x1400121d1  cmovz   r8, rcx
0x1400121d5  lea     rax, [rsp+68h+var_38]
0x1400121da  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x1400121e1  mov     [rsp+68h+var_28], r8
0x1400121e6  mov     r9d, 2
0x1400121ec  mov     [rsp+68h+var_48], rax
0x1400121f1  call    McGenEventWrite_EventWriteTransfer
0x1400121f6  mov     rcx, [rsp+68h+var_18]
0x1400121fb  xor     rcx, rsp; StackCookie
0x1400121fe  call    __security_check_cookie
0x140012203  add     rsp, 68h
0x140012207  retn
```
