# PlugInManager::Initialize(void)

- ea: `0x14000c6f0`
- end: `0x14000c875`
- name: `?Initialize@PlugInManager@@SAJXZ`
- size: `389`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14002bc98`

## callees

- `0x140007d50`
- `0x140007da0`
- `0x140007df0`
- `0x140008968`
- `0x14000bd48`
- `0x14000c6f0`
- `0x14000c8f0`
- `0x14000c980`
- `0x14000c9c4`
- `0x14000ca00`
- `0x14001bd40`
- `0x14002826c`
- `0x14005b464`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14000c7e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c806`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c806`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c712`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c76d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c712`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c76d`

## string_xrefs

- `0x14000c7ab`: `\SYSTEM32\WINBIOPLUGINS\`
- `0x14000c728`: `onecore\ds\security\biometrics\service\trustlet\exe\pluginmanager.cpp`
- `0x14000c781`: `onecore\ds\security\biometrics\service\trustlet\exe\pluginmanager.cpp`

## pseudocode

```c
__int64 PlugInManager::Initialize(void)
{
  UINT WindowsDirectoryW; // eax
  const char *v1; // r9
  const char *v3; // r9
  unsigned int LastError; // ebx
  _QWORD *v5; // r9
  _QWORD *v6; // rdx
  int v7; // r8d
  _QWORD *v8; // rdx
  RTL_SRWLOCK *v9; // rbx
  struct PlugInManager *v10; // rax
  struct PlugInManager *v11; // rax
  __int16 v12; // [rsp+30h] [rbp-50h] BYREF
  RTL_SRWLOCK *v13; // [rsp+38h] [rbp-48h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v15; // [rsp+50h] [rbp-30h]
  _DWORD Src[4]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+68h] [rbp-18h]
  unsigned __int64 v18; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  WindowsDirectoryW = GetWindowsDirectoryW(0, 0);
  if ( !WindowsDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\pluginmanager.cpp",
             v1);
  v12 = 0;
  *(_OWORD *)lpBuffer = 0;
  v15 = 0;
  std::vector<unsigned short>::_Construct_n<unsigned short const &>(lpBuffer, WindowsDirectoryW, &v12);
  if ( GetWindowsDirectoryW(lpBuffer[0], lpBuffer[1] - lpBuffer[0]) )
  {
    std::wstring::wstring(Src, lpBuffer[0]);
    std::wstring::_Append<unsigned short>(Src);
    if ( v18 > 7 )
    {
      LODWORD(v5) = Src[0];
      LODWORD(v6) = Src[0];
    }
    else
    {
      v5 = Src;
      v6 = Src;
    }
    v7 = (_DWORD)v6 + 2 * v17;
    v8 = Src;
    if ( v18 > 7 )
      LODWORD(v8) = Src[0];
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)&v13,
      (_DWORD)v8,
      v7,
      (_DWORD)v5,
      (__int64)towupper);
    v9 = (RTL_SRWLOCK *)PlugInManager::Instance();
    AcquireSRWLockExclusive(v9);
    v13 = v9;
    v10 = PlugInManager::Instance();
    std::wstring::operator=((char *)v10 + 24, Src);
    v11 = PlugInManager::Instance();
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PlugIn>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<PlugIn>>>,0>>::clear((char *)v11 + 8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v13);
    std::wstring::_Tidy_deallocate(Src);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x17,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\pluginmanager.cpp",
                  v3);
  }
  std::vector<unsigned short>::_Tidy(lpBuffer);
  return LastError;
}

```

## disassembly

```asm
0x14000c6f0  mov     [rsp-8+arg_0], rbx
0x14000c6f5  push    rbp
0x14000c6f6  mov     rbp, rsp
0x14000c6f9  sub     rsp, 80h
0x14000c700  mov     rax, cs:__security_cookie
0x14000c707  xor     rax, rsp
0x14000c70a  mov     [rbp+var_8], rax
0x14000c70e  xor     edx, edx; uSize
0x14000c710  xor     ecx, ecx; lpBuffer
0x14000c712  call    cs:__imp_GetWindowsDirectoryW
0x14000c719  nop     dword ptr [rax+rax+00h]
0x14000c71e  mov     ecx, eax
0x14000c720  test    eax, eax
0x14000c722  jnz     short loc_14000C73C
0x14000c724  mov     rcx, [rbp+8]; this
0x14000c728  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c72f  lea     edx, [rax+0Fh]; void *
0x14000c732  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c737  jmp     loc_14000C857
0x14000c73c  xor     eax, eax
0x14000c73e  mov     [rbp+var_50], ax
0x14000c742  xorps   xmm0, xmm0
0x14000c745  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x14000c74a  mov     [rbp+var_30], rax
0x14000c74e  mov     rdx, rcx
0x14000c751  lea     r8, [rbp+var_50]
0x14000c755  lea     rcx, [rbp+lpBuffer]
0x14000c759  call    ??$_Construct_n@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBG@Z; std::vector<ushort>::_Construct_n<ushort const &>(unsigned __int64,ushort const &)
0x14000c75e  nop
0x14000c75f  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x14000c763  mov     rdx, [rbp+lpBuffer+8]
0x14000c767  sub     rdx, rcx
0x14000c76a  sar     rdx, 1; uSize
0x14000c76d  call    cs:__imp_GetWindowsDirectoryW
0x14000c774  nop     dword ptr [rax+rax+00h]
0x14000c779  test    eax, eax
0x14000c77b  jnz     short loc_14000C797
0x14000c77d  mov     rcx, [rbp+8]; this
0x14000c781  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\biometrics\\serv"...
0x14000c788  lea     edx, [rax+17h]; void *
0x14000c78b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c790  mov     ebx, eax
0x14000c792  jmp     loc_14000C84C
0x14000c797  mov     rdx, [rbp+lpBuffer]
0x14000c79b  lea     rcx, [rbp+Src]
0x14000c79f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000c7a4  nop
0x14000c7a5  mov     r8d, 18h
0x14000c7ab  lea     rdx, aSystem32Winbio; "\\SYSTEM32\\WINBIOPLUGINS\\"
0x14000c7b2  lea     rcx, [rbp+Src]; Src
0x14000c7b6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14000c7bb  mov     rcx, qword ptr [rbp+Src]
0x14000c7bf  cmp     [rbp+var_10], 7
0x14000c7c4  ja      short loc_14000C7D0
0x14000c7c6  lea     r9, [rbp+Src]
0x14000c7ca  lea     rdx, [rbp+Src]
0x14000c7ce  jmp     short loc_14000C7D6
0x14000c7d0  mov     r9, rcx
0x14000c7d3  mov     rdx, rcx
0x14000c7d6  mov     rax, [rbp+var_18]
0x14000c7da  lea     r8, [rdx+rax*2]
0x14000c7de  lea     rdx, [rbp+Src]
0x14000c7e2  cmova   rdx, rcx
0x14000c7e6  mov     rax, cs:__imp_towupper
0x14000c7ed  mov     [rsp+80h+var_60], rax
0x14000c7f2  lea     rcx, [rbp+var_48]
0x14000c7f6  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x14000c7fb  call    ?Instance@PlugInManager@@SAAEAV1@XZ; PlugInManager::Instance(void)
0x14000c800  mov     rbx, rax
0x14000c803  mov     rcx, rax; SRWLock
0x14000c806  call    cs:__imp_AcquireSRWLockExclusive
0x14000c80d  nop     dword ptr [rax+rax+00h]
0x14000c812  mov     [rbp+var_48], rbx
0x14000c816  call    ?Instance@PlugInManager@@SAAEAV1@XZ; PlugInManager::Instance(void)
0x14000c81b  lea     rcx, [rax+18h]
0x14000c81f  lea     rdx, [rbp+Src]
0x14000c823  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000c828  call    ?Instance@PlugInManager@@SAAEAV1@XZ; PlugInManager::Instance(void)
0x14000c82d  lea     rcx, [rax+8]
0x14000c831  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlugIn@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlugIn@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<PlugIn>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<PlugIn>>>,0>>::clear(void)
0x14000c836  nop
0x14000c837  lea     rcx, [rbp+var_48]
0x14000c83b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14000c840  nop
0x14000c841  lea     rcx, [rbp+Src]
0x14000c845  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000c84a  xor     ebx, ebx
0x14000c84c  lea     rcx, [rbp+lpBuffer]
0x14000c850  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x14000c855  mov     eax, ebx
0x14000c857  mov     rcx, [rbp+var_8]
0x14000c85b  xor     rcx, rsp; StackCookie
0x14000c85e  call    __security_check_cookie
0x14000c863  mov     rbx, [rsp+80h+arg_0]
0x14000c86b  add     rsp, 80h
0x14000c872  pop     rbp
0x14000c873  retn
```
