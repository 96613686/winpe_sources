# WaasMedic::MockSettingsProvider::GetSettingString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x180024080`
- end: `0x180024359`
- name: `?GetSettingString@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x180023860`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000cbfc`
- `0x180010db4`
- `0x18001d650`
- `0x180023d10`
- `0x180024080`
- `0x18002a300`
- `0x18002a4e4`
- `0x180034964`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002418c`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002418c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800241e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800241e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024214`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002426c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024214`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002426c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800242c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800242c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::MockSettingsProvider::GetSettingString(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r8
  __int64 v7; // rax
  const WCHAR *v8; // rsi
  const WCHAR *v9; // rbx
  BYTE *v10; // rdi
  REGSAM v11; // r9d
  LSTATUS v12; // eax
  void *v13; // rdx
  signed int v14; // ebx
  bool v15; // cc
  bool v16; // r8
  DWORD v17; // eax
  __int64 v19; // r8
  DWORD cbData; // [rsp+40h] [rbp-69h] BYREF
  DWORD Type; // [rsp+44h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v24; // [rsp+60h] [rbp-49h]
  _SYSTEM_INFO SystemInfo; // [rsp+70h] [rbp-39h] BYREF
  _BYTE Src[32]; // [rsp+A0h] [rbp-9h] BYREF

  v6 = a2[2];
  if ( v6 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(Src, a2, v6, a2, v6, L"_", 1);
  v7 = std::wstring::append(Src);
  *(_OWORD *)lpValueName = 0;
  v24 = 0;
  *(_OWORD *)lpValueName = *(_OWORD *)v7;
  v24 = *(_OWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  *(_WORD *)v7 = 0;
  std::wstring::~wstring(Src);
  v8 = (const WCHAR *)lpValueName;
  if ( *((_QWORD *)&v24 + 1) > 7u )
    v8 = lpValueName[0];
  v9 = (const WCHAR *)(a1 + 8);
  if ( *((_QWORD *)v9 + 3) > 7u )
    v9 = *(const WCHAR **)v9;
  Type = 0;
  hKey = 0;
  cbData = 0;
  v10 = 0;
  if ( !dword_1800A55AC )
  {
    dword_1800A55B0 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_1800A55B0 = 1;
    dword_1800A55AC = 1;
  }
  v11 = 1;
  if ( dword_1800A55B0 )
    v11 = 257;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, v11, &hKey);
  v14 = v12;
  v15 = v12 <= 0;
  if ( v12 || (v12 = RegQueryValueExW(hKey, v8, 0, &Type, 0, &cbData), v14 = v12, v15 = v12 <= 0, v12) )
  {
LABEL_24:
    if ( !v15 )
      v14 = (unsigned __int16)v12 | 0x80070000;
LABEL_26:
    if ( v14 >= 0 )
      goto LABEL_29;
    goto LABEL_27;
  }
  v17 = cbData;
  if ( !cbData )
    goto LABEL_26;
  if ( Type != 1 )
  {
    v14 = -2147024883;
    goto LABEL_27;
  }
  cbData += 2;
  v10 = (BYTE *)WaasMedic::SafeAlloc((WaasMedic *)(v17 + 2), (unsigned __int64)v13, v16);
  if ( v10 )
  {
    v12 = RegQueryValueExW(hKey, v8, 0, &Type, v10, &cbData);
    v14 = v12;
    v15 = v12 <= 0;
    if ( !v12 )
    {
      v14 = 0;
      *(_WORD *)&v10[cbData & 0xFFFFFFFE] = 0;
      goto LABEL_29;
    }
    goto LABEL_24;
  }
  v14 = -2147024882;
LABEL_27:
  WaasMedic::SafeFree((WaasMedic *)v10, v13);
  v10 = 0;
  if ( v14 != -2147024894 )
    WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(L"string", v8, v14);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 != -2147024894 )
  {
    if ( v14 < 0 )
    {
      std::wstring::~wstring(lpValueName);
      return (unsigned int)v14;
    }
    *(_DWORD *)(a4 + 32) = 5;
    memset(&SystemInfo, 0, 32);
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v10[2 * v19] );
    std::wstring::_Construct<1,unsigned short const *>(&SystemInfo, v10, v19);
    std::wstring::operator=(a4, &SystemInfo);
    std::wstring::~wstring(&SystemInfo);
  }
  std::wstring::~wstring(lpValueName);
  return 0;
}

```

## disassembly

```asm
0x180024080  push    rbp
0x180024082  push    rbx
0x180024083  push    rsi
0x180024084  push    rdi
0x180024085  push    r14
0x180024087  push    r15
0x180024089  lea     rbp, [rsp-2Fh]
0x18002408e  sub     rsp, 0D8h
0x180024095  mov     rax, cs:__security_cookie
0x18002409c  xor     rax, rsp
0x18002409f  mov     [rbp+57h+var_40], rax
0x1800240a3  mov     r14, r9
0x1800240a6  mov     rdi, r8
0x1800240a9  mov     rbx, rcx
0x1800240ac  xor     r15d, r15d
0x1800240af  mov     r8, [rdx+10h]
0x1800240b3  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800240bd  sub     rax, r8
0x1800240c0  cmp     rax, 1
0x1800240c4  jb      loc_180024353
0x1800240ca  cmp     qword ptr [rdx+18h], 7
0x1800240cf  jbe     short loc_1800240D4
0x1800240d1  mov     rdx, [rdx]
0x1800240d4  mov     [rsp+100h+var_D0], 1
0x1800240dd  lea     rax, asc_18007A640; "_"
0x1800240e4  mov     [rsp+100h+lpcbData], rax
0x1800240e9  mov     [rsp+100h+phkResult], r8
0x1800240ee  mov     r9, rdx
0x1800240f1  lea     rcx, [rbp+57h+Src]
0x1800240f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800240fa  nop
0x1800240fb  mov     rdx, rdi
0x1800240fe  lea     rcx, [rbp+57h+Src]; Src
0x180024102  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180024107  xorps   xmm0, xmm0
0x18002410a  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18002410e  xorps   xmm1, xmm1
0x180024111  movdqu  [rbp+57h+var_A0], xmm1
0x180024116  movups  xmm0, xmmword ptr [rax]
0x180024119  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18002411d  movups  xmm1, xmmword ptr [rax+10h]
0x180024121  movups  [rbp+57h+var_A0], xmm1
0x180024125  mov     [rax+10h], r15
0x180024129  mov     qword ptr [rax+18h], 7
0x180024131  mov     [rax], r15w
0x180024135  lea     rcx, [rbp+57h+Src]; void *
0x180024139  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002413e  lea     rsi, [rbp+57h+lpValueName]
0x180024142  cmp     qword ptr [rbp+57h+var_A0+8], 7
0x180024147  cmova   rsi, [rbp+57h+lpValueName]
0x18002414c  add     rbx, 8
0x180024150  cmp     qword ptr [rbx+18h], 7
0x180024155  jbe     short loc_18002415A
0x180024157  mov     rbx, [rbx]
0x18002415a  mov     [rbp+57h+Type], r15d
0x18002415e  mov     [rbp+57h+hKey], r15
0x180024162  mov     [rbp+57h+cbData], r15d
0x180024166  mov     rdi, r15
0x180024169  cmp     cs:dword_1800A55AC, r15d
0x180024170  jnz     short loc_1800241BC
0x180024172  mov     cs:dword_1800A55B0, r15d
0x180024179  xorps   xmm0, xmm0
0x18002417c  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180024180  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180024184  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180024188  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18002418c  call    cs:__imp_GetNativeSystemInfo
0x180024192  mov     eax, 6
0x180024197  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x18002419b  jz      short loc_1800241A8
0x18002419d  mov     eax, 9
0x1800241a2  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x1800241a6  jnz     short loc_1800241B2
0x1800241a8  mov     cs:dword_1800A55B0, 1
0x1800241b2  mov     cs:dword_1800A55AC, 1
0x1800241bc  mov     eax, 101h
0x1800241c1  mov     r9d, 1
0x1800241c7  cmp     cs:dword_1800A55B0, r15d
0x1800241ce  cmovnz  r9d, eax; samDesired
0x1800241d2  lea     rax, [rbp+57h+hKey]
0x1800241d6  mov     [rsp+100h+phkResult], rax; phkResult
0x1800241db  xor     r8d, r8d; ulOptions
0x1800241de  mov     rdx, rbx; lpSubKey
0x1800241e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800241e8  call    cs:__imp_RegOpenKeyExW
0x1800241ee  mov     ebx, eax
0x1800241f0  test    eax, eax
0x1800241f2  jnz     loc_180024289
0x1800241f8  lea     rax, [rbp+57h+cbData]
0x1800241fc  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180024201  mov     [rsp+100h+phkResult], r15; lpData
0x180024206  lea     r9, [rbp+57h+Type]; lpType
0x18002420a  xor     r8d, r8d; lpReserved
0x18002420d  mov     rdx, rsi; lpValueName
0x180024210  mov     rcx, [rbp+57h+hKey]; hKey
0x180024214  call    cs:__imp_RegQueryValueExW
0x18002421a  mov     ebx, eax
0x18002421c  test    eax, eax
0x18002421e  jnz     short loc_180024289
0x180024220  mov     eax, [rbp+57h+cbData]
0x180024223  test    eax, eax
0x180024225  jz      short loc_180024294
0x180024227  cmp     [rbp+57h+Type], 1
0x18002422b  jz      short loc_180024234
0x18002422d  mov     ebx, 8007000Dh
0x180024232  jmp     short loc_180024298
0x180024234  add     eax, 2
0x180024237  mov     [rbp+57h+cbData], eax
0x18002423a  mov     ecx, eax; this
0x18002423c  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180024241  mov     rdi, rax
0x180024244  test    rax, rax
0x180024247  jnz     short loc_180024250
0x180024249  mov     ebx, 8007000Eh
0x18002424e  jmp     short loc_180024298
0x180024250  lea     rax, [rbp+57h+cbData]
0x180024254  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180024259  mov     [rsp+100h+phkResult], rdi; lpData
0x18002425e  lea     r9, [rbp+57h+Type]; lpType
0x180024262  xor     r8d, r8d; lpReserved
0x180024265  mov     rdx, rsi; lpValueName
0x180024268  mov     rcx, [rbp+57h+hKey]; hKey
0x18002426c  call    cs:__imp_RegQueryValueExW
0x180024272  mov     ebx, eax
0x180024274  test    eax, eax
0x180024276  jnz     short loc_180024289
0x180024278  mov     ebx, r15d
0x18002427b  mov     ecx, [rbp+57h+cbData]
0x18002427e  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180024282  mov     [rcx+rdi], r15w
0x180024287  jmp     short loc_1800242BD
0x180024289  jle     short loc_180024294
0x18002428b  movzx   ebx, ax
0x18002428e  or      ebx, 80070000h
0x180024294  test    ebx, ebx
0x180024296  jns     short loc_1800242BD
0x180024298  mov     rcx, rdi; this
0x18002429b  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x1800242a0  mov     rdi, r15
0x1800242a3  cmp     ebx, 80070002h
0x1800242a9  jz      short loc_1800242BD
0x1800242ab  mov     r8d, ebx; int
0x1800242ae  mov     rdx, rsi; unsigned __int16 *
0x1800242b1  lea     rcx, aString_0; "string"
0x1800242b8  call    ?ReportRegUtilQueryValueFailed@TelemetryProvider@WaasMedic@@SAXPEBG0J@Z; WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(ushort const *,ushort const *,long)
0x1800242bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800242c1  test    rcx, rcx
0x1800242c4  jz      short loc_1800242CC
0x1800242c6  call    cs:__imp_RegCloseKey
0x1800242cc  cmp     ebx, 80070002h
0x1800242d2  jz      short loc_18002432C
0x1800242d4  test    ebx, ebx
0x1800242d6  jns     short loc_1800242E5
0x1800242d8  lea     rcx, [rbp+57h+lpValueName]; void *
0x1800242dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800242e1  mov     eax, ebx
0x1800242e3  jmp     short loc_180024337
0x1800242e5  mov     dword ptr [r14+20h], 5
0x1800242ed  xorps   xmm0, xmm0
0x1800242f0  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x1800242f4  xorps   xmm1, xmm1
0x1800242f7  movdqu  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800242fc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024300  inc     r8
0x180024303  cmp     [rdi+r8*2], r15w
0x180024308  jnz     short loc_180024300
0x18002430a  mov     rdx, rdi
0x18002430d  lea     rcx, [rbp+57h+SystemInfo]
0x180024311  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024316  lea     rdx, [rbp+57h+SystemInfo]
0x18002431a  mov     rcx, r14
0x18002431d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180024322  lea     rcx, [rbp+57h+SystemInfo]; void *
0x180024326  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002432b  nop
0x18002432c  lea     rcx, [rbp+57h+lpValueName]; void *
0x180024330  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024335  xor     eax, eax
0x180024337  mov     rcx, [rbp+57h+var_40]
0x18002433b  xor     rcx, rsp; StackCookie
0x18002433e  call    __security_check_cookie
0x180024343  add     rsp, 0D8h
0x18002434a  pop     r15
0x18002434c  pop     r14
0x18002434e  pop     rdi
0x18002434f  pop     rsi
0x180024350  pop     rbx
0x180024351  pop     rbp
0x180024352  retn
0x180024353  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
