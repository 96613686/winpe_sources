# AppCompatUtility::GetOneSettingsValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180041644`
- end: `0x180041bc3`
- name: `?GetOneSettingsValue@AppCompatUtility@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@11@Z`
- size: `1407`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bb60`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000dfd8`
- `0x18000e064`
- `0x18000e504`
- `0x180041644`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180041a02`
- `ntdll!RtlAllocateHeap` at `0x180041a02`
- `ntdll!RtlFreeHeap` at `0x180041b5e`
- `ntdll!RtlFreeHeap` at `0x180041b5e`
- `ADVAPI32!RegGetValueW` at `0x18004195a`
- `ADVAPI32!RegGetValueW` at `0x180041a7e`
- `ADVAPI32!RegGetValueW` at `0x18004195a`
- `ADVAPI32!RegGetValueW` at `0x180041a7e`

## string_xrefs

- `0x1800419da`: `AppCompatUtility::GetOneSettingsValue`
- `0x180041a29`: `AppCompatUtility::GetOneSettingsValue`
- `0x180041acb`: `AppCompatUtility::GetOneSettingsValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AppCompatUtility::GetOneSettingsValue(char **a1, void *a2, void *a3, WCHAR *a4)
{
  WCHAR *v4; // rdi
  void *v5; // r13
  void *v6; // r12
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // r8
  const WCHAR *v16; // rdx
  int v17; // r14d
  LSTATUS ValueW; // eax
  LSTATUS v19; // r8d
  WCHAR *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r10
  const char *v23; // r9
  LPCWSTR *v24; // rdx
  PVOID pvData; // rsi
  const WCHAR *v26; // r8
  const WCHAR *v27; // rdx
  LSTATUS v28; // edx
  const wchar_t *v29; // rcx
  const wchar_t *v30; // rax
  unsigned __int64 v31; // rdx
  char *v32; // r14
  __int64 v33; // rbx
  LPDWORD pcbData; // [rsp+30h] [rbp-188h]
  DWORD v36; // [rsp+40h] [rbp-178h] BYREF
  int v37; // [rsp+44h] [rbp-174h]
  PVOID v38; // [rsp+48h] [rbp-170h]
  __int64 v39; // [rsp+50h] [rbp-168h]
  void *v40; // [rsp+58h] [rbp-160h]
  void *v41; // [rsp+60h] [rbp-158h]
  WCHAR *v42; // [rsp+68h] [rbp-150h]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp-148h] BYREF
  __m128i si128; // [rsp+80h] [rbp-138h]
  __int128 v45; // [rsp+90h] [rbp-128h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-118h]
  __int128 v47; // [rsp+B0h] [rbp-108h] BYREF
  __int128 v48; // [rsp+C0h] [rbp-F8h]
  __int128 v49; // [rsp+D0h] [rbp-E8h] BYREF
  __int128 v50; // [rsp+E0h] [rbp-D8h]
  __int128 v51; // [rsp+F0h] [rbp-C8h] BYREF
  __int128 v52; // [rsp+100h] [rbp-B8h]
  __int128 Src; // [rsp+110h] [rbp-A8h] BYREF
  __int128 v54; // [rsp+120h] [rbp-98h]
  _OWORD v55[2]; // [rsp+130h] [rbp-88h] BYREF
  _OWORD v56[2]; // [rsp+150h] [rbp-68h] BYREF

  v39 = -2;
  try
  {
    v4 = a4;
    v5 = a3;
    v6 = a2;
    v40 = a2;
    v41 = a3;
    v42 = a4;
    v8 = -2147467259;
    v37 = -2147467259;
    v36 = 0;
    *(_OWORD *)lpSubKey = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpSubKey[0]) = 0;
    memset(v55, 0, sizeof(v55));
    std::wstring::_Construct<1,unsigned short const *>(
      v55,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OneSettings",
      53);
    v9 = std::wstring::append(v55, (void *)L"\\");
    Src = 0;
    v54 = 0;
    Src = *(_OWORD *)v9;
    v54 = *(_OWORD *)(v9 + 16);
    *(_QWORD *)(v9 + 16) = 0;
    *(_QWORD *)(v9 + 24) = 7;
    *(_WORD *)v9 = 0;
    v10 = std::wstring::append(&Src);
    v51 = 0;
    v52 = 0;
    v51 = *(_OWORD *)v10;
    v52 = *(_OWORD *)(v10 + 16);
    *(_QWORD *)(v10 + 16) = 0;
    *(_QWORD *)(v10 + 24) = 7;
    *(_WORD *)v10 = 0;
    v11 = std::wstring::append(&v51, (void *)L"\\");
    v49 = 0;
    v50 = 0;
    v49 = *(_OWORD *)v11;
    v50 = *(_OWORD *)(v11 + 16);
    *(_QWORD *)(v11 + 16) = 0;
    *(_QWORD *)(v11 + 24) = 7;
    *(_WORD *)v11 = 0;
    v12 = std::wstring::append(&v49);
    v47 = 0;
    v48 = 0;
    v47 = *(_OWORD *)v12;
    v48 = *(_OWORD *)(v12 + 16);
    *(_QWORD *)(v12 + 16) = 0;
    *(_QWORD *)(v12 + 24) = 7;
    *(_WORD *)v12 = 0;
    v13 = std::wstring::append(&v47, (void *)L"\\");
    v45 = 0;
    v46 = 0;
    v45 = *(_OWORD *)v13;
    v46 = *(_OWORD *)(v13 + 16);
    *(_QWORD *)(v13 + 16) = 0;
    *(_QWORD *)(v13 + 24) = 7;
    *(_WORD *)v13 = 0;
    v14 = std::wstring::append(&v45, L"Settings");
    v56[0] = *(_OWORD *)v14;
    v56[1] = *(_OWORD *)(v14 + 16);
    *(_QWORD *)(v14 + 16) = 0;
    *(_QWORD *)(v14 + 24) = 7;
    *(_WORD *)v14 = 0;
    std::wstring::operator=(lpSubKey, v56);
    std::wstring::~wstring(v56);
    std::wstring::~wstring(&v45);
    std::wstring::~wstring(&v47);
    std::wstring::~wstring(&v49);
    std::wstring::~wstring(&v51);
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(v55);
    if ( *((_QWORD *)v4 + 3) <= 7u )
      v15 = v4;
    else
      v15 = *(const WCHAR **)v4;
    v16 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = lpSubKey[0];
    v17 = 2;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v16, v15, 2u, 0, 0, &v36);
  }
  catch ( ... )
  {
    AslLogCallPrintf(
      1,
      "AppCompatUtility::GetOneSettingsValue",
      2042,
      "Failed to create final OneSettings registry path.");
    v8 = v37;
    v6 = v40;
    v5 = v41;
    v4 = v42;
    goto LABEL_44;
  }
  v19 = ValueW;
  if ( ValueW )
  {
    if ( ValueW == 2 )
    {
      if ( *((_QWORD *)v4 + 3) <= 7u )
        v20 = v4;
      else
        v20 = *(WCHAR **)v4;
      v21 = 3;
      v22 = 2061;
      v23 = "Reg value 'HKLM\\%S [%S]' not found. [0x%x]";
    }
    else
    {
      if ( *((_QWORD *)v4 + 3) <= 7u )
        v20 = v4;
      else
        v20 = *(WCHAR **)v4;
      v21 = 1;
      v22 = 2065;
      v23 = "Failed to data length for reg value 'HKLM\\%S [%S]'. [0x%x]";
      v17 = v19;
    }
    v24 = lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v24 = (LPCWSTR *)lpSubKey[0];
    LODWORD(pcbData) = v17;
    AslLogCallPrintf(v21, "AppCompatUtility::GetOneSettingsValue", v22, v23, v24, v20, pcbData);
  }
  else
  {
    pvData = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v36);
    v38 = pvData;
    if ( pvData )
    {
      if ( *((_QWORD *)v4 + 3) <= 7u )
        v26 = v4;
      else
        v26 = *(const WCHAR **)v4;
      v27 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v27 = lpSubKey[0];
      v28 = RegGetValueW(HKEY_LOCAL_MACHINE, v27, v26, 2u, 0, pvData, &v36);
      if ( v28 )
      {
        if ( *((_QWORD *)v4 + 3) <= 7u )
          v29 = v4;
        else
          v29 = *(const wchar_t **)v4;
        v30 = (const wchar_t *)lpSubKey;
        if ( si128.m128i_i64[1] > 7uLL )
          v30 = lpSubKey[0];
        AslLogCallPrintf(
          1,
          "AppCompatUtility::GetOneSettingsValue",
          2094,
          "Failed to query reg value 'HKLM\\%S [%S]'. [0x%x]",
          v30,
          v29,
          v28);
      }
      else
      {
        try
        {
          v31 = -1;
          do
            ++v31;
          while ( *((_WORD *)pvData + v31) );
          if ( v31 > (unsigned __int64)a1[3] )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1);
          }
          else
          {
            if ( (unsigned __int64)a1[3] <= 7 )
              v32 = (char *)a1;
            else
              v32 = *a1;
            a1[2] = (char *)v31;
            v33 = 2 * v31;
            memmove_0(v32, pvData, 2 * v31);
            *(_WORD *)&v32[v33] = 0;
          }
        }
        catch ( ... )
        {
          AslLogCallPrintf(1, "AppCompatUtility::GetOneSettingsValue", 2107, "Failed to create std::wstring.");
          v8 = v37;
          pvData = v38;
          v6 = v40;
          v5 = v41;
          v4 = v42;
          goto LABEL_43;
        }
        v8 = 0;
      }
LABEL_43:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pvData);
    }
    else
    {
      v8 = -2147024882;
      AslLogCallPrintf(1, "AppCompatUtility::GetOneSettingsValue", 2077, "Failed to allocate memory for ValueBuffer.");
    }
  }
LABEL_44:
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(v6);
  std::wstring::~wstring(v5);
  std::wstring::~wstring(v4);
  return v8;
}

```

## disassembly

```asm
0x180041644  mov     r11, rsp
0x180041647  push    rbx
0x180041648  push    rsi
0x180041649  push    rdi
0x18004164a  push    r12
0x18004164c  push    r13
0x18004164e  push    r14
0x180041650  push    r15
0x180041652  sub     rsp, 180h
0x180041659  mov     [rsp+1B8h+var_168], 0FFFFFFFFFFFFFFFEh
0x180041662  mov     rax, cs:__security_cookie
0x180041669  xor     rax, rsp
0x18004166c  mov     [rsp+1B8h+var_48], rax
0x180041674  mov     rdi, r9
0x180041677  mov     r13, r8
0x18004167a  mov     r12, rdx
0x18004167d  mov     r15, rcx
0x180041680  mov     [rsp+1B8h+var_160], rdx
0x180041685  mov     [rsp+1B8h+var_158], r8
0x18004168a  mov     [rsp+1B8h+var_150], r9
0x18004168f  xor     r14d, r14d
0x180041692  mov     ebx, 80004005h
0x180041697  mov     [rsp+1B8h+var_174], ebx
0x18004169b  mov     [rsp+1B8h+var_178], r14d
0x1800416a0  xorps   xmm0, xmm0
0x1800416a3  movups  xmmword ptr [rsp+1B8h+lpSubKey], xmm0
0x1800416a8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800416b0  movdqu  [rsp+1B8h+var_138], xmm1
0x1800416b9  mov     word ptr [rsp+1B8h+lpSubKey], r14w
0x1800416bf  movups  [rsp+1B8h+var_88], xmm0
0x1800416c7  xorps   xmm1, xmm1
0x1800416ca  movdqu  xmmword ptr [r11-78h], xmm1
0x1800416d0  lea     r8d, [r14+35h]
0x1800416d4  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800416db  lea     rcx, [r11-88h]
0x1800416e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800416e7  nop
0x1800416e8  lea     rdx, asc_18006E074; "\\"
0x1800416ef  lea     rcx, [rsp+1B8h+var_88]; Src
0x1800416f7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800416fc  xorps   xmm0, xmm0
0x1800416ff  movups  [rsp+1B8h+Src], xmm0
0x180041707  xorps   xmm1, xmm1
0x18004170a  movdqu  [rsp+1B8h+var_98], xmm1
0x180041713  movups  xmm0, xmmword ptr [rax]
0x180041716  movups  [rsp+1B8h+Src], xmm0
0x18004171e  movups  xmm1, xmmword ptr [rax+10h]
0x180041722  movups  [rsp+1B8h+var_98], xmm1
0x18004172a  mov     [rax+10h], r14
0x18004172e  lea     esi, [r14+7]
0x180041732  mov     [rax+18h], rsi
0x180041736  mov     [rax], r14w
0x18004173a  mov     rdx, r12
0x18004173d  lea     rcx, [rsp+1B8h+Src]; Src
0x180041745  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18004174a  xorps   xmm0, xmm0
0x18004174d  movups  [rsp+1B8h+var_C8], xmm0
0x180041755  xorps   xmm1, xmm1
0x180041758  movdqu  [rsp+1B8h+var_B8], xmm1
0x180041761  movups  xmm0, xmmword ptr [rax]
0x180041764  movups  [rsp+1B8h+var_C8], xmm0
0x18004176c  movups  xmm1, xmmword ptr [rax+10h]
0x180041770  movups  [rsp+1B8h+var_B8], xmm1
0x180041778  mov     [rax+10h], r14
0x18004177c  mov     [rax+18h], rsi
0x180041780  mov     [rax], r14w
0x180041784  lea     rdx, asc_18006E074; "\\"
0x18004178b  lea     rcx, [rsp+1B8h+var_C8]; Src
0x180041793  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041798  xorps   xmm0, xmm0
0x18004179b  movups  [rsp+1B8h+var_E8], xmm0
0x1800417a3  xorps   xmm1, xmm1
0x1800417a6  movdqu  [rsp+1B8h+var_D8], xmm1
0x1800417af  movups  xmm0, xmmword ptr [rax]
0x1800417b2  movups  [rsp+1B8h+var_E8], xmm0
0x1800417ba  movups  xmm1, xmmword ptr [rax+10h]
0x1800417be  movups  [rsp+1B8h+var_D8], xmm1
0x1800417c6  mov     [rax+10h], r14
0x1800417ca  mov     [rax+18h], rsi
0x1800417ce  mov     [rax], r14w
0x1800417d2  mov     rdx, r13
0x1800417d5  lea     rcx, [rsp+1B8h+var_E8]; Src
0x1800417dd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800417e2  xorps   xmm0, xmm0
0x1800417e5  movups  [rsp+1B8h+var_108], xmm0
0x1800417ed  xorps   xmm1, xmm1
0x1800417f0  movdqu  [rsp+1B8h+var_F8], xmm1
0x1800417f9  movups  xmm0, xmmword ptr [rax]
0x1800417fc  movups  [rsp+1B8h+var_108], xmm0
0x180041804  movups  xmm1, xmmword ptr [rax+10h]
0x180041808  movups  [rsp+1B8h+var_F8], xmm1
0x180041810  mov     [rax+10h], r14
0x180041814  mov     [rax+18h], rsi
0x180041818  mov     [rax], r14w
0x18004181c  lea     rdx, asc_18006E074; "\\"
0x180041823  lea     rcx, [rsp+1B8h+var_108]; Src
0x18004182b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041830  xorps   xmm0, xmm0
0x180041833  movups  [rsp+1B8h+var_128], xmm0
0x18004183b  xorps   xmm1, xmm1
0x18004183e  movdqu  [rsp+1B8h+var_118], xmm1
0x180041847  movups  xmm0, xmmword ptr [rax]
0x18004184a  movups  [rsp+1B8h+var_128], xmm0
0x180041852  movups  xmm1, xmmword ptr [rax+10h]
0x180041856  movups  [rsp+1B8h+var_118], xmm1
0x18004185e  mov     [rax+10h], r14
0x180041862  mov     [rax+18h], rsi
0x180041866  mov     [rax], r14w
0x18004186a  lea     rdx, aSettings; "Settings"
0x180041871  lea     rcx, [rsp+1B8h+var_128]; Src
0x180041879  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004187e  movups  xmm0, xmmword ptr [rax]
0x180041881  movups  [rsp+1B8h+var_68], xmm0
0x180041889  movups  xmm1, xmmword ptr [rax+10h]
0x18004188d  movups  [rsp+1B8h+var_58], xmm1
0x180041895  mov     [rax+10h], r14
0x180041899  mov     [rax+18h], rsi
0x18004189d  mov     [rax], r14w
0x1800418a1  lea     rdx, [rsp+1B8h+var_68]
0x1800418a9  lea     rcx, [rsp+1B8h+lpSubKey]
0x1800418ae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800418b3  lea     rcx, [rsp+1B8h+var_68]; void *
0x1800418bb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800418c0  nop
0x1800418c1  lea     rcx, [rsp+1B8h+var_128]; void *
0x1800418c9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800418ce  nop
0x1800418cf  lea     rcx, [rsp+1B8h+var_108]; void *
0x1800418d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800418dc  nop
0x1800418dd  lea     rcx, [rsp+1B8h+var_E8]; void *
0x1800418e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800418ea  nop
0x1800418eb  lea     rcx, [rsp+1B8h+var_C8]; void *
0x1800418f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800418f8  nop
0x1800418f9  lea     rcx, [rsp+1B8h+Src]; void *
0x180041901  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041906  nop
0x180041907  lea     rcx, [rsp+1B8h+var_88]; void *
0x18004190f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041914  nop
0x180041915  cmp     [rdi+18h], rsi
0x180041919  jbe     short loc_180041920
0x18004191b  mov     r8, [rdi]
0x18004191e  jmp     short loc_180041923
0x180041920  mov     r8, rdi; lpValue
0x180041923  lea     rdx, [rsp+1B8h+lpSubKey]
0x180041928  cmp     qword ptr [rsp+1B8h+var_138+8], rsi
0x180041930  cmova   rdx, [rsp+1B8h+lpSubKey]; lpSubKey
0x180041936  lea     rax, [rsp+1B8h+var_178]
0x18004193b  mov     [rsp+1B8h+pcbData], rax; pcbData
0x180041940  mov     [rsp+1B8h+pvData], r14; pvData
0x180041945  mov     [rsp+1B8h+pdwType], r14; pdwType
0x18004194a  mov     r14d, 2
0x180041950  mov     r9d, r14d; dwFlags
0x180041953  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004195a  call    cs:__imp_RegGetValueW
0x180041960  mov     r8d, eax
0x180041963  test    eax, eax
0x180041965  jz      loc_1800419EB
0x18004196b  cmp     eax, r14d
0x18004196e  jnz     short loc_180041992
0x180041970  cmp     [rdi+18h], rsi
0x180041974  jbe     short loc_18004197B
0x180041976  mov     rax, [rdi]
0x180041979  jmp     short loc_18004197E
0x18004197b  mov     rax, rdi
0x18004197e  mov     ecx, 3
0x180041983  mov     r10d, 80Dh
0x180041989  lea     r9, aRegValueHklmSS; "Reg value 'HKLM\\%S [%S]' not found. [0"...
0x180041990  jmp     short loc_1800419B5
0x180041992  cmp     [rdi+18h], rsi
0x180041996  jbe     short loc_18004199D
0x180041998  mov     rax, [rdi]
0x18004199b  jmp     short loc_1800419A0
0x18004199d  mov     rax, rdi
0x1800419a0  mov     ecx, 1
0x1800419a5  mov     r10d, 811h
0x1800419ab  lea     r9, aFailedToDataLe; "Failed to data length for reg value 'HK"...
0x1800419b2  mov     r14d, r8d
0x1800419b5  lea     rdx, [rsp+1B8h+lpSubKey]
0x1800419ba  cmp     qword ptr [rsp+1B8h+var_138+8], rsi
0x1800419c2  cmova   rdx, [rsp+1B8h+lpSubKey]
0x1800419c8  mov     dword ptr [rsp+1B8h+pcbData], r14d
0x1800419cd  mov     [rsp+1B8h+pvData], rax
0x1800419d2  mov     [rsp+1B8h+pdwType], rdx
0x1800419d7  mov     r8, r10
0x1800419da  lea     rdx, aAppcompatutili_7; "AppCompatUtility::GetOneSettingsValue"
0x1800419e1  call    AslLogCallPrintf
0x1800419e6  jmp     loc_180041B79
0x1800419eb  mov     r8d, [rsp+1B8h+var_178]; Size
0x1800419f0  mov     rcx, gs:60h
0x1800419f9  mov     edx, 8; Flags
0x1800419fe  mov     rcx, [rcx+30h]; HeapHandle
0x180041a02  call    cs:__imp_RtlAllocateHeap
0x180041a08  mov     rsi, rax
0x180041a0b  mov     [rsp+1B8h+var_170], rax
0x180041a10  xor     ecx, ecx
0x180041a12  test    rax, rax
0x180041a15  jnz     short loc_180041A3D
0x180041a17  mov     ebx, 8007000Eh
0x180041a1c  lea     r9, aFailedToAlloca_0; "Failed to allocate memory for ValueBuff"...
0x180041a23  mov     r8d, 81Dh
0x180041a29  lea     rdx, aAppcompatutili_7; "AppCompatUtility::GetOneSettingsValue"
0x180041a30  lea     ecx, [rax+1]
0x180041a33  call    AslLogCallPrintf
0x180041a38  jmp     loc_180041B79
0x180041a3d  cmp     qword ptr [rdi+18h], 7
0x180041a42  jbe     short loc_180041A49
0x180041a44  mov     r8, [rdi]
0x180041a47  jmp     short loc_180041A4C
0x180041a49  mov     r8, rdi; lpValue
0x180041a4c  lea     rdx, [rsp+1B8h+lpSubKey]
0x180041a51  cmp     qword ptr [rsp+1B8h+var_138+8], 7
0x180041a5a  cmova   rdx, [rsp+1B8h+lpSubKey]; lpSubKey
0x180041a60  lea     rax, [rsp+1B8h+var_178]
0x180041a65  mov     [rsp+1B8h+pcbData], rax; pcbData
0x180041a6a  mov     [rsp+1B8h+pvData], rsi; pvData
0x180041a6f  mov     [rsp+1B8h+pdwType], rcx; pdwType
0x180041a74  mov     r9d, r14d; dwFlags
0x180041a77  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180041a7e  call    cs:__imp_RegGetValueW
0x180041a84  mov     edx, eax
0x180041a86  xor     r14d, r14d
0x180041a89  test    eax, eax
0x180041a8b  jz      short loc_180041ADE
0x180041a8d  cmp     qword ptr [rdi+18h], 7
0x180041a92  jbe     short loc_180041A99
0x180041a94  mov     rcx, [rdi]
0x180041a97  jmp     short loc_180041A9C
0x180041a99  mov     rcx, rdi
0x180041a9c  lea     rax, [rsp+1B8h+lpSubKey]
0x180041aa1  cmp     qword ptr [rsp+1B8h+var_138+8], 7
0x180041aaa  cmova   rax, [rsp+1B8h+lpSubKey]
0x180041ab0  mov     dword ptr [rsp+1B8h+pcbData], edx
0x180041ab4  mov     [rsp+1B8h+pvData], rcx
0x180041ab9  mov     [rsp+1B8h+pdwType], rax
0x180041abe  lea     r9, aFailedToQueryR_0; "Failed to query reg value 'HKLM\\%S [%S"...
0x180041ac5  mov     r8d, 82Eh
0x180041acb  lea     rdx, aAppcompatutili_7; "AppCompatUtility::GetOneSettingsValue"
0x180041ad2  mov     ecx, 1
0x180041ad7  call    AslLogCallPrintf
0x180041adc  jmp     short loc_180041B4C
0x180041ade  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180041ae2  inc     rdx
0x180041ae5  cmp     [rsi+rdx*2], r14w
0x180041aea  jnz     short loc_180041AE2
0x180041aec  cmp     rdx, [r15+18h]
0x180041af0  ja      short loc_180041B23
0x180041af2  cmp     qword ptr [r15+18h], 7
0x180041af7  jbe     short loc_180041AFE
0x180041af9  mov     r14, [r15]
0x180041afc  jmp     short loc_180041B01
0x180041afe  mov     r14, r15
0x180041b01  mov     [r15+10h], rdx
0x180041b05  lea     rbx, [rdx+rdx]
0x180041b09  mov     r8, rbx; Size
0x180041b0c  mov     rdx, rsi; Src
0x180041b0f  mov     rcx, r14; void *
0x180041b12  call    memmove_0
0x180041b17  xor     eax, eax
0x180041b19  mov     [r14+rbx], ax
0x180041b1e  xor     r14d, r14d
0x180041b21  jmp     short loc_180041B2F
0x180041b23  mov     r9, rsi
0x180041b26  mov     rcx, r15
0x180041b29  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180041b2e  nop
0x180041b2f  mov     ebx, r14d
0x180041b32  jmp     short loc_180041B4C
0x180041b34  mov     ebx, [rsp+1B8h+var_174]
0x180041b38  mov     rsi, [rsp+1B8h+var_170]
0x180041b3d  mov     r12, [rsp+1B8h+var_160]
0x180041b42  mov     r13, [rsp+1B8h+var_158]
0x180041b47  mov     rdi, [rsp+1B8h+var_150]
0x180041b4c  mov     rcx, gs:60h
0x180041b55  mov     r8, rsi; P
0x180041b58  xor     edx, edx; Flags
0x180041b5a  mov     rcx, [rcx+30h]; HeapHandle
0x180041b5e  call    cs:__imp_RtlFreeHeap
0x180041b64  jmp     short loc_180041B79
0x180041b66  mov     ebx, [rsp+1B8h+var_174]
0x180041b6a  mov     r12, [rsp+1B8h+var_160]
0x180041b6f  mov     r13, [rsp+1B8h+var_158]
0x180041b74  mov     rdi, [rsp+1B8h+var_150]
0x180041b79  lea     rcx, [rsp+1B8h+lpSubKey]; void *
0x180041b7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041b83  nop
0x180041b84  mov     rcx, r12; void *
0x180041b87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041b8c  nop
0x180041b8d  mov     rcx, r13; void *
0x180041b90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041b95  nop
0x180041b96  mov     rcx, rdi; void *
0x180041b99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041b9e  mov     eax, ebx
0x180041ba0  mov     rcx, [rsp+1B8h+var_48]
0x180041ba8  xor     rcx, rsp; StackCookie
  ... truncated ...
```
