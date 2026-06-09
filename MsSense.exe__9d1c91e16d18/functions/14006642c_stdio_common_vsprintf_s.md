# __stdio_common_vsprintf_s

- ea: `0x14006642c`
- end: `0x14006653d`
- name: `__stdio_common_vsprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400310f8`

## callees

- `0x140061148`
- `0x14006147c`
- `0x1400616d8`
- `0x14006642c`

## pseudocode

```c
int __cdecl _stdio_common_vsprintf_s(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  struct localeinfo_struct v7; // xmm0
  int v8; // eax
  int v9; // edi
  int v10; // ebx
  int v11; // ebx
  _QWORD v13[2]; // [rsp+30h] [rbp-40h] BYREF
  char v14; // [rsp+40h] [rbp-30h]
  struct localeinfo_struct v15; // [rsp+48h] [rbp-28h]
  char v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]
  char v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+64h] [rbp-Ch]
  char v20; // [rsp+68h] [rbp-8h]

  v13[0] = 0;
  v14 = 0;
  v16 = 0;
  v18 = 0;
  v20 = 0;
  if ( Locale )
  {
    v7 = *Locale;
LABEL_5:
    v16 = 1;
    v15 = v7;
    goto LABEL_6;
  }
  if ( !dword_1400C43C8 )
  {
    v7 = *(struct localeinfo_struct *)&off_1400BE1B8;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || !Buffer || !BufferCount )
  {
    v17 = 22;
    goto LABEL_14;
  }
  v8 = sub_1400616D8(Options, (int)Buffer, BufferCount, (int)Format, (__crt_cached_ptd_host *)v13, (__int64)ArgList);
  v9 = v8;
  if ( v8 < 0 )
    *Buffer = 0;
  if ( v8 == -2 )
  {
    v17 = 34;
LABEL_14:
    v18 = 1;
    sub_14006147C(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v13);
    v9 = -1;
  }
  if ( v16 == 2 )
    *(_DWORD *)(v13[0] + 936LL) &= ~2u;
  if ( v18 )
  {
    v10 = v17;
    *(_DWORD *)(unknown_libname_67(v13) + 32) = v10;
  }
  if ( v20 )
  {
    v11 = v19;
    *(_DWORD *)(unknown_libname_67(v13) + 36) = v11;
  }
  return v9;
}

```

## disassembly

```asm
0x14006642c  mov     [rsp-8+arg_0], rbx
0x140066431  mov     [rsp-8+arg_8], rsi
0x140066436  mov     [rsp-8+arg_10], rdi
0x14006643b  push    rbp
0x14006643c  mov     rbp, rsp
0x14006643f  sub     rsp, 70h
0x140066443  mov     rax, [rbp+Locale]
0x140066447  xor     esi, esi
0x140066449  mov     [rbp+var_40], rsi
0x14006644d  mov     rbx, rdx
0x140066450  mov     [rbp+var_30], sil
0x140066454  mov     [rbp+var_18], sil
0x140066458  mov     [rbp+var_10], sil
0x14006645c  mov     [rbp+var_8], sil
0x140066460  test    rax, rax
0x140066463  jz      short loc_14006646A
0x140066465  movups  xmm0, xmmword ptr [rax]
0x140066468  jmp     short loc_140066479
0x14006646a  cmp     cs:dword_1400C43C8, esi
0x140066470  jnz     short loc_140066482
0x140066472  movups  xmm0, xmmword ptr cs:off_1400BE1B8
0x140066479  mov     [rbp+var_18], 1
0x14006647d  movdqu  [rbp+var_28], xmm0
0x140066482  test    r9, r9
0x140066485  jz      short loc_1400664BF
0x140066487  test    rbx, rbx
0x14006648a  jz      short loc_1400664BF
0x14006648c  test    r8, r8
0x14006648f  jz      short loc_1400664BF
0x140066491  mov     rax, [rbp+ArgList]
0x140066495  mov     [rsp+70h+var_48], rax; __int64
0x14006649a  lea     rax, [rbp+var_40]
0x14006649e  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x1400664a3  call    sub_1400616D8
0x1400664a8  mov     edi, eax
0x1400664aa  test    eax, eax
0x1400664ac  jns     short loc_1400664B1
0x1400664ae  mov     [rbx], sil
0x1400664b1  cmp     eax, 0FFFFFFFEh
0x1400664b4  jnz     short loc_1400664EA
0x1400664b6  mov     [rbp+var_14], 22h ; '"'
0x1400664bd  jmp     short loc_1400664C6
0x1400664bf  mov     [rbp+var_14], 16h
0x1400664c6  lea     rax, [rbp+var_40]
0x1400664ca  mov     [rbp+var_10], 1
0x1400664ce  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x1400664d3  xor     r9d, r9d; LineNo
0x1400664d6  xor     r8d, r8d; FileName
0x1400664d9  mov     [rsp+70h+var_50], rsi; uintptr_t
0x1400664de  xor     edx, edx; FunctionName
0x1400664e0  xor     ecx, ecx; Expression
0x1400664e2  call    sub_14006147C
0x1400664e7  or      edi, 0FFFFFFFFh
0x1400664ea  cmp     [rbp+var_18], 2
0x1400664ee  jnz     short loc_1400664FB
0x1400664f0  mov     rax, [rbp+var_40]
0x1400664f4  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1400664fb  cmp     [rbp+var_10], sil
0x1400664ff  jz      short loc_140066510
0x140066501  mov     ebx, [rbp+var_14]
0x140066504  lea     rcx, [rbp+var_40]
0x140066508  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x14006650d  mov     [rax+20h], ebx
0x140066510  cmp     [rbp+var_8], sil
0x140066514  jz      short loc_140066525
0x140066516  mov     ebx, [rbp+var_C]
0x140066519  lea     rcx, [rbp+var_40]
0x14006651d  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x140066522  mov     [rax+24h], ebx
0x140066525  lea     r11, [rsp+70h+var_s0]
0x14006652a  mov     eax, edi
0x14006652c  mov     rbx, [r11+10h]
0x140066530  mov     rsi, [r11+18h]
0x140066534  mov     rdi, [r11+20h]
0x140066538  mov     rsp, r11
0x14006653b  pop     rbp
0x14006653c  retn
```
