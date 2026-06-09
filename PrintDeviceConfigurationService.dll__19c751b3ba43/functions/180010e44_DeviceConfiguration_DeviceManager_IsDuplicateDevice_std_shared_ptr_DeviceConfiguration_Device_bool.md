# DeviceConfiguration::DeviceManager::_IsDuplicateDevice(std::shared_ptr<DeviceConfiguration::Device>,bool *)

- ea: `0x180010e44`
- end: `0x18001116d`
- name: `?_IsDuplicateDevice@DeviceManager@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@PEA_N@Z`
- size: `809`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _BYTE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010b10`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000af54`
- `0x18000d89c`
- `0x18000e03c`
- `0x18000e0e8`
- `0x18000e628`
- `0x18000e66c`
- `0x18000ea68`
- `0x18000f48c`
- `0x180010e44`
- `0x180011510`
- `0x1800115a0`
- `0x180011664`
- `0x18001467c`
- `0x1800146a0`
- `0x1800146c4`
- `0x180016284`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180010f3c`
- `WINSPOOL!OpenPrinterW` at `0x180010f3c`

## string_xrefs

- `0x180010fac`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`
- `0x180011090`: `DeviceConfiguration::DeviceManager::_IsPrinterAttachedToPort`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::_IsDuplicateDevice(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  __int64 v5; // rbx
  __int64 PrinterName; // rbx
  __int64 UserSid; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  WCHAR *v10; // rcx
  const char *v11; // r9
  unsigned int v12; // eax
  const wchar_t *v13; // rbx
  std::_Ref_count_base *v14; // rcx
  __int64 result; // rax
  std::_Ref_count_base *v16; // rcx
  const char *v17; // [rsp+28h] [rbp-100h]
  HANDLE phPrinter; // [rsp+38h] [rbp-F0h] BYREF
  int v19; // [rsp+40h] [rbp-E8h]
  const wchar_t *v20; // [rsp+48h] [rbp-E0h]
  _QWORD *v21; // [rsp+50h] [rbp-D8h]
  LPWSTR pPrinterName[4]; // [rsp+58h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+88h] [rbp-A0h]
  _BYTE v25[32]; // [rsp+98h] [rbp-90h] BYREF
  _BYTE v26[32]; // [rsp+B8h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  try
  {
    v21 = a2;
    LODWORD(phPrinter) = 0;
    *a3 = 0;
    v5 = *(_QWORD *)(DeviceConfiguration::Device::GetUserSid(*a2, v25) + 16);
    std::wstring::_Tidy_deallocate(v25);
    if ( v5 )
    {
      phPrinter = 0;
      PrinterName = DeviceConfiguration::Device::GetPrinterName(*a2, &v23);
      UserSid = DeviceConfiguration::Device::GetUserSid(*a2, v26);
      v8 = std::operator+<unsigned short>(v25, UserSid);
      std::wstring::wstring(pPrinterName, v9, v8, PrinterName);
      std::wstring::_Tidy_deallocate(v25);
      std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(&v23);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &phPrinter,
        0);
      v10 = (WCHAR *)pPrinterName;
      if ( pPrinterName[3] > (LPWSTR)7 )
        v10 = pPrinterName[0];
      if ( OpenPrinterW(v10, &phPrinter, 0) )
        *a3 = 1;
      std::wstring::_Tidy_deallocate(pPrinterName);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
    }
    else
    {
      v19 = 0;
      v23 = 0;
      v24 = 0;
      v12 = DeviceConfiguration::EnumeratePrinters(0x2000002u);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x27C,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
        (const char *)v12,
        (int)"EnumeratePrinters failed!",
        v17);
      v13 = L"Microsoft IPP Class Driver";
      if ( *(_DWORD *)(*a2 + 248LL) )
        v13 = L"Universal Print Class Driver";
      v20 = v13;
      std::vector<unsigned char>::_Tidy(&v23);
    }
    v14 = (std::_Ref_count_base *)a2[1];
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(phPrinter) = wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x28C,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
                           v11);
    v16 = (std::_Ref_count_base *)v21[1];
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    return (unsigned int)phPrinter;
  }
  return result;
}

```

## disassembly

```asm
0x180010e44  mov     [rsp+arg_0], rbx
0x180010e49  push    rsi
0x180010e4a  push    r12
0x180010e4c  push    r13
0x180010e4e  push    r14
0x180010e50  push    r15
0x180010e52  sub     rsp, 100h
0x180010e59  mov     rax, cs:__security_cookie
0x180010e60  xor     rax, rsp
0x180010e63  mov     [rsp+128h+var_30], rax
0x180010e6b  mov     r15, r8
0x180010e6e  mov     r14, rdx
0x180010e71  mov     [rsp+128h+var_D8], rdx
0x180010e76  xor     esi, esi
0x180010e78  mov     dword ptr [rsp+128h+phPrinter], esi
0x180010e7c  mov     [r8], sil
0x180010e7f  lea     rdx, [rsp+128h+var_90]
0x180010e87  mov     rcx, [r14]
0x180010e8a  call    ?GetUserSid@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetUserSid(void)
0x180010e8f  mov     rbx, [rax+10h]
0x180010e93  lea     rcx, [rsp+128h+var_90]
0x180010e9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010ea0  test    rbx, rbx
0x180010ea3  jz      loc_180010F64
0x180010ea9  mov     [rsp+128h+phPrinter], rsi
0x180010eae  lea     rdx, [rsp+128h+var_B0]
0x180010eb3  mov     rcx, [r14]
0x180010eb6  call    ?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPrinterName(void)
0x180010ebb  mov     rbx, rax
0x180010ebe  lea     rdx, [rsp+128h+var_70]
0x180010ec6  mov     rcx, [r14]
0x180010ec9  call    ?GetUserSid@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetUserSid(void)
0x180010ece  nop
0x180010ecf  mov     rdx, rax
0x180010ed2  lea     rcx, [rsp+128h+var_90]
0x180010eda  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180010edf  nop
0x180010ee0  mov     r9, rbx
0x180010ee3  mov     r8, rax
0x180010ee6  lea     rcx, [rsp+128h+pPrinterName]
0x180010eeb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180010ef0  nop
0x180010ef1  lea     rcx, [rsp+128h+var_90]
0x180010ef9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010efe  nop
0x180010eff  lea     rcx, [rsp+128h+var_70]
0x180010f07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010f0c  nop
0x180010f0d  lea     rcx, [rsp+128h+var_B0]
0x180010f12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010f17  xor     edx, edx
0x180010f19  lea     rcx, [rsp+128h+phPrinter]
0x180010f1e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180010f23  lea     rcx, [rsp+128h+pPrinterName]
0x180010f28  cmp     [rsp+128h+var_B8], 7
0x180010f2e  cmova   rcx, [rsp+128h+pPrinterName]; pPrinterName
0x180010f34  xor     r8d, r8d; pDefault
0x180010f37  lea     rdx, [rsp+128h+phPrinter]; phPrinter
0x180010f3c  call    cs:__imp_OpenPrinterW
0x180010f42  test    eax, eax
0x180010f44  jz      short loc_180010F4A
0x180010f46  mov     byte ptr [r15], 1
0x180010f4a  lea     rcx, [rsp+128h+pPrinterName]
0x180010f4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010f54  nop
0x180010f55  lea     rcx, [rsp+128h+phPrinter]
0x180010f5a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010f5f  jmp     loc_180011105
0x180010f64  mov     [rsp+128h+var_E8], 0
0x180010f6c  xorps   xmm0, xmm0
0x180010f6f  movdqu  [rsp+128h+var_B0], xmm0
0x180010f75  mov     [rsp+128h+var_A0], 0
0x180010f81  lea     r9, [rsp+128h+var_B0]
0x180010f86  lea     r8, [rsp+128h+var_E8]
0x180010f8b  mov     ecx, 2000002h; Flags
0x180010f90  call    ?EnumeratePrinters@DeviceConfiguration@@YAJKKPEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; DeviceConfiguration::EnumeratePrinters(ulong,ulong,ulong *,std::vector<uchar> &)
0x180010f95  mov     rcx, [rsp+128h]; this
0x180010f9d  lea     rdx, aEnumerateprint; "EnumeratePrinters failed!"
0x180010fa4  mov     qword ptr [rsp+128h+var_108], rdx; int
0x180010fa9  mov     r9d, eax; char *
0x180010fac  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x180010fb3  mov     edx, 27Ch; void *
0x180010fb8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010fbd  mov     rax, [r14]
0x180010fc0  lea     rcx, aUniversalPrint; "Universal Print Class Driver"
0x180010fc7  lea     rbx, aMicrosoftIppCl; "Microsoft IPP Class Driver"
0x180010fce  cmp     dword ptr [rax+0F8h], 0
0x180010fd5  cmovnz  rbx, rcx
0x180010fd9  mov     [rsp+128h+var_E0], rbx
0x180010fde  mov     r13, qword ptr [rsp+128h+var_B0]
0x180010fe3  xor     r12d, r12d
0x180010fe6  cmp     r12d, [rsp+128h+var_E8]
0x180010feb  jnb     loc_1800110FA
0x180010ff1  mov     rdx, [r13+20h]
0x180010ff5  lea     rcx, [rsp+128h+var_90]
0x180010ffd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011002  nop
0x180011003  or      esi, 1
0x180011006  mov     dword ptr [rsp+128h+phPrinter], esi
0x18001100a  mov     rdx, rbx
0x18001100d  lea     rcx, [rsp+128h+var_70]
0x180011015  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001101a  nop
0x18001101b  or      esi, 2
0x18001101e  mov     dword ptr [rsp+128h+phPrinter], esi
0x180011022  lea     rdx, [rsp+128h+var_90]
0x18001102a  lea     rcx, [rsp+128h+var_70]
0x180011032  call    ?IEquals@StringHelpers@PrintCore@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IEquals(std::wstring const &,std::wstring const &)
0x180011037  test    al, al
0x180011039  jz      short loc_1800110AC
0x18001103b  lea     rdx, [rsp+128h+var_50]
0x180011043  mov     rcx, [r14]
0x180011046  call    ?GetPortName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPortName(void)
0x18001104b  or      esi, 4
0x18001104e  mov     [rsp+128h+phPrinter], r13
0x180011053  cmp     qword ptr [rax+10h], 0
0x180011058  jz      short loc_1800110AC
0x18001105a  mov     [rsp+128h+var_F8], 0
0x18001105f  lea     rcx, [rsp+128h+phPrinter]
0x180011064  mov     [rsp+128h+pPrinterName], rcx
0x180011069  lea     rcx, [rsp+128h+var_F8]
0x18001106e  mov     [rsp+128h+var_C8], rcx
0x180011073  mov     [rsp+128h+var_C0], rax
0x180011078  lea     rcx, [rsp+128h+pPrinterName]
0x18001107d  call    wil__ResultFromException__lambda_d000f55860b18980f4660ce398d7b6f7___
0x180011082  test    eax, eax
0x180011084  jns     short loc_1800110A0
0x180011086  mov     r8d, eax
0x180011089  lea     rdx, aFailedToWalkAl; "Failed to walk all of the ports! hr: 0x"...
0x180011090  lea     rcx, aDeviceconfigur_12; "DeviceConfiguration::DeviceManager::_Is"...
0x180011097  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001109c  xor     al, al
0x18001109e  jmp     short loc_1800110A4
0x1800110a0  mov     al, [rsp+128h+var_F8]
0x1800110a4  test    al, al
0x1800110a6  jz      short loc_1800110AC
0x1800110a8  mov     bl, 1
0x1800110aa  jmp     short loc_1800110AE
0x1800110ac  xor     bl, bl
0x1800110ae  test    sil, 4
0x1800110b2  jz      short loc_1800110C5
0x1800110b4  and     esi, 0FFFFFFFBh
0x1800110b7  lea     rcx, [rsp+128h+var_50]
0x1800110bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800110c4  nop
0x1800110c5  test    sil, 2
0x1800110c9  jz      short loc_1800110DC
0x1800110cb  and     esi, 0FFFFFFFDh
0x1800110ce  lea     rcx, [rsp+128h+var_70]
0x1800110d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800110db  nop
0x1800110dc  test    sil, 1
0x1800110e0  jz      short loc_1800110F2
0x1800110e2  and     esi, 0FFFFFFFEh
0x1800110e5  lea     rcx, [rsp+128h+var_90]
0x1800110ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800110f2  test    bl, bl
0x1800110f4  jz      short loc_180011157
0x1800110f6  mov     byte ptr [r15], 1
0x1800110fa  lea     rcx, [rsp+128h+var_B0]
0x1800110ff  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180011104  nop
0x180011105  mov     rcx, [r14+8]; this
0x180011109  test    rcx, rcx
0x18001110c  jz      short loc_180011113
0x18001110e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011113  xor     eax, eax
0x180011115  jmp     short loc_18001112E
0x180011117  mov     rax, [rsp+128h+var_D8]
0x18001111c  mov     rcx, [rax+8]; this
0x180011120  test    rcx, rcx
0x180011123  jz      short loc_18001112A
0x180011125  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001112a  mov     eax, dword ptr [rsp+128h+phPrinter]
0x18001112e  mov     rcx, [rsp+128h+var_30]
0x180011136  xor     rcx, rsp; StackCookie
0x180011139  call    __security_check_cookie
0x18001113e  mov     rbx, [rsp+128h+arg_0]
0x180011146  add     rsp, 100h
0x18001114d  pop     r15
0x18001114f  pop     r14
0x180011151  pop     r13
0x180011153  pop     r12
0x180011155  pop     rsi
0x180011156  retn
0x180011157  inc     r12d
0x18001115a  add     r13, 88h
0x180011161  mov     rbx, [rsp+128h+var_E0]
0x180011166  jmp     loc_180010FE6
```
