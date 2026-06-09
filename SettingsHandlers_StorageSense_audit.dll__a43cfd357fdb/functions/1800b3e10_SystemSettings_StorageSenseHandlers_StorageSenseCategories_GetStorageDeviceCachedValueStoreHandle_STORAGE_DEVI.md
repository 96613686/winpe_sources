# SystemSettings::StorageSenseHandlers::StorageSenseCategories::GetStorageDeviceCachedValueStoreHandle(_STORAGE_DEVICE_TYPE,ulong,ulong,HKEY__ * *)

- ea: `0x1800b3e10`
- end: `0x1800b3f64`
- name: `?GetStorageDeviceCachedValueStoreHandle@StorageSenseCategories@StorageSenseHandlers@SystemSettings@@YAJW4_STORAGE_DEVICE_TYPE@@KKPEAPEAUHKEY__@@@Z`
- size: `340`
- prototype: `int __high(enum _STORAGE_DEVICE_TYPE, unsigned int, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b3d60`
- `0x1800b54dc`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x18000f07c`
- `0x1800b3e10`
- `0x1800b3f6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b3f22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b3f22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b3f41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b3f41`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800b3ec8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800b3ec8`

## string_xrefs

- `0x1800b3ef2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\StorageSense\Parameters\CachedSizes`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::StorageSenseCategories::GetStorageDeviceCachedValueStoreHandle(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        HKEY *a4)
{
  REGSAM v5; // edi
  signed int StorageDeviceGUIDString; // ebx
  __int64 v7; // rdx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  int v11; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v13[3]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v14[2]; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v5 = a3;
  v13[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v13[2] = *(_OWORD *)L"000-0000-000000000000}";
  v13[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v14[0] = *(_OWORD *)L"-000000000000}";
  phkResult = 0;
  *(_OWORD *)((char *)v14 + 14) = *(_OWORD *)L"000000}";
  if ( !a4 )
  {
    StorageDeviceGUIDString = -2147024809;
    v7 = 265;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\util.cpp",
      (const char *)(unsigned int)StorageDeviceGUIDString,
      v11);
    return (unsigned int)StorageDeviceGUIDString;
  }
  StorageDeviceGUIDString = SystemSettings::StorageSenseHandlers::StorageSenseCategories::GetStorageDeviceGUIDString(
                              a1,
                              a2,
                              a3,
                              v13);
  if ( StorageDeviceGUIDString < 0 )
  {
    v7 = 266;
    goto LABEL_3;
  }
  v8 = RegOpenCurrentUser(v5, &phkResult);
  StorageDeviceGUIDString = v8;
  if ( v8 > 0 )
    StorageDeviceGUIDString = (unsigned __int16)v8 | 0x80070000;
  if ( StorageDeviceGUIDString < 0 )
  {
    v7 = 274;
    goto LABEL_3;
  }
  StringCchPrintfW(
    SubKey,
    0x104u,
    L"%s\\%s",
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\Parameters\\CachedSizes",
    v13);
  v9 = RegOpenKeyExW(phkResult, SubKey, 0, v5, a4);
  StorageDeviceGUIDString = v9;
  if ( v9 > 0 )
    StorageDeviceGUIDString = (unsigned __int16)v9 | 0x80070000;
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)StorageDeviceGUIDString;
}

```

## disassembly

```asm
0x1800b3e10  push    rbp
0x1800b3e12  push    rbx
0x1800b3e13  push    rsi
0x1800b3e14  push    rdi
0x1800b3e15  lea     rbp, [rsp-1B8h]
0x1800b3e1d  sub     rsp, 2B8h
0x1800b3e24  mov     rax, cs:__security_cookie
0x1800b3e2b  xor     rax, rsp
0x1800b3e2e  mov     [rbp+1D0h+var_30], rax
0x1800b3e35  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800b3e3c  mov     rsi, r9
0x1800b3e3f  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x1800b3e46  mov     edi, r8d
0x1800b3e49  movaps  [rsp+2D0h+var_290], xmm0
0x1800b3e4e  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x1800b3e55  movaps  [rsp+2D0h+var_270], xmm0
0x1800b3e5a  movaps  [rsp+2D0h+var_280], xmm1
0x1800b3e5f  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x1800b3e66  movaps  xmmword ptr [rsp+2D0h+var_260], xmm1
0x1800b3e6b  mov     [rsp+2D0h+phkResult], 0
0x1800b3e74  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x1800b3e7b  movups  xmmword ptr [rsp+2D0h+var_260+0Eh], xmm0
0x1800b3e80  test    r9, r9
0x1800b3e83  jnz     short loc_1800B3EAA
0x1800b3e85  mov     ebx, 80070057h
0x1800b3e8a  mov     edx, 109h; void *
0x1800b3e8f  mov     rcx, [rbp+1D8h]; this
0x1800b3e96  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\coresettinghandlers"...
0x1800b3e9d  mov     r9d, ebx; char *
0x1800b3ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3ea5  jmp     loc_1800B3F47
0x1800b3eaa  lea     r9, [rsp+2D0h+var_290]
0x1800b3eaf  call    ?GetStorageDeviceGUIDString@StorageSenseCategories@StorageSenseHandlers@SystemSettings@@YAJW4_STORAGE_DEVICE_TYPE@@KIPEAG@Z; SystemSettings::StorageSenseHandlers::StorageSenseCategories::GetStorageDeviceGUIDString(_STORAGE_DEVICE_TYPE,ulong,uint,ushort *)
0x1800b3eb4  mov     ebx, eax
0x1800b3eb6  test    eax, eax
0x1800b3eb8  jns     short loc_1800B3EC1
0x1800b3eba  mov     edx, 10Ah
0x1800b3ebf  jmp     short loc_1800B3E8F
0x1800b3ec1  lea     rdx, [rsp+2D0h+phkResult]; phkResult
0x1800b3ec6  mov     ecx, edi; samDesired
0x1800b3ec8  call    cs:__imp_RegOpenCurrentUser
0x1800b3ece  mov     ebx, eax
0x1800b3ed0  test    eax, eax
0x1800b3ed2  jle     short loc_1800B3EDD
0x1800b3ed4  movzx   ebx, ax
0x1800b3ed7  or      ebx, 80070000h
0x1800b3edd  test    ebx, ebx
0x1800b3edf  jns     short loc_1800B3EE8
0x1800b3ee1  mov     edx, 112h
0x1800b3ee6  jmp     short loc_1800B3E8F
0x1800b3ee8  lea     rax, [rsp+2D0h+var_290]
0x1800b3eed  mov     edx, 104h; unsigned __int64
0x1800b3ef2  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800b3ef9  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x1800b3efe  lea     r8, aSS_0; "%s\\%s"
0x1800b3f05  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x1800b3f09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b3f0e  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x1800b3f13  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800b3f17  mov     r9d, edi; samDesired
0x1800b3f1a  mov     qword ptr [rsp+2D0h+var_2B0], rsi; phkResult
0x1800b3f1f  xor     r8d, r8d; ulOptions
0x1800b3f22  call    cs:__imp_RegOpenKeyExW
0x1800b3f28  mov     ebx, eax
0x1800b3f2a  test    eax, eax
0x1800b3f2c  jle     short loc_1800B3F37
0x1800b3f2e  movzx   ebx, ax
0x1800b3f31  or      ebx, 80070000h
0x1800b3f37  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x1800b3f3c  test    rcx, rcx
0x1800b3f3f  jz      short loc_1800B3F47
0x1800b3f41  call    cs:__imp_RegCloseKey
0x1800b3f47  mov     eax, ebx
0x1800b3f49  mov     rcx, [rbp+1D0h+var_30]
0x1800b3f50  xor     rcx, rsp; StackCookie
0x1800b3f53  call    __security_check_cookie
0x1800b3f58  add     rsp, 2B8h
0x1800b3f5f  pop     rdi
0x1800b3f60  pop     rsi
0x1800b3f61  pop     rbx
0x1800b3f62  pop     rbp
0x1800b3f63  retn
```
