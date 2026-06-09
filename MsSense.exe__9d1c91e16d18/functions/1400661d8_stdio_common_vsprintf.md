# __stdio_common_vsprintf

- ea: `0x1400661d8`
- end: `0x140066429`
- name: `__stdio_common_vsprintf`
- size: `593`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140060b84`

## callees

- `0x140051ba0`
- `0x140061148`
- `0x14006147c`
- `0x140063e2c`
- `0x1400661d8`
- `0x140072280`

## pseudocode

```c
int __cdecl _stdio_common_vsprintf(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  char v8; // r15
  struct localeinfo_struct v9; // xmm0
  size_t v10; // rdi
  int v11; // eax
  __int64 v12; // rax
  void *v13; // rcx
  int v14; // ebx
  int v15; // ebx
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  char v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+49h] [rbp-B7h]
  __int16 v21; // [rsp+4Dh] [rbp-B3h]
  char v22; // [rsp+4Fh] [rbp-B1h]
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+60h] [rbp-A0h]
  struct localeinfo_struct v25; // [rsp+68h] [rbp-98h]
  char v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+7Ch] [rbp-84h]
  char v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+84h] [rbp-7Ch]
  char v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[4]; // [rsp+90h] [rbp-70h] BYREF
  int v32; // [rsp+B0h] [rbp-50h]
  char v33; // [rsp+B4h] [rbp-4Ch]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+C0h] [rbp-40h]
  __int16 v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+D8h] [rbp-28h]
  char v38; // [rsp+DCh] [rbp-24h]
  void *Block[2]; // [rsp+4E0h] [rbp+3E0h]
  _QWORD *v40; // [rsp+4F0h] [rbp+3F0h]
  int v41; // [rsp+4F8h] [rbp+3F8h]

  v23[0] = 0;
  v24 = 0;
  v26 = 0;
  v8 = Options;
  v28 = 0;
  v30 = 0;
  if ( Locale )
  {
    v9 = *Locale;
LABEL_5:
    v26 = 1;
    v25 = v9;
    goto LABEL_6;
  }
  if ( !dword_1400C43C8 )
  {
    v9 = *(struct localeinfo_struct *)&off_1400BE1B8;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || BufferCount && !Buffer )
  {
    v28 = 1;
    v27 = 22;
    sub_14006147C(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v23);
LABEL_8:
    LODWORD(v10) = -1;
    goto LABEL_34;
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v17[0] = Buffer;
  v17[1] = BufferCount;
  v18 = 0;
  if ( (Options & 2) != 0 || (v19 = 0, !Buffer) )
    v19 = 1;
  v32 = 0;
  v31[1] = v23;
  v33 = 0;
  v40 = v17;
  v31[3] = ArgList;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)Block = 0;
  v31[0] = Options;
  v31[2] = Format;
  v41 = 0;
  v11 = sub_140063E2C(v31);
  v10 = v11;
  if ( !Buffer )
    goto LABEL_33;
  if ( (v8 & 1) != 0 )
  {
    if ( !BufferCount && v11 )
      goto LABEL_18;
    v12 = v18;
    if ( v18 == BufferCount )
    {
      if ( (v10 & 0x80000000) == 0LL && v10 > BufferCount )
        goto LABEL_18;
      goto LABEL_33;
    }
    goto LABEL_32;
  }
  if ( (v8 & 2) == 0 )
  {
    if ( !BufferCount )
    {
LABEL_18:
      free_base(Block[1]);
      goto LABEL_8;
    }
    v12 = v18;
    if ( v18 == BufferCount )
    {
      v13 = Block[1];
      Buffer[BufferCount - 1] = 0;
      free_base(v13);
      LODWORD(v10) = -2;
      goto LABEL_34;
    }
    goto LABEL_32;
  }
  if ( BufferCount )
  {
    if ( v11 < 0 )
    {
      *Buffer = 0;
      goto LABEL_33;
    }
    v12 = v18;
    if ( v18 == BufferCount )
    {
      Buffer[BufferCount - 1] = 0;
      goto LABEL_33;
    }
LABEL_32:
    Buffer[v12] = 0;
  }
LABEL_33:
  free_base(Block[1]);
LABEL_34:
  if ( v26 == 2 )
    *(_DWORD *)(v23[0] + 936LL) &= ~2u;
  if ( v28 )
  {
    v14 = v27;
    *(_DWORD *)(unknown_libname_67(v23) + 32) = v14;
  }
  if ( v30 )
  {
    v15 = v29;
    *(_DWORD *)(unknown_libname_67(v23) + 36) = v15;
  }
  return v10;
}

```

## disassembly

```asm
0x1400661d8  push    rbp
0x1400661da  push    rbx
0x1400661db  push    rsi
0x1400661dc  push    rdi
0x1400661dd  push    r12
0x1400661df  push    r14
0x1400661e1  push    r15
0x1400661e3  lea     rbp, [rsp-410h]
0x1400661eb  sub     rsp, 510h
0x1400661f2  mov     rax, cs:__security_cookie
0x1400661f9  xor     rax, rsp
0x1400661fc  mov     [rbp+440h+var_40], rax
0x140066203  mov     rax, [rbp+440h+Locale]
0x14006620a  xor     r12d, r12d
0x14006620d  mov     [rsp+540h+var_4F0], r12
0x140066212  mov     rbx, r8
0x140066215  mov     [rsp+540h+var_4E0], r12b
0x14006621a  mov     rsi, rdx
0x14006621d  mov     [rsp+540h+var_4C8], r12b
0x140066222  mov     r15, rcx
0x140066225  mov     [rbp+440h+var_4C0], r12b
0x140066229  mov     [rbp+440h+var_4B8], r12b
0x14006622d  test    rax, rax
0x140066230  jz      short loc_140066237
0x140066232  movups  xmm0, xmmword ptr [rax]
0x140066235  jmp     short loc_140066247
0x140066237  cmp     cs:dword_1400C43C8, r12d
0x14006623e  jnz     short loc_140066252
0x140066240  movups  xmm0, xmmword ptr cs:off_1400BE1B8
0x140066247  mov     [rsp+540h+var_4C8], 1
0x14006624c  movdqu  [rsp+540h+var_4D8], xmm0
0x140066252  test    r9, r9
0x140066255  jnz     short loc_140066289
0x140066257  lea     rax, [rsp+540h+var_4F0]
0x14006625c  mov     [rbp+440h+var_4C0], 1
0x140066260  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x140066265  xor     r9d, r9d; LineNo
0x140066268  xor     r8d, r8d; FileName
0x14006626b  mov     [rsp+540h+var_520], r12; uintptr_t
0x140066270  xor     edx, edx; FunctionName
0x140066272  mov     [rsp+540h+var_4C4], 16h
0x14006627a  xor     ecx, ecx; Expression
0x14006627c  call    sub_14006147C
0x140066281  or      edi, 0FFFFFFFFh
0x140066284  jmp     loc_1400663C6
0x140066289  test    rbx, rbx
0x14006628c  jz      short loc_140066293
0x14006628e  test    rsi, rsi
0x140066291  jz      short loc_140066257
0x140066293  mov     r14, r15
0x140066296  mov     [rsp+540h+var_4F7], r12d
0x14006629b  mov     [rsp+540h+var_4F3], r12w
0x1400662a1  mov     [rsp+540h+var_4F1], r12b
0x1400662a6  mov     [rsp+540h+var_510], rsi
0x1400662ab  mov     [rsp+540h+var_508], rbx
0x1400662b0  mov     [rsp+540h+var_500], r12
0x1400662b5  and     r14d, 2
0x1400662b9  jnz     short loc_1400662C5
0x1400662bb  mov     [rsp+540h+var_4F8], r12b
0x1400662c0  test    rsi, rsi
0x1400662c3  jnz     short loc_1400662CA
0x1400662c5  mov     [rsp+540h+var_4F8], 1
0x1400662ca  lea     rax, [rsp+540h+var_4F0]
0x1400662cf  mov     [rbp+440h+var_490], r12d
0x1400662d3  mov     [rbp+440h+var_4A8], rax
0x1400662d7  lea     rcx, [rbp+440h+var_4B0]
0x1400662db  lea     rax, [rsp+540h+var_510]
0x1400662e0  mov     [rbp+440h+var_48C], r12b
0x1400662e4  mov     [rbp+440h+var_50], rax
0x1400662eb  xorps   xmm0, xmm0
0x1400662ee  mov     rax, [rbp+440h+ArgList]
0x1400662f5  mov     [rbp+440h+var_498], rax
0x1400662f9  mov     [rbp+440h+var_488], r12
0x1400662fd  mov     [rbp+440h+var_480], r12d
0x140066301  mov     [rbp+440h+var_478], r12w
0x140066306  mov     [rbp+440h+var_468], r12d
0x14006630a  mov     [rbp+440h+var_464], r12b
0x14006630e  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x140066316  mov     [rbp+440h+var_4B0], r15
0x14006631a  mov     [rbp+440h+var_4A0], r9
0x14006631e  mov     [rbp+440h+var_48], r12d
0x140066325  call    sub_140063E2C
0x14006632a  movsxd  rdi, eax
0x14006632d  test    rsi, rsi
0x140066330  jz      loc_1400663BA
0x140066336  test    r15b, 1
0x14006633a  jz      short loc_14006636B
0x14006633c  test    rbx, rbx
0x14006633f  jnz     short loc_140066356
0x140066341  test    eax, eax
0x140066343  jz      short loc_140066356
0x140066345  mov     rcx, [rbp+440h+Block+8]; Block
0x14006634c  call    _free_base
0x140066351  jmp     loc_140066281
0x140066356  mov     rax, [rsp+540h+var_500]
0x14006635b  cmp     rax, rbx
0x14006635e  jnz     short loc_1400663B6
0x140066360  test    edi, edi
0x140066362  js      short loc_1400663BA
0x140066364  cmp     rdi, rbx
0x140066367  jbe     short loc_1400663BA
0x140066369  jmp     short loc_140066345
0x14006636b  test    r14, r14
0x14006636e  jz      short loc_14006638F
0x140066370  test    rbx, rbx
0x140066373  jz      short loc_1400663BA
0x140066375  test    eax, eax
0x140066377  jns     short loc_14006637E
0x140066379  mov     [rsi], r12b
0x14006637c  jmp     short loc_1400663BA
0x14006637e  mov     rax, [rsp+540h+var_500]
0x140066383  cmp     rax, rbx
0x140066386  jnz     short loc_1400663B6
0x140066388  mov     [rbx+rsi-1], r12b
0x14006638d  jmp     short loc_1400663BA
0x14006638f  test    rbx, rbx
0x140066392  jz      short loc_140066345
0x140066394  mov     rax, [rsp+540h+var_500]
0x140066399  cmp     rax, rbx
0x14006639c  jnz     short loc_1400663B6
0x14006639e  mov     rcx, [rbp+440h+Block+8]; Block
0x1400663a5  mov     [rbx+rsi-1], r12b
0x1400663aa  call    _free_base
0x1400663af  mov     edi, 0FFFFFFFEh
0x1400663b4  jmp     short loc_1400663C6
0x1400663b6  mov     [rax+rsi], r12b
0x1400663ba  mov     rcx, [rbp+440h+Block+8]; Block
0x1400663c1  call    _free_base
0x1400663c6  cmp     [rsp+540h+var_4C8], 2
0x1400663cb  jnz     short loc_1400663D9
0x1400663cd  mov     rax, [rsp+540h+var_4F0]
0x1400663d2  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1400663d9  cmp     [rbp+440h+var_4C0], r12b
0x1400663dd  jz      short loc_1400663F0
0x1400663df  mov     ebx, [rsp+540h+var_4C4]
0x1400663e3  lea     rcx, [rsp+540h+var_4F0]
0x1400663e8  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x1400663ed  mov     [rax+20h], ebx
0x1400663f0  cmp     [rbp+440h+var_4B8], r12b
0x1400663f4  jz      short loc_140066406
0x1400663f6  mov     ebx, [rbp+440h+var_4BC]
0x1400663f9  lea     rcx, [rsp+540h+var_4F0]
0x1400663fe  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x140066403  mov     [rax+24h], ebx
0x140066406  mov     eax, edi
0x140066408  mov     rcx, [rbp+440h+var_40]
0x14006640f  xor     rcx, rsp; StackCookie
0x140066412  call    __security_check_cookie
0x140066417  add     rsp, 510h
0x14006641e  pop     r15
0x140066420  pop     r14
0x140066422  pop     r12
0x140066424  pop     rdi
0x140066425  pop     rsi
0x140066426  pop     rbx
0x140066427  pop     rbp
0x140066428  retn
```
