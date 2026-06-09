# WPP_SF_ssssDDDD

- ea: `0x18000bcb4`
- end: `0x18000be08`
- name: `WPP_SF_ssssDDDD`
- size: `340`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, __int64, __int64, char, char, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009344`

## callees

- `0x18000bcb4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000bded`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000bded`

## string_xrefs

- `0x18000bdaa`: `Card::ExecuteCommand`

## pseudocode

```c
ULONG WPP_SF_ssssDDDD(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        const char *a6,
        const char *a7,
        ...)
{
  const char *v7; // r8
  __int64 v8; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  __int64 v12; // r11
  const char *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  bool v16; // zf
  __int64 v18; // [rsp+F8h] [rbp+40h] BYREF
  va_list va; // [rsp+F8h] [rbp+40h]
  __int64 v20; // [rsp+100h] [rbp+48h] BYREF
  va_list va1; // [rsp+100h] [rbp+48h]
  __int64 v22; // [rsp+108h] [rbp+50h] BYREF
  va_list va2; // [rsp+108h] [rbp+50h]
  va_list va3; // [rsp+110h] [rbp+58h] BYREF

  va_start(va3, a7);
  va_start(va2, a7);
  va_start(va1, a7);
  va_start(va, a7);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v22 = va_arg(va3, _QWORD);
  v7 = a7;
  v8 = -1;
  v10 = 5;
  if ( a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a7[v11] );
    v12 = v11 + 1;
  }
  else
  {
    v12 = 5;
  }
  v13 = a6;
  if ( !a7 )
    v7 = "NULL";
  if ( a6 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a6[v14] );
    v15 = v14 + 1;
  }
  else
  {
    v15 = 5;
  }
  if ( !a6 )
    v13 = "NULL";
  v16 = a4 == 0;
  if ( a4 )
  {
    do
      ++v8;
    while ( a4[v8] );
    v10 = v8 + 1;
    v16 = a4 == 0;
  }
  if ( v16 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_12dd2fb335f93662815f4b653cabac9e_Traceguids,
           0xFu,
           a4,
           v10,
           "Card::ExecuteCommand",
           21,
           v13,
           v15,
           v7,
           v12,
           va,
           4,
           va1,
           4,
           va2,
           4,
           va3,
           4,
           0);
}

```

## disassembly

```asm
0x18000bcb4  mov     [rsp+arg_0], rbx
0x18000bcb9  mov     [rsp+arg_8], rsi
0x18000bcbe  push    rdi
0x18000bcbf  sub     rsp, 0B0h
0x18000bcc6  mov     r8, [rsp+0B8h+arg_30]
0x18000bcce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bcd2  xor     edi, edi
0x18000bcd4  mov     rbx, rcx
0x18000bcd7  mov     r10d, 5
0x18000bcdd  test    r8, r8
0x18000bce0  jz      short loc_18000BCF4
0x18000bce2  mov     rdx, rax
0x18000bce5  inc     rdx
0x18000bce8  cmp     [r8+rdx], dil
0x18000bcec  jnz     short loc_18000BCE5
0x18000bcee  lea     r11, [rdx+1]
0x18000bcf2  jmp     short loc_18000BCF7
0x18000bcf4  mov     r11, r10
0x18000bcf7  mov     rcx, [rsp+0B8h+arg_28]
0x18000bcff  lea     rsi, aNull; "NULL"
0x18000bd06  test    r8, r8
0x18000bd09  cmovz   r8, rsi
0x18000bd0d  test    rcx, rcx
0x18000bd10  jz      short loc_18000BD23
0x18000bd12  mov     rdx, rax
0x18000bd15  inc     rdx
0x18000bd18  cmp     [rcx+rdx], dil
0x18000bd1c  jnz     short loc_18000BD15
0x18000bd1e  inc     rdx
0x18000bd21  jmp     short loc_18000BD26
0x18000bd23  mov     rdx, r10
0x18000bd26  test    rcx, rcx
0x18000bd29  cmovz   rcx, rsi
0x18000bd2d  test    r9, r9
0x18000bd30  jz      short loc_18000BD42
0x18000bd32  inc     rax
0x18000bd35  cmp     [r9+rax], dil
0x18000bd39  jnz     short loc_18000BD32
0x18000bd3b  lea     r10, [rax+1]
0x18000bd3f  test    r9, r9
0x18000bd42  mov     [rsp+0B8h+var_18], rdi
0x18000bd4a  lea     rax, [rsp+0B8h+arg_50]
0x18000bd52  cmovz   r9, rsi
0x18000bd56  mov     esi, 0Fh
0x18000bd5b  lea     edi, [rsi-0Bh]
0x18000bd5e  mov     [rsp+0B8h+var_20], rdi
0x18000bd66  mov     [rsp+0B8h+var_28], rax
0x18000bd6e  lea     rax, [rsp+0B8h+arg_48]
0x18000bd76  mov     [rsp+0B8h+var_30], rdi
0x18000bd7e  mov     [rsp+0B8h+var_38], rax
0x18000bd86  lea     rax, [rsp+0B8h+arg_40]
0x18000bd8e  mov     [rsp+0B8h+var_40], rdi
0x18000bd93  mov     [rsp+0B8h+var_48], rax
0x18000bd98  lea     rax, [rsp+0B8h+arg_38]
0x18000bda0  mov     [rsp+0B8h+var_50], rdi
0x18000bda5  mov     [rsp+0B8h+var_58], rax
0x18000bdaa  lea     rax, aCardExecutecom; "Card::ExecuteCommand"
0x18000bdb1  mov     [rsp+0B8h+var_60], r11
0x18000bdb6  mov     [rsp+0B8h+var_68], r8
0x18000bdbb  lea     r8, WPP_12dd2fb335f93662815f4b653cabac9e_Traceguids; MessageGuid
0x18000bdc2  mov     [rsp+0B8h+var_70], rdx
0x18000bdc7  lea     edx, [rsi+1Ch]; MessageFlags
0x18000bdca  mov     [rsp+0B8h+var_78], rcx
0x18000bdcf  mov     rcx, rbx; LoggerHandle
0x18000bdd2  mov     [rsp+0B8h+var_80], 15h
0x18000bddb  mov     [rsp+0B8h+var_88], rax
0x18000bde0  mov     [rsp+0B8h+var_90], r10
0x18000bde5  mov     [rsp+0B8h+var_98], r9
0x18000bdea  mov     r9d, esi; MessageNumber
0x18000bded  call    cs:__imp_TraceMessage
0x18000bdf3  lea     r11, [rsp+0B8h+var_8]
0x18000bdfb  mov     rbx, [r11+10h]
0x18000bdff  mov     rsi, [r11+18h]
0x18000be03  mov     rsp, r11
0x18000be06  pop     rdi
0x18000be07  retn
```
