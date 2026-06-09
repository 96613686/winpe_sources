# AppReadiness::Storage::PackageList::OpenUserMachineRoot(AppReadiness::User const *,ulong)

- ea: `0x180009f50`
- end: `0x18000a1a1`
- name: `?OpenUserMachineRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z`
- size: `593`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, REGSAM)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005a70`
- `0x180009e10`
- `0x18001e268`
- `0x18001ea8c`
- `0x180035458`

## callees

- `0x180009f50`
- `0x180027a4c`
- `0x18002e6f8`
- `0x18003ecb4`
- `0x1800473d8`
- `0x180061904`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009fa6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009fa6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a0b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a0b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009fd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009fd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a137`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a137`

## string_xrefs

- `0x18000a024`: `InitOnceExecuteOnce(&initOnce, [](PINIT_ONCE , void* , void** ) -> BOOL { MICROSOFT_TELEMETRY_ASSERT(!s_registryGate.IsValid()); s_registryGate = std::move(Microsoft::WRL::Wrappers::Semaphore(CreateSemaphore(nullptr, 1, 1, nullptr))); ThrowIfFalse(s_registryGate.IsValid(), ResultFromKnownLastError()) if (!s_registryRoot.empty()) { ThrowIfWin32ResultFailed(RegOpenKeyEx(HKEY_CURRENT_USER, s_registryRoot.c_str(), 0, KEY_ALL_ACCESS, s_machineRootKey.GetAddressOf())); } else { ThrowIfWin32ResultFaile`
- `0x18000a01d`: `AppReadiness::Storage::PackageList::InitRegistry`
- `0x18000a011`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18000a0d1`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18000a159`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x18000a0e4`: `RegCreateKeyEx(s_machineRootKey.Get(), user->GetUserSid().c_str(), 0, nullptr, 0, accessRights, &securityAttr, key.GetAddressOf(), nullptr)`
- `0x18000a0dd`: `AppReadiness::Storage::PackageList::OpenUserMachineRoot`
- `0x18000a165`: `AppReadiness::Storage::PackageList::OpenUserMachineRoot`

## pseudocode

```c
_QWORD *__fastcall AppReadiness::Storage::PackageList::OpenUserMachineRoot(_QWORD *a1, __int64 a2, REGSAM a3)
{
  HKEY *phkResult; // r14
  const WCHAR *v7; // rdi
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  HLOCAL v11; // rbx
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  const unsigned __int16 *v14; // r8
  unsigned __int64 v15; // rdx
  int Error; // edx
  struct _SECURITY_ATTRIBUTES pExceptionObject; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v18[88]; // [rsp+80h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+F8h] [rbp+20h] BYREF

  *a1 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  phkResult = (HKEY *)(a1 + 1);
  a1[1] = 0;
  if ( !InitOnceExecuteOnce(&InitOnce, lambda_f7ad04c3e90c7334854a11f38297585c_::_lambda_invoker_cdecl_, 0, 0) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      -2147418113,
      "InitOnceExecuteOnce(&initOnce, [](PINIT_ONCE , void* , void** ) -> BOOL { MICROSOFT_TELEMETRY_ASSERT(!s_registryGa"
      "te.IsValid()); s_registryGate = std::move(Microsoft::WRL::Wrappers::Semaphore(CreateSemaphore(nullptr, 1, 1, nullp"
      "tr))); ThrowIfFalse(s_registryGate.IsValid(), ResultFromKnownLastError()) if (!s_registryRoot.empty()) { ThrowIfWi"
      "n32ResultFailed(RegOpenKeyEx(HKEY_CURRENT_USER, s_registryRoot.c_str(), 0, KEY_ALL_ACCESS, s_machineRootKey.GetAdd"
      "ressOf())); } else { ThrowIfWin32ResultFailed(RegOpenKeyEx(HKEY_LOCAL_MACHINE, c_AppReadinessRegRoot, 0, KEY_ALL_A"
      "CCESS, s_machineRootKey.GetAddressOf())); } return true; }, nullptr, nullptr)",
      "AppReadiness::Storage::PackageList::InitRegistry",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
      105);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v7 = (const WCHAR *)(a2 + 64);
  if ( *(_QWORD *)(a2 + 88) <= 7u )
    v8 = (const WCHAR *)(a2 + 64);
  else
    v8 = *(const WCHAR **)v7;
  v9 = RegOpenKeyExW(hKey, v8, 0, a3, phkResult);
  if ( (unsigned int)(v9 - 2) <= 1 )
  {
    if ( (a3 & 0x20006) != 0 )
    {
      AppReadiness::Storage::PackageList::CreateSecurityDescriptor(&hMem, a2);
      *(_QWORD *)&pExceptionObject.nLength = 24;
      v11 = hMem;
      pExceptionObject.lpSecurityDescriptor = hMem;
      *(_QWORD *)&pExceptionObject.bInheritHandle = 0;
      if ( *((_QWORD *)v7 + 3) <= 7u )
        v12 = v7;
      else
        v12 = *(const WCHAR **)v7;
      v13 = RegCreateKeyExW(hKey, v12, 0, 0, 0, a3, &pExceptionObject, phkResult, 0);
      v15 = (unsigned int)v13;
      if ( v13 > 0 )
        v15 = (unsigned __int16)v13 | 0x80070000;
      if ( (v15 & 0x80000000) != 0LL )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)v18,
          v15,
          "RegCreateKeyEx(s_machineRootKey.Get(), user->GetUserSid().c_str(), 0, nullptr, 0, accessRights, &securityAttr,"
          " key.GetAddressOf(), nullptr)",
          "AppReadiness::Storage::PackageList::OpenUserMachineRoot",
          "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
          268);
        throw (Windows::HResultException *)v18;
      }
      if ( *((_QWORD *)v7 + 3) > 7u )
        v7 = *(const WCHAR **)v7;
      SHRegSetString(*phkResult, (const unsigned __int16 *)v15, v14, v7);
      if ( v11 )
        LocalFree(v11);
    }
  }
  else if ( v9 )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&pExceptionObject,
        Error,
        "GetLastError()",
        "AppReadiness::Storage::PackageList::OpenUserMachineRoot",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
        276);
      throw (Windows::HResultException *)&pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180009f50  mov     [rsp+arg_8], rbx
0x180009f55  mov     [rsp+arg_0], rcx
0x180009f5a  push    rbp
0x180009f5b  push    rsi
0x180009f5c  push    rdi
0x180009f5d  push    r14
0x180009f5f  push    r15
0x180009f61  sub     rsp, 0B0h
0x180009f68  mov     ebp, r8d
0x180009f6b  mov     rbx, rdx
0x180009f6e  mov     rsi, rcx
0x180009f71  xor     r15d, r15d
0x180009f74  mov     [rsp+0D8h+var_88], r15d
0x180009f79  lea     rax, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180009f80  mov     [rcx], rax
0x180009f83  lea     r14, [rcx+8]
0x180009f87  mov     [r14], r15
0x180009f8a  mov     [rsp+0D8h+var_88], 1
0x180009f92  xor     r9d, r9d; Context
0x180009f95  xor     r8d, r8d; Parameter
0x180009f98  lea     rdx, _lambda_f7ad04c3e90c7334854a11f38297585c____lambda_invoker_cdecl_; InitFn
0x180009f9f  lea     rcx, InitOnce; InitOnce
0x180009fa6  call    cs:__imp_InitOnceExecuteOnce
0x180009fac  test    eax, eax
0x180009fae  jz      short loc_18000A009
0x180009fb0  lea     rdi, [rbx+40h]
0x180009fb4  cmp     qword ptr [rdi+18h], 7
0x180009fb9  jbe     short loc_18000A004
0x180009fbb  mov     rdx, [rdi]; lpSubKey
0x180009fbe  mov     [rsp+0D8h+phkResult], r14; phkResult
0x180009fc3  mov     r9d, ebp; samDesired
0x180009fc6  xor     r8d, r8d; ulOptions
0x180009fc9  mov     rcx, cs:hKey; hKey
0x180009fd0  call    cs:__imp_RegOpenKeyExW
0x180009fd6  lea     ecx, [rax-2]
0x180009fd9  cmp     ecx, 1
0x180009fdc  jbe     loc_18000A18F
0x180009fe2  test    eax, eax
0x180009fe4  jnz     loc_18000A142
0x180009fea  mov     rax, rsi
0x180009fed  mov     rbx, [rsp+0D8h+arg_8]
0x180009ff5  add     rsp, 0B0h
0x180009ffc  pop     r15
0x180009ffe  pop     r14
0x18000a000  pop     rdi
0x18000a001  pop     rsi
0x18000a002  pop     rbp
0x18000a003  retn
0x18000a004  mov     rdx, rdi
0x18000a007  jmp     short loc_180009FBE
0x18000a009  mov     [rsp+0D8h+samDesired], 69h ; 'i'; int
0x18000a011  lea     rax, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000a018  mov     [rsp+0D8h+phkResult], rax; char *
0x18000a01d  lea     r9, aAppreadinessSt_4; "AppReadiness::Storage::PackageList::Ini"...
0x18000a024  lea     r8, aInitonceexecut; "InitOnceExecuteOnce(&initOnce, [](PINIT"...
0x18000a02b  mov     edx, 8000FFFFh; int
0x18000a030  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x18000a035  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000a03a  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000a041  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000a046  call    _CxxThrowException_0
0x18000a04c  mov     rdx, rbx
0x18000a04f  lea     rcx, [rsp+0D8h+hMem]
0x18000a057  call    ?CreateSecurityDescriptor@PackageList@Storage@AppReadiness@@CA?AV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$LocalMem_Deleter@U_SECURITY_DESCRIPTOR@@@@@std@@PEBVUser@3@@Z; AppReadiness::Storage::PackageList::CreateSecurityDescriptor(AppReadiness::User const *)
0x18000a05c  nop
0x18000a05d  mov     [rsp+0D8h+pExceptionObject], 18h
0x18000a066  mov     rbx, [rsp+0D8h+hMem]
0x18000a06e  mov     [rsp+0D8h+var_78], rbx
0x18000a073  mov     [rsp+0D8h+var_70], r15
0x18000a078  cmp     qword ptr [rdi+18h], 7
0x18000a07d  jbe     loc_18000A10D
0x18000a083  mov     rdx, [rdi]; lpSubKey
0x18000a086  mov     [rsp+0D8h+lpdwDisposition], r15; lpdwDisposition
0x18000a08b  mov     [rsp+0D8h+var_A0], r14; phkResult
0x18000a090  lea     rax, [rsp+0D8h+pExceptionObject]
0x18000a095  mov     [rsp+0D8h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000a09a  mov     [rsp+0D8h+samDesired], ebp; samDesired
0x18000a09e  mov     dword ptr [rsp+0D8h+phkResult], r15d; dwOptions
0x18000a0a3  xor     r9d, r9d; lpClass
0x18000a0a6  xor     r8d, r8d; Reserved
0x18000a0a9  mov     rcx, cs:hKey; hKey
0x18000a0b0  call    cs:__imp_RegCreateKeyExW
0x18000a0b6  mov     edx, eax
0x18000a0b8  test    eax, eax
0x18000a0ba  jle     short loc_18000A0C5
0x18000a0bc  movzx   edx, ax
0x18000a0bf  or      edx, 80070000h; unsigned __int16 *
0x18000a0c5  test    edx, edx
0x18000a0c7  jns     short loc_18000A115
0x18000a0c9  mov     [rsp+0D8h+samDesired], 10Ch; int
0x18000a0d1  lea     rax, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000a0d8  mov     [rsp+0D8h+phkResult], rax; char *
0x18000a0dd  lea     r9, aAppreadinessSt_2; "AppReadiness::Storage::PackageList::Ope"...
0x18000a0e4  lea     r8, aRegcreatekeyex_2; "RegCreateKeyEx(s_machineRootKey.Get(), "...
0x18000a0eb  lea     rcx, [rsp+0D8h+var_58]; this
0x18000a0f3  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000a0f8  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000a0ff  lea     rcx, [rsp+0D8h+var_58]; pExceptionObject
0x18000a107  call    _CxxThrowException_0
0x18000a10d  mov     rdx, rdi
0x18000a110  jmp     loc_18000A086
0x18000a115  cmp     qword ptr [rdi+18h], 7
0x18000a11a  jbe     short loc_18000A11F
0x18000a11c  mov     rdi, [rdi]
0x18000a11f  mov     r9, rdi; unsigned __int16 *
0x18000a122  mov     rcx, [r14]; HKEY
0x18000a125  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000a12a  nop
0x18000a12b  test    rbx, rbx
0x18000a12e  jz      loc_180009FEA
0x18000a134  mov     rcx, rbx; hMem
0x18000a137  call    cs:__imp_LocalFree
0x18000a13d  jmp     loc_180009FEA
0x18000a142  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a147  mov     edx, eax; int
0x18000a149  test    eax, eax
0x18000a14b  jns     loc_180009FEA
0x18000a151  mov     [rsp+0D8h+samDesired], 114h; int
0x18000a159  lea     rax, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000a160  mov     [rsp+0D8h+phkResult], rax; char *
0x18000a165  lea     r9, aAppreadinessSt_2; "AppReadiness::Storage::PackageList::Ope"...
0x18000a16c  lea     r8, aGetlasterror; "GetLastError()"
0x18000a173  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x18000a178  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000a17d  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18000a184  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000a189  call    _CxxThrowException_0
0x18000a18f  test    ebp, 20006h
0x18000a195  jz      loc_180009FEA
0x18000a19b  jmp     loc_18000A04C
```
