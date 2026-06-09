# WPP_SF_ssDss

- ea: `0x1800522d0`
- end: `0x1800523dc`
- name: `WPP_SF_ssDss`
- size: `268`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, int, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800428c0`

## callees

- `0x1800522d0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800523c5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800523c5`

## string_xrefs

- `0x18005239f`: `GidsApplication::ExecuteCommand`

## pseudocode

```c
ULONG __fastcall WPP_SF_ssDss(
        TRACEHANDLE LoggerHandle,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char a6,
        const char *a7,
        const char *a8)
{
  const char *v8; // r8
  __int64 v9; // rdx
  __int64 v11; // r10
  __int64 v12; // rax
  __int64 v13; // r11
  const char *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  bool v17; // zf

  v8 = a8;
  v9 = -1;
  v11 = 5;
  if ( a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a8[v12] );
    v13 = v12 + 1;
  }
  else
  {
    v13 = 5;
  }
  v14 = a7;
  if ( !a8 )
    v8 = "NULL";
  if ( a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a7[v15] );
    v16 = v15 + 1;
  }
  else
  {
    v16 = 5;
  }
  if ( !a7 )
    v14 = "NULL";
  v17 = a4 == 0;
  if ( a4 )
  {
    do
      ++v9;
    while ( a4[v9] );
    v11 = v9 + 1;
    v17 = a4 == 0;
  }
  if ( v17 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids,
           0x13u,
           a4,
           v11,
           "GidsApplication::ExecuteCommand",
           32,
           &a6,
           4,
           v14,
           v16,
           v8,
           v13,
           0);
}

```

## disassembly

```asm
0x1800522d0  mov     [rsp+arg_0], rbx
0x1800522d5  push    rsi
0x1800522d6  sub     rsp, 80h
0x1800522dd  mov     r8, [rsp+88h+arg_38]
0x1800522e5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800522e9  mov     rbx, rcx
0x1800522ec  mov     r10d, 5
0x1800522f2  test    r8, r8
0x1800522f5  jz      short loc_18005230A
0x1800522f7  mov     rax, rdx
0x1800522fa  inc     rax
0x1800522fd  cmp     byte ptr [r8+rax], 0
0x180052302  jnz     short loc_1800522FA
0x180052304  lea     r11, [rax+1]
0x180052308  jmp     short loc_18005230D
0x18005230a  mov     r11, r10
0x18005230d  mov     rcx, [rsp+88h+arg_30]
0x180052315  lea     rsi, aNull; "NULL"
0x18005231c  test    r8, r8
0x18005231f  cmovz   r8, rsi
0x180052323  test    rcx, rcx
0x180052326  jz      short loc_180052339
0x180052328  mov     rax, rdx
0x18005232b  inc     rax
0x18005232e  cmp     byte ptr [rcx+rax], 0
0x180052332  jnz     short loc_18005232B
0x180052334  inc     rax
0x180052337  jmp     short loc_18005233C
0x180052339  mov     rax, r10
0x18005233c  test    rcx, rcx
0x18005233f  cmovz   rcx, rsi
0x180052343  test    r9, r9
0x180052346  jz      short loc_180052359
0x180052348  inc     rdx
0x18005234b  cmp     byte ptr [r9+rdx], 0
0x180052350  jnz     short loc_180052348
0x180052352  lea     r10, [rdx+1]
0x180052356  test    r9, r9
0x180052359  mov     [rsp+88h+var_18], 0
0x180052362  cmovz   r9, rsi
0x180052366  mov     [rsp+88h+var_20], r11
0x18005236b  mov     edx, 13h
0x180052370  mov     [rsp+88h+var_28], r8
0x180052375  lea     r8, WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids; MessageGuid
0x18005237c  mov     [rsp+88h+var_30], rax
0x180052381  lea     rax, [rsp+88h+arg_28]
0x180052389  mov     [rsp+88h+var_38], rcx
0x18005238e  mov     rcx, rbx; LoggerHandle
0x180052391  mov     [rsp+88h+var_40], 4
0x18005239a  mov     [rsp+88h+var_48], rax
0x18005239f  lea     rax, aGidsapplicatio_4; "GidsApplication::ExecuteCommand"
0x1800523a6  mov     [rsp+88h+var_50], 20h ; ' '
0x1800523af  mov     [rsp+88h+var_58], rax
0x1800523b4  mov     [rsp+88h+var_60], r10
0x1800523b9  mov     [rsp+88h+var_68], r9
0x1800523be  mov     r9d, edx; MessageNumber
0x1800523c1  lea     edx, [r9+18h]; MessageFlags
0x1800523c5  call    cs:__imp_TraceMessage
0x1800523cb  mov     rbx, [rsp+88h+arg_0]
0x1800523d3  add     rsp, 80h
0x1800523da  pop     rsi
0x1800523db  retn
```
