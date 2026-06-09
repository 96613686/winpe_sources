# McTemplateU0dsqs_EventWriteTransfer

- ea: `0x1800065c0`
- end: `0x180006691`
- name: `McTemplateU0dsqs_EventWriteTransfer`
- size: `209`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, char, const char *, ...)`
- caller_count: `123`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800030c0`
- `0x1800034c0`
- `0x1800035e0`
- `0x1800036d0`
- `0x180003940`
- `0x180003a30`
- `0x180003d50`
- `0x180003fa0`
- `0x1800040d0`
- `0x1800043e0`
- `0x180004550`
- `0x180004a10`
- `0x180004b90`
- `0x180004ca0`
- `0x1800050a0`
- `0x1800053b0`
- `0x1800054a0`
- `0x1800055a0`
- `0x1800056c0`
- `0x1800057e0`
- `0x1800058b0`
- `0x180005a60`
- `0x180005d00`
- `0x180005ea0`
- `0x18000685c`
- `0x1800069e8`
- `0x180006b24`
- `0x1800074e4`
- `0x180007974`
- `0x1800080a4`
- `0x180008154`
- `0x180008438`
- `0x180008908`
- `0x1800089b8`
- `0x180008a6c`
- `0x180008be0`
- `0x180008efc`
- `0x180009d18`
- `0x18000a528`
- `0x18000addc`
- `0x18000b0e4`
- `0x18000b634`
- `0x18000bb9c`
- `0x18000bd94`
- `0x18000c6e8`
- `0x18000edc0`
- `0x18000f3b8`
- `0x180010adc`
- `0x180010eb4`
- `0x18001134c`

## callees

- `0x180001520`
- `0x180006560`
- `0x1800065c0`

## pseudocode

```c
ULONG McTemplateU0dsqs_EventWriteTransfer(_DWORD a1, _DWORD a2, int a3, const char *a4, char a5, const char *a6, ...)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // ecx
  const char *v9; // rcx
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-19h] BYREF
  int *v13; // [rsp+40h] [rbp-9h]
  __int64 v14; // [rsp+48h] [rbp-1h]
  const char *v15; // [rsp+50h] [rbp+7h]
  int v16; // [rsp+58h] [rbp+Fh]
  int v17; // [rsp+5Ch] [rbp+13h]
  char *v18; // [rsp+60h] [rbp+17h]
  __int64 v19; // [rsp+68h] [rbp+1Fh]
  const char *v20; // [rsp+70h] [rbp+27h]
  int v21; // [rsp+78h] [rbp+2Fh]
  int v22; // [rsp+7Ch] [rbp+33h]
  int v23; // [rsp+B0h] [rbp+67h] BYREF

  v23 = a3;
  v14 = 4;
  v13 = &v23;
  v6 = -1;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  v16 = v8;
  v17 = 0;
  v18 = &a5;
  v9 = a6;
  if ( !a4 )
    a4 = "NULL";
  v19 = 4;
  v15 = a4;
  if ( a6 )
  {
    do
      ++v6;
    while ( a6[v6] );
    v10 = v6 + 1;
  }
  else
  {
    v10 = 5;
  }
  v21 = v10;
  v22 = 0;
  if ( !a6 )
    v9 = "NULL";
  v20 = v9;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v9,
           (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_EHM_FAILED,
           5,
           5u,
           &v12);
}

```

## disassembly

```asm
0x1800065c0  mov     [rsp-8+arg_10], r8d
0x1800065c5  push    rbp
0x1800065c6  lea     rbp, [rsp-47h]
0x1800065cb  sub     rsp, 90h
0x1800065d2  mov     rax, cs:__security_cookie
0x1800065d9  xor     rax, rsp
0x1800065dc  mov     [rbp+47h+var_10], rax
0x1800065e0  lea     rax, [rbp+47h+arg_10]
0x1800065e4  mov     [rbp+47h+var_48], 4
0x1800065ec  xor     edx, edx
0x1800065ee  mov     [rbp+47h+var_50], rax
0x1800065f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800065f6  lea     r8d, [rdx+5]
0x1800065fa  test    r9, r9
0x1800065fd  jz      short loc_18000660F
0x1800065ff  mov     rcx, rax
0x180006602  inc     rcx
0x180006605  cmp     [r9+rcx], dl
0x180006609  jnz     short loc_180006602
0x18000660b  inc     ecx
0x18000660d  jmp     short loc_180006612
0x18000660f  mov     ecx, r8d
0x180006612  mov     [rbp+47h+var_38], ecx
0x180006615  lea     r11, aNull; "NULL"
0x18000661c  lea     rcx, [rbp+47h+arg_20]
0x180006620  mov     [rbp+47h+var_34], edx
0x180006623  test    r9, r9
0x180006626  mov     [rbp+47h+var_30], rcx
0x18000662a  mov     rcx, [rbp+47h+arg_28]
0x18000662e  cmovz   r9, r11
0x180006632  mov     [rbp+47h+var_28], 4
0x18000663a  mov     [rbp+47h+var_40], r9
0x18000663e  test    rcx, rcx
0x180006641  jz      short loc_18000664F
0x180006643  inc     rax
0x180006646  cmp     [rcx+rax], dl
0x180006649  jnz     short loc_180006643
0x18000664b  inc     eax
0x18000664d  jmp     short loc_180006652
0x18000664f  mov     eax, r8d
0x180006652  test    rcx, rcx
0x180006655  mov     [rbp+47h+var_18], eax
0x180006658  mov     [rbp+47h+var_14], edx
0x18000665b  lea     rax, [rbp+47h+var_60]
0x18000665f  cmovz   rcx, r11
0x180006663  mov     [rsp+90h+var_70], rax
0x180006668  mov     r9d, r8d
0x18000666b  mov     [rbp+47h+var_20], rcx
0x18000666f  lea     rdx, MDMCOMMON_TRACE_EHM_FAILED
0x180006676  call    McGenEventWrite_EventWriteTransfer
0x18000667b  mov     rcx, [rbp+47h+var_10]
0x18000667f  xor     rcx, rsp; StackCookie
0x180006682  call    __security_check_cookie
0x180006687  add     rsp, 90h
0x18000668e  pop     rbp
0x18000668f  retn
```
