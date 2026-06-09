# McTemplateU0xqb16qb16q_EventWriteTransfer

- ea: `0x180012430`
- end: `0x1800124de`
- name: `McTemplateU0xqb16qb16q_EventWriteTransfer`
- size: `174`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, int, __int64, char, __int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f668`
- `0x1800128d0`

## callees

- `0x180001d40`
- `0x18000c224`

## pseudocode

```c
ULONG __fastcall McTemplateU0xqb16qb16q_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        char a6,
        __int64 a7,
        char a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-49h] BYREF
  __int64 *v10; // [rsp+40h] [rbp-39h]
  __int64 v11; // [rsp+48h] [rbp-31h]
  int *v12; // [rsp+50h] [rbp-29h]
  __int64 v13; // [rsp+58h] [rbp-21h]
  __int64 v14; // [rsp+60h] [rbp-19h]
  __int64 v15; // [rsp+68h] [rbp-11h]
  char *v16; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  __int64 v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  char *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]
  __int64 v22; // [rsp+D0h] [rbp+57h] BYREF
  int v23; // [rsp+D8h] [rbp+5Fh] BYREF

  v23 = a4;
  v22 = a3;
  v11 = 8;
  v10 = &v22;
  v13 = 4;
  v12 = &v23;
  v14 = a5;
  v16 = &a6;
  v18 = a7;
  v20 = &a8;
  v15 = 16;
  v17 = 4;
  v19 = 16;
  v21 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 7u, &v9);
}

```

## disassembly

```asm
0x180012430  mov     [rsp-8+arg_18], r9d
0x180012435  mov     [rsp-8+arg_10], r8
0x18001243a  push    rbp
0x18001243b  lea     rbp, [rsp-37h]
0x180012440  sub     rsp, 0B0h
0x180012447  mov     rax, cs:__security_cookie
0x18001244e  xor     rax, rsp
0x180012451  mov     [rbp+37h+var_10], rax
0x180012455  lea     rax, [rbp+37h+arg_10]
0x180012459  mov     [rbp+37h+var_68], 8
0x180012461  mov     [rbp+37h+var_70], rax
0x180012465  mov     r9d, 7
0x18001246b  lea     rax, [rbp+37h+arg_18]
0x18001246f  mov     [rbp+37h+var_58], 4
0x180012477  mov     [rbp+37h+var_60], rax
0x18001247b  mov     rax, [rbp+37h+arg_20]
0x18001247f  mov     [rbp+37h+var_50], rax
0x180012483  lea     rax, [rbp+37h+arg_28]
0x180012487  mov     [rbp+37h+var_40], rax
0x18001248b  mov     rax, [rbp+37h+arg_30]
0x18001248f  mov     [rbp+37h+var_30], rax
0x180012493  lea     rax, [rbp+37h+arg_38]
0x180012497  mov     [rbp+37h+var_20], rax
0x18001249b  lea     rax, [rbp+37h+var_80]
0x18001249f  mov     [rsp+0B0h+var_90], rax
0x1800124a4  mov     [rbp+37h+var_48], 10h
0x1800124ac  mov     [rbp+37h+var_38], 4
0x1800124b4  mov     [rbp+37h+var_28], 10h
0x1800124bc  mov     [rbp+37h+var_18], 4
0x1800124c4  call    McGenEventWrite_EventWriteTransfer
0x1800124c9  mov     rcx, [rbp+37h+var_10]
0x1800124cd  xor     rcx, rsp; StackCookie
0x1800124d0  call    __security_check_cookie
0x1800124d5  add     rsp, 0B0h
0x1800124dc  pop     rbp
0x1800124dd  retn
```
