# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)

- ea: `0x180024494`
- end: `0x180024901`
- name: `?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ`
- size: `1133`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001ecf8`
- `0x180021250`
- `0x1800258d4`
- `0x18002ac44`

## callees

- `0x180001b90`
- `0x180002180`
- `0x180002d31`
- `0x18000a924`
- `0x180011648`
- `0x180012afc`
- `0x180022d48`
- `0x180022ee8`
- `0x1800232b4`
- `0x180024494`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800244fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800244fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800245db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800245db`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180024803`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180024803`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800247c2`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800247c2`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800246d6`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800246d6`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18002481a`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18002481a`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18002471f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18002471f`

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
0x180024494  mov     [rsp+arg_8], rbx
0x180024499  mov     [rsp+arg_10], rsi
0x18002449e  push    rdi
0x18002449f  push    r12
0x1800244a1  push    r13
0x1800244a3  push    r14
0x1800244a5  push    r15
0x1800244a7  sub     rsp, 0C80h
0x1800244ae  mov     rax, cs:__security_cookie
0x1800244b5  xor     rax, rsp
0x1800244b8  mov     [rsp+0CA8h+var_38], rax
0x1800244c0  mov     rdi, rcx
0x1800244c3  mov     rsi, [rcx+8]
0x1800244c7  mov     rbx, [rcx]
0x1800244ca  cmp     rbx, rsi
0x1800244cd  jz      short loc_1800244F0
0x1800244cf  lea     rcx, [rbx+20h]
0x1800244d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800244d8  mov     rcx, rbx
0x1800244db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800244e0  add     rbx, 40h ; '@'
0x1800244e4  cmp     rbx, rsi
0x1800244e7  jnz     short loc_1800244CF
0x1800244e9  mov     rax, [rdi]
0x1800244ec  mov     [rdi+8], rax
0x1800244f0  mov     r14d, 104h
0x1800244f6  mov     edx, r14d; uSize
0x1800244f9  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x1800244fe  call    cs:__imp_GetSystemDirectoryW
0x180024505  nop     dword ptr [rax+rax+00h]
0x18002450a  xor     r15d, r15d
0x18002450d  test    eax, eax
0x18002450f  jz      loc_1800248D7
0x180024515  lea     rcx, [rdi+30h]
0x180024519  lea     rax, [rsp+0CA8h+Buffer]
0x18002451e  or      r13, 0FFFFFFFFFFFFFFFFh
0x180024522  mov     rdx, r13
0x180024525  inc     rdx
0x180024528  cmp     [rax+rdx*2], r15w
0x18002452d  jnz     short loc_180024525
0x18002452f  cmp     rdx, [rcx+18h]
0x180024533  ja      short loc_180024563
0x180024535  cmp     qword ptr [rcx+18h], 7
0x18002453a  jbe     short loc_180024541
0x18002453c  mov     rsi, [rcx]
0x18002453f  jmp     short loc_180024544
0x180024541  mov     rsi, rcx
0x180024544  mov     [rcx+10h], rdx
0x180024548  lea     rbx, [rdx+rdx]
0x18002454c  mov     r8, rbx; Size
0x18002454f  lea     rdx, [rsp+0CA8h+Buffer]; Src
0x180024554  mov     rcx, rsi; void *
0x180024557  call    memmove_0
0x18002455c  mov     [rbx+rsi], r15w
0x180024561  jmp     short loc_18002456D
0x180024563  lea     r9, [rsp+0CA8h+Buffer]
0x180024568  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002456d  xor     r9d, r9d; bool
0x180024570  lea     r8, String2; unsigned __int16 *
0x180024577  lea     rdx, asc_18003F0F8; "\\??\\\\"
0x18002457e  mov     rcx, rdi; this
0x180024581  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180024586  xor     r9d, r9d; bool
0x180024589  lea     r8, String2; unsigned __int16 *
0x180024590  lea     rdx, asc_18003F108; "\\??\\"
0x180024597  mov     rcx, rdi; this
0x18002459a  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002459f  mov     r9b, 1; bool
0x1800245a2  lea     r8, aGlobalrootDriv_1; "\\\\?\\GLOBALROOT\\DriverStores\\BSPDRI"...
0x1800245a9  lea     rdx, aDriverstoresBs; "\\DriverStores\\BSPDRIVERS"
0x1800245b0  mov     rcx, rdi; this
0x1800245b3  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800245b8  mov     r9b, 1; bool
0x1800245bb  lea     r8, aGlobalrootDriv_0; "\\\\?\\GLOBALROOT\\DriverStore\\Nodes"
0x1800245c2  lea     rdx, aDriverstoreNod; "\\DriverStore\\Nodes"
0x1800245c9  mov     rcx, rdi; this
0x1800245cc  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800245d1  mov     edx, 105h; uSize
0x1800245d6  lea     rcx, [rsp+0CA8h+Buffer]; lpBuffer
0x1800245db  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800245e2  nop     dword ptr [rax+rax+00h]
0x1800245e7  test    eax, eax
0x1800245e9  jz      loc_1800248DD
0x1800245ef  lea     rcx, [rsp+0CA8h+Buffer]
0x1800245f4  mov     rax, r13
0x1800245f7  inc     rax
0x1800245fa  cmp     [rcx+rax*2], r15w
0x1800245ff  jnz     short loc_1800245F7
0x180024601  cmp     rax, 2
0x180024605  jb      loc_1800248CC
0x18002460b  cmp     [rsp+0CA8h+var_C76], 3Ah ; ':'
0x180024611  jnz     loc_1800248CC
0x180024617  mov     r12d, 5Ch ; '\'
0x18002461d  cmp     [rsp+rax*2+0CA8h+var_C7A], r12w
0x180024623  jz      short loc_18002464F
0x180024625  cmp     rax, r14
0x180024628  jnb     loc_1800248E9
0x18002462e  mov     [rsp+rax*2+0CA8h+Buffer], r12w
0x180024634  lea     rcx, ds:2[rax*2]
0x18002463c  cmp     rcx, 20Ah
0x180024643  jnb     loc_1800248E3
0x180024649  mov     [rsp+rcx+0CA8h+Buffer], r15w
0x18002464f  lea     rsi, [rdi+50h]
0x180024653  lea     rax, [rsp+0CA8h+Buffer]
0x180024658  mov     rdx, r13
0x18002465b  inc     rdx
0x18002465e  cmp     [rax+rdx*2], r15w
0x180024663  jnz     short loc_18002465B
0x180024665  cmp     rdx, [rsi+18h]
0x180024669  ja      short loc_18002469F
0x18002466b  cmp     qword ptr [rsi+18h], 7
0x180024670  jbe     short loc_180024677
0x180024672  mov     r14, [rsi]
0x180024675  jmp     short loc_18002467A
0x180024677  mov     r14, rsi
0x18002467a  mov     [rsi+10h], rdx
0x18002467e  lea     rbx, [rdx+rdx]
0x180024682  mov     r8, rbx; Size
0x180024685  lea     rdx, [rsp+0CA8h+Buffer]; Src
0x18002468a  mov     rcx, r14; void *
0x18002468d  call    memmove_0
0x180024692  mov     [rbx+r14], r15w
0x180024697  mov     r14d, 104h
0x18002469d  jmp     short loc_1800246AC
0x18002469f  lea     r9, [rsp+0CA8h+Buffer]
0x1800246a4  mov     rcx, rsi
0x1800246a7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800246ac  cmp     qword ptr [rsi+18h], 7
0x1800246b1  jbe     short loc_1800246B6
0x1800246b3  mov     rsi, [rsi]
0x1800246b6  mov     r9b, 1; bool
0x1800246b9  mov     r8, rsi; unsigned __int16 *
0x1800246bc  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x1800246c3  mov     rcx, rdi; this
0x1800246c6  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800246cb  mov     edx, r14d; cchBufferLength
0x1800246ce  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x1800246d6  call    cs:__imp_FindFirstVolumeW
0x1800246dd  nop     dword ptr [rax+rax+00h]
0x1800246e2  mov     rsi, rax
0x1800246e5  mov     [rsp+28h], rax
0x1800246ea  cmp     rax, r13
0x1800246ed  jz      loc_1800248F4
0x1800246f3  mov     [rsp+0CA8h+cchReturnLength], r15d
0x1800246f8  mov     [rsp+0CA8h+var_862], r15w
0x180024701  mov     ebx, r15d
0x180024704  lea     r9, [rsp+0CA8h+cchReturnLength]; lpcchReturnLength
0x180024709  mov     r8d, 410h; cchBufferLength
0x18002470f  lea     rdx, [rsp+0CA8h+szVolumePathNames]; lpszVolumePathNames
0x180024717  lea     rcx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x18002471f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180024726  nop     dword ptr [rax+rax+00h]
0x18002472b  test    eax, eax
0x18002472d  jz      short loc_18002473B
0x18002472f  cmp     [rsp+0CA8h+szVolumePathNames], r15w
0x180024738  setnz   bl
0x18002473b  lea     rcx, [rsp+0CA8h+szVolumeName]
0x180024743  mov     rax, r13
0x180024746  inc     rax
0x180024749  cmp     [rcx+rax*2], r15w
0x18002474e  jnz     short loc_180024746
0x180024750  test    rax, rax
0x180024753  jz      short loc_18002477E
0x180024755  cmp     [rsp+rax*2+0CA8h+var_A6A], r12w
0x18002475e  jnz     short loc_18002477E
0x180024760  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180024768  cmp     rcx, 208h
0x18002476f  jnb     loc_1800248FA
0x180024775  mov     [rsp+rcx+0CA8h+szVolumeName], r15w
0x18002477e  cmp     [rsp+0CA8h+szVolumeName], r12w
0x180024787  jnz     short loc_1800247B2
0x180024789  cmp     [rsp+0CA8h+var_A66], r12w
0x180024792  jnz     short loc_1800247B2
0x180024794  cmp     [rsp+0CA8h+var_A64], 3Fh ; '?'
0x18002479d  jnz     short loc_1800247B2
0x18002479f  cmp     [rsp+0CA8h+var_A62], r12w
0x1800247a8  lea     rcx, [rsp+0CA8h+var_A60]
0x1800247b0  jz      short loc_1800247BA
0x1800247b2  lea     rcx, [rsp+0CA8h+szVolumeName]; lpDeviceName
0x1800247ba  mov     r8d, r14d; ucchMax
0x1800247bd  lea     rdx, [rsp+0CA8h+Buffer]; lpTargetPath
0x1800247c2  call    cs:__imp_QueryDosDeviceW
0x1800247c9  nop     dword ptr [rax+rax+00h]
0x1800247ce  test    eax, eax
0x1800247d0  jz      short loc_1800247F5
0x1800247d2  lea     rdx, [rsp+0CA8h+Buffer]; unsigned __int16 *
0x1800247d7  mov     rcx, rdi; this
0x1800247da  test    ebx, ebx
0x1800247dc  jz      short loc_1800247F0
0x1800247de  mov     r9b, 1; bool
0x1800247e1  lea     r8, [rsp+0CA8h+szVolumePathNames]; unsigned __int16 *
0x1800247e9  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x1800247ee  jmp     short loc_1800247F5
0x1800247f0  call    ?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)
0x1800247f5  mov     r8d, r14d; cchBufferLength
0x1800247f8  lea     rdx, [rsp+0CA8h+szVolumeName]; lpszVolumeName
0x180024800  mov     rcx, rsi; hFindVolume
0x180024803  call    cs:__imp_FindNextVolumeW
0x18002480a  nop     dword ptr [rax+rax+00h]
0x18002480f  test    eax, eax
0x180024811  jnz     loc_1800246F8
0x180024817  mov     rcx, rsi; hFindVolume
0x18002481a  call    cs:__imp_FindVolumeClose
0x180024821  nop     dword ptr [rax+rax+00h]
0x180024826  xor     r9d, r9d; bool
0x180024829  lea     rbx, asc_18003F308; "\\\\"
0x180024830  mov     r8, rbx; unsigned __int16 *
0x180024833  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x18002483a  mov     rcx, rdi; this
0x18002483d  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180024842  xor     r9d, r9d; bool
0x180024845  mov     r8, rbx; unsigned __int16 *
0x180024848  lea     rdx, aDeviceMup; "\\Device\\Mup\\"
0x18002484f  mov     rcx, rdi; this
0x180024852  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180024857  xor     r9d, r9d; bool
0x18002485a  lea     r8, aVmsmb; "\\\\?\\VMSMB\\"
0x180024861  lea     rdx, aDeviceVmsmb; "\\Device\\vmsmb\\"
0x180024868  mov     rcx, rdi; this
0x18002486b  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180024870  xor     r9d, r9d; bool
0x180024873  lea     r8, asc_18003F2D0; "\\\\?\\"
0x18002487a  lea     rdx, aGlobal; "\\GLOBAL??\\"
0x180024881  mov     rcx, rdi; this
0x180024884  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x180024889  xor     r9d, r9d; bool
0x18002488c  mov     r8, rbx; unsigned __int16 *
0x18002488f  mov     rdx, rbx; unsigned __int16 *
0x180024892  mov     rcx, rdi; this
0x180024895  call    ?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)
0x18002489a  mov     byte ptr [rdi+70h], 1
0x18002489e  mov     rcx, [rsp+0CA8h+var_38]
0x1800248a6  xor     rcx, rsp; StackCookie
0x1800248a9  call    __security_check_cookie
0x1800248ae  lea     r11, [rsp+0CA8h+var_28]
0x1800248b6  mov     rbx, [r11+38h]
0x1800248ba  mov     rsi, [r11+40h]
0x1800248be  mov     rsp, r11
0x1800248c1  pop     r15
0x1800248c3  pop     r14
0x1800248c5  pop     r13
0x1800248c7  pop     r12
0x1800248c9  pop     rdi
0x1800248ca  retn
0x1800248cc  mov     ecx, 8000FFFFh; int
0x1800248d1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800248d7  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800248dd  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800248e3  call    __report_rangecheckfailure
0x1800248e9  mov     ecx, 8007007Ah; int
0x1800248ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800248f4  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800248fa  call    __report_rangecheckfailure
```
