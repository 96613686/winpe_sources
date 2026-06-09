# WPP_SF_qISdLLLLDqLDLDq

- ea: `0x18000ba5c`
- end: `0x18000bbd9`
- name: `WPP_SF_qISdLLLLDqLDLDq`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800058b0`

## callees

- `0x1800072e0`
- `0x18000ba5c`

## pseudocode

```c
ULONG WPP_SF_qISdLLLLDqLDLDq(
        _DWORD a1,
        _DWORD a2,
        _DWORD a3,
        __int64 a4,
        char a5,
        const wchar_t *a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16,
        ...)
{
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+140h] [rbp-58h] BYREF
  __int64 v21; // [rsp+1A8h] [rbp+10h] BYREF
  va_list va; // [rsp+1A8h] [rbp+10h]
  va_list va1; // [rsp+1B0h] [rbp+18h] BYREF

  va_start(va1, a16);
  va_start(va, a16);
  v21 = va_arg(va1, _QWORD);
  v20 = a4;
  v16 = a6;
  if ( a6 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a6[v17] );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v18 = 10;
  }
  if ( !a6 )
    v16 = L"NULL";
  return FastWppTraceMessage(
           1050,
           0x1Au,
           (ULONGLONG)WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids,
           &v20,
           8,
           &a5,
           8,
           v16,
           v18,
           &a7,
           4,
           &a8,
           4,
           &a9,
           4,
           &a10,
           4,
           &a11,
           4,
           &a12,
           4,
           &a13,
           8,
           &a14,
           4,
           &a15,
           4,
           &a16,
           4,
           va,
           4,
           va1,
           8,
           0);
}

```

## disassembly

```asm
0x18000ba5c  mov     rax, rsp
0x18000ba5f  mov     [rax+20h], r9
0x18000ba63  push    rbp
0x18000ba64  lea     rbp, [rax+78h]
0x18000ba68  sub     rsp, 110h
0x18000ba6f  mov     rcx, [rbp-80h+arg_28]
0x18000ba73  xor     r8d, r8d
0x18000ba76  test    rcx, rcx
0x18000ba79  jz      short loc_18000BA93
0x18000ba7b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ba7f  inc     rax
0x18000ba82  cmp     [rcx+rax*2], r8w
0x18000ba87  jnz     short loc_18000BA7F
0x18000ba89  lea     rax, ds:2[rax*2]
0x18000ba91  jmp     short loc_18000BA98
0x18000ba93  mov     eax, 0Ah
0x18000ba98  mov     [rsp+108h], r8
0x18000baa0  lea     rdx, aNull_0; "NULL"
0x18000baa7  mov     r10d, 1Ah
0x18000baad  test    rcx, rcx
0x18000bab0  mov     r11d, 41Ah
0x18000bab6  cmovz   rcx, rdx
0x18000baba  lea     rdx, [rbp-80h+arg_88]
0x18000babe  lea     r8d, [r10-16h]
0x18000bac2  lea     r9d, [r10-12h]
0x18000bac6  mov     [rsp+110h+var_10], r9
0x18000bace  mov     [rsp+110h+var_18], rdx
0x18000bad6  lea     rdx, [rbp-80h+arg_80]
0x18000bada  mov     [rsp+110h+var_20], r8
0x18000bae2  mov     [rsp+110h+var_28], rdx
0x18000baea  lea     rdx, [rbp-80h+arg_78]
0x18000baee  mov     [rsp+110h+var_30], r8
0x18000baf6  mov     [rsp+110h+var_38], rdx
0x18000bafe  lea     rdx, [rbp-80h+arg_70]
0x18000bb02  mov     [rsp+110h+var_40], r8
0x18000bb0a  mov     [rsp+110h+var_48], rdx
0x18000bb12  lea     rdx, [rbp-80h+arg_68]
0x18000bb16  mov     [rsp+110h+var_50], r8
0x18000bb1e  mov     [rsp+110h+var_58], rdx
0x18000bb26  lea     rdx, [rbp-80h+arg_60]
0x18000bb2a  mov     [rsp+110h+var_60], r9
0x18000bb32  mov     [rsp+110h+var_68], rdx
0x18000bb3a  lea     rdx, [rbp-80h+arg_58]
0x18000bb3e  mov     [rsp+110h+var_70], r8
0x18000bb46  mov     [rsp+110h+var_78], rdx
0x18000bb4e  lea     rdx, [rbp-80h+arg_50]
0x18000bb52  mov     [rsp+110h+var_80], r8
0x18000bb5a  mov     [rsp+110h+var_88], rdx
0x18000bb62  lea     rdx, [rbp-80h+arg_48]
0x18000bb66  mov     [rsp+110h+var_90], r8
0x18000bb6e  mov     [rsp+110h+var_98], rdx
0x18000bb73  lea     rdx, [rbp-80h+arg_40]
0x18000bb77  mov     [rsp+110h+var_A0], r8
0x18000bb7c  mov     [rsp+110h+var_A8], rdx
0x18000bb81  lea     rdx, [rbp-80h+arg_38]
0x18000bb85  mov     [rsp+110h+var_B0], r8
0x18000bb8a  mov     [rsp+110h+var_B8], rdx
0x18000bb8f  lea     rdx, [rbp-80h+arg_30]
0x18000bb93  mov     [rsp+110h+var_C0], r8
0x18000bb98  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x18000bb9f  mov     [rsp+110h+var_C8], rdx
0x18000bba4  mov     edx, r10d
0x18000bba7  mov     [rsp+110h+var_D0], rax
0x18000bbac  lea     rax, [rbp-80h+arg_20]
0x18000bbb0  mov     [rsp+110h+var_D8], rcx
0x18000bbb5  mov     ecx, r11d
0x18000bbb8  mov     [rsp+110h+var_E0], r9
0x18000bbbd  mov     [rsp+110h+var_E8], rax
0x18000bbc2  mov     [rsp+110h+var_F0], r9
0x18000bbc7  lea     r9, [rbp-80h+arg_18]
0x18000bbcb  call    FastWppTraceMessage
0x18000bbd0  add     rsp, 110h
0x18000bbd7  pop     rbp
0x18000bbd8  retn
```
