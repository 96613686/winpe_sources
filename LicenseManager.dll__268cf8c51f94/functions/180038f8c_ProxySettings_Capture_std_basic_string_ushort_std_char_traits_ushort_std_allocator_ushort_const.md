# ProxySettings::Capture(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180038f8c`
- end: `0x180039168`
- name: `?Capture@ProxySettings@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012984`

## callees

- `0x1800044d4`
- `0x180017230`
- `0x18001faec`
- `0x180038f8c`
- `0x18008a400`
- `0x1800a88c4`
- `0x1800a8c00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180039110`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003911f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003912e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003913e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003914d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180039110`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003911f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003912e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003913e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003914d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180038ff8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180038ff8`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180039019`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180039019`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180039090`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180039090`

## string_xrefs

- `0x180039027`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HGLOBAL __fastcall ProxySettings::Capture(__int64 a1, __int64 a2)
{
  _WORD **v4; // rdi
  _WORD *v5; // rcx
  HGLOBAL result; // rax
  const char *v7; // r9
  __int64 ProxyVectorFromList; // rax
  LPWSTR lpszAutoConfigUrl; // rax
  LPWSTR lpszProxy; // rcx
  __int64 v11; // rax
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-38h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int v16; // [rsp+90h] [rbp+20h] BYREF

  *(_WORD *)a1 = 0;
  v4 = (_WORD **)(a1 + 32);
  *(_QWORD *)(a1 + 48) = 0;
  if ( *(_QWORD *)(a1 + 56) <= 7u )
    v5 = (_WORD *)(a1 + 32);
  else
    v5 = *v4;
  *v5 = 0;
  if ( *(_QWORD *)(a1 + 8) != *(_QWORD *)(a1 + 16) )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(*(ContentIdString **)(a1 + 8));
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  }
  v16 = 0;
  result = (HGLOBAL)RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
  if ( v16 != 5 )
  {
    memset(&pProxyInfo, 0, sizeof(pProxyInfo));
    if ( !WinHttpGetDefaultProxyConfiguration(&pProxyInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v7);
    if ( pProxyInfo.dwAccessType == 3 )
    {
      *(_BYTE *)a1 = 1;
      ProxyVectorFromList = GetProxyVectorFromList(v13, a2, pProxyInfo.lpszProxy);
      std::vector<std::wstring>::operator=(a1 + 8, ProxyVectorFromList);
      result = (HGLOBAL)std::vector<std::wstring>::_Tidy(v13);
      if ( pProxyInfo.lpszProxyBypass )
        result = (HGLOBAL)std::wstring::assign(v4, pProxyInfo.lpszProxyBypass);
    }
    else
    {
      memset(&pProxyConfig, 0, sizeof(pProxyConfig));
      if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
      {
        if ( pProxyConfig.fAutoDetect )
          *(_BYTE *)(a1 + 1) = 1;
        lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
        if ( pProxyConfig.lpszAutoConfigUrl )
        {
          *(_BYTE *)a1 = 1;
          *(_BYTE *)(a1 + 2) = 1;
          std::wstring::assign(a1 + 64, lpszAutoConfigUrl);
        }
        lpszProxy = pProxyConfig.lpszProxy;
        if ( pProxyConfig.lpszProxy )
        {
          *(_BYTE *)a1 = 1;
          v11 = GetProxyVectorFromList(v13, a2, lpszProxy);
          std::vector<std::wstring>::operator=(a1 + 8, v11);
          std::vector<std::wstring>::_Tidy(v13);
          if ( pProxyConfig.lpszProxyBypass )
            std::wstring::assign(v4, pProxyConfig.lpszProxyBypass);
        }
      }
      result = pProxyConfig.lpszAutoConfigUrl;
      if ( pProxyConfig.lpszAutoConfigUrl )
        result = GlobalFree(pProxyConfig.lpszAutoConfigUrl);
      if ( pProxyConfig.lpszProxy )
        result = GlobalFree(pProxyConfig.lpszProxy);
      if ( pProxyConfig.lpszProxyBypass )
        result = GlobalFree(pProxyConfig.lpszProxyBypass);
    }
    if ( pProxyInfo.lpszProxy )
      result = GlobalFree(pProxyInfo.lpszProxy);
    if ( pProxyInfo.lpszProxyBypass )
      return GlobalFree(pProxyInfo.lpszProxyBypass);
  }
  return result;
}

```

## disassembly

```asm
0x180038f8c  mov     [rsp-18h+arg_8], rbx
0x180038f91  mov     [rsp-18h+arg_10], rsi
0x180038f96  push    rbp
0x180038f97  push    rdi
0x180038f98  push    r14
0x180038f9a  mov     rbp, rsp
0x180038f9d  sub     rsp, 70h
0x180038fa1  mov     r14, rdx
0x180038fa4  mov     rbx, rcx
0x180038fa7  mov     word ptr [rcx], 0
0x180038fac  lea     rdi, [rcx+20h]
0x180038fb0  mov     qword ptr [rdi+10h], 0
0x180038fb8  cmp     qword ptr [rdi+18h], 7
0x180038fbd  jbe     short loc_180038FC4
0x180038fbf  mov     rcx, [rdi]
0x180038fc2  jmp     short loc_180038FC7
0x180038fc4  mov     rcx, rdi
0x180038fc7  xor     eax, eax
0x180038fc9  mov     [rcx], ax
0x180038fcc  lea     rsi, [rbx+8]
0x180038fd0  mov     rdx, [rsi+8]
0x180038fd4  cmp     [rsi], rdx
0x180038fd7  jz      short loc_180038FE8
0x180038fd9  mov     rcx, [rsi]; this
0x180038fdc  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180038fe1  mov     rax, [rsi]
0x180038fe4  mov     [rsi+8], rax
0x180038fe8  mov     [rbp+arg_0], 0
0x180038fef  xor     r8d, r8d
0x180038ff2  lea     rdx, [rbp+arg_0]
0x180038ff6  xor     ecx, ecx
0x180038ff8  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180038ffe  cmp     [rbp+arg_0], 5
0x180039002  jz      loc_180039153
0x180039008  xorps   xmm0, xmm0
0x18003900b  xor     eax, eax
0x18003900d  movups  xmmword ptr [rbp+pProxyInfo.dwAccessType], xmm0
0x180039011  mov     [rbp+pProxyInfo.lpszProxyBypass], rax
0x180039015  lea     rcx, [rbp+pProxyInfo]; pProxyInfo
0x180039019  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18003901f  mov     rcx, [rbp+18h]; this
0x180039023  test    eax, eax
0x180039025  jnz     short loc_180039037
0x180039027  lea     r8, aOnecoreuapEndu_32; "onecoreuap\\enduser\\winstore\\services"...
0x18003902e  lea     edx, [rax+74h]; void *
0x180039031  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180039037  cmp     [rbp+pProxyInfo.dwAccessType], 3
0x18003903b  jnz     short loc_180039081
0x18003903d  mov     byte ptr [rbx], 1
0x180039040  mov     r8, [rbp+pProxyInfo.lpszProxy]
0x180039044  mov     rdx, r14
0x180039047  lea     rcx, [rbp+var_38]
0x18003904b  call    ?GetProxyVectorFromList@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBG@Z; GetProxyVectorFromList(std::wstring const &,ushort const *)
0x180039050  mov     rdx, rax
0x180039053  mov     rcx, rsi
0x180039056  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x18003905b  lea     rcx, [rbp+var_38]
0x18003905f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180039064  mov     rcx, [rbp+pProxyInfo.lpszProxyBypass]
0x180039068  test    rcx, rcx
0x18003906b  jz      loc_180039135
0x180039071  mov     rdx, rcx
0x180039074  mov     rcx, rdi
0x180039077  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18003907c  jmp     loc_180039135
0x180039081  xorps   xmm0, xmm0
0x180039084  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm0
0x180039088  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x18003908c  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x180039090  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180039096  test    eax, eax
0x180039098  jz      short loc_180039104
0x18003909a  cmp     [rbp+pProxyConfig.fAutoDetect], 0
0x18003909e  jz      short loc_1800390A4
0x1800390a0  mov     byte ptr [rbx+1], 1
0x1800390a4  mov     rax, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x1800390a8  test    rax, rax
0x1800390ab  jz      short loc_1800390C0
0x1800390ad  mov     byte ptr [rbx], 1
0x1800390b0  mov     byte ptr [rbx+2], 1
0x1800390b4  lea     rcx, [rbx+40h]
0x1800390b8  mov     rdx, rax
0x1800390bb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800390c0  mov     rcx, [rbp+pProxyConfig.lpszProxy]
0x1800390c4  test    rcx, rcx
0x1800390c7  jz      short loc_180039104
0x1800390c9  mov     byte ptr [rbx], 1
0x1800390cc  mov     r8, rcx
0x1800390cf  mov     rdx, r14
0x1800390d2  lea     rcx, [rbp+var_38]
0x1800390d6  call    ?GetProxyVectorFromList@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBG@Z; GetProxyVectorFromList(std::wstring const &,ushort const *)
0x1800390db  mov     rdx, rax
0x1800390de  mov     rcx, rsi
0x1800390e1  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x1800390e6  lea     rcx, [rbp+var_38]
0x1800390ea  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800390ef  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]
0x1800390f3  test    rcx, rcx
0x1800390f6  jz      short loc_180039104
0x1800390f8  mov     rdx, rcx
0x1800390fb  mov     rcx, rdi
0x1800390fe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180039103  nop
0x180039104  mov     rax, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x180039108  test    rax, rax
0x18003910b  jz      short loc_180039116
0x18003910d  mov     rcx, rax; hMem
0x180039110  call    cs:__imp_GlobalFree
0x180039116  mov     rcx, [rbp+pProxyConfig.lpszProxy]; hMem
0x18003911a  test    rcx, rcx
0x18003911d  jz      short loc_180039125
0x18003911f  call    cs:__imp_GlobalFree
0x180039125  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]; hMem
0x180039129  test    rcx, rcx
0x18003912c  jz      short loc_180039135
0x18003912e  call    cs:__imp_GlobalFree
0x180039134  nop
0x180039135  mov     rcx, [rbp+pProxyInfo.lpszProxy]; hMem
0x180039139  test    rcx, rcx
0x18003913c  jz      short loc_180039144
0x18003913e  call    cs:__imp_GlobalFree
0x180039144  mov     rcx, [rbp+pProxyInfo.lpszProxyBypass]; hMem
0x180039148  test    rcx, rcx
0x18003914b  jz      short loc_180039153
0x18003914d  call    cs:__imp_GlobalFree
0x180039153  lea     r11, [rsp+70h+var_s0]
0x180039158  mov     rbx, [r11+28h]
0x18003915c  mov     rsi, [r11+30h]
0x180039160  mov     rsp, r11
0x180039163  pop     r14
0x180039165  pop     rdi
0x180039166  pop     rbp
0x180039167  retn
```
