# AppReadiness::Storage::PackageList::OpenUserQueueRoot(AppReadiness::User const *,ulong)

- ea: `0x180009e10`
- end: `0x180009f43`
- name: `?OpenUserQueueRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z`
- size: `307`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, REGSAM)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800097d0`
- `0x18000a2c8`
- `0x18000b530`
- `0x18000bb90`
- `0x18001b370`
- `0x180039d8c`

## callees

- `0x180009d60`
- `0x180009e10`
- `0x180009f50`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009ee0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009ee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ec1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009e8e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009e8e`

## string_xrefs

- `0x180009eef`: `onecoreuap\shell\appreadiness\src\core\packagelist.cpp`
- `0x180009efb`: `AppReadiness::Storage::PackageList::OpenUserQueueRoot`
- `0x180009f02`: `RegCreateKeyEx(userRootKey.Get(), c_UserQueueKeyName, 0, nullptr, 0, accessRights, nullptr, key.GetAddressOf(), nullptr)`

## pseudocode

```c
_QWORD *__fastcall AppReadiness::Storage::PackageList::OpenUserQueueRoot(_QWORD *a1, __int64 a2, REGSAM a3)
{
  HKEY *phkResult; // rsi
  HKEY v6; // rax
  int Key; // eax
  bool v8; // sf
  int LastError; // eax
  void **v11; // [rsp+58h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-48h]
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-40h] BYREF

  *a1 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  phkResult = (HKEY *)(a1 + 1);
  a1[1] = 0;
  AppReadiness::Storage::PackageList::OpenUserMachineRoot(&v11);
  v6 = hKey;
  if ( hKey )
  {
    Key = RegCreateKeyExW(hKey, L"Queue", 0, 0, 0, a3, 0, phkResult, 0);
    v8 = Key < 0;
    if ( Key > 0 )
    {
      Key = (unsigned __int16)Key | 0x80070000;
      v8 = Key < 0;
    }
    if ( v8 )
    {
LABEL_11:
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Key,
        "RegCreateKeyEx(userRootKey.Get(), c_UserQueueKeyName, 0, nullptr, 0, accessRights, nullptr, key.GetAddressOf(), nullptr)",
        "AppReadiness::Storage::PackageList::OpenUserQueueRoot",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packagelist.cpp",
        289);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v6 = hKey;
  }
  v11 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  if ( v6
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v11) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    goto LABEL_11;
  }
  return a1;
}

```

## disassembly

```asm
0x180009e10  mov     [rsp+arg_8], rbx
0x180009e15  mov     [rsp+arg_10], rbp
0x180009e1a  mov     [rsp+arg_0], rcx
0x180009e1f  push    rsi
0x180009e20  push    rdi
0x180009e21  push    r14
0x180009e23  sub     rsp, 90h
0x180009e2a  mov     edi, r8d
0x180009e2d  mov     rbx, rcx
0x180009e30  xor     r14d, r14d
0x180009e33  mov     [rsp+0A8h+var_58], r14d
0x180009e38  lea     rbp, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180009e3f  mov     [rcx], rbp
0x180009e42  lea     rsi, [rcx+8]
0x180009e46  mov     [rsi], r14
0x180009e49  mov     [rsp+0A8h+var_58], 1
0x180009e51  lea     rcx, [rsp+0A8h+var_50]
0x180009e56  call    ?OpenUserMachineRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserMachineRoot(AppReadiness::User const *,ulong)
0x180009e5b  nop
0x180009e5c  mov     rax, [rsp+0A8h+hKey]
0x180009e61  test    rax, rax
0x180009e64  jz      short loc_180009EA9
0x180009e66  mov     [rsp+0A8h+lpdwDisposition], r14; lpdwDisposition
0x180009e6b  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x180009e70  mov     [rsp+0A8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180009e75  mov     [rsp+0A8h+samDesired], edi; samDesired
0x180009e79  mov     [rsp+0A8h+dwOptions], r14d; dwOptions
0x180009e7e  xor     r9d, r9d; lpClass
0x180009e81  xor     r8d, r8d; Reserved
0x180009e84  lea     rdx, aQueue; "Queue"
0x180009e8b  mov     rcx, rax; hKey
0x180009e8e  call    cs:__imp_RegCreateKeyExW
0x180009e94  test    eax, eax
0x180009e96  jle     short loc_180009EA2
0x180009e98  movzx   eax, ax
0x180009e9b  or      eax, 80070000h
0x180009ea0  test    eax, eax
0x180009ea2  js      short loc_180009EE7
0x180009ea4  mov     rax, [rsp+0A8h+hKey]
0x180009ea9  mov     [rsp+0A8h+var_50], rbp
0x180009eae  test    rax, rax
0x180009eb1  jz      short loc_180009F27
0x180009eb3  lea     rcx, [rsp+0A8h+var_50]
0x180009eb8  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180009ebd  test    al, al
0x180009ebf  jnz     short loc_180009F27
0x180009ec1  call    cs:__imp_GetLastError
0x180009ec7  test    eax, eax
0x180009ec9  jle     short loc_180009ED3
0x180009ecb  movzx   eax, ax
0x180009ece  or      eax, 80070000h
0x180009ed3  xor     r9d, r9d; lpArguments
0x180009ed6  xor     r8d, r8d; nNumberOfArguments
0x180009ed9  mov     edx, 1; dwExceptionFlags
0x180009ede  mov     ecx, eax; dwExceptionCode
0x180009ee0  call    cs:__imp_RaiseException
0x180009ee6  nop
0x180009ee7  mov     [rsp+0A8h+samDesired], 121h; int
0x180009eef  lea     rcx, aOnecoreuapShel_10; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009ef6  mov     qword ptr [rsp+0A8h+dwOptions], rcx; char *
0x180009efb  lea     r9, aAppreadinessSt_7; "AppReadiness::Storage::PackageList::Ope"...
0x180009f02  lea     r8, aRegcreatekeyex_0; "RegCreateKeyEx(userRootKey.Get(), c_Use"...
0x180009f09  mov     edx, eax; int
0x180009f0b  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180009f10  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009f15  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180009f1c  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180009f21  call    _CxxThrowException_0
0x180009f27  mov     rax, rbx
0x180009f2a  lea     r11, [rsp+0A8h+var_18]
0x180009f32  mov     rbx, [r11+28h]
0x180009f36  mov     rbp, [r11+30h]
0x180009f3a  mov     rsp, r11
0x180009f3d  pop     r14
0x180009f3f  pop     rdi
0x180009f40  pop     rsi
0x180009f41  retn
```
