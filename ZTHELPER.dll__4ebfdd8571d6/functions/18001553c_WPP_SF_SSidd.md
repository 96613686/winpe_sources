# WPP_SF_SSidd

- ea: `0x18001553c`
- end: `0x180015612`
- name: `WPP_SF_SSidd`
- size: `214`
- prototype: `ULONG(__int64, USHORT, __int64, const wchar_t *, const wchar_t *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800054bc`
- `0x180005924`

## callees

- `0x18000b794`
- `0x18001553c`

## pseudocode

```c
ULONG WPP_SF_SSidd(__int64 a1, USHORT a2, __int64 a3, const wchar_t *a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 v9; // r8
  bool v10; // zf
  __int64 v12; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v14; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  va_list va2; // [rsp+B8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return FastWppTraceMessage(
           1026,
           a2,
           (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids,
           a4,
           v7,
           v5,
           v9,
           va,
           8,
           va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x18001553c  push    rbx
0x18001553e  sub     rsp, 70h
0x180015542  mov     rcx, [rsp+78h+arg_20]
0x18001554a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001554e  xor     r11d, r11d
0x180015551  mov     r10d, 0Ah
0x180015557  test    rcx, rcx
0x18001555a  jz      short loc_180015573
0x18001555c  mov     r8, rax
0x18001555f  inc     r8
0x180015562  cmp     [rcx+r8*2], r11w
0x180015567  jnz     short loc_18001555F
0x180015569  lea     r8, ds:2[r8*2]
0x180015571  jmp     short loc_180015576
0x180015573  mov     r8, r10
0x180015576  test    rcx, rcx
0x180015579  lea     rbx, aNull_0; "NULL"
0x180015580  cmovz   rcx, rbx
0x180015584  test    r9, r9
0x180015587  jz      short loc_18001559E
0x180015589  inc     rax
0x18001558c  cmp     [r9+rax*2], r11w
0x180015591  jnz     short loc_180015589
0x180015593  lea     r10, ds:2[rax*2]
0x18001559b  test    r9, r9
0x18001559e  mov     [rsp+78h+var_10], r11
0x1800155a3  lea     rax, [rsp+78h+arg_38]
0x1800155ab  mov     r11d, 4
0x1800155b1  movzx   edx, dx
0x1800155b4  mov     [rsp+78h+var_18], r11
0x1800155b9  cmovz   r9, rbx
0x1800155bd  mov     [rsp+78h+var_20], rax
0x1800155c2  mov     ebx, 402h
0x1800155c7  mov     [rsp+78h+var_28], r11
0x1800155cc  lea     rax, [rsp+78h+arg_30]
0x1800155d4  mov     [rsp+78h+var_30], rax
0x1800155d9  lea     rax, [rsp+78h+arg_28]
0x1800155e1  mov     [rsp+78h+var_38], 8
0x1800155ea  mov     [rsp+78h+var_40], rax
0x1800155ef  mov     [rsp+78h+var_48], r8
0x1800155f4  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x1800155fb  mov     [rsp+78h+var_50], rcx
0x180015600  mov     ecx, ebx
0x180015602  mov     [rsp+78h+var_58], r10
0x180015607  call    FastWppTraceMessage
0x18001560c  add     rsp, 70h
0x180015610  pop     rbx
0x180015611  retn
```
