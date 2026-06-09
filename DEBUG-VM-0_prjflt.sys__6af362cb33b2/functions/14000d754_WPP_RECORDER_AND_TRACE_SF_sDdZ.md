# WPP_RECORDER_AND_TRACE_SF_sDdZ

- ea: `0x14000d754`
- end: `0x14000d957`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdZ`
- size: `515`
- prototype: ``
- caller_count: `45`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b3c`
- `0x1400025f4`
- `0x1400047cc`
- `0x1400057b0`
- `0x140006a58`
- `0x140007300`
- `0x14000752c`
- `0x140022320`
- `0x140023d68`
- `0x140024184`
- `0x140028b30`
- `0x140029088`
- `0x140029214`
- `0x140029650`
- `0x14002a260`
- `0x14002aa24`
- `0x14002b0d0`
- `0x14002b3c0`
- `0x14002b888`
- `0x14002d988`
- `0x1400306f8`
- `0x140034428`
- `0x1400346f0`
- `0x1400349fc`
- `0x140034c70`
- `0x140034e88`
- `0x140035060`
- `0x140035f3c`
- `0x140037418`
- `0x140037b8c`
- `0x140038b78`
- `0x140038f1c`
- `0x1400396a4`
- `0x140039de8`
- `0x14003a6e4`
- `0x14003b724`
- `0x14003c4b8`
- `0x14003c668`
- `0x14003d620`
- `0x14003fdf0`
- `0x140041a3c`
- `0x140042658`
- `0x140042eac`
- `0x140043844`
- `0x140044794`

## callees

- `0x140005cf4`
- `0x14000d754`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000d936`
- `WppRecorder!WppAutoLogTrace` at `0x14000d936`

## pseudocode

```c
__int64 WPP_RECORDER_AND_TRACE_SF_sDdZ(
        __int16 a1,
        char a2,
        char a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned int a6,
        USHORT a7,
        ULONGLONG a8,
        const char *a9,
        ...)
{
  const wchar_t *v9; // rbx
  const wchar_t *v10; // r15
  const char *v11; // rdi
  __int64 v12; // rbp
  __int64 v13; // rsi
  __int64 result; // rax
  __int64 v16; // r14
  __int64 v18; // rcx
  const wchar_t *v19; // r8
  const wchar_t *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  const char *v23; // r9
  bool v24; // zf
  bool v25; // zf
  int v26; // [rsp+20h] [rbp-B8h]
  __int64 v27; // [rsp+88h] [rbp-50h]
  __int64 v28; // [rsp+90h] [rbp-48h]
  __int64 v29; // [rsp+98h] [rbp-40h]
  __int64 v30; // [rsp+A0h] [rbp-38h]
  __int64 v31; // [rsp+A8h] [rbp-30h]
  __int64 v33; // [rsp+128h] [rbp+50h] BYREF
  va_list va; // [rsp+128h] [rbp+50h]
  __int64 v35; // [rsp+130h] [rbp+58h] BYREF
  va_list va1; // [rsp+130h] [rbp+58h]
  unsigned __int16 *v37; // [rsp+138h] [rbp+60h]
  va_list va2; // [rsp+140h] [rbp+68h] BYREF

  va_start(va2, a9);
  va_start(va1, a9);
  va_start(va, a9);
  v33 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v35 = va_arg(va2, _QWORD);
  v37 = va_arg(va2, unsigned __int16 *);
  v9 = v37;
  v10 = L"NULL";
  v11 = a9;
  v12 = 8;
  v13 = -1;
  result = a4;
  v16 = 5;
  if ( !a2 )
    goto LABEL_17;
  if ( !v37 )
  {
    v18 = 8;
    goto LABEL_6;
  }
  v18 = *v37;
  if ( !*v37 )
  {
LABEL_6:
    v19 = L"NULL";
    goto LABEL_7;
  }
  v19 = (const wchar_t *)*((_QWORD *)v37 + 1);
LABEL_7:
  v20 = v37;
  if ( !v37 )
    v20 = L"\b";
  if ( a9 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a9[v21] );
    v22 = v21 + 1;
  }
  else
  {
    v22 = 5;
  }
  v23 = a9;
  if ( !a9 )
    v23 = "NULL";
  FastWppTraceMessage(a1, a7, a8, v23, v22, va, 4, va1, 4, v20, 2, v19, v18, 0);
  result = a4;
LABEL_17:
  if ( a3 )
  {
    v24 = v9 == 0;
    if ( v9 )
    {
      v12 = *v9;
      if ( *v9 )
        v10 = (const wchar_t *)*((_QWORD *)v9 + 1);
      v24 = v9 == 0;
    }
    if ( v24 )
      v9 = L"\b";
    v25 = a9 == 0;
    if ( a9 )
    {
      do
        ++v13;
      while ( a9[v13] );
      v16 = v13 + 1;
      v25 = a9 == 0;
    }
    if ( v25 )
      v11 = "NULL";
    LOWORD(v26) = a7;
    return WppAutoLogTrace(
             result,
             a5,
             a6,
             a8,
             v26,
             v11,
             v16,
             (__int64 *)va,
             4,
             (__int64 *)va1,
             4,
             v9,
             2,
             v10,
             v12,
             0,
             "NULL",
             v27,
             v28,
             v29,
             v30,
             v31);
  }
  return result;
}

```

## disassembly

```asm
0x14000d754  mov     [rsp+arg_18], r9
0x14000d759  push    rbx
0x14000d75a  push    rbp
0x14000d75b  push    rsi
0x14000d75c  push    rdi
0x14000d75d  push    r12
0x14000d75f  push    r13
0x14000d761  push    r14
0x14000d763  push    r15
0x14000d765  sub     rsp, 98h
0x14000d76c  mov     rbx, [rsp+0D8h+arg_58]
0x14000d774  lea     r15, aNull_0; "NULL"
0x14000d77b  mov     rdi, [rsp+0D8h+arg_40]
0x14000d783  mov     ebp, 8
0x14000d788  movzx   r13d, [rsp+0D8h+arg_30]
0x14000d791  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d795  movzx   r10d, cx
0x14000d799  xor     r11d, r11d
0x14000d79c  lea     rcx, aNull; "NULL"
0x14000d7a3  mov     rax, r9
0x14000d7a6  mov     [rsp+0D8h+var_58], rcx
0x14000d7ae  lea     r14d, [rbp-3]
0x14000d7b2  lea     r9, asc_1400156D4; "\b"
0x14000d7b9  mov     r12b, r8b
0x14000d7bc  test    dl, dl
0x14000d7be  jz      loc_14000D887
0x14000d7c4  test    rbx, rbx
0x14000d7c7  jz      short loc_14000D7D8
0x14000d7c9  movzx   ecx, word ptr [rbx]
0x14000d7cc  cmp     [rbx], r11w
0x14000d7d0  jz      short loc_14000D7DB
0x14000d7d2  mov     r8, [rbx+8]
0x14000d7d6  jmp     short loc_14000D7DE
0x14000d7d8  mov     rcx, rbp
0x14000d7db  mov     r8, r15
0x14000d7de  test    rbx, rbx
0x14000d7e1  mov     rdx, rbx
0x14000d7e4  cmovz   rdx, r9
0x14000d7e8  test    rdi, rdi
0x14000d7eb  jz      short loc_14000D7FE
0x14000d7ed  mov     rax, rsi
0x14000d7f0  inc     rax
0x14000d7f3  cmp     [rdi+rax], r11b
0x14000d7f7  jnz     short loc_14000D7F0
0x14000d7f9  inc     rax
0x14000d7fc  jmp     short loc_14000D801
0x14000d7fe  mov     rax, r14
0x14000d801  mov     [rsp+0D8h+var_70], r11
0x14000d806  test    rdi, rdi
0x14000d809  mov     [rsp+0D8h+var_78], rcx
0x14000d80e  mov     r9, rdi
0x14000d811  cmovz   r9, [rsp+0D8h+var_58]
0x14000d81a  lea     rcx, [rsp+0D8h+arg_50]
0x14000d822  mov     [rsp+0D8h+var_80], r8
0x14000d827  mov     r8, [rsp+0D8h+arg_38]
0x14000d82f  mov     [rsp+0D8h+var_88], 2
0x14000d838  mov     [rsp+0D8h+var_90], rdx
0x14000d83d  mov     edx, 4
0x14000d842  mov     [rsp+0D8h+var_98], rdx
0x14000d847  mov     [rsp+0D8h+var_A0], rcx
0x14000d84c  lea     rcx, [rsp+0D8h+arg_48]
0x14000d854  mov     [rsp+0D8h+var_A8], rdx
0x14000d859  mov     edx, r13d
0x14000d85c  mov     [rsp+0D8h+var_B0], rcx
0x14000d861  mov     ecx, r10d
0x14000d864  mov     [rsp+0D8h+var_B8], rax
0x14000d869  call    FastWppTraceMessage
0x14000d86e  mov     rax, [rsp+0D8h+arg_18]
0x14000d876  lea     r9, asc_1400156D4; "\b"
0x14000d87d  xor     r11d, r11d
0x14000d880  lea     rcx, aNull; "NULL"
0x14000d887  test    r12b, r12b
0x14000d88a  jz      loc_14000D942
0x14000d890  test    rbx, rbx
0x14000d893  jz      short loc_14000D8A5
0x14000d895  movzx   ebp, word ptr [rbx]
0x14000d898  cmp     [rbx], r11w
0x14000d89c  jz      short loc_14000D8A2
0x14000d89e  mov     r15, [rbx+8]
0x14000d8a2  test    rbx, rbx
0x14000d8a5  cmovz   rbx, r9
0x14000d8a9  test    rdi, rdi
0x14000d8ac  jz      short loc_14000D8BE
0x14000d8ae  inc     rsi
0x14000d8b1  cmp     [rdi+rsi], r11b
0x14000d8b5  jnz     short loc_14000D8AE
0x14000d8b7  lea     r14, [rsi+1]
0x14000d8bb  test    rdi, rdi
0x14000d8be  mov     r9, [rsp+0D8h+arg_38]
0x14000d8c6  cmovz   rdi, rcx
0x14000d8ca  mov     r8d, [rsp+0D8h+arg_28]
0x14000d8d2  lea     rcx, [rsp+0D8h+arg_50]
0x14000d8da  movzx   edx, [rsp+0D8h+arg_20]
0x14000d8e2  mov     [rsp+0D8h+var_60], r11
0x14000d8e7  mov     [rsp+0D8h+var_68], rbp
0x14000d8ec  mov     [rsp+0D8h+var_70], r15
0x14000d8f1  mov     [rsp+0D8h+var_78], 2
0x14000d8fa  mov     [rsp+0D8h+var_80], rbx
0x14000d8ff  mov     [rsp+0D8h+var_88], 4
0x14000d908  mov     [rsp+0D8h+var_90], rcx
0x14000d90d  lea     rcx, [rsp+0D8h+arg_48]
0x14000d915  mov     [rsp+0D8h+var_98], 4
0x14000d91e  mov     [rsp+0D8h+var_A0], rcx
0x14000d923  mov     rcx, rax
0x14000d926  mov     [rsp+0D8h+var_A8], r14
0x14000d92b  mov     [rsp+0D8h+var_B0], rdi
0x14000d930  mov     word ptr [rsp+0D8h+var_B8], r13w
0x14000d936  call    cs:__imp_WppAutoLogTrace
0x14000d93d  nop     dword ptr [rax+rax+00h]
0x14000d942  add     rsp, 98h
0x14000d949  pop     r15
0x14000d94b  pop     r14
0x14000d94d  pop     r13
0x14000d94f  pop     r12
0x14000d951  pop     rdi
0x14000d952  pop     rsi
0x14000d953  pop     rbp
0x14000d954  pop     rbx
0x14000d955  retn
```
