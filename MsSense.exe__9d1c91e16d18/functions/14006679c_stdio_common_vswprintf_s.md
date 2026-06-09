# __stdio_common_vswprintf_s

- ea: `0x14006679c`
- end: `0x1400668ad`
- name: `__stdio_common_vswprintf_s`
- size: `273`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002b18c`

## callees

- `0x140061148`
- `0x14006147c`
- `0x140061888`
- `0x14006679c`

## pseudocode

```c
int __cdecl _stdio_common_vswprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
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
  v8 = sub_140061888(Options, (int)Buffer, BufferCount, (int)Format, (__crt_cached_ptd_host *)v13, (__int64)ArgList);
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
0x14006679c  mov     [rsp-8+arg_0], rbx
0x1400667a1  mov     [rsp-8+arg_8], rsi
0x1400667a6  mov     [rsp-8+arg_10], rdi
0x1400667ab  push    rbp
0x1400667ac  mov     rbp, rsp
0x1400667af  sub     rsp, 70h
0x1400667b3  mov     rax, [rbp+Locale]
0x1400667b7  xor     esi, esi
0x1400667b9  mov     [rbp+var_40], rsi
0x1400667bd  mov     rbx, rdx
0x1400667c0  mov     [rbp+var_30], sil
0x1400667c4  mov     [rbp+var_18], sil
0x1400667c8  mov     [rbp+var_10], sil
0x1400667cc  mov     [rbp+var_8], sil
0x1400667d0  test    rax, rax
0x1400667d3  jz      short loc_1400667DA
0x1400667d5  movups  xmm0, xmmword ptr [rax]
0x1400667d8  jmp     short loc_1400667E9
0x1400667da  cmp     cs:dword_1400C43C8, esi
0x1400667e0  jnz     short loc_1400667F2
0x1400667e2  movups  xmm0, xmmword ptr cs:off_1400BE1B8
0x1400667e9  mov     [rbp+var_18], 1
0x1400667ed  movdqu  [rbp+var_28], xmm0
0x1400667f2  test    r9, r9
0x1400667f5  jz      short loc_14006682F
0x1400667f7  test    rbx, rbx
0x1400667fa  jz      short loc_14006682F
0x1400667fc  test    r8, r8
0x1400667ff  jz      short loc_14006682F
0x140066801  mov     rax, [rbp+ArgList]
0x140066805  mov     [rsp+70h+var_48], rax; __int64
0x14006680a  lea     rax, [rbp+var_40]
0x14006680e  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x140066813  call    sub_140061888
0x140066818  mov     edi, eax
0x14006681a  test    eax, eax
0x14006681c  jns     short loc_140066821
0x14006681e  mov     [rbx], si
0x140066821  cmp     eax, 0FFFFFFFEh
0x140066824  jnz     short loc_14006685A
0x140066826  mov     [rbp+var_14], 22h ; '"'
0x14006682d  jmp     short loc_140066836
0x14006682f  mov     [rbp+var_14], 16h
0x140066836  lea     rax, [rbp+var_40]
0x14006683a  mov     [rbp+var_10], 1
0x14006683e  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x140066843  xor     r9d, r9d; LineNo
0x140066846  xor     r8d, r8d; FileName
0x140066849  mov     [rsp+70h+var_50], rsi; uintptr_t
0x14006684e  xor     edx, edx; FunctionName
0x140066850  xor     ecx, ecx; Expression
0x140066852  call    sub_14006147C
0x140066857  or      edi, 0FFFFFFFFh
0x14006685a  cmp     [rbp+var_18], 2
0x14006685e  jnz     short loc_14006686B
0x140066860  mov     rax, [rbp+var_40]
0x140066864  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x14006686b  cmp     [rbp+var_10], sil
0x14006686f  jz      short loc_140066880
0x140066871  mov     ebx, [rbp+var_14]
0x140066874  lea     rcx, [rbp+var_40]
0x140066878  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x14006687d  mov     [rax+20h], ebx
0x140066880  cmp     [rbp+var_8], sil
0x140066884  jz      short loc_140066895
0x140066886  mov     ebx, [rbp+var_C]
0x140066889  lea     rcx, [rbp+var_40]
0x14006688d  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x140066892  mov     [rax+24h], ebx
0x140066895  lea     r11, [rsp+70h+var_s0]
0x14006689a  mov     eax, edi
0x14006689c  mov     rbx, [r11+10h]
0x1400668a0  mov     rsi, [r11+18h]
0x1400668a4  mov     rdi, [r11+20h]
0x1400668a8  mov     rsp, r11
0x1400668ab  pop     rbp
0x1400668ac  retn
```
