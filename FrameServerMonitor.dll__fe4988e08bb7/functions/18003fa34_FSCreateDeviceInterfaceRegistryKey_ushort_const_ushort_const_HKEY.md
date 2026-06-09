# FSCreateDeviceInterfaceRegistryKey(ushort const *,ushort const *,HKEY__ * *)

- ea: `0x18003fa34`
- end: `0x18003fcd4`
- name: `?FSCreateDeviceInterfaceRegistryKey@@YAJPEBG0PEAPEAUHKEY__@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004289c`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180004f34`
- `0x1800060f8`
- `0x180006a98`
- `0x18000e6bc`
- `0x180017b98`
- `0x18003f660`
- `0x18003fa34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fbe5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fbe5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003fb10`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18003fb10`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18003fab5`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18003fab5`

## pseudocode

```c
__int64 __fastcall FSCreateDeviceInterfaceRegistryKey(LPCWSTR pszDeviceInterface, const unsigned __int16 *a2, HKEY *a3)
{
  signed int v6; // ebx
  CONFIGRET v7; // eax
  __int64 v8; // rdx
  signed int v9; // eax
  WCHAR *v10; // rdi
  WCHAR *v11; // r14
  bool v12; // si
  WCHAR v13; // ax
  WCHAR v14; // si
  LSTATUS v15; // eax
  HKEY phkDeviceInterface; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  phkDeviceInterface = 0;
  if ( pszDeviceInterface )
  {
    if ( !a3 )
    {
      v6 = -2147467261;
      goto LABEL_37;
    }
    *a3 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkDeviceInterface,
      0);
    v7 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0xF003Fu, 1u, &phkDeviceInterface, 0);
    if ( v7 )
    {
      v9 = CM_MapCrToWin32Err(v7, 0xDu);
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_37;
        v8 = 35;
        goto LABEL_16;
      }
    }
    else
    {
      v6 = 0;
    }
    if ( a2 )
    {
      memset_0(SubKey, 0, 0x208u);
      v6 = StringCchCopyW(SubKey, 0x104u, a2);
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_37;
        v8 = 36;
LABEL_16:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v6);
        goto LABEL_37;
      }
      v10 = SubKey;
      v11 = SubKey;
      v12 = SubKey[0] == 0;
      while ( !v12 )
      {
        phkResult = 0;
        while ( 1 )
        {
          v13 = *v10;
          if ( !*v10 || v13 == 92 || v13 == 47 )
            break;
          ++v10;
        }
        v14 = *v10;
        *v10 = 0;
        if ( v10 == v11 )
        {
          v12 = 1;
        }
        else
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &phkResult,
            0);
          v15 = RegCreateKeyExW(phkDeviceInterface, v11, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
          v6 = v15;
          if ( v15 )
          {
            if ( v15 > 0 )
              v6 = (unsigned __int16)v15 | 0x80070000;
            if ( v6 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  37,
                  &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
                  0,
                  v6);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
              goto LABEL_37;
            }
          }
          else
          {
            v6 = 0;
          }
          v19[0] = phkDeviceInterface;
          phkDeviceInterface = 0;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
            &phkDeviceInterface,
            &phkResult);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
            &phkResult,
            v19);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v19);
          *v10++ = v14;
          v11 = v10;
          v12 = *v10 == 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      }
    }
    *a3 = phkDeviceInterface;
    phkDeviceInterface = 0;
    goto LABEL_37;
  }
  v6 = -2147024809;
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003fa34  push    rbp
0x18003fa36  push    rbx
0x18003fa37  push    rsi
0x18003fa38  push    rdi
0x18003fa39  push    r12
0x18003fa3b  push    r14
0x18003fa3d  push    r15
0x18003fa3f  lea     rbp, [rsp-190h]
0x18003fa47  sub     rsp, 290h
0x18003fa4e  mov     rax, cs:__security_cookie
0x18003fa55  xor     rax, rsp
0x18003fa58  mov     [rbp+1C0h+var_40], rax
0x18003fa5f  xor     r12d, r12d
0x18003fa62  mov     r15, r8
0x18003fa65  mov     [rsp+2C0h+phkDeviceInterface], r12
0x18003fa6a  mov     rdi, rdx
0x18003fa6d  mov     rbx, rcx
0x18003fa70  test    rcx, rcx
0x18003fa73  jnz     short loc_18003FA7F
0x18003fa75  mov     ebx, 80070057h
0x18003fa7a  jmp     loc_18003FCA7
0x18003fa7f  test    r15, r15
0x18003fa82  jnz     short loc_18003FA8E
0x18003fa84  mov     ebx, 80004003h
0x18003fa89  jmp     loc_18003FCA7
0x18003fa8e  xor     edx, edx
0x18003fa90  mov     [r8], r12
0x18003fa93  lea     rcx, [rsp+2C0h+phkDeviceInterface]
0x18003fa98  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003fa9d  lea     r9, [rsp+2C0h+phkDeviceInterface]; phkDeviceInterface
0x18003faa2  mov     [rsp+2C0h+ulFlags], r12d; ulFlags
0x18003faa7  mov     edx, 0F003Fh; samDesired
0x18003faac  mov     r8d, 1; Disposition
0x18003fab2  mov     rcx, rbx; pszDeviceInterface
0x18003fab5  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18003fabb  test    eax, eax
0x18003fabd  jnz     short loc_18003FB09
0x18003fabf  mov     ebx, r12d
0x18003fac2  test    rdi, rdi
0x18003fac5  jz      loc_18003FC9A
0x18003facb  xor     edx, edx; Val
0x18003facd  lea     rcx, [rsp+2C0h+SubKey]; void *
0x18003fad2  mov     r8d, 208h; Size
0x18003fad8  call    memset_0
0x18003fadd  mov     r8, rdi; unsigned __int16 *
0x18003fae0  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x18003fae5  mov     edx, 104h; unsigned __int64
0x18003faea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003faef  mov     ebx, eax
0x18003faf1  test    eax, eax
0x18003faf3  jns     short loc_18003FB5E
0x18003faf5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fafa  cmp     al, 1
0x18003fafc  jb      loc_18003FCA7
0x18003fb02  mov     edx, 24h ; '$'
0x18003fb07  jmp     short loc_18003FB3B
0x18003fb09  mov     edx, 0Dh; DefaultErr
0x18003fb0e  mov     ecx, eax; CmReturnCode
0x18003fb10  call    cs:__imp_CM_MapCrToWin32Err
0x18003fb16  mov     ebx, eax
0x18003fb18  test    eax, eax
0x18003fb1a  jle     short loc_18003FB25
0x18003fb1c  movzx   ebx, ax
0x18003fb1f  or      ebx, 80070000h
0x18003fb25  test    ebx, ebx
0x18003fb27  jns     short loc_18003FAC2
0x18003fb29  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fb2e  cmp     al, 1
0x18003fb30  jb      loc_18003FCA7
0x18003fb36  mov     edx, 23h ; '#'
0x18003fb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb42  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18003fb49  xor     r9d, r9d
0x18003fb4c  mov     [rsp+2C0h+ulFlags], ebx
0x18003fb50  mov     rcx, [rcx+10h]
0x18003fb54  call    WPP_SF_qD
0x18003fb59  jmp     loc_18003FCA7
0x18003fb5e  cmp     [rsp+2C0h+SubKey], r12w
0x18003fb64  lea     rdi, [rsp+2C0h+SubKey]
0x18003fb69  lea     r14, [rsp+2C0h+SubKey]
0x18003fb6e  setz    sil
0x18003fb72  test    sil, sil
0x18003fb75  jnz     loc_18003FC9A
0x18003fb7b  mov     [rsp+2C0h+var_268], r12
0x18003fb80  jmp     short loc_18003FB92
0x18003fb82  cmp     ax, 5Ch ; '\'
0x18003fb86  jz      short loc_18003FB9A
0x18003fb88  cmp     ax, 2Fh ; '/'
0x18003fb8c  jz      short loc_18003FB9A
0x18003fb8e  add     rdi, 2
0x18003fb92  movzx   eax, word ptr [rdi]
0x18003fb95  test    ax, ax
0x18003fb98  jnz     short loc_18003FB82
0x18003fb9a  movzx   esi, word ptr [rdi]
0x18003fb9d  mov     [rdi], r12w
0x18003fba1  cmp     rdi, r14
0x18003fba4  jz      loc_18003FC50
0x18003fbaa  xor     edx, edx
0x18003fbac  lea     rcx, [rsp+2C0h+var_268]
0x18003fbb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003fbb6  mov     rcx, [rsp+2C0h+phkDeviceInterface]; hKey
0x18003fbbb  lea     rax, [rsp+2C0h+var_268]
0x18003fbc0  mov     [rsp+2C0h+lpdwDisposition], r12; lpdwDisposition
0x18003fbc5  xor     r9d, r9d; lpClass
0x18003fbc8  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18003fbcd  xor     r8d, r8d; Reserved
0x18003fbd0  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18003fbd5  mov     rdx, r14; lpSubKey
0x18003fbd8  mov     [rsp+2C0h+samDesired], 0F003Fh; samDesired
0x18003fbe0  mov     [rsp+2C0h+ulFlags], r12d; dwOptions
0x18003fbe5  call    cs:__imp_RegCreateKeyExW
0x18003fbeb  mov     ebx, eax
0x18003fbed  test    eax, eax
0x18003fbef  jnz     short loc_18003FBF6
0x18003fbf1  mov     ebx, r12d
0x18003fbf4  jmp     short loc_18003FC05
0x18003fbf6  jle     short loc_18003FC01
0x18003fbf8  movzx   ebx, ax
0x18003fbfb  or      ebx, 80070000h
0x18003fc01  test    ebx, ebx
0x18003fc03  js      short loc_18003FC62
0x18003fc05  mov     rax, [rsp+2C0h+phkDeviceInterface]
0x18003fc0a  lea     rdx, [rsp+2C0h+var_268]
0x18003fc0f  lea     rcx, [rsp+2C0h+phkDeviceInterface]
0x18003fc14  mov     [rsp+2C0h+var_260], rax
0x18003fc19  mov     [rsp+2C0h+phkDeviceInterface], r12
0x18003fc1e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18003fc23  lea     rdx, [rsp+2C0h+var_260]
0x18003fc28  lea     rcx, [rsp+2C0h+var_268]
0x18003fc2d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18003fc32  lea     rcx, [rsp+2C0h+var_260]
0x18003fc37  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003fc3c  mov     [rdi], si
0x18003fc3f  add     rdi, 2
0x18003fc43  mov     r14, rdi
0x18003fc46  cmp     [rdi], r12w
0x18003fc4a  setz    sil
0x18003fc4e  jmp     short loc_18003FC53
0x18003fc50  mov     sil, 1
0x18003fc53  lea     rcx, [rsp+2C0h+var_268]
0x18003fc58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003fc5d  jmp     loc_18003FB72
0x18003fc62  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003fc67  cmp     al, 1
0x18003fc69  jb      short loc_18003FC8E
0x18003fc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc72  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18003fc79  mov     edx, 25h ; '%'
0x18003fc7e  mov     [rsp+2C0h+ulFlags], ebx
0x18003fc82  xor     r9d, r9d
0x18003fc85  mov     rcx, [rcx+10h]
0x18003fc89  call    WPP_SF_qD
0x18003fc8e  lea     rcx, [rsp+2C0h+var_268]
0x18003fc93  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003fc98  jmp     short loc_18003FCA7
0x18003fc9a  mov     rax, [rsp+2C0h+phkDeviceInterface]
0x18003fc9f  mov     [r15], rax
0x18003fca2  mov     [rsp+2C0h+phkDeviceInterface], r12
0x18003fca7  lea     rcx, [rsp+2C0h+phkDeviceInterface]
0x18003fcac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003fcb1  mov     eax, ebx
0x18003fcb3  mov     rcx, [rbp+1C0h+var_40]
0x18003fcba  xor     rcx, rsp; StackCookie
0x18003fcbd  call    __security_check_cookie
0x18003fcc2  add     rsp, 290h
0x18003fcc9  pop     r15
0x18003fccb  pop     r14
0x18003fccd  pop     r12
0x18003fccf  pop     rdi
0x18003fcd0  pop     rsi
0x18003fcd1  pop     rbx
0x18003fcd2  pop     rbp
0x18003fcd3  retn
```
