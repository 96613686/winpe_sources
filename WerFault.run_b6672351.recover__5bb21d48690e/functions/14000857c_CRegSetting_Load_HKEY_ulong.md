# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x14000857c`
- end: `0x140008861`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `741`
- prototype: `int(CRegSetting *__hidden this, HKEY, unsigned int)`
- caller_count: `13`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x14000bee0`
- `0x1400183d0`
- `0x140020118`
- `0x1400322f0`
- `0x140032478`
- `0x14003a67c`
- `0x14003aa8c`
- `0x140041cb8`
- `0x140045078`
- `0x14004cc34`
- `0x1400562e0`
- `0x140056cbc`
- `0x140057d24`

## callees

- `0x140002748`
- `0x1400030f8`
- `0x14000551c`
- `0x14000857c`
- `0x14000c060`
- `0x14000ce0c`
- `0x14005f588`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000883e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000883e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008625`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008625`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008663`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000874f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008663`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000874f`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, int a3)
{
  HKEY v4; // r14
  HKEY *phkResult; // rax
  int v8; // ebx
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // edx
  LPBYTE *v14; // rdi
  unsigned __int64 v15; // r15
  LPBYTE v16; // rax
  unsigned __int64 v17; // rbx
  bool v18; // zf
  __int64 v19; // r8
  __int64 v20; // r9
  LPBYTE v21; // rax
  __int64 v22; // rbx
  unsigned __int64 v23; // r14
  __int64 v24; // r8
  __int64 v25; // r9
  void *v26; // r14
  LPBYTE v27; // rax
  size_t v28; // rbx
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h]
  char *v31; // [rsp+40h] [rbp-20h]
  _WORD v32[12]; // [rsp+48h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Src = v32;
  Type = 0;
  v31 = (char *)v32;
  v4 = a2;
  cbData = 0;
  v32[0] = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    return 2149285891LL;
  if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
    goto LABEL_45;
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
LABEL_11:
    if ( RegQueryValueExW(v4, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
      goto LABEL_9;
    v10 = cbData;
    if ( Type - 1 <= 1 )
    {
      v10 = cbData + 1;
    }
    else
    {
      if ( Type != 7 )
        goto LABEL_17;
      v10 = cbData + 2;
    }
    cbData = v10;
LABEL_17:
    v11 = 0;
    while ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11 + 1) != Type )
    {
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= 0xB )
      {
        v12 = 9;
        goto LABEL_22;
      }
    }
    v12 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11);
LABEL_22:
    v13 = *((_DWORD *)this + 1);
    if ( v13 != v12 && v13 != 9 && (v13 != 5 || v12 != 1) && (v13 != 1 || v12 != 5) && (v13 || v12 != 1) )
      goto LABEL_9;
    v14 = (LPBYTE *)((char *)this + 8);
    *((_DWORD *)this + 1) = v12;
    v15 = v10;
    v16 = (LPBYTE)*((_QWORD *)this + 1);
    v17 = *((_QWORD *)this + 2) - (_QWORD)v16;
    if ( v15 > v17 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v15,
                               v9,
                               &CRegSetting::s_typeMapping) )
      {
LABEL_32:
        v8 = -2147024882;
        goto LABEL_46;
      }
      memset_0(*((void **)this + 2), 0, v15 - v17);
      v16 = *v14;
    }
    *((_QWORD *)this + 2) = &v16[v15];
    v18 = RegQueryValueExW(v4, *((LPCWSTR *)this + 8), 0, &Type, *v14, &cbData) == 0;
    v21 = *v14;
    if ( !v18 )
    {
      v8 = -2147467259;
      *((_QWORD *)this + 2) = v21;
      goto LABEL_46;
    }
    v22 = cbData;
    v23 = *((_QWORD *)this + 2) - (_QWORD)v21;
    if ( cbData > v23 )
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)this + 8,
                              cbData,
                              v19,
                              v20) )
      {
        memset_0(*((void **)this + 2), 0, v22 - v23);
        *((_QWORD *)this + 2) = &(*v14)[v22];
      }
    }
    else
    {
      *((_QWORD *)this + 2) = &v21[cbData];
    }
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v8 = UtilExpandEnvironmentStrings((LPCWSTR)*v14);
      if ( v8 < 0 )
        goto LABEL_46;
      v26 = Src;
      v27 = *v14;
      cbData = 2 * ((v31 - (_BYTE *)Src) >> 1) + 2;
      v28 = cbData;
      *((_QWORD *)this + 2) = v27;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               v28,
                               v24,
                               v25) )
        goto LABEL_32;
      memcpy_0(*((void **)this + 2), v26, v28);
      *((_QWORD *)this + 2) += v28;
    }
    *(_BYTE *)this = 1;
LABEL_45:
    v8 = 0;
    goto LABEL_46;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(v4, *((LPCWSTR *)this + 4), 0, a3 | 0x20019, phkResult) )
  {
    v4 = hKey;
    goto LABEL_11;
  }
LABEL_9:
  v8 = -2147467259;
LABEL_46:
  if ( Src != v32 )
    operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000857c  mov     [rsp-28h+arg_0], rbx
0x140008581  push    rbp
0x140008582  push    rsi
0x140008583  push    rdi
0x140008584  push    r14
0x140008586  push    r15
0x140008588  mov     rbp, rsp
0x14000858b  sub     rsp, 60h
0x14000858f  lea     rax, [rbp+var_18]
0x140008593  mov     [rbp+hKey], 0
0x14000859b  mov     [rbp+Src], rax
0x14000859f  mov     ebx, r8d
0x1400085a2  lea     rax, [rbp+var_18]
0x1400085a6  mov     [rbp+Type], 0
0x1400085ad  mov     [rbp+var_20], rax
0x1400085b1  mov     r14, rdx
0x1400085b4  xor     eax, eax
0x1400085b6  mov     [rbp+cbData], 0
0x1400085bd  mov     [rbp+var_18], ax
0x1400085c1  mov     rsi, rcx
0x1400085c4  test    rdx, rdx
0x1400085c7  jnz     short loc_1400085D3
0x1400085c9  mov     eax, 80070057h
0x1400085ce  jmp     loc_14000884C
0x1400085d3  mov     rax, [rcx+48h]
0x1400085d7  cmp     [rcx+40h], rax
0x1400085db  jnz     short loc_1400085E7
0x1400085dd  mov     eax, 801B8003h
0x1400085e2  jmp     loc_14000884C
0x1400085e7  cmp     byte ptr [rcx+1], 0
0x1400085eb  jz      loc_14000881A
0x1400085f1  cmp     byte ptr [rcx], 0
0x1400085f4  jnz     loc_14000881A
0x1400085fa  mov     rax, [rcx+28h]
0x1400085fe  cmp     [rcx+20h], rax
0x140008602  jz      short loc_140008643
0x140008604  lea     rcx, [rbp+hKey]
0x140008608  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000860d  mov     rdx, [rsi+20h]; lpSubKey
0x140008611  or      ebx, 20019h
0x140008617  mov     r9d, ebx; samDesired
0x14000861a  mov     [rsp+60h+phkResult], rax; phkResult
0x14000861f  xor     r8d, r8d; ulOptions
0x140008622  mov     rcx, r14; hKey
0x140008625  call    cs:__imp_RegOpenKeyExW
0x14000862c  nop     dword ptr [rax+rax+00h]
0x140008631  test    eax, eax
0x140008633  jz      short loc_14000863F
0x140008635  mov     ebx, 80004005h
0x14000863a  jmp     loc_14000881C
0x14000863f  mov     r14, [rbp+hKey]
0x140008643  mov     rdx, [rsi+40h]; lpValueName
0x140008647  lea     rax, [rbp+cbData]
0x14000864b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140008650  lea     r9, [rbp+Type]; lpType
0x140008654  xor     r8d, r8d; lpReserved
0x140008657  mov     [rsp+60h+phkResult], 0; lpData
0x140008660  mov     rcx, r14; hKey
0x140008663  call    cs:__imp_RegQueryValueExW
0x14000866a  nop     dword ptr [rax+rax+00h]
0x14000866f  test    eax, eax
0x140008671  jnz     short loc_140008635
0x140008673  mov     edx, [rbp+Type]
0x140008676  lea     eax, [rdx-1]
0x140008679  cmp     eax, 1
0x14000867c  mov     eax, [rbp+cbData]
0x14000867f  jbe     short loc_14000868B
0x140008681  cmp     edx, 7
0x140008684  jnz     short loc_140008690
0x140008686  add     eax, 2
0x140008689  jmp     short loc_14000868D
0x14000868b  inc     eax
0x14000868d  mov     [rbp+cbData], eax
0x140008690  xor     ecx, ecx
0x140008692  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x140008699  cmp     [r9+rcx*8+4], edx
0x14000869e  jz      short loc_1400086AE
0x1400086a0  inc     ecx
0x1400086a2  cmp     ecx, 0Bh
0x1400086a5  jb      short loc_140008699
0x1400086a7  mov     ecx, 9
0x1400086ac  jmp     short loc_1400086B2
0x1400086ae  mov     ecx, [r9+rcx*8]
0x1400086b2  mov     edx, [rsi+4]
0x1400086b5  cmp     edx, ecx
0x1400086b7  jz      short loc_1400086E3
0x1400086b9  cmp     edx, 9
0x1400086bc  jz      short loc_1400086E3
0x1400086be  cmp     edx, 5
0x1400086c1  jnz     short loc_1400086C8
0x1400086c3  cmp     ecx, 1
0x1400086c6  jz      short loc_1400086E3
0x1400086c8  cmp     edx, 1
0x1400086cb  jnz     short loc_1400086D2
0x1400086cd  cmp     ecx, 5
0x1400086d0  jz      short loc_1400086E3
0x1400086d2  test    edx, edx
0x1400086d4  jnz     loc_140008635
0x1400086da  cmp     ecx, 1
0x1400086dd  jnz     loc_140008635
0x1400086e3  lea     rdi, [rsi+8]
0x1400086e7  mov     [rsi+4], ecx
0x1400086ea  mov     rbx, [rdi+8]
0x1400086ee  mov     r15d, eax
0x1400086f1  mov     rax, [rdi]
0x1400086f4  sub     rbx, rax
0x1400086f7  cmp     r15, rbx
0x1400086fa  jbe     short loc_140008729
0x1400086fc  mov     edx, r15d
0x1400086ff  mov     rcx, rdi
0x140008702  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x140008707  test    al, al
0x140008709  jnz     short loc_140008715
0x14000870b  mov     ebx, 8007000Eh
0x140008710  jmp     loc_14000881C
0x140008715  mov     rcx, [rdi+8]; void *
0x140008719  mov     r8, r15
0x14000871c  sub     r8, rbx; Size
0x14000871f  xor     edx, edx; Val
0x140008721  call    memset_0
0x140008726  mov     rax, [rdi]
0x140008729  add     rax, r15
0x14000872c  lea     r9, [rbp+Type]; lpType
0x140008730  mov     [rdi+8], rax
0x140008734  xor     r8d, r8d; lpReserved
0x140008737  mov     rdx, [rsi+40h]; lpValueName
0x14000873b  lea     rax, [rbp+cbData]
0x14000873f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140008744  mov     rcx, r14; hKey
0x140008747  mov     rax, [rdi]
0x14000874a  mov     [rsp+60h+phkResult], rax; lpData
0x14000874f  call    cs:__imp_RegQueryValueExW
0x140008756  nop     dword ptr [rax+rax+00h]
0x14000875b  test    eax, eax
0x14000875d  mov     rax, [rdi]
0x140008760  jz      short loc_140008770
0x140008762  mov     ebx, 80004005h
0x140008767  mov     [rdi+8], rax
0x14000876b  jmp     loc_14000881C
0x140008770  mov     r14, [rdi+8]
0x140008774  mov     ebx, [rbp+cbData]
0x140008777  sub     r14, rax
0x14000877a  cmp     rbx, r14
0x14000877d  ja      short loc_140008788
0x14000877f  add     rax, rbx
0x140008782  mov     [rdi+8], rax
0x140008786  jmp     short loc_1400087B2
0x140008788  mov     rdx, rbx
0x14000878b  mov     rcx, rdi
0x14000878e  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x140008793  test    al, al
0x140008795  jz      short loc_1400087B2
0x140008797  mov     rcx, [rdi+8]; void *
0x14000879b  mov     r8, rbx
0x14000879e  sub     r8, r14; Size
0x1400087a1  xor     edx, edx; Val
0x1400087a3  call    memset_0
0x1400087a8  mov     rcx, [rdi]
0x1400087ab  add     rcx, rbx
0x1400087ae  mov     [rdi+8], rcx
0x1400087b2  cmp     dword ptr [rsi+4], 5
0x1400087b6  jnz     short loc_140008817
0x1400087b8  mov     rcx, [rdi]; lpSrc
0x1400087bb  lea     rdx, [rbp+Src]
0x1400087bf  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1400087c4  mov     ebx, eax
0x1400087c6  test    eax, eax
0x1400087c8  js      short loc_14000881C
0x1400087ca  mov     r14, [rbp+Src]
0x1400087ce  mov     rax, [rbp+var_20]
0x1400087d2  sub     rax, r14
0x1400087d5  sar     rax, 1
0x1400087d8  lea     ecx, ds:2[rax*2]
0x1400087df  mov     rax, [rdi]
0x1400087e2  mov     ebx, ecx
0x1400087e4  mov     [rbp+cbData], ecx
0x1400087e7  sub     rbx, r14
0x1400087ea  add     rbx, r14
0x1400087ed  mov     [rdi+8], rax
0x1400087f1  mov     rdx, rbx
0x1400087f4  mov     rcx, rdi
0x1400087f7  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1400087fc  test    al, al
0x1400087fe  jz      loc_14000870B
0x140008804  mov     rcx, [rdi+8]; void *
0x140008808  mov     r8, rbx; Size
0x14000880b  mov     rdx, r14; Src
0x14000880e  call    memcpy_0
0x140008813  add     [rdi+8], rbx
0x140008817  mov     byte ptr [rsi], 1
0x14000881a  xor     ebx, ebx
0x14000881c  mov     rcx, [rbp+Src]; void *
0x140008820  lea     rax, [rbp+var_18]
0x140008824  cmp     rcx, rax
0x140008827  jz      short loc_140008835
0x140008829  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008830  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008835  mov     rcx, [rbp+hKey]; hKey
0x140008839  test    rcx, rcx
0x14000883c  jz      short loc_14000884A
0x14000883e  call    cs:__imp_RegCloseKey
0x140008845  nop     dword ptr [rax+rax+00h]
0x14000884a  mov     eax, ebx
0x14000884c  mov     rbx, [rsp+60h+arg_0]
0x140008854  add     rsp, 60h
0x140008858  pop     r15
0x14000885a  pop     r14
0x14000885c  pop     rdi
0x14000885d  pop     rsi
0x14000885e  pop     rbp
0x14000885f  retn
```
