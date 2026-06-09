# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x140008620`
- end: `0x1400088ec`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `716`
- prototype: `int(CRegSetting *__hidden this, HKEY, unsigned int)`
- caller_count: `13`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x14000bcf8`
- `0x140017680`
- `0x14001eb14`
- `0x140030150`
- `0x1400302d0`
- `0x1400380cc`
- `0x1400384dc`
- `0x14003f174`
- `0x140042250`
- `0x14004986c`
- `0x1400529d8`
- `0x140053360`
- `0x140054344`

## callees

- `0x140002728`
- `0x1400030a8`
- `0x140005468`
- `0x140008620`
- `0x14000be58`
- `0x14000cb9c`
- `0x14005b7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400088d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400088d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400086c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400086c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400087e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400087e7`

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
    while ( CRegSetting::s_typeMapping[2 * v11 + 1] != Type )
    {
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= 0xB )
      {
        v12 = 9;
        goto LABEL_22;
      }
    }
    v12 = CRegSetting::s_typeMapping[2 * v11];
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
                               CRegSetting::s_typeMapping) )
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
0x140008620  mov     [rsp-28h+arg_0], rbx
0x140008625  push    rbp
0x140008626  push    rsi
0x140008627  push    rdi
0x140008628  push    r14
0x14000862a  push    r15
0x14000862c  mov     rbp, rsp
0x14000862f  sub     rsp, 60h
0x140008633  lea     rax, [rbp+var_18]
0x140008637  mov     [rbp+hKey], 0
0x14000863f  mov     [rbp+Src], rax
0x140008643  mov     ebx, r8d
0x140008646  lea     rax, [rbp+var_18]
0x14000864a  mov     [rbp+Type], 0
0x140008651  mov     [rbp+var_20], rax
0x140008655  mov     r14, rdx
0x140008658  xor     eax, eax
0x14000865a  mov     [rbp+cbData], 0
0x140008661  mov     [rbp+var_18], ax
0x140008665  mov     rsi, rcx
0x140008668  test    rdx, rdx
0x14000866b  jnz     short loc_140008677
0x14000866d  mov     eax, 80070057h
0x140008672  jmp     loc_1400088D8
0x140008677  mov     rax, [rcx+48h]
0x14000867b  cmp     [rcx+40h], rax
0x14000867f  jnz     short loc_14000868B
0x140008681  mov     eax, 801B8003h
0x140008686  jmp     loc_1400088D8
0x14000868b  cmp     byte ptr [rcx+1], 0
0x14000868f  jz      loc_1400088AC
0x140008695  cmp     byte ptr [rcx], 0
0x140008698  jnz     loc_1400088AC
0x14000869e  mov     rax, [rcx+28h]
0x1400086a2  cmp     [rcx+20h], rax
0x1400086a6  jz      short loc_1400086E1
0x1400086a8  lea     rcx, [rbp+hKey]
0x1400086ac  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400086b1  mov     rdx, [rsi+20h]; lpSubKey
0x1400086b5  or      ebx, 20019h
0x1400086bb  mov     r9d, ebx; samDesired
0x1400086be  mov     [rsp+60h+phkResult], rax; phkResult
0x1400086c3  xor     r8d, r8d; ulOptions
0x1400086c6  mov     rcx, r14; hKey
0x1400086c9  call    cs:__imp_RegOpenKeyExW
0x1400086cf  test    eax, eax
0x1400086d1  jz      short loc_1400086DD
0x1400086d3  mov     ebx, 80004005h
0x1400086d8  jmp     loc_1400088AE
0x1400086dd  mov     r14, [rbp+hKey]
0x1400086e1  mov     rdx, [rsi+40h]; lpValueName
0x1400086e5  lea     rax, [rbp+cbData]
0x1400086e9  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1400086ee  lea     r9, [rbp+Type]; lpType
0x1400086f2  xor     r8d, r8d; lpReserved
0x1400086f5  mov     [rsp+60h+phkResult], 0; lpData
0x1400086fe  mov     rcx, r14; hKey
0x140008701  call    cs:__imp_RegQueryValueExW
0x140008707  test    eax, eax
0x140008709  jnz     short loc_1400086D3
0x14000870b  mov     edx, [rbp+Type]
0x14000870e  lea     eax, [rdx-1]
0x140008711  cmp     eax, 1
0x140008714  mov     eax, [rbp+cbData]
0x140008717  jbe     short loc_140008723
0x140008719  cmp     edx, 7
0x14000871c  jnz     short loc_140008728
0x14000871e  add     eax, 2
0x140008721  jmp     short loc_140008725
0x140008723  inc     eax
0x140008725  mov     [rbp+cbData], eax
0x140008728  xor     ecx, ecx
0x14000872a  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x140008731  cmp     [r9+rcx*8+4], edx
0x140008736  jz      short loc_140008746
0x140008738  inc     ecx
0x14000873a  cmp     ecx, 0Bh
0x14000873d  jb      short loc_140008731
0x14000873f  mov     ecx, 9
0x140008744  jmp     short loc_14000874A
0x140008746  mov     ecx, [r9+rcx*8]
0x14000874a  mov     edx, [rsi+4]
0x14000874d  cmp     edx, ecx
0x14000874f  jz      short loc_14000877B
0x140008751  cmp     edx, 9
0x140008754  jz      short loc_14000877B
0x140008756  cmp     edx, 5
0x140008759  jnz     short loc_140008760
0x14000875b  cmp     ecx, 1
0x14000875e  jz      short loc_14000877B
0x140008760  cmp     edx, 1
0x140008763  jnz     short loc_14000876A
0x140008765  cmp     ecx, 5
0x140008768  jz      short loc_14000877B
0x14000876a  test    edx, edx
0x14000876c  jnz     loc_1400086D3
0x140008772  cmp     ecx, 1
0x140008775  jnz     loc_1400086D3
0x14000877b  lea     rdi, [rsi+8]
0x14000877f  mov     [rsi+4], ecx
0x140008782  mov     rbx, [rdi+8]
0x140008786  mov     r15d, eax
0x140008789  mov     rax, [rdi]
0x14000878c  sub     rbx, rax
0x14000878f  cmp     r15, rbx
0x140008792  jbe     short loc_1400087C1
0x140008794  mov     edx, r15d
0x140008797  mov     rcx, rdi
0x14000879a  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000879f  test    al, al
0x1400087a1  jnz     short loc_1400087AD
0x1400087a3  mov     ebx, 8007000Eh
0x1400087a8  jmp     loc_1400088AE
0x1400087ad  mov     rcx, [rdi+8]; void *
0x1400087b1  mov     r8, r15
0x1400087b4  sub     r8, rbx; Size
0x1400087b7  xor     edx, edx; Val
0x1400087b9  call    memset_0
0x1400087be  mov     rax, [rdi]
0x1400087c1  add     rax, r15
0x1400087c4  lea     r9, [rbp+Type]; lpType
0x1400087c8  mov     [rdi+8], rax
0x1400087cc  xor     r8d, r8d; lpReserved
0x1400087cf  mov     rdx, [rsi+40h]; lpValueName
0x1400087d3  lea     rax, [rbp+cbData]
0x1400087d7  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1400087dc  mov     rcx, r14; hKey
0x1400087df  mov     rax, [rdi]
0x1400087e2  mov     [rsp+60h+phkResult], rax; lpData
0x1400087e7  call    cs:__imp_RegQueryValueExW
0x1400087ed  test    eax, eax
0x1400087ef  mov     rax, [rdi]
0x1400087f2  jz      short loc_140008802
0x1400087f4  mov     ebx, 80004005h
0x1400087f9  mov     [rdi+8], rax
0x1400087fd  jmp     loc_1400088AE
0x140008802  mov     r14, [rdi+8]
0x140008806  mov     ebx, [rbp+cbData]
0x140008809  sub     r14, rax
0x14000880c  cmp     rbx, r14
0x14000880f  ja      short loc_14000881A
0x140008811  add     rax, rbx
0x140008814  mov     [rdi+8], rax
0x140008818  jmp     short loc_140008844
0x14000881a  mov     rdx, rbx
0x14000881d  mov     rcx, rdi
0x140008820  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x140008825  test    al, al
0x140008827  jz      short loc_140008844
0x140008829  mov     rcx, [rdi+8]; void *
0x14000882d  mov     r8, rbx
0x140008830  sub     r8, r14; Size
0x140008833  xor     edx, edx; Val
0x140008835  call    memset_0
0x14000883a  mov     rcx, [rdi]
0x14000883d  add     rcx, rbx
0x140008840  mov     [rdi+8], rcx
0x140008844  cmp     dword ptr [rsi+4], 5
0x140008848  jnz     short loc_1400088A9
0x14000884a  mov     rcx, [rdi]; lpSrc
0x14000884d  lea     rdx, [rbp+Src]
0x140008851  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140008856  mov     ebx, eax
0x140008858  test    eax, eax
0x14000885a  js      short loc_1400088AE
0x14000885c  mov     r14, [rbp+Src]
0x140008860  mov     rax, [rbp+var_20]
0x140008864  sub     rax, r14
0x140008867  sar     rax, 1
0x14000886a  lea     ecx, ds:2[rax*2]
0x140008871  mov     rax, [rdi]
0x140008874  mov     ebx, ecx
0x140008876  mov     [rbp+cbData], ecx
0x140008879  sub     rbx, r14
0x14000887c  add     rbx, r14
0x14000887f  mov     [rdi+8], rax
0x140008883  mov     rdx, rbx
0x140008886  mov     rcx, rdi
0x140008889  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000888e  test    al, al
0x140008890  jz      loc_1400087A3
0x140008896  mov     rcx, [rdi+8]; void *
0x14000889a  mov     r8, rbx; Size
0x14000889d  mov     rdx, r14; Src
0x1400088a0  call    memcpy_0
0x1400088a5  add     [rdi+8], rbx
0x1400088a9  mov     byte ptr [rsi], 1
0x1400088ac  xor     ebx, ebx
0x1400088ae  mov     rcx, [rbp+Src]; void *
0x1400088b2  lea     rax, [rbp+var_18]
0x1400088b6  cmp     rcx, rax
0x1400088b9  jz      short loc_1400088C7
0x1400088bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400088c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400088c7  mov     rcx, [rbp+hKey]; hKey
0x1400088cb  test    rcx, rcx
0x1400088ce  jz      short loc_1400088D6
0x1400088d0  call    cs:__imp_RegCloseKey
0x1400088d6  mov     eax, ebx
0x1400088d8  mov     rbx, [rsp+60h+arg_0]
0x1400088e0  add     rsp, 60h
0x1400088e4  pop     r15
0x1400088e6  pop     r14
0x1400088e8  pop     rdi
0x1400088e9  pop     rsi
0x1400088ea  pop     rbp
0x1400088eb  retn
```
