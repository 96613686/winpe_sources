# WPP_SF_ss_HEX_DLLLssD

- ea: `0x18003c114`
- end: `0x18003c2b4`
- name: `WPP_SF_ss_HEX_DLLLssD`
- size: `416`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, __int64, char, char, char, char, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c21c`

## callees

- `0x18003c114`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003c29e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003c29e`

## string_xrefs

- `0x18003c26e`: `FileSystem::DedicatedFile::DeleteEf`

## pseudocode

```c
ULONG WPP_SF_ss_HEX_DLLLssD(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        _QWORD *a6,
        char a7,
        char a8,
        char a9,
        ...)
{
  const char *v9; // r8
  __int64 v10; // rdx
  __int64 v12; // r10
  __int64 v13; // rax
  __int64 v14; // rbx
  const char *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r11
  bool v18; // zf
  __int64 v20; // [rsp+168h] [rbp+50h] BYREF
  va_list va; // [rsp+168h] [rbp+50h]
  const char *v22; // [rsp+170h] [rbp+58h]
  const char *v23; // [rsp+178h] [rbp+60h]
  va_list va1; // [rsp+180h] [rbp+68h] BYREF

  va_start(va1, a9);
  va_start(va, a9);
  v20 = va_arg(va1, _QWORD);
  v22 = va_arg(va1, const char *);
  v23 = va_arg(va1, const char *);
  v9 = v23;
  v10 = -1;
  v12 = 5;
  if ( v23 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v23[v13] );
    v14 = v13 + 1;
  }
  else
  {
    v14 = 5;
  }
  v15 = v22;
  if ( !v23 )
    v9 = "NULL";
  if ( v22 )
  {
    v16 = -1;
    do
      ++v16;
    while ( v22[v16] );
    v17 = v16 + 1;
  }
  else
  {
    v17 = 5;
  }
  if ( !v22 )
    v15 = "NULL";
  v18 = a4 == 0;
  if ( a4 )
  {
    do
      ++v10;
    while ( a4[v10] );
    v12 = v10 + 1;
    v18 = a4 == 0;
  }
  if ( v18 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
           0x62u,
           a4,
           v12,
           "FileSystem::DedicatedFile::DeleteEf",
           36,
           a6 + 1,
           2,
           *a6,
           a6[1],
           &a7,
           4,
           &a8,
           4,
           &a9,
           4,
           va,
           4,
           v15,
           v17,
           v9,
           v14,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18003c114  push    rbx
0x18003c116  push    rbp
0x18003c117  push    rsi
0x18003c118  push    rdi
0x18003c119  push    r14
0x18003c11b  push    r15
0x18003c11d  sub     rsp, 0E8h
0x18003c124  mov     r8, [rsp+118h+arg_58]
0x18003c12c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003c130  xor     r14d, r14d
0x18003c133  mov     rbp, rcx
0x18003c136  mov     r10d, 5
0x18003c13c  test    r8, r8
0x18003c13f  jz      short loc_18003C153
0x18003c141  mov     rax, rdx
0x18003c144  inc     rax
0x18003c147  cmp     [r8+rax], r14b
0x18003c14b  jnz     short loc_18003C144
0x18003c14d  lea     rbx, [rax+1]
0x18003c151  jmp     short loc_18003C156
0x18003c153  mov     rbx, r10
0x18003c156  mov     rcx, [rsp+118h+arg_50]
0x18003c15e  lea     r15, aNull; "NULL"
0x18003c165  test    r8, r8
0x18003c168  cmovz   r8, r15
0x18003c16c  test    rcx, rcx
0x18003c16f  jz      short loc_18003C183
0x18003c171  mov     rax, rdx
0x18003c174  inc     rax
0x18003c177  cmp     [rcx+rax], r14b
0x18003c17b  jnz     short loc_18003C174
0x18003c17d  lea     r11, [rax+1]
0x18003c181  jmp     short loc_18003C186
0x18003c183  mov     r11, r10
0x18003c186  mov     rax, [rsp+118h+arg_28]
0x18003c18e  test    rcx, rcx
0x18003c191  cmovz   rcx, r15
0x18003c195  lea     rdi, [rax+8]
0x18003c199  mov     rax, [rax]
0x18003c19c  mov     rsi, [rdi]
0x18003c19f  test    r9, r9
0x18003c1a2  jz      short loc_18003C1B4
0x18003c1a4  inc     rdx
0x18003c1a7  cmp     [r9+rdx], r14b
0x18003c1ab  jnz     short loc_18003C1A4
0x18003c1ad  lea     r10, [rdx+1]
0x18003c1b1  test    r9, r9
0x18003c1b4  mov     [rsp+118h+var_48], r14
0x18003c1bc  lea     rdx, [rsp+118h+arg_60]
0x18003c1c4  cmovz   r9, r15
0x18003c1c8  mov     r15d, 62h ; 'b'
0x18003c1ce  lea     r14d, [r15-5Eh]
0x18003c1d2  mov     [rsp+118h+var_50], r14
0x18003c1da  mov     [rsp+118h+var_58], rdx
0x18003c1e2  lea     edx, [r15-37h]; MessageFlags
0x18003c1e6  mov     [rsp+118h+var_60], rbx
0x18003c1ee  mov     [rsp+118h+var_68], r8
0x18003c1f6  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids; MessageGuid
0x18003c1fd  mov     [rsp+118h+var_70], r11
0x18003c205  mov     [rsp+118h+var_78], rcx
0x18003c20d  lea     rcx, [rsp+118h+arg_48]
0x18003c215  mov     [rsp+118h+var_80], r14
0x18003c21d  mov     [rsp+118h+var_88], rcx
0x18003c225  lea     rcx, [rsp+118h+arg_40]
0x18003c22d  mov     [rsp+118h+var_90], r14
0x18003c235  mov     [rsp+118h+var_98], rcx
0x18003c23d  lea     rcx, [rsp+118h+arg_38]
0x18003c245  mov     [rsp+118h+var_A0], r14
0x18003c24a  mov     [rsp+118h+var_A8], rcx
0x18003c24f  lea     rcx, [rsp+118h+arg_30]
0x18003c257  mov     [rsp+118h+var_B0], r14
0x18003c25c  mov     [rsp+118h+var_B8], rcx
0x18003c261  mov     rcx, rbp; LoggerHandle
0x18003c264  mov     [rsp+118h+var_C0], rsi
0x18003c269  mov     [rsp+118h+var_C8], rax
0x18003c26e  lea     rax, aFilesystemDedi_3; "FileSystem::DedicatedFile::DeleteEf"
0x18003c275  mov     [rsp+118h+var_D0], 2
0x18003c27e  mov     [rsp+118h+var_D8], rdi
0x18003c283  mov     [rsp+118h+var_E0], 24h ; '$'
0x18003c28c  mov     [rsp+118h+var_E8], rax
0x18003c291  mov     [rsp+118h+var_F0], r10
0x18003c296  mov     [rsp+118h+var_F8], r9
0x18003c29b  mov     r9d, r15d; MessageNumber
0x18003c29e  call    cs:__imp_TraceMessage
0x18003c2a4  add     rsp, 0E8h
0x18003c2ab  pop     r15
0x18003c2ad  pop     r14
0x18003c2af  pop     rdi
0x18003c2b0  pop     rsi
0x18003c2b1  pop     rbp
0x18003c2b2  pop     rbx
0x18003c2b3  retn
```
