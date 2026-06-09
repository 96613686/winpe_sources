# CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage(_GUID &,std::list<_WWAN_DATA_ROAM_CONTROL_OBJECT,std::allocator<_WWAN_DATA_ROAM_CONTROL_OBJECT>> &)

- ea: `0x180030658`
- end: `0x1800308e1`
- name: `?_SetRoamingPoliciesToPersistedStorage@CWwanDataExecutor@@CAXAEAU_GUID@@AEAV?$list@U_WWAN_DATA_ROAM_CONTROL_OBJECT@@V?$allocator@U_WWAN_DATA_ROAM_CONTROL_OBJECT@@@std@@@std@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e34c`

## callees

- `0x1800085d0`
- `0x1800094d0`
- `0x1800094f4`
- `0x180011650`
- `0x180012300`
- `0x1800123cc`
- `0x180013288`
- `0x180013588`
- `0x18001375c`
- `0x180014154`
- `0x180014f1c`
- `0x18001a63c`
- `0x180030658`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030699`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030699`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030761`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030761`
- `MobileNetworking!PersistentRegPathSetDWORD` at `0x18003085a`
- `MobileNetworking!PersistentRegPathSetDWORD` at `0x18003085a`

## string_xrefs

- `0x18003070b`: `failed to GetPersistentRegPathWstring with error [%u] Policy path = [%s]`
- `0x180030787`: `deleting registry key with error [%u] for roaming policy Policy path = [%s]`
- `0x180030798`: `deleted registry key for roaming policy Policy path = [%s]`
- `0x180030885`: `writing roaming policy to registry with error (%u). Policy path = [%s], Position = %d`
- `0x1800308a1`: `wrote roaming policy to registry. Policy path = [%s], Position = %d, roamControlState = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage(GUID *rguid, __int64 ***a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rax
  int v6; // r9d
  __int64 v8; // rax
  int v9; // r9d
  unsigned int v10; // esi
  __int64 **v11; // rdi
  __int64 *i; // rbx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edx
  __int64 v17; // r9
  __int64 v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+28h] [rbp-D8h]
  struct _GUID Buf1; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C0h]
  _BYTE v22[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[40]; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[48]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(sz, 0, 0x5Eu);
  StringFromGUID2(rguid, sz, 47);
  std::wstring::wstring(v23, L"RoamingPolicyForPhone");
  std::wstring::append(v23, L"\\");
  std::wstring::append(v23, sz);
  std::wstring::wstring(v22);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  GetPersistentRegPathWstring(0, v4, v22);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  if ( !v6 )
  {
    RegDeleteKeyExW(HKEY_LOCAL_MACHINE, v5, 0x300u, 0);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    if ( v9 )
    {
      HIDWORD(v18) = HIDWORD(v8);
      WwanLog::Error(
        "CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage",
        0,
        L"deleting registry key with error [%u] for roaming policy Policy path = [%s]");
    }
    else
    {
      WwanLog::Info(
        "CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage",
        0,
        L"deleted registry key for roaming policy Policy path = [%s]",
        v8);
    }
    v10 = 1;
    v11 = *a2;
    for ( i = *v11; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)v11 )
        goto LABEL_3;
      Buf1 = (struct _GUID)*((_OWORD *)i + 1);
      v21 = *((_DWORD *)i + 8);
      std::wstring::wstring(v24);
      if ( !memcmp_0(&Buf1, &WWAN_PROFILE_SET_GUID_INTERNET_AO, 0x10u) )
      {
        v13 = L"InternetAlwaysOn";
      }
      else
      {
        if ( memcmp_0(&Buf1, &WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES, 0x10u) )
        {
          v17 = v10++;
          WwanLog::Info(
            "CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage",
            &Buf1,
            L"ignored profileSetGuid Position %d",
            v17);
          goto LABEL_17;
        }
        v13 = L"AllProfiles";
      }
      std::wstring::assign(v24, v13);
      ++v10;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
      PersistentRegPathSetDWORD(0, v14);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      if ( v16 )
      {
        LODWORD(v19) = v10;
        WwanLog::Error(
          "CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage",
          0,
          L"writing roaming policy to registry with error (%u). Policy path = [%s], Position = %d",
          v16,
          v15,
          v19);
      }
      else
      {
        LODWORD(v19) = v21;
        LODWORD(v18) = v10;
        WwanLog::Info(
          "CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage",
          0,
          L"wrote roaming policy to registry. Policy path = [%s], Position = %d, roamControlState = 0x%x",
          v15,
          v18,
          v19);
      }
LABEL_17:
      std::wstring::_Tidy_deallocate(v24);
    }
  }
  WwanLog::Error(
    "CWwanDataExecutor::_SetRoamingPoliciesToPersistedStorage",
    0,
    L"failed to GetPersistentRegPathWstring with error [%u] Policy path = [%s]");
LABEL_3:
  std::wstring::_Tidy_deallocate(v22);
  return std::wstring::_Tidy_deallocate(v23);
}

```

## disassembly

```asm
0x180030658  push    rbp
0x18003065a  push    rbx
0x18003065b  push    rsi
0x18003065c  push    rdi
0x18003065d  lea     rbp, [rsp-28h]
0x180030662  sub     rsp, 128h
0x180030669  mov     rax, cs:__security_cookie
0x180030670  xor     rax, rsp
0x180030673  mov     [rbp+40h+var_30], rax
0x180030677  mov     rdi, rdx
0x18003067a  mov     rbx, rcx
0x18003067d  xor     edx, edx; Val
0x18003067f  lea     r8d, [rdx+5Eh]; Size
0x180030683  lea     rcx, [rbp+40h+sz]; void *
0x180030687  call    memset_0
0x18003068c  mov     r8d, 2Fh ; '/'; cchMax
0x180030692  lea     rdx, [rbp+40h+sz]; lpsz
0x180030696  mov     rcx, rbx; rguid
0x180030699  call    cs:__imp_StringFromGUID2
0x18003069f  lea     rdx, ?sc_wszRoamingPolicyRegSubPath@CWwanDataExecutor@@0QBGB; "RoamingPolicyForPhone"
0x1800306a6  lea     rcx, [rsp+140h+var_D8]
0x1800306ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800306b0  nop
0x1800306b1  lea     rdx, SubBlock; "\\"
0x1800306b8  lea     rcx, [rsp+140h+var_D8]
0x1800306bd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800306c2  lea     rdx, [rbp+40h+sz]
0x1800306c6  lea     rcx, [rsp+140h+var_D8]
0x1800306cb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800306d0  lea     rcx, [rsp+140h+var_F8]
0x1800306d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800306da  nop
0x1800306db  lea     rcx, [rsp+140h+var_D8]
0x1800306e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800306e5  mov     rdx, rax
0x1800306e8  lea     r8, [rsp+140h+var_F8]
0x1800306ed  xor     ecx, ecx
0x1800306ef  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x1800306f4  mov     r9d, eax
0x1800306f7  lea     rcx, [rsp+140h+var_F8]
0x1800306fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030701  test    r9d, r9d
0x180030704  jz      short loc_18003074E
0x180030706  mov     [rsp+140h+var_120], rax
0x18003070b  lea     r8, aFailedToGetper_0; "failed to GetPersistentRegPathWstring w"...
0x180030712  xor     edx, edx; struct _GUID *
0x180030714  lea     rcx, aCwwandataexecu_24; "CWwanDataExecutor::_SetRoamingPoliciesT"...
0x18003071b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180030720  nop
0x180030721  lea     rcx, [rsp+140h+var_F8]
0x180030726  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003072b  nop
0x18003072c  lea     rcx, [rsp+140h+var_D8]
0x180030731  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030736  mov     rcx, [rbp+40h+var_30]
0x18003073a  xor     rcx, rsp; StackCookie
0x18003073d  call    __security_check_cookie
0x180030742  add     rsp, 128h
0x180030749  pop     rdi
0x18003074a  pop     rsi
0x18003074b  pop     rbx
0x18003074c  pop     rbp
0x18003074d  retn
0x18003074e  xor     r9d, r9d; Reserved
0x180030751  mov     r8d, 300h; samDesired
0x180030757  mov     rdx, rax; lpSubKey
0x18003075a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030761  call    cs:__imp_RegDeleteKeyExW
0x180030767  mov     r9d, eax
0x18003076a  lea     rcx, [rsp+140h+var_F8]
0x18003076f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030774  xor     edx, edx; struct _GUID *
0x180030776  lea     rcx, aCwwandataexecu_24; "CWwanDataExecutor::_SetRoamingPoliciesT"...
0x18003077d  test    r9d, r9d
0x180030780  jz      short loc_180030795
0x180030782  mov     [rsp+140h+var_120], rax
0x180030787  lea     r8, aDeletingRegist; "deleting registry key with error [%u] f"...
0x18003078e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180030793  jmp     short loc_1800307A4
0x180030795  mov     r9, rax
0x180030798  lea     r8, aDeletedRegistr; "deleted registry key for roaming policy"...
0x18003079f  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800307a4  mov     esi, 1
0x1800307a9  mov     rdi, [rdi]
0x1800307ac  mov     rbx, [rdi]
0x1800307af  cmp     rbx, rdi
0x1800307b2  jz      loc_180030721
0x1800307b8  movups  xmm0, xmmword ptr [rbx+10h]
0x1800307bc  movups  [rsp+140h+Buf1], xmm0
0x1800307c1  mov     eax, [rbx+20h]
0x1800307c4  mov     [rsp+140h+var_100], eax
0x1800307c8  lea     rcx, [rbp+40h+var_B8]
0x1800307cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800307d1  nop
0x1800307d2  mov     r8d, 10h; Size
0x1800307d8  lea     rdx, WWAN_PROFILE_SET_GUID_INTERNET_AO; Buf2
0x1800307df  lea     rcx, [rsp+140h+Buf1]; Buf1
0x1800307e4  call    memcmp_0
0x1800307e9  test    eax, eax
0x1800307eb  jnz     short loc_1800307F6
0x1800307ed  lea     rdx, ?sc_wszProfileSetPolicyAlwaysOnInternetValue@CWwanDataExecutor@@0QBGB; "InternetAlwaysOn"
0x1800307f4  jmp     short loc_18003081C
0x1800307f6  mov     r8d, 10h; Size
0x1800307fc  lea     rdx, WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES; Buf2
0x180030803  lea     rcx, [rsp+140h+Buf1]; Buf1
0x180030808  call    memcmp_0
0x18003080d  test    eax, eax
0x18003080f  jnz     loc_1800308B1
0x180030815  lea     rdx, ?sc_wszProfileSetPolicyAllProfilesValue@CWwanDataExecutor@@0QBGB; "AllProfiles"
0x18003081c  lea     rcx, [rbp+40h+var_B8]
0x180030820  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180030825  mov     r9d, esi
0x180030828  inc     esi
0x18003082a  shl     r9d, 10h
0x18003082e  mov     eax, [rsp+140h+var_100]
0x180030832  and     eax, 7FFFh
0x180030837  or      r9d, eax
0x18003083a  bts     r9d, 0Fh
0x18003083f  lea     rcx, [rbp+40h+var_B8]
0x180030843  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030848  mov     r8, rax
0x18003084b  lea     rcx, [rsp+140h+var_D8]
0x180030850  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030855  mov     rdx, rax
0x180030858  xor     ecx, ecx
0x18003085a  call    cs:__imp_PersistentRegPathSetDWORD
0x180030860  mov     edx, eax
0x180030862  lea     rcx, [rbp+40h+var_B8]
0x180030866  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003086b  mov     r9, rax
0x18003086e  lea     rcx, aCwwandataexecu_24; "CWwanDataExecutor::_SetRoamingPoliciesT"...
0x180030875  test    edx, edx
0x180030877  jz      short loc_180030895
0x180030879  mov     dword ptr [rsp+140h+var_118], esi
0x18003087d  mov     [rsp+140h+var_120], rax
0x180030882  mov     r9d, edx
0x180030885  lea     r8, aWritingRoaming; "writing roaming policy to registry with"...
0x18003088c  xor     edx, edx; struct _GUID *
0x18003088e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180030893  jmp     short loc_1800308CF
0x180030895  mov     eax, [rsp+140h+var_100]
0x180030899  mov     dword ptr [rsp+140h+var_118], eax
0x18003089d  mov     dword ptr [rsp+140h+var_120], esi
0x1800308a1  lea     r8, aWroteRoamingPo; "wrote roaming policy to registry. Polic"...
0x1800308a8  xor     edx, edx; struct _GUID *
0x1800308aa  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800308af  jmp     short loc_1800308CF
0x1800308b1  mov     r9d, esi
0x1800308b4  inc     esi
0x1800308b6  lea     r8, aIgnoredProfile; "ignored profileSetGuid Position %d"
0x1800308bd  lea     rdx, [rsp+140h+Buf1]; struct _GUID *
0x1800308c2  lea     rcx, aCwwandataexecu_24; "CWwanDataExecutor::_SetRoamingPoliciesT"...
0x1800308c9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800308ce  nop
0x1800308cf  lea     rcx, [rbp+40h+var_B8]
0x1800308d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800308d8  mov     rbx, [rbx]
0x1800308db  jmp     loc_1800307AF
```
