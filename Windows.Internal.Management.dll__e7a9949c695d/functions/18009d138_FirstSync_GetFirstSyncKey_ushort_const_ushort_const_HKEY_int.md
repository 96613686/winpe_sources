# FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)

- ea: `0x18009d138`
- end: `0x18009d3dd`
- name: `?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z`
- size: `677`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *, HKEY *, int)`
- caller_count: `20`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180026e0c`
- `0x18009ce90`
- `0x18009cf9c`
- `0x18009d050`
- `0x18009d3e4`
- `0x18009d448`
- `0x18009d528`
- `0x18009d608`
- `0x18009d6dc`
- `0x18009d7b0`
- `0x18009d9b8`
- `0x18009da6c`
- `0x18009db4c`
- `0x18009dc4c`
- `0x18009dea4`
- `0x18009e840`
- `0x18009e96c`
- `0x18009ebbc`
- `0x18009ed14`
- `0x18009ef78`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000a2a4`
- `0x180015f70`
- `0x1800169b8`
- `0x18002b664`
- `0x18003446c`
- `0x18009d138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009d337`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009d337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d255`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d37e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d255`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d37e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18009d1dd`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18009d1dd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d1ff`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d27d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d29b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d1ff`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d27d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009d29b`

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
0x18009d138  mov     [rsp-8+arg_18], rbx
0x18009d13d  push    rbp
0x18009d13e  push    rsi
0x18009d13f  push    rdi
0x18009d140  push    r12
0x18009d142  push    r14
0x18009d144  lea     rbp, [rsp-180h]
0x18009d14c  sub     rsp, 280h
0x18009d153  mov     rax, cs:__security_cookie
0x18009d15a  xor     rax, rsp
0x18009d15d  mov     [rbp+1A0h+var_30], rax
0x18009d164  mov     r14d, r9d
0x18009d167  mov     rdi, r8
0x18009d16a  mov     rsi, rdx
0x18009d16d  mov     rbx, rcx
0x18009d170  test    rcx, rcx
0x18009d173  jnz     short loc_18009D19A
0x18009d175  mov     edx, 16Fh; void *
0x18009d17a  mov     ebx, 80070057h
0x18009d17f  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009d186  mov     r9d, ebx; char *
0x18009d189  mov     rcx, [rbp+1A8h]; this
0x18009d190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d195  jmp     loc_18009D3B5
0x18009d19a  test    rdi, rdi
0x18009d19d  jnz     short loc_18009D1A6
0x18009d19f  mov     edx, 170h
0x18009d1a4  jmp     short loc_18009D17A
0x18009d1a6  mov     qword ptr [r8], 0
0x18009d1ad  xor     edx, edx; Val
0x18009d1af  mov     r8d, 208h; Size
0x18009d1b5  lea     rcx, [rsp+2A0h+pszPathOut]; void *
0x18009d1ba  call    memset_0
0x18009d1bf  mov     ecx, 2
0x18009d1c4  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009d1c9  mov     r8, rax; pszPathIn
0x18009d1cc  mov     r9, rbx; pszMore
0x18009d1cf  mov     r12d, 104h
0x18009d1d5  mov     edx, r12d; cchPathOut
0x18009d1d8  lea     rcx, [rsp+2A0h+pszPathOut]; pszPathOut
0x18009d1dd  call    cs:__imp_PathCchCombine
0x18009d1e3  mov     ebx, eax
0x18009d1e5  test    eax, eax
0x18009d1e7  jns     short loc_18009D1F0
0x18009d1e9  lea     edx, [r12+71h]
0x18009d1ee  jmp     short loc_18009D17F
0x18009d1f0  lea     r8, aFirstsync; "FirstSync"
0x18009d1f7  mov     rdx, r12; cchPath
0x18009d1fa  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x18009d1ff  call    cs:__imp_PathCchAppend
0x18009d205  mov     ebx, eax
0x18009d207  test    eax, eax
0x18009d209  jns     short loc_18009D215
0x18009d20b  mov     edx, 176h
0x18009d210  jmp     loc_18009D17F
0x18009d215  mov     rbx, 0FFFFFFFF80000002h
0x18009d21c  test    rsi, rsi
0x18009d21f  jz      loc_18009D2DE
0x18009d225  mov     [rsp+2A0h+var_248], 0
0x18009d22e  xor     edx, edx
0x18009d230  lea     rcx, [rsp+2A0h+var_248]
0x18009d235  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009d23a  lea     rax, [rsp+2A0h+var_248]
0x18009d23f  mov     [rsp+2A0h+phkResult], rax; int
0x18009d244  mov     r9d, 20019h; samDesired
0x18009d24a  xor     r8d, r8d; ulOptions
0x18009d24d  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x18009d252  mov     rcx, rbx; hKey
0x18009d255  call    cs:__imp_RegOpenKeyExW
0x18009d25b  mov     ebx, eax
0x18009d25d  test    eax, eax
0x18009d25f  jle     short loc_18009D26A
0x18009d261  movzx   ebx, ax
0x18009d264  or      ebx, 80070000h
0x18009d26a  test    ebx, ebx
0x18009d26c  js      short loc_18009D2C3
0x18009d26e  lea     r8, asc_1800D9938; "\\"
0x18009d275  mov     rdx, r12; cchPath
0x18009d278  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x18009d27d  call    cs:__imp_PathCchAppend
0x18009d283  mov     ebx, eax
0x18009d285  test    eax, eax
0x18009d287  jns     short loc_18009D290
0x18009d289  mov     edx, 182h
0x18009d28e  jmp     short loc_18009D2AC
0x18009d290  mov     r8, rsi; pszMore
0x18009d293  mov     rdx, r12; cchPath
0x18009d296  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x18009d29b  call    cs:__imp_PathCchAppend
0x18009d2a1  mov     ebx, eax
0x18009d2a3  test    eax, eax
0x18009d2a5  jns     short loc_18009D2CD
0x18009d2a7  mov     edx, 183h; void *
0x18009d2ac  mov     r9d, eax; char *
0x18009d2af  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009d2b6  mov     rcx, [rbp+1A8h]; this
0x18009d2bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d2c2  nop
0x18009d2c3  lea     rcx, [rsp+2A0h+var_248]
0x18009d2c8  jmp     loc_18009D3B0
0x18009d2cd  lea     rcx, [rsp+2A0h+var_248]
0x18009d2d2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009d2d7  mov     rbx, 0FFFFFFFF80000002h
0x18009d2de  mov     [rsp+2A0h+var_250], 0
0x18009d2e7  xor     edx, edx
0x18009d2e9  lea     rcx, [rsp+2A0h+var_250]
0x18009d2ee  test    r14d, r14d
0x18009d2f1  jz      short loc_18009D35E
0x18009d2f3  mov     dword ptr [rsp+2A0h+var_248], edx
0x18009d2f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009d2fc  lea     rax, [rsp+2A0h+var_248]
0x18009d301  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18009d306  lea     rax, [rsp+2A0h+var_250]
0x18009d30b  mov     [rsp+2A0h+var_268], rax; phkResult
0x18009d310  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009d319  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x18009d321  mov     dword ptr [rsp+2A0h+phkResult], 0; unsigned int
0x18009d329  xor     r9d, r9d; lpClass
0x18009d32c  xor     r8d, r8d; Reserved
0x18009d32f  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x18009d334  mov     rcx, rbx; hKey
0x18009d337  call    cs:__imp_RegCreateKeyExW
0x18009d33d  test    eax, eax
0x18009d33f  jz      short loc_18009D398
0x18009d341  mov     rcx, [rbp+1A8h]; this
0x18009d348  mov     r9d, eax; char *
0x18009d34b  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009d352  mov     edx, 18Ah; void *
0x18009d357  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009d35c  jmp     short loc_18009D394
0x18009d35e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009d363  lea     rax, [rsp+2A0h+var_250]
0x18009d368  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18009d36d  mov     r9d, 20019h; samDesired
0x18009d373  xor     r8d, r8d; ulOptions
0x18009d376  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x18009d37b  mov     rcx, rbx; hKey
0x18009d37e  call    cs:__imp_RegOpenKeyExW
0x18009d384  test    eax, eax
0x18009d386  jle     short loc_18009D392
0x18009d388  movzx   eax, ax
0x18009d38b  or      eax, 80070000h
0x18009d390  test    eax, eax
0x18009d392  jns     short loc_18009D398
0x18009d394  mov     ebx, eax
0x18009d396  jmp     short loc_18009D3AB
0x18009d398  mov     rax, [rsp+2A0h+var_250]
0x18009d39d  mov     [rsp+2A0h+var_250], 0
0x18009d3a6  mov     [rdi], rax
0x18009d3a9  xor     ebx, ebx
0x18009d3ab  lea     rcx, [rsp+2A0h+var_250]
0x18009d3b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009d3b5  mov     eax, ebx
0x18009d3b7  mov     rcx, [rbp+1A0h+var_30]
0x18009d3be  xor     rcx, rsp; StackCookie
0x18009d3c1  call    __security_check_cookie
0x18009d3c6  mov     rbx, [rsp+2A0h+arg_18]
0x18009d3ce  add     rsp, 280h
0x18009d3d5  pop     r14
0x18009d3d7  pop     r12
0x18009d3d9  pop     rdi
0x18009d3da  pop     rsi
0x18009d3db  pop     rbp
0x18009d3dc  retn
```
