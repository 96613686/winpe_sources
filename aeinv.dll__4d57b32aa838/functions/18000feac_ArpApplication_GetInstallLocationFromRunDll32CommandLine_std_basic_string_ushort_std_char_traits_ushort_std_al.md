# ArpApplication::GetInstallLocationFromRunDll32CommandLine(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000feac`
- end: `0x1800101fd`
- name: `?GetInstallLocationFromRunDll32CommandLine@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `849`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003d33c`

## callees

- `0x18000e780`
- `0x18000feac`
- `0x1800118d0`
- `0x1800175b0`
- `0x180018300`
- `0x180018450`
- `0x180018a60`
- `0x180018ff4`
- `0x1800197d4`
- `0x18001becc`
- `0x18001ccfc`
- `0x1800404c4`
- `0x180040500`
- `0x180045468`
- `0x180046c78`
- `0x1800512b4`
- `0x180051410`
- `0x180059920`
- `0x180069330`
- `0x18012549c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180010112`
- `KERNEL32!GetFileAttributesW` at `0x180010112`

## string_xrefs

- `0x18000ffcf`: `rundll32.exe`
- `0x18001002d`: `rundll32`
- `0x18001018e`: `Rundll32 command line: %ws -> %ws`
- `0x18001019b`: `ArpApplication::GetInstallLocationFromRunDll32CommandLine`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ArpApplication::GetInstallLocationFromRunDll32CommandLine(__int64 a1)
{
  __int64 v2; // rdx
  LPCWSTR *v3; // rax
  LPCWSTR *v4; // rcx
  char *v5; // r14
  const WCHAR *v6; // rdx
  __int64 traits_2_0_unsigned_short; // rax
  __int64 v8; // r11
  __int64 v9; // rdx
  LPCWSTR *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // r14
  LPCWSTR *v13; // rax
  __int64 v14; // rbx
  __int128 *v15; // r9
  LPCWSTR *v16; // rcx
  __int64 v17; // rax
  LPCWSTR *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 LongPath; // rax
  const WCHAR *v25; // rcx
  DWORD FileAttributesW; // eax
  __int64 last_of; // rax
  __int64 v28; // rax
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v31; // [rsp+60h] [rbp-31h]
  unsigned __int64 v32; // [rsp+68h] [rbp-29h]
  __int128 v33; // [rsp+70h] [rbp-21h] BYREF
  __int64 v34; // [rsp+80h] [rbp-11h]
  unsigned __int64 v35; // [rsp+88h] [rbp-9h]
  _OWORD v36[2]; // [rsp+90h] [rbp-1h] BYREF
  _BYTE v37[32]; // [rsp+B0h] [rbp+1Fh] BYREF

  memset(v36, 0, sizeof(v36));
  std::wstring::_Construct_empty(v36);
  Utility::ToLower(lpFileName, v2);
  v3 = lpFileName;
  v4 = (LPCWSTR *)lpFileName[0];
  if ( v32 > 7 )
    v3 = (LPCWSTR *)lpFileName[0];
  v5 = (char *)v3 + 2 * v31;
  if ( v32 > 7 )
  {
    v6 = &lpFileName[0][v31];
  }
  else
  {
    v6 = (const WCHAR *)lpFileName + v31;
    v4 = lpFileName;
  }
  traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                v4,
                                v6,
                                34);
  v8 = traits_2_0_unsigned_short;
  if ( traits_2_0_unsigned_short != v9 )
    v8 = _std_remove_2(traits_2_0_unsigned_short);
  v10 = lpFileName;
  if ( v32 > 7 )
    v10 = (LPCWSTR *)lpFileName[0];
  v11 = (v8 - (__int64)v10) >> 1;
  v12 = (__int64)&v5[-v8] >> 1;
  if ( v31 - v11 < v12 )
    v12 = v31 - v11;
  v13 = lpFileName;
  if ( v32 > 7 )
    v13 = (LPCWSTR *)lpFileName[0];
  v14 = v31 - v12;
  memmove_0((char *)v13 + 2 * v11, (char *)v13 + 2 * v11 + 2 * v12, 2 * (v31 - v12 - v11) + 2);
  v31 = v14;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v33);
  v15 = &v33;
  if ( v35 > 7 )
    LODWORD(v15) = v33;
  v16 = lpFileName;
  if ( v32 > 7 )
    LODWORD(v16) = lpFileName[0];
  v17 = std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)v16, v31, 0, (_DWORD)v15, v34);
  v18 = lpFileName;
  if ( v17 )
  {
    if ( v32 > 7 )
      LODWORD(v18) = lpFileName[0];
    if ( std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)v18, v31, 0, (unsigned int)L"rundll32", 8) )
    {
      std::wstring::wstring(a1, &byte_1801389F0);
      goto LABEL_32;
    }
    v19 = v34 - 4;
  }
  else
  {
    v19 = v34;
  }
  v20 = std::wstring::substr(lpFileName, v37, v19, -1);
  std::wstring::operator=(lpFileName, v20);
  std::wstring::~wstring(v37);
  v21 = Utility::TrimSpace(lpFileName);
  std::wstring::operator=(lpFileName, v21);
  v22 = std::wstring::find(lpFileName, 44);
  if ( v22 != -1 )
  {
    v23 = std::wstring::substr(lpFileName, v37, 0, v22);
    std::wstring::operator=(lpFileName, v23);
    std::wstring::~wstring(v37);
    LongPath = Utility::GetLongPath(v37, lpFileName);
    std::wstring::operator=(lpFileName, LongPath);
    std::wstring::~wstring(v37);
    v25 = (const WCHAR *)lpFileName;
    if ( v32 > 7 )
      v25 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v25);
    if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
    {
      last_of = std::wstring::find_last_of(lpFileName, 92);
      v28 = std::wstring::substr(lpFileName, v37, 0, last_of);
      std::wstring::operator=(lpFileName, v28);
      std::wstring::~wstring(v37);
      std::wstring::operator=(v36, lpFileName);
      AslLogCallPrintf(
        3,
        (unsigned int)"ArpApplication::GetInstallLocationFromRunDll32CommandLine",
        1103,
        (unsigned int)"Rundll32 command line: %ws -> %ws");
    }
  }
  std::wstring::wstring(a1, v36);
LABEL_32:
  std::wstring::~wstring(&v33);
  std::wstring::~wstring(lpFileName);
  std::wstring::~wstring(v36);
  return a1;
}

```

## disassembly

```asm
0x18000feac  mov     rax, rsp
0x18000feaf  push    rbp
0x18000feb0  push    rdi
0x18000feb1  push    r14
0x18000feb3  lea     rbp, [rax-5Fh]
0x18000feb7  sub     rsp, 0D0h
0x18000febe  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18000fec6  mov     [rax+18h], rbx
0x18000feca  mov     [rax+20h], rsi
0x18000fece  mov     rax, cs:__security_cookie
0x18000fed5  xor     rax, rsp
0x18000fed8  mov     [rbp+57h+var_18], rax
0x18000fedc  mov     rsi, rdx
0x18000fedf  mov     rdi, rcx
0x18000fee2  mov     [rbp+57h+var_A0], rcx
0x18000fee6  xorps   xmm0, xmm0
0x18000fee9  movups  [rbp+57h+var_58], xmm0
0x18000feed  xorps   xmm1, xmm1
0x18000fef0  movdqu  [rbp+57h+var_48], xmm1
0x18000fef5  lea     rcx, [rbp+57h+var_58]
0x18000fef9  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000fefe  nop
0x18000feff  lea     rcx, [rbp+57h+lpFileName]
0x18000ff03  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18000ff08  nop
0x18000ff09  lea     rax, [rbp+57h+lpFileName]
0x18000ff0d  mov     rcx, [rbp+57h+lpFileName]
0x18000ff11  cmp     [rbp+57h+var_80], 7
0x18000ff16  cmova   rax, rcx
0x18000ff1a  mov     rdx, [rbp+57h+var_88]
0x18000ff1e  lea     r14, [rax+rdx*2]
0x18000ff22  ja      short loc_18000FF32
0x18000ff24  lea     rax, [rbp+57h+lpFileName]
0x18000ff28  lea     rdx, [rax+rdx*2]
0x18000ff2c  lea     rcx, [rbp+57h+lpFileName]
0x18000ff30  jmp     short loc_18000FF36
0x18000ff32  lea     rdx, [rcx+rdx*2]
0x18000ff36  mov     r8d, 22h ; '"'
0x18000ff3c  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x18000ff41  mov     r11, rax
0x18000ff44  cmp     rax, rdx
0x18000ff47  jz      short loc_18000FF54
0x18000ff49  mov     rcx, rax
0x18000ff4c  call    __std_remove_2
0x18000ff51  mov     r11, rax
0x18000ff54  lea     rax, [rbp+57h+lpFileName]
0x18000ff58  cmp     [rbp+57h+var_80], 7
0x18000ff5d  cmova   rax, [rbp+57h+lpFileName]
0x18000ff62  mov     rdx, r11
0x18000ff65  sub     rdx, rax
0x18000ff68  sar     rdx, 1
0x18000ff6b  sub     r14, r11
0x18000ff6e  sar     r14, 1
0x18000ff71  mov     rbx, [rbp+57h+var_88]
0x18000ff75  mov     rax, rbx
0x18000ff78  sub     rax, rdx
0x18000ff7b  cmp     rax, r14
0x18000ff7e  cmovb   r14, rax
0x18000ff82  lea     rax, [rbp+57h+lpFileName]
0x18000ff86  cmp     [rbp+57h+var_80], 7
0x18000ff8b  cmova   rax, [rbp+57h+lpFileName]
0x18000ff90  lea     rcx, [rax+rdx*2]; void *
0x18000ff94  sub     rbx, r14
0x18000ff97  mov     r8, rbx
0x18000ff9a  sub     r8, rdx
0x18000ff9d  lea     r8, ds:2[r8*2]; Size
0x18000ffa5  lea     rdx, [rcx+r14*2]; Src
0x18000ffa9  call    memmove_0
0x18000ffae  mov     [rbp+57h+var_88], rbx
0x18000ffb2  xorps   xmm0, xmm0
0x18000ffb5  movups  [rbp+57h+var_78], xmm0
0x18000ffb9  mov     [rbp+57h+var_68], 0
0x18000ffc1  mov     [rbp+57h+var_60], 0
0x18000ffc9  mov     r8d, 0Ch
0x18000ffcf  lea     rdx, aRundll32Exe; "rundll32.exe"
0x18000ffd6  lea     rcx, [rbp+57h+var_78]
0x18000ffda  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ffdf  nop
0x18000ffe0  mov     rax, [rbp+57h+var_68]
0x18000ffe4  lea     r9, [rbp+57h+var_78]
0x18000ffe8  cmp     [rbp+57h+var_60], 7
0x18000ffed  cmova   r9, qword ptr [rbp+57h+var_78]
0x18000fff2  lea     rcx, [rbp+57h+lpFileName]
0x18000fff6  cmp     [rbp+57h+var_80], 7
0x18000fffb  cmova   rcx, [rbp+57h+lpFileName]
0x180010000  mov     [rsp+0E0h+var_C0], rax
0x180010005  xor     r8d, r8d
0x180010008  mov     rdx, [rbp+57h+var_88]
0x18001000c  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180010011  lea     rcx, [rbp+57h+lpFileName]
0x180010015  test    rax, rax
0x180010018  jz      short loc_180010067
0x18001001a  cmp     [rbp+57h+var_80], 7
0x18001001f  cmova   rcx, [rbp+57h+lpFileName]
0x180010024  mov     [rsp+0E0h+var_C0], 8
0x18001002d  lea     r9, aRundll32; "rundll32"
0x180010034  xor     r8d, r8d
0x180010037  mov     rdx, [rbp+57h+var_88]
0x18001003b  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180010040  test    rax, rax
0x180010043  jz      short loc_180010059
0x180010045  lea     rdx, byte_1801389F0
0x18001004c  mov     rcx, rdi
0x18001004f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010054  jmp     loc_1800101B9
0x180010059  mov     r8, [rbp+57h+var_68]
0x18001005d  add     r8, 0FFFFFFFFFFFFFFFCh
0x180010061  lea     rcx, [rbp+57h+lpFileName]
0x180010065  jmp     short loc_18001006B
0x180010067  mov     r8, [rbp+57h+var_68]
0x18001006b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001006f  lea     rdx, [rbp+57h+var_38]
0x180010073  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180010078  mov     rdx, rax
0x18001007b  lea     rcx, [rbp+57h+lpFileName]
0x18001007f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010084  lea     rcx, [rbp+57h+var_38]
0x180010088  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001008d  lea     rcx, [rbp+57h+lpFileName]
0x180010091  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x180010096  mov     rdx, rax
0x180010099  lea     rcx, [rbp+57h+lpFileName]
0x18001009d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800100a2  mov     edx, 2Ch ; ','
0x1800100a7  lea     rcx, [rbp+57h+lpFileName]
0x1800100ab  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x1800100b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800100b4  jz      loc_1800101AC
0x1800100ba  mov     r9, rax
0x1800100bd  xor     r8d, r8d
0x1800100c0  lea     rdx, [rbp+57h+var_38]
0x1800100c4  lea     rcx, [rbp+57h+lpFileName]
0x1800100c8  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800100cd  mov     rdx, rax
0x1800100d0  lea     rcx, [rbp+57h+lpFileName]
0x1800100d4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800100d9  lea     rcx, [rbp+57h+var_38]
0x1800100dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800100e2  lea     rdx, [rbp+57h+lpFileName]
0x1800100e6  lea     rcx, [rbp+57h+var_38]
0x1800100ea  call    ?GetLongPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetLongPath(std::wstring const &)
0x1800100ef  mov     rdx, rax
0x1800100f2  lea     rcx, [rbp+57h+lpFileName]
0x1800100f6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800100fb  lea     rcx, [rbp+57h+var_38]
0x1800100ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010104  lea     rcx, [rbp+57h+lpFileName]
0x180010108  cmp     [rbp+57h+var_80], 7
0x18001010d  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180010112  call    cs:__imp_GetFileAttributesW
0x180010118  cmp     eax, 0FFFFFFFFh
0x18001011b  jz      loc_1800101AC
0x180010121  test    al, 10h
0x180010123  jnz     loc_1800101AC
0x180010129  mov     edx, 5Ch ; '\'
0x18001012e  lea     rcx, [rbp+57h+lpFileName]
0x180010132  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x180010137  mov     r9, rax
0x18001013a  xor     r8d, r8d
0x18001013d  lea     rdx, [rbp+57h+var_38]
0x180010141  lea     rcx, [rbp+57h+lpFileName]
0x180010145  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18001014a  mov     rdx, rax
0x18001014d  lea     rcx, [rbp+57h+lpFileName]
0x180010151  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010156  lea     rcx, [rbp+57h+var_38]
0x18001015a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001015f  lea     rdx, [rbp+57h+lpFileName]
0x180010163  lea     rcx, [rbp+57h+var_58]
0x180010167  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001016c  lea     rax, [rbp+57h+var_58]
0x180010170  cmp     qword ptr [rbp+57h+var_48+8], 7
0x180010175  cmova   rax, qword ptr [rbp+57h+var_58]
0x18001017a  cmp     qword ptr [rsi+18h], 7
0x18001017f  jbe     short loc_180010184
0x180010181  mov     rsi, [rsi]
0x180010184  mov     [rsp+0E0h+var_B8], rax
0x180010189  mov     [rsp+0E0h+var_C0], rsi
0x18001018e  lea     r9, aRundll32Comman; "Rundll32 command line: %ws -> %ws"
0x180010195  mov     r8d, 44Fh
0x18001019b  lea     rdx, aArpapplication_1; "ArpApplication::GetInstallLocationFromR"...
0x1800101a2  mov     ecx, 3
0x1800101a7  call    AslLogCallPrintf
0x1800101ac  lea     rdx, [rbp+57h+var_58]
0x1800101b0  mov     rcx, rdi
0x1800101b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800101b8  nop
0x1800101b9  lea     rcx, [rbp+57h+var_78]
0x1800101bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800101c2  nop
0x1800101c3  lea     rcx, [rbp+57h+lpFileName]
0x1800101c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800101cc  nop
0x1800101cd  lea     rcx, [rbp+57h+var_58]
0x1800101d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800101d6  mov     rax, rdi
0x1800101d9  mov     rcx, [rbp+57h+var_18]
0x1800101dd  xor     rcx, rsp; StackCookie
0x1800101e0  call    __security_check_cookie
0x1800101e5  lea     r11, [rsp+0E0h+var_10]
0x1800101ed  mov     rbx, [r11+30h]
0x1800101f1  mov     rsi, [r11+38h]
0x1800101f5  mov     rsp, r11
0x1800101f8  pop     r14
0x1800101fa  pop     rdi
0x1800101fb  pop     rbp
0x1800101fc  retn
```
