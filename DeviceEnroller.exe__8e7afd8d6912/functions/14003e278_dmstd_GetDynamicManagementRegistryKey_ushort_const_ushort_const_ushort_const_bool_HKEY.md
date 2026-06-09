# dmstd::GetDynamicManagementRegistryKey(ushort const *,ushort const *,ushort const *,bool,HKEY__ * *)

- ea: `0x14003e278`
- end: `0x14003e66a`
- name: `?GetDynamicManagementRegistryKey@dmstd@@YAJPEBG00_NPEAPEAUHKEY__@@@Z`
- size: `1010`
- prototype: `__int64 __usercall@<rax>(dmstd *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, bool, HKEY *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003a114`
- `0x14004002c`
- `0x140040e10`
- `0x140041150`
- `0x140041710`
- `0x140043cc8`
- `0x140044720`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14001e784`
- `0x14001ed14`
- `0x14003d044`
- `0x14003d0d0`
- `0x14003d1d4`
- `0x14003e278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e61f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003e61f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14003e5e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14003e5e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall dmstd::GetDynamicManagementRegistryKey(
        dmstd *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        PHKEY phkResult)
{
  char v5; // r12
  __int64 v9; // rdx
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  const WCHAR *v19; // rdx
  LSTATUS Key; // eax
  unsigned int v21; // ebx
  LSTATUS v22; // eax
  int dwOptions; // [rsp+20h] [rbp-158h]
  LPCWSTR lpSubKey[2]; // [rsp+58h] [rbp-120h] BYREF
  __int128 v25; // [rsp+68h] [rbp-110h]
  __int128 v26; // [rsp+78h] [rbp-100h] BYREF
  __int128 v27; // [rsp+88h] [rbp-F0h]
  __int128 v28; // [rsp+98h] [rbp-E0h] BYREF
  __int128 v29; // [rsp+A8h] [rbp-D0h]
  __int128 v30; // [rsp+B8h] [rbp-C0h] BYREF
  __int128 v31; // [rsp+C8h] [rbp-B0h]
  __int128 v32; // [rsp+D8h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+E8h] [rbp-90h]
  _OWORD v34[2]; // [rsp+F8h] [rbp-80h] BYREF
  _OWORD Src[2]; // [rsp+118h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v5 = (char)a4;
  if ( !this )
  {
    v9 = 91;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\helpers.cpp",
      (const char *)0x80070057LL,
      dwOptions);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v9 = 92;
    goto LABEL_3;
  }
  if ( !phkResult )
  {
    v9 = 93;
    goto LABEL_3;
  }
  *phkResult = 0;
  memset(Src, 0, sizeof(Src));
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( qword_14007E6B8[v12] );
  std::wstring::_Construct<1,unsigned short const *>((char **)Src, qword_14007E6B8, v12);
  v13 = std::wstring::append(Src, (void *)L"\\");
  v30 = 0;
  v31 = 0;
  v30 = *(_OWORD *)v13;
  v31 = *(_OWORD *)(v13 + 16);
  *(_QWORD *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 24) = 7;
  *(_WORD *)v13 = 0;
  v14 = std::wstring::append(&v30, this);
  v28 = 0;
  v29 = 0;
  v28 = *(_OWORD *)v14;
  v29 = *(_OWORD *)(v14 + 16);
  *(_QWORD *)(v14 + 16) = 0;
  *(_QWORD *)(v14 + 24) = 7;
  *(_WORD *)v14 = 0;
  v15 = std::wstring::append(&v28, (void *)L"\\");
  *(_OWORD *)lpSubKey = 0;
  v25 = 0;
  *(_OWORD *)lpSubKey = *(_OWORD *)v15;
  v25 = *(_OWORD *)(v15 + 16);
  *(_QWORD *)(v15 + 16) = 0;
  *(_QWORD *)(v15 + 24) = 7;
  *(_WORD *)v15 = 0;
  std::wstring::~wstring((char **)&v28);
  std::wstring::~wstring((char **)&v30);
  std::wstring::~wstring((char **)Src);
  if ( a2 )
  {
    v26 = 0;
    v27 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v26, L"User", 4u);
    v16 = std::wstring::append(&v26, (void *)L"\\");
    v32 = 0;
    v33 = 0;
    v32 = *(_OWORD *)v16;
    v33 = *(_OWORD *)(v16 + 16);
    *(_QWORD *)(v16 + 16) = 0;
    *(_QWORD *)(v16 + 24) = 7;
    *(_WORD *)v16 = 0;
    v17 = std::wstring::append(&v32, a2);
    v34[0] = *(_OWORD *)v17;
    v34[1] = *(_OWORD *)(v17 + 16);
    *(_QWORD *)(v17 + 16) = 0;
    *(_QWORD *)(v17 + 24) = 7;
    *(_WORD *)v17 = 0;
    std::wstring::append(lpSubKey);
    std::wstring::~wstring((char **)v34);
    std::wstring::~wstring((char **)&v32);
    std::wstring::~wstring((char **)&v26);
  }
  else
  {
    std::wstring::append(lpSubKey, (void *)L"Device");
  }
  v26 = 0;
  v27 = 0;
  do
    ++v11;
  while ( a3[v11] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v26, a3, v11);
  std::operator+<unsigned short>(v34, v18, &v26);
  std::wstring::append(lpSubKey);
  std::wstring::~wstring((char **)v34);
  std::wstring::~wstring((char **)&v26);
  v19 = (const WCHAR *)lpSubKey;
  if ( v5 )
  {
    if ( *((_QWORD *)&v25 + 1) > 7u )
      v19 = lpSubKey[0];
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
    v21 = Key;
    if ( Key > 0 )
      v21 = (unsigned __int16)Key | 0x80070000;
  }
  else
  {
    if ( *((_QWORD *)&v25 + 1) > 7u )
      v19 = lpSubKey[0];
    v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0xF003Fu, phkResult);
    v21 = v22;
    if ( v22 > 0 )
      v21 = (unsigned __int16)v22 | 0x80070000;
  }
  std::wstring::~wstring((char **)lpSubKey);
  return v21;
}

```

## disassembly

```asm
0x14003e278  push    rbx
0x14003e27a  push    rsi
0x14003e27b  push    rdi
0x14003e27c  push    r12
0x14003e27e  push    r13
0x14003e280  push    r14
0x14003e282  push    r15
0x14003e284  sub     rsp, 140h
0x14003e28b  mov     rax, cs:__security_cookie
0x14003e292  xor     rax, rsp
0x14003e295  mov     [rsp+178h+var_40], rax
0x14003e29d  mov     r12b, r9b
0x14003e2a0  mov     rsi, r8
0x14003e2a3  mov     r15, rdx
0x14003e2a6  mov     r14, rcx
0x14003e2a9  mov     rdi, [rsp+178h+arg_20]
0x14003e2b1  xor     r13d, r13d
0x14003e2b4  test    rcx, rcx
0x14003e2b7  jnz     short loc_14003E2DF
0x14003e2b9  lea     edx, [rcx+5Bh]; void *
0x14003e2bc  mov     ebx, 80070057h
0x14003e2c1  mov     rcx, [rsp+178h]; this
0x14003e2c9  mov     r9d, ebx; char *
0x14003e2cc  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x14003e2d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003e2d8  mov     eax, ebx
0x14003e2da  jmp     loc_14003E646
0x14003e2df  test    rsi, rsi
0x14003e2e2  jnz     short loc_14003E2E9
0x14003e2e4  lea     edx, [rsi+5Ch]
0x14003e2e7  jmp     short loc_14003E2BC
0x14003e2e9  test    rdi, rdi
0x14003e2ec  jnz     short loc_14003E2F3
0x14003e2ee  lea     edx, [rdi+5Dh]
0x14003e2f1  jmp     short loc_14003E2BC
0x14003e2f3  mov     [rdi], r13
0x14003e2f6  mov     rdx, cs:qword_14007E6B8
0x14003e2fd  xorps   xmm0, xmm0
0x14003e300  movups  [rsp+178h+Src], xmm0
0x14003e308  xorps   xmm1, xmm1
0x14003e30b  movdqu  [rsp+178h+var_50], xmm1
0x14003e314  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003e318  mov     r8, rbx
0x14003e31b  inc     r8
0x14003e31e  cmp     [rdx+r8*2], r13w
0x14003e323  jnz     short loc_14003E31B
0x14003e325  lea     rcx, [rsp+178h+Src]
0x14003e32d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003e332  nop
0x14003e333  lea     rdx, asc_140061150; "\\"
0x14003e33a  lea     rcx, [rsp+178h+Src]; Src
0x14003e342  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003e347  xorps   xmm0, xmm0
0x14003e34a  movups  [rsp+178h+var_C0], xmm0
0x14003e352  xorps   xmm1, xmm1
0x14003e355  movdqu  [rsp+178h+var_B0], xmm1
0x14003e35e  movups  xmm0, xmmword ptr [rax]
0x14003e361  movups  [rsp+178h+var_C0], xmm0
0x14003e369  movups  xmm1, xmmword ptr [rax+10h]
0x14003e36d  movups  [rsp+178h+var_B0], xmm1
0x14003e375  mov     [rax+10h], r13
0x14003e379  mov     qword ptr [rax+18h], 7
0x14003e381  mov     [rax], r13w
0x14003e385  mov     rdx, r14; void *
0x14003e388  lea     rcx, [rsp+178h+var_C0]; Src
0x14003e390  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003e395  xorps   xmm0, xmm0
0x14003e398  movups  [rsp+178h+var_E0], xmm0
0x14003e3a0  xorps   xmm1, xmm1
0x14003e3a3  movdqu  [rsp+178h+var_D0], xmm1
0x14003e3ac  movups  xmm0, xmmword ptr [rax]
0x14003e3af  movups  [rsp+178h+var_E0], xmm0
0x14003e3b7  movups  xmm1, xmmword ptr [rax+10h]
0x14003e3bb  movups  [rsp+178h+var_D0], xmm1
0x14003e3c3  mov     [rax+10h], r13
0x14003e3c7  mov     r14d, 7
0x14003e3cd  mov     [rax+18h], r14
0x14003e3d1  mov     [rax], r13w
0x14003e3d5  lea     rdx, asc_140061150; "\\"
0x14003e3dc  lea     rcx, [rsp+178h+var_E0]; Src
0x14003e3e4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003e3e9  xorps   xmm0, xmm0
0x14003e3ec  movups  xmmword ptr [rsp+178h+lpSubKey], xmm0
0x14003e3f1  xorps   xmm1, xmm1
0x14003e3f4  movdqu  [rsp+178h+var_110], xmm1
0x14003e3fa  movups  xmm0, xmmword ptr [rax]
0x14003e3fd  movups  xmmword ptr [rsp+178h+lpSubKey], xmm0
0x14003e402  movups  xmm1, xmmword ptr [rax+10h]
0x14003e406  movups  [rsp+178h+var_110], xmm1
0x14003e40b  mov     [rax+10h], r13
0x14003e40f  mov     [rax+18h], r14
0x14003e413  mov     [rax], r13w
0x14003e417  lea     rcx, [rsp+178h+var_E0]
0x14003e41f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e424  nop
0x14003e425  lea     rcx, [rsp+178h+var_C0]
0x14003e42d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e432  nop
0x14003e433  lea     rcx, [rsp+178h+Src]
0x14003e43b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e440  test    r15, r15
0x14003e443  jz      loc_14003E52C
0x14003e449  xorps   xmm0, xmm0
0x14003e44c  movups  [rsp+178h+var_100], xmm0
0x14003e451  xorps   xmm1, xmm1
0x14003e454  movdqu  [rsp+178h+var_F0], xmm1
0x14003e45d  lea     r8d, [r14-3]
0x14003e461  lea     rdx, aUser; "User"
0x14003e468  lea     rcx, [rsp+178h+var_100]
0x14003e46d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003e472  nop
0x14003e473  lea     rdx, asc_140061150; "\\"
0x14003e47a  lea     rcx, [rsp+178h+var_100]; Src
0x14003e47f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003e484  xorps   xmm0, xmm0
0x14003e487  movups  [rsp+178h+var_A0], xmm0
0x14003e48f  xorps   xmm1, xmm1
0x14003e492  movdqu  [rsp+178h+var_90], xmm1
0x14003e49b  movups  xmm0, xmmword ptr [rax]
0x14003e49e  movups  [rsp+178h+var_A0], xmm0
0x14003e4a6  movups  xmm1, xmmword ptr [rax+10h]
0x14003e4aa  movups  [rsp+178h+var_90], xmm1
0x14003e4b2  mov     [rax+10h], r13
0x14003e4b6  mov     [rax+18h], r14
0x14003e4ba  mov     [rax], r13w
0x14003e4be  mov     rdx, r15; void *
0x14003e4c1  lea     rcx, [rsp+178h+var_A0]; Src
0x14003e4c9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003e4ce  movups  xmm0, xmmword ptr [rax]
0x14003e4d1  movups  [rsp+178h+var_80], xmm0
0x14003e4d9  movups  xmm1, xmmword ptr [rax+10h]
0x14003e4dd  movups  [rsp+178h+var_70], xmm1
0x14003e4e5  mov     [rax+10h], r13
0x14003e4e9  mov     [rax+18h], r14
0x14003e4ed  mov     [rax], r13w
0x14003e4f1  lea     rdx, [rsp+178h+var_80]
0x14003e4f9  lea     rcx, [rsp+178h+lpSubKey]; Src
0x14003e4fe  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14003e503  nop
0x14003e504  lea     rcx, [rsp+178h+var_80]
0x14003e50c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e511  nop
0x14003e512  lea     rcx, [rsp+178h+var_A0]
0x14003e51a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e51f  nop
0x14003e520  lea     rcx, [rsp+178h+var_100]
0x14003e525  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e52a  jmp     short loc_14003E53D
0x14003e52c  lea     rdx, aDevice; "Device"
0x14003e533  lea     rcx, [rsp+178h+lpSubKey]; Src
0x14003e538  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14003e53d  xorps   xmm0, xmm0
0x14003e540  movups  [rsp+178h+var_100], xmm0
0x14003e545  xorps   xmm1, xmm1
0x14003e548  movdqu  [rsp+178h+var_F0], xmm1
0x14003e551  inc     rbx
0x14003e554  cmp     [rsi+rbx*2], r13w
0x14003e559  jnz     short loc_14003E551
0x14003e55b  mov     r8, rbx
0x14003e55e  mov     rdx, rsi
0x14003e561  lea     rcx, [rsp+178h+var_100]
0x14003e566  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003e56b  nop
0x14003e56c  lea     r8, [rsp+178h+var_100]
0x14003e571  lea     rcx, [rsp+178h+var_80]
0x14003e579  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x14003e57e  nop
0x14003e57f  mov     rdx, rax
0x14003e582  lea     rcx, [rsp+178h+lpSubKey]; Src
0x14003e587  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14003e58c  nop
0x14003e58d  lea     rcx, [rsp+178h+var_80]
0x14003e595  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e59a  nop
0x14003e59b  lea     rcx, [rsp+178h+var_100]
0x14003e5a0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e5a5  lea     rdx, [rsp+178h+lpSubKey]
0x14003e5aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003e5b1  test    r12b, r12b
0x14003e5b4  jz      short loc_14003E606
0x14003e5b6  cmp     qword ptr [rsp+178h+var_110+8], r14
0x14003e5bb  cmova   rdx, [rsp+178h+lpSubKey]; lpSubKey
0x14003e5c1  mov     [rsp+178h+lpdwDisposition], r13; lpdwDisposition
0x14003e5c6  mov     [rsp+178h+phkResult], rdi; phkResult
0x14003e5cb  mov     [rsp+178h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14003e5d0  mov     [rsp+178h+samDesired], 0F003Fh; samDesired
0x14003e5d8  mov     [rsp+178h+dwOptions], r13d; dwOptions
0x14003e5dd  xor     r9d, r9d; lpClass
0x14003e5e0  xor     r8d, r8d; Reserved
0x14003e5e3  call    cs:__imp_RegCreateKeyExW
0x14003e5e9  mov     ebx, eax
0x14003e5eb  test    eax, eax
0x14003e5ed  jle     short loc_14003E5F8
0x14003e5ef  movzx   ebx, ax
0x14003e5f2  or      ebx, 80070000h
0x14003e5f8  lea     rcx, [rsp+178h+lpSubKey]
0x14003e5fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e602  mov     eax, ebx
0x14003e604  jmp     short loc_14003E646
0x14003e606  cmp     qword ptr [rsp+178h+var_110+8], r14
0x14003e60b  cmova   rdx, [rsp+178h+lpSubKey]; lpSubKey
0x14003e611  mov     qword ptr [rsp+178h+dwOptions], rdi; phkResult
0x14003e616  mov     r9d, 0F003Fh; samDesired
0x14003e61c  xor     r8d, r8d; ulOptions
0x14003e61f  call    cs:__imp_RegOpenKeyExW
0x14003e625  mov     ebx, eax
0x14003e627  test    eax, eax
0x14003e629  jle     short loc_14003E634
0x14003e62b  movzx   ebx, ax
0x14003e62e  or      ebx, 80070000h
0x14003e634  lea     rcx, [rsp+178h+lpSubKey]
0x14003e639  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003e63e  mov     eax, ebx
0x14003e640  jmp     short loc_14003E646
0x14003e642  mov     eax, [rsp+178h+var_128]
0x14003e646  mov     rcx, [rsp+178h+var_40]
0x14003e64e  xor     rcx, rsp; StackCookie
0x14003e651  call    __security_check_cookie
0x14003e656  add     rsp, 140h
0x14003e65d  pop     r15
0x14003e65f  pop     r14
0x14003e661  pop     r13
0x14003e663  pop     r12
0x14003e665  pop     rdi
0x14003e666  pop     rsi
0x14003e667  pop     rbx
0x14003e668  retn
```
