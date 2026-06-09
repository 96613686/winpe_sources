# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x1800233b4`
- end: `0x1800237f6`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `1090`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001dd5c`
- `0x180020204`
- `0x18002476c`
- `0x1800299c4`

## callees

- `0x180001b60`
- `0x180002150`
- `0x180002d01`
- `0x18000a600`
- `0x180010db8`
- `0x180012140`
- `0x180021e08`
- `0x180021fa4`
- `0x180022370`
- `0x1800233b4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002341e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002341e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800234f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800234f5`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180023705`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180023705`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800236ca`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800236ca`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800235ea`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800235ea`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180023716`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180023716`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18002362d`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18002362d`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *this)
{
  char **v2; // rsi
  char **v3; // rbx
  char **v4; // rcx
  unsigned __int64 v5; // rdx
  char *v6; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  const unsigned __int16 *v10; // rsi
  unsigned __int64 v11; // rdx
  char *v12; // r14
  __int64 v13; // rbx
  HANDLE FirstVolumeW; // rsi
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  WCHAR *v19; // rcx
  DWORD cchReturnLength; // [rsp+20h] [rbp-C88h] BYREF
  HANDLE v21; // [rsp+28h] [rbp-C80h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-C78h] BYREF
  WCHAR szVolumeName[4]; // [rsp+240h] [rbp-A68h] BYREF
  char v24; // [rsp+248h] [rbp-A60h] BYREF
  __int16 v25; // [rsp+446h] [rbp-862h]
  WCHAR szVolumePathNames[1040]; // [rsp+450h] [rbp-858h] BYREF

  v2 = (char **)*((_QWORD *)this + 1);
  v3 = *(char ***)this;
  if ( *(char ***)this != v2 )
  {
    do
    {
      std::wstring::~wstring(v3 + 4);
      std::wstring::~wstring(v3);
      v3 += 8;
    }
    while ( v3 != v2 );
    *((_QWORD *)this + 1) = *(_QWORD *)this;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  v4 = (char **)((char *)this + 48);
  v5 = -1;
  do
    ++v5;
  while ( Buffer[v5] );
  if ( v5 > *((_QWORD *)this + 9) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v4);
  }
  else
  {
    if ( *((_QWORD *)this + 9) <= 7u )
      v6 = (char *)this + 48;
    else
      v6 = *v4;
    *((_QWORD *)this + 8) = v5;
    v7 = 2 * v5;
    memmove_0(v6, Buffer, 2 * v5);
    *(_WORD *)&v6[v7] = 0;
  }
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\\\", &String2, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &String2, 0);
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
  v8 = -1;
  do
    ++v8;
  while ( Buffer[v8] );
  if ( v8 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v8 - 1] != 92 )
  {
    if ( v8 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v8] = 92;
    v9 = 2 * v8 + 2;
    if ( v9 >= 0x20A )
      ((void (__noreturn *)(void))_report_rangecheckfailure)();
    *(WCHAR *)((char *)Buffer + v9) = 0;
  }
  v10 = (const unsigned __int16 *)((char *)this + 80);
  v11 = -1;
  do
    ++v11;
  while ( Buffer[v11] );
  if ( v11 > *((_QWORD *)this + 13) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)this + 80);
  }
  else
  {
    if ( *((_QWORD *)this + 13) <= 7u )
      v12 = (char *)this + 80;
    else
      v12 = *(char **)v10;
    *((_QWORD *)this + 12) = v11;
    v13 = 2 * v11;
    memmove_0(v12, Buffer, 2 * v11);
    *(_WORD *)&v12[v13] = 0;
  }
  if ( *((_QWORD *)this + 13) > 7u )
    v10 = *(const unsigned __int16 **)v10;
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v10, 1);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v21 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    cchReturnLength = 0;
    do
    {
      v25 = 0;
      v15 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v15) = szVolumePathNames[0] != 0;
      v17 = -1;
      do
        ++v17;
      while ( szVolumeName[v17] );
      if ( v17 && Buffer[v17 + 263] == 92 )
      {
        v18 = 2 * v17 - 2;
        if ( v18 >= 0x208 )
          _report_rangecheckfailure(v18, v16);
        *(WCHAR *)((char *)szVolumeName + v18) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v19 = (WCHAR *)&v24, szVolumeName[3] != 92) )
      {
        v19 = szVolumeName;
      }
      if ( QueryDosDeviceW(v19, Buffer, 0x104u) )
      {
        if ( v15 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, Buffer, szVolumePathNames, 1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(this, Buffer);
      }
    }
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  }
  catch ( ... )
  {
    FindVolumeClose(v21);
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
0x1800233b4  mov     [rsp+arg_8], rbx
0x1800233b9  mov     [rsp+arg_10], rsi
0x1800233be  push    rdi
0x1800233bf  push    r12
0x1800233c1  push    r13
0x1800233c3  push    r14
0x1800233c5  push    r15
0x1800233c7  sub     rsp, 0C80h
0x1800233ce  mov     rax, cs:__security_cookie
0x1800233d5  xor     rax, rsp
0x1800233d8  mov     [rsp+0CA8h+var_38], rax
0x1800233e0  mov     rdi, rcx
0x1800233e3  mov     rsi, [rcx+8]
0x1800233e7  mov     rbx, [rcx]
0x1800233ea  cmp     rbx, rsi
0x1800233ed  jz      short loc_180023410
0x1800233ef  lea     rcx, [rbx+20h]
0x1800233f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800233f8  mov     rcx, rbx
0x1800233fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023400  add     rbx, 40h ; '@'
0x180023404  cmp     rbx, rsi
0x180023407  jnz     short loc_1800233EF
0x180023409  mov     rax, [rdi]
0x18002340c  mov     [rdi+8], rax
0x180023410  mov     r14d, 104h
0x180023416  mov     edx, r14d; uSize
0x180023419  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x18002341e  call    cs:__imp_GetSystemDirectoryW
0x180023424  xor     r15d, r15d
0x180023427  test    eax, eax
0x180023429  jz      loc_1800237CC
0x18002342f  lea     rcx, [rdi+30h]
0x180023433  lea     rax, [rsp+0CA8h+Buffer]
0x180023438  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002343c  mov     rdx, r13
0x18002343f  inc     rdx
0x180023442  cmp     [rax+rdx*2], r15w
0x180023447  jnz     short loc_18002343F
0x180023449  cmp     rdx, [rcx+18h]
0x18002344d  ja      short loc_18002347D
0x18002344f  cmp     qword ptr [rcx+18h], 7
0x180023454  jbe     short loc_18002345B
0x180023456  mov     rsi, [rcx]
0x180023459  jmp     short loc_18002345E
0x18002345b  mov     rsi, rcx
0x18002345e  mov     [rcx+10h], rdx
0x180023462  lea     rbx, [rdx+rdx]
0x180023466  mov     r8, rbx; Size
0x180023469  lea     rdx, [rsp+0CA8h+Buffer]; Src
0x18002346e  mov     rcx, rsi; void *
0x180023471  call    memmove_0
0x180023476  mov     [rbx+rsi], r15w
0x18002347b  jmp     short loc_180023487
0x18002347d  lea     r9, [rsp+0CA8h+Buffer]
0x180023482  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180023487  xor     r9d, r9d; bool
0x18002348a  lea     r8, String2; unsigned __int16 *
0x180023491  lea     rdx, asc_18003D118; "\\??\\\\"
0x180023498  mov     rcx, rdi; this
0x18002349b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800234a0  xor     r9d, r9d; bool
0x1800234a3  lea     r8, String2; unsigned __int16 *
0x1800234aa  lea     rdx, asc_18003D128; "\\??\\"
0x1800234b1  mov     rcx, rdi; this
0x1800234b4  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800234b9  mov     r9b, 1; bool
0x1800234bc  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x1800234c3  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x1800234ca  mov     rcx, rdi; this
0x1800234cd  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800234d2  mov     r9b, 1; bool
0x1800234d5  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x1800234dc  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x1800234e3  mov     rcx, rdi; this
0x1800234e6  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800234eb  mov     edx, 105h; uSize
0x1800234f0  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x1800234f5  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800234fb  test    eax, eax
0x1800234fd  jz      loc_1800237D2
0x180023503  lea     rcx, [rsp+0CA8h+Buffer]
0x180023508  mov     rax, r13
0x18002350b  inc     rax
0x18002350e  cmp     [rcx+rax*2], r15w
0x180023513  jnz     short loc_18002350B
0x180023515  cmp     rax, 2
0x180023519  jb      loc_1800237C1
0x18002351f  cmp     [rsp+0CA8h+var_C76], 3Ah ; ':'
0x180023525  jnz     loc_1800237C1
0x18002352b  mov     r12d, 5Ch ; '\'
0x180023531  cmp     [rsp+rax*2+0CA8h+var_C7A], r12w
0x180023537  jz      short loc_180023563
0x180023539  cmp     rax, r14
0x18002353c  jnb     loc_1800237DE
0x180023542  mov     [rsp+rax*2+0CA8h+Buffer], r12w
0x180023548  lea     rcx, ds:2[rax*2]
0x180023550  cmp     rcx, 20Ah
0x180023557  jnb     loc_1800237D8
0x18002355d  mov     [rsp+rcx+0CA8h+Buffer], r15w
0x180023563  lea     rsi, [rdi+50h]
0x180023567  lea     rax, [rsp+0CA8h+Buffer]
0x18002356c  mov     rdx, r13
0x18002356f  inc     rdx
0x180023572  cmp     [rax+rdx*2], r15w
0x180023577  jnz     short loc_18002356F
0x180023579  cmp     rdx, [rsi+18h]
0x18002357d  ja      short loc_1800235B3
0x18002357f  cmp     qword ptr [rsi+18h], 7
0x180023584  jbe     short loc_18002358B
0x180023586  mov     r14, [rsi]
0x180023589  jmp     short loc_18002358E
0x18002358b  mov     r14, rsi
0x18002358e  mov     [rsi+10h], rdx
0x180023592  lea     rbx, [rdx+rdx]
0x180023596  mov     r8, rbx; Size
0x180023599  lea     rdx, [rsp+0CA8h+Buffer]; Src
0x18002359e  mov     rcx, r14; void *
0x1800235a1  call    memmove_0
0x1800235a6  mov     [rbx+r14], r15w
0x1800235ab  mov     r14d, 104h
0x1800235b1  jmp     short loc_1800235C0
0x1800235b3  lea     r9, [rsp+0CA8h+Buffer]
0x1800235b8  mov     rcx, rsi
0x1800235bb  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800235c0  cmp     qword ptr [rsi+18h], 7
0x1800235c5  jbe     short loc_1800235CA
0x1800235c7  mov     rsi, [rsi]
0x1800235ca  mov     r9b, 1; bool
0x1800235cd  mov     r8, rsi; unsigned __int16 *
0x1800235d0  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x1800235d7  mov     rcx, rdi; this
0x1800235da  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800235df  mov     edx, r14d; cchBufferLength
0x1800235e2  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x1800235ea  call    cs:__imp_FindFirstVolumeW
0x1800235f0  mov     rsi, rax
0x1800235f3  mov     [rsp+28h], rax
0x1800235f8  cmp     rax, r13
0x1800235fb  jz      loc_1800237E9
0x180023601  mov     [rsp+0CA8h+cchReturnLength], r15d
0x180023606  mov     [rsp+0CA8h+var_862], r15w
0x18002360f  mov     ebx, r15d
0x180023612  lea     r9, [rsp+0CA8h+cchReturnLength]; lpcchReturnLength
0x180023617  mov     r8d, 410h; cchBufferLength
0x18002361d  lea     rdx, [rsp+0CA8h+szVolumePathNames]; lpszVolumePathNames
0x180023625  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x18002362d  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180023633  test    eax, eax
0x180023635  jz      short loc_180023643
0x180023637  cmp     [rsp+0CA8h+szVolumePathNames], r15w
0x180023640  setnz   bl
0x180023643  lea     rcx, [rsp+0CA8h+szVolumeName]
0x18002364b  mov     rax, r13
0x18002364e  inc     rax
0x180023651  cmp     [rcx+rax*2], r15w
0x180023656  jnz     short loc_18002364E
0x180023658  test    rax, rax
0x18002365b  jz      short loc_180023686
0x18002365d  cmp     [rsp+rax*2+0CA8h+var_A6A], r12w
0x180023666  jnz     short loc_180023686
0x180023668  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180023670  cmp     rcx, 208h
0x180023677  jnb     loc_1800237EF
0x18002367d  mov     [rsp+rcx+0CA8h+szVolumeName], r15w
0x180023686  cmp     [rsp+0CA8h+szVolumeName], r12w
0x18002368f  jnz     short loc_1800236BA
0x180023691  cmp     [rsp+0CA8h+var_A66], r12w
0x18002369a  jnz     short loc_1800236BA
0x18002369c  cmp     [rsp+0CA8h+var_A64], 3Fh ; '?'
0x1800236a5  jnz     short loc_1800236BA
0x1800236a7  cmp     [rsp+0CA8h+var_A62], r12w
0x1800236b0  lea     rcx, [rsp+0CA8h+var_A60]
0x1800236b8  jz      short loc_1800236C2
0x1800236ba  lea     rcx, [rsp+0CA8h+szVolumeName]; lpDeviceName
0x1800236c2  mov     r8d, r14d; ucchMax
0x1800236c5  lea     rdx, [rsp+0CA8h+Buffer]; lpTargetPath
0x1800236ca  call    cs:__imp_QueryDosDeviceW
0x1800236d0  test    eax, eax
0x1800236d2  jz      short loc_1800236F7
0x1800236d4  lea     rdx, [rsp+0CA8h+Buffer]; unsigned __int16 *
0x1800236d9  mov     rcx, rdi; this
0x1800236dc  test    ebx, ebx
0x1800236de  jz      short loc_1800236F2
0x1800236e0  mov     r9b, 1; bool
0x1800236e3  lea     r8, [rsp+0CA8h+szVolumePathNames]; unsigned __int16 *
0x1800236eb  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800236f0  jmp     short loc_1800236F7
0x1800236f2  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x1800236f7  mov     r8d, r14d; cchBufferLength
0x1800236fa  lea     rdx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180023702  mov     rcx, rsi; hFindVolume
0x180023705  call    cs:__imp_FindNextVolumeW
0x18002370b  test    eax, eax
0x18002370d  jnz     loc_180023606
0x180023713  mov     rcx, rsi; hFindVolume
0x180023716  call    cs:__imp_FindVolumeClose
0x18002371c  xor     r9d, r9d; bool
0x18002371f  lea     rbx, asc_18003D328; "\\\\"
0x180023726  mov     r8, rbx; unsigned __int16 *
0x180023729  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180023730  mov     rcx, rdi; this
0x180023733  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180023738  xor     r9d, r9d; bool
0x18002373b  mov     r8, rbx; unsigned __int16 *
0x18002373e  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180023745  mov     rcx, rdi; this
0x180023748  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002374d  xor     r9d, r9d; bool
0x180023750  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180023757  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x18002375e  mov     rcx, rdi; this
0x180023761  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180023766  xor     r9d, r9d; bool
0x180023769  lea     r8, asc_18003D2F0; "\\\\?\\"
0x180023770  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x180023777  mov     rcx, rdi; this
0x18002377a  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002377f  xor     r9d, r9d; bool
0x180023782  mov     r8, rbx; unsigned __int16 *
0x180023785  mov     rdx, rbx; unsigned __int16 *
0x180023788  mov     rcx, rdi; this
0x18002378b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180023790  mov     byte ptr [rdi+70h], 1
0x180023794  mov     rcx, [rsp+0CA8h+var_38]
0x18002379c  xor     rcx, rsp; StackCookie
0x18002379f  call    __security_check_cookie
0x1800237a4  lea     r11, [rsp+0CA8h+var_28]
0x1800237ac  mov     rbx, [r11+38h]
0x1800237b0  mov     rsi, [r11+40h]
0x1800237b4  mov     rsp, r11
0x1800237b7  pop     r15
0x1800237b9  pop     r14
0x1800237bb  pop     r13
0x1800237bd  pop     r12
0x1800237bf  pop     rdi
0x1800237c0  retn
0x1800237c1  mov     ecx, 8000FFFFh; int
0x1800237c6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800237cc  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800237d2  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800237d8  call    __report_rangecheckfailure
0x1800237de  mov     ecx, 8007007Ah; int
0x1800237e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800237e9  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800237ef  call    __report_rangecheckfailure
```
