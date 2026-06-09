# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x18004c8c4`
- end: `0x18004cd92`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1230`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18003dbcc`

## callees

- `0x18003e480`
- `0x18004c8c4`
- `0x18004d590`
- `0x180057f78`
- `0x18005f37c`
- `0x18005f458`
- `0x18005f4ec`
- `0x180060224`
- `0x180104ece`
- `0x180104f30`
- `0x180104ff0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18004cc6e`
- `msvcrt!wcscat_s` at `0x18004cc7f`
- `msvcrt!wcscat_s` at `0x18004cc94`
- `msvcrt!wcscat_s` at `0x18004ccb3`
- `msvcrt!wcscat_s` at `0x18004cc6e`
- `msvcrt!wcscat_s` at `0x18004cc7f`
- `msvcrt!wcscat_s` at `0x18004cc94`
- `msvcrt!wcscat_s` at `0x18004ccb3`
- `msvcrt!malloc` at `0x18004c90c`
- `msvcrt!malloc` at `0x18004c961`
- `msvcrt!malloc` at `0x18004cbd5`
- `msvcrt!malloc` at `0x18004c90c`
- `msvcrt!malloc` at `0x18004c961`
- `msvcrt!malloc` at `0x18004cbd5`
- `msvcrt!free` at `0x18004c972`
- `msvcrt!free` at `0x18004cbb7`
- `msvcrt!free` at `0x18004cbc0`
- `msvcrt!free` at `0x18004cbe8`
- `msvcrt!free` at `0x18004cd0b`
- `msvcrt!free` at `0x18004cd26`
- `msvcrt!free` at `0x18004cd2f`
- `msvcrt!free` at `0x18004cd45`
- `msvcrt!free` at `0x18004cd4e`
- `msvcrt!free` at `0x18004cd61`
- `msvcrt!free` at `0x18004c972`
- `msvcrt!free` at `0x18004cbb7`
- `msvcrt!free` at `0x18004cbc0`
- `msvcrt!free` at `0x18004cbe8`
- `msvcrt!free` at `0x18004cd0b`
- `msvcrt!free` at `0x18004cd26`
- `msvcrt!free` at `0x18004cd2f`
- `msvcrt!free` at `0x18004cd45`
- `msvcrt!free` at `0x18004cd4e`
- `msvcrt!free` at `0x18004cd61`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18004cc37`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18004cc37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004cb80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ccfd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004cb80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ccfd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004c94e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004c94e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x18004cc59`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x18004cc59`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18004c9dc`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18004c9dc`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  ATL::CRegParser *v5; // r12
  const WCHAR *v6; // r15
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  int Token; // ebx
  unsigned int i; // ebx
  unsigned __int16 *v12; // rdi
  __int16 v13; // r14
  HKEY v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 cbData; // r13
  __int64 v18; // rax
  void *v19; // rsp
  BYTE *lpData; // r15
  unsigned int v21; // r9d
  unsigned int v22; // r8d
  char v23; // r8
  unsigned __int64 v24; // rdx
  char v25; // al
  __int64 v26; // rbx
  const BYTE *v27; // r13
  _WORD *v28; // r14
  __int64 v29; // rax
  ATL::CRegObject *v30; // rcx
  const WCHAR *v31; // rax
  const wchar_t *v32; // r12
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // r15
  __int64 v35; // rax
  BYTE Data[8]; // [rsp+30h] [rbp+0h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp+8h] BYREF
  __int64 v39; // [rsp+40h] [rbp+10h] BYREF
  ATL::CRegParser *v40; // [rsp+48h] [rbp+18h]
  HKEY *v41; // [rsp+50h] [rbp+20h]
  unsigned __int16 *v42; // [rsp+58h] [rbp+28h]
  __int64 v43; // [rsp+60h] [rbp+30h] BYREF

  v5 = this;
  v40 = this;
  v42 = a4;
  v39 = 0;
  v6 = a3;
  *(_QWORD *)Data = a3;
  v41 = a2;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_9;
  Token = ATL::CRegParser::NextToken(v5, v8);
  if ( Token < 0 )
  {
LABEL_74:
    free(v9);
    goto LABEL_75;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
      return 2147614729LL;
    }
    if ( !lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v12 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v12 )
    goto LABEL_8;
  v13 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v5);
  Token = ATL::CRegParser::NextToken(v5, v12);
  if ( Token < 0 )
  {
LABEL_73:
    free(v12);
    goto LABEL_74;
  }
  pulOut = 0;
  if ( v13 != 8 )
  {
    if ( v13 != 17 )
    {
      if ( v13 == 19 )
      {
        VarUI4FromStr(v12, 0, 0, &pulOut);
        v14 = *a2;
        *(_DWORD *)Data = pulOut;
        RegSetValueExW(v14, v6, 0, 4u, Data, 4u);
      }
      goto LABEL_72;
    }
    v15 = -1;
    do
      ++v15;
    while ( v12[v15] );
    if ( (v15 & 1) == 0 )
    {
      v16 = (unsigned int)((int)v15 >> 31);
      cbData = (int)v15 / 2;
      if ( cbData <= 0x400
        && (LODWORD(v16) = (int)v15 % 2,
            ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v15 / 2), v16)) )
      {
        v18 = cbData + 15;
        if ( cbData + 15 < cbData )
          v18 = 0xFFFFFFFFFFFFFF0LL;
        v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
        lpData = Data;
      }
      else
      {
        lpData = (BYTE *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                           &v39,
                           cbData);
      }
      if ( lpData )
      {
        memset_0(lpData, 0, cbData);
        v21 = 0;
        if ( (int)v15 <= 0 )
        {
LABEL_52:
          RegSetValueExW(*v41, *(LPCWSTR *)Data, 0, 3u, lpData, cbData);
          goto LABEL_72;
        }
        while ( 2 )
        {
          v22 = v12[v21];
          if ( v22 > 0x61 )
          {
            if ( v22 != 98 && v22 != 99 && v22 != 100 && v22 - 101 >= 2 )
              goto LABEL_49;
          }
          else if ( v22 != 97 )
          {
            if ( v22 > 0x38 )
            {
              if ( v22 == 57 )
                goto LABEL_37;
              if ( v22 != 65 && v22 != 66 && v22 != 67 && v22 != 68 && v22 - 69 > 1 )
                goto LABEL_49;
              v23 = v22 - 55;
            }
            else
            {
              if ( v22 == 56
                || v22 == 48
                || v22 == 49
                || v22 == 50
                || v22 == 51
                || v22 == 52
                || v22 == 53
                || v22 - 54 <= 1 )
              {
LABEL_37:
                v23 = v22 - 48;
                goto LABEL_51;
              }
LABEL_49:
              v23 = 0;
            }
LABEL_51:
            v24 = (unsigned __int64)v21 >> 1;
            v25 = 4 * (v21++ & 1);
            lpData[v24] |= v23 << (4 - v25);
            if ( (int)v21 >= (int)v15 )
              goto LABEL_52;
            continue;
          }
          break;
        }
        v23 = v22 - 87;
        goto LABEL_51;
      }
    }
    goto LABEL_57;
  }
  v26 = -1;
  v27 = (const BYTE *)v12;
  v28 = 0;
  if ( !a5 )
  {
    do
LABEL_69:
      ++v26;
    while ( *(_WORD *)&v27[2 * v26] );
    RegSetValueExW(*v41, v6, 0, 1u, v27, 2 * v26 + 2);
    if ( v28 )
      free(v28);
LABEL_72:
    Token = ATL::CRegParser::NextToken(v5, v42);
    if ( Token >= 0 )
    {
      free(v12);
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
      return 0;
    }
    goto LABEL_73;
  }
  v29 = -1;
  do
    ++v29;
  while ( v12[v29] );
  if ( (int)v29 > 4094 )
  {
LABEL_57:
    free(v12);
    free(v9);
    Token = -2147467259;
    goto LABEL_75;
  }
  v28 = malloc(0x2000u);
  if ( v28 )
  {
    v30 = (ATL::CRegObject *)*((_QWORD *)v5 + 1);
    v43 = 0;
    v31 = ATL::CRegObject::StrFromMap(v30, L"Module");
    v32 = v31;
    if ( v31 )
    {
      v33 = (unsigned __int16 *)ATL::CRegParser::StrStrW(v12, v31);
      v34 = v33;
      if ( v33 && (v33 == v42 || *CharPrevW(v12, v33) != 34) )
      {
        *v28 = 0;
        lstrcpynW(v28, v12, v34 - v12);
        wcscat_s(v28, 0x1000u, L"\"");
        wcscat_s(v28, 0x1000u, v32);
        wcscat_s(v28, 0x1000u, L"\"");
        v35 = -1;
        do
          ++v35;
        while ( v32[v35] );
        wcscat_s(v28, 0x1000u, &v34[v35]);
        v27 = (const BYTE *)v28;
      }
      v6 = *(const WCHAR **)Data;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v43);
    v5 = v40;
    goto LABEL_69;
  }
  free(v12);
LABEL_8:
  free(v9);
LABEL_9:
  Token = -2147024882;
LABEL_75:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v39);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18004c8c4  push    rbp
0x18004c8c6  push    rbx
0x18004c8c7  push    rsi
0x18004c8c8  push    rdi
0x18004c8c9  push    r12
0x18004c8cb  push    r13
0x18004c8cd  push    r14
0x18004c8cf  push    r15
0x18004c8d1  sub     rsp, 78h
0x18004c8d5  lea     rbp, [rsp+30h]
0x18004c8da  mov     rax, cs:__security_cookie
0x18004c8e1  xor     rax, rbp
0x18004c8e4  mov     [rbp+80h+var_48], rax
0x18004c8e8  mov     r12, rcx
0x18004c8eb  mov     [rbp+80h+var_68], rcx
0x18004c8ef  xor     edi, edi
0x18004c8f1  mov     [rbp+80h+var_58], r9
0x18004c8f5  mov     ecx, 2000h; Size
0x18004c8fa  mov     [rbp+80h+var_70], rdi
0x18004c8fe  mov     r15, r8
0x18004c901  mov     qword ptr [rbp+80h+Data], r8
0x18004c905  mov     r13, rdx
0x18004c908  mov     [rbp+80h+var_60], rdx
0x18004c90c  call    cs:__imp_malloc
0x18004c912  mov     rsi, rax
0x18004c915  test    rax, rax
0x18004c918  jz      short loc_18004C978
0x18004c91a  mov     rdx, rax; unsigned __int16 *
0x18004c91d  mov     rcx, r12; this
0x18004c920  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004c925  mov     ebx, eax
0x18004c927  test    eax, eax
0x18004c929  js      loc_18004CD2C
0x18004c92f  mov     ebx, edi
0x18004c931  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004c938  mov     rcx, rsi; Block
0x18004c93b  cmp     ebx, 3
0x18004c93e  jnb     loc_18004CD61
0x18004c944  movsxd  r14, ebx
0x18004c947  add     r14, r14
0x18004c94a  mov     rdx, [rax+r14*8]; lpString2
0x18004c94e  call    cs:__imp_lstrcmpiW
0x18004c954  test    eax, eax
0x18004c956  jz      short loc_18004C95C
0x18004c958  inc     ebx
0x18004c95a  jmp     short loc_18004C931
0x18004c95c  mov     ecx, 2000h; Size
0x18004c961  call    cs:__imp_malloc
0x18004c967  mov     rdi, rax
0x18004c96a  test    rax, rax
0x18004c96d  jnz     short loc_18004C982
0x18004c96f  mov     rcx, rsi; Block
0x18004c972  call    cs:__imp_free
0x18004c978  mov     ebx, 8007000Eh
0x18004c97d  jmp     loc_18004CD35
0x18004c982  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18004c989  mov     rcx, r12; this
0x18004c98c  movzx   r14d, word ptr [rax+r14*8+8]
0x18004c992  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18004c997  mov     rdx, rdi; unsigned __int16 *
0x18004c99a  mov     rcx, r12; this
0x18004c99d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004c9a2  xor     ecx, ecx
0x18004c9a4  mov     ebx, eax
0x18004c9a6  test    eax, eax
0x18004c9a8  js      loc_18004CD23
0x18004c9ae  lea     eax, [rcx+8]
0x18004c9b1  mov     [rbp+80h+pulOut], ecx
0x18004c9b4  cmp     r14w, ax
0x18004c9b8  jz      loc_18004CB8B
0x18004c9be  cmp     r14w, 11h
0x18004c9c3  jz      short loc_18004CA0B
0x18004c9c5  cmp     r14w, 13h
0x18004c9ca  jnz     loc_18004CD11
0x18004c9d0  lea     r9, [rbp+80h+pulOut]; pulOut
0x18004c9d4  xor     r8d, r8d; dwFlags
0x18004c9d7  xor     edx, edx; lcid
0x18004c9d9  mov     rcx, rdi; strIn
0x18004c9dc  call    cs:__imp_VarUI4FromStr
0x18004c9e2  mov     eax, [rbp+80h+pulOut]
0x18004c9e5  mov     r9d, 4
0x18004c9eb  mov     rcx, [r13+0]
0x18004c9ef  mov     rdx, r15
0x18004c9f2  mov     dword ptr [rbp+80h+Data], eax
0x18004c9f5  lea     rax, [rbp+80h+Data]
0x18004c9f9  mov     [rsp+0B0h+cbData], 4
0x18004ca01  mov     [rsp+0B0h+lpData], rax
0x18004ca06  jmp     loc_18004CB7D
0x18004ca0b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004ca0f  inc     rbx
0x18004ca12  cmp     [rdi+rbx*2], cx
0x18004ca16  jnz     short loc_18004CA0F
0x18004ca18  test    bl, 1
0x18004ca1b  jnz     loc_18004CBB4
0x18004ca21  mov     eax, ebx
0x18004ca23  mov     ecx, 2
0x18004ca28  cdq; unsigned __int64
0x18004ca29  idiv    ecx
0x18004ca2b  movsxd  r13, eax
0x18004ca2e  cmp     r13, 400h
0x18004ca35  ja      short loc_18004CA69
0x18004ca37  mov     rcx, r13; this
0x18004ca3a  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18004ca3f  test    al, al
0x18004ca41  jz      short loc_18004CA69
0x18004ca43  lea     rax, [r13+0Fh]
0x18004ca47  cmp     rax, r13
0x18004ca4a  ja      short loc_18004CA56
0x18004ca4c  mov     rax, 0FFFFFFFFFFFFFF0h
0x18004ca56  and     rax, 0FFFFFFFFFFFFFFF0h
0x18004ca5a  call    _alloca_probe
0x18004ca5f  sub     rsp, rax
0x18004ca62  lea     r15, [rsp+0B0h+Data]
0x18004ca67  jmp     short loc_18004CA78
0x18004ca69  mov     rdx, r13
0x18004ca6c  lea     rcx, [rbp+80h+var_70]
0x18004ca70  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x18004ca75  mov     r15, rax
0x18004ca78  test    r15, r15
0x18004ca7b  jz      loc_18004CBB4
0x18004ca81  mov     r8, r13; Size
0x18004ca84  xor     edx, edx; Val
0x18004ca86  mov     rcx, r15; void *
0x18004ca89  call    memset_0
0x18004ca8e  xor     eax, eax
0x18004ca90  mov     r9d, eax
0x18004ca93  test    ebx, ebx
0x18004ca95  jle     loc_18004CB62
0x18004ca9b  mov     eax, r9d
0x18004ca9e  movzx   r8d, word ptr [rdi+rax*2]
0x18004caa3  cmp     r8d, 61h ; 'a'
0x18004caa7  ja      short loc_18004CB14
0x18004caa9  jz      loc_18004CB35
0x18004caaf  cmp     r8d, 38h ; '8'
0x18004cab3  ja      short loc_18004CAE8
0x18004cab5  jz      short loc_18004CAE2
0x18004cab7  mov     ecx, r8d
0x18004caba  sub     ecx, 30h ; '0'
0x18004cabd  jz      short loc_18004CAE2
0x18004cabf  sub     ecx, 1
0x18004cac2  jz      short loc_18004CAE2
0x18004cac4  sub     ecx, 1
0x18004cac7  jz      short loc_18004CAE2
0x18004cac9  sub     ecx, 1
0x18004cacc  jz      short loc_18004CAE2
0x18004cace  sub     ecx, 1
0x18004cad1  jz      short loc_18004CAE2
0x18004cad3  sub     ecx, 1
0x18004cad6  jz      short loc_18004CAE2
0x18004cad8  sub     ecx, 1
0x18004cadb  jz      short loc_18004CAE2
0x18004cadd  cmp     ecx, 1
0x18004cae0  jnz     short loc_18004CB30
0x18004cae2  sub     r8b, 30h ; '0'
0x18004cae6  jmp     short loc_18004CB39
0x18004cae8  mov     ecx, r8d
0x18004caeb  sub     ecx, 39h ; '9'
0x18004caee  jz      short loc_18004CAE2
0x18004caf0  sub     ecx, 8
0x18004caf3  jz      short loc_18004CB0E
0x18004caf5  sub     ecx, 1
0x18004caf8  jz      short loc_18004CB0E
0x18004cafa  sub     ecx, 1
0x18004cafd  jz      short loc_18004CB0E
0x18004caff  sub     ecx, 1
0x18004cb02  jz      short loc_18004CB0E
0x18004cb04  sub     ecx, 1
0x18004cb07  jz      short loc_18004CB0E
0x18004cb09  cmp     ecx, 1
0x18004cb0c  jnz     short loc_18004CB30
0x18004cb0e  sub     r8b, 37h ; '7'
0x18004cb12  jmp     short loc_18004CB39
0x18004cb14  mov     ecx, r8d
0x18004cb17  sub     ecx, 62h ; 'b'
0x18004cb1a  jz      short loc_18004CB35
0x18004cb1c  sub     ecx, 1
0x18004cb1f  jz      short loc_18004CB35
0x18004cb21  sub     ecx, 1
0x18004cb24  jz      short loc_18004CB35
0x18004cb26  sub     ecx, 1
0x18004cb29  jz      short loc_18004CB35
0x18004cb2b  cmp     ecx, 1
0x18004cb2e  jz      short loc_18004CB35
0x18004cb30  xor     r8b, r8b
0x18004cb33  jmp     short loc_18004CB39
0x18004cb35  sub     r8b, 57h ; 'W'
0x18004cb39  mov     eax, r9d
0x18004cb3c  mov     edx, r9d
0x18004cb3f  and     eax, 1
0x18004cb42  shr     rdx, 1
0x18004cb45  shl     eax, 2
0x18004cb48  mov     ecx, 4
0x18004cb4d  sub     ecx, eax
0x18004cb4f  inc     r9d
0x18004cb52  shl     r8b, cl
0x18004cb55  or      [rdx+r15], r8b
0x18004cb59  cmp     r9d, ebx
0x18004cb5c  jl      loc_18004CA9B
0x18004cb62  mov     rcx, [rbp+80h+var_60]
0x18004cb66  mov     r9d, 3; dwType
0x18004cb6c  mov     rdx, qword ptr [rbp+80h+Data]; lpValueName
0x18004cb70  mov     [rsp+0B0h+cbData], r13d; cbData
0x18004cb75  mov     [rsp+0B0h+lpData], r15; lpData
0x18004cb7a  mov     rcx, [rcx]; hKey
0x18004cb7d  xor     r8d, r8d; Reserved
0x18004cb80  call    cs:__imp_RegSetValueExW
0x18004cb86  jmp     loc_18004CD11
0x18004cb8b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004cb8f  mov     r13, rdi
0x18004cb92  mov     r14, rcx
0x18004cb95  cmp     [rbp+80h+arg_20], cl
0x18004cb9b  jz      loc_18004CCCF
0x18004cba1  mov     rax, rbx
0x18004cba4  inc     rax
0x18004cba7  cmp     [rdi+rax*2], cx
0x18004cbab  jnz     short loc_18004CBA4
0x18004cbad  cmp     eax, 0FFEh
0x18004cbb2  jle     short loc_18004CBD0
0x18004cbb4  mov     rcx, rdi; Block
0x18004cbb7  call    cs:__imp_free
0x18004cbbd  mov     rcx, rsi; Block
0x18004cbc0  call    cs:__imp_free
0x18004cbc6  mov     ebx, 80004005h
0x18004cbcb  jmp     loc_18004CD35
0x18004cbd0  mov     ecx, 2000h; Size
0x18004cbd5  call    cs:__imp_malloc
0x18004cbdb  mov     r14, rax
0x18004cbde  xor     eax, eax
0x18004cbe0  test    r14, r14
0x18004cbe3  jnz     short loc_18004CBF3
0x18004cbe5  mov     rcx, rdi; Block
0x18004cbe8  call    cs:__imp_free
0x18004cbee  jmp     loc_18004C96F
0x18004cbf3  mov     rcx, [r12+8]; this
0x18004cbf8  lea     rdx, aModule; "Module"
0x18004cbff  mov     [rbp+80h+var_50], rax
0x18004cc03  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18004cc08  mov     r12, rax
0x18004cc0b  test    rax, rax
0x18004cc0e  jz      loc_18004CCC0
0x18004cc14  mov     rdx, rax; LPCWSTR
0x18004cc17  mov     rcx, rdi; lpsz
0x18004cc1a  call    ?StrStrW@CRegParser@ATL@@KAPEBGPEBG0@Z; ATL::CRegParser::StrStrW(ushort const *,ushort const *)
0x18004cc1f  mov     r15, rax
0x18004cc22  test    rax, rax
0x18004cc25  jz      loc_18004CCBC
0x18004cc2b  cmp     rax, [rbp+80h+var_58]
0x18004cc2f  jz      short loc_18004CC43
0x18004cc31  mov     rdx, rax; lpszCurrent
0x18004cc34  mov     rcx, rdi; lpszStart
0x18004cc37  call    cs:__imp_CharPrevW
0x18004cc3d  cmp     word ptr [rax], 22h ; '"'
0x18004cc41  jz      short loc_18004CCBC
0x18004cc43  mov     r8, r15
0x18004cc46  xor     r13d, r13d
0x18004cc49  sub     r8, rdi
0x18004cc4c  mov     [r14], r13w
0x18004cc50  sar     r8, 1; iMaxLength
0x18004cc53  mov     rdx, rdi; lpString2
0x18004cc56  mov     rcx, r14; lpString1
0x18004cc59  call    cs:__imp_lstrcpynW
0x18004cc5f  lea     r8, Source; "\""
0x18004cc66  mov     edx, 1000h; SizeInWords
0x18004cc6b  mov     rcx, r14; Destination
0x18004cc6e  call    cs:__imp_wcscat_s
0x18004cc74  mov     r8, r12; Source
0x18004cc77  mov     edx, 1000h; SizeInWords
0x18004cc7c  mov     rcx, r14; Destination
0x18004cc7f  call    cs:__imp_wcscat_s
0x18004cc85  lea     r8, Source; "\""
0x18004cc8c  mov     edx, 1000h; SizeInWords
0x18004cc91  mov     rcx, r14; Destination
0x18004cc94  call    cs:__imp_wcscat_s
0x18004cc9a  mov     rax, rbx
0x18004cc9d  inc     rax
0x18004cca0  cmp     [r12+rax*2], r13w
0x18004cca5  jnz     short loc_18004CC9D
0x18004cca7  lea     r8, [r15+rax*2]; Source
0x18004ccab  mov     edx, 1000h; SizeInWords
0x18004ccb0  mov     rcx, r14; Destination
0x18004ccb3  call    cs:__imp_wcscat_s
0x18004ccb9  mov     r13, r14
0x18004ccbc  mov     r15, qword ptr [rbp+80h+Data]
0x18004ccc0  lea     rcx, [rbp+80h+var_50]
0x18004ccc4  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18004ccc9  mov     r12, [rbp+80h+var_68]
0x18004cccd  xor     ecx, ecx
0x18004cccf  inc     rbx
0x18004ccd2  cmp     [r13+rbx*2+0], cx
0x18004ccd8  jnz     short loc_18004CCCF
0x18004ccda  mov     rcx, [rbp+80h+var_60]
0x18004ccde  lea     eax, ds:2[rbx*2]
0x18004cce5  mov     [rsp+0B0h+cbData], eax; cbData
0x18004cce9  mov     r9d, 1; dwType
0x18004ccef  xor     r8d, r8d; Reserved
0x18004ccf2  mov     [rsp+0B0h+lpData], r13; lpData
0x18004ccf7  mov     rdx, r15; lpValueName
0x18004ccfa  mov     rcx, [rcx]; hKey
0x18004ccfd  call    cs:__imp_RegSetValueExW
0x18004cd03  test    r14, r14
  ... truncated ...
```
