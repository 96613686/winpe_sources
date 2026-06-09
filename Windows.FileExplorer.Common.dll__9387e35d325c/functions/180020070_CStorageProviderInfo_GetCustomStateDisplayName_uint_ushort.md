# CStorageProviderInfo::GetCustomStateDisplayName(uint,ushort * *)

- ea: `0x180020070`
- end: `0x1800202b8`
- name: `?GetCustomStateDisplayName@CStorageProviderInfo@@UEAAJIPEAPEAG@Z`
- size: `584`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004d6c`
- `0x180006bc8`
- `0x1800077c8`
- `0x18000bc30`
- `0x180020070`
- `0x1800202c0`
- `0x18002037c`
- `0x18002edcc`
- `0x180037780`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800201e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002013d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002013d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002019a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002019a`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180020262`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180020262`

## string_xrefs

- `0x1800201cc`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180020219`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002023b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18002027a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderInfo::GetCustomStateDisplayName(
        CStorageProviderInfo *this,
        const unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  int SyncRootManagerRegistryLocation; // ebx
  unsigned int v6; // ebx
  bool v7; // sf
  __int64 v9; // rdx
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY *p_hkey; // [rsp+50h] [rbp-B0h]
  HKEY v20; // [rsp+58h] [rbp-A8h] BYREF
  char v21; // [rsp+60h] [rbp-A0h]
  WCHAR pszSource[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  *a3 = 0;
  *(_QWORD *)pcbData = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)pcbData,
                                      a2);
  if ( SyncRootManagerRegistryLocation < 0 )
  {
    v9 = 749;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)SyncRootManagerRegistryLocation,
      (int)phkResult);
    return (unsigned int)SyncRootManagerRegistryLocation;
  }
  phkResult = (PHKEY)*((_QWORD *)this + 12);
  SyncRootManagerRegistryLocation = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\CustomStates\\%d", *(_QWORD *)pcbData);
  if ( SyncRootManagerRegistryLocation < 0 )
  {
    v9 = 752;
    goto LABEL_16;
  }
  hkey = 0;
  p_hkey = &hkey;
  v20 = 0;
  v21 = 1;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &v20);
  if ( v21 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      p_hkey,
      v20);
  if ( v6 )
  {
    SyncRootManagerRegistryLocation = wil::details::in1diag3::Return_Win32(
                                        retaddr,
                                        (void *)0x2F3,
                                        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src"
                                                      "\\syncrootmanager.cpp",
                                        (const char *)v6,
                                        phkResulta);
    goto LABEL_24;
  }
  pcbData[0] = 520;
  SyncRootManagerRegistryLocation = RegGetValueW(hkey, 0, L"DisplayName", 2u, 0, pszSource, pcbData);
  if ( SyncRootManagerRegistryLocation )
  {
    pszSource[0] = 0;
    v7 = SyncRootManagerRegistryLocation < 0;
    if ( SyncRootManagerRegistryLocation <= 0 )
      goto LABEL_10;
    SyncRootManagerRegistryLocation = (unsigned __int16)SyncRootManagerRegistryLocation | 0x80070000;
  }
  v7 = SyncRootManagerRegistryLocation < 0;
LABEL_10:
  if ( !v7 )
  {
    v10 = SHLoadIndirectString(pszSource, pszOutBuf, 0x104u, 0);
    SyncRootManagerRegistryLocation = v10;
    if ( v10 >= 0 )
    {
      v10 = _AllocString<CTCoAllocPolicy>(v12, v11, pszOutBuf, a3);
      SyncRootManagerRegistryLocation = v10;
      if ( v10 >= 0 )
      {
        SyncRootManagerRegistryLocation = 0;
        goto LABEL_24;
      }
      v13 = 762;
    }
    else
    {
      v13 = 761;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v10,
      phkResultb);
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return (unsigned int)SyncRootManagerRegistryLocation;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2F6,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)SyncRootManagerRegistryLocation,
    phkResultb);
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)SyncRootManagerRegistryLocation;
}

```

## disassembly

```asm
0x180020070  push    rbp
0x180020072  push    rbx
0x180020073  push    rsi
0x180020074  push    rdi
0x180020075  push    r14
0x180020077  lea     rbp, [rsp-5B0h]
0x18002007f  sub     rsp, 6B0h
0x180020086  mov     rax, cs:__security_cookie
0x18002008d  xor     rax, rsp
0x180020090  mov     [rbp+5D0h+var_30], rax
0x180020097  mov     rdi, r8
0x18002009a  mov     r14d, edx
0x18002009d  mov     rsi, rcx
0x1800200a0  mov     qword ptr [r8], 0
0x1800200a7  mov     qword ptr [rsp+6D0h+var_690], 0
0x1800200b0  lea     rcx, [rsp+6D0h+var_690]; this
0x1800200b5  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x1800200ba  mov     ebx, eax
0x1800200bc  test    eax, eax
0x1800200be  js      loc_18002020D
0x1800200c4  mov     dword ptr [rsp+6D0h+pvData], r14d
0x1800200c9  mov     rax, [rsi+60h]
0x1800200cd  mov     [rsp+6D0h+phkResult], rax; int
0x1800200d2  mov     r9, qword ptr [rsp+6D0h+var_690]
0x1800200d7  lea     r8, aSSCustomstates; "%s\\%s\\CustomStates\\%d"
0x1800200de  mov     esi, 104h
0x1800200e3  mov     edx, esi; unsigned __int64
0x1800200e5  lea     rcx, [rbp+5D0h+SubKey]; unsigned __int16 *
0x1800200ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800200f1  mov     ebx, eax
0x1800200f3  test    eax, eax
0x1800200f5  js      loc_180020214
0x1800200fb  mov     [rsp+6D0h+hkey], 0
0x180020104  lea     rax, [rsp+6D0h+hkey]
0x180020109  mov     [rsp+6D0h+var_680], rax
0x18002010e  mov     [rsp+6D0h+var_678], 0
0x180020117  mov     [rsp+6D0h+var_670], 1
0x18002011c  lea     rax, [rsp+6D0h+var_678]
0x180020121  mov     [rsp+6D0h+phkResult], rax; unsigned int
0x180020126  mov     r9d, 20119h; samDesired
0x18002012c  xor     r8d, r8d; ulOptions
0x18002012f  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x180020136  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002013d  call    cs:__imp_RegOpenKeyExW
0x180020143  mov     ebx, eax
0x180020145  cmp     [rsp+6D0h+var_670], 0
0x18002014a  jz      short loc_18002015B
0x18002014c  mov     rdx, [rsp+6D0h+var_678]
0x180020151  mov     rcx, [rsp+6D0h+var_680]
0x180020156  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002015b  test    ebx, ebx
0x18002015d  jnz     loc_180020231
0x180020163  mov     [rsp+6D0h+var_690], 208h
0x18002016b  lea     rax, [rsp+6D0h+var_690]
0x180020170  mov     [rsp+6D0h+pcbData], rax; pcbData
0x180020175  lea     rax, [rsp+6D0h+pszSource]
0x18002017a  mov     [rsp+6D0h+pvData], rax; pvData
0x18002017f  mov     [rsp+6D0h+phkResult], 0; int
0x180020188  lea     r9d, [rbx+2]; dwFlags
0x18002018c  lea     r8, aDisplayname; "DisplayName"
0x180020193  xor     edx, edx; lpSubKey
0x180020195  mov     rcx, [rsp+6D0h+hkey]; hkey
0x18002019a  call    cs:__imp_RegGetValueW
0x1800201a0  mov     ebx, eax
0x1800201a2  test    eax, eax
0x1800201a4  jz      short loc_1800201BA
0x1800201a6  xor     eax, eax
0x1800201a8  mov     [rsp+6D0h+pszSource], ax
0x1800201ad  test    ebx, ebx
0x1800201af  jle     short loc_1800201BC
0x1800201b1  movzx   ebx, bx
0x1800201b4  or      ebx, 80070000h
0x1800201ba  test    ebx, ebx
0x1800201bc  jns     loc_180020250
0x1800201c2  mov     rcx, [rbp+5D8h]; this
0x1800201c9  mov     r9d, ebx; char *
0x1800201cc  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800201d3  mov     edx, 2F6h; void *
0x1800201d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800201dd  nop
0x1800201de  mov     rcx, [rsp+6D0h+hkey]; hKey
0x1800201e3  test    rcx, rcx
0x1800201e6  jz      short loc_1800201EE
0x1800201e8  call    cs:__imp_RegCloseKey
0x1800201ee  mov     eax, ebx
0x1800201f0  mov     rcx, [rbp+5D0h+var_30]
0x1800201f7  xor     rcx, rsp; StackCookie
0x1800201fa  call    __security_check_cookie
0x1800201ff  add     rsp, 6B0h
0x180020206  pop     r14
0x180020208  pop     rdi
0x180020209  pop     rsi
0x18002020a  pop     rbx
0x18002020b  pop     rbp
0x18002020c  retn
0x18002020d  mov     edx, 2EDh
0x180020212  jmp     short loc_180020219
0x180020214  mov     edx, 2F0h; void *
0x180020219  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180020220  mov     r9d, ebx; char *
0x180020223  mov     rcx, [rbp+5D8h]; this
0x18002022a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002022f  jmp     short loc_1800201EE
0x180020231  mov     rcx, [rbp+5D8h]; this
0x180020238  mov     r9d, ebx; char *
0x18002023b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180020242  mov     edx, 2F3h; void *
0x180020247  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002024c  mov     ebx, eax
0x18002024e  jmp     short loc_1800202A9
0x180020250  xor     r9d, r9d; ppvReserved
0x180020253  mov     r8d, esi; cchOutBuf
0x180020256  lea     rdx, [rbp+5D0h+pszOutBuf]; pszOutBuf
0x18002025d  lea     rcx, [rsp+6D0h+pszSource]; pszSource
0x180020262  call    cs:__imp_SHLoadIndirectString
0x180020268  mov     ebx, eax
0x18002026a  test    eax, eax
0x18002026c  jns     short loc_180020292
0x18002026e  mov     edx, 2F9h
0x180020273  jmp     short loc_18002027A
0x180020275  mov     edx, 2FAh; void *
0x18002027a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180020281  mov     r9d, eax; char *
0x180020284  mov     rcx, [rbp+5D8h]; this
0x18002028b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020290  jmp     short loc_1800202A9
0x180020292  mov     r9, rdi
0x180020295  lea     r8, [rbp+5D0h+pszOutBuf]
0x18002029c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800202a1  mov     ebx, eax
0x1800202a3  test    eax, eax
0x1800202a5  js      short loc_180020275
0x1800202a7  xor     ebx, ebx
0x1800202a9  lea     rcx, [rsp+6D0h+hkey]
0x1800202ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800202b3  jmp     loc_1800201EE
```
