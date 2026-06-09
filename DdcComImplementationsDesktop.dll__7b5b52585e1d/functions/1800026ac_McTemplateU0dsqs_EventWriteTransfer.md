# McTemplateU0dsqs_EventWriteTransfer

- ea: `0x1800026ac`
- end: `0x180002771`
- name: `McTemplateU0dsqs_EventWriteTransfer`
- size: `197`
- prototype: `ULONG __fastcall(__int64, __int64, int, const char *, char, const char *)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x1800023d0`
- `0x180002880`
- `0x1800029e0`
- `0x180002bd0`
- `0x180002c50`
- `0x180002f10`
- `0x180003210`
- `0x180003520`
- `0x180003680`
- `0x1800040b8`
- `0x180004128`
- `0x180004218`
- `0x18000450c`
- `0x18000456c`
- `0x180004684`
- `0x1800047f8`
- `0x18000b1e4`

## callees

- `0x1800016b0`
- `0x18000264c`
- `0x1800026ac`

## pseudocode

```c
ULONG __fastcall McTemplateU0dsqs_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const char *a4,
        char a5,
        const char *a6)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // ecx
  const char *v10; // rcx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-19h] BYREF
  int *v14; // [rsp+40h] [rbp-9h]
  __int64 v15; // [rsp+48h] [rbp-1h]
  const char *v16; // [rsp+50h] [rbp+7h]
  int v17; // [rsp+58h] [rbp+Fh]
  int v18; // [rsp+5Ch] [rbp+13h]
  char *v19; // [rsp+60h] [rbp+17h]
  __int64 v20; // [rsp+68h] [rbp+1Fh]
  const char *v21; // [rsp+70h] [rbp+27h]
  int v22; // [rsp+78h] [rbp+2Fh]
  int v23; // [rsp+7Ch] [rbp+33h]
  int v24; // [rsp+B0h] [rbp+67h] BYREF

  v24 = a3;
  v15 = 4;
  v14 = &v24;
  v6 = -1;
  v7 = 5;
  if ( a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a4[v8] );
    v9 = v8 + 1;
  }
  else
  {
    v9 = 5;
  }
  v17 = v9;
  v18 = 0;
  v19 = &a5;
  v10 = a6;
  if ( !a4 )
    a4 = "NULL";
  v20 = 4;
  v16 = a4;
  v11 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v7 = (unsigned int)(v6 + 1);
    v11 = a6 == 0;
  }
  if ( v11 )
    v10 = "NULL";
  v22 = v7;
  v21 = v10;
  v23 = 0;
  return McGenEventWrite_EventWriteTransfer((__int64)v10, v7, 0, (__int64)a4, &v13);
}

```

## disassembly

```asm
0x1800026ac  mov     [rsp-8+arg_10], r8d
0x1800026b1  push    rbp
0x1800026b2  lea     rbp, [rsp-47h]
0x1800026b7  sub     rsp, 90h
0x1800026be  mov     rax, cs:__security_cookie
0x1800026c5  xor     rax, rsp
0x1800026c8  mov     [rbp+47h+var_10], rax
0x1800026cc  lea     rax, [rbp+47h+arg_10]
0x1800026d0  mov     [rbp+47h+var_48], 4
0x1800026d8  xor     r8d, r8d; int
0x1800026db  mov     [rbp+47h+var_50], rax
0x1800026df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800026e3  lea     edx, [r8+5]
0x1800026e7  test    r9, r9
0x1800026ea  jz      short loc_1800026FC
0x1800026ec  mov     rcx, rax
0x1800026ef  inc     rcx
0x1800026f2  cmp     [r9+rcx], r8b
0x1800026f6  jnz     short loc_1800026EF
0x1800026f8  inc     ecx
0x1800026fa  jmp     short loc_1800026FE
0x1800026fc  mov     ecx, edx
0x1800026fe  mov     [rbp+47h+var_38], ecx
0x180002701  lea     r11, aNull; "NULL"
0x180002708  lea     rcx, [rbp+47h+arg_20]
0x18000270c  mov     [rbp+47h+var_34], r8d
0x180002710  test    r9, r9
0x180002713  mov     [rbp+47h+var_30], rcx
0x180002717  mov     rcx, [rbp+47h+arg_28]
0x18000271b  cmovz   r9, r11; int
0x18000271f  mov     [rbp+47h+var_28], 4
0x180002727  mov     [rbp+47h+var_40], r9
0x18000272b  test    rcx, rcx
0x18000272e  jz      short loc_18000273F
0x180002730  inc     rax
0x180002733  cmp     [rcx+rax], r8b
0x180002737  jnz     short loc_180002730
0x180002739  lea     edx, [rax+1]; int
0x18000273c  test    rcx, rcx
0x18000273f  cmovz   rcx, r11; int
0x180002743  mov     [rbp+47h+var_18], edx
0x180002746  lea     rax, [rbp+47h+var_60]
0x18000274a  mov     [rbp+47h+var_20], rcx
0x18000274e  mov     [rsp+90h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180002753  mov     [rbp+47h+var_14], r8d
0x180002757  call    McGenEventWrite_EventWriteTransfer
0x18000275c  mov     rcx, [rbp+47h+var_10]
0x180002760  xor     rcx, rsp; StackCookie
0x180002763  call    __security_check_cookie
0x180002768  add     rsp, 90h
0x18000276f  pop     rbp
0x180002770  retn
```
