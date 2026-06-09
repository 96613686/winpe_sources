# ApplicationSpecificEndpointInfo::SetPersistedDefaultAudioEndpoint(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,ushort const *)

- ea: `0x1800470a0`
- end: `0x1800473a8`
- name: `?SetPersistedDefaultAudioEndpoint@ApplicationSpecificEndpointInfo@@UEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@PEBG@Z`
- size: `776`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001c74`
- `0x18000a384`
- `0x18000e37c`
- `0x18000e6a4`
- `0x180012844`
- `0x1800232a0`
- `0x180031960`
- `0x180046b28`
- `0x180046fb4`
- `0x1800470a0`
- `0x1800473b0`
- `0x1800474bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004723d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800472d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004723d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800472d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004729f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004736e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047380`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004729f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004736e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047380`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047321`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004732e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180047321`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004732e`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x1800471cc`
- `MMDevAPI!__imp_mmdDevGetMMDeviceFromInterfaceId` at `0x1800471cc`
- `RPCRT4!RpcRevertToSelf` at `0x180047141`
- `RPCRT4!RpcRevertToSelf` at `0x180047291`
- `RPCRT4!RpcRevertToSelf` at `0x1800472df`
- `RPCRT4!RpcRevertToSelf` at `0x180047360`
- `RPCRT4!RpcRevertToSelf` at `0x180047141`
- `RPCRT4!RpcRevertToSelf` at `0x180047291`
- `RPCRT4!RpcRevertToSelf` at `0x1800472df`
- `RPCRT4!RpcRevertToSelf` at `0x180047360`
- `RPCRT4!RpcImpersonateClient` at `0x1800470dd`
- `RPCRT4!RpcImpersonateClient` at `0x1800470dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationSpecificEndpointInfo::SetPersistedDefaultAudioEndpoint(
        ApplicationSpecificEndpointInfo *a1,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  unsigned int v8; // eax
  int AppKey; // ebx
  __int64 v11; // rdx
  int PersistentId; // eax
  ApplicationSpecificEndpointInfo *v13; // rcx
  void *v14; // rdi
  HKEY v15; // rbx
  ApplicationSpecificEndpointInfo *v16; // rcx
  int v17; // esi
  __int64 v18; // rdx
  int updated; // eax
  unsigned int v20; // edi
  int refreshed; // eax
  int v22; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+30h] [rbp-39h] BYREF
  struct IMMDevice *v24; // [rsp+38h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  WCHAR ValueName[12]; // [rsp+48h] [rbp-21h] BYREF
  WCHAR v27[12]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  hKey = 0;
  v8 = RpcImpersonateClient(0);
  if ( v8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x71,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
             (const char *)v8,
             v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  AppKey = ApplicationSpecificEndpointInfo::GetAppKey(a1, 0x2001Fu, 1, &hKey);
  if ( AppKey < 0 )
  {
    v11 = 117;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)(unsigned int)AppKey,
      v22);
LABEL_6:
    RpcRevertToSelf();
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)AppKey;
  }
  v22 = a2;
  AppKey = StringCbPrintfW(ValueName, 0x14u, L"%03d_%03d", a3);
  if ( AppKey < 0 )
  {
    v11 = 121;
    goto LABEL_5;
  }
  v22 = a2;
  AppKey = StringCbPrintfW(v27, 0x18u, L"%03d_%03d_p", a3);
  if ( AppKey < 0 )
  {
    v11 = 128;
    goto LABEL_5;
  }
  if ( a4 )
  {
    v24 = 0;
    if ( (int)mmdDevGetMMDeviceFromInterfaceId(a4, &v24) < 0 )
    {
      AppKey = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)0x80070057LL,
        a2);
LABEL_16:
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
      goto LABEL_6;
    }
    pv = 0;
    PersistentId = ApplicationSpecificEndpointInfo::GetPersistentId(v24, (unsigned __int16 **)&pv);
    AppKey = PersistentId;
    if ( PersistentId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)(unsigned int)PersistentId,
        a2);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_16;
    }
    v14 = pv;
    v15 = hKey;
    v17 = ApplicationSpecificEndpointInfo::WritePersistedEndpoint(v13, hKey, v27, (const unsigned __int16 *)pv);
    if ( v17 < 0 )
    {
      v18 = 143;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)(unsigned int)v17,
        a2);
      if ( v14 )
        CoTaskMemFree(v14);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
      RpcRevertToSelf();
      if ( v15 )
        RegCloseKey(v15);
      return (unsigned int)v17;
    }
    v17 = ApplicationSpecificEndpointInfo::WritePersistedEndpoint(v16, v15, ValueName, a4);
    if ( v17 < 0 )
    {
      v18 = 146;
      goto LABEL_22;
    }
    if ( v14 )
      CoTaskMemFree(v14);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v24);
  }
  else
  {
    v15 = hKey;
    RegDeleteValueW(hKey, ValueName);
    RegDeleteValueW(v15, v27);
    refreshed = ApplicationSpecificEndpointInfo::SendRefreshEndpointNotification(a1, a2, a3);
    v20 = refreshed;
    if ( refreshed < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)(unsigned int)refreshed,
        a2);
      RpcRevertToSelf();
      goto LABEL_36;
    }
  }
  RpcRevertToSelf();
  updated = ApplicationSpecificEndpointInfo::UpdateState(a1, a3, a2, a4);
  v20 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)(unsigned int)updated,
      a2);
LABEL_36:
    if ( v15 )
      RegCloseKey(v15);
    return v20;
  }
  if ( v15 )
    RegCloseKey(v15);
  return 0;
}

```

## disassembly

```asm
0x1800470a0  push    rbp
0x1800470a2  push    rbx
0x1800470a3  push    rsi
0x1800470a4  push    rdi
0x1800470a5  push    r12
0x1800470a7  push    r13
0x1800470a9  push    r14
0x1800470ab  push    r15
0x1800470ad  lea     rbp, [rsp-1Fh]
0x1800470b2  sub     rsp, 88h
0x1800470b9  mov     rax, cs:__security_cookie
0x1800470c0  xor     rax, rsp
0x1800470c3  mov     [rbp+57h+var_48], rax
0x1800470c7  mov     r14, r9
0x1800470ca  mov     r12d, r8d
0x1800470cd  mov     r15d, edx
0x1800470d0  mov     r13, rcx
0x1800470d3  mov     [rbp+57h+hKey], 0
0x1800470db  xor     ecx, ecx; BindingHandle
0x1800470dd  call    cs:__imp_RpcImpersonateClient
0x1800470e3  test    eax, eax
0x1800470e5  jz      short loc_180047104
0x1800470e7  mov     rcx, [rbp+5Fh]; this
0x1800470eb  mov     r9d, eax; char *
0x1800470ee  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x1800470f5  mov     edx, 71h ; 'q'; void *
0x1800470fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800470ff  jmp     loc_180047388
0x180047104  xor     edx, edx
0x180047106  lea     rcx, [rbp+57h+hKey]
0x18004710a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004710f  lea     r9, [rbp+57h+hKey]; HKEY *
0x180047113  mov     r8b, 1; bool
0x180047116  mov     edx, 2001Fh; unsigned int
0x18004711b  mov     rcx, r13; this
0x18004711e  call    ?GetAppKey@ApplicationSpecificEndpointInfo@@AEAAJK_NPEAPEAUHKEY__@@@Z; ApplicationSpecificEndpointInfo::GetAppKey(ulong,bool,HKEY__ * *)
0x180047123  mov     ebx, eax
0x180047125  test    eax, eax
0x180047127  jns     short loc_18004715D
0x180047129  mov     edx, 75h ; 'u'; void *
0x18004712e  mov     rcx, [rbp+5Fh]; this
0x180047132  mov     r9d, ebx; char *
0x180047135  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18004713c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047141  call    cs:__imp_RpcRevertToSelf
0x180047147  mov     rcx, [rbp+57h+hKey]; hKey
0x18004714b  test    rcx, rcx
0x18004714e  jz      short loc_180047156
0x180047150  call    cs:__imp_RegCloseKey
0x180047156  mov     eax, ebx
0x180047158  jmp     loc_180047388
0x18004715d  mov     [rsp+0C0h+var_A0], r15d
0x180047162  mov     r9d, r12d
0x180047165  lea     r8, a03d03d; "%03d_%03d"
0x18004716c  mov     edx, 14h; unsigned __int64
0x180047171  lea     rcx, [rbp+57h+ValueName]; unsigned __int16 *
0x180047175  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004717a  mov     ebx, eax
0x18004717c  test    eax, eax
0x18004717e  jns     short loc_180047187
0x180047180  mov     edx, 79h ; 'y'
0x180047185  jmp     short loc_18004712E
0x180047187  mov     [rsp+0C0h+var_A0], r15d; int
0x18004718c  mov     r9d, r12d
0x18004718f  lea     r8, a03d03dP; "%03d_%03d_p"
0x180047196  mov     edx, 18h; unsigned __int64
0x18004719b  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004719f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800471a4  mov     ebx, eax
0x1800471a6  test    eax, eax
0x1800471a8  jns     short loc_1800471B4
0x1800471aa  mov     edx, 80h
0x1800471af  jmp     loc_18004712E
0x1800471b4  test    r14, r14
0x1800471b7  jz      loc_180047316
0x1800471bd  mov     [rbp+57h+var_88], 0
0x1800471c5  lea     rdx, [rbp+57h+var_88]
0x1800471c9  mov     rcx, r14
0x1800471cc  call    cs:__imp_mmdDevGetMMDeviceFromInterfaceId
0x1800471d2  test    eax, eax
0x1800471d4  jns     short loc_180047201
0x1800471d6  mov     rcx, [rbp+5Fh]; this
0x1800471da  mov     ebx, 80070057h
0x1800471df  mov     r9d, ebx; char *
0x1800471e2  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x1800471e9  mov     edx, 89h; void *
0x1800471ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800471f3  lea     rcx, [rbp+57h+var_88]
0x1800471f7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800471fc  jmp     loc_180047141
0x180047201  mov     [rbp+57h+pv], 0
0x180047209  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18004720d  mov     rcx, [rbp+57h+var_88]; struct IMMDevice *
0x180047211  call    ?GetPersistentId@ApplicationSpecificEndpointInfo@@CAJPEAUIMMDevice@@PEAPEAG@Z; ApplicationSpecificEndpointInfo::GetPersistentId(IMMDevice *,ushort * *)
0x180047216  mov     ebx, eax
0x180047218  test    eax, eax
0x18004721a  jns     short loc_180047245
0x18004721c  mov     rcx, [rbp+5Fh]; this
0x180047220  mov     r9d, eax; char *
0x180047223  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18004722a  mov     edx, 8Eh; void *
0x18004722f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047234  mov     rcx, [rbp+57h+pv]; pv
0x180047238  test    rcx, rcx
0x18004723b  jz      short loc_1800471F3
0x18004723d  call    cs:__imp_CoTaskMemFree
0x180047243  jmp     short loc_1800471F3
0x180047245  mov     rdi, [rbp+57h+pv]
0x180047249  mov     r9, rdi; unsigned __int16 *
0x18004724c  lea     r8, [rbp+57h+var_60]; unsigned __int16 *
0x180047250  mov     rbx, [rbp+57h+hKey]
0x180047254  mov     rdx, rbx; HKEY
0x180047257  call    ?WritePersistedEndpoint@ApplicationSpecificEndpointInfo@@AEAAJPEAUHKEY__@@PEBG1@Z; ApplicationSpecificEndpointInfo::WritePersistedEndpoint(HKEY__ *,ushort const *,ushort const *)
0x18004725c  mov     esi, eax
0x18004725e  test    eax, eax
0x180047260  jns     short loc_1800472AC
0x180047262  mov     edx, 8Fh; void *
0x180047267  mov     r9d, esi; char *
0x18004726a  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180047271  mov     rcx, [rbp+5Fh]; this
0x180047275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004727a  test    rdi, rdi
0x18004727d  jz      short loc_180047288
0x18004727f  mov     rcx, rdi; pv
0x180047282  call    cs:__imp_CoTaskMemFree
0x180047288  lea     rcx, [rbp+57h+var_88]
0x18004728c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180047291  call    cs:__imp_RpcRevertToSelf
0x180047297  test    rbx, rbx
0x18004729a  jz      short loc_1800472A5
0x18004729c  mov     rcx, rbx; hKey
0x18004729f  call    cs:__imp_RegCloseKey
0x1800472a5  mov     eax, esi
0x1800472a7  jmp     loc_180047388
0x1800472ac  mov     r9, r14; unsigned __int16 *
0x1800472af  lea     r8, [rbp+57h+ValueName]; unsigned __int16 *
0x1800472b3  mov     rdx, rbx; HKEY
0x1800472b6  call    ?WritePersistedEndpoint@ApplicationSpecificEndpointInfo@@AEAAJPEAUHKEY__@@PEBG1@Z; ApplicationSpecificEndpointInfo::WritePersistedEndpoint(HKEY__ *,ushort const *,ushort const *)
0x1800472bb  mov     esi, eax
0x1800472bd  test    eax, eax
0x1800472bf  jns     short loc_1800472C8
0x1800472c1  mov     edx, 92h
0x1800472c6  jmp     short loc_180047267
0x1800472c8  test    rdi, rdi
0x1800472cb  jz      short loc_1800472D6
0x1800472cd  mov     rcx, rdi; pv
0x1800472d0  call    cs:__imp_CoTaskMemFree
0x1800472d6  lea     rcx, [rbp+57h+var_88]
0x1800472da  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800472df  call    cs:__imp_RpcRevertToSelf
0x1800472e5  mov     r9, r14
0x1800472e8  mov     r8d, r15d
0x1800472eb  mov     edx, r12d
0x1800472ee  mov     rcx, r13
0x1800472f1  call    ?UpdateState@ApplicationSpecificEndpointInfo@@AEAAJW4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEBG@Z; ApplicationSpecificEndpointInfo::UpdateState(__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,ushort const *)
0x1800472f6  mov     edi, eax
0x1800472f8  test    eax, eax
0x1800472fa  jns     short loc_180047378
0x1800472fc  mov     rcx, [rbp+5Fh]; this
0x180047300  mov     r9d, eax; char *
0x180047303  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18004730a  mov     edx, 0A2h; void *
0x18004730f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047314  jmp     short loc_180047366
0x180047316  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18004731a  mov     rbx, [rbp+57h+hKey]
0x18004731e  mov     rcx, rbx; hKey
0x180047321  call    cs:__imp_RegDeleteValueW
0x180047327  lea     rdx, [rbp+57h+var_60]; lpValueName
0x18004732b  mov     rcx, rbx; hKey
0x18004732e  call    cs:__imp_RegDeleteValueW
0x180047334  mov     r8d, r12d
0x180047337  mov     edx, r15d
0x18004733a  mov     rcx, r13
0x18004733d  call    ?SendRefreshEndpointNotification@ApplicationSpecificEndpointInfo@@AEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@@Z; ApplicationSpecificEndpointInfo::SendRefreshEndpointNotification(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001)
0x180047342  mov     edi, eax
0x180047344  test    eax, eax
0x180047346  jns     short loc_1800472DF
0x180047348  mov     rcx, [rbp+5Fh]; this
0x18004734c  mov     r9d, eax; char *
0x18004734f  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180047356  mov     edx, 9Bh; void *
0x18004735b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047360  call    cs:__imp_RpcRevertToSelf
0x180047366  test    rbx, rbx
0x180047369  jz      short loc_180047374
0x18004736b  mov     rcx, rbx; hKey
0x18004736e  call    cs:__imp_RegCloseKey
0x180047374  mov     eax, edi
0x180047376  jmp     short loc_180047388
0x180047378  test    rbx, rbx
0x18004737b  jz      short loc_180047386
0x18004737d  mov     rcx, rbx; hKey
0x180047380  call    cs:__imp_RegCloseKey
0x180047386  xor     eax, eax
0x180047388  mov     rcx, [rbp+57h+var_48]
0x18004738c  xor     rcx, rsp; StackCookie
0x18004738f  call    __security_check_cookie
0x180047394  add     rsp, 88h
0x18004739b  pop     r15
0x18004739d  pop     r14
0x18004739f  pop     r13
0x1800473a1  pop     r12
0x1800473a3  pop     rdi
0x1800473a4  pop     rsi
0x1800473a5  pop     rbx
0x1800473a6  pop     rbp
0x1800473a7  retn
```
