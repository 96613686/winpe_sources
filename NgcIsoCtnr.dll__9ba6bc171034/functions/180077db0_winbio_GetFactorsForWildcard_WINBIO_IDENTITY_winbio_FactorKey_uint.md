# winbio::GetFactorsForWildcard(_WINBIO_IDENTITY *,winbio::FactorKey,uint *)

- ea: `0x180077db0`
- end: `0x180077fef`
- name: `?GetFactorsForWildcard@winbio@@YAJPEAU_WINBIO_IDENTITY@@W4FactorKey@1@PEAI@Z`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180077a14`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18000d62c`
- `0x180011c9c`
- `0x18001cbe8`
- `0x18001cee4`
- `0x180069140`
- `0x180077db0`
- `0x180077ff8`
- `0x180078174`
- `0x1800781c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077eda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077eda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077fb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077fb8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077f56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180077f56`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180077fa3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180077fa3`

## string_xrefs

- `0x180077dee`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180077e87`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x180077eee`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winbio::GetFactorsForWildcard(winbio *a1, struct _WINBIO_IDENTITY *a2, _DWORD *a3)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  int KeyValueFromFactorKey; // ebx
  int WinBioRegistryLocation; // eax
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  int v10; // ebx
  DWORD v11; // esi
  DWORD i; // edx
  LSTATUS v13; // eax
  HKEY v14; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  LPCWSTR lpValue; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = (unsigned int)a2;
  if ( !a1 )
  {
    v5 = 460;
LABEL_3:
    KeyValueFromFactorKey = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)KeyValueFromFactorKey,
      phkResult);
    return (unsigned int)KeyValueFromFactorKey;
  }
  if ( !a3 )
  {
    v5 = 461;
    goto LABEL_3;
  }
  LOBYTE(a2) = 1;
  KeyValueFromFactorKey = winbio::ValidateIdentity(a1, a2, (bool)a3);
  if ( KeyValueFromFactorKey < 0 )
  {
    v5 = 463;
    goto LABEL_4;
  }
  *a3 = 0;
  lpValue = &LocaleName;
  KeyValueFromFactorKey = winbio::GetKeyValueFromFactorKey(v4, &lpValue);
  if ( KeyValueFromFactorKey < 0 )
  {
    v5 = 468;
    goto LABEL_4;
  }
  v23[0] = 0;
  v23[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23[0]) = 0;
  WinBioRegistryLocation = GetWinBioRegistryLocation((__int64)v23);
  KeyValueFromFactorKey = WinBioRegistryLocation;
  if ( WinBioRegistryLocation >= 0 )
  {
    std::wstring::append(v23, L"AccountInfo\\");
    hkey = 0;
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hkey);
    if ( v9 )
    {
      KeyValueFromFactorKey = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x1DB,
                                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
                                (const char *)v9,
                                phkResulta);
    }
    else
    {
      v10 = 0;
      v11 = 0;
      memset_0(SubKey, 0, 0x208u);
      for ( i = 0; ; i = v11 )
      {
        cchName = 260;
        v13 = RegEnumKeyExW(hkey, i, SubKey, &cchName, 0, 0, 0, 0);
        v14 = hkey;
        if ( v13 )
          break;
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(hkey, SubKey, lpValue, 0x20000010u, 0, &pvData, &pcbData) )
          v10 |= pvData;
        ++v11;
        memset_0(SubKey, 0, 0x208u);
      }
      *a3 = v10;
      RegCloseKey(v14);
      hkey = 0;
      KeyValueFromFactorKey = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
      (const char *)(unsigned int)WinBioRegistryLocation,
      phkResult);
  }
  std::wstring::_Tidy_deallocate(v23);
  return (unsigned int)KeyValueFromFactorKey;
}

```

## disassembly

```asm
0x180077db0  push    rbp
0x180077db2  push    rbx
0x180077db3  push    rsi
0x180077db4  push    rdi
0x180077db5  push    r14
0x180077db7  lea     rbp, [rsp-1A0h]
0x180077dbf  sub     rsp, 2A0h
0x180077dc6  mov     rax, cs:__security_cookie
0x180077dcd  xor     rax, rsp
0x180077dd0  mov     [rbp+1C0h+var_30], rax
0x180077dd7  mov     rdi, r8
0x180077dda  mov     esi, edx
0x180077ddc  xor     r14d, r14d
0x180077ddf  test    rcx, rcx
0x180077de2  jnz     short loc_180077E09
0x180077de4  mov     edx, 1CCh; void *
0x180077de9  mov     ebx, 80004003h
0x180077dee  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x180077df5  mov     r9d, ebx; char *
0x180077df8  mov     rcx, [rbp+1C8h]; this
0x180077dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077e04  jmp     loc_180077FD0
0x180077e09  test    rdi, rdi
0x180077e0c  jnz     short loc_180077E15
0x180077e0e  mov     edx, 1CDh
0x180077e13  jmp     short loc_180077DE9
0x180077e15  mov     dl, 1; struct _WINBIO_IDENTITY *
0x180077e17  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x180077e1c  mov     ebx, eax
0x180077e1e  test    eax, eax
0x180077e20  jns     short loc_180077E29
0x180077e22  mov     edx, 1CFh
0x180077e27  jmp     short loc_180077DEE
0x180077e29  mov     [rdi], r14d
0x180077e2c  lea     rax, LocaleName
0x180077e33  mov     [rsp+2C0h+lpValue], rax
0x180077e38  lea     rdx, [rsp+2C0h+lpValue]
0x180077e3d  mov     ecx, esi
0x180077e3f  call    ?GetKeyValueFromFactorKey@winbio@@YAJW4FactorKey@1@PEAPEBG@Z; winbio::GetKeyValueFromFactorKey(winbio::FactorKey,ushort const * *)
0x180077e44  mov     ebx, eax
0x180077e46  test    eax, eax
0x180077e48  jns     short loc_180077E51
0x180077e4a  mov     edx, 1D4h
0x180077e4f  jmp     short loc_180077DEE
0x180077e51  xorps   xmm0, xmm0
0x180077e54  movups  [rsp+2C0h+var_260], xmm0
0x180077e59  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180077e61  movdqu  [rsp+2C0h+var_250], xmm1
0x180077e67  mov     word ptr [rsp+2C0h+var_260], r14w
0x180077e6d  lea     rcx, [rsp+2C0h+var_260]
0x180077e72  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180077e77  mov     ebx, eax
0x180077e79  test    eax, eax
0x180077e7b  jns     short loc_180077E9D
0x180077e7d  mov     rcx, [rbp+1C8h]; this
0x180077e84  mov     r9d, eax; char *
0x180077e87  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x180077e8e  mov     edx, 1D7h; void *
0x180077e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077e98  jmp     loc_180077FC6
0x180077e9d  lea     rdx, aAccountinfo; "AccountInfo\\"
0x180077ea4  lea     rcx, [rsp+2C0h+var_260]
0x180077ea9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180077eae  mov     [rsp+2C0h+hkey], r14
0x180077eb3  lea     rcx, [rsp+2C0h+var_260]
0x180077eb8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180077ebd  mov     rdx, rax; lpSubKey
0x180077ec0  lea     rax, [rsp+2C0h+hkey]
0x180077ec5  mov     [rsp+2C0h+phkResult], rax; unsigned int
0x180077eca  mov     r9d, 20019h; samDesired
0x180077ed0  xor     r8d, r8d; ulOptions
0x180077ed3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077eda  call    cs:__imp_RegOpenKeyExW
0x180077ee0  test    eax, eax
0x180077ee2  jz      short loc_180077F06
0x180077ee4  mov     rcx, [rbp+1C8h]; this
0x180077eeb  mov     r9d, eax; char *
0x180077eee  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x180077ef5  mov     edx, 1DBh; void *
0x180077efa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180077eff  mov     ebx, eax
0x180077f01  jmp     loc_180077FC6
0x180077f06  mov     ebx, r14d
0x180077f09  mov     esi, r14d
0x180077f0c  xor     edx, edx; Val
0x180077f0e  mov     r8d, 208h; Size
0x180077f14  lea     rcx, [rbp+1C0h+SubKey]; void *
0x180077f18  call    memset_0
0x180077f1d  xor     edx, edx
0x180077f1f  jmp     short loc_180077F79
0x180077f21  mov     [rsp+2C0h+var_270], r14d
0x180077f26  mov     [rsp+2C0h+var_26C], 4
0x180077f2e  lea     rax, [rsp+2C0h+var_26C]
0x180077f33  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180077f38  lea     rax, [rsp+2C0h+var_270]
0x180077f3d  mov     [rsp+2C0h+pvData], rax; pvData
0x180077f42  mov     [rsp+2C0h+phkResult], r14; pdwType
0x180077f47  mov     r9d, 20000010h; dwFlags
0x180077f4d  mov     r8, [rsp+2C0h+lpValue]; lpValue
0x180077f52  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x180077f56  call    cs:__imp_RegGetValueW
0x180077f5c  test    eax, eax
0x180077f5e  jnz     short loc_180077F64
0x180077f60  or      ebx, [rsp+2C0h+var_270]
0x180077f64  inc     esi
0x180077f66  xor     edx, edx; Val
0x180077f68  mov     r8d, 208h; Size
0x180077f6e  lea     rcx, [rbp+1C0h+SubKey]; void *
0x180077f72  call    memset_0
0x180077f77  mov     edx, esi; dwIndex
0x180077f79  mov     [rsp+2C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180077f7e  mov     [rsp+2C0h+pcbData], r14; lpcchClass
0x180077f83  mov     [rsp+2C0h+pvData], r14; lpClass
0x180077f88  mov     [rsp+2C0h+phkResult], r14; lpReserved
0x180077f8d  mov     [rsp+2C0h+cchName], 104h
0x180077f95  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x180077f9a  lea     r8, [rbp+1C0h+SubKey]; lpName
0x180077f9e  mov     rcx, [rsp+2C0h+hkey]; hKey
0x180077fa3  call    cs:__imp_RegEnumKeyExW
0x180077fa9  mov     rcx, [rsp+2C0h+hkey]; hKey
0x180077fae  test    eax, eax
0x180077fb0  jz      loc_180077F21
0x180077fb6  mov     [rdi], ebx
0x180077fb8  call    cs:__imp_RegCloseKey
0x180077fbe  mov     [rsp+2C0h+hkey], r14
0x180077fc3  mov     ebx, r14d
0x180077fc6  lea     rcx, [rsp+2C0h+var_260]
0x180077fcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180077fd0  mov     eax, ebx
0x180077fd2  mov     rcx, [rbp+1C0h+var_30]
0x180077fd9  xor     rcx, rsp; StackCookie
0x180077fdc  call    __security_check_cookie
0x180077fe1  add     rsp, 2A0h
0x180077fe8  pop     r14
0x180077fea  pop     rdi
0x180077feb  pop     rsi
0x180077fec  pop     rbx
0x180077fed  pop     rbp
0x180077fee  retn
```
