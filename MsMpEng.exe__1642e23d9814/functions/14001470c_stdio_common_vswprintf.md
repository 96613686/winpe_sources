# __stdio_common_vswprintf

- ea: `0x14001470c`
- end: `0x140014965`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140008224`
- `0x1400082d8`

## callees

- `0x14000a640`
- `0x140011f80`
- `0x140012734`
- `0x14001470c`
- `0x140015fe4`
- `0x140019930`

## pseudocode

```c
int __cdecl _stdio_common_vswprintf(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
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
  char v36; // [rsp+C8h] [rbp-38h]
  __int16 v37; // [rsp+CAh] [rbp-36h]
  int v38; // [rsp+D8h] [rbp-28h]
  char v39; // [rsp+DCh] [rbp-24h]
  void *Block[2]; // [rsp+4E0h] [rbp+3E0h]
  _QWORD *v41; // [rsp+4F0h] [rbp+3F0h]
  int v42; // [rsp+4F8h] [rbp+3F8h]

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
  if ( !dword_14003E558 )
  {
    v9 = *(struct localeinfo_struct *)&off_14003C8F8;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || BufferCount && !Buffer )
  {
    v28 = 1;
    v27 = 22;
    sub_140015FE4(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v23);
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
  v41 = v17;
  v31[3] = ArgList;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  *(_OWORD *)Block = 0;
  v31[0] = Options;
  v31[2] = Format;
  v42 = 0;
  v11 = sub_140012734(v31);
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
    *(_DWORD *)(unknown_libname_33(v23) + 32) = v14;
  }
  if ( v30 )
  {
    v15 = v29;
    *(_DWORD *)(unknown_libname_33(v23) + 36) = v15;
  }
  return v10;
}

```

## disassembly

```asm
0x14001470c  push    rbp
0x14001470e  push    rbx
0x14001470f  push    rsi
0x140014710  push    rdi
0x140014711  push    r12
0x140014713  push    r14
0x140014715  push    r15
0x140014717  lea     rbp, [rsp-410h]
0x14001471f  sub     rsp, 510h
0x140014726  mov     rax, cs:__security_cookie
0x14001472d  xor     rax, rsp
0x140014730  mov     [rbp+440h+var_40], rax
0x140014737  mov     rax, [rbp+440h+Locale]
0x14001473e  xor     r12d, r12d
0x140014741  mov     [rsp+540h+var_4F0], r12
0x140014746  mov     rbx, r8
0x140014749  mov     [rsp+540h+var_4E0], r12b
0x14001474e  mov     rsi, rdx
0x140014751  mov     [rsp+540h+var_4C8], r12b
0x140014756  mov     r15, rcx
0x140014759  mov     [rbp+440h+var_4C0], r12b
0x14001475d  mov     [rbp+440h+var_4B8], r12b
0x140014761  test    rax, rax
0x140014764  jz      short loc_14001476B
0x140014766  movups  xmm0, xmmword ptr [rax]
0x140014769  jmp     short loc_14001477B
0x14001476b  cmp     cs:dword_14003E558, r12d
0x140014772  jnz     short loc_140014786
0x140014774  movups  xmm0, xmmword ptr cs:off_14003C8F8
0x14001477b  mov     [rsp+540h+var_4C8], 1
0x140014780  movdqu  [rsp+540h+var_4D8], xmm0
0x140014786  test    r9, r9
0x140014789  jnz     short loc_1400147BD
0x14001478b  lea     rax, [rsp+540h+var_4F0]
0x140014790  mov     [rbp+440h+var_4C0], 1
0x140014794  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x140014799  xor     r9d, r9d; LineNo
0x14001479c  xor     r8d, r8d; FileName
0x14001479f  mov     [rsp+540h+var_520], r12; uintptr_t
0x1400147a4  xor     edx, edx; FunctionName
0x1400147a6  mov     [rsp+540h+var_4C4], 16h
0x1400147ae  xor     ecx, ecx; Expression
0x1400147b0  call    sub_140015FE4
0x1400147b5  or      edi, 0FFFFFFFFh
0x1400147b8  jmp     loc_140014902
0x1400147bd  test    rbx, rbx
0x1400147c0  jz      short loc_1400147C7
0x1400147c2  test    rsi, rsi
0x1400147c5  jz      short loc_14001478B
0x1400147c7  mov     r14, r15
0x1400147ca  mov     [rsp+540h+var_4F7], r12d
0x1400147cf  mov     [rsp+540h+var_4F3], r12w
0x1400147d5  mov     [rsp+540h+var_4F1], r12b
0x1400147da  mov     [rsp+540h+var_510], rsi
0x1400147df  mov     [rsp+540h+var_508], rbx
0x1400147e4  mov     [rsp+540h+var_500], r12
0x1400147e9  and     r14d, 2
0x1400147ed  jnz     short loc_1400147F9
0x1400147ef  mov     [rsp+540h+var_4F8], r12b
0x1400147f4  test    rsi, rsi
0x1400147f7  jnz     short loc_1400147FE
0x1400147f9  mov     [rsp+540h+var_4F8], 1
0x1400147fe  lea     rax, [rsp+540h+var_4F0]
0x140014803  mov     [rbp+440h+var_490], r12d
0x140014807  mov     [rbp+440h+var_4A8], rax
0x14001480b  lea     rcx, [rbp+440h+var_4B0]
0x14001480f  lea     rax, [rsp+540h+var_510]
0x140014814  mov     [rbp+440h+var_48C], r12b
0x140014818  mov     [rbp+440h+var_50], rax
0x14001481f  xorps   xmm0, xmm0
0x140014822  mov     rax, [rbp+440h+ArgList]
0x140014829  mov     [rbp+440h+var_498], rax
0x14001482d  mov     [rbp+440h+var_488], r12
0x140014831  mov     [rbp+440h+var_480], r12d
0x140014835  mov     [rbp+440h+var_478], r12b
0x140014839  mov     [rbp+440h+var_476], r12w
0x14001483e  mov     [rbp+440h+var_468], r12d
0x140014842  mov     [rbp+440h+var_464], r12b
0x140014846  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x14001484e  mov     [rbp+440h+var_4B0], r15
0x140014852  mov     [rbp+440h+var_4A0], r9
0x140014856  mov     [rbp+440h+var_48], r12d
0x14001485d  call    sub_140012734
0x140014862  movsxd  rdi, eax
0x140014865  test    rsi, rsi
0x140014868  jz      loc_1400148F6
0x14001486e  test    r15b, 1
0x140014872  jz      short loc_1400148A3
0x140014874  test    rbx, rbx
0x140014877  jnz     short loc_14001488E
0x140014879  test    eax, eax
0x14001487b  jz      short loc_14001488E
0x14001487d  mov     rcx, [rbp+440h+Block+8]; Block
0x140014884  call    _free_base
0x140014889  jmp     loc_1400147B5
0x14001488e  mov     rax, [rsp+540h+var_500]
0x140014893  cmp     rax, rbx
0x140014896  jnz     short loc_1400148F1
0x140014898  test    edi, edi
0x14001489a  js      short loc_1400148F6
0x14001489c  cmp     rdi, rbx
0x14001489f  jbe     short loc_1400148F6
0x1400148a1  jmp     short loc_14001487D
0x1400148a3  test    r14, r14
0x1400148a6  jz      short loc_1400148C9
0x1400148a8  test    rbx, rbx
0x1400148ab  jz      short loc_1400148F6
0x1400148ad  test    eax, eax
0x1400148af  jns     short loc_1400148B7
0x1400148b1  mov     [rsi], r12w
0x1400148b5  jmp     short loc_1400148F6
0x1400148b7  mov     rax, [rsp+540h+var_500]
0x1400148bc  cmp     rax, rbx
0x1400148bf  jnz     short loc_1400148F1
0x1400148c1  mov     [rsi+rbx*2-2], r12w
0x1400148c7  jmp     short loc_1400148F6
0x1400148c9  test    rbx, rbx
0x1400148cc  jz      short loc_14001487D
0x1400148ce  mov     rax, [rsp+540h+var_500]
0x1400148d3  cmp     rax, rbx
0x1400148d6  jnz     short loc_1400148F1
0x1400148d8  mov     rcx, [rbp+440h+Block+8]; Block
0x1400148df  mov     [rsi+rbx*2-2], r12w
0x1400148e5  call    _free_base
0x1400148ea  mov     edi, 0FFFFFFFEh
0x1400148ef  jmp     short loc_140014902
0x1400148f1  mov     [rsi+rax*2], r12w
0x1400148f6  mov     rcx, [rbp+440h+Block+8]; Block
0x1400148fd  call    _free_base
0x140014902  cmp     [rsp+540h+var_4C8], 2
0x140014907  jnz     short loc_140014915
0x140014909  mov     rax, [rsp+540h+var_4F0]
0x14001490e  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x140014915  cmp     [rbp+440h+var_4C0], r12b
0x140014919  jz      short loc_14001492C
0x14001491b  mov     ebx, [rsp+540h+var_4C4]
0x14001491f  lea     rcx, [rsp+540h+var_4F0]
0x140014924  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x140014929  mov     [rax+20h], ebx
0x14001492c  cmp     [rbp+440h+var_4B8], r12b
0x140014930  jz      short loc_140014942
0x140014932  mov     ebx, [rbp+440h+var_4BC]
0x140014935  lea     rcx, [rsp+540h+var_4F0]
0x14001493a  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x14001493f  mov     [rax+24h], ebx
0x140014942  mov     eax, edi
0x140014944  mov     rcx, [rbp+440h+var_40]
0x14001494b  xor     rcx, rsp; StackCookie
0x14001494e  call    __security_check_cookie
0x140014953  add     rsp, 510h
0x14001495a  pop     r15
0x14001495c  pop     r14
0x14001495e  pop     r12
0x140014960  pop     rdi
0x140014961  pop     rsi
0x140014962  pop     rbx
0x140014963  pop     rbp
0x140014964  retn
```
