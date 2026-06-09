# McTemplateU0z_EventWriteTransfer

- ea: `0x180019d98`
- end: `0x180019e12`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180009424`
- `0x18000b32c`
- `0x18000b3c4`

## callees

- `0x18000b448`
- `0x180019d98`
- `0x18001a380`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
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
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180019d98  sub     rsp, 68h
0x180019d9c  mov     rax, cs:__security_cookie
0x180019da3  xor     rax, rsp
0x180019da6  mov     [rsp+68h+var_18], rax
0x180019dab  xor     r10d, r10d
0x180019dae  test    r8, r8
0x180019db1  jz      short loc_180019DCA
0x180019db3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019db7  inc     rax
0x180019dba  cmp     [r8+rax*2], r10w
0x180019dbf  jnz     short loc_180019DB7
0x180019dc1  lea     eax, ds:2[rax*2]
0x180019dc8  jmp     short loc_180019DCF
0x180019dca  mov     eax, 0Ah
0x180019dcf  lea     r9, aNull_1; "NULL"
0x180019dd6  mov     [rsp+68h+var_20], eax
0x180019dda  test    r8, r8
0x180019ddd  mov     [rsp+68h+var_1C], r10d
0x180019de2  lea     rax, [rsp+68h+var_38]
0x180019de7  cmovz   r8, r9
0x180019deb  mov     [rsp+68h+var_48], rax
0x180019df0  mov     r9d, 2
0x180019df6  mov     [rsp+68h+var_28], r8
0x180019dfb  call    McGenEventWrite_EventWriteTransfer
0x180019e00  mov     rcx, [rsp+68h+var_18]
0x180019e05  xor     rcx, rsp; StackCookie
0x180019e08  call    __security_check_cookie
0x180019e0d  add     rsp, 68h
0x180019e11  retn
```
