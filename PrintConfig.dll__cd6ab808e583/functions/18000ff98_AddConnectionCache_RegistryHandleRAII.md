# AddConnectionCache(RegistryHandleRAII &)

- ea: `0x18000ff98`
- end: `0x18001044f`
- name: `?AddConnectionCache@@YAXAEAVRegistryHandleRAII@@@Z`
- size: `1207`
- prototype: `void __fastcall(struct RegistryHandleRAII *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800147b8`

## callees

- `0x1800032e0`
- `0x180003af0`
- `0x180004418`
- `0x180004424`
- `0x18000be0c`
- `0x18000da28`
- `0x18000f380`
- `0x18000f590`
- `0x18000f8d4`
- `0x18000ff98`
- `0x180017b18`
- `0x180018314`
- `0x180018590`
- `0x180018bbc`
- `0x180036ad8`
- `0x180036cc0`
- `0x180152bd4`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18001000f`
- `KERNEL32!CreateDirectoryW` at `0x1800100ca`
- `KERNEL32!CreateDirectoryW` at `0x18001000f`
- `KERNEL32!CreateDirectoryW` at `0x1800100ca`
- `KERNEL32!GetLastError` at `0x180010019`
- `KERNEL32!GetLastError` at `0x180010252`
- `KERNEL32!GetLastError` at `0x180010019`
- `KERNEL32!GetLastError` at `0x180010252`
- `ole32!CoCreateGuid` at `0x18001004a`
- `ole32!CoCreateGuid` at `0x18001004a`
- `ole32!StringFromGUID2` at `0x180010069`
- `ole32!StringFromGUID2` at `0x180010069`

## string_xrefs

- `0x18001015e`: `CachedChangeID`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall AddConnectionCache(struct RegistryHandleRAII *a1)
{
  int V4SharingRoot; // eax
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
  signed int v14; // eax
  unsigned int v15; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v17; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+68h] [rbp-A0h]
  GUID pguid_8; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v20[7]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v21; // [rsp+C0h] [rbp-48h]
  char v22[8]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v23[56]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v24; // [rsp+108h] [rbp+0h]
  OLECHAR sz; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 v26[55]; // [rsp+11Ah] [rbp+12h] BYREF
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
        43,
        WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
        (unsigned int)V4SharingRoot);
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
            44,
            WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
            (unsigned int)v5);
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
        45,
        WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
        (unsigned int)v6);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v7);
    throw (hr_error *)&pExceptionObject[8];
  }
  if ( !StringFromGUID2(&pguid_8, &sz, 50) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, 2147942414LL);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], -2147024882);
    throw (hr_error *)&pExceptionObject[8];
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v26[v9 - 1] );
  v10 = 2 * v9 - 2;
  if ( v10 >= 0x64 )
    _report_rangecheckfailure(v10);
  *(unsigned __int16 *)((char *)&v26[-1] + v10) = 0;
  v11 = StringCchCatW(PathName, 0x104u, v26);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        47,
        WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
        (unsigned int)v11);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v12);
    throw (hr_error *)&pExceptionObject[8];
  }
  if ( !CreateDirectoryW(PathName, 0) )
  {
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v15);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject[8], v15);
    throw (hr_error *)&pExceptionObject[8];
  }
  v20[0] = off_1801C4358;
  v20[1] = PathName;
  v21 = v20;
  v22[0] = 0;
  v24 = 0;
  v24 = std::_Func_impl_no_alloc__lambda_b0a151323b3dba51a5a1a2a034a2ee0f__void_::_Move(v20, v23);
  if ( v21 )
  {
    v13 = v20;
    LOBYTE(v13) = v21 != v20;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v13);
    v21 = 0;
  }
  WriteConnectionReferenceCount(a1, 0);
  v17 = 0;
  v18 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v17, L"CachedChangeID", 0xEu);
  Win32Adapters::Registry::RegSetValueW(a1, &v17, 0);
  std::wstring::~wstring(&v17);
  memset(&pExceptionObject[8], 0, 32);
  do
    ++v8;
  while ( v26[v8] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&pExceptionObject[8], v26, v8);
  v17 = 0;
  v18 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v17, L"ConnectionGUID", 0xEu);
  Win32Adapters::Registry::RegSetValueW(a1, &v17, &pExceptionObject[8], 1);
  std::wstring::~wstring(&v17);
  std::wstring::~wstring(&pExceptionObject[8]);
  UpdateConnectionStatusFlags(a1, 0xFFFFFFFF, 0);
  v22[0] = 1;
  CallOnException::~CallOnException((CallOnException *)v22);
}

```

## disassembly

```asm
0x18000ff98  mov     rax, rsp
0x18000ff9b  push    rbp
0x18000ff9c  push    rdi
0x18000ff9d  push    r14
0x18000ff9f  lea     rbp, [rax-2B8h]
0x18000ffa6  sub     rsp, 3A0h
0x18000ffad  mov     [rsp+3B0h+var_390], 0FFFFFFFFFFFFFFFEh
0x18000ffb6  mov     [rax+10h], rbx
0x18000ffba  mov     [rax+18h], rsi
0x18000ffbe  mov     rax, cs:__security_cookie
0x18000ffc5  xor     rax, rsp
0x18000ffc8  mov     [rbp+2B0h+var_20], rax
0x18000ffcf  mov     rsi, rcx
0x18000ffd2  xor     edx, edx; Val
0x18000ffd4  mov     r8d, 208h; Size
0x18000ffda  lea     rcx, [rbp+2B0h+PathName]; void *
0x18000ffe1  call    memset_0
0x18000ffe6  mov     edi, 104h
0x18000ffeb  mov     edx, edi; unsigned int
0x18000ffed  lea     rcx, [rbp+2B0h+PathName]; unsigned __int16 *
0x18000fff4  call    ?GetV4SharingRoot@@YAJPEAGK@Z; GetV4SharingRoot(ushort *,ulong)
0x18000fff9  mov     ebx, eax
0x18000fffb  xor     r14d, r14d
0x18000fffe  test    eax, eax
0x180010000  js      loc_1800102BC
0x180010006  xor     edx, edx; lpSecurityAttributes
0x180010008  lea     rcx, [rbp+2B0h+PathName]; lpPathName
0x18001000f  call    cs:__imp_CreateDirectoryW
0x180010015  test    eax, eax
0x180010017  jnz     short loc_18001003D
0x180010019  call    cs:__imp_GetLastError
0x18001001f  mov     ebx, eax
0x180010021  cmp     eax, 0B7h
0x180010026  jz      short loc_18001003D
0x180010028  test    eax, eax
0x18001002a  jle     short loc_180010035
0x18001002c  movzx   ebx, ax
0x18001002f  or      ebx, 80070000h
0x180010035  test    ebx, ebx
0x180010037  js      loc_18001030C
0x18001003d  xorps   xmm0, xmm0
0x180010040  movups  xmmword ptr [rsp+3B0h+pguid+8], xmm0
0x180010045  lea     rcx, [rsp+3B0h+pguid+8]; pguid
0x18001004a  call    cs:__imp_CoCreateGuid
0x180010050  mov     ebx, eax
0x180010052  test    eax, eax
0x180010054  js      loc_18001035B
0x18001005a  mov     r8d, 32h ; '2'; cchMax
0x180010060  lea     rdx, [rbp+2B0h+sz]; lpsz
0x180010064  lea     rcx, [rsp+3B0h+pguid+8]; rguid
0x180010069  call    cs:__imp_StringFromGUID2
0x18001006f  test    eax, eax
0x180010071  jz      loc_1800103AB
0x180010077  lea     rcx, [rbp+2B0h+sz]
0x18001007b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001007f  mov     rax, rbx
0x180010082  inc     rax
0x180010085  cmp     [rcx+rax*2], r14w
0x18001008a  jnz     short loc_180010082
0x18001008c  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180010094  cmp     rcx, 64h ; 'd'
0x180010098  jnb     loc_1800102B6
0x18001009e  mov     [rbp+rcx+2B0h+sz], r14w
0x1800100a4  lea     r8, [rbp+2B0h+var_29E]; unsigned __int16 *
0x1800100a8  mov     rdx, rdi; unsigned __int64
0x1800100ab  lea     rcx, [rbp+2B0h+PathName]; unsigned __int16 *
0x1800100b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800100b7  mov     edi, eax
0x1800100b9  test    eax, eax
0x1800100bb  js      loc_1800103FF
0x1800100c1  xor     edx, edx; lpSecurityAttributes
0x1800100c3  lea     rcx, [rbp+2B0h+PathName]; lpPathName
0x1800100ca  call    cs:__imp_CreateDirectoryW
0x1800100d0  test    eax, eax
0x1800100d2  jz      loc_180010252
0x1800100d8  lea     rax, off_1801C4358
0x1800100df  mov     [rbp+2B0h+var_330], rax
0x1800100e3  lea     rax, [rbp+2B0h+PathName]
0x1800100ea  mov     [rbp+2B0h+var_328], rax
0x1800100ee  lea     rax, [rbp+2B0h+var_330]
0x1800100f2  mov     [rbp+2B0h+var_2F8], rax
0x1800100f6  mov     [rbp+2B0h+var_2F0], r14b
0x1800100fa  lea     rax, [rbp+2B0h+var_2E8]
0x1800100fe  mov     qword ptr [rsp+3B0h+pExceptionObject], rax
0x180010103  mov     [rbp+2B0h+var_2B0], r14
0x180010107  lea     rdx, [rbp+2B0h+var_2E8]
0x18001010b  lea     rcx, [rbp+2B0h+var_330]
0x18001010f  call    std___Func_impl_no_alloc__lambda_b0a151323b3dba51a5a1a2a034a2ee0f__void____Move
0x180010114  mov     [rbp+2B0h+var_2B0], rax
0x180010118  mov     rcx, [rbp+2B0h+var_2F8]
0x18001011c  test    rcx, rcx
0x18001011f  jz      short loc_18001013B
0x180010121  mov     rax, [rcx]
0x180010124  lea     rdx, [rbp+2B0h+var_330]
0x180010128  cmp     rcx, rdx
0x18001012b  setnz   dl
0x18001012e  mov     rax, [rax+20h]
0x180010132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010137  mov     [rbp+2B0h+var_2F8], r14
0x18001013b  xor     edx, edx; unsigned int
0x18001013d  mov     rcx, rsi; struct RegistryHandleRAII *
0x180010140  call    ?WriteConnectionReferenceCount@@YAXAEAVRegistryHandleRAII@@K@Z; WriteConnectionReferenceCount(RegistryHandleRAII &,ulong)
0x180010145  xorps   xmm0, xmm0
0x180010148  movups  [rsp+3B0h+var_368+8], xmm0
0x18001014d  xorps   xmm1, xmm1
0x180010150  movdqu  [rsp+3B0h+var_358+8], xmm1
0x180010156  mov     edi, 0Eh
0x18001015b  mov     r8d, edi
0x18001015e  lea     rdx, ValueName; "CachedChangeID"
0x180010165  lea     rcx, [rsp+3B0h+var_368+8]
0x18001016a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001016f  nop
0x180010170  xor     r8d, r8d
0x180010173  lea     rdx, [rsp+3B0h+var_368+8]
0x180010178  mov     rcx, rsi
0x18001017b  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,ulong)
0x180010180  nop
0x180010181  lea     rcx, [rsp+3B0h+var_368+8]
0x180010186  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001018b  xorps   xmm0, xmm0
0x18001018e  movups  [rsp+3B0h+pExceptionObject+8], xmm0
0x180010193  xorps   xmm1, xmm1
0x180010196  movdqu  [rsp+3B0h+var_378+8], xmm1
0x18001019c  lea     rax, [rbp+2B0h+var_29E]
0x1800101a0  inc     rbx
0x1800101a3  cmp     [rax+rbx*2], r14w
0x1800101a8  jnz     short loc_1800101A0
0x1800101aa  mov     r8, rbx
0x1800101ad  lea     rdx, [rbp+2B0h+var_29E]
0x1800101b1  lea     rcx, [rsp+3B0h+pExceptionObject+8]
0x1800101b6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800101bb  nop
0x1800101bc  xorps   xmm0, xmm0
0x1800101bf  movups  [rsp+3B0h+var_368+8], xmm0
0x1800101c4  xorps   xmm1, xmm1
0x1800101c7  movdqu  [rsp+3B0h+var_358+8], xmm1
0x1800101cd  mov     r8, rdi
0x1800101d0  lea     rdx, aConnectionguid; "ConnectionGUID"
0x1800101d7  lea     rcx, [rsp+3B0h+var_368+8]
0x1800101dc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800101e1  nop
0x1800101e2  mov     r9d, 1
0x1800101e8  lea     r8, [rsp+3B0h+pExceptionObject+8]
0x1800101ed  lea     rdx, [rsp+3B0h+var_368+8]
0x1800101f2  mov     rcx, rsi
0x1800101f5  call    ?RegSetValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Win32Adapters::Registry::RegSetValueW(RegistryHandleRAII &,std::wstring const &,std::wstring const &,ulong)
0x1800101fa  nop
0x1800101fb  lea     rcx, [rsp+3B0h+var_368+8]
0x180010200  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010205  nop
0x180010206  lea     rcx, [rsp+3B0h+pExceptionObject+8]
0x18001020b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010210  xor     r8d, r8d; bool
0x180010213  or      edx, 0FFFFFFFFh; unsigned int
0x180010216  mov     rcx, rsi; struct RegistryHandleRAII *
0x180010219  call    ?UpdateConnectionStatusFlags@@YAXAEAVRegistryHandleRAII@@K_N@Z; UpdateConnectionStatusFlags(RegistryHandleRAII &,ulong,bool)
0x18001021e  mov     [rbp+2B0h+var_2F0], 1
0x180010222  lea     rcx, [rbp+2B0h+var_2F0]; this
0x180010226  call    ??1CallOnException@@QEAA@XZ; CallOnException::~CallOnException(void)
0x18001022b  mov     rcx, [rbp+2B0h+var_20]
0x180010232  xor     rcx, rsp; StackCookie
0x180010235  call    __security_check_cookie
0x18001023a  lea     r11, [rsp+3B0h+var_10]
0x180010242  mov     rbx, [r11+28h]
0x180010246  mov     rsi, [r11+30h]
0x18001024a  mov     rsp, r11
0x18001024d  pop     r14
0x18001024f  pop     rdi
0x180010250  pop     rbp
0x180010251  retn
0x180010252  call    cs:__imp_GetLastError
0x180010258  mov     ebx, eax
0x18001025a  test    eax, eax
0x18001025c  jle     short loc_180010267
0x18001025e  movzx   ebx, ax
0x180010261  or      ebx, 80070000h
0x180010267  lea     rcx, WPP_GLOBAL_Control
0x18001026e  mov     rax, cs:WPP_GLOBAL_Control
0x180010275  cmp     rax, rcx
0x180010278  jz      short loc_180010298
0x18001027a  test    byte ptr [rax+44h], 1
0x18001027e  jz      short loc_180010298
0x180010280  mov     edx, 30h ; '0'
0x180010285  mov     r9d, ebx
0x180010288  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18001028f  mov     rcx, [rax+38h]
0x180010293  call    WPP_SF_d
0x180010298  mov     edx, ebx; int
0x18001029a  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x18001029f  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800102a4  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800102ab  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x1800102b0  call    _CxxThrowException_0
0x1800102b6  call    __report_rangecheckfailure
0x1800102bc  lea     rcx, WPP_GLOBAL_Control
0x1800102c3  mov     r10, cs:WPP_GLOBAL_Control
0x1800102ca  cmp     r10, rcx
0x1800102cd  jz      short loc_1800102EE
0x1800102cf  test    byte ptr [r10+44h], 1
0x1800102d4  jz      short loc_1800102EE
0x1800102d6  mov     edx, 2Bh ; '+'
0x1800102db  mov     r9d, ebx
0x1800102de  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x1800102e5  mov     rcx, [r10+38h]
0x1800102e9  call    WPP_SF_d
0x1800102ee  mov     edx, ebx; int
0x1800102f0  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x1800102f5  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800102fa  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180010301  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x180010306  call    _CxxThrowException_0
0x18001030c  lea     rcx, WPP_GLOBAL_Control
0x180010313  mov     rax, cs:WPP_GLOBAL_Control
0x18001031a  cmp     rax, rcx
0x18001031d  jz      short loc_18001033D
0x18001031f  test    byte ptr [rax+44h], 1
0x180010323  jz      short loc_18001033D
0x180010325  mov     edx, 2Ch ; ','
0x18001032a  mov     r9d, ebx
0x18001032d  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180010334  mov     rcx, [rax+38h]
0x180010338  call    WPP_SF_d
0x18001033d  mov     edx, ebx; int
0x18001033f  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x180010344  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180010349  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180010350  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x180010355  call    _CxxThrowException_0
0x18001035b  lea     rcx, WPP_GLOBAL_Control
0x180010362  mov     r10, cs:WPP_GLOBAL_Control
0x180010369  cmp     r10, rcx
0x18001036c  jz      short loc_18001038D
0x18001036e  test    byte ptr [r10+44h], 1
0x180010373  jz      short loc_18001038D
0x180010375  mov     edx, 2Dh ; '-'
0x18001037a  mov     r9d, ebx
0x18001037d  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180010384  mov     rcx, [r10+38h]
0x180010388  call    WPP_SF_d
0x18001038d  mov     edx, ebx; int
0x18001038f  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x180010394  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180010399  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800103a0  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x1800103a5  call    _CxxThrowException_0
0x1800103ab  lea     rcx, WPP_GLOBAL_Control
0x1800103b2  mov     ebx, 8007000Eh
0x1800103b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800103be  cmp     rax, rcx
0x1800103c1  jz      short loc_1800103E1
0x1800103c3  test    byte ptr [rax+44h], 1
0x1800103c7  jz      short loc_1800103E1
0x1800103c9  mov     edx, 2Eh ; '.'
0x1800103ce  mov     r9d, ebx
0x1800103d1  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x1800103d8  mov     rcx, [rax+38h]
0x1800103dc  call    WPP_SF_d
0x1800103e1  mov     edx, ebx; int
0x1800103e3  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x1800103e8  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800103ed  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800103f4  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x1800103f9  call    _CxxThrowException_0
0x1800103ff  lea     rcx, WPP_GLOBAL_Control
0x180010406  mov     r10, cs:WPP_GLOBAL_Control
0x18001040d  cmp     r10, rcx
0x180010410  jz      short loc_180010431
0x180010412  test    byte ptr [r10+44h], 1
0x180010417  jz      short loc_180010431
0x180010419  mov     edx, 2Fh ; '/'
0x18001041e  mov     r9d, edi
0x180010421  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180010428  mov     rcx, [r10+38h]
0x18001042c  call    WPP_SF_d
0x180010431  mov     edx, edi; int
0x180010433  lea     rcx, [rsp+3B0h+pExceptionObject+8]; this
0x180010438  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001043d  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180010444  lea     rcx, [rsp+3B0h+pExceptionObject+8]; pExceptionObject
0x180010449  call    _CxxThrowException_0
```
