# ProxySettings::Capture(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180046eac`
- end: `0x1800471cf`
- name: `?Capture@ProxySettings@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `803`
- prototype: `unsigned int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800374d4`

## callees

- `0x18000dc5b`
- `0x180030a68`
- `0x180030aac`
- `0x180034948`
- `0x180037ba8`
- `0x180046eac`
- `0x180047988`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180046f27`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180046f27`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047162`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047171`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047180`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047190`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004719f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047162`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047171`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047180`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180047190`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004719f`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180046f48`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180046f48`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180047027`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180047027`

## string_xrefs

- `0x1800471bd`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall ProxySettings::Capture(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  _QWORD *v4; // rsi
  unsigned __int64 *v5; // r13
  _WORD *v6; // rcx
  _QWORD *v7; // r14
  char **v8; // rdi
  char **v9; // rbx
  unsigned int result; // eax
  const char *v11; // r9
  _QWORD *ProxyVectorFromList; // rbx
  LPWSTR lpszProxyBypass; // rcx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rdi
  LPWSTR lpszAutoConfigUrl; // rcx
  unsigned __int64 v17; // rdx
  char *v18; // r12
  __int64 v19; // rbx
  LPWSTR lpszProxy; // rcx
  _QWORD *v21; // rbx
  LPWSTR v22; // rcx
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v24[24]; // [rsp+38h] [rbp-38h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v27; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+48h]

  v28 = a2;
  v2 = a2;
  *(_WORD *)a1 = 0;
  v4 = (_QWORD *)(a1 + 32);
  v5 = (unsigned __int64 *)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  if ( *(_QWORD *)(a1 + 56) <= 7u )
    v6 = (_WORD *)(a1 + 32);
  else
    v6 = (_WORD *)*v4;
  *v6 = 0;
  v7 = (_QWORD *)(a1 + 8);
  v8 = *(char ***)(a1 + 16);
  v9 = *(char ***)(a1 + 8);
  if ( v9 != v8 )
  {
    do
    {
      std::wstring::_Tidy_deallocate(v9);
      v9 += 4;
    }
    while ( v9 != v8 );
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  }
  v27 = 0;
  result = RtlGetDeviceFamilyInfoEnum(0, &v27, 0);
  if ( v27 != 5 )
  {
    memset(&pProxyInfo, 0, sizeof(pProxyInfo));
    if ( !WinHttpGetDefaultProxyConfiguration(&pProxyInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x74,
        (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
        v11);
    if ( pProxyInfo.dwAccessType == 3 )
    {
      *(_BYTE *)a1 = 1;
      ProxyVectorFromList = (_QWORD *)GetProxyVectorFromList(v24, v2, pProxyInfo.lpszProxy);
      if ( v7 != ProxyVectorFromList )
      {
        std::vector<std::wstring>::_Tidy(a1 + 8);
        *v7 = *ProxyVectorFromList;
        *(_QWORD *)(a1 + 16) = ProxyVectorFromList[1];
        *(_QWORD *)(a1 + 24) = ProxyVectorFromList[2];
        *ProxyVectorFromList = 0;
        ProxyVectorFromList[1] = 0;
        ProxyVectorFromList[2] = 0;
      }
      result = std::vector<std::wstring>::_Tidy(v24);
      lpszProxyBypass = pProxyInfo.lpszProxyBypass;
      if ( pProxyInfo.lpszProxyBypass )
      {
        v14 = -1;
        do
          ++v14;
        while ( pProxyInfo.lpszProxyBypass[v14] );
        if ( v14 > v4[3] )
        {
          result = std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v4);
        }
        else
        {
          if ( v4[3] > 7u )
            v4 = (_QWORD *)*v4;
          *v5 = v14;
          result = (unsigned int)memmove_0(v4, lpszProxyBypass, 2 * v14);
          *((_WORD *)v4 + v14) = 0;
        }
      }
    }
    else
    {
      memset(&pProxyConfig, 0, sizeof(pProxyConfig));
      result = WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig);
      if ( result )
      {
        if ( pProxyConfig.fAutoDetect )
          *(_BYTE *)(a1 + 1) = 1;
        v15 = -1;
        lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
        if ( pProxyConfig.lpszAutoConfigUrl )
        {
          *(_BYTE *)a1 = 1;
          *(_BYTE *)(a1 + 2) = 1;
          v17 = -1;
          do
            ++v17;
          while ( lpszAutoConfigUrl[v17] );
          if ( v17 > *(_QWORD *)(a1 + 88) )
          {
            result = std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1 + 64);
          }
          else
          {
            if ( *(_QWORD *)(a1 + 88) <= 7u )
              v18 = (char *)(a1 + 64);
            else
              v18 = *(char **)(a1 + 64);
            *(_QWORD *)(a1 + 80) = v17;
            v19 = 2 * v17;
            memmove_0(v18, lpszAutoConfigUrl, 2 * v17);
            result = 0;
            *(_WORD *)&v18[v19] = 0;
            v2 = v28;
          }
        }
        lpszProxy = pProxyConfig.lpszProxy;
        if ( pProxyConfig.lpszProxy )
        {
          *(_BYTE *)a1 = 1;
          v21 = (_QWORD *)GetProxyVectorFromList(v24, v2, lpszProxy);
          if ( v7 != v21 )
          {
            std::vector<std::wstring>::_Tidy(a1 + 8);
            *v7 = *v21;
            *(_QWORD *)(a1 + 16) = v21[1];
            *(_QWORD *)(a1 + 24) = v21[2];
            *v21 = 0;
            v21[1] = 0;
            v21[2] = 0;
          }
          result = std::vector<std::wstring>::_Tidy(v24);
          v22 = pProxyConfig.lpszProxyBypass;
          if ( pProxyConfig.lpszProxyBypass )
          {
            do
              ++v15;
            while ( pProxyConfig.lpszProxyBypass[v15] );
            if ( v15 > v4[3] )
            {
              result = std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v4);
            }
            else
            {
              if ( v4[3] > 7u )
                v4 = (_QWORD *)*v4;
              *v5 = v15;
              result = (unsigned int)memmove_0(v4, v22, 2 * v15);
              *((_WORD *)v4 + v15) = 0;
            }
          }
        }
      }
      if ( pProxyConfig.lpszAutoConfigUrl )
        result = (unsigned int)GlobalFree(pProxyConfig.lpszAutoConfigUrl);
      if ( pProxyConfig.lpszProxy )
        result = (unsigned int)GlobalFree(pProxyConfig.lpszProxy);
      if ( pProxyConfig.lpszProxyBypass )
        result = (unsigned int)GlobalFree(pProxyConfig.lpszProxyBypass);
    }
    if ( pProxyInfo.lpszProxy )
      result = (unsigned int)GlobalFree(pProxyInfo.lpszProxy);
    if ( pProxyInfo.lpszProxyBypass )
      return (unsigned int)GlobalFree(pProxyInfo.lpszProxyBypass);
  }
  return result;
}

```

## disassembly

```asm
0x180046eac  mov     [rsp-38h+arg_10], rbx
0x180046eb1  mov     [rsp-38h+arg_8], rdx
0x180046eb6  push    rbp
0x180046eb7  push    rsi
0x180046eb8  push    rdi
0x180046eb9  push    r12
0x180046ebb  push    r13
0x180046ebd  push    r14
0x180046ebf  push    r15
0x180046ec1  mov     rbp, rsp
0x180046ec4  sub     rsp, 70h
0x180046ec8  mov     r12, rdx
0x180046ecb  mov     r15, rcx
0x180046ece  xor     eax, eax
0x180046ed0  mov     [rcx], ax
0x180046ed3  lea     rsi, [rcx+20h]
0x180046ed7  lea     r13, [rsi+10h]
0x180046edb  mov     [r13+0], rax
0x180046edf  cmp     qword ptr [rsi+18h], 7
0x180046ee4  jbe     short loc_180046EEB
0x180046ee6  mov     rcx, [rsi]
0x180046ee9  jmp     short loc_180046EEE
0x180046eeb  mov     rcx, rsi
0x180046eee  mov     [rcx], ax
0x180046ef1  lea     r14, [r15+8]
0x180046ef5  mov     rdi, [r14+8]
0x180046ef9  mov     rbx, [r14]
0x180046efc  cmp     rbx, rdi
0x180046eff  jz      short loc_180046F19
0x180046f01  mov     rcx, rbx
0x180046f04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046f09  add     rbx, 20h ; ' '
0x180046f0d  cmp     rbx, rdi
0x180046f10  jnz     short loc_180046F01
0x180046f12  mov     rax, [r14]
0x180046f15  mov     [r14+8], rax
0x180046f19  xor     ebx, ebx
0x180046f1b  mov     [rbp+arg_0], ebx
0x180046f1e  xor     r8d, r8d
0x180046f21  lea     rdx, [rbp+arg_0]
0x180046f25  xor     ecx, ecx
0x180046f27  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180046f2d  cmp     [rbp+arg_0], 5
0x180046f31  jz      loc_1800471A5
0x180046f37  xorps   xmm0, xmm0
0x180046f3a  xor     eax, eax
0x180046f3c  movups  xmmword ptr [rbp+pProxyInfo.dwAccessType], xmm0
0x180046f40  mov     [rbp+pProxyInfo.lpszProxyBypass], rax
0x180046f44  lea     rcx, [rbp+pProxyInfo]; pProxyInfo
0x180046f48  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x180046f4e  mov     rcx, [rbp+38h]; this
0x180046f52  test    eax, eax
0x180046f54  jz      loc_1800471BD
0x180046f5a  cmp     [rbp+pProxyInfo.dwAccessType], 3
0x180046f5e  jnz     loc_180047018
0x180046f64  mov     byte ptr [r15], 1
0x180046f68  mov     r8, [rbp+pProxyInfo.lpszProxy]
0x180046f6c  mov     rdx, r12
0x180046f6f  lea     rcx, [rbp+var_38]
0x180046f73  call    ?GetProxyVectorFromList@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBG@Z; GetProxyVectorFromList(std::wstring const &,ushort const *)
0x180046f78  mov     rbx, rax
0x180046f7b  cmp     r14, rax
0x180046f7e  jz      short loc_180046FAE
0x180046f80  mov     rcx, r14
0x180046f83  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180046f88  mov     rcx, [rbx]
0x180046f8b  mov     [r14], rcx
0x180046f8e  mov     rcx, [rbx+8]
0x180046f92  mov     [r14+8], rcx
0x180046f96  mov     rcx, [rbx+10h]
0x180046f9a  mov     [r14+10h], rcx
0x180046f9e  xor     r14d, r14d
0x180046fa1  mov     [rbx], r14
0x180046fa4  mov     [rbx+8], r14
0x180046fa8  mov     [rbx+10h], r14
0x180046fac  jmp     short loc_180046FB1
0x180046fae  xor     r14d, r14d
0x180046fb1  lea     rcx, [rbp+var_38]
0x180046fb5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180046fba  mov     rcx, [rbp+pProxyInfo.lpszProxyBypass]
0x180046fbe  test    rcx, rcx
0x180046fc1  jz      loc_180047187
0x180046fc7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046fcb  inc     rdi
0x180046fce  cmp     [rcx+rdi*2], r14w
0x180046fd3  jnz     short loc_180046FCB
0x180046fd5  cmp     rdi, [rsi+18h]
0x180046fd9  ja      short loc_180047005
0x180046fdb  cmp     qword ptr [rsi+18h], 7
0x180046fe0  jbe     short loc_180046FE5
0x180046fe2  mov     rsi, [rsi]
0x180046fe5  mov     [r13+0], rdi
0x180046fe9  lea     rbx, [rdi+rdi]
0x180046fed  mov     r8, rbx; Size
0x180046ff0  mov     rdx, rcx; Src
0x180046ff3  mov     rcx, rsi; void *
0x180046ff6  call    memmove_0
0x180046ffb  mov     [rbx+rsi], r14w
0x180047000  jmp     loc_180047187
0x180047005  mov     r9, rcx
0x180047008  mov     rdx, rdi
0x18004700b  mov     rcx, rsi
0x18004700e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180047013  jmp     loc_180047187
0x180047018  xorps   xmm0, xmm0
0x18004701b  movups  xmmword ptr [rbp+pProxyConfig.fAutoDetect], xmm0
0x18004701f  movups  xmmword ptr [rbp+pProxyConfig.lpszProxy], xmm0
0x180047023  lea     rcx, [rbp+pProxyConfig]; pProxyConfig
0x180047027  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18004702d  test    eax, eax
0x18004702f  jz      loc_180047159
0x180047035  cmp     [rbp+pProxyConfig.fAutoDetect], ebx
0x180047038  jz      short loc_18004703F
0x18004703a  mov     byte ptr [r15+1], 1
0x18004703f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180047043  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]
0x180047047  test    rcx, rcx
0x18004704a  jz      short loc_1800470A8
0x18004704c  mov     byte ptr [r15], 1
0x180047050  mov     byte ptr [r15+2], 1
0x180047055  lea     rax, [r15+40h]
0x180047059  mov     rdx, rdi
0x18004705c  inc     rdx
0x18004705f  cmp     [rcx+rdx*2], bx
0x180047063  jnz     short loc_18004705C
0x180047065  cmp     rdx, [rax+18h]
0x180047069  ja      short loc_18004709D
0x18004706b  cmp     qword ptr [rax+18h], 7
0x180047070  jbe     short loc_180047077
0x180047072  mov     r12, [rax]
0x180047075  jmp     short loc_18004707A
0x180047077  mov     r12, rax
0x18004707a  mov     [rax+10h], rdx
0x18004707e  lea     rbx, [rdx+rdx]
0x180047082  mov     r8, rbx; Size
0x180047085  mov     rdx, rcx; Src
0x180047088  mov     rcx, r12; void *
0x18004708b  call    memmove_0
0x180047090  xor     eax, eax
0x180047092  mov     [rbx+r12], ax
0x180047097  mov     r12, [rbp+arg_8]
0x18004709b  jmp     short loc_1800470A8
0x18004709d  mov     r9, rcx
0x1800470a0  mov     rcx, rax
0x1800470a3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800470a8  mov     rcx, [rbp+pProxyConfig.lpszProxy]
0x1800470ac  test    rcx, rcx
0x1800470af  jz      loc_180047159
0x1800470b5  mov     byte ptr [r15], 1
0x1800470b9  mov     r8, rcx
0x1800470bc  mov     rdx, r12
0x1800470bf  lea     rcx, [rbp+var_38]
0x1800470c3  call    ?GetProxyVectorFromList@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBG@Z; GetProxyVectorFromList(std::wstring const &,ushort const *)
0x1800470c8  mov     rbx, rax
0x1800470cb  cmp     r14, rax
0x1800470ce  jz      short loc_1800470FE
0x1800470d0  mov     rcx, r14
0x1800470d3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800470d8  mov     rcx, [rbx]
0x1800470db  mov     [r14], rcx
0x1800470de  mov     rcx, [rbx+8]
0x1800470e2  mov     [r14+8], rcx
0x1800470e6  mov     rcx, [rbx+10h]
0x1800470ea  mov     [r14+10h], rcx
0x1800470ee  xor     r14d, r14d
0x1800470f1  mov     [rbx], r14
0x1800470f4  mov     [rbx+8], r14
0x1800470f8  mov     [rbx+10h], r14
0x1800470fc  jmp     short loc_180047101
0x1800470fe  xor     r14d, r14d
0x180047101  lea     rcx, [rbp+var_38]
0x180047105  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004710a  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]
0x18004710e  test    rcx, rcx
0x180047111  jz      short loc_180047159
0x180047113  inc     rdi
0x180047116  cmp     [rcx+rdi*2], r14w
0x18004711b  jnz     short loc_180047113
0x18004711d  cmp     rdi, [rsi+18h]
0x180047121  ja      short loc_18004714A
0x180047123  cmp     qword ptr [rsi+18h], 7
0x180047128  jbe     short loc_18004712D
0x18004712a  mov     rsi, [rsi]
0x18004712d  mov     [r13+0], rdi
0x180047131  lea     rbx, [rdi+rdi]
0x180047135  mov     r8, rbx; Size
0x180047138  mov     rdx, rcx; Src
0x18004713b  mov     rcx, rsi; void *
0x18004713e  call    memmove_0
0x180047143  mov     [rbx+rsi], r14w
0x180047148  jmp     short loc_180047159
0x18004714a  mov     r9, rcx
0x18004714d  mov     rdx, rdi
0x180047150  mov     rcx, rsi
0x180047153  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180047158  nop
0x180047159  mov     rcx, [rbp+pProxyConfig.lpszAutoConfigUrl]; hMem
0x18004715d  test    rcx, rcx
0x180047160  jz      short loc_180047168
0x180047162  call    cs:__imp_GlobalFree
0x180047168  mov     rcx, [rbp+pProxyConfig.lpszProxy]; hMem
0x18004716c  test    rcx, rcx
0x18004716f  jz      short loc_180047177
0x180047171  call    cs:__imp_GlobalFree
0x180047177  mov     rcx, [rbp+pProxyConfig.lpszProxyBypass]; hMem
0x18004717b  test    rcx, rcx
0x18004717e  jz      short loc_180047187
0x180047180  call    cs:__imp_GlobalFree
0x180047186  nop
0x180047187  mov     rcx, [rbp+pProxyInfo.lpszProxy]; hMem
0x18004718b  test    rcx, rcx
0x18004718e  jz      short loc_180047196
0x180047190  call    cs:__imp_GlobalFree
0x180047196  mov     rcx, [rbp+pProxyInfo.lpszProxyBypass]; hMem
0x18004719a  test    rcx, rcx
0x18004719d  jz      short loc_1800471A5
0x18004719f  call    cs:__imp_GlobalFree
0x1800471a5  mov     rbx, [rsp+70h+arg_10]
0x1800471ad  add     rsp, 70h
0x1800471b1  pop     r15
0x1800471b3  pop     r14
0x1800471b5  pop     r13
0x1800471b7  pop     r12
0x1800471b9  pop     rdi
0x1800471ba  pop     rsi
0x1800471bb  pop     rbp
0x1800471bc  retn
0x1800471bd  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x1800471c4  mov     edx, 74h ; 't'; void *
0x1800471c9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
