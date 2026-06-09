# SystemSettings::StorageSenseHandlers::CPackageSizeSetting::ShowOperationErrorDialog(long,SystemSettings::StorageSenseHandlers::AppOperationType,HWND__ *)

- ea: `0x180045ee0`
- end: `0x180046236`
- name: `?ShowOperationErrorDialog@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@UEAAJJW4AppOperationType@23@PEAUHWND__@@@Z`
- size: `854`
- prototype: `int __high(int, enum SystemSettings::StorageSenseHandlers::AppOperationType, HWND)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18000e6cc`
- `0x1800292a8`
- `0x18002bad4`
- `0x180035c0c`
- `0x180045ee0`
- `0x1800b5a08`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800461fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180046149`

## string_xrefs

- `0x180045f78`: `SystemSettings_StorageSense_Move_Fail`
- `0x180045fc2`: `SystemSettings_StorageSense_Move_Fail_NoSpace`
- `0x180046164`: `SystemSettings_StorageSense_Uninstall_Fail`
- `0x180046035`: `SystemSettings_StorageSense_Move_Fail_Filesystem`
- `0x180045ffa`: `SystemSettings_StorageSense_Move_Fail_AppStreaming`
- `0x1800460ab`: `SystemSettings_StorageSense_Move_Fail_OptOut`
- `0x180046070`: `SystemSettings_StorageSense_Set_AppWrite_Fail_NotSupported`
- `0x180046121`: `SystemSettings_StorageSense_Move_Fail_OptOut_Special_Profile`
- `0x1800460e6`: `SystemSettings_StorageSense_Move_Fail_OptOut_Machine`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageSizeSetting::ShowOperationErrorDialog(
        __int64 a1,
        unsigned int a2,
        int a3,
        SystemSettings::StorageSenseHandlers::StringHelpers *a4)
{
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned __int16 **v12; // rbx
  unsigned __int16 **StringRawBuffer; // rbx
  unsigned __int16 **v14; // r8
  int v16; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v17; // [rsp+28h] [rbp-30h]
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  HWND v19; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v20[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  unsigned __int16 *v22; // [rsp+90h] [rbp+38h] BYREF

  v19 = 0;
  v22 = 0;
  v20[0] = 0;
  string = 0;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 88LL);
  WindowsDeleteString(0);
  string = 0;
  v9 = v8(a1, &string);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 2952;
    goto LABEL_6;
  }
  if ( a3 )
  {
    if ( a3 == 1 )
    {
      StringRawBuffer = (unsigned __int16 **)WindowsGetStringRawBuffer(string, 0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
             (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Uninstall_Fail",
             (const unsigned __int16 *)&v19,
             StringRawBuffer);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = 2962;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v12 = (unsigned __int16 **)WindowsGetStringRawBuffer(string, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v19,
      0);
    v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
           (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail",
           (const unsigned __int16 *)&v19,
           v12);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = 2957;
      goto LABEL_6;
    }
    switch ( a2 )
    {
      case 0x80073CF4:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail_NoSpace",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80073CF4LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 2973;
          goto LABEL_6;
        }
        goto LABEL_33;
      case 0x80073D14:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail_AppStreaming",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80073D14LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 2978;
          goto LABEL_6;
        }
        goto LABEL_33;
      case 0x80073D13:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail_Filesystem",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80073D13LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 2983;
          goto LABEL_6;
        }
        goto LABEL_33;
      case 0x80070032:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Set_AppWrite_Fail_NotSupported",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80070032LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 2988;
          goto LABEL_6;
        }
        goto LABEL_33;
      case 0x80073D21:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail_OptOut",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80073D21LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 2993;
          goto LABEL_6;
        }
        goto LABEL_33;
      case 0x80073D22:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail_OptOut_Machine",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80073D22LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 2998;
          goto LABEL_6;
        }
        goto LABEL_33;
      case 0x80073D23:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v22,
          0);
        v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Move_Fail_OptOut_Special_Profile",
               (const unsigned __int16 *)&v22,
               (unsigned __int16 **)0x80073D23LL);
        v10 = v9;
        if ( v9 < 0 )
        {
          v11 = 3003;
          goto LABEL_6;
        }
        goto LABEL_33;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v22,
    0);
  v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
         (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Fail_Detail",
         (const unsigned __int16 *)&v22,
         (unsigned __int16 **)a2);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 3008;
    goto LABEL_6;
  }
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v20,
    0);
  v9 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
         (SystemSettings::DataModel *)L"SystemSettings_StorageSense_Fail_Confirm",
         (const unsigned __int16 *)v20,
         v14);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v10 = SystemSettings::StorageSenseHandlers::StringHelpers::ShowMessageDialog(a4, v19, v22, v20[0], 0, v17);
    goto LABEL_36;
  }
  v11 = 3012;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
    (const char *)(unsigned int)v9,
    v16);
LABEL_36:
  WindowsDeleteString(string);
  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v20);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  return v10;
}

```

## disassembly

```asm
0x180045ee0  push    rbp
0x180045ee2  push    rbx
0x180045ee3  push    rsi
0x180045ee4  push    rdi
0x180045ee5  push    r14
0x180045ee7  push    r15
0x180045ee9  mov     rbp, rsp
0x180045eec  sub     rsp, 58h
0x180045ef0  mov     r15, r9
0x180045ef3  mov     r14d, r8d
0x180045ef6  mov     esi, edx
0x180045ef8  mov     rdi, rcx
0x180045efb  mov     [rbp+var_20], 0
0x180045f03  mov     [rbp+arg_0], 0
0x180045f0b  mov     [rbp+var_18], 0
0x180045f13  mov     [rbp+string], 0
0x180045f1b  mov     rax, [rcx]
0x180045f1e  mov     rbx, [rax+58h]
0x180045f22  xor     ecx, ecx; string
0x180045f24  call    cs:__imp_WindowsDeleteString
0x180045f2a  mov     [rbp+string], 0
0x180045f32  lea     rdx, [rbp+string]
0x180045f36  mov     rcx, rdi
0x180045f39  mov     rax, rbx
0x180045f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f41  mov     ebx, eax
0x180045f43  test    eax, eax
0x180045f45  jns     short loc_180045F4E
0x180045f47  mov     edx, 0B88h
0x180045f4c  jmp     short loc_180045F8F
0x180045f4e  test    r14d, r14d
0x180045f51  jnz     loc_18004613D
0x180045f57  xor     edx, edx; length
0x180045f59  mov     rcx, [rbp+string]; string
0x180045f5d  call    cs:__imp_WindowsGetStringRawBuffer
0x180045f63  mov     rbx, rax
0x180045f66  xor     edx, edx
0x180045f68  lea     rcx, [rbp+var_20]
0x180045f6c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180045f71  mov     r8, rbx; unsigned __int16 **
0x180045f74  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x180045f78  lea     rcx, aSystemsettings_85; "SystemSettings_StorageSense_Move_Fail"
0x180045f7f  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180045f84  mov     ebx, eax
0x180045f86  test    eax, eax
0x180045f88  jns     short loc_180045FA7
0x180045f8a  mov     edx, 0B8Dh; void *
0x180045f8f  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180045f96  mov     r9d, eax; char *
0x180045f99  mov     rcx, [rbp+30h]; this
0x180045f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045fa2  jmp     loc_1800461F8
0x180045fa7  mov     ebx, 80073CF4h
0x180045fac  cmp     esi, ebx
0x180045fae  jnz     short loc_180045FDF
0x180045fb0  xor     edx, edx
0x180045fb2  lea     rcx, [rbp+arg_0]
0x180045fb6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180045fbb  mov     r8d, ebx; unsigned __int16 **
0x180045fbe  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180045fc2  lea     rcx, aSystemsettings_361; "SystemSettings_StorageSense_Move_Fail_N"...
0x180045fc9  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180045fce  mov     ebx, eax
0x180045fd0  test    eax, eax
0x180045fd2  jns     loc_1800461AE
0x180045fd8  mov     edx, 0B9Dh
0x180045fdd  jmp     short loc_180045F8F
0x180045fdf  mov     ebx, 80073D14h
0x180045fe4  cmp     esi, ebx
0x180045fe6  jnz     short loc_18004601A
0x180045fe8  xor     edx, edx
0x180045fea  lea     rcx, [rbp+arg_0]
0x180045fee  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180045ff3  mov     r8d, ebx; unsigned __int16 **
0x180045ff6  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180045ffa  lea     rcx, aSystemsettings_195; "SystemSettings_StorageSense_Move_Fail_A"...
0x180046001  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180046006  mov     ebx, eax
0x180046008  test    eax, eax
0x18004600a  jns     loc_1800461AE
0x180046010  mov     edx, 0BA2h
0x180046015  jmp     loc_180045F8F
0x18004601a  mov     ebx, 80073D13h
0x18004601f  cmp     esi, ebx
0x180046021  jnz     short loc_180046055
0x180046023  xor     edx, edx
0x180046025  lea     rcx, [rbp+arg_0]
0x180046029  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004602e  mov     r8d, ebx; unsigned __int16 **
0x180046031  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180046035  lea     rcx, aSystemsettings_246; "SystemSettings_StorageSense_Move_Fail_F"...
0x18004603c  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180046041  mov     ebx, eax
0x180046043  test    eax, eax
0x180046045  jns     loc_1800461AE
0x18004604b  mov     edx, 0BA7h
0x180046050  jmp     loc_180045F8F
0x180046055  mov     ebx, 80070032h
0x18004605a  cmp     esi, ebx
0x18004605c  jnz     short loc_180046090
0x18004605e  xor     edx, edx
0x180046060  lea     rcx, [rbp+arg_0]
0x180046064  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180046069  mov     r8d, ebx; unsigned __int16 **
0x18004606c  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180046070  lea     rcx, aSystemsettings_188; "SystemSettings_StorageSense_Set_AppWrit"...
0x180046077  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x18004607c  mov     ebx, eax
0x18004607e  test    eax, eax
0x180046080  jns     loc_1800461AE
0x180046086  mov     edx, 0BACh
0x18004608b  jmp     loc_180045F8F
0x180046090  mov     ebx, 80073D21h
0x180046095  cmp     esi, ebx
0x180046097  jnz     short loc_1800460CB
0x180046099  xor     edx, edx
0x18004609b  lea     rcx, [rbp+arg_0]
0x18004609f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800460a4  mov     r8d, ebx; unsigned __int16 **
0x1800460a7  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1800460ab  lea     rcx, aSystemsettings_343; "SystemSettings_StorageSense_Move_Fail_O"...
0x1800460b2  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800460b7  mov     ebx, eax
0x1800460b9  test    eax, eax
0x1800460bb  jns     loc_1800461AE
0x1800460c1  mov     edx, 0BB1h
0x1800460c6  jmp     loc_180045F8F
0x1800460cb  mov     ebx, 80073D22h
0x1800460d0  cmp     esi, ebx
0x1800460d2  jnz     short loc_180046106
0x1800460d4  xor     edx, edx
0x1800460d6  lea     rcx, [rbp+arg_0]
0x1800460da  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800460df  mov     r8d, ebx; unsigned __int16 **
0x1800460e2  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1800460e6  lea     rcx, aSystemsettings_92; "SystemSettings_StorageSense_Move_Fail_O"...
0x1800460ed  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800460f2  mov     ebx, eax
0x1800460f4  test    eax, eax
0x1800460f6  jns     loc_1800461AE
0x1800460fc  mov     edx, 0BB6h
0x180046101  jmp     loc_180045F8F
0x180046106  mov     ebx, 80073D23h
0x18004610b  cmp     esi, ebx
0x18004610d  jnz     short loc_180046180
0x18004610f  xor     edx, edx
0x180046111  lea     rcx, [rbp+arg_0]
0x180046115  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004611a  mov     r8d, ebx; unsigned __int16 **
0x18004611d  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180046121  lea     rcx, aSystemsettings_53; "SystemSettings_StorageSense_Move_Fail_O"...
0x180046128  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x18004612d  mov     ebx, eax
0x18004612f  test    eax, eax
0x180046131  jns     short loc_1800461AE
0x180046133  mov     edx, 0BBBh
0x180046138  jmp     loc_180045F8F
0x18004613d  cmp     r14d, 1
0x180046141  jnz     short loc_180046180
0x180046143  xor     edx, edx; length
0x180046145  mov     rcx, [rbp+string]; string
0x180046149  call    cs:__imp_WindowsGetStringRawBuffer
0x18004614f  mov     rbx, rax
0x180046152  xor     edx, edx
0x180046154  lea     rcx, [rbp+var_20]
0x180046158  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004615d  mov     r8, rbx; unsigned __int16 **
0x180046160  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x180046164  lea     rcx, aSystemsettings_82; "SystemSettings_StorageSense_Uninstall_F"...
0x18004616b  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x180046170  mov     ebx, eax
0x180046172  test    eax, eax
0x180046174  jns     short loc_180046180
0x180046176  mov     edx, 0B92h
0x18004617b  jmp     loc_180045F8F
0x180046180  xor     edx, edx
0x180046182  lea     rcx, [rbp+arg_0]
0x180046186  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004618b  mov     r8d, esi; unsigned __int16 **
0x18004618e  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180046192  lea     rcx, aSystemsettings_54; "SystemSettings_StorageSense_Fail_Detail"
0x180046199  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x18004619e  mov     ebx, eax
0x1800461a0  test    eax, eax
0x1800461a2  jns     short loc_1800461AE
0x1800461a4  mov     edx, 0BC0h
0x1800461a9  jmp     loc_180045F8F
0x1800461ae  xor     edx, edx
0x1800461b0  lea     rcx, [rbp+var_18]
0x1800461b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800461b9  lea     rdx, [rbp+var_18]; unsigned __int16 *
0x1800461bd  lea     rcx, aSystemsettings_249; "SystemSettings_StorageSense_Fail_Confir"...
0x1800461c4  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x1800461c9  mov     ebx, eax
0x1800461cb  test    eax, eax
0x1800461cd  jns     short loc_1800461D9
0x1800461cf  mov     edx, 0BC4h
0x1800461d4  jmp     loc_180045F8F
0x1800461d9  mov     [rsp+58h+var_38], 0; unsigned __int16 *
0x1800461e2  mov     r9, [rbp+var_18]; unsigned __int16 *
0x1800461e6  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x1800461ea  mov     rdx, [rbp+var_20]; HWND
0x1800461ee  mov     rcx, r15; this
0x1800461f1  call    ?ShowMessageDialog@StringHelpers@StorageSenseHandlers@SystemSettings@@YAJPEAUHWND__@@PEBG111@Z; SystemSettings::StorageSenseHandlers::StringHelpers::ShowMessageDialog(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800461f6  mov     ebx, eax
0x1800461f8  mov     rcx, [rbp+string]; string
0x1800461fc  call    cs:__imp_WindowsDeleteString
0x180046202  mov     [rbp+string], 0
0x18004620a  lea     rcx, [rbp+var_18]
0x18004620e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180046213  nop
0x180046214  lea     rcx, [rbp+arg_0]
0x180046218  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004621d  nop
0x18004621e  lea     rcx, [rbp+var_20]
0x180046222  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180046227  mov     eax, ebx
0x180046229  add     rsp, 58h
0x18004622d  pop     r15
0x18004622f  pop     r14
0x180046231  pop     rdi
0x180046232  pop     rsi
0x180046233  pop     rbx
0x180046234  pop     rbp
0x180046235  retn
```
