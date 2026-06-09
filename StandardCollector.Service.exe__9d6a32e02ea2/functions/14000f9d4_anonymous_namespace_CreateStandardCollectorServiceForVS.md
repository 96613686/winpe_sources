# _anonymous_namespace_::CreateStandardCollectorServiceForVS

- ea: `0x14000f9d4`
- end: `0x14000fcfc`
- name: `_anonymous_namespace_::CreateStandardCollectorServiceForVS`
- size: `808`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000356c`
- `0x14001008c`

## callees

- `0x140002e74`
- `0x1400043a0`
- `0x140006d10`
- `0x14000ec38`
- `0x14000f098`
- `0x14000f9d4`
- `0x140010260`
- `0x140010408`
- `0x1400108a8`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000fb0a`
- `KERNEL32!LeaveCriticalSection` at `0x14000fb72`
- `KERNEL32!LeaveCriticalSection` at `0x14000fb0a`
- `KERNEL32!LeaveCriticalSection` at `0x14000fb72`
- `KERNEL32!EnterCriticalSection` at `0x14000fa92`
- `KERNEL32!EnterCriticalSection` at `0x14000fa92`
- `ole32!CoCreateInstance` at `0x14000fb9d`
- `ole32!CoCreateInstance` at `0x14000fb9d`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fa47`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fbea`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fa47`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fbea`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fa3e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb4e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fcaf`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fcb9`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fa3e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fb4e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fcaf`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fcb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::CreateStandardCollectorServiceForVS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  DiagHubCommon *v5; // rdi
  int ModulePath; // ebx
  unsigned __int16 **v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  void (__fastcall ***v13)(_QWORD, __int64); // rbx
  __int64 v14; // rcx
  LPVOID v15; // r9
  __int64 v16; // rcx
  int v17; // eax
  BSTR v19; // [rsp+30h] [rbp-29h] BYREF
  void (__fastcall ***v20)(_QWORD, __int64); // [rsp+38h] [rbp-21h]
  BSTR bstrString[2]; // [rsp+40h] [rbp-19h] BYREF
  DiagHubCommon *v22; // [rsp+50h] [rbp-9h]
  struct _RTL_CRITICAL_SECTION *v23; // [rsp+58h] [rbp-1h]
  LPVOID ppv; // [rsp+60h] [rbp+7h] BYREF
  __int64 v25; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v26; // [rsp+70h] [rbp+17h] BYREF
  OLECHAR *psz[2]; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v28; // [rsp+88h] [rbp+2Fh]

  v5 = 0;
  v22 = 0;
  *(_OWORD *)psz = 0;
  v28 = 0;
  ModulePath = DiagHubCommon::ModulePath::GetModulePath(0);
  if ( ModulePath >= 0 )
  {
    if ( psz[0] )
    {
      SysFreeString(0);
      v5 = (DiagHubCommon *)SysAllocString(psz[0]);
      v22 = v5;
      if ( !v5 )
        ATL::AtlThrowImpl(-2147024882);
    }
    std::vector<unsigned short>::~vector<unsigned short>(psz);
    v19 = 0;
    ModulePath = DiagHubCommon::DetermineVsInstanceRoot(v5, (const unsigned __int16 *)&v19, v7);
    if ( ModulePath < 0 )
      goto LABEL_35;
    v23 = &CriticalSection;
    EnterCriticalSection(&CriticalSection);
    v9 = std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
           v8,
           &v19);
    v11 = *(_QWORD *)(std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(
                        v10,
                        bstrString,
                        &v19,
                        v9)
                    + 8);
    v12 = qword_140024A98;
    if ( v11 )
      v12 = v11;
    if ( v12 == qword_140024A98 )
    {
      v20 = 0;
      ModulePath = DiagHubCommon::RegisterStandardCollectorProxyStubs((__int64)v19);
      if ( ModulePath < 0 )
      {
        if ( v20 )
          (**v20)(v20, 1);
        LeaveCriticalSection(&CriticalSection);
LABEL_35:
        SysFreeString(v19);
        goto LABEL_36;
      }
      v13 = v20;
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v20)[1])(v20);
      if ( v19 )
      {
        bstrString[0] = SysAllocString(v19);
        if ( !bstrString[0] )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        bstrString[0] = 0;
      }
      std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::insert(
        v14,
        psz,
        bstrString);
      SysFreeString(bstrString[0]);
      if ( v13 )
        (**v13)(v13, 1);
    }
    LeaveCriticalSection(&CriticalSection);
    ppv = 0;
    ModulePath = CoCreateInstance(
                   &GUID_f2dc0f57_0b99_49e3_be80_936dbaa54ee0,
                   0,
                   4u,
                   &GUID_d2020dea_eb40_45d5_b420_b9fb623c4fd1,
                   &ppv);
    if ( ModulePath < 0 )
    {
LABEL_33:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_35;
    }
    v15 = ppv;
    v16 = 0;
    v25 = 0;
    if ( ppv )
    {
      v17 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
              ppv,
              &GUID_722e9581_5247_4066_9eda_5d4e36a13de9,
              &v25);
      v15 = ppv;
      if ( v17 >= 0 )
      {
        v16 = v25;
      }
      else
      {
        v16 = 0;
        v25 = 0;
      }
    }
    if ( v16 )
    {
      ModulePath = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, 0);
      if ( ModulePath < 0 )
      {
LABEL_31:
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        goto LABEL_33;
      }
      v15 = ppv;
    }
    v26 = 0;
    ModulePath = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, v19, &v26);
    if ( ModulePath >= 0 )
      ModulePath = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v26)(
                     v26,
                     &GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44,
                     a4);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_31;
  }
  std::vector<unsigned short>::~vector<unsigned short>(psz);
LABEL_36:
  SysFreeString((BSTR)v5);
  return (unsigned int)ModulePath;
}

```

## disassembly

```asm
0x14000f9d4  mov     [rsp-8+arg_0], rbx
0x14000f9d9  mov     [rsp-8+arg_8], rdi
0x14000f9de  push    rbp
0x14000f9df  push    r12
0x14000f9e1  push    r14
0x14000f9e3  lea     rbp, [rsp-47h]
0x14000f9e8  sub     rsp, 0A0h
0x14000f9ef  mov     rax, cs:__security_cookie
0x14000f9f6  xor     rax, rsp
0x14000f9f9  mov     [rbp+57h+var_20], rax
0x14000f9fd  mov     r14, r9
0x14000fa00  xor     edi, edi
0x14000fa02  mov     [rbp+57h+var_60], rdi
0x14000fa06  xor     eax, eax
0x14000fa08  xorps   xmm1, xmm1
0x14000fa0b  movdqu  xmmword ptr [rbp+57h+psz], xmm1
0x14000fa10  mov     [rbp+57h+var_28], rax
0x14000fa14  lea     rdx, [rbp+57h+psz]
0x14000fa18  xor     ecx, ecx; hModule
0x14000fa1a  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x14000fa1f  mov     ebx, eax
0x14000fa21  test    eax, eax
0x14000fa23  jns     short loc_14000FA33
0x14000fa25  lea     rcx, [rbp+57h+psz]
0x14000fa29  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000fa2e  jmp     loc_14000FCB6
0x14000fa33  mov     rbx, [rbp+57h+psz]
0x14000fa37  test    rbx, rbx
0x14000fa3a  jz      short loc_14000FA5D
0x14000fa3c  xor     ecx, ecx; bstrString
0x14000fa3e  call    cs:__imp_SysFreeString
0x14000fa44  mov     rcx, rbx; psz
0x14000fa47  call    cs:__imp_SysAllocString
0x14000fa4d  mov     rdi, rax
0x14000fa50  mov     [rbp+57h+var_60], rax
0x14000fa54  test    rax, rax
0x14000fa57  jz      loc_14000FCE6
0x14000fa5d  lea     rcx, [rbp+57h+psz]
0x14000fa61  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000fa66  mov     [rbp+57h+var_80], 0
0x14000fa6e  lea     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x14000fa72  mov     rcx, rdi; this
0x14000fa75  call    ?DetermineVsInstanceRoot@DiagHubCommon@@YAJPEBGPEAPEAG@Z; DiagHubCommon::DetermineVsInstanceRoot(ushort const *,ushort * *)
0x14000fa7a  mov     ebx, eax
0x14000fa7c  test    eax, eax
0x14000fa7e  js      loc_14000FCAB
0x14000fa84  lea     r12, CriticalSection
0x14000fa8b  mov     [rbp+57h+var_58], r12
0x14000fa8f  mov     rcx, r12; lpCriticalSection
0x14000fa92  call    cs:__imp_EnterCriticalSection
0x14000fa98  nop
0x14000fa99  lea     rdx, [rbp+57h+var_80]
0x14000fa9d  call    ??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z; std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)
0x14000faa2  mov     r9, rax
0x14000faa5  lea     r8, [rbp+57h+var_80]
0x14000faa9  lea     rdx, [rbp+57h+bstrString]
0x14000faad  call    ??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@VCComBSTR@ATL@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z; std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)
0x14000fab2  mov     rcx, [rax+8]
0x14000fab6  mov     rax, cs:qword_140024A98
0x14000fabd  test    rcx, rcx
0x14000fac0  cmovnz  rax, rcx
0x14000fac4  cmp     rax, cs:qword_140024A98
0x14000facb  jnz     loc_14000FB6F
0x14000fad1  mov     [rbp+57h+var_78], 0
0x14000fad9  lea     rdx, [rbp+57h+var_78]
0x14000fadd  mov     rcx, [rbp+57h+var_80]
0x14000fae1  call    ?RegisterStandardCollectorProxyStubs@DiagHubCommon@@YAJPEBGAEAV?$unique_ptr@VComProxyRegistration@DiagHubCommon@@U?$default_delete@VComProxyRegistration@DiagHubCommon@@@std@@@std@@@Z; DiagHubCommon::RegisterStandardCollectorProxyStubs(ushort const *,std::unique_ptr<DiagHubCommon::ComProxyRegistration> &)
0x14000fae6  mov     ebx, eax
0x14000fae8  test    eax, eax
0x14000faea  jns     short loc_14000FB15
0x14000faec  mov     rcx, [rbp+57h+var_78]
0x14000faf0  test    rcx, rcx
0x14000faf3  jz      short loc_14000FB07
0x14000faf5  mov     rax, [rcx]
0x14000faf8  mov     edx, 1
0x14000fafd  mov     rax, [rax]
0x14000fb00  call    cs:__guard_dispatch_icall_fptr
0x14000fb06  nop
0x14000fb07  mov     rcx, r12; lpCriticalSection
0x14000fb0a  call    cs:__imp_LeaveCriticalSection
0x14000fb10  jmp     loc_14000FCAB
0x14000fb15  mov     rbx, [rbp+57h+var_78]
0x14000fb19  mov     rax, [rbx]
0x14000fb1c  mov     rcx, rbx
0x14000fb1f  mov     rax, [rax+8]
0x14000fb23  call    cs:__guard_dispatch_icall_fptr
0x14000fb29  cmp     [rbp+57h+var_80], 0
0x14000fb2e  jnz     loc_14000FBE6
0x14000fb34  mov     [rbp+57h+bstrString], 0
0x14000fb3c  lea     r8, [rbp+57h+bstrString]
0x14000fb40  lea     rdx, [rbp+57h+psz]
0x14000fb44  call    ?insert@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VCComBSTR@ATL@@@std@@@std@@@std@@_N@2@$$QEAVCComBSTR@ATL@@@Z; std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::insert(ATL::CComBSTR &&)
0x14000fb49  nop
0x14000fb4a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14000fb4e  call    cs:__imp_SysFreeString
0x14000fb54  nop
0x14000fb55  test    rbx, rbx
0x14000fb58  jz      short loc_14000FB6F
0x14000fb5a  mov     rax, [rbx]
0x14000fb5d  mov     edx, 1
0x14000fb62  mov     rcx, rbx
0x14000fb65  mov     rax, [rax]
0x14000fb68  call    cs:__guard_dispatch_icall_fptr
0x14000fb6e  nop
0x14000fb6f  mov     rcx, r12; lpCriticalSection
0x14000fb72  call    cs:__imp_LeaveCriticalSection
0x14000fb78  mov     [rbp+57h+var_50], 0
0x14000fb80  lea     rax, [rbp+57h+var_50]
0x14000fb84  mov     [rsp+0B0h+ppv], rax; ppv
0x14000fb89  lea     r9, _GUID_d2020dea_eb40_45d5_b420_b9fb623c4fd1; riid
0x14000fb90  xor     edx, edx; pUnkOuter
0x14000fb92  lea     r8d, [rdx+4]; dwClsContext
0x14000fb96  lea     rcx, _GUID_f2dc0f57_0b99_49e3_be80_936dbaa54ee0; rclsid
0x14000fb9d  call    cs:__imp_CoCreateInstance
0x14000fba3  mov     ebx, eax
0x14000fba5  test    eax, eax
0x14000fba7  js      loc_14000FC94
0x14000fbad  mov     r9, [rbp+57h+var_50]
0x14000fbb1  xor     ecx, ecx
0x14000fbb3  mov     [rbp+57h+var_48], rcx
0x14000fbb7  test    r9, r9
0x14000fbba  jz      short loc_14000FC06
0x14000fbbc  mov     rax, [r9]
0x14000fbbf  lea     r8, [rbp+57h+var_48]
0x14000fbc3  lea     rdx, _GUID_722e9581_5247_4066_9eda_5d4e36a13de9
0x14000fbca  mov     rcx, r9
0x14000fbcd  mov     rax, [rax]
0x14000fbd0  call    cs:__guard_dispatch_icall_fptr
0x14000fbd6  mov     r9, [rbp+57h+var_50]
0x14000fbda  test    eax, eax
0x14000fbdc  jns     short loc_14000FC02
0x14000fbde  xor     ecx, ecx
0x14000fbe0  mov     [rbp+57h+var_48], rcx
0x14000fbe4  jmp     short loc_14000FC06
0x14000fbe6  mov     rcx, [rbp+57h+var_80]; psz
0x14000fbea  call    cs:__imp_SysAllocString
0x14000fbf0  mov     [rbp+57h+bstrString], rax
0x14000fbf4  test    rax, rax
0x14000fbf7  jz      loc_14000FCF1
0x14000fbfd  jmp     loc_14000FB3C
0x14000fc02  mov     rcx, [rbp+57h+var_48]
0x14000fc06  test    rcx, rcx
0x14000fc09  jz      short loc_14000FC24
0x14000fc0b  mov     rax, [rcx]
0x14000fc0e  xor     edx, edx
0x14000fc10  mov     rax, [rax+18h]
0x14000fc14  call    cs:__guard_dispatch_icall_fptr
0x14000fc1a  mov     ebx, eax
0x14000fc1c  test    eax, eax
0x14000fc1e  js      short loc_14000FC7D
0x14000fc20  mov     r9, [rbp+57h+var_50]
0x14000fc24  mov     [rbp+57h+var_40], 0
0x14000fc2c  mov     rax, [r9]
0x14000fc2f  lea     r8, [rbp+57h+var_40]
0x14000fc33  mov     rdx, [rbp+57h+var_80]
0x14000fc37  mov     rcx, r9
0x14000fc3a  mov     rax, [rax+18h]
0x14000fc3e  call    cs:__guard_dispatch_icall_fptr
0x14000fc44  mov     ebx, eax
0x14000fc46  test    eax, eax
0x14000fc48  js      short loc_14000FC66
0x14000fc4a  mov     rcx, [rbp+57h+var_40]
0x14000fc4e  mov     rax, [rcx]
0x14000fc51  mov     r8, r14
0x14000fc54  lea     rdx, _GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44
0x14000fc5b  mov     rax, [rax]
0x14000fc5e  call    cs:__guard_dispatch_icall_fptr
0x14000fc64  mov     ebx, eax
0x14000fc66  mov     rcx, [rbp+57h+var_40]
0x14000fc6a  test    rcx, rcx
0x14000fc6d  jz      short loc_14000FC7D
0x14000fc6f  mov     rdx, [rcx]
0x14000fc72  mov     rax, [rdx+10h]
0x14000fc76  call    cs:__guard_dispatch_icall_fptr
0x14000fc7c  nop
0x14000fc7d  mov     rcx, [rbp+57h+var_48]
0x14000fc81  test    rcx, rcx
0x14000fc84  jz      short loc_14000FC94
0x14000fc86  mov     rax, [rcx]
0x14000fc89  mov     rax, [rax+10h]
0x14000fc8d  call    cs:__guard_dispatch_icall_fptr
0x14000fc93  nop
0x14000fc94  mov     rcx, [rbp+57h+var_50]
0x14000fc98  test    rcx, rcx
0x14000fc9b  jz      short loc_14000FCAB
0x14000fc9d  mov     rax, [rcx]
0x14000fca0  mov     rax, [rax+10h]
0x14000fca4  call    cs:__guard_dispatch_icall_fptr
0x14000fcaa  nop
0x14000fcab  mov     rcx, [rbp+57h+var_80]; bstrString
0x14000fcaf  call    cs:__imp_SysFreeString
0x14000fcb5  nop
0x14000fcb6  mov     rcx, rdi; bstrString
0x14000fcb9  call    cs:__imp_SysFreeString
0x14000fcbf  mov     eax, ebx
0x14000fcc1  mov     rcx, [rbp+57h+var_20]
0x14000fcc5  xor     rcx, rsp; StackCookie
0x14000fcc8  call    __security_check_cookie
0x14000fccd  lea     r11, [rsp+0B0h+var_10]
0x14000fcd5  mov     rbx, [r11+20h]
0x14000fcd9  mov     rdi, [r11+28h]
0x14000fcdd  mov     rsp, r11
0x14000fce0  pop     r14
0x14000fce2  pop     r12
0x14000fce4  pop     rbp
0x14000fce5  retn
0x14000fce6  mov     ecx, 8007000Eh; int
0x14000fceb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000fcf1  mov     ecx, 8007000Eh; int
0x14000fcf6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
