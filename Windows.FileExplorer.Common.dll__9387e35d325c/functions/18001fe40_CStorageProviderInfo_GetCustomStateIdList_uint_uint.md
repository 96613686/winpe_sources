# CStorageProviderInfo::GetCustomStateIdList(uint * *,uint *)

- ea: `0x18001fe40`
- end: `0x180020062`
- name: `?GetCustomStateIdList@CStorageProviderInfo@@UEAAJPEAPEAIPEAI@Z`
- size: `546`
- prototype: `int(CStorageProviderInfo *__hidden this, unsigned int **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004d6c`
- `0x180006bc8`
- `0x1800077c8`
- `0x180013910`
- `0x18001dd40`
- `0x18001fe40`
- `0x1800202c0`
- `0x18002037c`
- `0x180037780`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001ffed`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001ffed`
- `SHCORE!SHEnumKeyExW` at `0x18001ff6f`
- `SHCORE!SHEnumKeyExW` at `0x18001ffde`
- `SHCORE!SHEnumKeyExW` at `0x18001ff6f`
- `SHCORE!SHEnumKeyExW` at `0x18001ffde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ff28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ff28`

## string_xrefs

- `0x18001fe9c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180020041`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStorageProviderInfo::GetCustomStateIdList(
        CStorageProviderInfo *this,
        const unsigned __int16 **a2,
        unsigned int *a3)
{
  int SyncRootManagerRegistryLocation; // ebx
  __int64 v7; // rdx
  LSTATUS v9; // ebx
  unsigned int v10; // edi
  DWORD i; // edx
  void *v12; // rcx
  __int64 v13; // rbx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD pcchName[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  HKEY *p_hkey; // [rsp+48h] [rbp-B8h]
  HKEY v20; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  WCHAR pszName[56]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  *a2 = 0;
  *a3 = 0;
  *(_QWORD *)pcchName = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)pcchName,
                                      a2);
  if ( SyncRootManagerRegistryLocation < 0 )
  {
    v7 = 710;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)SyncRootManagerRegistryLocation,
      (int)phkResult);
    return (unsigned int)SyncRootManagerRegistryLocation;
  }
  phkResult = (PHKEY)*((_QWORD *)this + 12);
  SyncRootManagerRegistryLocation = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\CustomStates", *(_QWORD *)pcchName);
  if ( SyncRootManagerRegistryLocation < 0 )
  {
    v7 = 712;
    goto LABEL_3;
  }
  hkey = 0;
  p_hkey = &hkey;
  v20 = 0;
  v21 = 1;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &v20);
  if ( v21 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      p_hkey,
      v20);
  if ( !v9 )
  {
    v10 = 0;
    for ( i = 0; ; i = v10 )
    {
      pcchName[0] = 50;
      if ( SHEnumKeyExW(hkey, i, pszName, pcchName) )
        break;
      ++v10;
    }
    *a2 = 0;
    v18 = 0;
    SyncRootManagerRegistryLocation = ULongLongMult(v10, 4u, &v18);
    if ( SyncRootManagerRegistryLocation < 0
      || (SyncRootManagerRegistryLocation = CTCoAllocPolicy::Alloc(v12, 1u, v18, (void **)a2),
          SyncRootManagerRegistryLocation < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D9,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)SyncRootManagerRegistryLocation,
        phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return (unsigned int)SyncRootManagerRegistryLocation;
    }
    *a3 = v10;
    v13 = 0;
    for ( pcchName[0] = 50; (unsigned int)v13 < *a3; pcchName[0] = 50 )
    {
      if ( SHEnumKeyExW(hkey, v13, pszName, pcchName) )
        break;
      *(_DWORD *)&(*a2)[2 * v13] = _o__wtoi(pszName);
      v13 = (unsigned int)(v13 + 1);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x18001fe40  push    rbp
0x18001fe42  push    rbx
0x18001fe43  push    rsi
0x18001fe44  push    rdi
0x18001fe45  push    r14
0x18001fe47  lea     rbp, [rsp-1F0h]
0x18001fe4f  sub     rsp, 2F0h
0x18001fe56  mov     rax, cs:__security_cookie
0x18001fe5d  xor     rax, rsp
0x18001fe60  mov     [rbp+210h+var_30], rax
0x18001fe67  mov     r14, r8
0x18001fe6a  mov     rsi, rdx
0x18001fe6d  mov     rdi, rcx
0x18001fe70  mov     qword ptr [rdx], 0
0x18001fe77  mov     dword ptr [r8], 0
0x18001fe7e  mov     qword ptr [rsp+310h+pcchName], 0
0x18001fe87  lea     rcx, [rsp+310h+pcchName]; this
0x18001fe8c  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x18001fe91  mov     ebx, eax
0x18001fe93  test    eax, eax
0x18001fe95  jns     short loc_18001FEB9
0x18001fe97  mov     edx, 2C6h; void *
0x18001fe9c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001fea3  mov     r9d, ebx; char *
0x18001fea6  mov     rcx, [rbp+218h]; this
0x18001fead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001feb2  mov     eax, ebx
0x18001feb4  jmp     loc_18002001A
0x18001feb9  mov     rax, [rdi+60h]
0x18001febd  mov     [rsp+310h+phkResult], rax
0x18001fec2  mov     r9, qword ptr [rsp+310h+pcchName]
0x18001fec7  lea     r8, aSSCustomstates_0; "%s\\%s\\CustomStates"
0x18001fece  mov     edx, 104h; unsigned __int64
0x18001fed3  lea     rcx, [rbp+210h+SubKey]; unsigned __int16 *
0x18001fed7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fedc  mov     ebx, eax
0x18001fede  test    eax, eax
0x18001fee0  jns     short loc_18001FEE9
0x18001fee2  mov     edx, 2C8h
0x18001fee7  jmp     short loc_18001FE9C
0x18001fee9  mov     [rsp+310h+hkey], 0
0x18001fef2  lea     rax, [rsp+310h+hkey]
0x18001fef7  mov     [rsp+310h+var_2C8], rax
0x18001fefc  mov     [rsp+310h+var_2C0], 0
0x18001ff05  mov     [rsp+310h+var_2B8], 1
0x18001ff0a  lea     rax, [rsp+310h+var_2C0]
0x18001ff0f  mov     [rsp+310h+phkResult], rax; phkResult
0x18001ff14  mov     r9d, 20119h; samDesired
0x18001ff1a  xor     r8d, r8d; ulOptions
0x18001ff1d  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18001ff21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ff28  call    cs:__imp_RegOpenKeyExW
0x18001ff2e  mov     ebx, eax
0x18001ff30  cmp     [rsp+310h+var_2B8], 0
0x18001ff35  jz      short loc_18001FF46
0x18001ff37  mov     rdx, [rsp+310h+var_2C0]
0x18001ff3c  mov     rcx, [rsp+310h+var_2C8]
0x18001ff41  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ff46  test    ebx, ebx
0x18001ff48  jnz     loc_180020008
0x18001ff4e  xor     edi, edi
0x18001ff50  xor     edx, edx
0x18001ff52  jmp     short loc_18001FF58
0x18001ff54  inc     edi
0x18001ff56  mov     edx, edi; dwIndex
0x18001ff58  mov     [rsp+310h+pcchName], 32h ; '2'
0x18001ff60  lea     r9, [rsp+310h+pcchName]; pcchName
0x18001ff65  lea     r8, [rsp+310h+pszName]; pszName
0x18001ff6a  mov     rcx, [rsp+310h+hkey]; hkey
0x18001ff6f  call    cs:__imp_SHEnumKeyExW
0x18001ff75  test    eax, eax
0x18001ff77  jz      short loc_18001FF54
0x18001ff79  mov     qword ptr [rsi], 0
0x18001ff80  mov     [rsp+310h+var_2D0], 0
0x18001ff89  mov     ecx, edi; unsigned __int64
0x18001ff8b  lea     r8, [rsp+310h+var_2D0]; unsigned __int64 *
0x18001ff90  mov     edx, 4; unsigned __int64
0x18001ff95  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001ff9a  mov     ebx, eax
0x18001ff9c  test    eax, eax
0x18001ff9e  js      loc_180020037
0x18001ffa4  mov     r9, rsi; void **
0x18001ffa7  mov     r8, [rsp+310h+var_2D0]; unsigned __int64
0x18001ffac  mov     edx, 1; unsigned int
0x18001ffb1  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001ffb6  mov     ebx, eax
0x18001ffb8  test    eax, eax
0x18001ffba  js      short loc_180020037
0x18001ffbc  mov     [r14], edi
0x18001ffbf  xor     ebx, ebx
0x18001ffc1  mov     [rsp+310h+pcchName], 32h ; '2'
0x18001ffc9  test    edi, edi
0x18001ffcb  jz      short loc_180020008
0x18001ffcd  lea     r9, [rsp+310h+pcchName]; pcchName
0x18001ffd2  lea     r8, [rsp+310h+pszName]; pszName
0x18001ffd7  mov     edx, ebx; dwIndex
0x18001ffd9  mov     rcx, [rsp+310h+hkey]; hkey
0x18001ffde  call    cs:__imp_SHEnumKeyExW
0x18001ffe4  test    eax, eax
0x18001ffe6  jnz     short loc_180020008
0x18001ffe8  lea     rcx, [rsp+310h+pszName]
0x18001ffed  call    cs:__imp__o__wtoi
0x18001fff3  mov     rcx, [rsi]
0x18001fff6  mov     [rcx+rbx*4], eax
0x18001fff9  inc     ebx
0x18001fffb  mov     [rsp+310h+pcchName], 32h ; '2'
0x180020003  cmp     ebx, [r14]
0x180020006  jb      short loc_18001FFCD
0x180020008  mov     rcx, [rsp+310h+hkey]; hKey
0x18002000d  test    rcx, rcx
0x180020010  jz      short loc_180020018
0x180020012  call    cs:__imp_RegCloseKey
0x180020018  xor     eax, eax
0x18002001a  mov     rcx, [rbp+210h+var_30]
0x180020021  xor     rcx, rsp; StackCookie
0x180020024  call    __security_check_cookie
0x180020029  add     rsp, 2F0h
0x180020030  pop     r14
0x180020032  pop     rdi
0x180020033  pop     rsi
0x180020034  pop     rbx
0x180020035  pop     rbp
0x180020036  retn
0x180020037  mov     rcx, [rbp+218h]; this
0x18002003e  mov     r9d, ebx; char *
0x180020041  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180020048  mov     edx, 2D9h; void *
0x18002004d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020052  nop
0x180020053  lea     rcx, [rsp+310h+hkey]
0x180020058  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002005d  jmp     loc_18001FEB2
```
