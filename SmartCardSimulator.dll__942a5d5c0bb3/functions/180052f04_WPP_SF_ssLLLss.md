# WPP_SF_ssLLLss

- ea: `0x180052f04`
- end: `0x180053037`
- name: `WPP_SF_ssLLLss`
- size: `307`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, char, char, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180042bcc`

## callees

- `0x180052f04`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180053020`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180053020`

## string_xrefs

- `0x180053002`: `GidsApplication::ManageSecurityEnvironment`

## pseudocode

```c
ULONG __fastcall WPP_SF_ssLLLss(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char a6,
        char a7,
        char a8,
        const char *a9,
        const char *a10)
{
  const char *v10; // r8
  __int64 v11; // rax
  __int64 v13; // r10
  __int64 v14; // rdx
  __int64 v15; // r11
  const char *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  bool v19; // zf

  v10 = a10;
  v11 = -1;
  v13 = 5;
  if ( a10 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a10[v14] );
    v15 = v14 + 1;
  }
  else
  {
    v15 = 5;
  }
  v16 = a9;
  if ( !a10 )
    v10 = "NULL";
  if ( a9 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a9[v17] );
    v18 = v17 + 1;
  }
  else
  {
    v18 = 5;
  }
  if ( !a9 )
    v16 = "NULL";
  v19 = a4 == 0;
  if ( a4 )
  {
    do
      ++v11;
    while ( a4[v11] );
    v13 = v11 + 1;
    v19 = a4 == 0;
  }
  if ( v19 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids,
           0x1Cu,
           a4,
           v13,
           "GidsApplication::ManageSecurityEnvironment",
           43,
           &a6,
           4,
           &a7,
           4,
           &a8,
           4,
           v16,
           v18,
           v10,
           v15,
           0);
}

```

## disassembly

```asm
0x180052f04  mov     [rsp+arg_0], rbx
0x180052f09  push    rdi
0x180052f0a  sub     rsp, 0A0h
0x180052f11  mov     r8, [rsp+0A8h+arg_48]
0x180052f19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052f1d  mov     rbx, rcx
0x180052f20  mov     r10d, 5
0x180052f26  test    r8, r8
0x180052f29  jz      short loc_180052F3E
0x180052f2b  mov     rdx, rax
0x180052f2e  inc     rdx
0x180052f31  cmp     byte ptr [r8+rdx], 0
0x180052f36  jnz     short loc_180052F2E
0x180052f38  lea     r11, [rdx+1]
0x180052f3c  jmp     short loc_180052F41
0x180052f3e  mov     r11, r10
0x180052f41  mov     rcx, [rsp+0A8h+arg_40]
0x180052f49  lea     rdi, aNull; "NULL"
0x180052f50  test    r8, r8
0x180052f53  cmovz   r8, rdi
0x180052f57  test    rcx, rcx
0x180052f5a  jz      short loc_180052F6D
0x180052f5c  mov     rdx, rax
0x180052f5f  inc     rdx
0x180052f62  cmp     byte ptr [rcx+rdx], 0
0x180052f66  jnz     short loc_180052F5F
0x180052f68  inc     rdx
0x180052f6b  jmp     short loc_180052F70
0x180052f6d  mov     rdx, r10
0x180052f70  test    rcx, rcx
0x180052f73  cmovz   rcx, rdi
0x180052f77  test    r9, r9
0x180052f7a  jz      short loc_180052F8D
0x180052f7c  inc     rax
0x180052f7f  cmp     byte ptr [r9+rax], 0
0x180052f84  jnz     short loc_180052F7C
0x180052f86  lea     r10, [rax+1]
0x180052f8a  test    r9, r9
0x180052f8d  mov     [rsp+0A8h+var_18], 0
0x180052f99  lea     rax, [rsp+0A8h+arg_38]
0x180052fa1  mov     [rsp+0A8h+var_20], r11
0x180052fa9  cmovz   r9, rdi
0x180052fad  mov     [rsp+0A8h+var_28], r8
0x180052fb5  mov     edi, 1Ch
0x180052fba  mov     [rsp+0A8h+var_30], rdx
0x180052fbf  lea     r8, WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids; MessageGuid
0x180052fc6  mov     [rsp+0A8h+var_38], rcx
0x180052fcb  lea     ecx, [rdi-18h]
0x180052fce  mov     [rsp+0A8h+var_40], rcx
0x180052fd3  lea     edx, [rdi+0Fh]; MessageFlags
0x180052fd6  mov     [rsp+0A8h+var_48], rax
0x180052fdb  lea     rax, [rsp+0A8h+arg_30]
0x180052fe3  mov     [rsp+0A8h+var_50], rcx
0x180052fe8  mov     [rsp+0A8h+var_58], rax
0x180052fed  lea     rax, [rsp+0A8h+arg_28]
0x180052ff5  mov     [rsp+0A8h+var_60], rcx
0x180052ffa  mov     rcx, rbx; LoggerHandle
0x180052ffd  mov     [rsp+0A8h+var_68], rax
0x180053002  lea     rax, aGidsapplicatio_26; "GidsApplication::ManageSecurityEnvironm"...
0x180053009  mov     [rsp+0A8h+var_70], rdx
0x18005300e  mov     [rsp+0A8h+var_78], rax
0x180053013  mov     [rsp+0A8h+var_80], r10
0x180053018  mov     [rsp+0A8h+var_88], r9
0x18005301d  mov     r9d, edi; MessageNumber
0x180053020  call    cs:__imp_TraceMessage
0x180053026  mov     rbx, [rsp+0A8h+arg_0]
0x18005302e  add     rsp, 0A0h
0x180053035  pop     rdi
0x180053036  retn
```
