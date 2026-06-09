# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x180037ac8`
- end: `0x180037e7d`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `949`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180027e60`
- `0x1800360c8`
- `0x18004a918`
- `0x18004d398`

## callees

- `0x180037ac8`
- `0x180044090`
- `0x180044210`
- `0x180046394`
- `0x18004a9d8`
- `0x18004ece0`
- `0x18004f2a0`
- `0x180076cd0`
- `0x180077b24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180037c85`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180037c85`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180037d75`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180037d75`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180037db6`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180037db6`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180037dc7`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180037dc7`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180037cdb`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180037cdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180037b27`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180037b27`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180037bcc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180037bcc`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *this)
{
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v2; // rdx
  __int64 v3; // r8
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rcx
  __int64 v6; // r8
  const unsigned __int16 *v7; // rdi
  HANDLE FirstVolumeW; // rsi
  int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  WCHAR *v14; // rcx
  bool v15; // r8
  DWORD cchReturnLength; // [rsp+20h] [rbp-C98h] BYREF
  HANDLE v17; // [rsp+28h] [rbp-C90h]
  __int64 v18; // [rsp+30h] [rbp-C88h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C78h] BYREF
  WCHAR szVolumeName[4]; // [rsp+250h] [rbp-A68h] BYREF
  char v22; // [rsp+258h] [rbp-A60h] BYREF
  __int16 v23; // [rsp+456h] [rbp-862h]
  WCHAR szVolumePathNames[1040]; // [rsp+460h] [rbp-858h] BYREF

  v18 = -2;
  v2 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*((_QWORD *)this + 1);
  if ( *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this != v2 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this,
      v2);
    *((_QWORD *)this + 1) = *(_QWORD *)this;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    ATL::AtlThrowLastWin32();
  v3 = -1;
  do
    ++v3;
  while ( Buffer[v3] );
  std::wstring::_Assign<unsigned short>((char *)this + 48);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\\\", &LocaleName, 0);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\??\\", &LocaleName, 0);
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
  v4 = -1;
  do
    ++v4;
  while ( Buffer[v4] );
  if ( v4 < 2 || Buffer[1] != 58 )
    ATL::AtlThrowImpl(-2147418113);
  if ( Buffer[v4 - 1] != 92 )
  {
    if ( v4 >= 0x104 )
      ATL::AtlThrowImpl(-2147024774);
    Buffer[v4] = 92;
    v5 = 2 * v4 + 2;
    if ( v5 >= 0x20A )
      ((void (__noreturn *)(void))_report_rangecheckfailure)();
    *(WCHAR *)((char *)Buffer + v5) = 0;
  }
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  v7 = (const unsigned __int16 *)((char *)this + 80);
  std::wstring::_Assign<unsigned short>((char *)this + 80);
  if ( *((_QWORD *)this + 13) > 7u )
    v7 = *(const unsigned __int16 **)v7;
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, L"\\SystemRoot\\", v7, 1);
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  v17 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    ATL::AtlThrowLastWin32();
  try
  {
    cchReturnLength = 0;
    do
    {
      v23 = 0;
      v9 = 0;
      if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x410u, &cchReturnLength) )
        LOBYTE(v9) = szVolumePathNames[0] != 0;
      v12 = -1;
      do
        ++v12;
      while ( szVolumeName[v12] );
      if ( v12 && Buffer[v12 + 263] == 92 )
      {
        v13 = 2 * v12 - 2;
        if ( v13 >= 0x208 )
          _report_rangecheckfailure(v13, v10, v11);
        *(WCHAR *)((char *)szVolumeName + v13) = 0;
      }
      if ( szVolumeName[0] != 92
        || szVolumeName[1] != 92
        || szVolumeName[2] != 63
        || (v14 = (WCHAR *)&v22, szVolumeName[3] != 92) )
      {
        v14 = szVolumeName;
      }
      if ( QueryDosDeviceW(v14, Buffer, 0x104u) )
      {
        if ( v9 )
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(this, Buffer, szVolumePathNames, 1);
        else
          Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(this, Buffer, v15);
      }
    }
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
  }
  catch ( ... )
  {
    FindVolumeClose(v17);
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
0x180037ac8  mov     rax, rsp
0x180037acb  push    rdi
0x180037acc  push    r12
0x180037ace  push    r13
0x180037ad0  push    r14
0x180037ad2  push    r15
0x180037ad4  sub     rsp, 0C90h
0x180037adb  mov     [rsp+0CB8h+var_C88], 0FFFFFFFFFFFFFFFEh
0x180037ae4  mov     [rax+10h], rbx
0x180037ae8  mov     [rax+18h], rsi
0x180037aec  mov     rax, cs:__security_cookie
0x180037af3  xor     rax, rsp
0x180037af6  mov     [rsp+0CB8h+var_38], rax
0x180037afe  mov     rbx, rcx
0x180037b01  mov     rdx, [rcx+8]
0x180037b05  cmp     [rcx], rdx
0x180037b08  jz      short loc_180037B19
0x180037b0a  mov     rcx, [rcx]; this
0x180037b0d  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x180037b12  mov     rax, [rbx]
0x180037b15  mov     [rbx+8], rax
0x180037b19  mov     r13d, 104h
0x180037b1f  mov     edx, r13d; uSize
0x180037b22  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180037b27  call    cs:__imp_GetSystemDirectoryW
0x180037b2d  xor     r14d, r14d
0x180037b30  test    eax, eax
0x180037b32  jnz     short loc_180037B3A
0x180037b34  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180037b3a  lea     rax, [rsp+0CB8h+Buffer]
0x180037b3f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180037b43  mov     r8, r12
0x180037b46  inc     r8
0x180037b49  cmp     [rax+r8*2], r14w
0x180037b4e  jnz     short loc_180037B46
0x180037b50  lea     rcx, [rbx+30h]
0x180037b54  lea     rdx, [rsp+0CB8h+Buffer]
0x180037b59  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037b5e  xor     r9d, r9d; bool
0x180037b61  lea     r8, LocaleName; unsigned __int16 *
0x180037b68  lea     rdx, asc_180099CD0; "\\??\\\\"
0x180037b6f  mov     rcx, rbx; this
0x180037b72  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037b77  xor     r9d, r9d; bool
0x180037b7a  lea     r8, LocaleName; unsigned __int16 *
0x180037b81  lea     rdx, asc_180099DD0; "\\??\\"
0x180037b88  mov     rcx, rbx; this
0x180037b8b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037b90  mov     r9b, 1; bool
0x180037b93  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x180037b9a  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x180037ba1  mov     rcx, rbx; this
0x180037ba4  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037ba9  mov     r9b, 1; bool
0x180037bac  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x180037bb3  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x180037bba  mov     rcx, rbx; this
0x180037bbd  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037bc2  mov     edx, 105h; uSize
0x180037bc7  lea     rcx, [rsp+0CB8h+Buffer]; lpBuffer
0x180037bcc  call    cs:__imp_GetSystemWindowsDirectoryW
0x180037bd2  test    eax, eax
0x180037bd4  jnz     short loc_180037BDC
0x180037bd6  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180037bdc  lea     rcx, [rsp+0CB8h+Buffer]
0x180037be1  mov     rax, r12
0x180037be4  inc     rax
0x180037be7  cmp     [rcx+rax*2], r14w
0x180037bec  jnz     short loc_180037BE4
0x180037bee  cmp     rax, 2
0x180037bf2  jb      loc_180037E72
0x180037bf8  cmp     [rsp+0CB8h+var_C76], 3Ah ; ':'
0x180037bfe  jnz     loc_180037E72
0x180037c04  mov     r15d, 5Ch ; '\'
0x180037c0a  cmp     [rsp+rax*2+0CB8h+var_C7A], r15w
0x180037c10  jz      short loc_180037C38
0x180037c12  cmp     rax, r13
0x180037c15  jnb     loc_180037CA4
0x180037c1b  mov     [rsp+rax*2+0CB8h+Buffer], r15w
0x180037c21  lea     rcx, ds:2[rax*2]
0x180037c29  cmp     rcx, 20Ah
0x180037c30  jnb     short loc_180037C9E
0x180037c32  mov     [rsp+rcx+0CB8h+Buffer], r14w
0x180037c38  lea     rax, [rsp+0CB8h+Buffer]
0x180037c3d  mov     r8, r12
0x180037c40  inc     r8
0x180037c43  cmp     [rax+r8*2], r14w
0x180037c48  jnz     short loc_180037C40
0x180037c4a  lea     rdi, [rbx+50h]
0x180037c4e  lea     rdx, [rsp+0CB8h+Buffer]
0x180037c53  mov     rcx, rdi
0x180037c56  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037c5b  cmp     qword ptr [rdi+18h], 7
0x180037c60  jbe     short loc_180037C65
0x180037c62  mov     rdi, [rdi]
0x180037c65  mov     r9b, 1; bool
0x180037c68  mov     r8, rdi; unsigned __int16 *
0x180037c6b  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x180037c72  mov     rcx, rbx; this
0x180037c75  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037c7a  mov     edx, r13d; cchBufferLength
0x180037c7d  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180037c85  call    cs:__imp_FindFirstVolumeW
0x180037c8b  mov     rsi, rax
0x180037c8e  mov     [rsp+0CB8h+var_C90], rax
0x180037c93  cmp     rax, r12
0x180037c96  jnz     short loc_180037CAF
0x180037c98  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180037c9e  call    __report_rangecheckfailure
0x180037ca4  mov     ecx, 8007007Ah; int
0x180037ca9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180037caf  mov     [rsp+0CB8h+cchReturnLength], r14d
0x180037cb4  mov     [rsp+0CB8h+var_862], r14w
0x180037cbd  mov     edi, r14d
0x180037cc0  lea     r9, [rsp+0CB8h+cchReturnLength]; lpcchReturnLength
0x180037cc5  mov     r8d, 410h; cchBufferLength
0x180037ccb  lea     rdx, [rsp+0CB8h+szVolumePathNames]; lpszVolumePathNames
0x180037cd3  lea     rcx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180037cdb  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180037ce1  test    eax, eax
0x180037ce3  jz      short loc_180037CF2
0x180037ce5  cmp     [rsp+0CB8h+szVolumePathNames], r14w
0x180037cee  setnz   dil
0x180037cf2  lea     rcx, [rsp+0CB8h+szVolumeName]
0x180037cfa  mov     rax, r12
0x180037cfd  inc     rax
0x180037d00  cmp     [rcx+rax*2], r14w
0x180037d05  jnz     short loc_180037CFD
0x180037d07  test    rax, rax
0x180037d0a  jz      short loc_180037D31
0x180037d0c  cmp     [rsp+rax*2+0CB8h+var_A6A], r15w
0x180037d15  jnz     short loc_180037D31
0x180037d17  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180037d1f  cmp     rcx, 208h
0x180037d26  jnb     short loc_180037D9D
0x180037d28  mov     [rsp+rcx+0CB8h+szVolumeName], r14w
0x180037d31  cmp     [rsp+0CB8h+szVolumeName], r15w
0x180037d3a  jnz     short loc_180037D65
0x180037d3c  cmp     [rsp+0CB8h+var_A66], r15w
0x180037d45  jnz     short loc_180037D65
0x180037d47  cmp     [rsp+0CB8h+var_A64], 3Fh ; '?'
0x180037d50  jnz     short loc_180037D65
0x180037d52  cmp     [rsp+0CB8h+var_A62], r15w
0x180037d5b  lea     rcx, [rsp+0CB8h+var_A60]
0x180037d63  jz      short loc_180037D6D
0x180037d65  lea     rcx, [rsp+0CB8h+szVolumeName]; lpDeviceName
0x180037d6d  mov     r8d, r13d; ucchMax
0x180037d70  lea     rdx, [rsp+0CB8h+Buffer]; lpTargetPath
0x180037d75  call    cs:__imp_QueryDosDeviceW
0x180037d7b  test    eax, eax
0x180037d7d  jz      short loc_180037DA8
0x180037d7f  lea     rdx, [rsp+0CB8h+Buffer]; unsigned __int16 *
0x180037d84  mov     rcx, rbx; this
0x180037d87  test    edi, edi
0x180037d89  jz      short loc_180037DA3
0x180037d8b  mov     r9b, 1; bool
0x180037d8e  lea     r8, [rsp+0CB8h+szVolumePathNames]; unsigned __int16 *
0x180037d96  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037d9b  jmp     short loc_180037DA8
0x180037d9d  call    __report_rangecheckfailure
0x180037da3  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x180037da8  mov     r8d, r13d; cchBufferLength
0x180037dab  lea     rdx, [rsp+0CB8h+szVolumeName]; lpszVolumeName
0x180037db3  mov     rcx, rsi; hFindVolume
0x180037db6  call    cs:__imp_FindNextVolumeW
0x180037dbc  test    eax, eax
0x180037dbe  jnz     loc_180037CB4
0x180037dc4  mov     rcx, rsi; hFindVolume
0x180037dc7  call    cs:__imp_FindVolumeClose
0x180037dcd  xor     r9d, r9d; bool
0x180037dd0  lea     rdi, asc_180099DC4; "\\\\"
0x180037dd7  mov     r8, rdi; unsigned __int16 *
0x180037dda  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x180037de1  mov     rcx, rbx; this
0x180037de4  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037de9  xor     r9d, r9d; bool
0x180037dec  mov     r8, rdi; unsigned __int16 *
0x180037def  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x180037df6  mov     rcx, rbx; this
0x180037df9  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037dfe  xor     r9d, r9d; bool
0x180037e01  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180037e08  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180037e0f  mov     rcx, rbx; this
0x180037e12  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037e17  xor     r9d, r9d; bool
0x180037e1a  lea     r8, asc_180099DB8; "\\\\?\\"
0x180037e21  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x180037e28  mov     rcx, rbx; this
0x180037e2b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037e30  xor     r9d, r9d; bool
0x180037e33  mov     r8, rdi; unsigned __int16 *
0x180037e36  mov     rdx, rdi; unsigned __int16 *
0x180037e39  mov     rcx, rbx; this
0x180037e3c  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180037e41  mov     byte ptr [rbx+70h], 1
0x180037e45  mov     rcx, [rsp+0CB8h+var_38]
0x180037e4d  xor     rcx, rsp; StackCookie
0x180037e50  call    __security_check_cookie
0x180037e55  lea     r11, [rsp+0CB8h+var_28]
0x180037e5d  mov     rbx, [r11+38h]
0x180037e61  mov     rsi, [r11+40h]
0x180037e65  mov     rsp, r11
0x180037e68  pop     r15
0x180037e6a  pop     r14
0x180037e6c  pop     r13
0x180037e6e  pop     r12
0x180037e70  pop     rdi
0x180037e71  retn
0x180037e72  mov     ecx, 8000FFFFh; int
0x180037e77  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
