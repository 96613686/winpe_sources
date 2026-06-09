# McTemplateU0xqbr1qqq_EventWriteTransfer

- ea: `0x180017bb0`
- end: `0x180017c62`
- name: `McTemplateU0xqbr1qqq_EventWriteTransfer`
- size: `178`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, __int64, char, char, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001468c`
- `0x180016094`

## callees

- `0x180001d40`
- `0x18000c224`

## pseudocode

```c
ULONG __fastcall McTemplateU0xqbr1qqq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        char a7,
        char a8)
{
  int v9; // [rsp+30h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v11; // [rsp+50h] [rbp-39h]
  __int64 v12; // [rsp+58h] [rbp-31h]
  int *v13; // [rsp+60h] [rbp-29h]
  __int64 v14; // [rsp+68h] [rbp-21h]
  __int64 v15; // [rsp+70h] [rbp-19h]
  __int64 v16; // [rsp+78h] [rbp-11h]
  char *v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  char *v19; // [rsp+90h] [rbp+7h]
  __int64 v20; // [rsp+98h] [rbp+Fh]
  char *v21; // [rsp+A0h] [rbp+17h]
  __int64 v22; // [rsp+A8h] [rbp+1Fh]
  __int64 v23; // [rsp+E0h] [rbp+57h] BYREF

  v23 = a3;
  v12 = 8;
  v9 = 16;
  v11 = &v23;
  v14 = 4;
  v13 = &v9;
  v15 = a5;
  v17 = &a6;
  v19 = &a7;
  v21 = &a8;
  v16 = 16;
  v18 = 4;
  v20 = 4;
  v22 = 4;
  return McGenEventWrite_EventWriteTransfer(16, (const EVENT_DESCRIPTOR *)IPXLATCFG_REMOTE_PREFIX_EVENT, a3, 7u, &v10);
}

```

## disassembly

```asm
0x180017bb0  mov     [rsp-8+arg_10], r8
0x180017bb5  push    rbp
0x180017bb6  lea     rbp, [rsp-37h]
0x180017bbb  sub     rsp, 0C0h
0x180017bc2  mov     rax, cs:__security_cookie
0x180017bc9  xor     rax, rsp
0x180017bcc  mov     [rbp+37h+var_10], rax
0x180017bd0  mov     ecx, 10h
0x180017bd5  mov     [rbp+37h+var_68], 8
0x180017bdd  lea     rax, [rbp+37h+arg_10]
0x180017be1  mov     [rbp+37h+var_90], ecx
0x180017be4  mov     [rbp+37h+var_70], rax
0x180017be8  lea     rdx, IPXLATCFG_REMOTE_PREFIX_EVENT
0x180017bef  lea     rax, [rbp+37h+var_90]
0x180017bf3  mov     [rbp+37h+var_58], 4
0x180017bfb  mov     [rbp+37h+var_60], rax
0x180017bff  lea     r9d, [rcx-9]
0x180017c03  mov     rax, [rbp+37h+arg_20]
0x180017c07  mov     [rbp+37h+var_50], rax
0x180017c0b  lea     rax, [rbp+37h+arg_28]
0x180017c0f  mov     [rbp+37h+var_40], rax
0x180017c13  lea     rax, [rbp+37h+arg_30]
0x180017c17  mov     [rbp+37h+var_30], rax
0x180017c1b  lea     rax, [rbp+37h+arg_38]
0x180017c1f  mov     [rbp+37h+var_20], rax
0x180017c23  lea     rax, [rbp+37h+var_80]
0x180017c27  mov     [rsp+0C0h+var_A0], rax
0x180017c2c  mov     [rbp+37h+var_48], rcx
0x180017c30  mov     [rbp+37h+var_38], 4
0x180017c38  mov     [rbp+37h+var_28], 4
0x180017c40  mov     [rbp+37h+var_18], 4
0x180017c48  call    McGenEventWrite_EventWriteTransfer
0x180017c4d  mov     rcx, [rbp+37h+var_10]
0x180017c51  xor     rcx, rsp; StackCookie
0x180017c54  call    __security_check_cookie
0x180017c59  add     rsp, 0C0h
0x180017c60  pop     rbp
0x180017c61  retn
```
