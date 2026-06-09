# Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckForConsentData(void *,ushort const *,CAMStorageAccessRequestType,uchar *)

- ea: `0x1800f512c`
- end: `0x1800f5631`
- name: `?AccessCheckForConsentData@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBGW4CAMStorageAccessRequestType@@PEAE@Z`
- size: `1285`
- prototype: `size_t __fastcall(void *, wchar_t *, int, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800edbb0`

## callees

- `0x180003060`
- `0x1800e5e6c`
- `0x1800ed418`
- `0x1800ed70c`
- `0x1800edb4c`
- `0x1800f44fc`
- `0x1800f4fa0`
- `0x1800f512c`
- `0x1800f5638`
- `0x1800f5b7c`
- `0x1800f5bb4`
- `0x1800f5bd8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f5230`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f532c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f5463`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f54f2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f5230`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f532c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f5463`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f54f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f51b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f51b3`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x1800f51e4`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x1800f51e4`

## string_xrefs

- `0x1800f55a8`: `onecore\base\devices\cam\desktop\lib\storage\access.cpp`
- `0x1800f55c9`: `onecore\base\devices\cam\desktop\lib\storage\access.cpp`
- `0x1800f55fc`: `onecore\base\devices\cam\desktop\lib\storage\access.cpp`
- `0x1800f561f`: `onecore\base\devices\cam\desktop\lib\storage\access.cpp`
- `0x1800f55f0`: `CAMStorageAccessRequestType out of expected range, value %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
size_t __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckForConsentData(
        void *a1,
        wchar_t *a2,
        int a3,
        _BYTE *a4)
{
  size_t result; // rax
  unsigned int v9; // r8d
  const char *v10; // r9
  const char *v11; // r9
  char v12; // bl
  char v13; // bl
  _QWORD *v14; // rax
  bool v15; // di
  WCHAR *v16; // rcx
  bool v17; // zf
  char v18; // bl
  _QWORD *v19; // rax
  char v20; // bl
  char v21; // bl
  char v22; // bl
  char v23; // bl
  char v24; // bl
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  int ReturnLength; // [rsp+20h] [rbp-69h]
  char *v29; // [rsp+28h] [rbp-61h]
  DWORD v30; // [rsp+30h] [rbp-59h] BYREF
  unsigned int TokenInformation; // [rsp+34h] [rbp-55h] BYREF
  int v32; // [rsp+38h] [rbp-51h] BYREF
  WCHAR v33[16]; // [rsp+40h] [rbp-49h] BYREF
  WCHAR StringSecurityDescriptor[16]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE Src[32]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v30 = 0;
  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl);
  if ( (_BYTE)result )
  {
    result = (unsigned int)(a3 - 2);
    if ( (unsigned int)result <= 1 )
    {
      TokenInformation = 0;
      v30 = 0;
      v32 = 0;
      if ( !GetTokenInformation(a1, TokenSessionId, &TokenInformation, 4u, &v30) )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x26, v9, v10);
      v29 = (char *)&v30;
      ReturnLength = 4;
      result = WinStationQueryInformationW(0, TokenInformation, 39, &v32);
      if ( !(_BYTE)result )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x30,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\access.cpp",
          v11);
      if ( v32 == 9 )
        goto LABEL_55;
    }
  }
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        if ( !a2 || !wcsnlen(a2, 1u) )
        {
          v25 = wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC7,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\access.cpp",
            (const char *)v25,
            ReturnLength);
        }
        std::wstring::wstring(v33, L"O:SYG:SYD:(A;;0x1;;;SY)");
        v22 = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
        result = std::wstring::~wstring(v33);
        if ( v22 )
          goto LABEL_56;
        v19 = (_QWORD *)Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(Src, a2);
        if ( v19[3] > 7u )
          v19 = (_QWORD *)*v19;
        break;
      case 2:
        if ( !a2 || !wcsnlen(a2, 1u) )
        {
          std::wstring::wstring(v33, L"O:SYG:SYD:(A;;0x1;;;SY)");
          v20 = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
          result = std::wstring::~wstring(v33);
          if ( v20 )
            goto LABEL_56;
          std::wstring::wstring(StringSecurityDescriptor, L"O:SYG:SYD:(A;;0x1;;;BA)");
          v21 = 1;
          v30 = 1;
          result = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(
                     a1,
                     StringSecurityDescriptor);
          v15 = 0;
          if ( (_BYTE)result )
          {
            std::wstring::wstring(v33, L"O:SYG:SYD:(A;;0x1;;;IU)");
            v21 = 3;
            v30 = 3;
            result = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
            if ( (_BYTE)result )
              v15 = 1;
          }
          if ( (v21 & 2) != 0 )
          {
            v21 &= ~2u;
            result = std::wstring::~wstring(v33);
          }
          if ( (v21 & 1) == 0 )
            goto LABEL_26;
          v16 = StringSecurityDescriptor;
          goto LABEL_25;
        }
        std::wstring::wstring(v33, L"O:SYG:SYD:(A;;0x1;;;SY)");
        v18 = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
        result = std::wstring::~wstring(v33);
        if ( v18 )
          goto LABEL_56;
        v19 = (_QWORD *)Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(Src, a2);
        if ( v19[3] > 7u )
          v19 = (_QWORD *)*v19;
        break;
      case 3:
        if ( !a2 || !wcsnlen(a2, 1u) )
        {
          v27 = wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8B,
            (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\access.cpp",
            (const char *)v27,
            ReturnLength);
        }
        std::wstring::wstring(StringSecurityDescriptor, L"O:SYG:SYD:(A;;0x1;;;SY)");
        v12 = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(
                a1,
                StringSecurityDescriptor);
        result = std::wstring::~wstring(StringSecurityDescriptor);
        if ( v12 )
          goto LABEL_56;
        std::wstring::wstring(
          v33,
          L"O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID Contains \"windows.immersivecontrolpanel_cw5n1h2txyewy\"))");
        v13 = 32;
        v30 = 32;
        result = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
        if ( !(_BYTE)result )
          goto LABEL_18;
        v14 = (_QWORD *)Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(Src, a2);
        v30 = 96;
        if ( v14[3] > 7u )
          v14 = (_QWORD *)*v14;
        std::wstring::wstring(StringSecurityDescriptor, v14);
        v13 = -32;
        v30 = 224;
        result = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(
                   a1,
                   StringSecurityDescriptor);
        if ( (_BYTE)result )
          v15 = 1;
        else
LABEL_18:
          v15 = 0;
        if ( v13 < 0 )
        {
          v13 &= ~0x80u;
          result = std::wstring::~wstring(StringSecurityDescriptor);
        }
        if ( (v13 & 0x40) != 0 )
        {
          v13 &= ~0x40u;
          result = std::wstring::~wstring(Src);
        }
        if ( (v13 & 0x20) == 0 )
          goto LABEL_26;
        v16 = v33;
LABEL_25:
        result = std::wstring::~wstring(v16);
LABEL_26:
        v17 = !v15;
        goto LABEL_54;
      default:
        v26 = wil::verify_hresult<long>(2147549183LL);
        LODWORD(v29) = a3;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xDF,
          (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\access.cpp",
          (const char *)v26,
          (int)"CAMStorageAccessRequestType out of expected range, value %d",
          v29);
    }
  }
  else
  {
    if ( !a2 )
      goto LABEL_56;
    result = wcsnlen(a2, 1u);
    if ( !result )
      goto LABEL_56;
    std::wstring::wstring(v33, L"O:SYG:SYD:(A;;0x1;;;SY)");
    v23 = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
    result = std::wstring::~wstring(v33);
    if ( v23 )
      goto LABEL_56;
    v19 = (_QWORD *)Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(Src, a2);
    if ( v19[3] > 7u )
      v19 = (_QWORD *)*v19;
  }
  std::wstring::wstring(v33, v19);
  v24 = Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(a1, v33);
  std::wstring::~wstring(v33);
  result = std::wstring::~wstring(Src);
  v17 = v24 == 0;
LABEL_54:
  if ( v17 )
  {
LABEL_55:
    *a4 = 0;
    return result;
  }
LABEL_56:
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x1800f512c  push    rbp
0x1800f512e  push    rbx
0x1800f512f  push    rsi
0x1800f5130  push    rdi
0x1800f5131  push    r12
0x1800f5133  push    r14
0x1800f5135  lea     rbp, [rsp-2Fh]
0x1800f513a  sub     rsp, 0B8h
0x1800f5141  mov     rax, cs:__security_cookie
0x1800f5148  xor     rax, rsp
0x1800f514b  mov     [rbp+57h+var_40], rax
0x1800f514f  mov     r14, r9
0x1800f5152  mov     ebx, r8d
0x1800f5155  mov     rdi, rdx
0x1800f5158  mov     rsi, rcx
0x1800f515b  mov     [rbp+57h+var_B0], 0
0x1800f5162  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x1800f5169  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x1800f516e  mov     r12d, 1
0x1800f5174  test    al, al
0x1800f5176  jz      loc_1800F51FC
0x1800f517c  lea     eax, [rbx-2]
0x1800f517f  cmp     eax, r12d
0x1800f5182  ja      short loc_1800F51FC
0x1800f5184  mov     [rbp+57h+TokenInformation], 0
0x1800f518b  mov     [rbp+57h+var_B0], 0
0x1800f5192  mov     [rbp+57h+var_A8], 0
0x1800f5199  lea     rax, [rbp+57h+var_B0]
0x1800f519d  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800f51a2  lea     r9d, [r12+3]; TokenInformationLength
0x1800f51a7  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800f51ab  lea     edx, [r12+0Bh]; TokenInformationClass
0x1800f51b0  mov     rcx, rsi; TokenHandle
0x1800f51b3  call    cs:__imp_GetTokenInformation
0x1800f51b9  mov     rcx, [rbp+5Fh]; this
0x1800f51bd  test    eax, eax
0x1800f51bf  jz      loc_1800F55BA
0x1800f51c5  lea     rax, [rbp+57h+var_B0]
0x1800f51c9  mov     [rsp+0E0h+var_B8], rax
0x1800f51ce  mov     dword ptr [rsp+0E0h+ReturnLength], 4; int
0x1800f51d6  lea     r9, [rbp+57h+var_A8]
0x1800f51da  lea     r8d, [r12+26h]
0x1800f51df  mov     edx, [rbp+57h+TokenInformation]
0x1800f51e2  xor     ecx, ecx
0x1800f51e4  call    cs:__imp_WinStationQueryInformationW
0x1800f51ea  test    al, al
0x1800f51ec  jz      loc_1800F55C5
0x1800f51f2  cmp     [rbp+57h+var_A8], 9
0x1800f51f6  jz      loc_1800F5572
0x1800f51fc  mov     ecx, ebx
0x1800f51fe  test    ebx, ebx
0x1800f5200  jz      loc_1800F54E3
0x1800f5206  sub     ecx, r12d
0x1800f5209  jz      loc_1800F5454
0x1800f520f  sub     ecx, r12d
0x1800f5212  jz      loc_1800F531D
0x1800f5218  cmp     ecx, r12d
0x1800f521b  jnz     loc_1800F55DB
0x1800f5221  test    rdi, rdi
0x1800f5224  jz      loc_1800F560E
0x1800f522a  mov     rdx, r12; MaxCount
0x1800f522d  mov     rcx, rdi; Source
0x1800f5230  call    cs:__imp_wcsnlen
0x1800f5236  test    rax, rax
0x1800f5239  jz      loc_1800F560E
0x1800f523f  lea     rdx, aOSygSydA0x1Sy; "O:SYG:SYD:(A;;0x1;;;SY)"
0x1800f5246  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x1800f524a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f524f  nop
0x1800f5250  lea     rdx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800f5254  mov     rcx, rsi; ClientToken
0x1800f5257  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f525c  mov     bl, al
0x1800f525e  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x1800f5262  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5267  test    bl, bl
0x1800f5269  jnz     loc_1800F5578
0x1800f526f  lea     rdx, aOSygSydXa0x1Iu; "O:SYG:SYD:(XA;;0x1;;;IU;(WIN://SYSAPPID"...
0x1800f5276  lea     rcx, [rbp+57h+var_A0]
0x1800f527a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f527f  nop
0x1800f5280  mov     ebx, 20h ; ' '
0x1800f5285  mov     [rbp+57h+var_B0], ebx
0x1800f5288  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f528c  mov     rcx, rsi; ClientToken
0x1800f528f  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f5294  test    al, al
0x1800f5296  jz      short loc_1800F52E0
0x1800f5298  mov     rdx, rdi; Source
0x1800f529b  lea     rcx, [rbp+57h+Src]; Src
0x1800f529f  call    ?BuildSDStringForUser@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(ushort const *)
0x1800f52a4  nop
0x1800f52a5  mov     [rbp+57h+var_B0], 60h ; '`'
0x1800f52ac  cmp     qword ptr [rax+18h], 7
0x1800f52b1  jbe     short loc_1800F52B6
0x1800f52b3  mov     rax, [rax]
0x1800f52b6  mov     rdx, rax
0x1800f52b9  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x1800f52bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f52c2  nop
0x1800f52c3  mov     ebx, 0E0h
0x1800f52c8  mov     [rbp+57h+var_B0], ebx
0x1800f52cb  lea     rdx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800f52cf  mov     rcx, rsi; ClientToken
0x1800f52d2  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f52d7  test    al, al
0x1800f52d9  jz      short loc_1800F52E0
0x1800f52db  mov     dil, r12b
0x1800f52de  jmp     short loc_1800F52E3
0x1800f52e0  xor     dil, dil
0x1800f52e3  test    bl, bl
0x1800f52e5  jns     short loc_1800F52F5
0x1800f52e7  btr     ebx, 7
0x1800f52eb  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x1800f52ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f52f4  nop
0x1800f52f5  test    bl, 40h
0x1800f52f8  jz      short loc_1800F5307
0x1800f52fa  and     ebx, 0FFFFFFBFh
0x1800f52fd  lea     rcx, [rbp+57h+Src]
0x1800f5301  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5306  nop
0x1800f5307  test    bl, 20h
0x1800f530a  jz      short loc_1800F5315
0x1800f530c  lea     rcx, [rbp+57h+var_A0]
0x1800f5310  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5315  test    dil, dil
0x1800f5318  jmp     loc_1800F5570
0x1800f531d  test    rdi, rdi
0x1800f5320  jz      loc_1800F53A8
0x1800f5326  mov     rdx, r12; MaxCount
0x1800f5329  mov     rcx, rdi; Source
0x1800f532c  call    cs:__imp_wcsnlen
0x1800f5332  test    rax, rax
0x1800f5335  jz      short loc_1800F53A8
0x1800f5337  lea     rdx, aOSygSydA0x1Sy; "O:SYG:SYD:(A;;0x1;;;SY)"
0x1800f533e  lea     rcx, [rbp+57h+var_A0]
0x1800f5342  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f5347  nop
0x1800f5348  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f534c  mov     rcx, rsi; ClientToken
0x1800f534f  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f5354  mov     bl, al
0x1800f5356  lea     rcx, [rbp+57h+var_A0]
0x1800f535a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f535f  test    bl, bl
0x1800f5361  jnz     loc_1800F5578
0x1800f5367  mov     rdx, rdi; Source
0x1800f536a  lea     rcx, [rbp+57h+Src]; Src
0x1800f536e  call    ?BuildSDStringForUser@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(ushort const *)
0x1800f5373  nop
0x1800f5374  cmp     qword ptr [rax+18h], 7
0x1800f5379  jbe     short loc_1800F537E
0x1800f537b  mov     rax, [rax]
0x1800f537e  mov     rdx, rax
0x1800f5381  lea     rcx, [rbp+57h+var_A0]
0x1800f5385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f538a  nop
0x1800f538b  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f538f  mov     rcx, rsi; ClientToken
0x1800f5392  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f5397  mov     bl, al
0x1800f5399  lea     rcx, [rbp+57h+var_A0]
0x1800f539d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f53a2  nop
0x1800f53a3  jmp     loc_1800F5565
0x1800f53a8  lea     rdx, aOSygSydA0x1Sy; "O:SYG:SYD:(A;;0x1;;;SY)"
0x1800f53af  lea     rcx, [rbp+57h+var_A0]
0x1800f53b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f53b8  nop
0x1800f53b9  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f53bd  mov     rcx, rsi; ClientToken
0x1800f53c0  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f53c5  mov     bl, al
0x1800f53c7  lea     rcx, [rbp+57h+var_A0]
0x1800f53cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f53d0  test    bl, bl
0x1800f53d2  jnz     loc_1800F5578
0x1800f53d8  lea     rdx, aOSygSydA0x1Ba; "O:SYG:SYD:(A;;0x1;;;BA)"
0x1800f53df  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x1800f53e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f53e8  nop
0x1800f53e9  mov     ebx, r12d
0x1800f53ec  mov     [rbp+57h+var_B0], ebx
0x1800f53ef  lea     rdx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800f53f3  mov     rcx, rsi; ClientToken
0x1800f53f6  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f53fb  test    al, al
0x1800f53fd  jz      short loc_1800F542D
0x1800f53ff  lea     rdx, aOSygSydA0x1Iu; "O:SYG:SYD:(A;;0x1;;;IU)"
0x1800f5406  lea     rcx, [rbp+57h+var_A0]
0x1800f540a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f540f  nop
0x1800f5410  mov     ebx, 3
0x1800f5415  mov     [rbp+57h+var_B0], ebx
0x1800f5418  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f541c  mov     rcx, rsi; ClientToken
0x1800f541f  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f5424  test    al, al
0x1800f5426  jz      short loc_1800F542D
0x1800f5428  mov     dil, r12b
0x1800f542b  jmp     short loc_1800F5430
0x1800f542d  xor     dil, dil
0x1800f5430  test    bl, 2
0x1800f5433  jz      short loc_1800F5442
0x1800f5435  and     ebx, 0FFFFFFFDh
0x1800f5438  lea     rcx, [rbp+57h+var_A0]
0x1800f543c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5441  nop
0x1800f5442  test    r12b, bl
0x1800f5445  jz      loc_1800F5315
0x1800f544b  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x1800f544f  jmp     loc_1800F5310
0x1800f5454  test    rdi, rdi
0x1800f5457  jz      loc_1800F5597
0x1800f545d  mov     rdx, r12; MaxCount
0x1800f5460  mov     rcx, rdi; Source
0x1800f5463  call    cs:__imp_wcsnlen
0x1800f5469  test    rax, rax
0x1800f546c  jz      loc_1800F5597
0x1800f5472  lea     rdx, aOSygSydA0x1Sy; "O:SYG:SYD:(A;;0x1;;;SY)"
0x1800f5479  lea     rcx, [rbp+57h+var_A0]
0x1800f547d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f5482  nop
0x1800f5483  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f5487  mov     rcx, rsi; ClientToken
0x1800f548a  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f548f  mov     bl, al
0x1800f5491  lea     rcx, [rbp+57h+var_A0]
0x1800f5495  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f549a  test    bl, bl
0x1800f549c  jnz     loc_1800F5578
0x1800f54a2  mov     rdx, rdi; Source
0x1800f54a5  lea     rcx, [rbp+57h+Src]; Src
0x1800f54a9  call    ?BuildSDStringForUser@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(ushort const *)
0x1800f54ae  nop
0x1800f54af  cmp     qword ptr [rax+18h], 7
0x1800f54b4  jbe     short loc_1800F54B9
0x1800f54b6  mov     rax, [rax]
0x1800f54b9  mov     rdx, rax
0x1800f54bc  lea     rcx, [rbp+57h+var_A0]
0x1800f54c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f54c5  nop
0x1800f54c6  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f54ca  mov     rcx, rsi; ClientToken
0x1800f54cd  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f54d2  mov     bl, al
0x1800f54d4  lea     rcx, [rbp+57h+var_A0]
0x1800f54d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f54dd  nop
0x1800f54de  jmp     loc_1800F5565
0x1800f54e3  test    rdi, rdi
0x1800f54e6  jz      loc_1800F5578
0x1800f54ec  mov     rdx, r12; MaxCount
0x1800f54ef  mov     rcx, rdi; Source
0x1800f54f2  call    cs:__imp_wcsnlen
0x1800f54f8  test    rax, rax
0x1800f54fb  jz      short loc_1800F5578
0x1800f54fd  lea     rdx, aOSygSydA0x1Sy; "O:SYG:SYD:(A;;0x1;;;SY)"
0x1800f5504  lea     rcx, [rbp+57h+var_A0]
0x1800f5508  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f550d  nop
0x1800f550e  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f5512  mov     rcx, rsi; ClientToken
0x1800f5515  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f551a  mov     bl, al
0x1800f551c  lea     rcx, [rbp+57h+var_A0]
0x1800f5520  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5525  test    bl, bl
0x1800f5527  jnz     short loc_1800F5578
0x1800f5529  mov     rdx, rdi; Source
0x1800f552c  lea     rcx, [rbp+57h+Src]; Src
0x1800f5530  call    ?BuildSDStringForUser@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::BuildSDStringForUser(ushort const *)
0x1800f5535  nop
0x1800f5536  cmp     qword ptr [rax+18h], 7
0x1800f553b  jbe     short loc_1800F5540
0x1800f553d  mov     rax, [rax]
0x1800f5540  mov     rdx, rax
0x1800f5543  lea     rcx, [rbp+57h+var_A0]
0x1800f5547  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f554c  nop
0x1800f554d  lea     rdx, [rbp+57h+var_A0]; StringSecurityDescriptor
0x1800f5551  mov     rcx, rsi; ClientToken
0x1800f5554  call    ?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::wstring const &)
0x1800f5559  mov     bl, al
0x1800f555b  lea     rcx, [rbp+57h+var_A0]
0x1800f555f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f5564  nop
0x1800f5565  lea     rcx, [rbp+57h+Src]
0x1800f5569  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f556e  test    bl, bl
0x1800f5570  jnz     short loc_1800F5578
0x1800f5572  mov     byte ptr [r14], 0
0x1800f5576  jmp     short loc_1800F557B
0x1800f5578  mov     [r14], r12b
0x1800f557b  mov     rcx, [rbp+57h+var_40]
0x1800f557f  xor     rcx, rsp; StackCookie
0x1800f5582  call    __security_check_cookie
0x1800f5587  add     rsp, 0B8h
0x1800f558e  pop     r14
  ... truncated ...
```
