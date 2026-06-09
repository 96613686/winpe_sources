# McTemplateU0dsqs_EventWriteTransfer

- ea: `0x180006548`
- end: `0x180006618`
- name: `McTemplateU0dsqs_EventWriteTransfer`
- size: `208`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, char, const char *, ...)`
- caller_count: `123`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800030c0`
- `0x1800034b0`
- `0x1800035d0`
- `0x1800036c0`
- `0x180003930`
- `0x180003a20`
- `0x180003d40`
- `0x180003f90`
- `0x1800040c0`
- `0x1800043b0`
- `0x180004520`
- `0x1800049e0`
- `0x180004b60`
- `0x180004c70`
- `0x180005070`
- `0x180005360`
- `0x180005450`
- `0x180005550`
- `0x180005670`
- `0x180005790`
- `0x180005860`
- `0x180005a10`
- `0x180005cb0`
- `0x180005e50`
- `0x1800067d8`
- `0x180006964`
- `0x180006aa0`
- `0x18000745c`
- `0x1800078ec`
- `0x180007fb4`
- `0x180008050`
- `0x180008328`
- `0x1800087d0`
- `0x18000886c`
- `0x180008910`
- `0x180008a6c`
- `0x180008d58`
- `0x180009b24`
- `0x18000a314`
- `0x18000abb4`
- `0x18000ae24`
- `0x18000b350`
- `0x18000b88c`
- `0x18000ba7c`
- `0x18000c38c`
- `0x18000e97c`
- `0x18000ef34`
- `0x180010740`
- `0x180010b0c`
- `0x180010f90`

## callees

- `0x180001520`
- `0x1800064f0`
- `0x180006548`

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
0x180006548  mov     [rsp-8+arg_10], r8d
0x18000654d  push    rbp
0x18000654e  lea     rbp, [rsp-47h]
0x180006553  sub     rsp, 90h
0x18000655a  mov     rax, cs:__security_cookie
0x180006561  xor     rax, rsp
0x180006564  mov     [rbp+47h+var_10], rax
0x180006568  lea     rax, [rbp+47h+arg_10]
0x18000656c  mov     [rbp+47h+var_48], 4
0x180006574  xor     edx, edx
0x180006576  mov     [rbp+47h+var_50], rax
0x18000657a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000657e  lea     r8d, [rdx+5]
0x180006582  test    r9, r9
0x180006585  jz      short loc_180006597
0x180006587  mov     rcx, rax
0x18000658a  inc     rcx
0x18000658d  cmp     [r9+rcx], dl
0x180006591  jnz     short loc_18000658A
0x180006593  inc     ecx
0x180006595  jmp     short loc_18000659A
0x180006597  mov     ecx, r8d
0x18000659a  mov     [rbp+47h+var_38], ecx
0x18000659d  lea     r11, aNull; "NULL"
0x1800065a4  lea     rcx, [rbp+47h+arg_20]
0x1800065a8  mov     [rbp+47h+var_34], edx
0x1800065ab  test    r9, r9
0x1800065ae  mov     [rbp+47h+var_30], rcx
0x1800065b2  mov     rcx, [rbp+47h+arg_28]
0x1800065b6  cmovz   r9, r11
0x1800065ba  mov     [rbp+47h+var_28], 4
0x1800065c2  mov     [rbp+47h+var_40], r9
0x1800065c6  test    rcx, rcx
0x1800065c9  jz      short loc_1800065D7
0x1800065cb  inc     rax
0x1800065ce  cmp     [rcx+rax], dl
0x1800065d1  jnz     short loc_1800065CB
0x1800065d3  inc     eax
0x1800065d5  jmp     short loc_1800065DA
0x1800065d7  mov     eax, r8d
0x1800065da  test    rcx, rcx
0x1800065dd  mov     [rbp+47h+var_18], eax
0x1800065e0  mov     [rbp+47h+var_14], edx
0x1800065e3  lea     rax, [rbp+47h+var_60]
0x1800065e7  cmovz   rcx, r11
0x1800065eb  mov     [rsp+90h+var_70], rax
0x1800065f0  mov     r9d, r8d
0x1800065f3  mov     [rbp+47h+var_20], rcx
0x1800065f7  lea     rdx, MDMCOMMON_TRACE_EHM_FAILED
0x1800065fe  call    McGenEventWrite_EventWriteTransfer
0x180006603  mov     rcx, [rbp+47h+var_10]
0x180006607  xor     rcx, rsp; StackCookie
0x18000660a  call    __security_check_cookie
0x18000660f  add     rsp, 90h
0x180006616  pop     rbp
0x180006617  retn
```
