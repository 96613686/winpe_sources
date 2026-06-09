# CONFIG_SECTION_WRITER::ParseCollectionElementSpecifier(ushort *,STRU *,COLLECTION_CONDITIONS *)

- ea: `0x180029f08`
- end: `0x18002a0b1`
- name: `?ParseCollectionElementSpecifier@CONFIG_SECTION_WRITER@@AEAAJPEAGPEAVSTRU@@PEAVCOLLECTION_CONDITIONS@@@Z`
- size: `425`
- prototype: `int(CONFIG_SECTION_WRITER *__hidden this, unsigned __int16 *, struct STRU *, struct COLLECTION_CONDITIONS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180029bf8`

## callees

- `0x180001fb0`
- `0x180002e60`
- `0x180002ed0`
- `0x180029a6c`
- `0x180029f08`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `msvcrt!wcsstr` at `0x180029fec`
- `msvcrt!wcsstr` at `0x180029fec`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_WRITER::ParseCollectionElementSpecifier(
        CONFIG_SECTION_WRITER *this,
        unsigned __int16 *a2,
        struct STRU *a3,
        struct COLLECTION_CONDITIONS *a4)
{
  unsigned __int16 *v7; // r14
  __int64 v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rsi
  int v11; // r8d
  int v12; // ebx
  signed int v13; // edi
  _BYTE v15[32]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-C0h]
  int v17; // [rsp+48h] [rbp-B8h]
  __int16 v18; // [rsp+4Ch] [rbp-B4h]
  int v19; // [rsp+50h] [rbp-B0h]
  const unsigned __int8 *v20[5]; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+80h] [rbp-80h]
  __int16 v22; // [rsp+84h] [rbp-7Ch]
  int v23; // [rsp+88h] [rbp-78h]
  _BYTE v24[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[126]; // [rsp+D2h] [rbp-2Eh] BYREF

  memset_0(v24, 0, sizeof(v24));
  v21 = 64;
  v20[4] = v24;
  v22 = 256;
  v23 = 0;
  memset_0(v26, 0, sizeof(v26));
  v17 = 128;
  v7 = &v25;
  v16 = &v25;
  v18 = 256;
  v19 = 0;
  v25 = 0;
  if ( !a2 )
    goto LABEL_19;
  if ( !a3 )
    goto LABEL_19;
  if ( !a4 )
    goto LABEL_19;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( (unsigned int)v8 <= 2 || *a2 != 123 || a2[(unsigned int)(v8 - 1)] != 125 )
  {
LABEL_19:
    v13 = -2147024809;
    goto LABEL_20;
  }
  v9 = wcsstr(a2, L":");
  v10 = v9;
  if ( v9 )
  {
    v11 = v9 - a2 - 1;
    v12 = v8 - v11 - 3;
  }
  else
  {
    v11 = v8 - 2;
    v12 = 0;
  }
  v13 = STRU::Copy((STRU *)v20, (const unsigned __int8 *)a2 + 2, v11);
  if ( v13 >= 0 )
  {
    if ( v12 )
    {
      v13 = STRU::Copy((STRU *)v15, (const unsigned __int8 *)v10 + 2, v12);
      if ( v13 < 0 )
        goto LABEL_20;
      v7 = v16;
    }
    v13 = STRU::Copy(a3, v20);
    if ( v13 >= 0 && v12 )
      v13 = COLLECTION_CONDITIONS::Initialize(a4, v7);
  }
LABEL_20:
  BUFFER::~BUFFER((BUFFER *)v15);
  BUFFER::~BUFFER((BUFFER *)v20);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180029f08  mov     [rsp-8+arg_0], rbx
0x180029f0d  push    rbp
0x180029f0e  push    rsi
0x180029f0f  push    rdi
0x180029f10  push    r12
0x180029f12  push    r13
0x180029f14  push    r14
0x180029f16  push    r15
0x180029f18  lea     rbp, [rsp-60h]
0x180029f1d  sub     rsp, 160h
0x180029f24  mov     rax, cs:__security_cookie
0x180029f2b  xor     rax, rsp
0x180029f2e  mov     [rbp+90h+var_40], rax
0x180029f32  mov     r12, r8
0x180029f35  lea     rcx, [rbp+90h+var_100]; void *
0x180029f39  mov     rdi, rdx
0x180029f3c  mov     ebx, 40h ; '@'
0x180029f41  mov     r8d, ebx; Size
0x180029f44  xor     edx, edx; Val
0x180029f46  mov     r15, r9
0x180029f49  call    memset_0
0x180029f4e  lea     rax, [rbp+90h+var_100]
0x180029f52  mov     [rbp+90h+var_110], ebx
0x180029f55  xor     r13d, r13d
0x180029f58  mov     [rsp+190h+var_118], rax
0x180029f5d  xor     edx, edx; Val
0x180029f5f  mov     [rbp+90h+var_10C], 100h
0x180029f65  lea     r8d, [rbx+3Eh]; Size
0x180029f69  mov     [rbp+90h+var_108], r13d
0x180029f6d  lea     rcx, [rbp+90h+var_BE]; void *
0x180029f71  call    memset_0
0x180029f76  mov     [rsp+190h+var_148], 80h
0x180029f7e  lea     r14, [rbp+90h+var_C0]
0x180029f82  mov     [rsp+190h+var_150], r14
0x180029f87  mov     [rsp+190h+var_144], 100h
0x180029f8e  mov     [rsp+190h+var_140], r13d
0x180029f93  mov     [rbp+90h+var_C0], r13w
0x180029f98  test    rdi, rdi
0x180029f9b  jz      loc_18002A06F
0x180029fa1  test    r12, r12
0x180029fa4  jz      loc_18002A06F
0x180029faa  test    r15, r15
0x180029fad  jz      loc_18002A06F
0x180029fb3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029fb7  inc     rbx
0x180029fba  cmp     [rdi+rbx*2], r13w
0x180029fbf  jnz     short loc_180029FB7
0x180029fc1  cmp     ebx, 2
0x180029fc4  jbe     loc_18002A06F
0x180029fca  cmp     word ptr [rdi], 7Bh ; '{'
0x180029fce  jnz     loc_18002A06F
0x180029fd4  lea     eax, [rbx-1]
0x180029fd7  cmp     word ptr [rdi+rax*2], 7Dh ; '}'
0x180029fdc  jnz     loc_18002A06F
0x180029fe2  lea     rdx, asc_18003A620; ":"
0x180029fe9  mov     rcx, rdi; Str
0x180029fec  call    cs:__imp_wcsstr
0x180029ff2  mov     rsi, rax
0x180029ff5  test    rax, rax
0x180029ff8  jnz     short loc_18002A003
0x180029ffa  lea     r8d, [rbx-2]
0x180029ffe  mov     ebx, r13d
0x18002a001  jmp     short loc_18002A015
0x18002a003  mov     r8, rsi
0x18002a006  sub     r8, rdi
0x18002a009  sar     r8, 1
0x18002a00c  dec     r8d; unsigned int
0x18002a00f  sub     ebx, r8d
0x18002a012  sub     ebx, 3
0x18002a015  lea     rdx, [rdi+2]; unsigned __int16 *
0x18002a019  lea     rcx, [rsp+190h+var_138]; this
0x18002a01e  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002a023  mov     edi, eax
0x18002a025  test    eax, eax
0x18002a027  js      short loc_18002A074
0x18002a029  test    ebx, ebx
0x18002a02b  jz      short loc_18002A049
0x18002a02d  lea     rdx, [rsi+2]; unsigned __int16 *
0x18002a031  mov     r8d, ebx; unsigned int
0x18002a034  lea     rcx, [rsp+190h+var_170]; this
0x18002a039  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002a03e  mov     edi, eax
0x18002a040  test    eax, eax
0x18002a042  js      short loc_18002A074
0x18002a044  mov     r14, [rsp+190h+var_150]
0x18002a049  lea     rdx, [rsp+190h+var_138]; struct STRU *
0x18002a04e  mov     rcx, r12; this
0x18002a051  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002a056  mov     edi, eax
0x18002a058  test    eax, eax
0x18002a05a  js      short loc_18002A074
0x18002a05c  test    ebx, ebx
0x18002a05e  jz      short loc_18002A074
0x18002a060  mov     rdx, r14; unsigned __int16 *
0x18002a063  mov     rcx, r15; this
0x18002a066  call    ?Initialize@COLLECTION_CONDITIONS@@QEAAJPEAG@Z; COLLECTION_CONDITIONS::Initialize(ushort *)
0x18002a06b  mov     edi, eax
0x18002a06d  jmp     short loc_18002A074
0x18002a06f  mov     edi, 80070057h
0x18002a074  lea     rcx, [rsp+190h+var_170]; this
0x18002a079  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a07e  lea     rcx, [rsp+190h+var_138]; this
0x18002a083  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a088  mov     eax, edi
0x18002a08a  mov     rcx, [rbp+90h+var_40]
0x18002a08e  xor     rcx, rsp; StackCookie
0x18002a091  call    __security_check_cookie
0x18002a096  mov     rbx, [rsp+190h+arg_0]
0x18002a09e  add     rsp, 160h
0x18002a0a5  pop     r15
0x18002a0a7  pop     r14
0x18002a0a9  pop     r13
0x18002a0ab  pop     r12
0x18002a0ad  pop     rdi
0x18002a0ae  pop     rsi
0x18002a0af  pop     rbp
0x18002a0b0  retn
```
