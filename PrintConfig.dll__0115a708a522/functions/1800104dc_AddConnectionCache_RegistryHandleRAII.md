# AddConnectionCache(RegistryHandleRAII &)

- ea: `0x1800104dc`
- end: `0x1800109b8`
- name: `?AddConnectionCache@@YAXAEAVRegistryHandleRAII@@@Z`
- size: `1244`
- prototype: `void __fastcall(struct RegistryHandleRAII *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800150ac`

## callees

- `0x180003400`
- `0x180003c10`
- `0x180004558`
- `0x180004564`
- `0x18000be68`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x18000fdb0`
- `0x1800104dc`
- `0x180018624`
- `0x180018e74`
- `0x1800190f0`
- `0x1800197b4`
- `0x180037f00`
- `0x1800380f4`
- `0x180159d10`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180010553`
- `KERNEL32!CreateDirectoryW` at `0x180010626`
- `KERNEL32!CreateDirectoryW` at `0x180010553`
- `KERNEL32!CreateDirectoryW` at `0x180010626`
- `KERNEL32!GetLastError` at `0x180010563`
- `KERNEL32!GetLastError` at `0x1800107b5`
- `KERNEL32!GetLastError` at `0x180010563`
- `KERNEL32!GetLastError` at `0x1800107b5`
- `ole32!CoCreateGuid` at `0x18001059a`
- `ole32!CoCreateGuid` at `0x18001059a`
- `ole32!StringFromGUID2` at `0x1800105bf`
- `ole32!StringFromGUID2` at `0x1800105bf`

## string_xrefs

- `0x1800106c0`: `CachedChangeID`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall AddConnectionCache(struct RegistryHandleRAII *a1)
{
  signed int V4SharingRoot; // eax
  int v3; // ebx
  signed int LastError; // eax
  signed int v5; // ebx
  HRESULT v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  int v11; // eax
  int v12; // edi
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  signed int v15; // eax
  unsigned int v16; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v18; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+68h] [rbp-A0h]
  GUID pguid_8; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v21[7]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v22; // [rsp+C0h] [rbp-48h]
  char v23[8]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v24[7]; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD *v25; // [rsp+108h] [rbp+0h]
  OLECHAR sz; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 v27[55]; // [rsp+11Ah] [rbp+12h] BYREF
  WCHAR PathName[264]; // [rsp+188h] [rbp+80h] BYREF

  memset_0(PathName, 0, 0x208u);
  V4SharingRoot = GetV4SharingRoot(PathName, 0x104u);
  v3 = V4SharingRoot;
  if ( V4SharingRoot < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x2Bu,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        V4SharingRoot);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v3);
    throw (hr_error *)&pExceptionObject[8];
  }
  if ( !CreateDirectoryW(PathName, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 183 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x2Cu,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v5);
        }
        hr_error::hr_error((hr_error *)&pExceptionObject[8], v5);
        throw (hr_error *)&pExceptionObject[8];
      }
    }
  }
  pguid_8 = 0;
  v6 = CoCreateGuid(&pguid_8);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x2Du,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v6);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v7);
    throw (hr_error *)&pExceptionObject[8];
  }
  if ( !StringFromGUID2(&pguid_8, &sz, 50) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x2Eu,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        -2147024882);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], -2147024882);
    throw (hr_error *)&pExceptionObject[8];
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v27[v9 - 1] );
  v10 = 2 * v9 - 2;
  if ( v10 >= 0x64 )
    _report_rangecheckfailure();
  *(unsigned __int16 *)((char *)&v27[-1] + v10) = 0;
  v11 = StringCchCatW(PathName, 260, v27);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x2Fu,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v11);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v12);
    throw (hr_error *)&pExceptionObject[8];
  }
  if ( !CreateDirectoryW(PathName, 0) )
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x30u,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v16);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v16);
    throw (hr_error *)&pExceptionObject[8];
  }
  v21[0] = off_1801CC358;
  v21[1] = PathName;
  v22 = v21;
  v23[0] = 0;
  v25 = 0;
  v25 = std::_Func_impl_no_alloc__lambda_b0a151323b3dba51a5a1a2a034a2ee0f__void_::_Move((__int64)v21, v24);
  if ( v22 )
  {
    v13 = v21;
    LOBYTE(v13) = v22 != v21;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v22 + 32LL))(v22, v13);
    v22 = 0;
  }
  WriteConnectionReferenceCount(a1, 0);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"CachedChangeID", 0xEu);
  Win32Adapters::Registry::RegSetValueW((HKEY *)a1, (const WCHAR *)&v18, 0);
  std::wstring::~wstring((char **)&v18);
  memset(&pExceptionObject[8], 0, 32);
  do
    ++v8;
  while ( v27[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject[8], v27, v8);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"ConnectionGUID", 0xEu);
  Win32Adapters::Registry::RegSetValueW((HKEY *)a1, (const WCHAR *)&v18, (__int64 *)&pExceptionObject[8], 1u);
  std::wstring::~wstring((char **)&v18);
  std::wstring::~wstring((char **)&pExceptionObject[8]);
  UpdateConnectionStatusFlags(a1, -1, 0);
  v23[0] = 1;
  CallOnException::~CallOnException((CallOnException *)v23, v14);
}

```

## disassembly

```asm
0x1800104dc  mov     rax, rsp
0x1800104df  push    rbp
0x1800104e0  push    rdi
0x1800104e1  push    r14
0x1800104e3  lea     rbp, [rax-2B8h]
0x1800104ea  sub     rsp, 3A0h
0x1800104f1  mov     [rsp+3B0h+var_390], 0FFFFFFFFFFFFFFFEh
0x1800104fa  mov     [rax+10h], rbx
0x1800104fe  mov     [rax+18h], rsi
0x180010502  mov     rax, cs:__security_cookie
0x180010509  xor     rax, rsp
0x18001050c  mov     [rbp+2B0h+var_20], rax
0x180010513  mov     rsi, rcx
0x180010516  xor     edx, edx; Val
0x180010518  mov     r8d, 208h; Size
0x18001051e  lea     rcx, [rbp+2B0h+PathName]; void *
0x180010525  call    memset_0
0x18001052a  mov     edi, 104h
0x18001052f  mov     edx, edi; unsigned int
0x180010531  lea     rcx, [rbp+2B0h+PathName]; unsigned __int16 *
0x180010538  call    ?GetV4SharingRoot@@YAJPEAGK@Z; GetV4SharingRoot(ushort *,ulong)
0x18001053d  mov     ebx, eax
0x18001053f  xor     r14d, r14d
0x180010542  test    eax, eax
0x180010544  js      loc_180010825
0x18001054a  xor     edx, edx; lpSecurityAttributes
0x18001054c  lea     rcx, [rbp+2B0h+PathName]; lpPathName
0x180010553  call    cs:__imp_CreateDirectoryW
0x18001055a  nop     dword ptr [rax+rax+00h]
0x18001055f  test    eax, eax
0x180010561  jnz     short loc_18001058D
0x180010563  call    cs:__imp_GetLastError
0x18001056a  nop     dword ptr [rax+rax+00h]
0x18001056f  mov     ebx, eax
0x180010571  cmp     eax, 0B7h
0x180010576  jz      short loc_18001058D
0x180010578  test    eax, eax
0x18001057a  jle     short loc_180010585
0x18001057c  movzx   ebx, ax
0x18001057f  or      ebx, 80070000h
0x180010585  test    ebx, ebx
0x180010587  js      loc_180010875
0x18001058d  xorps   xmm0, xmm0
0x180010590  movups  xmmword ptr [rsp+3B0h+pguid+8], xmm0
0x180010595  lea     rcx, [rsp+3B0h+pguid+8]; pguid
0x18001059a  call    cs:__imp_CoCreateGuid
0x1800105a1  nop     dword ptr [rax+rax+00h]
0x1800105a6  mov     ebx, eax
0x1800105a8  test    eax, eax
0x1800105aa  js      loc_1800108C4
0x1800105b0  mov     r8d, 32h ; '2'; cchMax
0x1800105b6  lea     rdx, [rbp+2B0h+sz]; lpsz
0x1800105ba  lea     rcx, [rsp+3B0h+pguid+8]; rguid
0x1800105bf  call    cs:__imp_StringFromGUID2
0x1800105c6  nop     dword ptr [rax+rax+00h]
0x1800105cb  test    eax, eax
0x1800105cd  jz      loc_180010914
0x1800105d3  lea     rcx, [rbp+2B0h+sz]
0x1800105d7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800105db  mov     rax, rbx
0x1800105de  inc     rax
0x1800105e1  cmp     [rcx+rax*2], r14w
0x1800105e6  jnz     short loc_1800105DE
0x1800105e8  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1800105f0  cmp     rcx, 64h ; 'd'
0x1800105f4  jnb     loc_18001081F
0x1800105fa  mov     [rbp+rcx+2B0h+sz], r14w
0x180010600  lea     r8, [rbp+2B0h+var_29E]; unsigned __int16 *
0x180010604  mov     rdx, rdi; unsigned __int64
0x180010607  lea     rcx, [rbp+2B0h+PathName]; unsigned __int16 *
0x18001060e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010613  mov     edi, eax
0x180010615  test    eax, eax
0x180010617  js      loc_180010968
0x18001061d  xor     edx, edx; lpSecurityAttributes
0x18001061f  lea     rcx, [rbp+2B0h+PathName]; lpPathName
0x180010626  call    cs:__imp_CreateDirectoryW
0x18001062d  nop     dword ptr [rax+rax+00h]
0x180010632  test    eax, eax
0x180010634  jz      loc_1800107B5
0x18001063a  lea     rax, off_1801CC358
0x180010641  mov     [rbp+2B0h+var_330], rax
0x180010645  lea     rax, [rbp+2B0h+PathName]
0x18001064c  mov     [rbp+2B0h+var_328], rax
0x180010650  lea     rax, [rbp+2B0h+var_330]
0x180010654  mov     [rbp+2B0h+var_2F8], rax
0x180010658  mov     [rbp+2B0h+var_2F0], r14b
0x18001065c  lea     rax, [rbp+2B0h+var_2E8]
0x180010660  mov     qword ptr [rsp+3B0h+pExceptionObject], rax
0x180010665  mov     [rbp+2B0h+var_2B0], r14
0x180010669  lea     rdx, [rbp+2B0h+var_2E8]
0x18001066d  lea     rcx, [rbp+2B0h+var_330]
0x180010671  call    std___Func_impl_no_alloc__lambda_b0a151323b3dba51a5a1a2a034a2ee0f__void____Move
0x180010676  mov     [rbp+2B0h+var_2B0], rax
0x18001067a  mov     rcx, [rbp+2B0h+var_2F8]
0x18001067e  test    rcx, rcx
0x180010681  jz      short loc_18001069D
0x180010683  mov     rax, [rcx]
0x180010686  lea     rdx, [rbp+2B0h+var_330]
0x18001068a  cmp     rcx, rdx
0x18001068d  setnz   dl
0x180010690  mov     rax, [rax+20h]
0x180010694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010699  mov     [rbp+2B0h+var_2F8], r14
0x18001069d  xor     edx, edx; unsigned int
0x18001069f  mov     rcx, rsi; struct RegistryHandleRAII *
0x1800106a2  call    ?WriteConnectionReferenceCount@@YAXAEAVRegistryHandleRAII@@K@Z; WriteConnectionReferenceCount(RegistryHandleRAII &,ulong)
0x1800106a7  xorps   xmm0, xmm0
0x1800106aa  movups  [rsp+3B0h+var_368+8], xmm0
0x1800106af  xorps   xmm1, xmm1
0x1800106b2  movdqu  [rsp+3B0h+var_358+8], xmm1
0x1800106b8  mov     edi, 0Eh
0x1800106bd  mov     r8d, edi
0x1800106c0  lea     rdx, ValueName; "CachedChangeID"
0x1800106c7  lea     rcx, [rsp+3B0h+var_368+8]
0x1800106cc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800106d1  nop
0x1800106d2  xor     r8d, r8d
0x1800106d5  lea     rdx, [rsp+3B0h+var_368+8]
0x1800106da  mov     rcx, rsi
0x1800106dd  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,ulong)
0x1800106e2  nop
0x1800106e3  lea     rcx, [rsp+3B0h+var_368+8]
0x1800106e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800106ed  xorps   xmm0, xmm0
0x1800106f0  movups  [rsp+3B0h+pExceptionObject+8], xmm0
0x1800106f5  xorps   xmm1, xmm1
0x1800106f8  movdqu  [rsp+3B0h+var_378+8], xmm1
0x1800106fe  lea     rax, [rbp+2B0h+var_29E]
0x180010702  inc     rbx
0x180010705  cmp     [rax+rbx*2], r14w
0x18001070a  jnz     short loc_180010702
0x18001070c  mov     r8, rbx
0x18001070f  lea     rdx, [rbp+2B0h+var_29E]
0x180010713  lea     rcx, [rsp+3B0h+pExceptionObject+8]
0x180010718  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001071d  nop
0x18001071e  xorps   xmm0, xmm0
0x180010721  movups  [rsp+3B0h+var_368+8], xmm0
0x180010726  xorps   xmm1, xmm1
0x180010729  movdqu  [rsp+3B0h+var_358+8], xmm1
0x18001072f  mov     r8, rdi
0x180010732  lea     rdx, aConnectionguid; "ConnectionGUID"
0x180010739  lea     rcx, [rsp+3B0h+var_368+8]
0x18001073e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010743  nop
0x180010744  mov     r9d, 1
0x18001074a  lea     r8, [rsp+3B0h+pExceptionObject+8]
0x18001074f  lea     rdx, [rsp+3B0h+var_368+8]
0x180010754  mov     rcx, rsi
0x180010757  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::wstring const &,ulong)
0x18001075c  nop
0x18001075d  lea     rcx, [rsp+3B0h+var_368+8]
0x180010762  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010767  nop
0x180010768  lea     rcx, [rsp+3B0h+pExceptionObject+8]
0x18001076d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010772  xor     r8d, r8d; bool
0x180010775  or      edx, 0FFFFFFFFh; unsigned int
0x180010778  mov     rcx, rsi; struct RegistryHandleRAII *
0x18001077b  call    ?UpdateConnectionStatusFlags@@YAXAEAVRegistryHandleRAII@@K_N@Z; UpdateConnectionStatusFlags(RegistryHandleRAII &,ulong,bool)
0x180010780  mov     [rbp+2B0h+var_2F0], 1
0x180010784  lea     rcx, [rbp+2B0h+var_2F0]; this
0x180010788  call    ??1CallOnException@@QEAA@XZ; CallOnException::~CallOnException(void)
0x18001078d  mov     rcx, [rbp+2B0h+var_20]
0x180010794  xor     rcx, rsp; StackCookie
0x180010797  call    __security_check_cookie
0x18001079c  lea     r11, [rsp+3B0h+var_10]
0x1800107a4  mov     rbx, [r11+28h]
0x1800107a8  mov     rsi, [r11+30h]
0x1800107ac  mov     rsp, r11
0x1800107af  pop     r14
0x1800107b1  pop     rdi
0x1800107b2  pop     rbp
0x1800107b3  retn
0x1800107b5  call    cs:__imp_GetLastError
0x1800107bc  nop     dword ptr [rax+rax+00h]
0x1800107c1  mov     ebx, eax
0x1800107c3  test    eax, eax
0x1800107c5  jle     short loc_1800107D0
0x1800107c7  movzx   ebx, ax
0x1800107ca  or      ebx, 80070000h
0x1800107d0  lea     rcx, WPP_GLOBAL_Control
0x1800107d7  mov     rax, cs:WPP_GLOBAL_Control
0x1800107de  cmp     rax, rcx
0x1800107e1  jz      short loc_180010801
0x1800107e3  test    byte ptr [rax+44h], 1
0x1800107e7  jz      short loc_180010801
0x1800107e9  mov     edx, 30h ; '0'
0x1800107ee  mov     r9d, ebx
0x1800107f1  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x1800107f8  mov     rcx, [rax+38h]
0x1800107fc  call    WPP_SF_d
0x180010801  mov     edx, ebx; int
0x180010803  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x180010808  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001080d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180010814  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x180010819  call    _CxxThrowException_0
0x18001081f  call    __report_rangecheckfailure
0x180010825  lea     rcx, WPP_GLOBAL_Control
0x18001082c  mov     r10, cs:WPP_GLOBAL_Control
0x180010833  cmp     r10, rcx
0x180010836  jz      short loc_180010857
0x180010838  test    byte ptr [r10+44h], 1
0x18001083d  jz      short loc_180010857
0x18001083f  mov     edx, 2Bh ; '+'
0x180010844  mov     r9d, ebx
0x180010847  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001084e  mov     rcx, [r10+38h]
0x180010852  call    WPP_SF_d
0x180010857  mov     edx, ebx; int
0x180010859  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x18001085e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180010863  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001086a  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x18001086f  call    _CxxThrowException_0
0x180010875  lea     rcx, WPP_GLOBAL_Control
0x18001087c  mov     rax, cs:WPP_GLOBAL_Control
0x180010883  cmp     rax, rcx
0x180010886  jz      short loc_1800108A6
0x180010888  test    byte ptr [rax+44h], 1
0x18001088c  jz      short loc_1800108A6
0x18001088e  mov     edx, 2Ch ; ','
0x180010893  mov     r9d, ebx
0x180010896  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001089d  mov     rcx, [rax+38h]
0x1800108a1  call    WPP_SF_d
0x1800108a6  mov     edx, ebx; int
0x1800108a8  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x1800108ad  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800108b2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800108b9  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x1800108be  call    _CxxThrowException_0
0x1800108c4  lea     rcx, WPP_GLOBAL_Control
0x1800108cb  mov     r10, cs:WPP_GLOBAL_Control
0x1800108d2  cmp     r10, rcx
0x1800108d5  jz      short loc_1800108F6
0x1800108d7  test    byte ptr [r10+44h], 1
0x1800108dc  jz      short loc_1800108F6
0x1800108de  mov     edx, 2Dh ; '-'
0x1800108e3  mov     r9d, ebx
0x1800108e6  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x1800108ed  mov     rcx, [r10+38h]
0x1800108f1  call    WPP_SF_d
0x1800108f6  mov     edx, ebx; int
0x1800108f8  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x1800108fd  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180010902  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180010909  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x18001090e  call    _CxxThrowException_0
0x180010914  lea     rcx, WPP_GLOBAL_Control
0x18001091b  mov     ebx, 8007000Eh
0x180010920  mov     rax, cs:WPP_GLOBAL_Control
0x180010927  cmp     rax, rcx
0x18001092a  jz      short loc_18001094A
0x18001092c  test    byte ptr [rax+44h], 1
0x180010930  jz      short loc_18001094A
0x180010932  mov     edx, 2Eh ; '.'
0x180010937  mov     r9d, ebx
0x18001093a  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180010941  mov     rcx, [rax+38h]
0x180010945  call    WPP_SF_d
0x18001094a  mov     edx, ebx; int
0x18001094c  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x180010951  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180010956  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001095d  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x180010962  call    _CxxThrowException_0
0x180010968  lea     rcx, WPP_GLOBAL_Control
0x18001096f  mov     r10, cs:WPP_GLOBAL_Control
0x180010976  cmp     r10, rcx
0x180010979  jz      short loc_18001099A
0x18001097b  test    byte ptr [r10+44h], 1
0x180010980  jz      short loc_18001099A
0x180010982  mov     edx, 2Fh ; '/'
0x180010987  mov     r9d, edi
0x18001098a  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180010991  mov     rcx, [r10+38h]
0x180010995  call    WPP_SF_d
0x18001099a  mov     edx, edi; int
0x18001099c  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x1800109a1  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800109a6  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800109ad  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x1800109b2  call    _CxxThrowException_0
```
