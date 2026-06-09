# PowerShellMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x180018a50`
- end: `0x180019521`
- name: `?PowerShellMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `2769`
- prototype: `__int64 __usercall@<rax>(AppCompatUtility *this@<rcx>, void *@<rdx>, struct _DB *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000c190`
- `0x18000e064`
- `0x18000e504`
- `0x180010718`
- `0x180010730`
- `0x1800118f4`
- `0x1800170f8`
- `0x180017560`
- `0x180017d4c`
- `0x180017ee0`
- `0x1800180dc`
- `0x180018970`
- `0x180018a50`
- `0x180019bf4`
- `0x180019e08`
- `0x18001a76c`
- `0x18001a900`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x180041cc8`
- `0x1800543c0`
- `0x18006512c`
- `0x180065150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019455`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019455`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800191f5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800191f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018bb4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001923f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180018bb4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001923f`
- `KERNEL32!ReadFile` at `0x180019378`
- `KERNEL32!ReadFile` at `0x180019378`
- `KERNEL32!CreateProcessW` at `0x18001928f`
- `KERNEL32!CreateProcessW` at `0x18001928f`
- `KERNEL32!SetHandleInformation` at `0x18001919a`
- `KERNEL32!SetHandleInformation` at `0x18001919a`
- `KERNEL32!CreatePipe` at `0x18001915e`
- `KERNEL32!CreatePipe` at `0x18001915e`
- `KERNEL32!CloseHandle` at `0x1800192c7`
- `KERNEL32!CloseHandle` at `0x1800192d7`
- `KERNEL32!CloseHandle` at `0x1800192e9`
- `KERNEL32!CloseHandle` at `0x180019427`
- `KERNEL32!CloseHandle` at `0x180019440`
- `KERNEL32!CloseHandle` at `0x1800192c7`
- `KERNEL32!CloseHandle` at `0x1800192d7`
- `KERNEL32!CloseHandle` at `0x1800192e9`
- `KERNEL32!CloseHandle` at `0x180019427`
- `KERNEL32!CloseHandle` at `0x180019440`
- `KERNEL32!GetLastError` at `0x180019168`
- `KERNEL32!GetLastError` at `0x1800191a4`
- `KERNEL32!GetLastError` at `0x180019299`
- `KERNEL32!GetLastError` at `0x180019168`
- `KERNEL32!GetLastError` at `0x1800191a4`
- `KERNEL32!GetLastError` at `0x180019299`
- `KERNEL32!WaitForSingleObject` at `0x1800192ba`
- `KERNEL32!WaitForSingleObject` at `0x1800192ba`
- `SHLWAPI!StrToIntExW` at `0x180018ea4`
- `SHLWAPI!StrToIntExW` at `0x180018ea4`

## string_xrefs

- `0x18001947b`: `CommandLine is null/empty`
- `0x180018bc6`: `Enter PowerShellMatchingPlugin, SdbId: %ws`
- `0x180018bd3`: `PowerShellMatchingPlugin`
- `0x180018bfa`: `PowerShellMatchingPlugin`
- `0x180018bed`: `Enter PowerShellMatchingPlugin`
- `0x180018c8e`: `Original CommandLine is %ws`
- `0x180018d66`: `Wrong command line format.`
- `0x180018e0b`: `Wrong command line format.`
- `0x180018fce`: `powershell.exe -ExecutionPolicy Restricted -Command `
- `0x18001901c`: `CommandLine is %ws`
- `0x180019064`: `PowerShellMatchingPlugin `
- `0x18001907a`: `PowerShellMatchingPlugin `
- `0x18001916e`: `CreatePipe failed %d`
- `0x18001929f`: `CreateProcess failed %d`
- `0x180019463`: `PowerShellMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PowerShellMatchingPlugin(
        AppCompatUtility *this,
        void *a2,
        struct _DB *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *Src)
{
  unsigned int v7; // ebx
  unsigned __int16 *v9; // rdx
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  wchar_t **v12; // rdi
  __int64 v13; // rbx
  const wchar_t *v14; // rdx
  wchar_t *v15; // rbx
  unsigned __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // r8
  wchar_t **v19; // rdx
  unsigned __int64 first_not_of; // rcx
  __int64 v21; // r8
  wchar_t **v22; // rax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // r8
  wchar_t **v26; // rdx
  const WCHAR *v27; // rcx
  PCWSTR *v28; // rax
  wchar_t **v29; // rax
  wchar_t **v30; // rax
  void **v31; // rax
  _WORD *v32; // rbx
  void **v33; // rdx
  unsigned int v34; // r9d
  int *v35; // rdx
  WCHAR *v37; // r14
  DWORD LastError; // eax
  const char *v39; // r9
  __int64 v40; // r8
  unsigned int v41; // r9d
  size_t v42; // rbx
  WCHAR *v43; // rax
  const char *v44; // r9
  __int64 v45; // r8
  void **v46; // r8
  DWORD v47; // ebx
  __int64 v48; // rax
  __int64 v49; // rax
  void **v50; // rdx
  unsigned int bInheritHandles; // [rsp+28h] [rbp-E0h]
  BOOL bInheritHandlesa[2]; // [rsp+28h] [rbp-E0h]
  DWORD dwCreationFlags[2]; // [rsp+30h] [rbp-D8h]
  LPVOID lpEnvironment; // [rsp+38h] [rbp-D0h]
  DWORD piRet; // [rsp+58h] [rbp-B0h] BYREF
  DWORD piRet_4; // [rsp+5Ch] [rbp-ACh] BYREF
  int piRet_8[4]; // [rsp+60h] [rbp-A8h] BYREF
  _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+70h] [rbp-98h] BYREF
  __int64 v59; // [rsp+88h] [rbp-80h]
  __int64 v60; // [rsp+90h] [rbp-78h]
  _BYTE v61[16]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v62[136]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v63[13]; // [rsp+140h] [rbp+38h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+1A8h] [rbp+A0h] BYREF
  wchar_t *String2[2]; // [rsp+218h] [rbp+110h] BYREF
  unsigned __int64 v66; // [rsp+228h] [rbp+120h]
  unsigned __int64 v67; // [rsp+230h] [rbp+128h]
  __int128 v68; // [rsp+238h] [rbp+130h] BYREF
  __int128 v69; // [rsp+248h] [rbp+140h]
  void *v70[2]; // [rsp+258h] [rbp+150h] BYREF
  __int64 v71; // [rsp+268h] [rbp+160h]
  unsigned __int64 v72; // [rsp+270h] [rbp+168h]
  void *v73[2]; // [rsp+278h] [rbp+170h] BYREF
  __m128i si128; // [rsp+288h] [rbp+180h]
  PCWSTR pszString[2]; // [rsp+298h] [rbp+190h] BYREF
  __m128i v76; // [rsp+2A8h] [rbp+1A0h]
  _BYTE v77[80]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _BYTE Buffer[272]; // [rsp+308h] [rbp+200h] BYREF

  v60 = -2;
  v7 = (unsigned int)a3;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  *(_OWORD *)piRet_8 = 0;
  memset(&PipeAttributes, 0, sizeof(PipeAttributes));
  *(_OWORD *)v70 = 0;
  v71 = 0;
  v72 = 7;
  LOWORD(v70[0]) = 0;
  v59 = 0;
  piRet = 0;
  memset_0(Buffer, 0, 0x104u);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v61);
  *(_DWORD *)this = 0;
  *(_OWORD *)String2 = 0;
  v66 = 0;
  v67 = 7;
  LOWORD(String2[0]) = 0;
  *(_OWORD *)v73 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v73[0]) = 0;
  *(_OWORD *)pszString = 0;
  v76 = si128;
  LOWORD(pszString[0]) = 0;
  piRet_4 = 6000;
  memset_0(v77, 0, sizeof(v77));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId>::GetImpl'::`2'::impl) )
  {
    if ( (int)AppCompatUtility::GetSdbIdFromParentEntry(
                (AppCompatUtility *)v77,
                v9,
                v7,
                (struct _DB *)a4,
                bInheritHandles) < 0 )
      _o_wcscpy_s(v77, 40, L"{Unknown}");
    AslLogCallPrintf(3, "PowerShellMatchingPlugin", 139, "Enter PowerShellMatchingPlugin, SdbId: %ws", v77);
  }
  else
  {
    AslLogCallPrintf(3, "PowerShellMatchingPlugin", 143, "Enter PowerShellMatchingPlugin");
  }
  if ( !Src || !*Src )
  {
    AslLogCallPrintf(1, "PowerShellMatchingPlugin", 148, "CommandLine is null/empty");
    goto LABEL_96;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( Src[v11] );
  if ( v11 > v67 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(String2);
  }
  else
  {
    v12 = String2;
    if ( v67 > 7 )
      v12 = (wchar_t **)String2[0];
    v66 = v11;
    v13 = 2 * v11;
    memmove_0(v12, Src, 2 * v11);
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  AslLogCallPrintf(3, "PowerShellMatchingPlugin", 153, "Original CommandLine is %ws", Src);
  v14 = (const wchar_t *)String2;
  v15 = String2[0];
  v16 = v67;
  if ( v67 > 7 )
    v14 = String2[0];
  if ( wcsncmp_0(L"-Timeout ", v14, 9u) )
  {
LABEL_46:
    if ( 0x7FFFFFFFFFFFFFFELL - v66 < 0x34 )
      std::_Xlen_string();
    v30 = String2;
    if ( v16 > 7 )
      v30 = (wchar_t **)v15;
    lpEnvironment = (LPVOID)v66;
    *(_QWORD *)dwCreationFlags = v30;
    std::wstring::wstring(&v68, v17, v18, L"powershell.exe -ExecutionPolicy Restricted -Command ");
    std::wstring::operator=(v73, &v68);
    std::wstring::~wstring(&v68);
    v31 = v73;
    if ( si128.m128i_i64[1] > 7uLL )
      v31 = (void **)v73[0];
    AslLogCallPrintf(
      3,
      "PowerShellMatchingPlugin",
      188,
      "CommandLine is %ws",
      v31,
      *(_QWORD *)dwCreationFlags,
      lpEnvironment);
    if ( v72 < 0x19 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v70);
    }
    else
    {
      v32 = v70[0];
      v71 = 25;
      memmove_0(v70[0], L"PowerShellMatchingPlugin ", 0x32u);
      v32[25] = 0;
    }
    v33 = v73;
    if ( si128.m128i_i64[1] > 7uLL )
      v33 = (void **)v73[0];
    std::wstring::append(v70, v33);
    v35 = (int *)v70;
    if ( v72 > 7 )
      v35 = (int *)v70[0];
    if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(this, v35, (const unsigned __int16 *)a5, v34) )
    {
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(v73);
      std::wstring::~wstring(String2);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v63);
      v63[0] = &std::ios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)v63);
      std::wstring::~wstring(v70);
      return 1;
    }
    v37 = 0;
    LODWORD(PipeAttributes.lpSecurityDescriptor) = 24;
    LODWORD(v59) = 1;
    if ( CreatePipe(
           &g_hChildStd_OUT_Rd,
           &g_hChildStd_OUT_Wr,
           (LPSECURITY_ATTRIBUTES)&PipeAttributes.lpSecurityDescriptor,
           0) )
    {
      if ( SetHandleInformation(g_hChildStd_OUT_Rd, 1u, 0) )
      {
        StartupInfo.cb = 104;
        StartupInfo.hStdOutput = g_hChildStd_OUT_Wr;
        StartupInfo.dwFlags = 257;
        StartupInfo.wShowWindow = 0;
        v42 = 2 * si128.m128i_i64[0] + 2;
        v43 = (WCHAR *)malloc(v42);
        v37 = v43;
        if ( v43 )
        {
          v46 = v73;
          if ( si128.m128i_i64[1] > 7uLL )
            v46 = (void **)v73[0];
          if ( !(unsigned int)_o_wcscpy_s(v43, v42 >> 1, v46) )
          {
            if ( CreateProcessW(0, v37, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, (LPPROCESS_INFORMATION)piRet_8) )
            {
              v47 = WaitForSingleObject(*(HANDLE *)piRet_8, piRet_4);
              CloseHandle(*(HANDLE *)piRet_8);
              *(_QWORD *)piRet_8 = 0;
              CloseHandle(*(HANDLE *)&piRet_8[2]);
              *(_QWORD *)&piRet_8[2] = 0;
              CloseHandle(g_hChildStd_OUT_Wr);
              g_hChildStd_OUT_Wr = 0;
              if ( v47 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId>::GetImpl'::`2'::impl) )
                  AslLogCallPrintf(1, "PowerShellMatchingPlugin", 281, "Process timed out, SdbId: %ws", v77);
                else
                  AslLogCallPrintf(1, "PowerShellMatchingPlugin", 285, "Process timed out");
              }
              else
              {
                while ( ReadFile(g_hChildStd_OUT_Rd, Buffer, 0x104u, &piRet, 0) && piRet )
                  std::ostream::write(v62, Buffer, piRet);
                std::ends<char,std::char_traits<char>>(v62);
                v48 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v61, &v68);
                if ( *(_QWORD *)(v48 + 24) > 0xFu )
                  v48 = *(_QWORD *)v48;
                AslLogCallPrintf(3, "PowerShellMatchingPlugin", 307, "Child process output is: %s", (const char *)v48);
                std::string::~string(&v68);
                v49 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v61, &v68);
                ParsePSResult(this, v49);
              }
              goto LABEL_84;
            }
            LastError = GetLastError();
            v39 = "CreateProcess failed %d";
            v40 = 258;
            goto LABEL_62;
          }
          v44 = "wcscpy_s failed";
          v45 = 240;
        }
        else
        {
          v44 = "Out of memory";
          v45 = 234;
        }
        AslLogCallPrintf(1, "PowerShellMatchingPlugin", v45, v44);
        goto LABEL_84;
      }
      LastError = GetLastError();
      v39 = "SetHandleInformation failed %d";
      v40 = 221;
    }
    else
    {
      LastError = GetLastError();
      v39 = "CreatePipe failed %d";
      v40 = 212;
    }
LABEL_62:
    bInheritHandlesa[0] = LastError;
    AslLogCallPrintf(1, "PowerShellMatchingPlugin", v40, v39, *(_QWORD *)bInheritHandlesa);
LABEL_84:
    if ( v71 )
    {
      v50 = v70;
      if ( v72 > 7 )
        LODWORD(v50) = v70[0];
      AppCompatUtility::AddCacheMatchingPlugin(
        (AppCompatUtility *)*(unsigned int *)this,
        (int)v50,
        (const unsigned __int16 *)a5,
        v41);
    }
    if ( g_hChildStd_OUT_Wr )
    {
      CloseHandle(g_hChildStd_OUT_Wr);
      g_hChildStd_OUT_Wr = 0;
    }
    if ( g_hChildStd_OUT_Rd )
    {
      CloseHandle(g_hChildStd_OUT_Rd);
      g_hChildStd_OUT_Rd = 0;
    }
    if ( v37 )
      free(v37);
    bInheritHandlesa[0] = *(_DWORD *)this;
    AslLogCallPrintf(
      3,
      "PowerShellMatchingPlugin",
      336,
      "PowerShellMatchingPlugin Matched = %d",
      *(_QWORD *)bInheritHandlesa);
    goto LABEL_96;
  }
  v68 = 0;
  v69 = 0;
  if ( v66 < 9 )
LABEL_97:
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  v19 = String2;
  if ( v16 > 7 )
    v19 = (wchar_t **)v15;
  std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v19 + 18, v66 - 9);
  std::wstring::operator=(String2, &v68);
  std::wstring::~wstring(&v68);
  first_not_of = std::wstring::find_first_not_of(String2);
  if ( first_not_of != -1 )
  {
    v68 = 0;
    v69 = 0;
    if ( v66 >= first_not_of )
    {
      v21 = -1;
      if ( v66 - first_not_of != -1 )
        v21 = v66 - first_not_of;
      v22 = String2;
      if ( v67 > 7 )
        v22 = (wchar_t **)String2[0];
      std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v22 + 2 * first_not_of, v21);
      std::wstring::operator=(String2, &v68);
      std::wstring::~wstring(&v68);
      v23 = std::wstring::find(String2, L" ");
      v24 = v23;
      if ( v23 == -1 )
      {
        AslLogCallPrintf(1, "PowerShellMatchingPlugin", 172, "Wrong command line format.");
        goto LABEL_96;
      }
      v68 = 0;
      v69 = 0;
      v25 = v23;
      if ( v66 < v23 )
        v25 = v66;
      v26 = String2;
      if ( v67 > 7 )
        v26 = (wchar_t **)String2[0];
      std::wstring::_Construct<1,unsigned short const *>(&v68, v26, v25);
      std::wstring::operator=(pszString, &v68);
      std::wstring::~wstring(&v68);
      v27 = (const WCHAR *)pszString;
      if ( v76.m128i_i64[1] > 7uLL )
        v27 = pszString[0];
      if ( !StrToIntExW(v27, 0, (int *)&piRet_4) )
      {
        v28 = pszString;
        if ( v76.m128i_i64[1] > 7uLL )
          v28 = (PCWSTR *)pszString[0];
        AslLogCallPrintf(1, "PowerShellMatchingPlugin", 178, "StrToIntEx failed %ws", v28);
        goto LABEL_96;
      }
      AslLogCallPrintf(3, "PowerShellMatchingPlugin", 181, "Timeout value is %d", piRet_4);
      v68 = 0;
      v69 = 0;
      if ( v66 >= v24 )
      {
        if ( v66 - v24 != -1 )
          v10 = v66 - v24;
        v29 = String2;
        if ( v67 > 7 )
          v29 = (wchar_t **)String2[0];
        std::wstring::_Construct<1,unsigned short const *>(&v68, (char *)v29 + 2 * v24, v10);
        std::wstring::operator=(String2, &v68);
        std::wstring::~wstring(&v68);
        v16 = v67;
        v15 = String2[0];
        goto LABEL_46;
      }
    }
    goto LABEL_97;
  }
  AslLogCallPrintf(1, "PowerShellMatchingPlugin", 164, "Wrong command line format.");
LABEL_96:
  std::wstring::~wstring(pszString);
  std::wstring::~wstring(v73);
  std::wstring::~wstring(String2);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v63);
  v63[0] = &std::ios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)v63);
  std::wstring::~wstring(v70);
  return 1;
}

```

## disassembly

```asm
0x180018a50  mov     rax, rsp
0x180018a53  push    rbp
0x180018a54  push    rsi
0x180018a55  push    rdi
0x180018a56  push    r12
0x180018a58  push    r13
0x180018a5a  push    r14
0x180018a5c  push    r15
0x180018a5e  lea     rbp, [rax-358h]
0x180018a65  sub     rsp, 420h
0x180018a6c  mov     [rbp+350h+var_3C8], 0FFFFFFFFFFFFFFFEh
0x180018a74  mov     [rax+10h], rbx
0x180018a78  mov     rax, cs:__security_cookie
0x180018a7f  xor     rax, rsp
0x180018a82  mov     [rbp+350h+var_40], rax
0x180018a89  mov     edi, r9d
0x180018a8c  mov     rbx, r8
0x180018a8f  mov     r13, rcx
0x180018a92  mov     r12, [rbp+350h+Src]
0x180018a99  xor     r14d, r14d
0x180018a9c  xor     edx, edx; Val
0x180018a9e  lea     r8d, [r14+68h]; Size
0x180018aa2  lea     rcx, [rbp+350h+StartupInfo]; void *
0x180018aa9  call    memset_0
0x180018aae  xorps   xmm0, xmm0
0x180018ab1  xor     eax, eax
0x180018ab3  movups  xmmword ptr [rsp+450h+piRet+8], xmm0
0x180018ab8  mov     qword ptr [rsp+450h+PipeAttributes.nLength], rax
0x180018abd  movups  xmmword ptr [rbp+350h+var_200], xmm0
0x180018ac4  mov     [rbp+350h+var_1F0], r14
0x180018acb  lea     esi, [rax+7]
0x180018ace  mov     [rbp+350h+var_1E8], rsi
0x180018ad5  mov     word ptr [rbp+350h+var_200], r14w
0x180018add  movups  xmmword ptr [rsp+450h+PipeAttributes.lpSecurityDescriptor], xmm0
0x180018ae2  mov     [rbp+350h+var_3D0], rax
0x180018ae6  mov     [rsp+450h+piRet], r14d
0x180018aeb  xor     edx, edx; Val
0x180018aed  mov     r8d, 104h; Size
0x180018af3  lea     rcx, [rbp+350h+Buffer]; void *
0x180018afa  call    memset_0
0x180018aff  lea     rcx, [rbp+350h+var_3B0]
0x180018b03  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180018b08  nop
0x180018b09  mov     [r13+0], r14d
0x180018b0d  xorps   xmm0, xmm0
0x180018b10  movups  xmmword ptr [rbp+350h+String2], xmm0
0x180018b17  mov     [rbp+350h+var_230], r14
0x180018b1e  mov     [rbp+350h+var_228], rsi
0x180018b25  mov     word ptr [rbp+350h+String2], r14w
0x180018b2d  movups  xmmword ptr [rbp+350h+var_1E0], xmm0
0x180018b34  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180018b3c  movdqu  [rbp+350h+var_1D0], xmm1
0x180018b44  mov     word ptr [rbp+350h+var_1E0], r14w
0x180018b4c  movups  xmmword ptr [rbp+350h+pszString], xmm0
0x180018b53  movdqu  [rbp+350h+var_1B0], xmm1
0x180018b5b  mov     word ptr [rbp+350h+pszString], r14w
0x180018b63  mov     [rsp+450h+piRet+4], 1770h
0x180018b6b  xor     edx, edx; Val
0x180018b6d  lea     r8d, [r14+50h]; Size
0x180018b71  lea     rcx, [rbp+350h+var_1A0]; void *
0x180018b78  call    memset_0
0x180018b7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId> `wil::Feature<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId>::GetImpl(void)'::`2'::impl
0x180018b84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Compat_Log_MatchingPlugin_ParentSdbId>::__private_IsEnabled(void)
0x180018b89  test    al, al
0x180018b8b  jz      short loc_180018BED
0x180018b8d  mov     r9d, edi; struct _DB *
0x180018b90  mov     r8, rbx; unsigned int
0x180018b93  lea     rcx, [rbp+350h+var_1A0]; this
0x180018b9a  call    ?GetSdbIdFromParentEntry@AppCompatUtility@@YAJPEAGKPEAU_DB@@K@Z; AppCompatUtility::GetSdbIdFromParentEntry(ushort *,ulong,_DB *,ulong)
0x180018b9f  test    eax, eax
0x180018ba1  jns     short loc_180018BBA
0x180018ba3  lea     r8, aUnknown; "{Unknown}"
0x180018baa  lea     edx, [rsi+21h]
0x180018bad  lea     rcx, [rbp+350h+var_1A0]
0x180018bb4  call    cs:__imp__o_wcscpy_s
0x180018bba  lea     rax, [rbp+350h+var_1A0]
0x180018bc1  mov     qword ptr [rsp+450h+bInheritHandles], rax
0x180018bc6  lea     r9, aEnterPowershel_0; "Enter PowerShellMatchingPlugin, SdbId: "...
0x180018bcd  mov     r8d, 8Bh
0x180018bd3  lea     rsi, aPowershellmatc_0; "PowerShellMatchingPlugin"
0x180018bda  mov     rdx, rsi
0x180018bdd  mov     r15d, 3
0x180018be3  mov     ecx, r15d
0x180018be6  call    AslLogCallPrintf
0x180018beb  jmp     short loc_180018C12
0x180018bed  lea     r9, aEnterPowershel; "Enter PowerShellMatchingPlugin"
0x180018bf4  mov     r8d, 8Fh
0x180018bfa  lea     rsi, aPowershellmatc_0; "PowerShellMatchingPlugin"
0x180018c01  mov     rdx, rsi
0x180018c04  mov     r15d, 3
0x180018c0a  mov     ecx, r15d
0x180018c0d  call    AslLogCallPrintf
0x180018c12  test    r12, r12
0x180018c15  jz      loc_18001947B
0x180018c1b  cmp     r14w, [r12]
0x180018c20  jz      loc_18001947B
0x180018c26  or      r14, 0FFFFFFFFFFFFFFFFh
0x180018c2a  mov     rdx, r14
0x180018c2d  xor     eax, eax
0x180018c2f  inc     rdx
0x180018c32  cmp     [r12+rdx*2], ax
0x180018c37  jnz     short loc_180018C2F
0x180018c39  cmp     rdx, [rbp+350h+var_228]
0x180018c40  ja      short loc_180018C7A
0x180018c42  lea     rdi, [rbp+350h+String2]
0x180018c49  cmp     [rbp+350h+var_228], 7
0x180018c51  cmova   rdi, [rbp+350h+String2]
0x180018c59  mov     [rbp+350h+var_230], rdx
0x180018c60  lea     rbx, [rdx+rdx]
0x180018c64  mov     r8, rbx; Size
0x180018c67  mov     rdx, r12; Src
0x180018c6a  mov     rcx, rdi; void *
0x180018c6d  call    memmove_0
0x180018c72  xor     eax, eax
0x180018c74  mov     [rbx+rdi], ax
0x180018c78  jmp     short loc_180018C89
0x180018c7a  mov     r9, r12
0x180018c7d  lea     rcx, [rbp+350h+String2]
0x180018c84  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180018c89  mov     qword ptr [rsp+450h+bInheritHandles], r12
0x180018c8e  lea     r9, aOriginalComman; "Original CommandLine is %ws"
0x180018c95  mov     r8d, 99h
0x180018c9b  mov     rdx, rsi
0x180018c9e  mov     ecx, r15d
0x180018ca1  call    AslLogCallPrintf
0x180018ca6  lea     rdx, [rbp+350h+String2]
0x180018cad  mov     rbx, [rbp+350h+String2]
0x180018cb4  mov     rdi, [rbp+350h+var_228]
0x180018cbb  cmp     rdi, 7
0x180018cbf  cmova   rdx, rbx; String2
0x180018cc3  mov     r8d, 9; MaxCount
0x180018cc9  lea     rcx, aTimeout; "-Timeout "
0x180018cd0  call    wcsncmp_0
0x180018cd5  xor     r12d, r12d
0x180018cd8  test    eax, eax
0x180018cda  jnz     loc_180018F8E
0x180018ce0  xorps   xmm0, xmm0
0x180018ce3  movups  [rbp+350h+var_220], xmm0
0x180018cea  xorps   xmm1, xmm1
0x180018ced  movdqu  [rbp+350h+var_210], xmm1
0x180018cf5  mov     rax, [rbp+350h+var_230]
0x180018cfc  cmp     rax, 9
0x180018d00  jb      loc_180019515
0x180018d06  add     rax, 0FFFFFFFFFFFFFFF7h
0x180018d0a  mov     r8, r14
0x180018d0d  cmp     rax, r14
0x180018d10  cmovb   r8, rax
0x180018d14  lea     rdx, [rbp+350h+String2]
0x180018d1b  cmp     rdi, 7
0x180018d1f  cmova   rdx, rbx
0x180018d23  add     rdx, 12h
0x180018d27  lea     rcx, [rbp+350h+var_220]
0x180018d2e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018d33  lea     rdx, [rbp+350h+var_220]
0x180018d3a  lea     rcx, [rbp+350h+String2]
0x180018d41  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018d46  lea     rcx, [rbp+350h+var_220]; void *
0x180018d4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018d52  lea     rcx, [rbp+350h+String2]; Src
0x180018d59  call    ?find_first_not_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_not_of(ushort const * const,unsigned __int64)
0x180018d5e  mov     rcx, rax
0x180018d61  cmp     rax, r14
0x180018d64  jnz     short loc_180018D78
0x180018d66  lea     r9, aWrongCommandLi_0; "Wrong command line format."
0x180018d6d  mov     r8d, 0A4h
0x180018d73  jmp     loc_180019488
0x180018d78  xorps   xmm0, xmm0
0x180018d7b  movups  [rbp+350h+var_220], xmm0
0x180018d82  xorps   xmm1, xmm1
0x180018d85  movdqu  [rbp+350h+var_210], xmm1
0x180018d8d  mov     rax, [rbp+350h+var_230]
0x180018d94  cmp     rax, rcx
0x180018d97  jb      loc_180019515
0x180018d9d  sub     rax, rcx
0x180018da0  mov     r8, r14
0x180018da3  cmp     rax, r14
0x180018da6  cmovb   r8, rax
0x180018daa  lea     rax, [rbp+350h+String2]
0x180018db1  cmp     [rbp+350h+var_228], 7
0x180018db9  cmova   rax, [rbp+350h+String2]
0x180018dc1  lea     rdx, [rax+rcx*2]
0x180018dc5  lea     rcx, [rbp+350h+var_220]
0x180018dcc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018dd1  lea     rdx, [rbp+350h+var_220]
0x180018dd8  lea     rcx, [rbp+350h+String2]
0x180018ddf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018de4  lea     rcx, [rbp+350h+var_220]; void *
0x180018deb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018df0  lea     rdx, S; " "
0x180018df7  lea     rcx, [rbp+350h+String2]
0x180018dfe  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180018e03  mov     rbx, rax
0x180018e06  cmp     rax, r14
0x180018e09  jnz     short loc_180018E1D
0x180018e0b  lea     r9, aWrongCommandLi_0; "Wrong command line format."
0x180018e12  mov     r8d, 0ACh
0x180018e18  jmp     loc_180019488
0x180018e1d  xorps   xmm0, xmm0
0x180018e20  movups  [rbp+350h+var_220], xmm0
0x180018e27  xorps   xmm1, xmm1
0x180018e2a  movdqu  [rbp+350h+var_210], xmm1
0x180018e32  mov     r8, rbx
0x180018e35  cmp     [rbp+350h+var_230], rbx
0x180018e3c  cmovb   r8, [rbp+350h+var_230]
0x180018e44  lea     rdx, [rbp+350h+String2]
0x180018e4b  cmp     [rbp+350h+var_228], 7
0x180018e53  cmova   rdx, [rbp+350h+String2]
0x180018e5b  lea     rcx, [rbp+350h+var_220]
0x180018e62  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018e67  lea     rdx, [rbp+350h+var_220]
0x180018e6e  lea     rcx, [rbp+350h+pszString]
0x180018e75  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018e7a  lea     rcx, [rbp+350h+var_220]; void *
0x180018e81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018e86  lea     rcx, [rbp+350h+pszString]
0x180018e8d  cmp     qword ptr [rbp+350h+var_1B0+8], 7
0x180018e95  cmova   rcx, [rbp+350h+pszString]; pszString
0x180018e9d  lea     r8, [rsp+450h+piRet+4]; piRet
0x180018ea2  xor     edx, edx; dwFlags
0x180018ea4  call    cs:__imp_StrToIntExW
0x180018eaa  mov     rdx, rsi
0x180018ead  test    eax, eax
0x180018eaf  jnz     short loc_180018EEB
0x180018eb1  lea     rax, [rbp+350h+pszString]
0x180018eb8  cmp     qword ptr [rbp+350h+var_1B0+8], 7
0x180018ec0  cmova   rax, [rbp+350h+pszString]
0x180018ec8  mov     qword ptr [rsp+450h+bInheritHandles], rax
0x180018ecd  lea     r9, aStrtointexFail_0; "StrToIntEx failed %ws"
0x180018ed4  mov     r8d, 0B2h
0x180018eda  mov     edi, 1
0x180018edf  mov     ecx, edi
0x180018ee1  call    AslLogCallPrintf
0x180018ee6  jmp     loc_180019498
0x180018eeb  mov     eax, [rsp+450h+piRet+4]
0x180018eef  mov     [rsp+450h+bInheritHandles], eax
0x180018ef3  lea     r9, aTimeoutValueIs; "Timeout value is %d"
0x180018efa  mov     r8d, 0B5h
0x180018f00  mov     ecx, r15d
0x180018f03  call    AslLogCallPrintf
0x180018f08  xorps   xmm0, xmm0
0x180018f0b  movups  [rbp+350h+var_220], xmm0
0x180018f12  xorps   xmm1, xmm1
0x180018f15  movdqu  [rbp+350h+var_210], xmm1
0x180018f1d  mov     rax, [rbp+350h+var_230]
0x180018f24  cmp     rax, rbx
0x180018f27  jb      loc_180019515
0x180018f2d  sub     rax, rbx
0x180018f30  cmp     rax, r14
0x180018f33  cmovb   r14, rax
0x180018f37  lea     rax, [rbp+350h+String2]
0x180018f3e  cmp     [rbp+350h+var_228], 7
0x180018f46  cmova   rax, [rbp+350h+String2]
0x180018f4e  lea     rdx, [rax+rbx*2]
0x180018f52  mov     r8, r14
0x180018f55  lea     rcx, [rbp+350h+var_220]
0x180018f5c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018f61  lea     rdx, [rbp+350h+var_220]
0x180018f68  lea     rcx, [rbp+350h+String2]
0x180018f6f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018f74  lea     rcx, [rbp+350h+var_220]; void *
0x180018f7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018f80  mov     rdi, [rbp+350h+var_228]
0x180018f87  mov     rbx, [rbp+350h+String2]
0x180018f8e  mov     rcx, [rbp+350h+var_230]
0x180018f95  mov     rax, 7FFFFFFFFFFFFFFEh
0x180018f9f  sub     rax, rcx
0x180018fa2  cmp     rax, 34h ; '4'
0x180018fa6  jb      loc_18001951B
0x180018fac  lea     rax, [rbp+350h+String2]
0x180018fb3  cmp     rdi, 7
0x180018fb7  cmova   rax, rbx
0x180018fbb  mov     [rsp+450h+lpEnvironment], rcx
0x180018fc0  mov     qword ptr [rsp+450h+dwCreationFlags], rax
0x180018fc5  mov     qword ptr [rsp+450h+bInheritHandles], 34h ; '4'
0x180018fce  lea     r9, aPowershellExeE; "powershell.exe -ExecutionPolicy Restric"...
0x180018fd5  lea     rcx, [rbp+350h+var_220]
0x180018fdc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180018fe1  lea     rdx, [rbp+350h+var_220]
0x180018fe8  lea     rcx, [rbp+350h+var_1E0]
0x180018fef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180018ff4  lea     rcx, [rbp+350h+var_220]; void *
0x180018ffb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019000  lea     rax, [rbp+350h+var_1E0]
0x180019007  cmp     qword ptr [rbp+350h+var_1D0+8], 7
0x18001900f  cmova   rax, [rbp+350h+var_1E0]
0x180019017  mov     qword ptr [rsp+450h+bInheritHandles], rax
0x18001901c  lea     r9, aCommandlineIsW; "CommandLine is %ws"
0x180019023  mov     r8d, 0BCh
0x180019029  mov     rdx, rsi
0x18001902c  mov     ecx, r15d
0x18001902f  call    AslLogCallPrintf
0x180019034  mov     edx, 19h
0x180019039  cmp     [rbp+350h+var_1E8], rdx
0x180019040  jb      short loc_18001907A
0x180019042  lea     rbx, [rbp+350h+var_200]
0x180019049  cmp     [rbp+350h+var_1E8], 7
0x180019051  cmova   rbx, [rbp+350h+var_200]
0x180019059  mov     [rbp+350h+var_1F0], rdx
0x180019060  lea     r8d, [rdx+19h]; Size
0x180019064  lea     rdx, aPowershellmatc_1; "PowerShellMatchingPlugin "
  ... truncated ...
```
