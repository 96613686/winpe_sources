# AppReadiness::User::UpdatePackageMetadata(void)

- ea: `0x180008d7c`
- end: `0x180009055`
- name: `?UpdatePackageMetadata@User@AppReadiness@@QEAAXXZ`
- size: `729`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009380`

## callees

- `0x180002958`
- `0x1800041e0`
- `0x180008d7c`
- `0x1800097d0`
- `0x180009d60`
- `0x18000b464`
- `0x180026954`
- `0x180027a4c`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008ef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008dbb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008dbb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ebe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008f82`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ebe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f66`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008f34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008f34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008e6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008e6e`

## string_xrefs

- `0x180008fc7`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x18000901f`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x18000902b`: `AppReadiness::Storage::PackageMetadata::Set`
- `0x180008fd3`: `AppReadiness::Storage::PackageMetadata::Clear`
- `0x180009032`: `SHRegSetDWORD(key.Get(), nullptr, MetadataTypeToValueName(type), value)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AppReadiness::User::UpdatePackageMetadata(RTL_SRWLOCK *this)
{
  _QWORD *v2; // rcx
  RTL_SRWLOCK *v3; // rdi
  AppReadiness::User *Ptr; // rsi
  int v5; // eax
  bool v6; // sf
  int LastError; // eax
  int v8; // eax
  int v9; // eax
  bool v10; // sf
  void **v11; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-21h]
  void **v13; // [rsp+40h] [rbp-19h] BYREF
  HKEY v14; // [rsp+48h] [rbp-11h]
  RTL_SRWLOCK *v15; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v16[2]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+68h] [rbp+Fh] BYREF
  int Data; // [rsp+C0h] [rbp+67h] BYREF
  RTL_SRWLOCK *v19; // [rsp+C8h] [rbp+6Fh]

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    goto LABEL_27;
  while ( 1 )
  {
    v3 = this + 7;
    AcquireSRWLockShared(this + 7);
    v19 = this + 7;
    if ( this )
      (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
    v15 = this;
    Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(&v15);
    v16[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    v16[1] = 0;
    if ( this )
      (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 2))(this);
    Ptr = (AppReadiness::User *)this[15].Ptr;
    this = (RTL_SRWLOCK *)this[16].Ptr;
    if ( Ptr == (AppReadiness::User *)this )
      break;
    while ( 1 )
    {
      AppReadiness::Storage::PackageMetadata::CreateMetadataKey(&v15, &v11, *(_QWORD *)Ptr + 40LL, 131078);
      Data = 0;
      v5 = RegSetValueExW(hKey, L"OnStart", 0, 4u, (const BYTE *)&Data, 4u);
      v6 = v5 < 0;
      if ( v5 > 0 )
      {
        v5 = (unsigned __int16)v5 | 0x80070000;
        v6 = v5 < 0;
      }
      if ( v6 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v5,
          "SHRegSetDWORD(key.Get(), nullptr, MetadataTypeToValueName(type), value)",
          "AppReadiness::Storage::PackageMetadata::Set",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
          100);
        throw (Windows::HResultException *)pExceptionObject;
      }
      v11 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
      if ( hKey )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v11) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          RaiseException(LastError, 1u, 0, 0);
          __debugbreak();
        }
        hKey = 0;
      }
      AppReadiness::Storage::PackageMetadata::CreateMetadataKey(&v15, &v13, *(_QWORD *)Ptr + 40LL, 131078);
      v8 = RegDeleteValueW(v14, L"StartPosition");
      if ( (v8 & 0xFFFFFFFC) != 0 || v8 == 1 )
      {
        v10 = v8 < 0;
        if ( v8 > 0 )
        {
          v8 = (unsigned __int16)v8 | 0x80070000;
          v10 = v8 < 0;
        }
        if ( v10 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)pExceptionObject,
            v8,
            "result",
            "AppReadiness::Storage::PackageMetadata::Clear",
            "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
            86);
          throw (Windows::HResultException *)pExceptionObject;
        }
      }
      v13 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
      if ( !v14 )
        goto LABEL_16;
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v13) )
        break;
      v14 = 0;
LABEL_16:
      Ptr = (AppReadiness::User *)((char *)Ptr + 16);
      if ( Ptr == (AppReadiness::User *)this )
        goto LABEL_17;
    }
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    RaiseException(v9, 1u, 0, 0);
LABEL_27:
    WPP_SF_S(v2[2], 14, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
  }
LABEL_17:
  v16[0] = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  if ( v3 )
    ReleaseSRWLockShared(v3);
}

```

## disassembly

```asm
0x180008d7c  mov     [rsp-8+arg_10], rbx
0x180008d81  push    rbp
0x180008d82  push    rsi
0x180008d83  push    rdi
0x180008d84  push    r12
0x180008d86  push    r15
0x180008d88  lea     rbp, [rsp-37h]
0x180008d8d  sub     rsp, 90h
0x180008d94  mov     rbx, rcx
0x180008d97  lea     rax, WPP_GLOBAL_Control
0x180008d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008da5  cmp     rcx, rax
0x180008da8  jz      short loc_180008DB4
0x180008daa  test    byte ptr [rcx+1Ch], 8
0x180008dae  jnz     loc_180008F89
0x180008db4  lea     rdi, [rbx+38h]
0x180008db8  mov     rcx, rdi; SRWLock
0x180008dbb  call    cs:__imp_AcquireSRWLockShared
0x180008dc1  mov     [rbp+57h+arg_8], rdi
0x180008dc5  test    rbx, rbx
0x180008dc8  jz      short loc_180008DDA
0x180008dca  mov     rax, [rbx]
0x180008dcd  mov     rcx, rbx
0x180008dd0  mov     rax, [rax+8]
0x180008dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dd9  nop
0x180008dda  mov     [rbp+57h+var_60], rbx
0x180008dde  lea     rcx, [rbp+57h+var_60]
0x180008de2  call    ?InternalAddRef@?$ComPtr@UIAppReadinessTaskCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAppReadinessTaskCallback>::InternalAddRef(void)
0x180008de7  lea     r15, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180008dee  mov     [rbp+57h+var_58], r15
0x180008df2  mov     [rbp+57h+var_50], 0
0x180008dfa  test    rbx, rbx
0x180008dfd  jz      short loc_180008E0F
0x180008dff  mov     rax, [rbx]
0x180008e02  mov     rcx, rbx
0x180008e05  mov     rax, [rax+10h]
0x180008e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0e  nop
0x180008e0f  mov     rsi, [rbx+78h]
0x180008e13  mov     rbx, [rbx+80h]
0x180008e1a  cmp     rsi, rbx
0x180008e1d  jz      loc_180008ED2
0x180008e23  mov     r12d, 80070000h
0x180008e29  mov     r8, [rsi]
0x180008e2c  add     r8, 28h ; '('
0x180008e30  mov     r9d, 20006h
0x180008e36  lea     rdx, [rbp+57h+var_80]
0x180008e3a  lea     rcx, [rbp+57h+var_60]
0x180008e3e  call    ?CreateMetadataKey@PackageMetadata@Storage@AppReadiness@@AEAA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; AppReadiness::Storage::PackageMetadata::CreateMetadataKey(std::wstring const &,ulong)
0x180008e43  nop
0x180008e44  mov     [rbp+57h+Data], 0
0x180008e4b  mov     ecx, 4
0x180008e50  mov     [rsp+0B0h+cbData], ecx; cbData
0x180008e54  lea     rax, [rbp+57h+Data]
0x180008e58  mov     [rsp+0B0h+lpData], rax; lpData
0x180008e5d  mov     r9d, ecx; dwType
0x180008e60  xor     r8d, r8d; Reserved
0x180008e63  mov     rdx, cs:off_18007A700; lpValueName
0x180008e6a  mov     rcx, [rbp+57h+hKey]; hKey
0x180008e6e  call    cs:__imp_RegSetValueExW
0x180008e74  test    eax, eax
0x180008e76  jle     short loc_180008E80
0x180008e78  movzx   eax, ax
0x180008e7b  or      eax, r12d
0x180008e7e  test    eax, eax
0x180008e80  js      loc_180009017
0x180008e86  mov     [rbp+57h+var_80], r15
0x180008e8a  cmp     [rbp+57h+hKey], 0
0x180008e8f  jz      short loc_180008F0E
0x180008e91  lea     rcx, [rbp+57h+var_80]
0x180008e95  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180008e9a  test    al, al
0x180008e9c  jnz     loc_180008FFD
0x180008ea2  call    cs:__imp_GetLastError
0x180008ea8  test    eax, eax
0x180008eaa  jle     short loc_180008EB2
0x180008eac  movzx   eax, ax
0x180008eaf  or      eax, r12d
0x180008eb2  xor     r9d, r9d; lpArguments
0x180008eb5  xor     r8d, r8d; nNumberOfArguments
0x180008eb8  lea     edx, [r9+1]; dwExceptionFlags
0x180008ebc  mov     ecx, eax; dwExceptionCode
0x180008ebe  call    cs:__imp_RaiseException
0x180008ec4  int     3; Trap to Debugger
0x180008ec5  add     rsi, 10h
0x180008ec9  cmp     rsi, rbx
0x180008ecc  jnz     loc_180008E29
0x180008ed2  mov     [rbp+57h+var_58], r15
0x180008ed6  lea     rcx, [rbp+57h+var_58]
0x180008eda  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180008edf  lea     rcx, [rbp+57h+var_60]
0x180008ee3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180008ee8  nop
0x180008ee9  test    rdi, rdi
0x180008eec  jz      short loc_180008EF7
0x180008eee  mov     rcx, rdi; SRWLock
0x180008ef1  call    cs:__imp_ReleaseSRWLockShared
0x180008ef7  mov     rbx, [rsp+0B0h+arg_10]
0x180008eff  add     rsp, 90h
0x180008f06  pop     r15
0x180008f08  pop     r12
0x180008f0a  pop     rdi
0x180008f0b  pop     rsi
0x180008f0c  pop     rbp
0x180008f0d  retn
0x180008f0e  mov     r8, [rsi]
0x180008f11  add     r8, 28h ; '('
0x180008f15  mov     r9d, 20006h
0x180008f1b  lea     rdx, [rbp+57h+var_70]
0x180008f1f  lea     rcx, [rbp+57h+var_60]
0x180008f23  call    ?CreateMetadataKey@PackageMetadata@Storage@AppReadiness@@AEAA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; AppReadiness::Storage::PackageMetadata::CreateMetadataKey(std::wstring const &,ulong)
0x180008f28  nop
0x180008f29  mov     rdx, cs:lpValue; lpValueName
0x180008f30  mov     rcx, [rbp+57h+var_68]; hKey
0x180008f34  call    cs:__imp_RegDeleteValueW
0x180008f3a  test    eax, 0FFFFFFFCh
0x180008f3f  jnz     short loc_180008FB1
0x180008f41  cmp     eax, 1
0x180008f44  jz      short loc_180008FB1
0x180008f46  mov     [rbp+57h+var_70], r15
0x180008f4a  cmp     [rbp+57h+var_68], 0
0x180008f4f  jz      loc_180008EC5
0x180008f55  lea     rcx, [rbp+57h+var_70]
0x180008f59  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180008f5e  test    al, al
0x180008f60  jnz     loc_18000900A
0x180008f66  call    cs:__imp_GetLastError
0x180008f6c  test    eax, eax
0x180008f6e  jle     short loc_180008F76
0x180008f70  movzx   eax, ax
0x180008f73  or      eax, r12d
0x180008f76  xor     r9d, r9d; lpArguments
0x180008f79  xor     r8d, r8d; nNumberOfArguments
0x180008f7c  lea     edx, [r9+1]; dwExceptionFlags
0x180008f80  mov     ecx, eax; dwExceptionCode
0x180008f82  call    cs:__imp_RaiseException
0x180008f88  nop
0x180008f89  lea     r9, [rbx+40h]
0x180008f8d  cmp     qword ptr [r9+18h], 7
0x180008f92  jbe     short loc_180008F97
0x180008f94  mov     r9, [r9]
0x180008f97  mov     edx, 0Eh
0x180008f9c  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x180008fa3  mov     rcx, [rcx+10h]
0x180008fa7  call    WPP_SF_S
0x180008fac  jmp     loc_180008DB4
0x180008fb1  test    eax, eax
0x180008fb3  jle     short loc_180008FBD
0x180008fb5  movzx   eax, ax
0x180008fb8  or      eax, r12d
0x180008fbb  test    eax, eax
0x180008fbd  jns     short loc_180008F46
0x180008fbf  mov     [rsp+0B0h+cbData], 56h ; 'V'; int
0x180008fc7  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180008fce  mov     [rsp+0B0h+lpData], rcx; char *
0x180008fd3  lea     r9, aAppreadinessSt_6; "AppReadiness::Storage::PackageMetadata:"...
0x180008fda  lea     r8, aResult; "result"
0x180008fe1  mov     edx, eax; int
0x180008fe3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180008fe7  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180008fec  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180008ff3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180008ff7  call    _CxxThrowException_0
0x180008ffd  mov     [rbp+57h+hKey], 0
0x180009005  jmp     loc_180008F0E
0x18000900a  mov     [rbp+57h+var_68], 0
0x180009012  jmp     loc_180008EC5
0x180009017  mov     [rsp+0B0h+cbData], 64h ; 'd'; int
0x18000901f  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009026  mov     [rsp+0B0h+lpData], rcx; char *
0x18000902b  lea     r9, aAppreadinessSt_10; "AppReadiness::Storage::PackageMetadata:"...
0x180009032  lea     r8, aShregsetdwordK; "SHRegSetDWORD(key.Get(), nullptr, Metad"...
0x180009039  mov     edx, eax; int
0x18000903b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000903f  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009044  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000904b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000904f  call    _CxxThrowException_0
```
