# __stdio_common_vsprintf

- ea: `0x1400144b8`
- end: `0x140014709`
- name: `__stdio_common_vsprintf`
- size: `593`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002a34`

## callees

- `0x14000a640`
- `0x140011f80`
- `0x140012108`
- `0x1400144b8`
- `0x140015fe4`
- `0x140019930`

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
  v11 = sub_140012108(v31);
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
0x1400144b8  push    rbp
0x1400144ba  push    rbx
0x1400144bb  push    rsi
0x1400144bc  push    rdi
0x1400144bd  push    r12
0x1400144bf  push    r14
0x1400144c1  push    r15
0x1400144c3  lea     rbp, [rsp-410h]
0x1400144cb  sub     rsp, 510h
0x1400144d2  mov     rax, cs:__security_cookie
0x1400144d9  xor     rax, rsp
0x1400144dc  mov     [rbp+440h+var_40], rax
0x1400144e3  mov     rax, [rbp+440h+Locale]
0x1400144ea  xor     r12d, r12d
0x1400144ed  mov     [rsp+540h+var_4F0], r12
0x1400144f2  mov     rbx, r8
0x1400144f5  mov     [rsp+540h+var_4E0], r12b
0x1400144fa  mov     rsi, rdx
0x1400144fd  mov     [rsp+540h+var_4C8], r12b
0x140014502  mov     r15, rcx
0x140014505  mov     [rbp+440h+var_4C0], r12b
0x140014509  mov     [rbp+440h+var_4B8], r12b
0x14001450d  test    rax, rax
0x140014510  jz      short loc_140014517
0x140014512  movups  xmm0, xmmword ptr [rax]
0x140014515  jmp     short loc_140014527
0x140014517  cmp     cs:dword_14003E558, r12d
0x14001451e  jnz     short loc_140014532
0x140014520  movups  xmm0, xmmword ptr cs:off_14003C8F8
0x140014527  mov     [rsp+540h+var_4C8], 1
0x14001452c  movdqu  [rsp+540h+var_4D8], xmm0
0x140014532  test    r9, r9
0x140014535  jnz     short loc_140014569
0x140014537  lea     rax, [rsp+540h+var_4F0]
0x14001453c  mov     [rbp+440h+var_4C0], 1
0x140014540  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x140014545  xor     r9d, r9d; LineNo
0x140014548  xor     r8d, r8d; FileName
0x14001454b  mov     [rsp+540h+var_520], r12; uintptr_t
0x140014550  xor     edx, edx; FunctionName
0x140014552  mov     [rsp+540h+var_4C4], 16h
0x14001455a  xor     ecx, ecx; Expression
0x14001455c  call    sub_140015FE4
0x140014561  or      edi, 0FFFFFFFFh
0x140014564  jmp     loc_1400146A6
0x140014569  test    rbx, rbx
0x14001456c  jz      short loc_140014573
0x14001456e  test    rsi, rsi
0x140014571  jz      short loc_140014537
0x140014573  mov     r14, r15
0x140014576  mov     [rsp+540h+var_4F7], r12d
0x14001457b  mov     [rsp+540h+var_4F3], r12w
0x140014581  mov     [rsp+540h+var_4F1], r12b
0x140014586  mov     [rsp+540h+var_510], rsi
0x14001458b  mov     [rsp+540h+var_508], rbx
0x140014590  mov     [rsp+540h+var_500], r12
0x140014595  and     r14d, 2
0x140014599  jnz     short loc_1400145A5
0x14001459b  mov     [rsp+540h+var_4F8], r12b
0x1400145a0  test    rsi, rsi
0x1400145a3  jnz     short loc_1400145AA
0x1400145a5  mov     [rsp+540h+var_4F8], 1
0x1400145aa  lea     rax, [rsp+540h+var_4F0]
0x1400145af  mov     [rbp+440h+var_490], r12d
0x1400145b3  mov     [rbp+440h+var_4A8], rax
0x1400145b7  lea     rcx, [rbp+440h+var_4B0]
0x1400145bb  lea     rax, [rsp+540h+var_510]
0x1400145c0  mov     [rbp+440h+var_48C], r12b
0x1400145c4  mov     [rbp+440h+var_50], rax
0x1400145cb  xorps   xmm0, xmm0
0x1400145ce  mov     rax, [rbp+440h+ArgList]
0x1400145d5  mov     [rbp+440h+var_498], rax
0x1400145d9  mov     [rbp+440h+var_488], r12
0x1400145dd  mov     [rbp+440h+var_480], r12d
0x1400145e1  mov     [rbp+440h+var_478], r12w
0x1400145e6  mov     [rbp+440h+var_468], r12d
0x1400145ea  mov     [rbp+440h+var_464], r12b
0x1400145ee  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x1400145f6  mov     [rbp+440h+var_4B0], r15
0x1400145fa  mov     [rbp+440h+var_4A0], r9
0x1400145fe  mov     [rbp+440h+var_48], r12d
0x140014605  call    sub_140012108
0x14001460a  movsxd  rdi, eax
0x14001460d  test    rsi, rsi
0x140014610  jz      loc_14001469A
0x140014616  test    r15b, 1
0x14001461a  jz      short loc_14001464B
0x14001461c  test    rbx, rbx
0x14001461f  jnz     short loc_140014636
0x140014621  test    eax, eax
0x140014623  jz      short loc_140014636
0x140014625  mov     rcx, [rbp+440h+Block+8]; Block
0x14001462c  call    _free_base
0x140014631  jmp     loc_140014561
0x140014636  mov     rax, [rsp+540h+var_500]
0x14001463b  cmp     rax, rbx
0x14001463e  jnz     short loc_140014696
0x140014640  test    edi, edi
0x140014642  js      short loc_14001469A
0x140014644  cmp     rdi, rbx
0x140014647  jbe     short loc_14001469A
0x140014649  jmp     short loc_140014625
0x14001464b  test    r14, r14
0x14001464e  jz      short loc_14001466F
0x140014650  test    rbx, rbx
0x140014653  jz      short loc_14001469A
0x140014655  test    eax, eax
0x140014657  jns     short loc_14001465E
0x140014659  mov     [rsi], r12b
0x14001465c  jmp     short loc_14001469A
0x14001465e  mov     rax, [rsp+540h+var_500]
0x140014663  cmp     rax, rbx
0x140014666  jnz     short loc_140014696
0x140014668  mov     [rbx+rsi-1], r12b
0x14001466d  jmp     short loc_14001469A
0x14001466f  test    rbx, rbx
0x140014672  jz      short loc_140014625
0x140014674  mov     rax, [rsp+540h+var_500]
0x140014679  cmp     rax, rbx
0x14001467c  jnz     short loc_140014696
0x14001467e  mov     rcx, [rbp+440h+Block+8]; Block
0x140014685  mov     [rbx+rsi-1], r12b
0x14001468a  call    _free_base
0x14001468f  mov     edi, 0FFFFFFFEh
0x140014694  jmp     short loc_1400146A6
0x140014696  mov     [rax+rsi], r12b
0x14001469a  mov     rcx, [rbp+440h+Block+8]; Block
0x1400146a1  call    _free_base
0x1400146a6  cmp     [rsp+540h+var_4C8], 2
0x1400146ab  jnz     short loc_1400146B9
0x1400146ad  mov     rax, [rsp+540h+var_4F0]
0x1400146b2  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1400146b9  cmp     [rbp+440h+var_4C0], r12b
0x1400146bd  jz      short loc_1400146D0
0x1400146bf  mov     ebx, [rsp+540h+var_4C4]
0x1400146c3  lea     rcx, [rsp+540h+var_4F0]
0x1400146c8  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x1400146cd  mov     [rax+20h], ebx
0x1400146d0  cmp     [rbp+440h+var_4B8], r12b
0x1400146d4  jz      short loc_1400146E6
0x1400146d6  mov     ebx, [rbp+440h+var_4BC]
0x1400146d9  lea     rcx, [rsp+540h+var_4F0]
0x1400146de  call    unknown_libname_33; Microsoft VisualC 64bit universal runtime
0x1400146e3  mov     [rax+24h], ebx
0x1400146e6  mov     eax, edi
0x1400146e8  mov     rcx, [rbp+440h+var_40]
0x1400146ef  xor     rcx, rsp; StackCookie
0x1400146f2  call    __security_check_cookie
0x1400146f7  add     rsp, 510h
0x1400146fe  pop     r15
0x140014700  pop     r14
0x140014702  pop     r12
0x140014704  pop     rdi
0x140014705  pop     rsi
0x140014706  pop     rbx
0x140014707  pop     rbp
0x140014708  retn
```
