# __stdio_common_vsprintf_s

- ea: `0x14000f644`
- end: `0x14000f755`
- name: `__stdio_common_vsprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140041318`

## callees

- `0x1400042e0`
- `0x140004614`
- `0x14000b120`
- `0x14000f644`

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
  if ( !dword_1400D6988 )
  {
    v7 = *(struct localeinfo_struct *)&off_1400D5158;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || !Buffer || !BufferCount )
  {
    v17 = 22;
    goto LABEL_14;
  }
  v8 = sub_14000B120(Options, (int)Buffer, BufferCount, (int)Format, (__crt_cached_ptd_host *)v13, (__int64)ArgList);
  v9 = v8;
  if ( v8 < 0 )
    *Buffer = 0;
  if ( v8 == -2 )
  {
    v17 = 34;
LABEL_14:
    v18 = 1;
    sub_140004614(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v13);
    v9 = -1;
  }
  if ( v16 == 2 )
    *(_DWORD *)(v13[0] + 936LL) &= ~2u;
  if ( v18 )
  {
    v10 = v17;
    *(_DWORD *)(unknown_libname_44(v13) + 32) = v10;
  }
  if ( v20 )
  {
    v11 = v19;
    *(_DWORD *)(unknown_libname_44(v13) + 36) = v11;
  }
  return v9;
}

```

## disassembly

```asm
0x14000f644  mov     [rsp-8+arg_0], rbx
0x14000f649  mov     [rsp-8+arg_8], rsi
0x14000f64e  mov     [rsp-8+arg_10], rdi
0x14000f653  push    rbp
0x14000f654  mov     rbp, rsp
0x14000f657  sub     rsp, 70h
0x14000f65b  mov     rax, [rbp+Locale]
0x14000f65f  xor     esi, esi
0x14000f661  mov     [rbp+var_40], rsi
0x14000f665  mov     rbx, rdx
0x14000f668  mov     [rbp+var_30], sil
0x14000f66c  mov     [rbp+var_18], sil
0x14000f670  mov     [rbp+var_10], sil
0x14000f674  mov     [rbp+var_8], sil
0x14000f678  test    rax, rax
0x14000f67b  jz      short loc_14000F682
0x14000f67d  movups  xmm0, xmmword ptr [rax]
0x14000f680  jmp     short loc_14000F691
0x14000f682  cmp     cs:dword_1400D6988, esi
0x14000f688  jnz     short loc_14000F69A
0x14000f68a  movups  xmm0, xmmword ptr cs:off_1400D5158
0x14000f691  mov     [rbp+var_18], 1
0x14000f695  movdqu  [rbp+var_28], xmm0
0x14000f69a  test    r9, r9
0x14000f69d  jz      short loc_14000F6D7
0x14000f69f  test    rbx, rbx
0x14000f6a2  jz      short loc_14000F6D7
0x14000f6a4  test    r8, r8
0x14000f6a7  jz      short loc_14000F6D7
0x14000f6a9  mov     rax, [rbp+ArgList]
0x14000f6ad  mov     [rsp+70h+var_48], rax; __int64
0x14000f6b2  lea     rax, [rbp+var_40]
0x14000f6b6  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x14000f6bb  call    sub_14000B120
0x14000f6c0  mov     edi, eax
0x14000f6c2  test    eax, eax
0x14000f6c4  jns     short loc_14000F6C9
0x14000f6c6  mov     [rbx], sil
0x14000f6c9  cmp     eax, 0FFFFFFFEh
0x14000f6cc  jnz     short loc_14000F702
0x14000f6ce  mov     [rbp+var_14], 22h ; '"'
0x14000f6d5  jmp     short loc_14000F6DE
0x14000f6d7  mov     [rbp+var_14], 16h
0x14000f6de  lea     rax, [rbp+var_40]
0x14000f6e2  mov     [rbp+var_10], 1
0x14000f6e6  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x14000f6eb  xor     r9d, r9d; LineNo
0x14000f6ee  xor     r8d, r8d; FileName
0x14000f6f1  mov     [rsp+70h+var_50], rsi; uintptr_t
0x14000f6f6  xor     edx, edx; FunctionName
0x14000f6f8  xor     ecx, ecx; Expression
0x14000f6fa  call    sub_140004614
0x14000f6ff  or      edi, 0FFFFFFFFh
0x14000f702  cmp     [rbp+var_18], 2
0x14000f706  jnz     short loc_14000F713
0x14000f708  mov     rax, [rbp+var_40]
0x14000f70c  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x14000f713  cmp     [rbp+var_10], sil
0x14000f717  jz      short loc_14000F728
0x14000f719  mov     ebx, [rbp+var_14]
0x14000f71c  lea     rcx, [rbp+var_40]
0x14000f720  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000f725  mov     [rax+20h], ebx
0x14000f728  cmp     [rbp+var_8], sil
0x14000f72c  jz      short loc_14000F73D
0x14000f72e  mov     ebx, [rbp+var_C]
0x14000f731  lea     rcx, [rbp+var_40]
0x14000f735  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000f73a  mov     [rax+24h], ebx
0x14000f73d  lea     r11, [rsp+70h+var_s0]
0x14000f742  mov     eax, edi
0x14000f744  mov     rbx, [r11+10h]
0x14000f748  mov     rsi, [r11+18h]
0x14000f74c  mov     rdi, [r11+20h]
0x14000f750  mov     rsp, r11
0x14000f753  pop     rbp
0x14000f754  retn
```
