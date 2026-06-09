# WPP_SF_qSD

- ea: `0x18000cd9c`
- end: `0x18000ce3e`
- name: `WPP_SF_qSD`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800050b0`
- `0x180006da0`
- `0x18000ccf0`

## callees

- `0x18000cd9c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000ce2c`
- `ntdll!EtwTraceMessage` at `0x18000ce2c`

## pseudocode

```c
__int64 WPP_SF_qSD(__int64 a1, __int64 a2, __int64 a3, ...)
{
  const wchar_t *v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  const wchar_t *v9; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  v9 = va_arg(va1, const wchar_t *);
  v3 = v9;
  if ( v9 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v9[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !v9 )
    v3 = L"NULL";
  return EtwTraceMessage(
           a1,
           43,
           WPP_321c0d2313123f81ee86e6c36df24469_Traceguids,
           29,
           (__int64 *)va,
           8,
           v3,
           v5,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18000cd9c  mov     [rsp+arg_18], r9
0x18000cda1  sub     rsp, 68h
0x18000cda5  mov     rdx, [rsp+68h+arg_20]
0x18000cdad  xor     r10d, r10d
0x18000cdb0  test    rdx, rdx
0x18000cdb3  jz      short loc_18000CDCD
0x18000cdb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cdb9  inc     rax
0x18000cdbc  cmp     [rdx+rax*2], r10w
0x18000cdc1  jnz     short loc_18000CDB9
0x18000cdc3  lea     rax, ds:2[rax*2]
0x18000cdcb  jmp     short loc_18000CDD2
0x18000cdcd  mov     eax, 0Ah
0x18000cdd2  mov     [rsp+68h+var_18], r10
0x18000cdd7  lea     r8, aNull_0; "NULL"
0x18000cdde  mov     [rsp+68h+var_20], 4
0x18000cde7  test    rdx, rdx
0x18000cdea  mov     r9d, 1Dh
0x18000cdf0  cmovz   rdx, r8
0x18000cdf4  lea     r8, [rsp+68h+arg_28]
0x18000cdfc  mov     [rsp+68h+var_28], r8
0x18000ce01  lea     r8, WPP_321c0d2313123f81ee86e6c36df24469_Traceguids
0x18000ce08  mov     [rsp+68h+var_30], rax
0x18000ce0d  lea     rax, [rsp+68h+arg_18]
0x18000ce15  mov     [rsp+68h+var_38], rdx
0x18000ce1a  lea     edx, [r9+0Eh]
0x18000ce1e  mov     [rsp+68h+var_40], 8
0x18000ce27  mov     [rsp+68h+var_48], rax
0x18000ce2c  call    cs:__imp_EtwTraceMessage
0x18000ce33  nop     dword ptr [rax+rax+00h]
0x18000ce38  add     rsp, 68h
0x18000ce3c  retn
```
