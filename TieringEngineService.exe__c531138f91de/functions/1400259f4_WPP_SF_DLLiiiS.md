# WPP_SF_DLLiiiS

- ea: `0x1400259f4`
- end: `0x140025ae9`
- name: `WPP_SF_DLLiiiS`
- size: `245`
- prototype: `ULONG __fastcall(TRACEHANDLE, __int64, __int64, int, char, char, char, char, char, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140021a28`

## callees

- `0x1400259f4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140025adb`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140025adb`

## pseudocode

```c
ULONG __fastcall WPP_SF_DLLiiiS(
        TRACEHANDLE a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        const wchar_t *a10)
{
  const wchar_t *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  int v14; // [rsp+C8h] [rbp+20h] BYREF

  v14 = a4;
  v10 = a10;
  if ( a10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a10[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  if ( !a10 )
    v10 = L"NULL";
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
           0x2Du,
           &v14,
           4,
           &a5,
           4,
           &a6,
           4,
           &a7,
           8,
           &a8,
           8,
           &a9,
           8,
           v10,
           v12,
           0);
}

```

## disassembly

```asm
0x1400259f4  mov     [rsp+arg_18], r9d
0x1400259f9  sub     rsp, 0A8h
0x140025a00  mov     rdx, [rsp+0A8h+arg_48]
0x140025a08  xor     r9d, r9d
0x140025a0b  test    rdx, rdx
0x140025a0e  jz      short loc_140025A28
0x140025a10  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025a14  inc     rax
0x140025a17  cmp     [rdx+rax*2], r9w
0x140025a1c  jnz     short loc_140025A14
0x140025a1e  lea     rax, ds:2[rax*2]
0x140025a26  jmp     short loc_140025A2D
0x140025a28  mov     eax, 0Ah
0x140025a2d  mov     [rsp+0A8h+var_18], r9
0x140025a35  lea     r8, aNull_1; "NULL"
0x140025a3c  mov     [rsp+0A8h+var_20], rax
0x140025a44  test    rdx, rdx
0x140025a47  lea     rax, [rsp+0A8h+arg_40]
0x140025a4f  cmovz   rdx, r8
0x140025a53  mov     r8d, 2Dh ; '-'
0x140025a59  mov     [rsp+0A8h+var_28], rdx
0x140025a61  mov     r9d, r8d; MessageNumber
0x140025a64  lea     edx, [r8-25h]
0x140025a68  mov     [rsp+0A8h+var_30], rdx
0x140025a6d  mov     [rsp+0A8h+var_38], rax
0x140025a72  lea     rax, [rsp+0A8h+arg_38]
0x140025a7a  mov     [rsp+0A8h+var_40], rdx
0x140025a7f  mov     [rsp+0A8h+var_48], rax
0x140025a84  lea     rax, [rsp+0A8h+arg_30]
0x140025a8c  mov     [rsp+0A8h+var_50], rdx
0x140025a91  lea     edx, [r8-29h]
0x140025a95  mov     [rsp+0A8h+var_58], rax
0x140025a9a  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids; MessageGuid
0x140025aa1  mov     [rsp+0A8h+var_60], rdx
0x140025aa6  lea     rax, [rsp+0A8h+arg_28]
0x140025aae  mov     [rsp+0A8h+var_68], rax
0x140025ab3  lea     rax, [rsp+0A8h+arg_20]
0x140025abb  mov     [rsp+0A8h+var_70], rdx
0x140025ac0  mov     [rsp+0A8h+var_78], rax
0x140025ac5  lea     rax, [rsp+0A8h+arg_18]
0x140025acd  mov     [rsp+0A8h+var_80], rdx
0x140025ad2  lea     edx, [r9-2]; MessageFlags
0x140025ad6  mov     [rsp+0A8h+var_88], rax
0x140025adb  call    cs:__imp_TraceMessage
0x140025ae1  add     rsp, 0A8h
0x140025ae8  retn
```
