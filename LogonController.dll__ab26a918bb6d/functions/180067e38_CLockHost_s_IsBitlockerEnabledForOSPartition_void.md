# CLockHost::_s_IsBitlockerEnabledForOSPartition(void)

- ea: `0x180067e38`
- end: `0x180067fac`
- name: `?_s_IsBitlockerEnabledForOSPartition@CLockHost@@CA_NXZ`
- size: `372`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18008ad04`

## callees

- `0x18002ba00`
- `0x18002bc20`
- `0x180067e38`
- `0x18006c000`
- `0x18006cad0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180067e91`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180067e91`
- `KERNEL32!LoadLibraryExW` at `0x180067eed`
- `KERNEL32!LoadLibraryExW` at `0x180067eed`
- `KERNEL32!FreeLibrary` at `0x180067f70`
- `KERNEL32!FreeLibrary` at `0x180067f70`
- `KERNEL32!GetProcAddress` at `0x180067f05`
- `KERNEL32!GetProcAddress` at `0x180067f34`
- `KERNEL32!GetProcAddress` at `0x180067f50`
- `KERNEL32!GetProcAddress` at `0x180067f05`
- `KERNEL32!GetProcAddress` at `0x180067f34`
- `KERNEL32!GetProcAddress` at `0x180067f50`

## string_xrefs

- `0x180067ee6`: `fveapi.dll`
- `0x180067efb`: `FveOpenVolumeW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool CLockHost::_s_IsBitlockerEnabledForOSPartition(void)
{
  int v0; // esi
  UINT SystemWindowsDirectoryW; // eax
  BOOL v2; // esi
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  int v7; // edi
  FARPROC v8; // rax
  __int64 v10; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v11[3]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v0 = CLockHost::_s_tbOSDeviceIsLockable;
  if ( !CLockHost::_s_tbOSDeviceIsLockable )
  {
    memset_0(Buffer, 0, 0x208u);
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
    v2 = 1;
    if ( SystemWindowsDirectoryW && SystemWindowsDirectoryW < 0x104 )
    {
      Buffer[2] = 0;
      memset(v11, 0, sizeof(v11));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                  v11,
                  L"\\\\.\\%ws",
                  Buffer) >= 0 )
      {
        Library = LoadLibraryExW(L"fveapi.dll", 0, 0x800u);
        v4 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "FveOpenVolumeW");
          v10 = 0;
          if ( ((int (__fastcall *)(_QWORD, __int64, __int64 *))ProcAddress)(v11[0], 1, &v10) >= 0 )
          {
            v6 = GetProcAddress(v4, "FveIsDeviceLockable");
            v7 = ((__int64 (__fastcall *)(__int64))v6)(v10);
            v8 = GetProcAddress(v4, "FveCloseVolume");
            ((void (__fastcall *)(__int64))v8)(v10);
            v2 = v7 != 0;
          }
        }
        if ( v4 )
          FreeLibrary(v4);
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v11);
    }
    v0 = v2 + 1;
    CLockHost::_s_tbOSDeviceIsLockable = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x180067e38  push    rbp
0x180067e3a  push    rbx
0x180067e3b  push    rsi
0x180067e3c  push    rdi
0x180067e3d  push    r15
0x180067e3f  lea     rbp, [rsp-160h]
0x180067e47  sub     rsp, 260h
0x180067e4e  mov     rax, cs:__security_cookie
0x180067e55  xor     rax, rsp
0x180067e58  mov     [rbp+180h+var_30], rax
0x180067e5f  mov     r15d, 1
0x180067e65  mov     esi, cs:?_s_tbOSDeviceIsLockable@CLockHost@@0W4TRIBIT@@A; TRIBIT CLockHost::_s_tbOSDeviceIsLockable
0x180067e6b  test    esi, esi
0x180067e6d  jnz     loc_180067F89
0x180067e73  xor     edx, edx; Val
0x180067e75  mov     r8d, 208h; Size
0x180067e7b  lea     rcx, [rsp+280h+Buffer]; void *
0x180067e80  call    memset_0
0x180067e85  mov     ebx, 104h
0x180067e8a  mov     edx, ebx; uSize
0x180067e8c  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x180067e91  call    cs:__imp_GetSystemWindowsDirectoryW
0x180067e97  mov     esi, r15d
0x180067e9a  test    eax, eax
0x180067e9c  jz      loc_180067F81
0x180067ea2  cmp     eax, ebx
0x180067ea4  jnb     loc_180067F81
0x180067eaa  xor     eax, eax
0x180067eac  mov     [rsp+280h+var_23C], ax
0x180067eb1  mov     [rsp+280h+var_258], rax
0x180067eb6  mov     [rsp+280h+var_250], rax
0x180067ebb  mov     [rsp+280h+var_248], rax
0x180067ec0  lea     r8, [rsp+280h+Buffer]
0x180067ec5  lea     rdx, aWs; "\\\\.\\%ws"
0x180067ecc  lea     rcx, [rsp+280h+var_258]
0x180067ed1  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180067ed6  test    eax, eax
0x180067ed8  js      loc_180067F77
0x180067ede  xor     edx, edx; hFile
0x180067ee0  mov     r8d, 800h; dwFlags
0x180067ee6  lea     rcx, aFveapiDll; "fveapi.dll"
0x180067eed  call    cs:__imp_LoadLibraryExW
0x180067ef3  mov     rbx, rax
0x180067ef6  test    rax, rax
0x180067ef9  jz      short loc_180067F68
0x180067efb  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x180067f02  mov     rcx, rax; hModule
0x180067f05  call    cs:__imp_GetProcAddress
0x180067f0b  mov     [rsp+280h+var_260], 0
0x180067f14  lea     r8, [rsp+280h+var_260]
0x180067f19  mov     edx, r15d
0x180067f1c  mov     rcx, [rsp+280h+var_258]
0x180067f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f26  test    eax, eax
0x180067f28  js      short loc_180067F68
0x180067f2a  lea     rdx, aFveisdeviceloc; "FveIsDeviceLockable"
0x180067f31  mov     rcx, rbx; hModule
0x180067f34  call    cs:__imp_GetProcAddress
0x180067f3a  mov     rcx, [rsp+280h+var_260]
0x180067f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f44  mov     edi, eax
0x180067f46  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x180067f4d  mov     rcx, rbx; hModule
0x180067f50  call    cs:__imp_GetProcAddress
0x180067f56  mov     rcx, [rsp+280h+var_260]
0x180067f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f60  xor     esi, esi
0x180067f62  test    edi, edi
0x180067f64  setnz   sil
0x180067f68  test    rbx, rbx
0x180067f6b  jz      short loc_180067F77
0x180067f6d  mov     rcx, rbx; hLibModule
0x180067f70  call    cs:__imp_FreeLibrary
0x180067f76  nop
0x180067f77  lea     rcx, [rsp+280h+var_258]
0x180067f7c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180067f81  inc     esi
0x180067f83  mov     cs:?_s_tbOSDeviceIsLockable@CLockHost@@0W4TRIBIT@@A, esi; TRIBIT CLockHost::_s_tbOSDeviceIsLockable
0x180067f89  cmp     esi, r15d
0x180067f8c  setz    al
0x180067f8f  mov     rcx, [rbp+180h+var_30]
0x180067f96  xor     rcx, rsp; StackCookie
0x180067f99  call    __security_check_cookie
0x180067f9e  add     rsp, 260h
0x180067fa5  pop     r15
0x180067fa7  pop     rdi
0x180067fa8  pop     rsi
0x180067fa9  pop     rbx
0x180067faa  pop     rbp
0x180067fab  retn
```
