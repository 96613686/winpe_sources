# WPP_SF_ssLDDdDss

- ea: `0x1800526e0`
- end: `0x180052847`
- name: `WPP_SF_ssLDDdDss`
- size: `359`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, char, char, char, char, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180042ab8`

## callees

- `0x1800526e0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180052830`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180052830`

## string_xrefs

- `0x18005280e`: `GidsApplication::CreateClaim`

## pseudocode

```c
ULONG __fastcall WPP_SF_ssLDDdDss(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        const char *a11,
        const char *a12)
{
  const char *v12; // r8
  __int64 v13; // rax
  __int64 v15; // r10
  __int64 v16; // rdx
  __int64 v17; // r11
  const char *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  bool v21; // zf

  v12 = a12;
  v13 = -1;
  v15 = 5;
  if ( a12 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a12[v16] );
    v17 = v16 + 1;
  }
  else
  {
    v17 = 5;
  }
  v18 = a11;
  if ( !a12 )
    v12 = "NULL";
  if ( a11 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a11[v19] );
    v20 = v19 + 1;
  }
  else
  {
    v20 = 5;
  }
  if ( !a11 )
    v18 = "NULL";
  v21 = a4 == 0;
  if ( a4 )
  {
    do
      ++v13;
    while ( a4[v13] );
    v15 = v13 + 1;
    v21 = a4 == 0;
  }
  if ( v21 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids,
           0x2Du,
           a4,
           v15,
           "GidsApplication::CreateClaim",
           29,
           &a6,
           4,
           &a7,
           4,
           &a8,
           4,
           &a9,
           4,
           &a10,
           4,
           v18,
           v20,
           v12,
           v17,
           0);
}

```

## disassembly

```asm
0x1800526e0  mov     [rsp+arg_0], rbx
0x1800526e5  push    rdi
0x1800526e6  sub     rsp, 0C0h
0x1800526ed  mov     r8, [rsp+0C8h+arg_58]
0x1800526f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800526f9  mov     rbx, rcx
0x1800526fc  mov     r10d, 5
0x180052702  test    r8, r8
0x180052705  jz      short loc_18005271A
0x180052707  mov     rdx, rax
0x18005270a  inc     rdx
0x18005270d  cmp     byte ptr [r8+rdx], 0
0x180052712  jnz     short loc_18005270A
0x180052714  lea     r11, [rdx+1]
0x180052718  jmp     short loc_18005271D
0x18005271a  mov     r11, r10
0x18005271d  mov     rcx, [rsp+0C8h+arg_50]
0x180052725  lea     rdi, aNull; "NULL"
0x18005272c  test    r8, r8
0x18005272f  cmovz   r8, rdi
0x180052733  test    rcx, rcx
0x180052736  jz      short loc_180052749
0x180052738  mov     rdx, rax
0x18005273b  inc     rdx
0x18005273e  cmp     byte ptr [rcx+rdx], 0
0x180052742  jnz     short loc_18005273B
0x180052744  inc     rdx
0x180052747  jmp     short loc_18005274C
0x180052749  mov     rdx, r10
0x18005274c  test    rcx, rcx
0x18005274f  cmovz   rcx, rdi
0x180052753  test    r9, r9
0x180052756  jz      short loc_180052769
0x180052758  inc     rax
0x18005275b  cmp     byte ptr [r9+rax], 0
0x180052760  jnz     short loc_180052758
0x180052762  lea     r10, [rax+1]
0x180052766  test    r9, r9
0x180052769  mov     [rsp+0C8h+var_18], 0
0x180052775  lea     rax, [rsp+0C8h+arg_48]
0x18005277d  mov     [rsp+0C8h+var_20], r11
0x180052785  cmovz   r9, rdi
0x180052789  mov     [rsp+0C8h+var_28], r8
0x180052791  mov     edi, 2Dh ; '-'
0x180052796  mov     [rsp+0C8h+var_30], rdx
0x18005279e  lea     r8, WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids; MessageGuid
0x1800527a5  mov     [rsp+0C8h+var_38], rcx
0x1800527ad  lea     ecx, [rdi-29h]
0x1800527b0  mov     [rsp+0C8h+var_40], rcx
0x1800527b8  lea     edx, [rdi-2]; MessageFlags
0x1800527bb  mov     [rsp+0C8h+var_48], rax
0x1800527c3  lea     rax, [rsp+0C8h+arg_40]
0x1800527cb  mov     [rsp+0C8h+var_50], rcx
0x1800527d0  mov     [rsp+0C8h+var_58], rax
0x1800527d5  lea     rax, [rsp+0C8h+arg_38]
0x1800527dd  mov     [rsp+0C8h+var_60], rcx
0x1800527e2  mov     [rsp+0C8h+var_68], rax
0x1800527e7  lea     rax, [rsp+0C8h+arg_30]
0x1800527ef  mov     [rsp+0C8h+var_70], rcx
0x1800527f4  mov     [rsp+0C8h+var_78], rax
0x1800527f9  lea     rax, [rsp+0C8h+arg_28]
0x180052801  mov     [rsp+0C8h+var_80], rcx
0x180052806  mov     rcx, rbx; LoggerHandle
0x180052809  mov     [rsp+0C8h+var_88], rax
0x18005280e  lea     rax, aGidsapplicatio_20; "GidsApplication::CreateClaim"
0x180052815  mov     [rsp+0C8h+var_90], 1Dh
0x18005281e  mov     [rsp+0C8h+var_98], rax
0x180052823  mov     [rsp+0C8h+var_A0], r10
0x180052828  mov     [rsp+0C8h+var_A8], r9
0x18005282d  mov     r9d, edi; MessageNumber
0x180052830  call    cs:__imp_TraceMessage
0x180052836  mov     rbx, [rsp+0C8h+arg_0]
0x18005283e  add     rsp, 0C0h
0x180052845  pop     rdi
0x180052846  retn
```
