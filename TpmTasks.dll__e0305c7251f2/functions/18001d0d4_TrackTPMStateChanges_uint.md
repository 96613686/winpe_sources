# TrackTPMStateChanges(uint)

- ea: `0x18001d0d4`
- end: `0x18001d936`
- name: `?TrackTPMStateChanges@@YAJI@Z`
- size: `2146`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x180007df0`
- `0x18000993c`
- `0x18000cbd4`
- `0x18000ce6c`
- `0x18000d524`
- `0x18000d7f4`
- `0x18000e360`
- `0x18000eb18`
- `0x18001a42c`
- `0x18001a450`
- `0x18001c7a0`
- `0x18001c8d8`
- `0x18001d0d4`
- `0x180023634`
- `0x18002386c`
- `0x180043360`
- `0x1800434b4`
- `0x180043824`
- `0x180043d58`
- `0x180043f94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d2b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d385`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d2b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d385`
- `TpmCoreProvisioning!TpmIsReadyInformation` at `0x18001d5af`
- `TpmCoreProvisioning!TpmIsReadyInformation` at `0x18001d5af`
- `TpmCoreProvisioning!TpmGet_ManufacturerVersion` at `0x18001d480`
- `TpmCoreProvisioning!TpmGet_ManufacturerVersion` at `0x18001d527`
- `TpmCoreProvisioning!TpmGet_ManufacturerVersion` at `0x18001d480`
- `TpmCoreProvisioning!TpmGet_ManufacturerVersion` at `0x18001d527`
- `TpmCoreProvisioning!TpmGet_IsTpmPresent` at `0x18001d14d`
- `TpmCoreProvisioning!TpmGet_IsTpmPresent` at `0x18001d14d`
- `TpmCoreProvisioning!TpmGet_ManufacturerId` at `0x18001d406`
- `TpmCoreProvisioning!TpmGet_ManufacturerId` at `0x18001d406`

## string_xrefs

- `0x18001d164`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d2c9`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d329`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d39a`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d41d`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d497`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d53e`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001d5c6`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall TrackTPMStateChanges(unsigned int a1)
{
  unsigned int v1; // r12d
  int IsTpmPresent; // eax
  unsigned int v3; // ebx
  __int64 String; // rax
  __int64 v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int DWord; // r13d
  int v9; // r15d
  unsigned int ValueW; // eax
  DWORD v11; // esi
  unsigned __int64 v12; // rax
  void *pvData; // rbx
  unsigned int v14; // eax
  bool v16; // si
  bool v17; // r14
  int ManufacturerId; // eax
  unsigned int v19; // ebx
  int ManufacturerVersion; // eax
  unsigned int v21; // ebx
  void **v22; // rax
  unsigned __int16 *v23; // rbx
  int v24; // eax
  unsigned int v25; // esi
  int IsReadyInformation; // eax
  unsigned int v27; // esi
  void **v28; // rax
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  bool v35; // zf
  char v36; // r15
  const unsigned __int16 *v37; // rax
  const unsigned __int16 *v38; // rdx
  const unsigned __int16 *v39; // r8
  bool v40; // r9
  bool v41; // r10
  __int64 v42; // rax
  unsigned int v43; // r8d
  const char *v44; // r9
  unsigned int v45; // r8d
  const char *v46; // r9
  int pdwType; // [rsp+20h] [rbp-148h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-148h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-148h]
  unsigned __int8 v50; // [rsp+60h] [rbp-108h] BYREF
  unsigned __int8 v51[3]; // [rsp+61h] [rbp-107h] BYREF
  unsigned int v52; // [rsp+64h] [rbp-104h] BYREF
  unsigned __int16 *v53; // [rsp+68h] [rbp-100h] BYREF
  void *v54; // [rsp+70h] [rbp-F8h] BYREF
  unsigned int v55; // [rsp+78h] [rbp-F0h] BYREF
  int v56; // [rsp+7Ch] [rbp-ECh]
  int v57; // [rsp+80h] [rbp-E8h]
  unsigned int v58; // [rsp+84h] [rbp-E4h]
  void *v59; // [rsp+88h] [rbp-E0h] BYREF
  unsigned int v60; // [rsp+90h] [rbp-D8h]
  DWORD pcbData; // [rsp+94h] [rbp-D4h] BYREF
  int v62; // [rsp+98h] [rbp-D0h]
  void *v63; // [rsp+A0h] [rbp-C8h] BYREF
  DWORD v64; // [rsp+A8h] [rbp-C0h] BYREF
  _BYTE v65[16]; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-A8h]
  _BYTE v67[16]; // [rsp+D0h] [rbp-98h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-88h]
  _BYTE v69[16]; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v70; // [rsp+100h] [rbp-68h]
  _BYTE v71[32]; // [rsp+110h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v1 = a1;
  LODWORD(v53) = a1;
  v56 = 0;
  LODWORD(v54) = 0;
  std::wstring::wstring(v69);
  std::wstring::wstring(v67);
  v52 = 0;
  v60 = 0;
  LODWORD(v63) = 0;
  LODWORD(v59) = 0;
  v50 = 0;
  IsTpmPresent = TpmGet_IsTpmPresent(&v50);
  v3 = IsTpmPresent;
  if ( IsTpmPresent < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DC,
      (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
      (const char *)(unsigned int)IsTpmPresent,
      pdwType);
LABEL_11:
    std::wstring::_Tidy_deallocate(v67);
    std::wstring::_Tidy_deallocate(v69);
    return v3;
  }
  try
  {
    DWord = HWSecurityRegistryManager::GetDWord(73);
    v60 = DWord;
    String = HWSecurityRegistryManager::GetString(v71, 71);
    std::wstring::operator=(v67, String);
    std::wstring::_Tidy_deallocate(v71);
    v5 = HWSecurityRegistryManager::GetString(v71, 74);
    std::wstring::operator=(v69, v5);
    std::wstring::_Tidy_deallocate(v71);
    v58 = HWSecurityRegistryManager::GetDWord(72);
    v52 = v58;
    v57 = HWSecurityRegistryManager::GetDWord(75);
    LODWORD(v63) = v57;
    v9 = HWSecurityRegistryManager::GetDWord(76);
    v62 = v9;
    LODWORD(v59) = v9;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x6EA, v6, v7);
    v58 = v52;
    DWord = v60;
    v57 = (int)v63;
    v9 = (int)v59;
    v62 = (int)v59;
    v56 = 0;
    v1 = (unsigned int)v53;
  }
  v55 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion",
             L"CurrentBuildNumber",
             2u,
             0,
             0,
             &pcbData);
  if ( ValueW )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x6FD,
           (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
           (const char *)ValueW,
           pdwTypea);
    goto LABEL_11;
  }
  v11 = (pcbData >> 1) + 1;
  v12 = 2LL * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  pvData = operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
  v54 = pvData;
  if ( !pvData )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x701,
      (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
      (const char *)0x8007000ELL,
      pdwTypea);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
    v3 = -2147024882;
    goto LABEL_11;
  }
  v64 = 2 * v11;
  v14 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion",
          L"CurrentBuildNumber",
          2u,
          0,
          pvData,
          &v64);
  if ( v14 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x70B,
           (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
           (const char *)v14,
           pdwTypeb);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
    goto LABEL_11;
  }
  v16 = 0;
  v17 = 0;
  std::wstring::wstring((__int64)v65, (__int64)pvData);
  v53 = 0;
  if ( v50 )
  {
    ManufacturerId = TpmGet_ManufacturerId(&v55);
    v19 = ManufacturerId;
    if ( ManufacturerId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x714,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
        (const char *)(unsigned int)ManufacturerId,
        pdwTypeb);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v53);
      std::wstring::_Tidy_deallocate(v65);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      return v19;
    }
    v52 = 0;
    ManufacturerVersion = TpmGet_ManufacturerVersion(&v52, 0);
    v21 = ManufacturerVersion;
    if ( ManufacturerVersion < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x718,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
        (const char *)(unsigned int)ManufacturerVersion,
        pdwTypeb);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v53);
      std::wstring::_Tidy_deallocate(v65);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      return v21;
    }
    v22 = (void **)std::make_unique<unsigned short [0],0>(&v63, v52);
    std::unique_ptr<unsigned short [0]>::operator=<std::default_delete<unsigned short [0]>,0>((void **)&v53, v22);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v63);
    v23 = v53;
    v24 = TpmGet_ManufacturerVersion(&v52, v53);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71A,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
        (const char *)(unsigned int)v24,
        pdwTypeb);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v53);
      std::wstring::_Tidy_deallocate(v65);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      return v25;
    }
    v51[0] = 0;
    LODWORD(v59) = 0;
    IsReadyInformation = TpmIsReadyInformation(v51, (unsigned int *)&v59);
    v27 = IsReadyInformation;
    if ( IsReadyInformation < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71F,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
        (const char *)(unsigned int)IsReadyInformation,
        pdwTypeb);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v53);
      std::wstring::_Tidy_deallocate(v65);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      return v27;
    }
    v16 = v51[0] != 0;
    v17 = (_DWORD)v59 == 0;
  }
  else
  {
    v28 = (void **)std::make_unique<unsigned short [0],0>(&v59, 1u);
    std::unique_ptr<unsigned short [0]>::operator=<std::default_delete<unsigned short [0]>,0>((void **)&v53, v28);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v59);
    v23 = v53;
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
  v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
  if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v29, v70, v30, v66)
    || (v31 = std::wstring::wstring((__int64)v71, (__int64)v23),
        v56 = 1,
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31),
        v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67),
        !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v32, v68, v33, v34))
    || v58 != v1
    || DWord != v55
    || (v57 != 0) != v17
    || (v35 = (v9 != 0) == v16, v36 = 1, !v35) )
  {
    v36 = 0;
  }
  if ( (v56 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v71);
  if ( v36 )
  {
    ProvisionTelemetryProvider::TpmTaskStateDidNotChange();
  }
  else
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
    v37 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
    ProvisionTelemetryProvider::TpmTaskStateChanged(v37, v38, v39, v23, DWord, v55, v58, v1, v41, v17, v40, v16);
    if ( v50 )
    {
      try
      {
        HWSecurityRegistryManager::SetString(74, v65);
        v42 = std::wstring::wstring((__int64)v71, (__int64)v23);
        HWSecurityRegistryManager::SetString(71, v42);
        std::wstring::_Tidy_deallocate(v71);
        HWSecurityRegistryManager::SetDWord(73, v55);
        HWSecurityRegistryManager::SetDWord(72, v1);
        HWSecurityRegistryManager::SetDWord(75, v17);
        HWSecurityRegistryManager::SetDWord(76, v16);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x756, v43, v44);
      }
    }
    else
    {
      try
      {
        HWSecurityRegistryManager::SetString(74, v65);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x75E, v45, v46);
      }
      HWSecurityRegistryManager::DeleteKeyValue(71);
      HWSecurityRegistryManager::DeleteKeyValue(73);
      HWSecurityRegistryManager::DeleteKeyValue(72);
      HWSecurityRegistryManager::DeleteKeyValue(75);
      HWSecurityRegistryManager::DeleteKeyValue(76);
    }
  }
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v53);
  std::wstring::_Tidy_deallocate(v65);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v54);
  std::wstring::_Tidy_deallocate(v67);
  std::wstring::_Tidy_deallocate(v69);
  return 0;
}

```

## disassembly

```asm
0x18001d0d4  mov     r11, rsp
0x18001d0d7  mov     [r11+10h], rbx
0x18001d0db  mov     [r11+18h], rsi
0x18001d0df  push    rdi
0x18001d0e0  push    r12
0x18001d0e2  push    r13
0x18001d0e4  push    r14
0x18001d0e6  push    r15
0x18001d0e8  sub     rsp, 140h
0x18001d0ef  mov     rax, cs:__security_cookie
0x18001d0f6  xor     rax, rsp
0x18001d0f9  mov     [rsp+168h+var_38], rax
0x18001d101  mov     r12d, ecx
0x18001d104  mov     dword ptr [rsp+168h+var_100], ecx
0x18001d108  xor     edi, edi
0x18001d10a  mov     [rsp+168h+var_EC], edi
0x18001d10e  mov     dword ptr [rsp+168h+var_F8], edi
0x18001d112  lea     rcx, [r11-78h]
0x18001d116  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d11b  nop
0x18001d11c  lea     rcx, [rsp+168h+var_98]
0x18001d124  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d129  nop
0x18001d12a  mov     [rsp+168h+var_104], edi
0x18001d12e  mov     [rsp+168h+var_D8], edi
0x18001d135  mov     dword ptr [rsp+168h+var_C8], edi
0x18001d13c  mov     dword ptr [rsp+168h+var_E0], edi
0x18001d143  mov     [rsp+168h+var_108], dil
0x18001d148  lea     rcx, [rsp+168h+var_108]
0x18001d14d  call    cs:__imp_?TpmGet_IsTpmPresent@@YAJPEAE@Z; TpmGet_IsTpmPresent(uchar *)
0x18001d153  mov     ebx, eax
0x18001d155  test    eax, eax
0x18001d157  jns     short loc_18001D17A
0x18001d159  mov     rcx, [rsp+168h]; this
0x18001d161  mov     r9d, eax; char *
0x18001d164  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d16b  mov     edx, 6DCh; void *
0x18001d170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d175  jmp     loc_18001D3B8
0x18001d17a  mov     ecx, 49h ; 'I'
0x18001d17f  call    ?GetDWord@HWSecurityRegistryManager@@SAKW4RegValues@1@@Z; HWSecurityRegistryManager::GetDWord(HWSecurityRegistryManager::RegValues)
0x18001d184  mov     r13d, eax
0x18001d187  mov     [rsp+168h+var_D8], eax
0x18001d18e  mov     edx, 47h ; 'G'
0x18001d193  lea     rcx, [rsp+168h+var_58]
0x18001d19b  call    ?GetString@HWSecurityRegistryManager@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RegValues@1@@Z; HWSecurityRegistryManager::GetString(HWSecurityRegistryManager::RegValues)
0x18001d1a0  mov     rdx, rax
0x18001d1a3  lea     rcx, [rsp+168h+var_98]
0x18001d1ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d1b0  lea     rcx, [rsp+168h+var_58]
0x18001d1b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d1bd  mov     edx, 4Ah ; 'J'
0x18001d1c2  lea     rcx, [rsp+168h+var_58]
0x18001d1ca  call    ?GetString@HWSecurityRegistryManager@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RegValues@1@@Z; HWSecurityRegistryManager::GetString(HWSecurityRegistryManager::RegValues)
0x18001d1cf  mov     rdx, rax
0x18001d1d2  lea     rcx, [rsp+168h+var_78]
0x18001d1da  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d1df  lea     rcx, [rsp+168h+var_58]
0x18001d1e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d1ec  mov     ecx, 48h ; 'H'
0x18001d1f1  call    ?GetDWord@HWSecurityRegistryManager@@SAKW4RegValues@1@@Z; HWSecurityRegistryManager::GetDWord(HWSecurityRegistryManager::RegValues)
0x18001d1f6  mov     [rsp+168h+var_E4], eax
0x18001d1fd  mov     [rsp+168h+var_104], eax
0x18001d201  mov     ecx, 4Bh ; 'K'
0x18001d206  call    ?GetDWord@HWSecurityRegistryManager@@SAKW4RegValues@1@@Z; HWSecurityRegistryManager::GetDWord(HWSecurityRegistryManager::RegValues)
0x18001d20b  mov     [rsp+168h+var_E8], eax
0x18001d212  mov     dword ptr [rsp+168h+var_C8], eax
0x18001d219  mov     ecx, 4Ch ; 'L'
0x18001d21e  call    ?GetDWord@HWSecurityRegistryManager@@SAKW4RegValues@1@@Z; HWSecurityRegistryManager::GetDWord(HWSecurityRegistryManager::RegValues)
0x18001d223  mov     r15d, eax
0x18001d226  mov     [rsp+168h+var_D0], eax
0x18001d22d  mov     dword ptr [rsp+168h+var_E0], eax
0x18001d234  jmp     short loc_18001D274
0x18001d236  xor     edi, edi
0x18001d238  mov     eax, [rsp+168h+var_104]
0x18001d23c  mov     [rsp+168h+var_E4], eax
0x18001d243  mov     r13d, [rsp+168h+var_D8]
0x18001d24b  mov     eax, dword ptr [rsp+168h+var_C8]
0x18001d252  mov     [rsp+168h+var_E8], eax
0x18001d259  mov     r15d, dword ptr [rsp+168h+var_E0]
0x18001d261  mov     [rsp+168h+var_D0], r15d
0x18001d269  mov     eax, edi
0x18001d26b  mov     [rsp+168h+var_EC], eax
0x18001d26f  mov     r12d, dword ptr [rsp+168h+var_100]
0x18001d274  mov     [rsp+168h+var_F0], edi
0x18001d278  mov     [rsp+168h+var_D4], edi
0x18001d27f  lea     rax, [rsp+168h+var_D4]
0x18001d287  mov     [rsp+168h+pcbData], rax; pcbData
0x18001d28c  mov     [rsp+168h+pvData], rdi; pvData
0x18001d291  mov     [rsp+168h+pdwType], rdi; int
0x18001d296  mov     r14d, 2
0x18001d29c  mov     r9d, r14d; dwFlags
0x18001d29f  lea     r8, aCurrentbuildnu; "CurrentBuildNumber"
0x18001d2a6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001d2ad  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001d2b4  call    cs:__imp_RegGetValueW
0x18001d2ba  test    eax, eax
0x18001d2bc  jz      short loc_18001D2E1
0x18001d2be  mov     rcx, [rsp+168h]; this
0x18001d2c6  mov     r9d, eax; char *
0x18001d2c9  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d2d0  mov     edx, 6FDh; void *
0x18001d2d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d2da  mov     ebx, eax
0x18001d2dc  jmp     loc_18001D3B8
0x18001d2e1  mov     esi, [rsp+168h+var_D4]
0x18001d2e8  shr     esi, 1
0x18001d2ea  inc     esi
0x18001d2ec  mov     ecx, esi
0x18001d2ee  mov     rax, r14
0x18001d2f1  mul     rcx
0x18001d2f4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d2fb  cmovb   rax, rcx
0x18001d2ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d306  mov     rcx, rax; unsigned __int64
0x18001d309  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d30e  mov     rbx, rax
0x18001d311  mov     [rsp+168h+var_F8], rax
0x18001d316  test    rax, rax
0x18001d319  jnz     short loc_18001D34C
0x18001d31b  mov     rcx, [rsp+168h]; this
0x18001d323  mov     r9d, 8007000Eh; char *
0x18001d329  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d330  mov     edx, 701h; void *
0x18001d335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d33a  nop
0x18001d33b  lea     rcx, [rsp+168h+var_F8]
0x18001d340  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d345  mov     ebx, 8007000Eh
0x18001d34a  jmp     short loc_18001D3B8
0x18001d34c  lea     eax, [rsi+rsi]
0x18001d34f  mov     [rsp+168h+var_C0], eax
0x18001d356  lea     rax, [rsp+168h+var_C0]
0x18001d35e  mov     [rsp+168h+pcbData], rax; pcbData
0x18001d363  mov     [rsp+168h+pvData], rbx; pvData
0x18001d368  mov     [rsp+168h+pdwType], rdi; int
0x18001d36d  mov     r9d, r14d; dwFlags
0x18001d370  lea     r8, aCurrentbuildnu; "CurrentBuildNumber"
0x18001d377  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001d37e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001d385  call    cs:__imp_RegGetValueW
0x18001d38b  test    eax, eax
0x18001d38d  jz      short loc_18001D3DA
0x18001d38f  mov     rcx, [rsp+168h]; this
0x18001d397  mov     r9d, eax; char *
0x18001d39a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d3a1  mov     edx, 70Bh; void *
0x18001d3a6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d3ab  mov     ebx, eax
0x18001d3ad  lea     rcx, [rsp+168h+var_F8]
0x18001d3b2  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d3b7  nop
0x18001d3b8  lea     rcx, [rsp+168h+var_98]
0x18001d3c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d3c5  nop
0x18001d3c6  lea     rcx, [rsp+168h+var_78]
0x18001d3ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d3d3  mov     eax, ebx
0x18001d3d5  jmp     loc_18001D909
0x18001d3da  mov     sil, dil
0x18001d3dd  mov     r14b, dil
0x18001d3e0  mov     rdx, rbx
0x18001d3e3  lea     rcx, [rsp+168h+var_B8]
0x18001d3eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d3f0  nop
0x18001d3f1  mov     [rsp+168h+var_100], rdi
0x18001d3f6  cmp     [rsp+168h+var_108], dil
0x18001d3fb  jz      loc_18001D634
0x18001d401  lea     rcx, [rsp+168h+var_F0]
0x18001d406  call    cs:__imp_?TpmGet_ManufacturerId@@YAJPEAI@Z; TpmGet_ManufacturerId(uint *)
0x18001d40c  mov     ebx, eax
0x18001d40e  test    eax, eax
0x18001d410  jns     short loc_18001D475
0x18001d412  mov     rcx, [rsp+168h]; this
0x18001d41a  mov     r9d, eax; char *
0x18001d41d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d424  mov     edx, 714h; void *
0x18001d429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d42e  nop
0x18001d42f  lea     rcx, [rsp+168h+var_100]
0x18001d434  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d439  nop
0x18001d43a  lea     rcx, [rsp+168h+var_B8]
0x18001d442  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d447  nop
0x18001d448  lea     rcx, [rsp+168h+var_F8]
0x18001d44d  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d452  nop
0x18001d453  lea     rcx, [rsp+168h+var_98]
0x18001d45b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d460  nop
0x18001d461  lea     rcx, [rsp+168h+var_78]
0x18001d469  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d46e  mov     eax, ebx
0x18001d470  jmp     loc_18001D909
0x18001d475  mov     [rsp+168h+var_104], edi
0x18001d479  xor     edx, edx
0x18001d47b  lea     rcx, [rsp+168h+var_104]
0x18001d480  call    cs:__imp_?TpmGet_ManufacturerVersion@@YAJPEAIPEAG@Z; TpmGet_ManufacturerVersion(uint *,ushort *)
0x18001d486  mov     ebx, eax
0x18001d488  test    eax, eax
0x18001d48a  jns     short loc_18001D4EF
0x18001d48c  mov     rcx, [rsp+168h]; this
0x18001d494  mov     r9d, eax; char *
0x18001d497  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d49e  mov     edx, 718h; void *
0x18001d4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d4a8  nop
0x18001d4a9  lea     rcx, [rsp+168h+var_100]
0x18001d4ae  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d4b3  nop
0x18001d4b4  lea     rcx, [rsp+168h+var_B8]
0x18001d4bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d4c1  nop
0x18001d4c2  lea     rcx, [rsp+168h+var_F8]
0x18001d4c7  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d4cc  nop
0x18001d4cd  lea     rcx, [rsp+168h+var_98]
0x18001d4d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d4da  nop
0x18001d4db  lea     rcx, [rsp+168h+var_78]
0x18001d4e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d4e8  mov     eax, ebx
0x18001d4ea  jmp     loc_18001D909
0x18001d4ef  mov     edx, [rsp+168h+var_104]
0x18001d4f3  lea     rcx, [rsp+168h+var_C8]
0x18001d4fb  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x18001d500  mov     rdx, rax
0x18001d503  lea     rcx, [rsp+168h+var_100]
0x18001d508  call    ??$?4U?$default_delete@$$BY0A@G@std@@$0A@@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort [0]>::operator=<std::default_delete<ushort [0]>,0>(std::unique_ptr<ushort [0]> &&)
0x18001d50d  lea     rcx, [rsp+168h+var_C8]
0x18001d515  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d51a  mov     rbx, [rsp+168h+var_100]
0x18001d51f  mov     rdx, rbx
0x18001d522  lea     rcx, [rsp+168h+var_104]
0x18001d527  call    cs:__imp_?TpmGet_ManufacturerVersion@@YAJPEAIPEAG@Z; TpmGet_ManufacturerVersion(uint *,ushort *)
0x18001d52d  mov     esi, eax
0x18001d52f  test    eax, eax
0x18001d531  jns     short loc_18001D596
0x18001d533  mov     rcx, [rsp+168h]; this
0x18001d53b  mov     r9d, eax; char *
0x18001d53e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d545  mov     edx, 71Ah; void *
0x18001d54a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d54f  nop
0x18001d550  lea     rcx, [rsp+168h+var_100]
0x18001d555  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d55a  nop
0x18001d55b  lea     rcx, [rsp+168h+var_B8]
0x18001d563  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d568  nop
0x18001d569  lea     rcx, [rsp+168h+var_F8]
0x18001d56e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d573  nop
0x18001d574  lea     rcx, [rsp+168h+var_98]
0x18001d57c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d581  nop
0x18001d582  lea     rcx, [rsp+168h+var_78]
0x18001d58a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d58f  mov     eax, esi
0x18001d591  jmp     loc_18001D909
0x18001d596  mov     [rsp+168h+var_107], dil
0x18001d59b  mov     dword ptr [rsp+168h+var_E0], edi
0x18001d5a2  lea     rdx, [rsp+168h+var_E0]
0x18001d5aa  lea     rcx, [rsp+168h+var_107]
0x18001d5af  call    cs:__imp_?TpmIsReadyInformation@@YAJPEAEPEAI@Z; TpmIsReadyInformation(uchar *,uint *)
0x18001d5b5  mov     esi, eax
0x18001d5b7  test    eax, eax
0x18001d5b9  jns     short loc_18001D61E
0x18001d5bb  mov     rcx, [rsp+168h]; this
0x18001d5c3  mov     r9d, eax; char *
0x18001d5c6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001d5cd  mov     edx, 71Fh; void *
0x18001d5d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d5d7  nop
0x18001d5d8  lea     rcx, [rsp+168h+var_100]
0x18001d5dd  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d5e2  nop
0x18001d5e3  lea     rcx, [rsp+168h+var_B8]
0x18001d5eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d5f0  nop
0x18001d5f1  lea     rcx, [rsp+168h+var_F8]
0x18001d5f6  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001d5fb  nop
0x18001d5fc  lea     rcx, [rsp+168h+var_98]
0x18001d604  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d609  nop
0x18001d60a  lea     rcx, [rsp+168h+var_78]
0x18001d612  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d617  mov     eax, esi
0x18001d619  jmp     loc_18001D909
0x18001d61e  cmp     [rsp+168h+var_107], dil
0x18001d623  setnz   sil
0x18001d627  cmp     dword ptr [rsp+168h+var_E0], edi
0x18001d62e  setz    r14b
0x18001d632  jmp     short loc_18001D665
0x18001d634  mov     edx, 1
0x18001d639  lea     rcx, [rsp+168h+var_E0]
0x18001d641  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x18001d646  mov     rdx, rax
  ... truncated ...
```
