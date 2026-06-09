# McTemplateU0sqx_EventWriteTransfer

- ea: `0x180012388`
- end: `0x180012427`
- name: `McTemplateU0sqx_EventWriteTransfer`
- size: `159`
- prototype: `ULONG __fastcall(__int64, __int64, const char *, int, char)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f668`
- `0x18000f9f0`
- `0x180010c8c`
- `0x180014344`
- `0x18001468c`
- `0x1800151f4`
- `0x180015340`
- `0x1800156dc`
- `0x1800158d0`
- `0x180015a1c`
- `0x180016094`
- `0x1800163d0`
- `0x18001667c`
- `0x180016860`
- `0x180016a94`
- `0x180016d2c`
- `0x180016f84`
- `0x1800172a4`
- `0x18001879f`
- `0x18001881f`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x180012388`

## pseudocode

```c
ULONG __fastcall McTemplateU0sqx_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, int a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  const char *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A8h] [rbp+28h] BYREF

  v16 = a4;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v10 = v6;
  v11 = 0;
  v12 = &v16;
  v15 = 8;
  v14 = &a5;
  if ( !a3 )
    a3 = "NULL";
  v9 = a3;
  v13 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)"NULL",
           (const EVENT_DESCRIPTOR *)IPXLATCFG_INTERFACE_ERROR_EVENT,
           (__int64)a3,
           4u,
           &v8);
}

```

## disassembly

```asm
0x180012388  mov     [rsp-8+arg_18], r9d
0x18001238d  push    rbp
0x18001238e  mov     rbp, rsp
0x180012391  sub     rsp, 80h
0x180012398  mov     rax, cs:__security_cookie
0x18001239f  xor     rax, rsp
0x1800123a2  mov     [rbp+var_10], rax
0x1800123a6  xor     edx, edx
0x1800123a8  test    r8, r8
0x1800123ab  jz      short loc_1800123BE
0x1800123ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800123b1  inc     rax
0x1800123b4  cmp     [r8+rax], dl
0x1800123b8  jnz     short loc_1800123B1
0x1800123ba  inc     eax
0x1800123bc  jmp     short loc_1800123C3
0x1800123be  mov     eax, 5
0x1800123c3  mov     [rbp+var_38], eax
0x1800123c6  lea     rcx, aNull; "NULL"
0x1800123cd  lea     rax, [rbp+arg_18]
0x1800123d1  mov     [rbp+var_34], edx
0x1800123d4  mov     [rbp+var_30], rax
0x1800123d8  lea     rdx, IPXLATCFG_INTERFACE_ERROR_EVENT
0x1800123df  lea     rax, [rbp+arg_20]
0x1800123e3  mov     [rbp+var_18], 8
0x1800123eb  test    r8, r8
0x1800123ee  mov     [rbp+var_20], rax
0x1800123f2  lea     rax, [rbp+var_50]
0x1800123f6  mov     r9d, 4
0x1800123fc  cmovz   r8, rcx
0x180012400  mov     [rsp+80h+var_60], rax
0x180012405  mov     [rbp+var_40], r8
0x180012409  mov     [rbp+var_28], r9
0x18001240d  call    McGenEventWrite_EventWriteTransfer
0x180012412  mov     rcx, [rbp+var_10]
0x180012416  xor     rcx, rsp; StackCookie
0x180012419  call    __security_check_cookie
0x18001241e  add     rsp, 80h
0x180012425  pop     rbp
0x180012426  retn
```
