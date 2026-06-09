# SystemSettings::PenSettings::DevicesPenSetActionModifierBase::GetPossibleValues(IInspectable * *)

- ea: `0x180027b20`
- end: `0x180027dc3`
- name: `?GetPossibleValues@DevicesPenSetActionModifierBase@PenSettings@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `675`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetActionModifierBase *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003110`
- `0x180005b2c`
- `0x18000a2bc`
- `0x18000d02c`
- `0x18001012c`
- `0x180012154`
- `0x1800161a0`
- `0x180019a40`
- `0x180019fcc`
- `0x180027b20`
- `0x1800284f8`
- `0x18003114c`
- `0x180052518`
- `0x1800526d8`
- `0x18005d010`

## string_xrefs

- `0x180027c65`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180027c8a`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180027d01`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180027d5e`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionModifierBase::GetPossibleValues(
        SystemSettings::PenSettings::DevicesPenSetActionModifierBase *this,
        struct IInspectable **a2)
{
  void *v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned __int16 **v11; // r8
  int ResourceStringById; // edi
  int v13; // eax
  __int64 v14; // rdx
  struct SystemSettings::PenSettings::EnumerateModernAppsSingleton *Instance; // rax
  struct SystemSettings::PenSettings::EnumerateModernAppsSingleton *v16; // rax
  int ModernApps; // eax
  unsigned int v18; // ebx
  __int64 i; // rbx
  __int64 v21; // rax
  int appended; // eax
  unsigned int v23; // edi
  unsigned __int16 v24[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v25; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *v27; // [rsp+68h] [rbp+10h] BYREF
  __int64 v28; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v28);
  v28 = 0;
  v4 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v27 = v4;
  v5 = 0;
  if ( v4 )
  {
    v5 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v4);
    v27 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>::~MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>(&v27);
  if ( v5 )
  {
    v6 = 0;
    v28 = v5;
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v6 >= 0 )
  {
    v9 = *((_DWORD *)this + 69);
    if ( v9 == 5 )
    {
      v10 = 0;
      while ( 1 )
      {
        memset(v24, 0, sizeof(v24));
        v25 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v24);
        *(_QWORD *)&v24[4] = -1;
        v25 = -1;
        ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                               (SystemSettings::DataModel *)(&off_18007B9C8)[2 * v10],
                               v24,
                               v11);
        if ( ResourceStringById < 0 )
          break;
        ResourceStringById = SystemSettings::DataModel::AppendStringToVector(*(_QWORD *)v24, v28);
        if ( ResourceStringById < 0 )
        {
          v14 = 1146;
          goto LABEL_18;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v24);
        if ( ++v10 >= 4 )
          goto LABEL_13;
      }
      v14 = 1145;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)ResourceStringById,
        *(int *)v24);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v24);
      v6 = ResourceStringById;
      goto LABEL_29;
    }
    if ( v9 == 2 )
    {
      Instance = SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance();
      (*(void (__fastcall **)(struct SystemSettings::PenSettings::EnumerateModernAppsSingleton *, _QWORD, SystemSettings::PenSettings::DevicesPenSetActionModifierBase *))(*(_QWORD *)Instance + 72LL))(
        Instance,
        0,
        this);
      *(_OWORD *)v24 = 0;
      v25 = 0;
      v16 = SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance();
      ModernApps = SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetModernApps(v16, v24);
      v18 = ModernApps;
      if ( ModernApps < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x484,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)ModernApps,
          *(int *)v24);
        std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(v24);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v28);
        return v18;
      }
      for ( i = *(_QWORD *)v24; i != *(_QWORD *)&v24[4]; i += 136 )
      {
        v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
        appended = SystemSettings::DataModel::AppendStringToVector(v21, v28);
        v23 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x487,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)appended,
            *(int *)v24);
          std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(v24);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v28);
          return v23;
        }
      }
      std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(v24);
    }
LABEL_13:
    v13 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
            v28,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            a2);
    v6 = v13;
    if ( v13 >= 0 )
    {
      v6 = 0;
      goto LABEL_29;
    }
    v7 = (unsigned int)v13;
    v8 = 1165;
  }
  else
  {
    v7 = (unsigned int)v6;
    v8 = 1138;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
    (const char *)v7,
    *(int *)v24);
LABEL_29:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180027b20  mov     [rsp+arg_0], rbx
0x180027b25  push    rsi
0x180027b26  push    rdi
0x180027b27  push    r14
0x180027b29  sub     rsp, 40h
0x180027b2d  mov     r14, rdx
0x180027b30  mov     rsi, rcx
0x180027b33  mov     qword ptr [rdx], 0
0x180027b3a  mov     [rsp+58h+arg_10], 0
0x180027b43  lea     rcx, [rsp+58h+arg_10]
0x180027b48  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180027b4d  mov     [rsp+58h+arg_10], 0
0x180027b56  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027b5d  mov     ecx, 0B8h; unsigned __int64
0x180027b62  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027b67  mov     [rsp+58h+arg_8], rax
0x180027b6c  xor     edi, edi
0x180027b6e  test    rax, rax
0x180027b71  jz      short loc_180027B87
0x180027b73  mov     rcx, rax
0x180027b76  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x180027b7b  mov     rdi, rax
0x180027b7e  mov     [rsp+58h+arg_8], 0
0x180027b87  lea     rcx, [rsp+58h+arg_8]
0x180027b8c  call    ??1?$MakeAllocator@VCDevicesPenEnableKeyPressedDisplay@PenSettings@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>::~MakeAllocator<SystemSettings::PenSettings::CDevicesPenEnableKeyPressedDisplay>(void)
0x180027b91  test    rdi, rdi
0x180027b94  jnz     short loc_180027B9D
0x180027b96  mov     ebx, 8007000Eh
0x180027b9b  jmp     short loc_180027BA4
0x180027b9d  xor     ebx, ebx
0x180027b9f  mov     [rsp+58h+arg_10], rdi
0x180027ba4  test    ebx, ebx
0x180027ba6  jns     short loc_180027BB5
0x180027ba8  mov     r9d, ebx
0x180027bab  mov     edx, 472h
0x180027bb0  jmp     loc_180027C65
0x180027bb5  mov     eax, [rsi+114h]
0x180027bbb  cmp     eax, 5
0x180027bbe  jnz     loc_180027CAD
0x180027bc4  xor     ebx, ebx
0x180027bc6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027bca  mov     qword ptr [rsp+58h+var_38], 0; int
0x180027bd3  mov     qword ptr [rsp+58h+var_38+8], 0
0x180027bdc  mov     [rsp+58h+var_28], 0
0x180027be5  lea     rcx, [rsp+58h+var_38]
0x180027bea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027bef  mov     qword ptr [rsp+58h+var_38+8], rsi
0x180027bf4  mov     [rsp+58h+var_28], rsi
0x180027bf9  mov     ecx, ebx
0x180027bfb  add     rcx, rcx
0x180027bfe  lea     rax, off_18007B9C8; "SystemSettings_Devices_Pen_ButtonCustom"...
0x180027c05  lea     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x180027c0a  mov     rcx, [rax+rcx*8]; this
0x180027c0e  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x180027c13  mov     edi, eax
0x180027c15  test    eax, eax
0x180027c17  js      short loc_180027C82
0x180027c19  mov     rdx, [rsp+58h+arg_10]
0x180027c1e  mov     rcx, qword ptr [rsp+58h+var_38]
0x180027c23  call    ?AppendStringToVector@DataModel@SystemSettings@@YAJPEBGPEAV?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@Z; SystemSettings::DataModel::AppendStringToVector(ushort const *,Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>> *)
0x180027c28  mov     edi, eax
0x180027c2a  test    eax, eax
0x180027c2c  js      short loc_180027C7B
0x180027c2e  lea     rcx, [rsp+58h+var_38]
0x180027c33  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027c38  inc     ebx
0x180027c3a  cmp     ebx, 4
0x180027c3d  jb      short loc_180027BCA
0x180027c3f  mov     r8, r14
0x180027c42  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180027c49  mov     rcx, [rsp+58h+arg_10]
0x180027c4e  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180027c53  mov     ebx, eax
0x180027c55  test    eax, eax
0x180027c57  jns     loc_180027DA7
0x180027c5d  mov     r9d, eax; char *
0x180027c60  mov     edx, 48Dh; void *
0x180027c65  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180027c6c  mov     rcx, [rsp+58h]; this
0x180027c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c76  jmp     loc_180027DA9
0x180027c7b  mov     edx, 47Ah
0x180027c80  jmp     short loc_180027C87
0x180027c82  mov     edx, 479h; void *
0x180027c87  mov     r9d, edi; char *
0x180027c8a  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180027c91  mov     rcx, [rsp+58h]; this
0x180027c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c9b  nop
0x180027c9c  lea     rcx, [rsp+58h+var_38]
0x180027ca1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027ca6  mov     ebx, edi
0x180027ca8  jmp     loc_180027DA9
0x180027cad  cmp     eax, 2
0x180027cb0  jnz     short loc_180027C3F
0x180027cb2  call    ?GetInstance@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@SAAEAV123@XZ; SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance(void)
0x180027cb7  mov     r9, rax
0x180027cba  mov     rcx, [rax]
0x180027cbd  mov     rax, [rcx+48h]
0x180027cc1  mov     r8, rsi
0x180027cc4  xor     edx, edx
0x180027cc6  mov     rcx, r9
0x180027cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cce  nop
0x180027ccf  xorps   xmm0, xmm0
0x180027cd2  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x180027cd8  mov     [rsp+58h+var_28], 0
0x180027ce1  call    ?GetInstance@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@SAAEAV123@XZ; SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetInstance(void)
0x180027ce6  lea     rdx, [rsp+58h+var_38]
0x180027ceb  mov     rcx, rax
0x180027cee  call    ?GetModernApps@EnumerateModernAppsSingleton@PenSettings@SystemSettings@@QEAAJPEAV?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@@Z; SystemSettings::PenSettings::EnumerateModernAppsSingleton::GetModernApps(std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo> *)
0x180027cf3  mov     ebx, eax
0x180027cf5  test    eax, eax
0x180027cf7  jns     short loc_180027D2F
0x180027cf9  mov     rcx, [rsp+58h]; this
0x180027cfe  mov     r9d, eax; char *
0x180027d01  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180027d08  mov     edx, 484h; void *
0x180027d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d12  nop
0x180027d13  lea     rcx, [rsp+58h+var_38]
0x180027d18  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x180027d1d  nop
0x180027d1e  lea     rcx, [rsp+58h+arg_10]
0x180027d23  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180027d28  mov     eax, ebx
0x180027d2a  jmp     loc_180027DB5
0x180027d2f  mov     rbx, qword ptr [rsp+58h+var_38]
0x180027d34  cmp     rbx, qword ptr [rsp+58h+var_38+8]
0x180027d39  jz      short loc_180027D92
0x180027d3b  mov     rcx, rbx
0x180027d3e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027d43  mov     rdx, [rsp+58h+arg_10]
0x180027d48  mov     rcx, rax
0x180027d4b  call    ?AppendStringToVector@DataModel@SystemSettings@@YAJPEBGPEAV?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@Z; SystemSettings::DataModel::AppendStringToVector(ushort const *,Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>> *)
0x180027d50  mov     edi, eax
0x180027d52  test    eax, eax
0x180027d54  jns     short loc_180027D89
0x180027d56  mov     rcx, [rsp+58h]; this
0x180027d5b  mov     r9d, eax; char *
0x180027d5e  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180027d65  mov     edx, 487h; void *
0x180027d6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d6f  nop
0x180027d70  lea     rcx, [rsp+58h+var_38]
0x180027d75  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x180027d7a  nop
0x180027d7b  lea     rcx, [rsp+58h+arg_10]
0x180027d80  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180027d85  mov     eax, edi
0x180027d87  jmp     short loc_180027DB5
0x180027d89  add     rbx, 88h
0x180027d90  jmp     short loc_180027D34
0x180027d92  lea     rcx, [rsp+58h+var_38]
0x180027d97  call    ?_Tidy@?$vector@UPenLaunchableAppInfo@PenSettings@SystemSettings@@V?$allocator@UPenLaunchableAppInfo@PenSettings@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::PenSettings::PenLaunchableAppInfo>::_Tidy(void)
0x180027d9c  jmp     loc_180027C3F
0x180027da1  mov     ebx, dword ptr [rsp+58h+arg_8]
0x180027da5  jmp     short loc_180027DA9
0x180027da7  xor     ebx, ebx
0x180027da9  lea     rcx, [rsp+58h+arg_10]
0x180027dae  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180027db3  mov     eax, ebx
0x180027db5  mov     rbx, [rsp+58h+arg_0]
0x180027dba  add     rsp, 40h
0x180027dbe  pop     r14
0x180027dc0  pop     rdi
0x180027dc1  pop     rsi
0x180027dc2  retn
```
