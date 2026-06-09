# COMMAND_PROCESSOR::GetIndexer(ushort const *,PARAMETER_LIST *,ushort const * *,COLLECTION_INDEX_TYPE *,ulong *)

- ea: `0x180008990`
- end: `0x180008e5f`
- name: `?GetIndexer@COMMAND_PROCESSOR@@AEAAJPEBGPEAVPARAMETER_LIST@@PEAPEBGPEAW4COLLECTION_INDEX_TYPE@@PEAK@Z`
- size: `1231`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, struct PARAMETER_LIST *, const unsigned __int16 **, enum COLLECTION_INDEX_TYPE *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009aac`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002680`
- `0x180002e60`
- `0x180002ed0`
- `0x1800049b0`
- `0x180008990`
- `0x180013288`
- `0x180033c5c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180008bd5`
- `msvcrt!wcstoul` at `0x180008bd5`
- `msvcrt!wcschr` at `0x180008b31`
- `msvcrt!wcschr` at `0x180008b45`
- `msvcrt!wcschr` at `0x180008b59`
- `msvcrt!wcschr` at `0x180008c40`
- `msvcrt!wcschr` at `0x180008d18`
- `msvcrt!wcschr` at `0x180008b31`
- `msvcrt!wcschr` at `0x180008b45`
- `msvcrt!wcschr` at `0x180008b59`
- `msvcrt!wcschr` at `0x180008c40`
- `msvcrt!wcschr` at `0x180008d18`
- `msvcrt!_wcsicmp` at `0x180008b98`
- `msvcrt!_wcsicmp` at `0x180008bb5`
- `msvcrt!_wcsicmp` at `0x180008bf0`
- `msvcrt!_wcsicmp` at `0x180008b98`
- `msvcrt!_wcsicmp` at `0x180008bb5`
- `msvcrt!_wcsicmp` at `0x180008bf0`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::GetIndexer(
        COMMAND_PROCESSOR *this,
        const unsigned __int16 *a2,
        struct PARAMETER_LIST *a3,
        const unsigned __int16 **a4,
        enum COLLECTION_INDEX_TYPE *a5,
        unsigned int *a6)
{
  int v9; // ebx
  _WORD *v10; // r15
  int v11; // r14d
  unsigned int v12; // r13d
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  struct PARAMETER_LIST *v15; // r12
  const wchar_t *v16; // rbx
  wchar_t *v17; // rdi
  wchar_t *v18; // rsi
  wchar_t *v19; // rax
  wchar_t *v20; // rsi
  wchar_t *i; // rax
  wchar_t v22; // si
  const unsigned __int8 *v23; // rdx
  int v24; // edi
  _WORD *j; // rax
  wchar_t *v26; // rdi
  wchar_t *v27; // rbx
  wchar_t *v28; // rax
  __int64 v29; // rdx
  wchar_t *v32; // [rsp+38h] [rbp-C8h] BYREF
  COMMAND_PROCESSOR *v33; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 **v34; // [rsp+48h] [rbp-B8h]
  enum COLLECTION_INDEX_TYPE *v35; // [rsp+50h] [rbp-B0h]
  unsigned int *v36; // [rsp+58h] [rbp-A8h]
  _BYTE v37[32]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+88h] [rbp-78h]
  __int16 v40; // [rsp+8Ch] [rbp-74h]
  int v41; // [rsp+90h] [rbp-70h]
  _BYTE v42[32]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String1; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+C4h] [rbp-3Ch]
  int v46; // [rsp+C8h] [rbp-38h]
  const unsigned __int8 *v47[5]; // [rsp+D0h] [rbp-30h] BYREF
  int v48; // [rsp+F8h] [rbp-8h]
  __int16 v49; // [rsp+FCh] [rbp-4h]
  int v50; // [rsp+100h] [rbp+0h]
  __int16 v51; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v52[510]; // [rsp+112h] [rbp+12h] BYREF
  __int16 v53; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v54[510]; // [rsp+312h] [rbp+212h] BYREF
  __int16 v55; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v56[510]; // [rsp+512h] [rbp+412h] BYREF

  v33 = this;
  v34 = a4;
  v35 = a5;
  v36 = a6;
  memset_0(v52, 0, sizeof(v52));
  v45 = 256;
  String1 = (wchar_t *)&v51;
  v44 = 512;
  v46 = 0;
  v51 = 0;
  memset_0(v54, 0, sizeof(v54));
  v39 = 512;
  v41 = 0;
  v53 = 0;
  v32 = 0;
  Str = (wchar_t *)&v53;
  v40 = 256;
  memset_0(v56, 0, sizeof(v56));
  v48 = 512;
  v49 = 256;
  v47[4] = (const unsigned __int8 *)&v55;
  v50 = 0;
  v55 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v9 = -2147024809;
    goto LABEL_64;
  }
  v9 = (*(__int64 (__fastcall **)(struct PARAMETER_LIST *))(*(_QWORD *)a3 + 64LL))(a3);
  if ( v9 >= 0 )
  {
    if ( *a2 != 91 )
    {
LABEL_8:
      v9 = -2147024883;
      goto LABEL_64;
    }
    v10 = 0;
    v11 = 0;
    v12 = -1;
    v13 = 0x100002200LL;
    do
      v14 = *++a2;
    while ( (unsigned __int16)v14 <= 0x20u && _bittest64(&v13, v14) );
    v15 = a3;
    while ( (_WORD)v14 == 64 )
    {
      if ( v11 )
        goto LABEL_8;
      v16 = a2 + 1;
      v17 = wcschr(a2 + 1, 0x2Cu);
      if ( !v17 )
      {
        v17 = wcschr(v16, 0x5Du);
        if ( !v17 )
        {
          v17 = wcschr(v16, 0x20u);
          if ( !v17 )
            goto LABEL_8;
        }
      }
      v9 = STRU::Copy((STRU *)v42, (const unsigned __int8 *)v16, v17 - v16);
      if ( v9 < 0 )
        goto LABEL_64;
      v18 = String1;
      if ( _wcsicmp(String1, L"start") )
      {
        if ( _wcsicmp(v18, L"end") )
        {
          v11 = 1;
          v12 = wcstoul(v18, 0, 10);
          if ( !v12 && _wcsicmp(v18, L"0") )
          {
            v9 = -2147024809;
            v32 = v18;
            (*(void (__fastcall **)(__int64, __int64, __int64, wchar_t **, _DWORD))(*((_QWORD *)v33 + 1) + 144LL))(
              (__int64)v33 + 8,
              2147942487LL,
              3221226536LL,
              &v32,
              0);
            goto LABEL_64;
          }
        }
        else
        {
          v11 = 3;
        }
      }
      else
      {
        v11 = 2;
      }
LABEL_55:
      v29 = 0x100002200LL;
      while ( *v17 <= 0x20u && _bittest64(&v29, *v17) )
        ++v17;
      v15 = a3;
      if ( *v17 == 93 )
      {
        *v34 = v17;
        *(_DWORD *)v35 = v11;
        *v36 = v12;
        goto LABEL_64;
      }
      if ( *v17 != 44 )
        goto LABEL_8;
      a2 = v17 + 1;
      LOWORD(v14) = *a2;
    }
    v19 = wcschr(a2, 0x3Du);
    v20 = v19;
    if ( !v19 )
      goto LABEL_8;
    v9 = STRU::Copy((STRU *)v42, (const unsigned __int8 *)a2, v19 - a2);
    if ( v9 >= 0 )
    {
      v9 = StripWhiteSpace((struct STRU *)v42);
      if ( v9 >= 0 )
      {
        for ( i = v20 + 1; ; ++i )
        {
          v22 = *i;
          if ( !*i )
            break;
          if ( v22 == 39 || v22 == 34 )
          {
            v23 = (const unsigned __int8 *)(i + 1);
            v24 = 0;
            for ( j = i + 1; *j; ++j )
            {
              if ( *j == v22 )
              {
                if ( j[1] != v22 )
                {
                  v10 = j;
                  break;
                }
                v24 = 1;
                ++j;
              }
            }
            if ( !v10 )
              goto LABEL_8;
            v9 = STRU::Copy((STRU *)v37, v23, ((char *)v10 - (char *)v23) >> 1);
            if ( v9 >= 0 )
            {
              if ( !v24 )
                goto LABEL_67;
              v26 = Str;
              v27 = Str;
              STRU::SetLen((STRU *)v47, 0);
              while ( 1 )
              {
                v28 = wcschr(v26, v22);
                if ( !v28 )
                  break;
                v26 = v28 + 1;
                v9 = STRU::Append((STRU *)v47, v27, v28 + 1 - v27);
                if ( v9 < 0 )
                  goto LABEL_64;
                if ( *v26 == v22 )
                  ++v26;
                v27 = v26;
              }
              v9 = STRU::Append((STRU *)v47, (const unsigned __int8 *)v27);
              if ( v9 >= 0 )
              {
                v9 = STRU::Copy((STRU *)v37, v47);
                if ( v9 >= 0 )
                {
LABEL_67:
                  v9 = STRU::UnescapeOnly((STRU *)v37);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct PARAMETER_LIST *, wchar_t *, wchar_t *))(*(_QWORD *)v15 + 56LL))(
                           v15,
                           String1,
                           Str);
                    if ( v9 >= 0 )
                    {
                      v17 = v10 + 1;
                      goto LABEL_55;
                    }
                  }
                }
              }
            }
            goto LABEL_64;
          }
        }
        goto LABEL_8;
      }
    }
  }
LABEL_64:
  BUFFER::~BUFFER((BUFFER *)v47);
  BUFFER::~BUFFER((BUFFER *)v37);
  BUFFER::~BUFFER((BUFFER *)v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008990  push    rbp
0x180008992  push    rbx
0x180008993  push    rsi
0x180008994  push    rdi
0x180008995  push    r12
0x180008997  push    r13
0x180008999  push    r14
0x18000899b  push    r15
0x18000899d  lea     rbp, [rsp-628h]
0x1800089a5  sub     rsp, 728h
0x1800089ac  mov     rax, cs:__security_cookie
0x1800089b3  xor     rax, rsp
0x1800089b6  mov     [rbp+660h+var_50], rax
0x1800089bd  mov     rsi, [rbp+660h+arg_20]
0x1800089c4  mov     rbx, r9
0x1800089c7  mov     r14, [rbp+660h+arg_28]
0x1800089ce  mov     r12, r8
0x1800089d1  mov     [rsp+760h+var_730], r8
0x1800089d6  mov     rdi, rdx
0x1800089d9  mov     [rsp+760h+var_720], rcx
0x1800089de  mov     r13d, 1FEh
0x1800089e4  mov     r8d, r13d; Size
0x1800089e7  mov     [rsp+760h+var_718], rbx
0x1800089ec  xor     edx, edx; Val
0x1800089ee  mov     [rsp+760h+var_710], rsi
0x1800089f3  lea     rcx, [rbp+660h+var_64E]; void *
0x1800089f7  mov     [rsp+760h+var_708], r14
0x1800089fc  call    memset_0
0x180008a01  lea     rax, [rbp+660h+var_650]
0x180008a05  mov     [rbp+660h+var_69C], 100h
0x180008a0b  mov     [rbp+660h+String1], rax
0x180008a0f  lea     r15d, [r13+2]
0x180008a13  xor     eax, eax
0x180008a15  mov     [rbp+660h+var_6A0], r15d
0x180008a19  mov     r8d, r13d; Size
0x180008a1c  mov     [rbp+660h+var_698], eax
0x180008a1f  xor     edx, edx; Val
0x180008a21  mov     [rbp+660h+var_650], ax
0x180008a25  lea     rcx, [rbp+660h+var_44E]; void *
0x180008a2c  call    memset_0
0x180008a31  xor     ecx, ecx
0x180008a33  mov     [rbp+660h+var_6D8], r15d
0x180008a37  mov     [rbp+660h+var_6D0], ecx
0x180008a3a  lea     rax, [rbp+660h+var_450]
0x180008a41  mov     [rbp+660h+var_450], cx
0x180008a48  mov     r8d, r13d; Size
0x180008a4b  mov     [rsp+760h+var_728], rcx
0x180008a50  xor     edx, edx; Val
0x180008a52  lea     rcx, [rbp+660h+var_24E]; void *
0x180008a59  mov     [rbp+660h+Str], rax
0x180008a5d  mov     [rbp+660h+var_6D4], 100h
0x180008a63  call    memset_0
0x180008a68  xor     ecx, ecx
0x180008a6a  mov     [rbp+660h+var_668], r15d
0x180008a6e  mov     [rbp+660h+var_664], 100h
0x180008a74  lea     rax, [rbp+660h+var_250]
0x180008a7b  mov     [rbp+660h+var_670], rax
0x180008a7f  mov     [rbp+660h+var_660], ecx
0x180008a82  mov     [rbp+660h+var_250], cx
0x180008a89  test    rdi, rdi
0x180008a8c  jz      loc_180008E19
0x180008a92  test    r12, r12
0x180008a95  jz      loc_180008E19
0x180008a9b  test    rbx, rbx
0x180008a9e  jz      loc_180008E19
0x180008aa4  test    rsi, rsi
0x180008aa7  jz      loc_180008E19
0x180008aad  xor     esi, esi
0x180008aaf  test    r14, r14
0x180008ab2  jz      loc_180008E19
0x180008ab8  mov     rax, [r12]
0x180008abc  mov     rcx, r12
0x180008abf  mov     rax, [rax+40h]
0x180008ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac8  mov     ebx, eax
0x180008aca  test    eax, eax
0x180008acc  js      loc_180008E1E
0x180008ad2  cmp     word ptr [rdi], 5Bh ; '['
0x180008ad6  jz      short loc_180008AE2
0x180008ad8  mov     ebx, 8007000Dh
0x180008add  jmp     loc_180008E1E
0x180008ae2  mov     r15, rsi
0x180008ae5  mov     r14d, esi
0x180008ae8  or      r13d, 0FFFFFFFFh
0x180008aec  mov     rdx, 100002200h
0x180008af6  mov     r12d, 20h ; ' '
0x180008afc  add     rdi, 2
0x180008b00  movzx   ecx, word ptr [rdi]
0x180008b03  cmp     cx, r12w
0x180008b07  ja      short loc_180008B0F
0x180008b09  bt      rdx, rcx
0x180008b0d  jb      short loc_180008AFC
0x180008b0f  mov     r12, [rsp+760h+var_730]
0x180008b14  mov     eax, 2Ch ; ','
0x180008b19  cmp     cx, 40h ; '@'
0x180008b1d  jnz     loc_180008C38
0x180008b23  test    r14d, r14d
0x180008b26  jnz     short loc_180008AD8
0x180008b28  lea     rbx, [rdi+2]
0x180008b2c  mov     edx, eax; Ch
0x180008b2e  mov     rcx, rbx; Str
0x180008b31  call    cs:__imp_wcschr
0x180008b37  mov     rdi, rax
0x180008b3a  test    rax, rax
0x180008b3d  jnz     short loc_180008B6B
0x180008b3f  lea     edx, [rax+5Dh]; Ch
0x180008b42  mov     rcx, rbx; Str
0x180008b45  call    cs:__imp_wcschr
0x180008b4b  mov     rdi, rax
0x180008b4e  test    rax, rax
0x180008b51  jnz     short loc_180008B6B
0x180008b53  lea     edx, [rax+20h]; Ch
0x180008b56  mov     rcx, rbx; Str
0x180008b59  call    cs:__imp_wcschr
0x180008b5f  mov     rdi, rax
0x180008b62  test    rax, rax
0x180008b65  jz      loc_180008AD8
0x180008b6b  mov     r8, rdi
0x180008b6e  lea     rcx, [rbp+660h+var_6C8]; this
0x180008b72  sub     r8, rbx
0x180008b75  mov     rdx, rbx; unsigned __int16 *
0x180008b78  sar     r8, 1; unsigned int
0x180008b7b  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180008b80  mov     ebx, eax
0x180008b82  test    eax, eax
0x180008b84  js      loc_180008E1E
0x180008b8a  mov     rsi, [rbp+660h+String1]
0x180008b8e  lea     rdx, aStart_0; "start"
0x180008b95  mov     rcx, rsi; String1
0x180008b98  call    cs:__imp__wcsicmp
0x180008b9e  test    eax, eax
0x180008ba0  jnz     short loc_180008BAB
0x180008ba2  lea     r14d, [rax+2]
0x180008ba6  jmp     loc_180008DB1
0x180008bab  lea     rdx, aEnd; "end"
0x180008bb2  mov     rcx, rsi; String1
0x180008bb5  call    cs:__imp__wcsicmp
0x180008bbb  test    eax, eax
0x180008bbd  jnz     short loc_180008BC8
0x180008bbf  lea     r14d, [rax+3]
0x180008bc3  jmp     loc_180008DB1
0x180008bc8  xor     edx, edx; EndPtr
0x180008bca  mov     rcx, rsi; String
0x180008bcd  lea     r8d, [rdx+0Ah]; Radix
0x180008bd1  lea     r14d, [rdx+1]
0x180008bd5  call    cs:__imp_wcstoul
0x180008bdb  mov     r13d, eax
0x180008bde  test    eax, eax
0x180008be0  jnz     loc_180008DB1
0x180008be6  lea     rdx, a0; "0"
0x180008bed  mov     rcx, rsi; String1
0x180008bf0  call    cs:__imp__wcsicmp
0x180008bf6  xor     edx, edx
0x180008bf8  test    eax, eax
0x180008bfa  jz      loc_180008DB1
0x180008c00  mov     rcx, [rsp+760h+var_720]
0x180008c05  lea     r9, [rsp+760h+var_728]
0x180008c0a  add     rcx, 8
0x180008c0e  mov     [rsp+760h+var_740], edx
0x180008c12  mov     ebx, 80070057h
0x180008c17  mov     [rsp+760h+var_728], rsi
0x180008c1c  mov     r8d, 0C0000428h
0x180008c22  mov     edx, ebx
0x180008c24  mov     rax, [rcx]
0x180008c27  mov     rax, [rax+90h]
0x180008c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c33  jmp     loc_180008E1E
0x180008c38  mov     edx, 3Dh ; '='; Ch
0x180008c3d  mov     rcx, rdi; Str
0x180008c40  call    cs:__imp_wcschr
0x180008c46  mov     rsi, rax
0x180008c49  test    rax, rax
0x180008c4c  jz      loc_180008AD8
0x180008c52  mov     r8, rax
0x180008c55  lea     rcx, [rbp+660h+var_6C8]; this
0x180008c59  sub     r8, rdi
0x180008c5c  mov     rdx, rdi; unsigned __int16 *
0x180008c5f  sar     r8, 1; unsigned int
0x180008c62  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180008c67  mov     ebx, eax
0x180008c69  test    eax, eax
0x180008c6b  js      loc_180008E1E
0x180008c71  lea     rcx, [rbp+660h+var_6C8]; this
0x180008c75  call    ?StripWhiteSpace@@YAJPEAVSTRU@@@Z; StripWhiteSpace(STRU *)
0x180008c7a  xor     r8d, r8d
0x180008c7d  mov     ebx, eax
0x180008c7f  test    eax, eax
0x180008c81  js      loc_180008E1E
0x180008c87  lea     rax, [rsi+2]
0x180008c8b  movzx   esi, word ptr [rax]
0x180008c8e  test    si, si
0x180008c91  jz      loc_180008AD8
0x180008c97  cmp     si, 27h ; '''
0x180008c9b  jz      short loc_180008CA9
0x180008c9d  cmp     si, 22h ; '"'
0x180008ca1  jz      short loc_180008CA9
0x180008ca3  add     rax, 2
0x180008ca7  jmp     short loc_180008C8B
0x180008ca9  lea     rdx, [rax+2]; unsigned __int16 *
0x180008cad  mov     edi, r8d
0x180008cb0  mov     rax, rdx
0x180008cb3  cmp     [rax], r8w
0x180008cb7  jz      short loc_180008CD6
0x180008cb9  cmp     [rax], si
0x180008cbc  jnz     short loc_180008CCD
0x180008cbe  cmp     [rax+2], si
0x180008cc2  jnz     short loc_180008CD3
0x180008cc4  mov     edi, 1
0x180008cc9  add     rax, 2
0x180008ccd  add     rax, 2
0x180008cd1  jmp     short loc_180008CB3
0x180008cd3  mov     r15, rax
0x180008cd6  test    r15, r15
0x180008cd9  jz      loc_180008AD8
0x180008cdf  mov     r8, r15
0x180008ce2  lea     rcx, [rsp+760h+var_700]; this
0x180008ce7  sub     r8, rdx
0x180008cea  sar     r8, 1; unsigned int
0x180008ced  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180008cf2  mov     ebx, eax
0x180008cf4  test    eax, eax
0x180008cf6  js      loc_180008E1E
0x180008cfc  test    edi, edi
0x180008cfe  jz      short loc_180008D7B
0x180008d00  mov     rdi, [rbp+660h+Str]
0x180008d04  lea     rcx, [rbp+660h+var_690]; this
0x180008d08  xor     edx, edx; unsigned int
0x180008d0a  mov     rbx, rdi
0x180008d0d  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180008d12  movzx   edx, si; Ch
0x180008d15  mov     rcx, rdi; Str
0x180008d18  call    cs:__imp_wcschr
0x180008d1e  mov     rdx, rbx; unsigned __int16 *
0x180008d21  lea     rcx, [rbp+660h+var_690]; this
0x180008d25  test    rax, rax
0x180008d28  jz      short loc_180008D54
0x180008d2a  lea     rdi, [rax+2]
0x180008d2e  mov     r8, rdi
0x180008d31  sub     r8, rbx
0x180008d34  sar     r8, 1; unsigned int
0x180008d37  call    ?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180008d3c  mov     ebx, eax
0x180008d3e  test    eax, eax
0x180008d40  js      loc_180008E1E
0x180008d46  cmp     [rdi], si
0x180008d49  jnz     short loc_180008D4F
0x180008d4b  add     rdi, 2
0x180008d4f  mov     rbx, rdi
0x180008d52  jmp     short loc_180008D12
0x180008d54  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180008d59  mov     ebx, eax
0x180008d5b  test    eax, eax
0x180008d5d  js      loc_180008E1E
0x180008d63  lea     rdx, [rbp+660h+var_690]; struct STRU *
0x180008d67  lea     rcx, [rsp+760h+var_700]; this
0x180008d6c  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180008d71  mov     ebx, eax
0x180008d73  test    eax, eax
0x180008d75  js      loc_180008E1E
0x180008d7b  lea     rcx, [rsp+760h+var_700]; this
0x180008d80  call    ?UnescapeOnly@STRU@@QEAAJXZ; STRU::UnescapeOnly(void)
0x180008d85  mov     ebx, eax
0x180008d87  test    eax, eax
0x180008d89  js      loc_180008E1E
0x180008d8f  mov     rax, [r12]
0x180008d93  mov     rcx, r12
0x180008d96  mov     r8, [rbp+660h+Str]
0x180008d9a  mov     rdx, [rbp+660h+String1]
0x180008d9e  mov     rax, [rax+38h]
0x180008da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da7  mov     ebx, eax
0x180008da9  test    eax, eax
0x180008dab  js      short loc_180008E1E
0x180008dad  lea     rdi, [r15+2]
0x180008db1  mov     rdx, 100002200h
0x180008dbb  mov     r12d, 20h ; ' '
0x180008dc1  cmp     [rdi], r12w
0x180008dc5  ja      short loc_180008DD6
0x180008dc7  movzx   eax, word ptr [rdi]
0x180008dca  bt      rdx, rax
0x180008dce  jnb     short loc_180008DD6
0x180008dd0  add     rdi, 2
0x180008dd4  jmp     short loc_180008DC1
0x180008dd6  mov     r12, [rsp+760h+var_730]
0x180008ddb  mov     eax, 5Dh ; ']'
0x180008de0  cmp     [rdi], ax
0x180008de3  jz      short loc_180008DFF
0x180008de5  mov     eax, 2Ch ; ','
0x180008dea  cmp     [rdi], ax
0x180008ded  jnz     loc_180008AD8
0x180008df3  add     rdi, 2
0x180008df7  movzx   ecx, word ptr [rdi]
0x180008dfa  jmp     loc_180008B19
0x180008dff  mov     rax, [rsp+760h+var_718]
0x180008e04  mov     [rax], rdi
0x180008e07  mov     rax, [rsp+760h+var_710]
0x180008e0c  mov     [rax], r14d
0x180008e0f  mov     rax, [rsp+760h+var_708]
0x180008e14  mov     [rax], r13d
0x180008e17  jmp     short loc_180008E1E
  ... truncated ...
```
