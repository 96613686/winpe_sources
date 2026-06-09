# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x1800127d0`
- end: `0x180012c12`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `1090`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d144`
- `0x18000f5dc`
- `0x180013890`
- `0x180018bc4`

## callees

- `0x180001870`
- `0x180001f60`
- `0x1800027bd`
- `0x180003bb8`
- `0x180003be0`
- `0x18000b534`
- `0x18000c5c0`
- `0x1800111f8`
- `0x180011394`
- `0x1800127d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001283a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001283a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180012911`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180012911`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180012b32`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180012b32`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180012b21`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180012b21`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180012ae6`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180012ae6`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180012a06`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180012a06`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180012a49`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180012a49`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *this)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // r8
  char **v5; // rcx
  unsigned __int64 v6; // rdx
  char *v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  const unsigned __int16 *v12; // rsi
  unsigned __int64 v13; // rdx
  char *v14; // r14
  __int64 v15; // rbx
  HANDLE FirstVolumeW; // rsi
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  WCHAR *v21; // rcx
  bool v22; // r8
  DWORD cchReturnLength; // [rsp+20h] [rbp-C88h] BYREF
  HANDLE v24; // [rsp+28h] [rbp-C80h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-C78h] BYREF
  WCHAR szVolumeName[4]; // [rsp+240h] [rbp-A68h] BYREF
  char v27; // [rsp+248h] [rbp-A60h] BYREF
  __int16 v28; // [rsp+446h] [rbp-862h]
  WCHAR szVolumePathNames[1040]; // [rsp+450h] [rbp-858h] BYREF

  v2 = *((_QWORD *)this + 1);
  v3 = *(_QWORD *)this;
  if ( *(_QWORD *)this != v2 )
  {
    do
    {
      std::wstring::~wstring(v3 + 32);
      std::wstring::~wstring(v3);
      v3 += 64;
    }
    while ( v3 != v2 );
    *((_QWORD *)this + 1) = *(_QWORD *)this;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  v5 = (char **)((char *)this + 48);
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( v6 > *((_QWORD *)this + 9) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v5, v6, v4, Buffer);
  }
  else
  {
    if ( *((_QWORD *)this + 9) <= 7u )
      v7 = (char *)this + 48;
    else
      v7 = *v5;
    *((_QWORD *)this + 8) = v6;
    v8 = 2 * v6;
    memmove_0(v7, Buffer, 2 * v6);
    *(_WORD *)&v7[v8] = 0;
  }
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\\\", &word_18002D338, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &word_18002D338, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\DriverStores\\BSPDRIVERS",
    L"\\\\?\\GLOBALROOT\\DriverStores\\BSPDRIVERS",
    1);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\DriverStore\\Nodes",
    L"\\\\?\\GLOBALROOT\\DriverStore\\Nodes",
    1);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
    ATL::AtlThrowLastWin32();
  v10 = -1;
  do
    ++v10;
  while ( Buffer[v10] );
  if ( v10 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v10 - 1] != 92 )
  {
    if ( v10 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v10] = 92;
    v11 = 2 * v10 + 2;
    if ( v11 >= 0x20A )
      ((void (__noreturn *)(void))_report_rangecheckfailure)();
    *(WCHAR *)((char *)Buffer + v11) = 0;
  }
  v12 = (const unsigned __int16 *)((char *)this + 80);
  v13 = -1;
  do
    ++v13;
  while ( Buffer[v13] );
  if ( v13 > *((_QWORD *)this + 13) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char *)this + 80,
      v13,
      v9,
      Buffer);
  }
  else
  {
    if ( *((_QWORD *)this + 13) <= 7u )
      v14 = (char *)this + 80;
    else
      v14 = *(char **)v12;
    *((_QWORD *)this + 12) = v13;
    v15 = 2 * v13;
    memmove_0(v14, Buffer, 2 * v13);
    *(_WORD *)&v14[v15] = 0;
  }
  if ( *((_QWORD *)this + 13) > 7u )
    v12 = *(const unsigned __int16 **)v12;
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v12, 1);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v24 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    cchReturnLength = 0;
    do
    {
      v28 = 0;
      v17 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v17) = szVolumePathNames[0] != 0;
      v19 = -1;
      do
        ++v19;
      while ( szVolumeName[v19] );
      if ( v19 && Buffer[v19 + 263] == 92 )
      {
        v20 = 2 * v19 - 2;
        if ( v20 >= 0x208 )
          _report_rangecheckfailure(v20, v18);
        *(WCHAR *)((char *)szVolumeName + v20) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v21 = (WCHAR *)&v27, szVolumeName[3] != 92) )
      {
        v21 = szVolumeName;
      }
      if ( QueryDosDeviceW(v21, Buffer, 0x104u) )
      {
        if ( v17 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, Buffer, szVolumePathNames, 1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(this, Buffer, v22);
      }
    }
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  }
  catch ( ... )
  {
    FindVolumeClose(v24);
    throw;
  }
  FindVolumeClose(FirstVolumeW);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
    this,
    L"\\Device\\LanmanRedirector\\",
    L"\\\\",
    0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\Mup\\", L"\\\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\Device\\vmsmb\\", L"\\\\?\\VMSMB\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\GLOBAL??\\", L"\\\\?\\", 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\\\", L"\\\\", 0);
  *((_BYTE *)this + 112) = 1;
}

```

## disassembly

```asm
0x1800127d0  mov     [rsp+arg_8], rbx
0x1800127d5  mov     [rsp+arg_10], rsi
0x1800127da  push    rdi
0x1800127db  push    r12
0x1800127dd  push    r13
0x1800127df  push    r14
0x1800127e1  push    r15
0x1800127e3  sub     rsp, 0C80h
0x1800127ea  mov     rax, cs:__security_cookie
0x1800127f1  xor     rax, rsp
0x1800127f4  mov     [rsp+0CA8h+var_38], rax
0x1800127fc  mov     rdi, rcx
0x1800127ff  mov     rsi, [rcx+8]
0x180012803  mov     rbx, [rcx]
0x180012806  cmp     rbx, rsi
0x180012809  jz      short loc_18001282C
0x18001280b  lea     rcx, [rbx+20h]
0x18001280f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012814  mov     rcx, rbx
0x180012817  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001281c  add     rbx, 40h ; '@'
0x180012820  cmp     rbx, rsi
0x180012823  jnz     short loc_18001280B
0x180012825  mov     rax, [rdi]
0x180012828  mov     [rdi+8], rax
0x18001282c  mov     r14d, 104h
0x180012832  mov     edx, r14d; uSize
0x180012835  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x18001283a  call    cs:__imp_GetSystemDirectoryW
0x180012840  xor     r15d, r15d
0x180012843  test    eax, eax
0x180012845  jz      loc_180012BE8
0x18001284b  lea     rcx, [rdi+30h]
0x18001284f  lea     rax, [rsp+0CA8h+Buffer]
0x180012854  or      r13, 0FFFFFFFFFFFFFFFFh
0x180012858  mov     rdx, r13
0x18001285b  inc     rdx
0x18001285e  cmp     [rax+rdx*2], r15w
0x180012863  jnz     short loc_18001285B
0x180012865  cmp     rdx, [rcx+18h]
0x180012869  ja      short loc_180012899
0x18001286b  cmp     qword ptr [rcx+18h], 7
0x180012870  jbe     short loc_180012877
0x180012872  mov     rsi, [rcx]
0x180012875  jmp     short loc_18001287A
0x180012877  mov     rsi, rcx
0x18001287a  mov     [rcx+10h], rdx
0x18001287e  lea     rbx, [rdx+rdx]
0x180012882  mov     r8, rbx; Size
0x180012885  lea     rdx, [rsp+0CA8h+Buffer]; Src
0x18001288a  mov     rcx, rsi; void *
0x18001288d  call    memmove_0
0x180012892  mov     [rbx+rsi], r15w
0x180012897  jmp     short loc_1800128A3
0x180012899  lea     r9, [rsp+0CA8h+Buffer]
0x18001289e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800128a3  xor     r9d, r9d; bool
0x1800128a6  lea     r8, word_18002D338; unsigned __int16 *
0x1800128ad  lea     rdx, asc_18002E1C0; "\\??\\\\"
0x1800128b4  mov     rcx, rdi; this
0x1800128b7  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800128bc  xor     r9d, r9d; bool
0x1800128bf  lea     r8, word_18002D338; unsigned __int16 *
0x1800128c6  lea     rdx, asc_18002E1D0; "\\??\\"
0x1800128cd  mov     rcx, rdi; this
0x1800128d0  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800128d5  mov     r9b, 1; bool
0x1800128d8  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x1800128df  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x1800128e6  mov     rcx, rdi; this
0x1800128e9  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800128ee  mov     r9b, 1; bool
0x1800128f1  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x1800128f8  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x1800128ff  mov     rcx, rdi; this
0x180012902  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012907  mov     edx, 105h; uSize
0x18001290c  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x180012911  call    cs:__imp_GetSystemWindowsDirectoryW
0x180012917  test    eax, eax
0x180012919  jz      loc_180012BEE
0x18001291f  lea     rcx, [rsp+0CA8h+Buffer]
0x180012924  mov     rax, r13
0x180012927  inc     rax
0x18001292a  cmp     [rcx+rax*2], r15w
0x18001292f  jnz     short loc_180012927
0x180012931  cmp     rax, 2
0x180012935  jb      loc_180012BDD
0x18001293b  cmp     [rsp+0CA8h+var_C76], 3Ah ; ':'
0x180012941  jnz     loc_180012BDD
0x180012947  mov     r12d, 5Ch ; '\'
0x18001294d  cmp     [rsp+rax*2+0CA8h+var_C7A], r12w
0x180012953  jz      short loc_18001297F
0x180012955  cmp     rax, r14
0x180012958  jnb     loc_180012BFA
0x18001295e  mov     [rsp+rax*2+0CA8h+Buffer], r12w
0x180012964  lea     rcx, ds:2[rax*2]
0x18001296c  cmp     rcx, 20Ah
0x180012973  jnb     loc_180012BF4
0x180012979  mov     [rsp+rcx+0CA8h+Buffer], r15w
0x18001297f  lea     rsi, [rdi+50h]
0x180012983  lea     rax, [rsp+0CA8h+Buffer]
0x180012988  mov     rdx, r13
0x18001298b  inc     rdx
0x18001298e  cmp     [rax+rdx*2], r15w
0x180012993  jnz     short loc_18001298B
0x180012995  cmp     rdx, [rsi+18h]
0x180012999  ja      short loc_1800129CF
0x18001299b  cmp     qword ptr [rsi+18h], 7
0x1800129a0  jbe     short loc_1800129A7
0x1800129a2  mov     r14, [rsi]
0x1800129a5  jmp     short loc_1800129AA
0x1800129a7  mov     r14, rsi
0x1800129aa  mov     [rsi+10h], rdx
0x1800129ae  lea     rbx, [rdx+rdx]
0x1800129b2  mov     r8, rbx; Size
0x1800129b5  lea     rdx, [rsp+0CA8h+Buffer]; Src
0x1800129ba  mov     rcx, r14; void *
0x1800129bd  call    memmove_0
0x1800129c2  mov     [rbx+r14], r15w
0x1800129c7  mov     r14d, 104h
0x1800129cd  jmp     short loc_1800129DC
0x1800129cf  lea     r9, [rsp+0CA8h+Buffer]
0x1800129d4  mov     rcx, rsi
0x1800129d7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800129dc  cmp     qword ptr [rsi+18h], 7
0x1800129e1  jbe     short loc_1800129E6
0x1800129e3  mov     rsi, [rsi]
0x1800129e6  mov     r9b, 1; bool
0x1800129e9  mov     r8, rsi; unsigned __int16 *
0x1800129ec  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x1800129f3  mov     rcx, rdi; this
0x1800129f6  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800129fb  mov     edx, r14d; cchBufferLength
0x1800129fe  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180012a06  call    cs:__imp_FindFirstVolumeW
0x180012a0c  mov     rsi, rax
0x180012a0f  mov     [rsp+28h], rax
0x180012a14  cmp     rax, r13
0x180012a17  jz      loc_180012C05
0x180012a1d  mov     [rsp+0CA8h+cchReturnLength], r15d
0x180012a22  mov     [rsp+0CA8h+var_862], r15w
0x180012a2b  mov     ebx, r15d
0x180012a2e  lea     r9, [rsp+0CA8h+cchReturnLength]; lpcchReturnLength
0x180012a33  mov     r8d, 410h; cchBufferLength
0x180012a39  lea     rdx, [rsp+0CA8h+szVolumePathNames]; lpszVolumePathNames
0x180012a41  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180012a49  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180012a4f  test    eax, eax
0x180012a51  jz      short loc_180012A5F
0x180012a53  cmp     [rsp+0CA8h+szVolumePathNames], r15w
0x180012a5c  setnz   bl
0x180012a5f  lea     rcx, [rsp+0CA8h+szVolumeName]
0x180012a67  mov     rax, r13
0x180012a6a  inc     rax
0x180012a6d  cmp     [rcx+rax*2], r15w
0x180012a72  jnz     short loc_180012A6A
0x180012a74  test    rax, rax
0x180012a77  jz      short loc_180012AA2
0x180012a79  cmp     [rsp+rax*2+0CA8h+var_A6A], r12w
0x180012a82  jnz     short loc_180012AA2
0x180012a84  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180012a8c  cmp     rcx, 208h
0x180012a93  jnb     loc_180012C0B
0x180012a99  mov     [rsp+rcx+0CA8h+szVolumeName], r15w
0x180012aa2  cmp     [rsp+0CA8h+szVolumeName], r12w
0x180012aab  jnz     short loc_180012AD6
0x180012aad  cmp     [rsp+0CA8h+var_A66], r12w
0x180012ab6  jnz     short loc_180012AD6
0x180012ab8  cmp     [rsp+0CA8h+var_A64], 3Fh ; '?'
0x180012ac1  jnz     short loc_180012AD6
0x180012ac3  cmp     [rsp+0CA8h+var_A62], r12w
0x180012acc  lea     rcx, [rsp+0CA8h+var_A60]
0x180012ad4  jz      short loc_180012ADE
0x180012ad6  lea     rcx, [rsp+0CA8h+szVolumeName]; lpDeviceName
0x180012ade  mov     r8d, r14d; ucchMax
0x180012ae1  lea     rdx, [rsp+0CA8h+Buffer]; lpTargetPath
0x180012ae6  call    cs:__imp_QueryDosDeviceW
0x180012aec  test    eax, eax
0x180012aee  jz      short loc_180012B13
0x180012af0  lea     rdx, [rsp+0CA8h+Buffer]; unsigned __int16 *
0x180012af5  mov     rcx, rdi; this
0x180012af8  test    ebx, ebx
0x180012afa  jz      short loc_180012B0E
0x180012afc  mov     r9b, 1; bool
0x180012aff  lea     r8, [rsp+0CA8h+szVolumePathNames]; unsigned __int16 *
0x180012b07  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b0c  jmp     short loc_180012B13
0x180012b0e  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x180012b13  mov     r8d, r14d; cchBufferLength
0x180012b16  lea     rdx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180012b1e  mov     rcx, rsi; hFindVolume
0x180012b21  call    cs:__imp_FindNextVolumeW
0x180012b27  test    eax, eax
0x180012b29  jnz     loc_180012A22
0x180012b2f  mov     rcx, rsi; hFindVolume
0x180012b32  call    cs:__imp_FindVolumeClose
0x180012b38  xor     r9d, r9d; bool
0x180012b3b  lea     rbx, asc_18002E3C8; "\\\\"
0x180012b42  mov     r8, rbx; unsigned __int16 *
0x180012b45  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180012b4c  mov     rcx, rdi; this
0x180012b4f  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b54  xor     r9d, r9d; bool
0x180012b57  mov     r8, rbx; unsigned __int16 *
0x180012b5a  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180012b61  mov     rcx, rdi; this
0x180012b64  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b69  xor     r9d, r9d; bool
0x180012b6c  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180012b73  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180012b7a  mov     rcx, rdi; this
0x180012b7d  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b82  xor     r9d, r9d; bool
0x180012b85  lea     r8, asc_18002E390; "\\\\?\\"
0x180012b8c  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x180012b93  mov     rcx, rdi; this
0x180012b96  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012b9b  xor     r9d, r9d; bool
0x180012b9e  mov     r8, rbx; unsigned __int16 *
0x180012ba1  mov     rdx, rbx; unsigned __int16 *
0x180012ba4  mov     rcx, rdi; this
0x180012ba7  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180012bac  mov     byte ptr [rdi+70h], 1
0x180012bb0  mov     rcx, [rsp+0CA8h+var_38]
0x180012bb8  xor     rcx, rsp; StackCookie
0x180012bbb  call    __security_check_cookie
0x180012bc0  lea     r11, [rsp+0CA8h+var_28]
0x180012bc8  mov     rbx, [r11+38h]
0x180012bcc  mov     rsi, [r11+40h]
0x180012bd0  mov     rsp, r11
0x180012bd3  pop     r15
0x180012bd5  pop     r14
0x180012bd7  pop     r13
0x180012bd9  pop     r12
0x180012bdb  pop     rdi
0x180012bdc  retn
0x180012bdd  mov     ecx, 8000FFFFh; int
0x180012be2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012be8  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180012bee  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180012bf4  call    __report_rangecheckfailure
0x180012bfa  mov     ecx, 8007007Ah; int
0x180012bff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012c05  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180012c0b  call    __report_rangecheckfailure
```
