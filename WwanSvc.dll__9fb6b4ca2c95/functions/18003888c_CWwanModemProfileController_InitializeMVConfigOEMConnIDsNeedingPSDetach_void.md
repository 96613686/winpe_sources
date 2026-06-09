# CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach(void)

- ea: `0x18003888c`
- end: `0x180038ad5`
- name: `?_InitializeMVConfigOEMConnIDsNeedingPSDetach@CWwanModemProfileController@@CAXXZ`
- size: `585`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800325b8`

## callees

- `0x1800085d0`
- `0x180008a7c`
- `0x180008b24`
- `0x180011650`
- `0x180012300`
- `0x1800123cc`
- `0x180013288`
- `0x180013588`
- `0x180014f1c`
- `0x1800216bc`
- `0x18003888c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038949`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800389ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180038949`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800389ab`
- `RPCRT4!UuidFromStringW` at `0x1800389e2`
- `RPCRT4!UuidFromStringW` at `0x1800389e2`

## string_xrefs

- `0x1800388ef`: `failed to GetPersistentRegPathWstring error %u`
- `0x1800388f8`: `CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach`
- `0x180038a07`: `CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach`
- `0x180038a20`: `CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach`
- `0x180038a3e`: `CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach`
- `0x180038a7f`: `CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach`
- `0x180038aa7`: `CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach`
- `0x180038a35`: `failed to read reg value %s after initially succeeding at getting size. Code %u`
- `0x180038a9e`: ` reg value %s under path %s does not exist`
- `0x180038a76`: `reg value %s under path %s can't be read w error %u`
- `0x1800388d7`: `IMSISpecific\Default\CellData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach(void)
{
  unsigned int PersistentRegPathWstring; // eax
  const WCHAR *v1; // rax
  LSTATUS ValueW; // edx
  void *v3; // rsi
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  unsigned int v6; // edi
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-29h]
  PVOID pvData; // [rsp+28h] [rbp-21h]
  DWORD pcbData; // [rsp+40h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp+Fh] BYREF

  if ( !CWwanModemProfileController::m_s_fHaveMVConfigOEMConnIDsNeedingPSDetach )
  {
    CWwanModemProfileController::m_s_fHaveMVConfigOEMConnIDsNeedingPSDetach = 1;
    std::wstring::wstring(v15);
    pcbData = 0;
    PersistentRegPathWstring = GetPersistentRegPathWstring(1, L"IMSISpecific\\Default\\CellData", v15);
    if ( PersistentRegPathWstring )
    {
      WwanLog::Error(
        "CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach",
        0,
        L"failed to GetPersistentRegPathWstring error %u",
        PersistentRegPathWstring);
    }
    else
    {
      v1 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v1, L"LTEAttachGUIDs", 0x20u, 0, 0, &pcbData);
      if ( ValueW )
      {
        if ( ValueW == 1168 || ValueW == 2 )
        {
          v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
          WwanLog::Info(
            "CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach",
            0,
            L" reg value %s under path %s does not exist",
            L"LTEAttachGUIDs",
            v10);
        }
        else
        {
          v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
          LODWORD(pvData) = v9;
          WwanLog::Error(
            "CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach",
            0,
            L"reg value %s under path %s can't be read w error %u",
            L"LTEAttachGUIDs",
            v8,
            pvData);
        }
      }
      else
      {
        v3 = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
        v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
        v5 = RegGetValueW(HKEY_LOCAL_MACHINE, v4, L"LTEAttachGUIDs", 0x20u, 0, v3, &pcbData);
        if ( v5 )
        {
          LODWORD(pdwType) = v5;
          WwanLog::Error(
            "CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach",
            0,
            L"failed to read reg value %s after initially succeeding at getting size. Code %u",
            L"LTEAttachGUIDs",
            pdwType);
        }
        else
        {
          v6 = 0;
          v7 = (unsigned int)(((3134165325u * (unsigned __int64)(pcbData >> 1)) >> 32)
                            + ((unsigned int)((pcbData >> 1) - ((3134165325u * (unsigned __int64)(pcbData >> 1)) >> 32)) >> 1)) >> 5;
          while ( v6 < v7 )
          {
            Uuid = 0;
            if ( UuidFromStringW((RPC_WSTR)v3 + 37 * v6, &Uuid) )
            {
              WwanLog::Error(
                "CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach",
                0,
                L"failed atUuidFromString");
              break;
            }
            std::vector<_GUID>::_Emplace_one_at_back<_GUID const &>(
              &CWwanModemProfileController::m_s_OEMConnIDsNeedingPSDetach,
              &Uuid);
            WwanLog::Info(
              "CWwanModemProfileController::_InitializeMVConfigOEMConnIDsNeedingPSDetach",
              &Uuid,
              L" Added one OEMConnID needing PS detach to take effect");
            ++v6;
          }
        }
        operator delete(v3);
      }
    }
    std::wstring::_Tidy_deallocate(v15);
  }
}

```

## disassembly

```asm
0x18003888c  push    rbp
0x18003888e  push    rbx
0x18003888f  push    rsi
0x180038890  push    rdi
0x180038891  lea     rbp, [rsp-3Fh]
0x180038896  sub     rsp, 88h
0x18003889d  mov     rax, cs:__security_cookie
0x1800388a4  xor     rax, rsp
0x1800388a7  mov     [rbp+57h+var_28], rax
0x1800388ab  cmp     cs:?m_s_fHaveMVConfigOEMConnIDsNeedingPSDetach@CWwanModemProfileController@@0HA, 0; int CWwanModemProfileController::m_s_fHaveMVConfigOEMConnIDsNeedingPSDetach
0x1800388b2  jnz     loc_180038ABD
0x1800388b8  mov     cs:?m_s_fHaveMVConfigOEMConnIDsNeedingPSDetach@CWwanModemProfileController@@0HA, 1; int CWwanModemProfileController::m_s_fHaveMVConfigOEMConnIDsNeedingPSDetach
0x1800388c2  lea     rcx, [rbp+57h+var_48]
0x1800388c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800388cb  nop
0x1800388cc  mov     [rbp+57h+var_60], 0
0x1800388d3  lea     r8, [rbp+57h+var_48]
0x1800388d7  lea     rdx, aImsispecificDe_0; "IMSISpecific\\Default\\CellData"
0x1800388de  mov     ecx, 1
0x1800388e3  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x1800388e8  test    eax, eax
0x1800388ea  jz      short loc_180038909
0x1800388ec  mov     r9d, eax
0x1800388ef  lea     r8, aFailedToGetper; "failed to GetPersistentRegPathWstring e"...
0x1800388f6  xor     edx, edx; struct _GUID *
0x1800388f8  lea     rcx, aCwwanmodemprof_30; "CWwanModemProfileController::_Initializ"...
0x1800388ff  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180038904  jmp     loc_180038AB4
0x180038909  lea     rcx, [rbp+57h+var_48]
0x18003890d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180038912  mov     rdx, rax; lpSubKey
0x180038915  lea     rax, [rbp+57h+var_60]
0x180038919  mov     [rsp+0A0h+pcbData], rax; pcbData
0x18003891e  mov     [rsp+0A0h+pvData], 0; pvData
0x180038927  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180038930  mov     edi, 20h ; ' '
0x180038935  mov     r9d, edi; dwFlags
0x180038938  lea     rbx, Value; "LTEAttachGUIDs"
0x18003893f  mov     r8, rbx; lpValue
0x180038942  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180038949  call    cs:__imp_RegGetValueW
0x18003894f  mov     edx, eax
0x180038951  test    eax, eax
0x180038953  jnz     loc_180038A54
0x180038959  mov     ecx, [rbp+57h+var_60]
0x18003895c  shr     rcx, 1
0x18003895f  lea     eax, [rdi-1Eh]
0x180038962  mul     rcx
0x180038965  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18003896c  cmovb   rax, rdx
0x180038970  mov     rcx, rax; unsigned __int64
0x180038973  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180038978  mov     rsi, rax
0x18003897b  lea     rcx, [rbp+57h+var_48]
0x18003897f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180038984  mov     rdx, rax; lpSubKey
0x180038987  lea     rax, [rbp+57h+var_60]
0x18003898b  mov     [rsp+0A0h+pcbData], rax; pcbData
0x180038990  mov     [rsp+0A0h+pvData], rsi; pvData
0x180038995  mov     [rsp+0A0h+pdwType], 0; pdwType
0x18003899e  mov     r9d, edi; dwFlags
0x1800389a1  mov     r8, rbx; lpValue
0x1800389a4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800389ab  call    cs:__imp_RegGetValueW
0x1800389b1  test    eax, eax
0x1800389b3  jnz     short loc_180038A2E
0x1800389b5  xor     edi, edi
0x1800389b7  mov     ebx, [rbp+57h+var_60]
0x1800389ba  shr     ebx, 1
0x1800389bc  mov     eax, 0BACF914Dh
0x1800389c1  mul     ebx
0x1800389c3  sub     ebx, edx
0x1800389c5  shr     ebx, 1
0x1800389c7  add     ebx, edx
0x1800389c9  shr     ebx, 5
0x1800389cc  cmp     edi, ebx
0x1800389ce  jnb     short loc_180038A4A
0x1800389d0  xorps   xmm0, xmm0
0x1800389d3  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800389d7  imul    eax, edi, 25h ; '%'
0x1800389da  lea     rcx, [rsi+rax*2]; StringUuid
0x1800389de  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800389e2  call    cs:__imp_UuidFromStringW
0x1800389e8  test    eax, eax
0x1800389ea  jnz     short loc_180038A17
0x1800389ec  lea     rdx, [rbp+57h+Uuid]
0x1800389f0  lea     rcx, ?m_s_OEMConnIDsNeedingPSDetach@CWwanModemProfileController@@0V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@A; std::vector<_GUID> CWwanModemProfileController::m_s_OEMConnIDsNeedingPSDetach
0x1800389f7  call    ??$_Emplace_one_at_back@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAAEAU_GUID@@AEBU2@@Z; std::vector<_GUID>::_Emplace_one_at_back<_GUID const &>(_GUID const &)
0x1800389fc  lea     r8, aAddedOneOemcon; " Added one OEMConnID needing PS detach "...
0x180038a03  lea     rdx, [rbp+57h+Uuid]; struct _GUID *
0x180038a07  lea     rcx, aCwwanmodemprof_30; "CWwanModemProfileController::_Initializ"...
0x180038a0e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180038a13  inc     edi
0x180038a15  jmp     short loc_1800389CC
0x180038a17  lea     r8, aFailedAtuuidfr; "failed atUuidFromString"
0x180038a1e  xor     edx, edx; struct _GUID *
0x180038a20  lea     rcx, aCwwanmodemprof_30; "CWwanModemProfileController::_Initializ"...
0x180038a27  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180038a2c  jmp     short loc_180038A4A
0x180038a2e  mov     dword ptr [rsp+0A0h+pdwType], eax
0x180038a32  mov     r9, rbx
0x180038a35  lea     r8, aFailedToReadRe_0; "failed to read reg value %s after initi"...
0x180038a3c  xor     edx, edx; struct _GUID *
0x180038a3e  lea     rcx, aCwwanmodemprof_30; "CWwanModemProfileController::_Initializ"...
0x180038a45  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180038a4a  mov     rcx, rsi; Block
0x180038a4d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038a52  jmp     short loc_180038AB4
0x180038a54  cmp     edx, 490h
0x180038a5a  jz      short loc_180038A8D
0x180038a5c  cmp     edx, 2
0x180038a5f  jz      short loc_180038A8D
0x180038a61  lea     rcx, [rbp+57h+var_48]
0x180038a65  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180038a6a  mov     dword ptr [rsp+0A0h+pvData], edx
0x180038a6e  mov     [rsp+0A0h+pdwType], rax
0x180038a73  mov     r9, rbx
0x180038a76  lea     r8, aRegValueSUnder; "reg value %s under path %s can't be rea"...
0x180038a7d  xor     edx, edx; struct _GUID *
0x180038a7f  lea     rcx, aCwwanmodemprof_30; "CWwanModemProfileController::_Initializ"...
0x180038a86  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180038a8b  jmp     short loc_180038AB4
0x180038a8d  lea     rcx, [rbp+57h+var_48]
0x180038a91  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180038a96  mov     [rsp+0A0h+pdwType], rax
0x180038a9b  mov     r9, rbx
0x180038a9e  lea     r8, aRegValueSUnder_0; " reg value %s under path %s does not ex"...
0x180038aa5  xor     edx, edx; struct _GUID *
0x180038aa7  lea     rcx, aCwwanmodemprof_30; "CWwanModemProfileController::_Initializ"...
0x180038aae  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180038ab3  nop
0x180038ab4  lea     rcx, [rbp+57h+var_48]
0x180038ab8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038abd  mov     rcx, [rbp+57h+var_28]
0x180038ac1  xor     rcx, rsp; StackCookie
0x180038ac4  call    __security_check_cookie
0x180038ac9  add     rsp, 88h
0x180038ad0  pop     rdi
0x180038ad1  pop     rsi
0x180038ad2  pop     rbx
0x180038ad3  pop     rbp
0x180038ad4  retn
```
