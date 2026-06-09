# McTemplateU0ssd_EventWriteTransfer

- ea: `0x18000390c`
- end: `0x1800039cc`
- name: `McTemplateU0ssd_EventWriteTransfer`
- size: `192`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, const char *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002bd4`

## callees

- `0x180001730`
- `0x18000375c`
- `0x18000390c`

## pseudocode

```c
ULONG __fastcall McTemplateU0ssd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        const char *a4,
        char a5)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-58h] BYREF
  const char *v13; // [rsp+40h] [rbp-48h]
  int v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+4Ch] [rbp-3Ch]
  const char *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  char *v19; // [rsp+60h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-20h]

  v5 = -1;
  v7 = 5;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(v8 + 1);
  }
  else
  {
    v9 = 5;
  }
  v14 = v9;
  v15 = 0;
  if ( !a3 )
    a3 = "NULL";
  v13 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v7 = v5 + 1;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = "NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v20 = 4;
  v18 = 0;
  return McGenEventWrite_EventWriteTransfer(v9, a2, (__int64)a3, 4u, &v12);
}

```

## disassembly

```asm
0x18000390c  push    rbx
0x18000390e  sub     rsp, 80h
0x180003915  mov     rax, cs:__security_cookie
0x18000391c  xor     rax, rsp
0x18000391f  mov     [rsp+88h+var_18], rax
0x180003924  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003928  xor     r11d, r11d
0x18000392b  mov     r10, rdx
0x18000392e  mov     edx, 5
0x180003933  test    r8, r8
0x180003936  jz      short loc_180003948
0x180003938  mov     rcx, rax
0x18000393b  inc     rcx
0x18000393e  cmp     [r8+rcx], r11b
0x180003942  jnz     short loc_18000393B
0x180003944  inc     ecx
0x180003946  jmp     short loc_18000394A
0x180003948  mov     ecx, edx
0x18000394a  test    r8, r8
0x18000394d  mov     [rsp+88h+var_40], ecx
0x180003951  lea     rbx, aNull; "NULL"
0x180003958  mov     [rsp+88h+var_3C], r11d
0x18000395d  cmovz   r8, rbx
0x180003961  mov     [rsp+88h+var_48], r8
0x180003966  test    r9, r9
0x180003969  jz      short loc_18000397A
0x18000396b  inc     rax
0x18000396e  cmp     [r9+rax], r11b
0x180003972  jnz     short loc_18000396B
0x180003974  lea     edx, [rax+1]
0x180003977  test    r9, r9
0x18000397a  cmovz   r9, rbx
0x18000397e  mov     [rsp+88h+var_30], edx
0x180003982  lea     rax, [rsp+88h+arg_20]
0x18000398a  mov     [rsp+88h+var_38], r9
0x18000398f  mov     [rsp+88h+var_28], rax
0x180003994  mov     r9d, 4
0x18000399a  lea     rax, [rsp+88h+var_58]
0x18000399f  mov     [rsp+88h+var_20], r9
0x1800039a4  mov     rdx, r10
0x1800039a7  mov     [rsp+88h+var_68], rax
0x1800039ac  mov     [rsp+88h+var_2C], r11d
0x1800039b1  call    McGenEventWrite_EventWriteTransfer
0x1800039b6  mov     rcx, [rsp+88h+var_18]
0x1800039bb  xor     rcx, rsp; StackCookie
0x1800039be  call    __security_check_cookie
0x1800039c3  add     rsp, 80h
0x1800039ca  pop     rbx
0x1800039cb  retn
```
