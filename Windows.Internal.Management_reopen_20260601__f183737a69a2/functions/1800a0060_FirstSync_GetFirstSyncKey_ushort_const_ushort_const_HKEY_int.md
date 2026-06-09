# FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)

- ea: `0x1800a0060`
- end: `0x1800a0330`
- name: `?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z`
- size: `720`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *, HKEY *, int)`
- caller_count: `20`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002556c`
- `0x18009fda0`
- `0x18009feb4`
- `0x18009ff70`
- `0x1800a0338`
- `0x1800a03a0`
- `0x1800a0488`
- `0x1800a0570`
- `0x1800a0648`
- `0x1800a0720`
- `0x1800a094c`
- `0x1800a0a08`
- `0x1800a0af0`
- `0x1800a0bf8`
- `0x1800a0e5c`
- `0x1800a1838`
- `0x1800a1970`
- `0x1800a1bc8`
- `0x1800a1d24`
- `0x1800a1fa8`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000a5c4`
- `0x180016698`
- `0x180017118`
- `0x18002a028`
- `0x180033500`
- `0x1800a0060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0189`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a02ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0189`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a02ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a027d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a027d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800a0105`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800a0105`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a012d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a01b7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a01db`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a012d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a01b7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a01db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FirstSync::GetFirstSyncKey(PCWSTR pszMore, PCWSTR a2, unsigned __int16 *a3, HKEY *a4)
{
  int v4; // r14d
  __int64 v8; // rdx
  int v9; // ebx
  const WCHAR *v10; // rax
  LSTATUS v11; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  HKEY *p_lpdwDisposition; // rcx
  unsigned int v15; // eax
  int v16; // eax
  bool v17; // sf
  HKEY v18; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v23; // [rsp+50h] [rbp-B0h] BYREF
  HKEY lpdwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = (int)a4;
  if ( pszMore )
  {
    if ( !a3 )
    {
      v8 = 368;
      goto LABEL_3;
    }
    *(_QWORD *)a3 = 0;
    memset_0(pszPathOut, 0, 0x208u);
    v10 = (const WCHAR *)DMGetKnownRegPath(2);
    v9 = PathCchCombine(pszPathOut, 0x104u, v10, pszMore);
    if ( v9 < 0 )
    {
      v8 = 373;
      goto LABEL_4;
    }
    v9 = PathCchAppend(pszPathOut, 0x104u, L"FirstSync");
    if ( v9 < 0 )
    {
      v8 = 374;
      goto LABEL_4;
    }
    if ( a2 )
    {
      lpdwDisposition = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &lpdwDisposition,
        0);
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &lpdwDisposition);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 < 0 )
        goto LABEL_20;
      v12 = PathCchAppend(pszPathOut, 0x104u, L"\\");
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 386;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
          (const char *)(unsigned int)v12,
          phkResulta);
LABEL_20:
        p_lpdwDisposition = &lpdwDisposition;
LABEL_31:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(p_lpdwDisposition);
        return (unsigned int)v9;
      }
      v12 = PathCchAppend(pszPathOut, 0x104u, a2);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 387;
        goto LABEL_19;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpdwDisposition);
    }
    v23 = 0;
    if ( v4 )
    {
      LODWORD(lpdwDisposition) = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v23,
        0);
      v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &v23, (LPDWORD)&lpdwDisposition);
      if ( v15 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x18A,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
                (const char *)v15,
                phkResultb);
LABEL_28:
        v9 = v16;
LABEL_30:
        p_lpdwDisposition = &v23;
        goto LABEL_31;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v23,
        0);
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &v23);
      v17 = v16 < 0;
      if ( v16 > 0 )
      {
        v16 = (unsigned __int16)v16 | 0x80070000;
        v17 = v16 < 0;
      }
      if ( v17 )
        goto LABEL_28;
    }
    v18 = v23;
    v23 = 0;
    *(_QWORD *)a3 = v18;
    v9 = 0;
    goto LABEL_30;
  }
  v8 = 367;
LABEL_3:
  v9 = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
    (const char *)(unsigned int)v9,
    phkResult);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a0060  mov     [rsp-8+arg_18], rbx
0x1800a0065  push    rbp
0x1800a0066  push    rsi
0x1800a0067  push    rdi
0x1800a0068  push    r12
0x1800a006a  push    r14
0x1800a006c  lea     rbp, [rsp-180h]
0x1800a0074  sub     rsp, 280h
0x1800a007b  mov     rax, cs:__security_cookie
0x1800a0082  xor     rax, rsp
0x1800a0085  mov     [rbp+1A0h+var_30], rax
0x1800a008c  mov     r14d, r9d
0x1800a008f  mov     rdi, r8
0x1800a0092  mov     rsi, rdx
0x1800a0095  mov     rbx, rcx
0x1800a0098  test    rcx, rcx
0x1800a009b  jnz     short loc_1800A00C2
0x1800a009d  mov     edx, 16Fh; void *
0x1800a00a2  mov     ebx, 80070057h
0x1800a00a7  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a00ae  mov     r9d, ebx; char *
0x1800a00b1  mov     rcx, [rbp+1A8h]; this
0x1800a00b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a00bd  jmp     loc_1800A0307
0x1800a00c2  test    rdi, rdi
0x1800a00c5  jnz     short loc_1800A00CE
0x1800a00c7  mov     edx, 170h
0x1800a00cc  jmp     short loc_1800A00A2
0x1800a00ce  mov     qword ptr [r8], 0
0x1800a00d5  xor     edx, edx; Val
0x1800a00d7  mov     r8d, 208h; Size
0x1800a00dd  lea     rcx, [rsp+2A0h+pszPathOut]; void *
0x1800a00e2  call    memset_0
0x1800a00e7  mov     ecx, 2
0x1800a00ec  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800a00f1  mov     r8, rax; pszPathIn
0x1800a00f4  mov     r9, rbx; pszMore
0x1800a00f7  mov     r12d, 104h
0x1800a00fd  mov     edx, r12d; cchPathOut
0x1800a0100  lea     rcx, [rsp+2A0h+pszPathOut]; pszPathOut
0x1800a0105  call    cs:__imp_PathCchCombine
0x1800a010c  nop     dword ptr [rax+rax+00h]
0x1800a0111  mov     ebx, eax
0x1800a0113  test    eax, eax
0x1800a0115  jns     short loc_1800A011E
0x1800a0117  lea     edx, [r12+71h]
0x1800a011c  jmp     short loc_1800A00A7
0x1800a011e  lea     r8, aFirstsync; "FirstSync"
0x1800a0125  mov     rdx, r12; cchPath
0x1800a0128  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x1800a012d  call    cs:__imp_PathCchAppend
0x1800a0134  nop     dword ptr [rax+rax+00h]
0x1800a0139  mov     ebx, eax
0x1800a013b  test    eax, eax
0x1800a013d  jns     short loc_1800A0149
0x1800a013f  mov     edx, 176h
0x1800a0144  jmp     loc_1800A00A7
0x1800a0149  mov     rbx, 0FFFFFFFF80000002h
0x1800a0150  test    rsi, rsi
0x1800a0153  jz      loc_1800A0224
0x1800a0159  mov     [rsp+2A0h+var_248], 0
0x1800a0162  xor     edx, edx
0x1800a0164  lea     rcx, [rsp+2A0h+var_248]
0x1800a0169  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a016e  lea     rax, [rsp+2A0h+var_248]
0x1800a0173  mov     [rsp+2A0h+phkResult], rax; int
0x1800a0178  mov     r9d, 20019h; samDesired
0x1800a017e  xor     r8d, r8d; ulOptions
0x1800a0181  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x1800a0186  mov     rcx, rbx; hKey
0x1800a0189  call    cs:__imp_RegOpenKeyExW
0x1800a0190  nop     dword ptr [rax+rax+00h]
0x1800a0195  mov     ebx, eax
0x1800a0197  test    eax, eax
0x1800a0199  jle     short loc_1800A01A4
0x1800a019b  movzx   ebx, ax
0x1800a019e  or      ebx, 80070000h
0x1800a01a4  test    ebx, ebx
0x1800a01a6  js      short loc_1800A0209
0x1800a01a8  lea     r8, asc_1800DD8B8; "\\"
0x1800a01af  mov     rdx, r12; cchPath
0x1800a01b2  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x1800a01b7  call    cs:__imp_PathCchAppend
0x1800a01be  nop     dword ptr [rax+rax+00h]
0x1800a01c3  mov     ebx, eax
0x1800a01c5  test    eax, eax
0x1800a01c7  jns     short loc_1800A01D0
0x1800a01c9  mov     edx, 182h
0x1800a01ce  jmp     short loc_1800A01F2
0x1800a01d0  mov     r8, rsi; pszMore
0x1800a01d3  mov     rdx, r12; cchPath
0x1800a01d6  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x1800a01db  call    cs:__imp_PathCchAppend
0x1800a01e2  nop     dword ptr [rax+rax+00h]
0x1800a01e7  mov     ebx, eax
0x1800a01e9  test    eax, eax
0x1800a01eb  jns     short loc_1800A0213
0x1800a01ed  mov     edx, 183h; void *
0x1800a01f2  mov     r9d, eax; char *
0x1800a01f5  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a01fc  mov     rcx, [rbp+1A8h]; this
0x1800a0203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0208  nop
0x1800a0209  lea     rcx, [rsp+2A0h+var_248]
0x1800a020e  jmp     loc_1800A0302
0x1800a0213  lea     rcx, [rsp+2A0h+var_248]
0x1800a0218  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a021d  mov     rbx, 0FFFFFFFF80000002h
0x1800a0224  mov     [rsp+2A0h+var_250], 0
0x1800a022d  xor     edx, edx
0x1800a022f  lea     rcx, [rsp+2A0h+var_250]
0x1800a0234  test    r14d, r14d
0x1800a0237  jz      short loc_1800A02AA
0x1800a0239  mov     dword ptr [rsp+2A0h+var_248], edx
0x1800a023d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a0242  lea     rax, [rsp+2A0h+var_248]
0x1800a0247  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800a024c  lea     rax, [rsp+2A0h+var_250]
0x1800a0251  mov     [rsp+2A0h+var_268], rax; phkResult
0x1800a0256  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a025f  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x1800a0267  mov     dword ptr [rsp+2A0h+phkResult], 0; unsigned int
0x1800a026f  xor     r9d, r9d; lpClass
0x1800a0272  xor     r8d, r8d; Reserved
0x1800a0275  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x1800a027a  mov     rcx, rbx; hKey
0x1800a027d  call    cs:__imp_RegCreateKeyExW
0x1800a0284  nop     dword ptr [rax+rax+00h]
0x1800a0289  test    eax, eax
0x1800a028b  jz      short loc_1800A02EA
0x1800a028d  mov     rcx, [rbp+1A8h]; this
0x1800a0294  mov     r9d, eax; char *
0x1800a0297  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a029e  mov     edx, 18Ah; void *
0x1800a02a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a02a8  jmp     short loc_1800A02E6
0x1800a02aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a02af  lea     rax, [rsp+2A0h+var_250]
0x1800a02b4  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800a02b9  mov     r9d, 20019h; samDesired
0x1800a02bf  xor     r8d, r8d; ulOptions
0x1800a02c2  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x1800a02c7  mov     rcx, rbx; hKey
0x1800a02ca  call    cs:__imp_RegOpenKeyExW
0x1800a02d1  nop     dword ptr [rax+rax+00h]
0x1800a02d6  test    eax, eax
0x1800a02d8  jle     short loc_1800A02E4
0x1800a02da  movzx   eax, ax
0x1800a02dd  or      eax, 80070000h
0x1800a02e2  test    eax, eax
0x1800a02e4  jns     short loc_1800A02EA
0x1800a02e6  mov     ebx, eax
0x1800a02e8  jmp     short loc_1800A02FD
0x1800a02ea  mov     rax, [rsp+2A0h+var_250]
0x1800a02ef  mov     [rsp+2A0h+var_250], 0
0x1800a02f8  mov     [rdi], rax
0x1800a02fb  xor     ebx, ebx
0x1800a02fd  lea     rcx, [rsp+2A0h+var_250]
0x1800a0302  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a0307  mov     eax, ebx
0x1800a0309  mov     rcx, [rbp+1A0h+var_30]
0x1800a0310  xor     rcx, rsp; StackCookie
0x1800a0313  call    __security_check_cookie
0x1800a0318  mov     rbx, [rsp+2A0h+arg_18]
0x1800a0320  add     rsp, 280h
0x1800a0327  pop     r14
0x1800a0329  pop     r12
0x1800a032b  pop     rdi
0x1800a032c  pop     rsi
0x1800a032d  pop     rbp
0x1800a032e  retn
```
