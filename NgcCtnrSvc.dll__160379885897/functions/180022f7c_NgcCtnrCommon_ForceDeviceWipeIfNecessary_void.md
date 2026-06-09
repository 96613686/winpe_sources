# NgcCtnrCommon::ForceDeviceWipeIfNecessary(void)

- ea: `0x180022f7c`
- end: `0x18002326f`
- name: `?ForceDeviceWipeIfNecessary@NgcCtnrCommon@@YAJXZ`
- size: `755`
- prototype: `__int64 __fastcall(NgcCtnrCommon *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022b70`

## callees

- `0x18000c688`
- `0x180014414`
- `0x180016f14`
- `0x180017820`
- `0x180019c94`
- `0x180022f7c`
- `0x180023278`
- `0x180023430`
- `0x1800234ac`
- `0x180029314`
- `0x180029980`
- `0x18002c640`
- `0x18003b650`
- `0x18003d1f0`
- `0x18005b2ac`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002307c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002307c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fc3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800231b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800231b1`
- `UpdateAPI!ResetDevice` at `0x1800231c7`
- `UpdateAPI!ResetDevice` at `0x1800231c7`

## string_xrefs

- `0x180022ff5`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180022fbc`: `Windows.Internal.PlatformExtensions.Lock`
- `0x180023048`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x1800230a5`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x1800230e6`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x180023127`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x18002319a`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x1800231e0`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x180023075`: `ngcctnrsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NgcCtnrCommon::ForceDeviceWipeIfNecessary(NgcCtnrCommon *this)
{
  HRESULT v1; // eax
  int v2; // edx
  __int64 v3; // r8
  int v4; // eax
  bool *v5; // rdx
  __int64 v6; // rcx
  int IsWipeRequired; // eax
  unsigned int v9; // ebx
  NgcUtils *ModuleHandleW; // rax
  const char *v11; // r9
  unsigned __int16 **v12; // r9
  int v13; // eax
  unsigned __int16 **v14; // r9
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // r14
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64); // rsi
  __int64 v19; // rdi
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // [rsp+20h] [rbp-59h] BYREF
  unsigned int v24[2]; // [rsp+28h] [rbp-51h] BYREF
  unsigned int v25[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v26; // [rsp+38h] [rbp-41h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+80h] [rbp+7h] BYREF
  void **v31; // [rsp+88h] [rbp+Fh] BYREF
  NgcUtils *v32; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v30 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(L"Windows.Internal.PlatformExtensions.Lock", 0x28u, &hstringHeader, &string);
  if ( v1 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v1, v2, v3);
    __debugbreak();
  }
  v4 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(string, 0, v3, &v30);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v4,
      v23);
    v6 = v30;
    goto LABEL_6;
  }
  v6 = v30;
  if ( !v30 )
  {
LABEL_6:
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return 0;
  }
  LOBYTE(v23) = 0;
  IsWipeRequired = NgcUtils::DeviceLockIsWipeRequired((NgcUtils *)&v23, v5);
  v9 = IsWipeRequired;
  if ( IsWipeRequired >= 0 )
  {
    if ( (_BYTE)v23 && (unsigned int)IsResetDevicePresent() )
    {
      ModuleHandleW = (NgcUtils *)GetModuleHandleW(L"ngcctnrsvc.dll");
      v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      v32 = ModuleHandleW;
      if ( !ModuleHandleW )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x142,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
          v11);
      *(_QWORD *)v25 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v25,
        0);
      v13 = NgcUtils::CoMemResourceStringAllocCopy(v32, (HINSTANCE)0x12D, (unsigned int)v25, v12);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x148,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
          (const char *)(unsigned int)v13,
          v23);
      *(_QWORD *)v24 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v24,
        0);
      v15 = NgcUtils::CoMemResourceStringAllocCopy(v32, (HINSTANCE)0x12E, (unsigned int)v24, v14);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
          (const char *)(unsigned int)v15,
          v23);
      v16 = *(_QWORD *)v25;
      if ( *(_QWORD *)v25 && *(_QWORD *)v24 )
      {
        v17 = v30;
        v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v30 + 56LL);
        v26 = *(_QWORD *)v24;
        v19 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v26) + 24);
        v26 = v16;
        v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v29, &v26);
        v21 = v18(v17, *(_QWORD *)(v20 + 24), v19);
        if ( v21 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
            (const char *)(unsigned int)v21,
            v23);
        Sleep(0x2710u);
      }
      v22 = ResetDevice(32, 0x4000);
      v9 = v22;
      if ( v22 >= 0 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v25);
        v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v30);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
        (const char *)(unsigned int)v22,
        v23);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v25);
      v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
      (const char *)(unsigned int)IsWipeRequired,
      v23);
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v30);
  return v9;
}

```

## disassembly

```asm
0x180022f7c  push    rbp
0x180022f7e  push    rbx
0x180022f7f  push    rsi
0x180022f80  push    rdi
0x180022f81  push    r13
0x180022f83  push    r14
0x180022f85  lea     rbp, [rsp-2Fh]
0x180022f8a  sub     rsp, 0A8h
0x180022f91  mov     rax, cs:__security_cookie
0x180022f98  xor     rax, rsp
0x180022f9b  mov     [rbp+57h+var_38], rax
0x180022f9f  mov     [rbp+57h+var_50], 0
0x180022fa7  mov     [rbp+57h+string], 0
0x180022faf  lea     r9, [rbp+57h+string]; string
0x180022fb3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180022fb7  mov     edx, 28h ; '('; length
0x180022fbc  lea     rcx, sourceString; "Windows.Internal.PlatformExtensions.Loc"...
0x180022fc3  call    cs:__imp_WindowsCreateStringReference
0x180022fca  nop     dword ptr [rax+rax+00h]
0x180022fcf  test    eax, eax
0x180022fd1  jns     short loc_180022FDB
0x180022fd3  mov     ecx, eax; this
0x180022fd5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180022fda  int     3; Trap to Debugger
0x180022fdb  xor     edx, edx
0x180022fdd  lea     r9, [rbp+57h+var_50]
0x180022fe1  mov     rcx, [rbp+57h+string]
0x180022fe5  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180022fea  test    eax, eax
0x180022fec  jns     short loc_18002300C
0x180022fee  mov     rcx, [rbp+5Fh]; this
0x180022ff2  mov     r9d, eax; char *
0x180022ff5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180022ffc  mov     edx, 299h; void *
0x180023001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023006  mov     rcx, [rbp+57h+var_50]
0x18002300a  jmp     short loc_180023015
0x18002300c  mov     rcx, [rbp+57h+var_50]
0x180023010  test    rcx, rcx
0x180023013  jnz     short loc_18002302E
0x180023015  test    rcx, rcx
0x180023018  jz      short loc_180023027
0x18002301a  mov     rax, [rcx]
0x18002301d  mov     rax, [rax+10h]
0x180023021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023026  nop
0x180023027  xor     eax, eax
0x180023029  jmp     loc_180023252
0x18002302e  mov     byte ptr [rbp+57h+var_B0], 0
0x180023032  lea     rcx, [rbp+57h+var_B0]; this
0x180023036  call    ?DeviceLockIsWipeRequired@NgcUtils@@YAJPEA_N@Z; NgcUtils::DeviceLockIsWipeRequired(bool *)
0x18002303b  mov     ebx, eax
0x18002303d  test    eax, eax
0x18002303f  jns     short loc_18002305E
0x180023041  mov     rcx, [rbp+5Fh]; this
0x180023045  mov     r9d, eax; char *
0x180023048  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18002304f  mov     edx, 13Ah; void *
0x180023054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023059  jmp     loc_180023247
0x18002305e  cmp     byte ptr [rbp+57h+var_B0], 0
0x180023062  jz      loc_180023245
0x180023068  call    ?IsResetDevicePresent@@YAHXZ; IsResetDevicePresent(void)
0x18002306d  test    eax, eax
0x18002306f  jz      loc_180023245
0x180023075  lea     rcx, aNgcctnrsvcDll_0; "ngcctnrsvc.dll"
0x18002307c  call    cs:__imp_GetModuleHandleW
0x180023083  nop     dword ptr [rax+rax+00h]
0x180023088  lea     r13, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002308f  mov     [rbp+57h+var_48], r13
0x180023093  mov     [rbp+57h+var_40], rax
0x180023097  test    rax, rax
0x18002309a  setz    al
0x18002309d  mov     rcx, [rbp+5Fh]; this
0x1800230a1  test    al, al
0x1800230a3  jz      short loc_1800230B6
0x1800230a5  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x1800230ac  mov     edx, 142h; void *
0x1800230b1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800230b6  mov     qword ptr [rbp+57h+var_A0], 0
0x1800230be  xor     edx, edx
0x1800230c0  lea     rcx, [rbp+57h+var_A0]
0x1800230c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800230c9  lea     r8, [rbp+57h+var_A0]; unsigned int
0x1800230cd  mov     edx, 12Dh; HINSTANCE
0x1800230d2  mov     rcx, [rbp+57h+var_40]; this
0x1800230d6  call    ?CoMemResourceStringAllocCopy@NgcUtils@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; NgcUtils::CoMemResourceStringAllocCopy(HINSTANCE__ *,uint,ushort * *)
0x1800230db  mov     rcx, [rbp+5Fh]; this
0x1800230df  test    eax, eax
0x1800230e1  jns     short loc_1800230F7
0x1800230e3  mov     r9d, eax; char *
0x1800230e6  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x1800230ed  mov     edx, 148h; void *
0x1800230f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800230f7  mov     qword ptr [rbp+57h+var_A8], 0
0x1800230ff  xor     edx, edx
0x180023101  lea     rcx, [rbp+57h+var_A8]
0x180023105  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002310a  lea     r8, [rbp+57h+var_A8]; unsigned int
0x18002310e  mov     edx, 12Eh; HINSTANCE
0x180023113  mov     rcx, [rbp+57h+var_40]; this
0x180023117  call    ?CoMemResourceStringAllocCopy@NgcUtils@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; NgcUtils::CoMemResourceStringAllocCopy(HINSTANCE__ *,uint,ushort * *)
0x18002311c  mov     rcx, [rbp+5Fh]; this
0x180023120  test    eax, eax
0x180023122  jns     short loc_180023138
0x180023124  mov     r9d, eax; char *
0x180023127  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18002312e  mov     edx, 14Eh; void *
0x180023133  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023138  mov     rbx, qword ptr [rbp+57h+var_A0]
0x18002313c  test    rbx, rbx
0x18002313f  jz      short loc_1800231BD
0x180023141  mov     rax, qword ptr [rbp+57h+var_A8]
0x180023145  test    rax, rax
0x180023148  jz      short loc_1800231BD
0x18002314a  mov     r14, [rbp+57h+var_50]
0x18002314e  mov     rcx, [r14]
0x180023151  mov     rsi, [rcx+38h]
0x180023155  mov     [rbp+57h+var_98], rax
0x180023159  lea     rdx, [rbp+57h+var_98]
0x18002315d  lea     rcx, [rbp+57h+hstringHeader]
0x180023161  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180023166  nop
0x180023167  mov     rdi, [rax+18h]
0x18002316b  mov     [rbp+57h+var_98], rbx
0x18002316f  lea     rdx, [rbp+57h+var_98]
0x180023173  lea     rcx, [rbp+57h+var_70]
0x180023177  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18002317c  nop
0x18002317d  mov     r8, rdi
0x180023180  mov     rdx, [rax+18h]
0x180023184  mov     rcx, r14
0x180023187  mov     rax, rsi
0x18002318a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002318f  mov     rcx, [rbp+5Fh]; this
0x180023193  test    eax, eax
0x180023195  jns     short loc_1800231AC
0x180023197  mov     r9d, eax; char *
0x18002319a  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x1800231a1  mov     edx, 154h; void *
0x1800231a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800231ab  nop
0x1800231ac  mov     ecx, 2710h; dwMilliseconds
0x1800231b1  call    cs:__imp_Sleep
0x1800231b8  nop     dword ptr [rax+rax+00h]
0x1800231bd  mov     edx, 4000h
0x1800231c2  mov     ecx, 20h ; ' '
0x1800231c7  call    cs:__imp_ResetDevice
0x1800231ce  nop     dword ptr [rax+rax+00h]
0x1800231d3  mov     ebx, eax
0x1800231d5  test    eax, eax
0x1800231d7  jns     short loc_180023215
0x1800231d9  mov     rcx, [rbp+5Fh]; this
0x1800231dd  mov     r9d, eax; char *
0x1800231e0  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x1800231e7  mov     edx, 159h; void *
0x1800231ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800231f1  nop
0x1800231f2  lea     rcx, [rbp+57h+var_A8]
0x1800231f6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800231fb  nop
0x1800231fc  lea     rcx, [rbp+57h+var_A0]
0x180023200  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180023205  nop
0x180023206  mov     [rbp+57h+var_48], r13
0x18002320a  lea     rcx, [rbp+57h+var_48]
0x18002320e  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180023213  jmp     short loc_180023247
0x180023215  lea     rcx, [rbp+57h+var_A8]
0x180023219  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002321e  nop
0x18002321f  lea     rcx, [rbp+57h+var_A0]
0x180023223  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180023228  nop
0x180023229  mov     [rbp+57h+var_48], r13
0x18002322d  lea     rcx, [rbp+57h+var_48]
0x180023231  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180023236  nop
0x180023237  lea     rcx, [rbp+57h+var_50]
0x18002323b  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180023240  jmp     loc_180023027
0x180023245  xor     ebx, ebx
0x180023247  lea     rcx, [rbp+57h+var_50]
0x18002324b  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180023250  mov     eax, ebx
0x180023252  mov     rcx, [rbp+57h+var_38]
0x180023256  xor     rcx, rsp; StackCookie
0x180023259  call    __security_check_cookie
0x18002325e  add     rsp, 0A8h
0x180023265  pop     r14
0x180023267  pop     r13
0x180023269  pop     rdi
0x18002326a  pop     rsi
0x18002326b  pop     rbx
0x18002326c  pop     rbp
0x18002326d  retn
```
