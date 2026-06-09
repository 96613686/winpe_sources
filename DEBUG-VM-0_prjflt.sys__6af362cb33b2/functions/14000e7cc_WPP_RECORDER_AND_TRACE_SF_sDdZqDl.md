# WPP_RECORDER_AND_TRACE_SF_sDdZqDl

- ea: `0x14000e7cc`
- end: `0x14000e9ed`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdZqDl`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000e7cc`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000e9cc`
- `WppRecorder!WppAutoLogTrace` at `0x14000e9cc`

## string_xrefs

- `0x14000e803`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x14000e8ef`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdZqDl(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        USHORT a7,
        int a8,
        int a9,
        ...)
{
  const wchar_t *v9; // rbx
  const wchar_t *v10; // rdi
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  const wchar_t *v15; // rax
  __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-D8h]
  __int64 v18; // [rsp+148h] [rbp+50h] BYREF
  va_list va; // [rsp+148h] [rbp+50h]
  __int64 v20; // [rsp+150h] [rbp+58h] BYREF
  va_list va1; // [rsp+150h] [rbp+58h]
  unsigned __int16 *v22; // [rsp+158h] [rbp+60h]
  __int64 v23; // [rsp+160h] [rbp+68h] BYREF
  va_list va2; // [rsp+160h] [rbp+68h]
  __int64 v25; // [rsp+168h] [rbp+70h] BYREF
  va_list va3; // [rsp+168h] [rbp+70h]
  va_list va4; // [rsp+170h] [rbp+78h] BYREF

  va_start(va4, a9);
  va_start(va3, a9);
  va_start(va2, a9);
  va_start(va1, a9);
  va_start(va, a9);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  v22 = va_arg(va2, unsigned __int16 *);
  va_copy(va3, va2);
  v23 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v25 = va_arg(va4, _QWORD);
  v9 = v22;
  v10 = L"NULL";
  if ( !a2 )
    goto LABEL_10;
  if ( !v22 )
  {
    v13 = 8;
    goto LABEL_6;
  }
  v13 = *v22;
  if ( !*v22 )
  {
LABEL_6:
    v14 = L"NULL";
    goto LABEL_7;
  }
  v14 = (const wchar_t *)*((_QWORD *)v22 + 1);
LABEL_7:
  v15 = v22;
  if ( !v22 )
    v15 = L"\b";
  FastWppTraceMessage(
    517,
    a7,
    (ULONGLONG)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
    "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
    42,
    va,
    4,
    va1,
    4,
    v15,
    2,
    v14,
    v13,
    va2,
    8,
    va3,
    4,
    va4,
    4,
    0);
LABEL_10:
  if ( a3 )
  {
    if ( v9 )
    {
      v16 = *v9;
      if ( *v9 )
        v10 = (const wchar_t *)*((_QWORD *)v9 + 1);
    }
    else
    {
      v16 = 8;
    }
    if ( !v9 )
      v9 = L"\b";
    LOWORD(v17) = a7;
    WppAutoLogTrace(
      a4,
      2,
      5,
      WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v17,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      v9,
      2,
      v10,
      v16,
      (__int64 *)va2,
      8,
      (__int64 *)va3,
      4,
      va4,
      4,
      0);
  }
}

```

## disassembly

```asm
0x14000e7cc  push    rbx
0x14000e7ce  push    rbp
0x14000e7cf  push    rsi
0x14000e7d0  push    rdi
0x14000e7d1  push    r12
0x14000e7d3  push    r13
0x14000e7d5  push    r14
0x14000e7d7  push    r15
0x14000e7d9  sub     rsp, 0B8h
0x14000e7e0  mov     rbx, [rsp+0F8h+arg_58]
0x14000e7e8  lea     rdi, aNull_0; "NULL"
0x14000e7ef  movzx   ebp, [rsp+0F8h+arg_30]
0x14000e7f7  mov     r12d, 8
0x14000e7fd  xor     r15d, r15d
0x14000e800  mov     r14, r9
0x14000e803  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e80a  mov     sil, r8b
0x14000e80d  lea     r8, asc_1400156D4; "\b"
0x14000e814  lea     r13d, [r12-4]
0x14000e819  test    dl, dl
0x14000e81b  jz      loc_14000E8F6
0x14000e821  test    rbx, rbx
0x14000e824  jz      short loc_14000E835
0x14000e826  movzx   ecx, word ptr [rbx]
0x14000e829  cmp     [rbx], r15w
0x14000e82d  jz      short loc_14000E838
0x14000e82f  mov     rdx, [rbx+8]
0x14000e833  jmp     short loc_14000E83B
0x14000e835  mov     rcx, r12
0x14000e838  mov     rdx, rdi
0x14000e83b  mov     [rsp+0F8h+var_60], r15
0x14000e843  test    rbx, rbx
0x14000e846  mov     [rsp+0F8h+var_68], r13
0x14000e84e  mov     r10d, 205h
0x14000e854  mov     rax, rbx
0x14000e857  cmovz   rax, r8
0x14000e85b  lea     r8, [rsp+0F8h+arg_70]
0x14000e863  mov     [rsp+0F8h+var_70], r8
0x14000e86b  lea     r8, [rsp+0F8h+arg_68]
0x14000e873  mov     [rsp+0F8h+var_78], r13
0x14000e87b  mov     [rsp+0F8h+var_80], r8
0x14000e880  lea     r8, [rsp+0F8h+arg_60]
0x14000e888  mov     [rsp+0F8h+var_88], r12
0x14000e88d  mov     [rsp+0F8h+var_90], r8
0x14000e892  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e899  mov     [rsp+0F8h+var_98], rcx
0x14000e89e  mov     ecx, r10d
0x14000e8a1  mov     [rsp+0F8h+var_A0], rdx
0x14000e8a6  mov     edx, ebp
0x14000e8a8  mov     [rsp+0F8h+var_A8], 2
0x14000e8b1  mov     [rsp+0F8h+var_B0], rax
0x14000e8b6  lea     rax, [rsp+0F8h+arg_50]
0x14000e8be  mov     [rsp+0F8h+var_B8], r13
0x14000e8c3  mov     [rsp+0F8h+var_C0], rax
0x14000e8c8  lea     rax, [rsp+0F8h+arg_48]
0x14000e8d0  mov     [rsp+0F8h+var_C8], r13
0x14000e8d5  mov     [rsp+0F8h+var_D0], rax
0x14000e8da  mov     [rsp+0F8h+var_D8], 2Ah ; '*'
0x14000e8e3  call    FastWppTraceMessage
0x14000e8e8  lea     r8, asc_1400156D4; "\b"
0x14000e8ef  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e8f6  test    sil, sil
0x14000e8f9  jz      loc_14000E9D8
0x14000e8ff  test    rbx, rbx
0x14000e902  jz      short loc_14000E913
0x14000e904  movzx   eax, word ptr [rbx]
0x14000e907  cmp     [rbx], r15w
0x14000e90b  jz      short loc_14000E916
0x14000e90d  mov     rdi, [rbx+8]
0x14000e911  jmp     short loc_14000E916
0x14000e913  mov     rax, r12
0x14000e916  mov     [rsp+0F8h+var_50], r15
0x14000e91e  lea     rcx, [rsp+0F8h+arg_70]
0x14000e926  mov     [rsp+0F8h+var_58], r13
0x14000e92e  test    rbx, rbx
0x14000e931  mov     [rsp+0F8h+var_60], rcx
0x14000e939  mov     edx, 2
0x14000e93e  mov     [rsp+0F8h+var_68], r13
0x14000e946  lea     rcx, [rsp+0F8h+arg_68]
0x14000e94e  mov     [rsp+0F8h+var_70], rcx
0x14000e956  cmovz   rbx, r8
0x14000e95a  mov     [rsp+0F8h+var_78], r12
0x14000e962  lea     rcx, [rsp+0F8h+arg_60]
0x14000e96a  mov     [rsp+0F8h+var_80], rcx
0x14000e96f  lea     r8d, [rdx+3]
0x14000e973  mov     [rsp+0F8h+var_88], rax
0x14000e978  mov     rcx, r14
0x14000e97b  mov     [rsp+0F8h+var_90], rdi
0x14000e980  lea     rax, [rsp+0F8h+arg_50]
0x14000e988  mov     [rsp+0F8h+var_98], 2
0x14000e991  mov     [rsp+0F8h+var_A0], rbx
0x14000e996  mov     [rsp+0F8h+var_A8], r13
0x14000e99b  mov     [rsp+0F8h+var_B0], rax
0x14000e9a0  lea     rax, [rsp+0F8h+arg_48]
0x14000e9a8  mov     [rsp+0F8h+var_B8], r13
0x14000e9ad  mov     [rsp+0F8h+var_C0], rax
0x14000e9b2  mov     [rsp+0F8h+var_C8], 2Ah ; '*'
0x14000e9bb  mov     [rsp+0F8h+var_D0], r9
0x14000e9c0  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e9c7  mov     word ptr [rsp+0F8h+var_D8], bp
0x14000e9cc  call    cs:__imp_WppAutoLogTrace
0x14000e9d3  nop     dword ptr [rax+rax+00h]
0x14000e9d8  add     rsp, 0B8h
0x14000e9df  pop     r15
0x14000e9e1  pop     r14
0x14000e9e3  pop     r13
0x14000e9e5  pop     r12
0x14000e9e7  pop     rdi
0x14000e9e8  pop     rsi
0x14000e9e9  pop     rbp
0x14000e9ea  pop     rbx
0x14000e9eb  retn
```
