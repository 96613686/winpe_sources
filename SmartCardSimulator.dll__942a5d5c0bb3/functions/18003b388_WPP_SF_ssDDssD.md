# WPP_SF_ssDDssD

- ea: `0x18003b388`
- end: `0x18003b4c4`
- name: `WPP_SF_ssDDssD`
- size: `316`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, char, char, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002aee8`

## callees

- `0x18003b388`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b4a9`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b4a9`

## string_xrefs

- `0x18003b487`: `FileSystem::ElementaryFile::WriteDataObjectToDisk`

## pseudocode

```c
ULONG WPP_SF_ssDDssD(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, const char *a4, int a5, char a6, ...)
{
  const char *v6; // r8
  __int64 v7; // rax
  __int64 v9; // r10
  __int64 v10; // rdx
  __int64 v11; // r11
  const char *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  bool v15; // zf
  __int64 v17; // [rsp+E0h] [rbp+38h] BYREF
  va_list va; // [rsp+E0h] [rbp+38h]
  const char *v19; // [rsp+E8h] [rbp+40h]
  const char *v20; // [rsp+F0h] [rbp+48h]
  va_list va1; // [rsp+F8h] [rbp+50h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v17 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, const char *);
  v20 = va_arg(va1, const char *);
  v6 = v20;
  v7 = -1;
  v9 = 5;
  if ( v20 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v20[v10] );
    v11 = v10 + 1;
  }
  else
  {
    v11 = 5;
  }
  v12 = v19;
  if ( !v20 )
    v6 = "NULL";
  if ( v19 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v19[v13] );
    v14 = v13 + 1;
  }
  else
  {
    v14 = 5;
  }
  if ( !v19 )
    v12 = "NULL";
  v15 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v9 = v7 + 1;
    v15 = a4 == 0;
  }
  if ( v15 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
           0x51u,
           a4,
           v9,
           "FileSystem::ElementaryFile::WriteDataObjectToDisk",
           50,
           &a6,
           4,
           va,
           4,
           v12,
           v14,
           v6,
           v11,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18003b388  mov     [rsp+arg_0], rbx
0x18003b38d  mov     [rsp+arg_8], rsi
0x18003b392  push    rdi
0x18003b393  sub     rsp, 0A0h
0x18003b39a  mov     r8, [rsp+0A8h+arg_40]
0x18003b3a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003b3a6  xor     edi, edi
0x18003b3a8  mov     rbx, rcx
0x18003b3ab  mov     r10d, 5
0x18003b3b1  test    r8, r8
0x18003b3b4  jz      short loc_18003B3C8
0x18003b3b6  mov     rdx, rax
0x18003b3b9  inc     rdx
0x18003b3bc  cmp     [r8+rdx], dil
0x18003b3c0  jnz     short loc_18003B3B9
0x18003b3c2  lea     r11, [rdx+1]
0x18003b3c6  jmp     short loc_18003B3CB
0x18003b3c8  mov     r11, r10
0x18003b3cb  mov     rcx, [rsp+0A8h+arg_38]
0x18003b3d3  lea     rsi, aNull; "NULL"
0x18003b3da  test    r8, r8
0x18003b3dd  cmovz   r8, rsi
0x18003b3e1  test    rcx, rcx
0x18003b3e4  jz      short loc_18003B3F7
0x18003b3e6  mov     rdx, rax
0x18003b3e9  inc     rdx
0x18003b3ec  cmp     [rcx+rdx], dil
0x18003b3f0  jnz     short loc_18003B3E9
0x18003b3f2  inc     rdx
0x18003b3f5  jmp     short loc_18003B3FA
0x18003b3f7  mov     rdx, r10
0x18003b3fa  test    rcx, rcx
0x18003b3fd  cmovz   rcx, rsi
0x18003b401  test    r9, r9
0x18003b404  jz      short loc_18003B416
0x18003b406  inc     rax
0x18003b409  cmp     [r9+rax], dil
0x18003b40d  jnz     short loc_18003B406
0x18003b40f  lea     r10, [rax+1]
0x18003b413  test    r9, r9
0x18003b416  mov     [rsp+0A8h+var_18], rdi
0x18003b41e  lea     rax, [rsp+0A8h+arg_48]
0x18003b426  cmovz   r9, rsi
0x18003b42a  mov     esi, 51h ; 'Q'
0x18003b42f  lea     edi, [rsi-4Dh]
0x18003b432  mov     [rsp+0A8h+var_20], rdi
0x18003b43a  mov     [rsp+0A8h+var_28], rax
0x18003b442  lea     rax, [rsp+0A8h+arg_30]
0x18003b44a  mov     [rsp+0A8h+var_30], r11
0x18003b44f  mov     [rsp+0A8h+var_38], r8
0x18003b454  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids; MessageGuid
0x18003b45b  mov     [rsp+0A8h+var_40], rdx
0x18003b460  lea     edx, [rsi-26h]; MessageFlags
0x18003b463  mov     [rsp+0A8h+var_48], rcx
0x18003b468  mov     rcx, rbx; LoggerHandle
0x18003b46b  mov     [rsp+0A8h+var_50], rdi
0x18003b470  mov     [rsp+0A8h+var_58], rax
0x18003b475  lea     rax, [rsp+0A8h+arg_28]
0x18003b47d  mov     [rsp+0A8h+var_60], rdi
0x18003b482  mov     [rsp+0A8h+var_68], rax
0x18003b487  lea     rax, aFilesystemElem_4; "FileSystem::ElementaryFile::WriteDataOb"...
0x18003b48e  mov     [rsp+0A8h+var_70], 32h ; '2'
0x18003b497  mov     [rsp+0A8h+var_78], rax
0x18003b49c  mov     [rsp+0A8h+var_80], r10
0x18003b4a1  mov     [rsp+0A8h+var_88], r9
0x18003b4a6  mov     r9d, esi; MessageNumber
0x18003b4a9  call    cs:__imp_TraceMessage
0x18003b4af  lea     r11, [rsp+0A8h+var_8]
0x18003b4b7  mov     rbx, [r11+10h]
0x18003b4bb  mov     rsi, [r11+18h]
0x18003b4bf  mov     rsp, r11
0x18003b4c2  pop     rdi
0x18003b4c3  retn
```
