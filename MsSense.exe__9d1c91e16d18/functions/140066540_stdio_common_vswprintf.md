# __stdio_common_vswprintf

- ea: `0x140066540`
- end: `0x140066799`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001518c`
- `0x140015244`
- `0x14007f810`

## callees

- `0x140051ba0`
- `0x140061148`
- `0x14006147c`
- `0x140064458`
- `0x140066540`
- `0x140072280`

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
  v11 = sub_140064458(v31);
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
0x140066540  push    rbp
0x140066542  push    rbx
0x140066543  push    rsi
0x140066544  push    rdi
0x140066545  push    r12
0x140066547  push    r14
0x140066549  push    r15
0x14006654b  lea     rbp, [rsp-410h]
0x140066553  sub     rsp, 510h
0x14006655a  mov     rax, cs:__security_cookie
0x140066561  xor     rax, rsp
0x140066564  mov     [rbp+440h+var_40], rax
0x14006656b  mov     rax, [rbp+440h+Locale]
0x140066572  xor     r12d, r12d
0x140066575  mov     [rsp+540h+var_4F0], r12
0x14006657a  mov     rbx, r8
0x14006657d  mov     [rsp+540h+var_4E0], r12b
0x140066582  mov     rsi, rdx
0x140066585  mov     [rsp+540h+var_4C8], r12b
0x14006658a  mov     r15, rcx
0x14006658d  mov     [rbp+440h+var_4C0], r12b
0x140066591  mov     [rbp+440h+var_4B8], r12b
0x140066595  test    rax, rax
0x140066598  jz      short loc_14006659F
0x14006659a  movups  xmm0, xmmword ptr [rax]
0x14006659d  jmp     short loc_1400665AF
0x14006659f  cmp     cs:dword_1400C43C8, r12d
0x1400665a6  jnz     short loc_1400665BA
0x1400665a8  movups  xmm0, xmmword ptr cs:off_1400BE1B8
0x1400665af  mov     [rsp+540h+var_4C8], 1
0x1400665b4  movdqu  [rsp+540h+var_4D8], xmm0
0x1400665ba  test    r9, r9
0x1400665bd  jnz     short loc_1400665F1
0x1400665bf  lea     rax, [rsp+540h+var_4F0]
0x1400665c4  mov     [rbp+440h+var_4C0], 1
0x1400665c8  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x1400665cd  xor     r9d, r9d; LineNo
0x1400665d0  xor     r8d, r8d; FileName
0x1400665d3  mov     [rsp+540h+var_520], r12; uintptr_t
0x1400665d8  xor     edx, edx; FunctionName
0x1400665da  mov     [rsp+540h+var_4C4], 16h
0x1400665e2  xor     ecx, ecx; Expression
0x1400665e4  call    sub_14006147C
0x1400665e9  or      edi, 0FFFFFFFFh
0x1400665ec  jmp     loc_140066736
0x1400665f1  test    rbx, rbx
0x1400665f4  jz      short loc_1400665FB
0x1400665f6  test    rsi, rsi
0x1400665f9  jz      short loc_1400665BF
0x1400665fb  mov     r14, r15
0x1400665fe  mov     [rsp+540h+var_4F7], r12d
0x140066603  mov     [rsp+540h+var_4F3], r12w
0x140066609  mov     [rsp+540h+var_4F1], r12b
0x14006660e  mov     [rsp+540h+var_510], rsi
0x140066613  mov     [rsp+540h+var_508], rbx
0x140066618  mov     [rsp+540h+var_500], r12
0x14006661d  and     r14d, 2
0x140066621  jnz     short loc_14006662D
0x140066623  mov     [rsp+540h+var_4F8], r12b
0x140066628  test    rsi, rsi
0x14006662b  jnz     short loc_140066632
0x14006662d  mov     [rsp+540h+var_4F8], 1
0x140066632  lea     rax, [rsp+540h+var_4F0]
0x140066637  mov     [rbp+440h+var_490], r12d
0x14006663b  mov     [rbp+440h+var_4A8], rax
0x14006663f  lea     rcx, [rbp+440h+var_4B0]
0x140066643  lea     rax, [rsp+540h+var_510]
0x140066648  mov     [rbp+440h+var_48C], r12b
0x14006664c  mov     [rbp+440h+var_50], rax
0x140066653  xorps   xmm0, xmm0
0x140066656  mov     rax, [rbp+440h+ArgList]
0x14006665d  mov     [rbp+440h+var_498], rax
0x140066661  mov     [rbp+440h+var_488], r12
0x140066665  mov     [rbp+440h+var_480], r12d
0x140066669  mov     [rbp+440h+var_478], r12b
0x14006666d  mov     [rbp+440h+var_476], r12w
0x140066672  mov     [rbp+440h+var_468], r12d
0x140066676  mov     [rbp+440h+var_464], r12b
0x14006667a  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x140066682  mov     [rbp+440h+var_4B0], r15
0x140066686  mov     [rbp+440h+var_4A0], r9
0x14006668a  mov     [rbp+440h+var_48], r12d
0x140066691  call    sub_140064458
0x140066696  movsxd  rdi, eax
0x140066699  test    rsi, rsi
0x14006669c  jz      loc_14006672A
0x1400666a2  test    r15b, 1
0x1400666a6  jz      short loc_1400666D7
0x1400666a8  test    rbx, rbx
0x1400666ab  jnz     short loc_1400666C2
0x1400666ad  test    eax, eax
0x1400666af  jz      short loc_1400666C2
0x1400666b1  mov     rcx, [rbp+440h+Block+8]; Block
0x1400666b8  call    _free_base
0x1400666bd  jmp     loc_1400665E9
0x1400666c2  mov     rax, [rsp+540h+var_500]
0x1400666c7  cmp     rax, rbx
0x1400666ca  jnz     short loc_140066725
0x1400666cc  test    edi, edi
0x1400666ce  js      short loc_14006672A
0x1400666d0  cmp     rdi, rbx
0x1400666d3  jbe     short loc_14006672A
0x1400666d5  jmp     short loc_1400666B1
0x1400666d7  test    r14, r14
0x1400666da  jz      short loc_1400666FD
0x1400666dc  test    rbx, rbx
0x1400666df  jz      short loc_14006672A
0x1400666e1  test    eax, eax
0x1400666e3  jns     short loc_1400666EB
0x1400666e5  mov     [rsi], r12w
0x1400666e9  jmp     short loc_14006672A
0x1400666eb  mov     rax, [rsp+540h+var_500]
0x1400666f0  cmp     rax, rbx
0x1400666f3  jnz     short loc_140066725
0x1400666f5  mov     [rsi+rbx*2-2], r12w
0x1400666fb  jmp     short loc_14006672A
0x1400666fd  test    rbx, rbx
0x140066700  jz      short loc_1400666B1
0x140066702  mov     rax, [rsp+540h+var_500]
0x140066707  cmp     rax, rbx
0x14006670a  jnz     short loc_140066725
0x14006670c  mov     rcx, [rbp+440h+Block+8]; Block
0x140066713  mov     [rsi+rbx*2-2], r12w
0x140066719  call    _free_base
0x14006671e  mov     edi, 0FFFFFFFEh
0x140066723  jmp     short loc_140066736
0x140066725  mov     [rsi+rax*2], r12w
0x14006672a  mov     rcx, [rbp+440h+Block+8]; Block
0x140066731  call    _free_base
0x140066736  cmp     [rsp+540h+var_4C8], 2
0x14006673b  jnz     short loc_140066749
0x14006673d  mov     rax, [rsp+540h+var_4F0]
0x140066742  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x140066749  cmp     [rbp+440h+var_4C0], r12b
0x14006674d  jz      short loc_140066760
0x14006674f  mov     ebx, [rsp+540h+var_4C4]
0x140066753  lea     rcx, [rsp+540h+var_4F0]
0x140066758  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x14006675d  mov     [rax+20h], ebx
0x140066760  cmp     [rbp+440h+var_4B8], r12b
0x140066764  jz      short loc_140066776
0x140066766  mov     ebx, [rbp+440h+var_4BC]
0x140066769  lea     rcx, [rsp+540h+var_4F0]
0x14006676e  call    unknown_libname_67; Microsoft VisualC 64bit universal runtime
0x140066773  mov     [rax+24h], ebx
0x140066776  mov     eax, edi
0x140066778  mov     rcx, [rbp+440h+var_40]
0x14006677f  xor     rcx, rsp; StackCookie
0x140066782  call    __security_check_cookie
0x140066787  add     rsp, 510h
0x14006678e  pop     r15
0x140066790  pop     r14
0x140066792  pop     r12
0x140066794  pop     rdi
0x140066795  pop     rsi
0x140066796  pop     rbx
0x140066797  pop     rbp
0x140066798  retn
```
