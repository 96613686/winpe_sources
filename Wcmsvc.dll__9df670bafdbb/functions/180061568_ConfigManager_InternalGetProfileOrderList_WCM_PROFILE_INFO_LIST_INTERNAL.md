# ConfigManager::InternalGetProfileOrderList(_WCM_PROFILE_INFO_LIST_INTERNAL * *)

- ea: `0x180061568`
- end: `0x180061a1c`
- name: `?InternalGetProfileOrderList@ConfigManager@@AEAAJPEAPEAU_WCM_PROFILE_INFO_LIST_INTERNAL@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(ConfigManager *__hidden this, struct _WCM_PROFILE_INFO_LIST_INTERNAL **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006e224`

## callees

- `0x1800137a0`
- `0x180017ad0`
- `0x180019434`
- `0x18001b970`
- `0x18001f7d0`
- `0x180027250`
- `0x180027630`
- `0x180027660`
- `0x18004b9fc`
- `0x180061568`
- `0x180061a30`
- `0x1800622cc`
- `0x180084f50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180061703`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180061732`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180061703`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180061732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800616b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800617c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006183a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800618ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061953`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800619cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800619e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800616b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800617c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006183a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800618ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061953`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800619cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800619e3`
- `RPCRT4!UuidFromStringW` at `0x18006186d`
- `RPCRT4!UuidFromStringW` at `0x18006186d`

## string_xrefs

- `0x180061628`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x18006168b`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180061790`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x18006180c`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x1800618ba`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x18006199f`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall ConfigManager::InternalGetProfileOrderList(
        ConfigManager *this,
        struct _WCM_PROFILE_INFO_LIST_INTERNAL **a2)
{
  ConfigManager *v3; // rcx
  __int64 v4; // rcx
  signed __int64 v5; // rax
  unsigned int v6; // ebx
  __int64 v8; // r15
  unsigned int *v9; // rax
  unsigned int *v10; // rsi
  unsigned int v11; // edi
  RPC_WSTR v12; // rbx
  RPC_WSTR v13; // r13
  unsigned __int64 v14; // rcx
  RPC_WSTR v15; // rcx
  RPC_WSTR v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  const unsigned __int16 *v19; // r8
  int v20; // eax
  unsigned int v21; // r14d
  unsigned __int16 *v22; // rcx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  RPC_WSTR StringUuid[2]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v27; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, &s_keyLock);
  ConfigManager::InternalInit(v3);
  if ( s_wcmRootKey )
  {
    *(_OWORD *)StringUuid = 0;
    v27 = 0;
    WcmCommon::Registry::Key::GetMultiSzValue(v4, StringUuid);
    v5 = ((char *)StringUuid[1] - (char *)StringUuid[0]) >> 5;
    if ( (v5 & 3) != 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
      }
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x565,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
             (const char *)0x139F,
             (unsigned int)lpCriticalSection);
      std::vector<std::wstring>::_Tidy(StringUuid);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return v6;
    }
    else
    {
      v8 = (unsigned int)v5 >> 2;
      v9 = (unsigned int *)WcmAlloc(536 * v8 + 540);
      v10 = v9;
      if ( v9 )
      {
        *v9 = v8;
        v11 = 0;
        v12 = StringUuid[0];
        v13 = StringUuid[1];
        while ( v12 != v13 )
        {
          v14 = *((_QWORD *)v12 + 3);
          if ( (v11 & 3) != 0 )
          {
            if ( (v11 & 3) == 1 )
            {
              if ( v14 <= 7 )
                v19 = v12;
              else
                v19 = *(const unsigned __int16 **)v12;
              v20 = StringCchCopyW((unsigned __int16 *)&v10[134 * ((unsigned __int64)v11 >> 2) + 1], 0x100u, v19);
              v21 = v20;
              if ( v20 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x58B,
                  (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                  (const char *)(unsigned int)v20,
                  (int)lpCriticalSection);
                WcmFree(v10);
                std::vector<std::wstring>::_Tidy(StringUuid);
                if ( lpCriticalSection )
                  LeaveCriticalSection(lpCriticalSection);
                return v21;
              }
            }
            else if ( (v11 & 3) == 2 )
            {
              if ( v14 <= 7 )
                v16 = v12;
              else
                v16 = *(RPC_WSTR *)v12;
              v17 = _o__wtoi(v16);
              v10[134 * ((unsigned __int64)v11 >> 2) + 133] = v17;
              if ( v17 >= 5 )
              {
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
                }
                v18 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x598,
                        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                        (const char *)0x139F,
                        (unsigned int)lpCriticalSection);
                WcmFree(v10);
                std::vector<std::wstring>::_Tidy(StringUuid);
                if ( lpCriticalSection )
                  LeaveCriticalSection(lpCriticalSection);
                return v18;
              }
            }
            else
            {
              if ( v14 <= 7 )
                v15 = v12;
              else
                v15 = *(RPC_WSTR *)v12;
              v10[134 * ((unsigned __int64)v11 >> 2) + 134] = _o__wtoi(v15);
            }
          }
          else
          {
            if ( v14 <= 7 )
              v22 = v12;
            else
              v22 = *(unsigned __int16 **)v12;
            if ( UuidFromStringW(v22, (UUID *)&v10[134 * ((unsigned __int64)v11 >> 2) + 129]) )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
              }
              v23 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x582,
                      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                      (const char *)0x139F,
                      (unsigned int)lpCriticalSection);
              WcmFree(v10);
              std::vector<std::wstring>::_Tidy(StringUuid);
              if ( lpCriticalSection )
                LeaveCriticalSection(lpCriticalSection);
              return v23;
            }
          }
          ++v11;
          v12 += 16;
        }
        if ( (v11 & 3) != 0 || v11 >> 2 != (_DWORD)v8 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
          }
          v24 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x5A9,
                  (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                  (const char *)0x139F,
                  (unsigned int)lpCriticalSection);
          WcmFree(v10);
          std::vector<std::wstring>::_Tidy(StringUuid);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          return v24;
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, *v10);
          }
          *a2 = (struct _WCM_PROFILE_INFO_LIST_INTERNAL *)v10;
          std::vector<std::wstring>::_Tidy(StringUuid);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          return 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56E,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
          (const char *)0x8007000ELL,
          (int)lpCriticalSection);
        std::vector<std::wstring>::_Tidy(StringUuid);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        return 2147942414LL;
      }
    }
  }
  else
  {
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180061568  mov     r11, rsp
0x18006156b  mov     [r11+8], rbx
0x18006156f  mov     [r11+18h], rsi
0x180061573  push    rdi
0x180061574  push    r12
0x180061576  push    r13
0x180061578  push    r14
0x18006157a  push    r15
0x18006157c  sub     rsp, 50h
0x180061580  mov     rax, cs:__security_cookie
0x180061587  xor     rax, rsp
0x18006158a  mov     [rsp+78h+var_38], rax
0x18006158f  mov     r12, rdx
0x180061592  mov     qword ptr [r11-58h], 0
0x18006159a  lea     rdx, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x1800615a1  lea     rcx, [r11-58h]
0x1800615a5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800615aa  nop
0x1800615ab  call    ?InternalInit@ConfigManager@@AEAAXXZ; ConfigManager::InternalInit(void)
0x1800615b0  cmp     cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootKey
0x1800615b8  jz      loc_1800619D9
0x1800615be  xorps   xmm0, xmm0
0x1800615c1  xor     eax, eax
0x1800615c3  movups  xmmword ptr [rsp+78h+StringUuid], xmm0
0x1800615c8  mov     [rsp+78h+var_40], rax
0x1800615cd  lea     rdx, [rsp+78h+StringUuid]
0x1800615d2  call    ?GetMultiSzValue@Key@Registry@WcmCommon@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBG@Z; WcmCommon::Registry::Key::GetMultiSzValue(ushort const * const)
0x1800615d7  mov     rax, [rsp+78h+StringUuid+8]
0x1800615dc  sub     rax, [rsp+78h+StringUuid]
0x1800615e1  sar     rax, 5
0x1800615e5  test    al, 3
0x1800615e7  jz      short loc_18006165D
0x1800615e9  lea     rax, WPP_GLOBAL_Control
0x1800615f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800615f7  cmp     rcx, rax
0x1800615fa  jz      short loc_18006161D
0x1800615fc  cmp     byte ptr [rcx+19h], 2
0x180061600  jb      short loc_18006161D
0x180061602  test    byte ptr [rcx+1Ch], 1
0x180061606  jz      short loc_18006161D
0x180061608  mov     edx, 34h ; '4'
0x18006160d  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x180061614  mov     rcx, [rcx+10h]
0x180061618  call    WPP_SF_
0x18006161d  mov     rcx, [rsp+78h]; this
0x180061622  mov     r9d, 139Fh; char *
0x180061628  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x18006162f  mov     edx, 565h; void *
0x180061634  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061639  mov     ebx, eax
0x18006163b  lea     rcx, [rsp+78h+StringUuid]
0x180061640  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180061645  nop
0x180061646  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18006164b  test    rcx, rcx
0x18006164e  jz      short loc_180061656
0x180061650  call    cs:__imp_LeaveCriticalSection
0x180061656  mov     eax, ebx
0x180061658  jmp     loc_1800619F4
0x18006165d  shr     eax, 2
0x180061660  mov     r15d, eax
0x180061663  imul    rcx, r15, 218h
0x18006166a  add     rcx, 21Ch; dwBytes
0x180061671  call    WcmAlloc
0x180061676  mov     rsi, rax
0x180061679  test    rax, rax
0x18006167c  jnz     short loc_1800616BE
0x18006167e  mov     rcx, [rsp+78h]; this
0x180061683  mov     ebx, 8007000Eh
0x180061688  mov     r9d, ebx; char *
0x18006168b  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061692  mov     edx, 56Eh; void *
0x180061697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006169c  lea     rcx, [rsp+78h+StringUuid]
0x1800616a1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800616a6  nop
0x1800616a7  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800616ac  test    rcx, rcx
0x1800616af  jz      short loc_1800616B7
0x1800616b1  call    cs:__imp_LeaveCriticalSection
0x1800616b7  mov     eax, ebx
0x1800616b9  jmp     loc_1800619F4
0x1800616be  mov     [rax], r15d
0x1800616c1  xor     edi, edi
0x1800616c3  mov     rbx, [rsp+78h+StringUuid]
0x1800616c8  mov     r13, [rsp+78h+StringUuid+8]
0x1800616cd  mov     eax, edi
0x1800616cf  and     eax, 3
0x1800616d2  cmp     rbx, r13
0x1800616d5  jz      loc_1800618F7
0x1800616db  mov     rcx, [rbx+18h]
0x1800616df  test    eax, eax
0x1800616e1  jz      loc_180061848
0x1800616e7  sub     eax, 1
0x1800616ea  jz      loc_1800617CD
0x1800616f0  cmp     eax, 1
0x1800616f3  jz      short loc_180061724
0x1800616f5  cmp     rcx, 7
0x1800616f9  jbe     short loc_180061700
0x1800616fb  mov     rcx, [rbx]
0x1800616fe  jmp     short loc_180061703
0x180061700  mov     rcx, rbx
0x180061703  call    cs:__imp__o__wtoi
0x180061709  mov     ecx, edi
0x18006170b  shr     rcx, 2
0x18006170f  inc     rcx
0x180061712  imul    rcx, 218h
0x180061719  mov     [rcx+rsi], eax
0x18006171c  inc     edi
0x18006171e  add     rbx, 20h ; ' '
0x180061722  jmp     short loc_1800616CD
0x180061724  cmp     rcx, 7
0x180061728  jbe     short loc_18006172F
0x18006172a  mov     rcx, [rbx]
0x18006172d  jmp     short loc_180061732
0x18006172f  mov     rcx, rbx
0x180061732  call    cs:__imp__o__wtoi
0x180061738  mov     ecx, edi
0x18006173a  shr     rcx, 2
0x18006173e  imul    rcx, 218h
0x180061745  mov     [rcx+rsi+214h], eax
0x18006174c  cmp     eax, 5
0x18006174f  jl      short loc_18006171C
0x180061751  lea     rax, WPP_GLOBAL_Control
0x180061758  mov     rcx, cs:WPP_GLOBAL_Control
0x18006175f  cmp     rcx, rax
0x180061762  jz      short loc_180061785
0x180061764  cmp     byte ptr [rcx+19h], 3
0x180061768  jb      short loc_180061785
0x18006176a  test    byte ptr [rcx+1Ch], 1
0x18006176e  jz      short loc_180061785
0x180061770  mov     edx, 36h ; '6'
0x180061775  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18006177c  mov     rcx, [rcx+10h]
0x180061780  call    WPP_SF_
0x180061785  mov     rcx, [rsp+78h]; this
0x18006178a  mov     r9d, 139Fh; char *
0x180061790  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061797  mov     edx, 598h; void *
0x18006179c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800617a1  mov     ebx, eax
0x1800617a3  mov     rcx, rsi; lpMem
0x1800617a6  call    WcmFree
0x1800617ab  lea     rcx, [rsp+78h+StringUuid]
0x1800617b0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800617b5  nop
0x1800617b6  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800617bb  test    rcx, rcx
0x1800617be  jz      short loc_1800617C6
0x1800617c0  call    cs:__imp_LeaveCriticalSection
0x1800617c6  mov     eax, ebx
0x1800617c8  jmp     loc_1800619F4
0x1800617cd  cmp     rcx, 7
0x1800617d1  jbe     short loc_1800617D8
0x1800617d3  mov     r8, [rbx]
0x1800617d6  jmp     short loc_1800617DB
0x1800617d8  mov     r8, rbx; unsigned __int16 *
0x1800617db  mov     eax, edi
0x1800617dd  shr     rax, 2
0x1800617e1  imul    rcx, rax, 218h
0x1800617e8  add     rcx, 4
0x1800617ec  add     rcx, rsi; unsigned __int16 *
0x1800617ef  mov     edx, 100h; unsigned __int64
0x1800617f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800617f9  mov     r14d, eax
0x1800617fc  test    eax, eax
0x1800617fe  jns     loc_18006171C
0x180061804  mov     rcx, [rsp+78h]; this
0x180061809  mov     r9d, eax; char *
0x18006180c  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061813  mov     edx, 58Bh; void *
0x180061818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006181d  mov     rcx, rsi; lpMem
0x180061820  call    WcmFree
0x180061825  lea     rcx, [rsp+78h+StringUuid]
0x18006182a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006182f  nop
0x180061830  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x180061835  test    rcx, rcx
0x180061838  jz      short loc_180061840
0x18006183a  call    cs:__imp_LeaveCriticalSection
0x180061840  mov     eax, r14d
0x180061843  jmp     loc_1800619F4
0x180061848  mov     eax, edi
0x18006184a  shr     rax, 2
0x18006184e  imul    rdx, rax, 218h
0x180061855  add     rdx, 204h
0x18006185c  add     rdx, rsi; Uuid
0x18006185f  cmp     rcx, 7
0x180061863  jbe     short loc_18006186A
0x180061865  mov     rcx, [rbx]
0x180061868  jmp     short loc_18006186D
0x18006186a  mov     rcx, rbx; StringUuid
0x18006186d  call    cs:__imp_UuidFromStringW
0x180061873  test    eax, eax
0x180061875  jz      loc_18006171C
0x18006187b  lea     rax, WPP_GLOBAL_Control
0x180061882  mov     rcx, cs:WPP_GLOBAL_Control
0x180061889  cmp     rcx, rax
0x18006188c  jz      short loc_1800618AF
0x18006188e  cmp     byte ptr [rcx+19h], 2
0x180061892  jb      short loc_1800618AF
0x180061894  test    byte ptr [rcx+1Ch], 1
0x180061898  jz      short loc_1800618AF
0x18006189a  mov     edx, 35h ; '5'
0x18006189f  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x1800618a6  mov     rcx, [rcx+10h]
0x1800618aa  call    WPP_SF_
0x1800618af  mov     rcx, [rsp+78h]; this
0x1800618b4  mov     r9d, 139Fh; char *
0x1800618ba  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x1800618c1  mov     edx, 582h; void *
0x1800618c6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800618cb  mov     ebx, eax
0x1800618cd  mov     rcx, rsi; lpMem
0x1800618d0  call    WcmFree
0x1800618d5  lea     rcx, [rsp+78h+StringUuid]
0x1800618da  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800618df  nop
0x1800618e0  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800618e5  test    rcx, rcx
0x1800618e8  jz      short loc_1800618F0
0x1800618ea  call    cs:__imp_LeaveCriticalSection
0x1800618f0  mov     eax, ebx
0x1800618f2  jmp     loc_1800619F4
0x1800618f7  test    eax, eax
0x1800618f9  jnz     short loc_180061960
0x1800618fb  shr     edi, 2
0x1800618fe  cmp     edi, r15d
0x180061901  jnz     short loc_180061960
0x180061903  lea     rax, WPP_GLOBAL_Control
0x18006190a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061911  cmp     rcx, rax
0x180061914  jz      short loc_18006193A
0x180061916  cmp     byte ptr [rcx+19h], 4
0x18006191a  jb      short loc_18006193A
0x18006191c  test    byte ptr [rcx+1Ch], 1
0x180061920  jz      short loc_18006193A
0x180061922  mov     edx, 38h ; '8'
0x180061927  mov     r9d, [rsi]
0x18006192a  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x180061931  mov     rcx, [rcx+10h]
0x180061935  call    WPP_SF_d
0x18006193a  mov     [r12], rsi
0x18006193e  lea     rcx, [rsp+78h+StringUuid]
0x180061943  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180061948  nop
0x180061949  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18006194e  test    rcx, rcx
0x180061951  jz      short loc_180061959
0x180061953  call    cs:__imp_LeaveCriticalSection
0x180061959  xor     eax, eax
0x18006195b  jmp     loc_1800619F4
0x180061960  lea     rax, WPP_GLOBAL_Control
0x180061967  mov     rcx, cs:WPP_GLOBAL_Control
0x18006196e  cmp     rcx, rax
0x180061971  jz      short loc_180061994
0x180061973  cmp     byte ptr [rcx+19h], 2
0x180061977  jb      short loc_180061994
0x180061979  test    byte ptr [rcx+1Ch], 1
0x18006197d  jz      short loc_180061994
0x18006197f  mov     edx, 37h ; '7'
0x180061984  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x18006198b  mov     rcx, [rcx+10h]
0x18006198f  call    WPP_SF_
0x180061994  mov     rcx, [rsp+78h]; this
0x180061999  mov     r9d, 139Fh; char *
0x18006199f  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x1800619a6  mov     edx, 5A9h; void *
0x1800619ab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800619b0  mov     ebx, eax
0x1800619b2  mov     rcx, rsi; lpMem
0x1800619b5  call    WcmFree
0x1800619ba  lea     rcx, [rsp+78h+StringUuid]
0x1800619bf  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800619c4  nop
0x1800619c5  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800619ca  test    rcx, rcx
0x1800619cd  jz      short loc_1800619D5
0x1800619cf  call    cs:__imp_LeaveCriticalSection
0x1800619d5  mov     eax, ebx
0x1800619d7  jmp     short loc_1800619F4
0x1800619d9  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800619de  test    rcx, rcx
0x1800619e1  jz      short loc_1800619E9
0x1800619e3  call    cs:__imp_LeaveCriticalSection
0x1800619e9  mov     eax, 80070002h
0x1800619ee  jmp     short loc_1800619F4
0x1800619f0  mov     eax, dword ptr [rsp+78h+lpCriticalSection]
0x1800619f4  mov     rcx, [rsp+78h+var_38]
0x1800619f9  xor     rcx, rsp; StackCookie
0x1800619fc  call    __security_check_cookie
0x180061a01  lea     r11, [rsp+78h+var_28]
0x180061a06  mov     rbx, [r11+30h]
0x180061a0a  mov     rsi, [r11+40h]
0x180061a0e  mov     rsp, r11
0x180061a11  pop     r15
0x180061a13  pop     r14
0x180061a15  pop     r13
0x180061a17  pop     r12
  ... truncated ...
```
