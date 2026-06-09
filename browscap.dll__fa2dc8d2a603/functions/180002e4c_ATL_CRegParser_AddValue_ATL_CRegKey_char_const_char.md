# ATL::CRegParser::AddValue(ATL::CRegKey &,char const *,char *)

- ea: `0x180002e4c`
- end: `0x1800034ef`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBDPEAD@Z`
- size: `1699`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const char *, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180005408`

## callees

- `0x180002e4c`
- `0x1800034f8`
- `0x180003738`
- `0x1800037f4`
- `0x180003ea4`
- `0x1800048d0`
- `0x180007034`
- `0x18000b60e`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!free` at `0x180003200`
- `msvcrt!free` at `0x18000324a`
- `msvcrt!free` at `0x180003262`
- `msvcrt!free` at `0x180003200`
- `msvcrt!free` at `0x18000324a`
- `msvcrt!free` at `0x180003262`
- `msvcrt!malloc` at `0x180003193`
- `msvcrt!malloc` at `0x180003193`
- `ADVAPI32!RegSetValueExA` at `0x1800030bd`
- `ADVAPI32!RegSetValueExA` at `0x18000323a`
- `ADVAPI32!RegSetValueExA` at `0x180003431`
- `ADVAPI32!RegSetValueExA` at `0x18000348c`
- `ADVAPI32!RegSetValueExA` at `0x1800030bd`
- `ADVAPI32!RegSetValueExA` at `0x18000323a`
- `ADVAPI32!RegSetValueExA` at `0x180003431`
- `ADVAPI32!RegSetValueExA` at `0x18000348c`
- `KERNEL32!lstrcmpiA` at `0x180002ecd`
- `KERNEL32!lstrcmpiA` at `0x180002ecd`
- `KERNEL32!MultiByteToWideChar` at `0x1800031d6`
- `KERNEL32!MultiByteToWideChar` at `0x1800031d6`
- `KERNEL32!IsDBCSLeadByte` at `0x18000304b`
- `KERNEL32!IsDBCSLeadByte` at `0x18000304b`
- `USER32!CharNextA` at `0x180003022`
- `USER32!CharNextA` at `0x18000303b`
- `USER32!CharNextA` at `0x1800034b4`
- `USER32!CharNextA` at `0x180003022`
- `USER32!CharNextA` at `0x18000303b`
- `USER32!CharNextA` at `0x1800034b4`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800031ec`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800031ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::AddValue(LPCSTR *this, HKEY *a2, const char *a3, char *a4)
{
  const CHAR *v4; // r15
  HKEY *v5; // r13
  LPCSTR *v6; // r14
  __int64 result; // rax
  unsigned int v8; // edi
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  int v12; // eax
  CHAR *v13; // rbx
  CHAR *i; // r14
  const CHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  unsigned int v19; // ecx
  LSTATUS v20; // esi
  _QWORD *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // r14
  __int64 v25; // rax
  void *v26; // rsp
  WCHAR *v27; // r15
  _QWORD *v28; // rax
  HRESULT v29; // esi
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  __int64 v33; // r14
  DWORD v34; // r15d
  size_t v35; // rbx
  BYTE *v36; // rcx
  const CHAR *v37; // rsi
  unsigned int v38; // r10d
  int v39; // r9d
  char v40; // r9
  __int64 v41; // rsi
  int Token; // eax
  WCHAR WideCharStr[2]; // [rsp+30h] [rbp+0h] BYREF
  ATL::CRegParser *v44; // [rsp+38h] [rbp+8h]
  BYTE Data[8]; // [rsp+40h] [rbp+10h] BYREF
  LPCSTR lpValueName; // [rsp+48h] [rbp+18h]
  ATL::CRegParser *v47; // [rsp+50h] [rbp+20h]
  const char *v48; // [rsp+60h] [rbp+30h]
  struct ATL::CRegKey *v49; // [rsp+70h] [rbp+40h]
  size_t v50; // [rsp+78h] [rbp+48h]
  char *v51; // [rsp+80h] [rbp+50h]
  BYTE *v52; // [rsp+90h] [rbp+60h] BYREF
  _BYTE v53[264]; // [rsp+98h] [rbp+68h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp+170h] BYREF
  CHAR v55[264]; // [rsp+1A8h] [rbp+178h] BYREF
  CHAR String1[4096]; // [rsp+2B0h] [rbp+280h] BYREF

  v4 = a3;
  lpValueName = a3;
  v5 = a2;
  v6 = this;
  v44 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v47 = (ATL::CRegParser *)this;
  v49 = (struct ATL::CRegKey *)a2;
  v48 = a3;
  v51 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( (int)result < 0 )
    return result;
  v9 = 0;
  while ( lstrcmpiA(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
  {
    if ( (unsigned int)++v9 >= 4 )
      return 2147614729LL;
  }
  v10 = (__int16)(&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9 + 1];
  while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
    *v6 = CharNextA(*v6);
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
  if ( (int)result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v41 = -1;
    do
      ++v41;
    while ( String1[v41] );
    v20 = RegSetValueExA(*v5, v4, 0, 1u, (const BYTE *)String1, v41 + 1);
LABEL_44:
    if ( v20 )
      return ATL::AtlHresultFromWin32(v20);
    goto LABEL_117;
  }
  if ( v10 == 17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( String1[v33] );
    *(_DWORD *)Data = v33;
    if ( (v33 & 1) != 0 )
      return 2147500037LL;
    try
    {
      v34 = (int)v33 / 2;
      v52 = 0;
      v35 = (int)v33 / 2;
      v50 = v35;
      if ( !((int)v33 / 2) )
        goto LABEL_80;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v35) )
        ATL::AtlThrowImpl(-2147024809);
      if ( v35 > 0x100 )
      {
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(&v52, v35);
        v36 = v52;
      }
      else
      {
LABEL_80:
        v36 = v53;
        v52 = v53;
      }
      v37 = lpValueName;
    }
    catch ( ... )
    {
      v8 = 0;
      LODWORD(v33) = *(_DWORD *)Data;
      v36 = v52;
      v35 = v50;
      v44 = v47;
      v5 = (HKEY *)v49;
      v37 = v48;
      v34 = v50;
    }
    if ( !v36 )
    {
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v52);
      return 2147500037LL;
    }
    memset_0(v36, 0, v35);
    v38 = 0;
    if ( (int)v33 <= 0 )
    {
LABEL_112:
      v20 = RegSetValueExA(*v5, v37, 0, 3u, v52, v34);
      if ( v52 != v53 )
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v52);
      goto LABEL_43;
    }
    while ( 1 )
    {
      v39 = String1[v38];
      if ( String1[v38] > 97 )
      {
        if ( v39 == 98 || v39 == 99 || v39 == 100 || (unsigned int)(v39 - 101) < 2 )
        {
LABEL_110:
          v40 = v39 - 87;
          goto LABEL_111;
        }
LABEL_109:
        v40 = 0;
        goto LABEL_111;
      }
      if ( String1[v38] == 97 )
        goto LABEL_110;
      if ( (char)v39 <= 56 )
        break;
      if ( v39 == 57 )
        goto LABEL_97;
      if ( v39 != 65 && v39 != 66 && v39 != 67 && v39 != 68 && (unsigned int)(v39 - 69) > 1 )
        goto LABEL_109;
      v40 = v39 - 55;
LABEL_111:
      v52[(unsigned __int64)v38 >> 1] |= v40 << (4 - 4 * (v38 & 1));
      if ( (int)++v38 >= (int)v33 )
        goto LABEL_112;
    }
    if ( (_BYTE)v39 != 56
      && v39 != 48
      && v39 != 49
      && v39 != 50
      && v39 != 51
      && v39 != 52
      && v39 != 53
      && (unsigned int)(v39 - 54) > 1 )
    {
      goto LABEL_109;
    }
LABEL_97:
    v40 = v39 - 48;
    goto LABEL_111;
  }
  if ( v10 != 19 )
  {
    if ( v10 != 16392 )
    {
LABEL_117:
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v51);
      if ( Token < 0 )
        return (unsigned int)Token;
      return v8;
    }
    v11 = -1;
    do
      ++v11;
    while ( String1[v11] );
    v12 = v11 + 2;
    lpData = 0;
    try
    {
      if ( !v12 )
        goto LABEL_23;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v12) )
        ATL::AtlThrowImpl(-2147024809);
      if ( (unsigned __int64)v12 > 0x100 )
      {
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
        v13 = (CHAR *)lpData;
      }
      else
      {
LABEL_23:
        v13 = v55;
        lpData = (BYTE *)v55;
      }
    }
    catch ( ... )
    {
      v8 = 0;
      v13 = (CHAR *)lpData;
      v5 = *(HKEY **)Data;
      v44 = v47;
      v4 = v48;
    }
    if ( v13 )
    {
      for ( i = String1; *i; ++v13 )
      {
        v15 = CharNextA(i);
        if ( *i == 92 && *v15 == 48 )
        {
          *v13 = 0;
          i = CharNextA(v15);
        }
        else
        {
          *v13 = *i;
          if ( IsDBCSLeadByte(*i) )
          {
            ++v13;
            if ( !*++i )
              break;
            *v13 = *i;
          }
          ++i;
        }
      }
      *(_WORD *)v13 = 0;
      if ( !lpData )
        ATL::AtlThrowImpl(-2147467259);
      cbData = 0;
      v17 = lpData;
      do
      {
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        v19 = v18 + 1;
        v17 += v19;
        cbData += v19;
      }
      while ( v19 != 1 );
      v20 = RegSetValueExA(*v5, v4, 0, 7u, lpData, cbData);
      v13 = (CHAR *)lpData;
    }
    else
    {
      v20 = 14;
    }
    if ( v13 != v55 )
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
    goto LABEL_43;
  }
  *(_DWORD *)WideCharStr = 0;
  v21 = 0;
  v49 = 0;
  v22 = -1;
  do
    ++v22;
  while ( String1[v22] );
  v23 = 2LL * ((int)v22 + 1);
  if ( (unsigned __int64)(v23 + 0x80000000LL) <= 0xFFFFFFFF )
  {
    v24 = (int)v23;
    if ( (int)v23 <= 1024
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v23, 0xFFFFFFFF) )
    {
      v25 = v24 + 15;
      if ( v24 + 15 < v24 )
        v25 = 0xFFFFFFFFFFFFFF0LL;
      v26 = alloca(v25 & 0xFFFFFFFFFFFFFFF0uLL);
      v27 = WideCharStr;
    }
    else
    {
      if ( ~v24 < 0x10 )
        ATL::AtlThrowImpl(-2147024809);
      v28 = malloc(v24 + 16);
      if ( v28 )
      {
        *v28 = 0;
        v21 = v28;
        v27 = (WCHAR *)(v28 + 2);
      }
      else
      {
        v27 = 0;
      }
    }
    if ( v27 )
    {
      *v27 = 0;
      if ( MultiByteToWideChar(3u, 0, String1, -1, v27, v24 >> 1) )
      {
        v29 = VarUI4FromStr(v27, 0, 0, (ULONG *)WideCharStr);
        if ( v29 < 0 )
        {
          while ( v21 )
          {
            v30 = v21;
            v21 = (_QWORD *)*v21;
            free(v30);
          }
          return (unsigned int)v29;
        }
        *(_DWORD *)Data = *(_DWORD *)WideCharStr;
        v20 = RegSetValueExA(*v5, lpValueName, 0, 4u, Data, 4u);
        while ( v21 )
        {
          v31 = v21;
          v21 = (_QWORD *)*v21;
          free(v31);
        }
LABEL_43:
        v6 = (LPCSTR *)v44;
        goto LABEL_44;
      }
    }
  }
  while ( v21 )
  {
    v32 = v21;
    v21 = (_QWORD *)*v21;
    free(v32);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180002e4c  push    rbp
0x180002e4e  push    rbx
0x180002e4f  push    rsi
0x180002e50  push    rdi
0x180002e51  push    r12
0x180002e53  push    r13
0x180002e55  push    r14
0x180002e57  push    r15
0x180002e59  mov     eax, 12C8h
0x180002e5e  call    _alloca_probe
0x180002e63  sub     rsp, rax
0x180002e66  lea     rbp, [rsp+30h]
0x180002e6b  mov     rax, cs:__security_cookie
0x180002e72  xor     rax, rbp
0x180002e75  mov     [rbp+12D0h+var_50], rax
0x180002e7c  mov     r15, r8
0x180002e7f  mov     [rbp+12D0h+lpValueName], r8
0x180002e83  mov     r13, rdx
0x180002e86  mov     r14, rcx
0x180002e89  mov     [rbp+12D0h+var_12C8], rcx
0x180002e8d  mov     qword ptr [rbp+12D0h+Data], rdx
0x180002e91  mov     [rbp+12D0h+var_12B0], rcx
0x180002e95  mov     [rbp+12D0h+var_1290], rdx
0x180002e99  mov     [rbp+12D0h+var_12A0], r8
0x180002e9d  mov     [rbp+12D0h+var_1280], r9
0x180002ea1  lea     rdx, [rbp+12D0h+String1]; char *
0x180002ea8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180002ead  xor     edi, edi
0x180002eaf  test    eax, eax
0x180002eb1  js      short loc_180002EE3
0x180002eb3  mov     ebx, edi
0x180002eb5  lea     r12, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBDAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(char const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(char const *,ushort &)'::`2'::map
0x180002ebc  movsxd  rsi, ebx
0x180002ebf  add     rsi, rsi
0x180002ec2  mov     rdx, [r12+rsi*8]; lpString2
0x180002ec6  lea     rcx, [rbp+12D0h+String1]; lpString1
0x180002ecd  call    cs:__imp_lstrcmpiA
0x180002ed3  test    eax, eax
0x180002ed5  jz      short loc_180002F06
0x180002ed7  inc     ebx
0x180002ed9  cmp     ebx, 4
0x180002edc  jb      short loc_180002EBC
0x180002ede  mov     eax, 80020009h
0x180002ee3  mov     rcx, [rbp+12D0h+var_50]
0x180002eea  xor     rcx, rbp; StackCookie
0x180002eed  call    __security_check_cookie
0x180002ef2  lea     rsp, [rbp+1298h]
0x180002ef9  pop     r15
0x180002efb  pop     r14
0x180002efd  pop     r13
0x180002eff  pop     r12
0x180002f01  pop     rdi
0x180002f02  pop     rsi
0x180002f03  pop     rbx
0x180002f04  pop     rbp
0x180002f05  retn
0x180002f06  movzx   ebx, word ptr [r12+rsi*8+8]
0x180002f0c  mov     esi, 13h
0x180002f11  mov     rdx, [r14]
0x180002f14  movsx   ecx, byte ptr [rdx]
0x180002f17  sub     ecx, 9
0x180002f1a  jz      loc_1800034B1
0x180002f20  sub     ecx, 1
0x180002f23  jz      loc_1800034B1
0x180002f29  sub     ecx, 3
0x180002f2c  jz      loc_1800034B1
0x180002f32  cmp     ecx, esi
0x180002f34  jz      loc_1800034B1
0x180002f3a  lea     rdx, [rbp+12D0h+String1]; char *
0x180002f41  mov     rcx, r14; this
0x180002f44  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x180002f49  test    eax, eax
0x180002f4b  js      short loc_180002EE3
0x180002f4d  mov     r12d, 8
0x180002f53  cmp     bx, r12w
0x180002f57  jz      loc_180003455
0x180002f5d  cmp     bx, 11h
0x180002f61  jz      loc_180003277
0x180002f67  cmp     bx, si
0x180002f6a  jz      loc_180003103
0x180002f70  mov     eax, 4008h
0x180002f75  cmp     bx, ax
0x180002f78  jnz     loc_180003499
0x180002f7e  lea     rcx, [rbp+12D0h+String1]
0x180002f85  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002f89  mov     rax, rsi
0x180002f8c  inc     rax
0x180002f8f  cmp     [rcx+rax], dil
0x180002f93  jnz     short loc_180002F8C
0x180002f95  add     eax, 2
0x180002f98  mov     [rbp+12D0h+var_1160], rdi
0x180002f9f  test    eax, eax
0x180002fa1  jz      short loc_180002FD9
0x180002fa3  movsxd  rcx, eax
0x180002fa6  xor     edx, edx
0x180002fa8  mov     rax, rsi
0x180002fab  div     rcx
0x180002fae  cmp     rax, 1
0x180002fb2  jb      loc_1800034C2
0x180002fb8  cmp     rcx, 100h
0x180002fbf  jbe     short loc_180002FD9
0x180002fc1  mov     rdx, rcx
0x180002fc4  lea     rcx, [rbp+12D0h+var_1160]
0x180002fcb  call    ?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002fd0  mov     rbx, [rbp+12D0h+var_1160]
0x180002fd7  jmp     short loc_180002FE7
0x180002fd9  lea     rbx, [rbp+12D0h+var_1158]
0x180002fe0  mov     [rbp+12D0h+var_1160], rbx
0x180002fe7  jmp     short loc_180003006
0x180002fe9  xor     edi, edi
0x180002feb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002fef  mov     rbx, [rbp+12D0h+var_1160]
0x180002ff6  mov     r13, qword ptr [rbp+12D0h+Data]
0x180002ffa  mov     rax, [rbp+12D0h+var_12B0]
0x180002ffe  mov     [rbp+12D0h+var_12C8], rax
0x180003002  mov     r15, [rbp+12D0h+var_12A0]
0x180003006  test    rbx, rbx
0x180003009  jz      loc_1800030CE
0x18000300f  lea     r14, [rbp+12D0h+String1]
0x180003016  cmp     [rbp+12D0h+String1], dil
0x18000301d  jz      short loc_18000306F
0x18000301f  mov     rcx, r14; lpsz
0x180003022  call    cs:__imp_CharNextA
0x180003028  mov     cl, [r14]
0x18000302b  cmp     cl, 5Ch ; '\'
0x18000302e  jnz     short loc_180003046
0x180003030  cmp     byte ptr [rax], 30h ; '0'
0x180003033  jnz     short loc_180003046
0x180003035  mov     [rbx], dil
0x180003038  mov     rcx, rax; lpsz
0x18000303b  call    cs:__imp_CharNextA
0x180003041  mov     r14, rax
0x180003044  jmp     short loc_180003067
0x180003046  mov     [rbx], cl
0x180003048  mov     cl, [r14]; TestChar
0x18000304b  call    cs:__imp_IsDBCSLeadByte
0x180003051  test    eax, eax
0x180003053  jz      short loc_180003064
0x180003055  inc     rbx
0x180003058  inc     r14
0x18000305b  mov     al, [r14]
0x18000305e  test    al, al
0x180003060  jz      short loc_18000306F
0x180003062  mov     [rbx], al
0x180003064  inc     r14
0x180003067  inc     rbx
0x18000306a  cmp     [r14], dil
0x18000306d  jnz     short loc_18000301F
0x18000306f  mov     word ptr [rbx], 0
0x180003074  mov     r8, [rbp+12D0h+var_1160]
0x18000307b  test    r8, r8
0x18000307e  jz      loc_1800034CD
0x180003084  mov     r10d, edi
0x180003087  mov     r9, r8
0x18000308a  mov     rcx, rsi
0x18000308d  inc     rcx
0x180003090  cmp     [r9+rcx], dil
0x180003094  jnz     short loc_18000308D
0x180003096  inc     ecx
0x180003098  mov     eax, ecx
0x18000309a  add     r9, rax
0x18000309d  add     r10d, ecx
0x1800030a0  cmp     ecx, 1
0x1800030a3  jnz     short loc_18000308A
0x1800030a5  mov     [rsp+1300h+cbData], r10d; cbData
0x1800030aa  mov     [rsp+1300h+lpData], r8; lpData
0x1800030af  lea     r9d, [rcx+6]; dwType
0x1800030b3  xor     r8d, r8d; Reserved
0x1800030b6  mov     rdx, r15; lpValueName
0x1800030b9  mov     rcx, [r13+0]; hKey
0x1800030bd  call    cs:__imp_RegSetValueExA
0x1800030c3  mov     esi, eax
0x1800030c5  mov     rbx, [rbp+12D0h+var_1160]
0x1800030cc  jmp     short loc_1800030D3
0x1800030ce  mov     esi, 0Eh
0x1800030d3  lea     rax, [rbp+12D0h+var_1158]
0x1800030da  cmp     rbx, rax
0x1800030dd  jz      short loc_1800030EB
0x1800030df  lea     rcx, [rbp+12D0h+var_1160]
0x1800030e6  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800030eb  mov     r14, [rbp+12D0h+var_12C8]
0x1800030ef  test    esi, esi
0x1800030f1  jz      loc_180003499
0x1800030f7  mov     ecx, esi; unsigned int
0x1800030f9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800030fe  jmp     loc_180002EE3
0x180003103  mov     dword ptr [rbp+12D0h+WideCharStr], edi
0x180003106  mov     rbx, rdi
0x180003109  mov     [rbp+12D0h+var_1290], rbx
0x18000310d  lea     rcx, [rbp+12D0h+String1]
0x180003114  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003118  mov     rax, rsi
0x18000311b  inc     rax
0x18000311e  cmp     [rcx+rax], dil
0x180003122  jnz     short loc_18000311B
0x180003124  inc     eax
0x180003126  movsxd  rcx, eax
0x180003129  add     rcx, rcx
0x18000312c  mov     eax, 80000000h
0x180003131  add     rax, rcx
0x180003134  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180003139  cmp     rax, rdx
0x18000313c  ja      loc_18000325A
0x180003142  movsxd  r14, ecx
0x180003145  cmp     ecx, 400h
0x18000314b  jg      short loc_18000317F
0x18000314d  mov     rcx, r14; this
0x180003150  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003155  test    al, al
0x180003157  jz      short loc_18000317F
0x180003159  lea     rax, [r14+0Fh]
0x18000315d  cmp     rax, r14
0x180003160  ja      short loc_18000316C
0x180003162  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000316c  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003170  call    _alloca_probe
0x180003175  sub     rsp, rax
0x180003178  lea     r15, [rsp+1300h+WideCharStr]
0x18000317d  jmp     short loc_1800031AD
0x18000317f  mov     rax, r14
0x180003182  not     rax
0x180003185  cmp     rax, 10h
0x180003189  jb      loc_1800034D8
0x18000318f  lea     rcx, [r14+10h]; Size
0x180003193  call    cs:__imp_malloc
0x180003199  test    rax, rax
0x18000319c  jnz     short loc_1800031A3
0x18000319e  mov     r15, rdi
0x1800031a1  jmp     short loc_1800031AD
0x1800031a3  mov     [rax], rdi
0x1800031a6  mov     rbx, rax
0x1800031a9  lea     r15, [rax+10h]
0x1800031ad  test    r15, r15
0x1800031b0  jz      loc_18000325A
0x1800031b6  mov     [r15], di
0x1800031ba  shr     r14, 1
0x1800031bd  mov     [rsp+1300h+cbData], r14d; cchWideChar
0x1800031c2  mov     [rsp+1300h+lpData], r15; lpWideCharStr
0x1800031c7  mov     r9d, esi; cbMultiByte
0x1800031ca  lea     r8, [rbp+12D0h+String1]; lpMultiByteStr
0x1800031d1  xor     edx, edx; dwFlags
0x1800031d3  lea     ecx, [rdx+3]; CodePage
0x1800031d6  call    cs:__imp_MultiByteToWideChar
0x1800031dc  test    eax, eax
0x1800031de  jz      short loc_18000325A
0x1800031e0  lea     r9, [rbp+12D0h+WideCharStr]; pulOut
0x1800031e4  xor     r8d, r8d; dwFlags
0x1800031e7  xor     edx, edx; lcid
0x1800031e9  mov     rcx, r15; strIn
0x1800031ec  call    cs:__imp_VarUI4FromStr
0x1800031f2  mov     esi, eax
0x1800031f4  test    eax, eax
0x1800031f6  jns     short loc_180003212
0x1800031f8  jmp     short loc_180003206
0x1800031fa  mov     rcx, rbx; Block
0x1800031fd  mov     rbx, [rbx]
0x180003200  call    cs:__imp_free
0x180003206  test    rbx, rbx
0x180003209  jnz     short loc_1800031FA
0x18000320b  mov     eax, esi
0x18000320d  jmp     loc_180002EE3
0x180003212  mov     eax, dword ptr [rbp+12D0h+WideCharStr]
0x180003215  mov     dword ptr [rbp+12D0h+Data], eax
0x180003218  mov     [rsp+1300h+cbData], 4; cbData
0x180003220  lea     rax, [rbp+12D0h+Data]
0x180003224  mov     [rsp+1300h+lpData], rax; lpData
0x180003229  mov     r9d, 4; dwType
0x18000322f  xor     r8d, r8d; Reserved
0x180003232  mov     rdx, [rbp+12D0h+lpValueName]; lpValueName
0x180003236  mov     rcx, [r13+0]; hKey
0x18000323a  call    cs:__imp_RegSetValueExA
0x180003240  mov     esi, eax
0x180003242  jmp     short loc_180003250
0x180003244  mov     rcx, rbx; Block
0x180003247  mov     rbx, [rbx]
0x18000324a  call    cs:__imp_free
0x180003250  test    rbx, rbx
0x180003253  jnz     short loc_180003244
0x180003255  jmp     loc_1800030EB
0x18000325a  jmp     short loc_180003268
0x18000325c  mov     rcx, rbx; Block
0x18000325f  mov     rbx, [rbx]
0x180003262  call    cs:__imp_free
0x180003268  test    rbx, rbx
0x18000326b  jnz     short loc_18000325C
0x18000326d  mov     eax, 8007000Eh
0x180003272  jmp     loc_180002EE3
0x180003277  lea     rax, [rbp+12D0h+String1]
0x18000327e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003282  mov     r14, rsi
0x180003285  inc     r14
0x180003288  cmp     [rax+r14], dil
0x18000328c  jnz     short loc_180003285
0x18000328e  mov     dword ptr [rbp+12D0h+Data], r14d
0x180003292  test    r14b, 1
0x180003296  jnz     loc_180003324
0x18000329c  mov     eax, r14d
0x18000329f  cdq
0x1800032a0  sub     eax, edx
0x1800032a2  sar     eax, 1
  ... truncated ...
```
