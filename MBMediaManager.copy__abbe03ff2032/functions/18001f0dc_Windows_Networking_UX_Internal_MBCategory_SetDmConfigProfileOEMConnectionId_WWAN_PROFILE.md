# Windows::Networking::UX::Internal::MBCategory::_SetDmConfigProfileOEMConnectionId(WWAN_PROFILE &)

- ea: `0x18001f0dc`
- end: `0x18001f283`
- name: `?_SetDmConfigProfileOEMConnectionId@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEAUWWAN_PROFILE@@@Z`
- size: `423`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this, struct WWAN_PROFILE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180041260`

## callees

- `0x18000ad20`
- `0x18001f0dc`
- `0x18001f34c`
- `0x18001f5b8`
- `0x18001f7a4`
- `0x180026ab8`
- `0x18002cd20`
- `0x18002d796`
- `0x18002d8d4`
- `0x18003dd18`
- `0x18003e184`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001f1fe`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001f1fe`

## string_xrefs

- `0x18001f17b`: `IMSISpecific\`
- `0x18001f218`: `Windows::Networking::UX::Internal::MBCategory::_SetDmConfigProfileOEMConnectionId`
- `0x18001f241`: `Windows::Networking::UX::Internal::MBCategory::_SetDmConfigProfileOEMConnectionId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Networking::UX::Internal::MBCategory::_SetDmConfigProfileOEMConnectionId(
        Windows::Networking::UX::Internal::MBCategory *this,
        struct WWAN_PROFILE *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  const unsigned __int16 *v5; // r8
  unsigned int v6; // r9d
  const unsigned __int16 *v7; // rdx
  unsigned int *v8; // [rsp+20h] [rbp-E0h]
  DWORD v9; // [rsp+40h] [rbp-C0h] BYREF
  const char *v10; // [rsp+48h] [rbp-B8h] BYREF
  char v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+51h] [rbp-AFh]
  __int16 v13; // [rsp+55h] [rbp-ABh]
  char v14; // [rsp+57h] [rbp-A9h]
  void **pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD Src[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[32]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[48]; // [rsp+B0h] [rbp-50h] BYREF

  std::wstring::wstring(v18);
  if ( (unsigned int)GetPersistentRegPathWstring(v4, v3, (__int64)v18) )
  {
    pExceptionObject = &std::exception::`vftable';
    v16 = 0;
    v10 = "failed to get persistent root string";
    v11 = 1;
    v12 = 0;
    v13 = 0;
    v14 = 0;
    o___std_exception_copy_0(&v10, &v16);
    throw (std::exception *)&pExceptionObject;
  }
  v9 = 96;
  std::wstring::wstring(Src, L"IMSISpecific\\");
  std::wstring::_Append<unsigned short>(Src);
  std::wstring::_Append<unsigned short>(Src);
  v7 = (const unsigned __int16 *)Src;
  if ( Src[3] > 7u )
    v7 = (const unsigned __int16 *)Src[0];
  if ( StateSeparation::GetValue((StateSeparation *)v18, v7, v5, v6, v8, sz, &v9) || IIDFromString(sz, (LPIID)a2 + 294) )
  {
    *((_OWORD *)a2 + 294) = ATTGeneralInternetandLTEAttachGUID;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_SetDmConfigProfileOEMConnectionId",
      4521,
      "Set connection GUID as _ATTGeneralInternetandLTEAttachGUID");
  }
  else
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::_SetDmConfigProfileOEMConnectionId",
      4514,
      "Set custom connection GUID. wstrGuid=%ls",
      sz);
  }
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v18);
}

```

## disassembly

```asm
0x18001f0dc  mov     [rsp-8+arg_10], rbx
0x18001f0e1  mov     [rsp-8+arg_18], rdi
0x18001f0e6  push    rbp
0x18001f0e7  lea     rbp, [rsp-20h]
0x18001f0ec  sub     rsp, 120h
0x18001f0f3  mov     rax, cs:__security_cookie
0x18001f0fa  xor     rax, rsp
0x18001f0fd  mov     [rbp+20h+var_10], rax
0x18001f101  mov     rbx, rdx
0x18001f104  mov     rdi, rcx
0x18001f107  lea     rcx, [rbp+20h+var_90]
0x18001f10b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001f110  nop
0x18001f111  lea     r8, [rbp+20h+var_90]
0x18001f115  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x18001f11a  test    eax, eax
0x18001f11c  jz      short loc_18001F173
0x18001f11e  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001f125  mov     [rsp+120h+pExceptionObject], rax
0x18001f12a  xorps   xmm0, xmm0
0x18001f12d  movups  [rsp+120h+var_C0], xmm0
0x18001f132  lea     rax, aFailedToGetPer; "failed to get persistent root string"
0x18001f139  mov     [rsp+120h+var_D8], rax
0x18001f13e  mov     [rsp+120h+var_D0], 1
0x18001f143  xor     eax, eax
0x18001f145  mov     [rsp+120h+var_CF], eax
0x18001f149  mov     [rsp+120h+var_CB], ax
0x18001f14e  mov     [rsp+120h+var_C9], al
0x18001f152  lea     rdx, [rsp+120h+var_C0]
0x18001f157  lea     rcx, [rsp+120h+var_D8]
0x18001f15c  call    _o___std_exception_copy_0
0x18001f161  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x18001f168  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18001f16d  call    _CxxThrowException_0
0x18001f173  mov     [rsp+120h+var_E0], 60h ; '`'
0x18001f17b  lea     rdx, aImsispecific_0; "IMSISpecific\\"
0x18001f182  lea     rcx, [rsp+120h+Src]
0x18001f187  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f18c  nop
0x18001f18d  lea     rdx, [rdi+190h]
0x18001f194  mov     r8, [rdx+10h]
0x18001f198  cmp     qword ptr [rdx+18h], 7
0x18001f19d  jbe     short loc_18001F1A2
0x18001f19f  mov     rdx, [rdx]
0x18001f1a2  lea     rcx, [rsp+120h+Src]; Src
0x18001f1a7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001f1ac  mov     r8d, 7
0x18001f1b2  lea     rdx, aCellux; "\\CellUx"
0x18001f1b9  lea     rcx, [rsp+120h+Src]; Src
0x18001f1be  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001f1c3  lea     rdx, [rsp+120h+Src]
0x18001f1c8  cmp     [rbp+20h+var_98], 7
0x18001f1cd  cmova   rdx, [rsp+120h+Src]; unsigned __int16 *
0x18001f1d3  lea     rax, [rsp+120h+var_E0]
0x18001f1d8  mov     [rsp+120h+var_F0], rax; LPDWORD
0x18001f1dd  lea     rax, [rbp+20h+sz]
0x18001f1e1  mov     [rsp+120h+var_F8], rax; PVOID
0x18001f1e6  lea     rcx, [rbp+20h+var_90]; this
0x18001f1ea  call    ?GetValue@StateSeparation@@QEAAKPEBG0KPEAKPEAX1@Z; StateSeparation::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x18001f1ef  test    eax, eax
0x18001f1f1  jnz     short loc_18001F226
0x18001f1f3  lea     rdx, [rbx+1260h]; lpiid
0x18001f1fa  lea     rcx, [rbp+20h+sz]; lpsz
0x18001f1fe  call    cs:__imp_IIDFromString
0x18001f204  test    eax, eax
0x18001f206  jnz     short loc_18001F226
0x18001f208  lea     r9, [rbp+20h+sz]
0x18001f20c  lea     r8, aSetCustomConne; "Set custom connection GUID. wstrGuid=%l"...
0x18001f213  mov     edx, 11A2h; unsigned int
0x18001f218  lea     rcx, aWindowsNetwork_48; "Windows::Networking::UX::Internal::MBCa"...
0x18001f21f  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001f224  jmp     short loc_18001F24E
0x18001f226  movups  xmm0, cs:_ATTGeneralInternetandLTEAttachGUID
0x18001f22d  movdqu  xmmword ptr [rbx+1260h], xmm0
0x18001f235  lea     r8, aSetConnectionG; "Set connection GUID as _ATTGeneralInter"...
0x18001f23c  mov     edx, 11A9h; unsigned int
0x18001f241  lea     rcx, aWindowsNetwork_48; "Windows::Networking::UX::Internal::MBCa"...
0x18001f248  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001f24d  nop
0x18001f24e  lea     rcx, [rsp+120h+Src]
0x18001f253  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f258  nop
0x18001f259  lea     rcx, [rbp+20h+var_90]
0x18001f25d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f262  mov     rcx, [rbp+20h+var_10]
0x18001f266  xor     rcx, rsp; StackCookie
0x18001f269  call    __security_check_cookie
0x18001f26e  lea     r11, [rsp+120h+var_s0]
0x18001f276  mov     rbx, [r11+20h]
0x18001f27a  mov     rdi, [r11+28h]
0x18001f27e  mov     rsp, r11
0x18001f281  pop     rbp
0x18001f282  retn
```
