# TpmPolicySession::SetTpmState(TpmPolicySession::TpmState)

- ea: `0x180050b54`
- end: `0x180050d0a`
- name: `?SetTpmState@TpmPolicySession@@YAJW4TpmState@1@@Z`
- size: `438`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f218`
- `0x18004faf0`

## callees

- `0x18000782c`
- `0x18000e960`
- `0x180010aec`
- `0x1800138c0`
- `0x180048304`
- `0x180050b54`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180050c3d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180050c3d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050cac`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050cac`

## string_xrefs

- `0x180050ba4`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmsupport.cpp`
- `0x180050bfb`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmsupport.cpp`
- `0x180050c53`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmsupport.cpp`
- `0x180050cbe`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmsupport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmPolicySession::SetTpmState(unsigned int a1)
{
  int WinBioRegistryLocation; // eax
  unsigned int v3; // edi
  const char *v4; // r9
  __int64 result; // rax
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  unsigned int lpDataa; // [rsp+20h] [rbp-48h]
  unsigned int Data; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    *(_OWORD *)lpSubKey = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpSubKey[0]) = 0;
    WinBioRegistryLocation = GetWinBioRegistryLocation(lpSubKey);
    v3 = WinBioRegistryLocation;
    if ( WinBioRegistryLocation < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmsupport.cpp",
        (const char *)(unsigned int)WinBioRegistryLocation,
        lpData);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
      return v3;
    }
    std::wstring::append(lpSubKey, L"SensorInfo\\");
    if ( a1 < 2 )
    {
      Data = a1;
      v9 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v9 = lpSubKey[0];
      v10 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v9, L"TpmSupported", 4u, &Data, 4u);
      if ( v10 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x63,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmsupport.cpp",
                (const char *)v10,
                lpDataa);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        return v11;
      }
    }
    else
    {
      if ( a1 != -1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x67,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmsupport.cpp",
          (const char *)0x80070057LL,
          lpData);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        return 2147942487LL;
      }
      v6 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v6 = lpSubKey[0];
      v7 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v6, L"TpmSupported");
      if ( v7 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x54,
               (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmsupport.cpp",
               (const char *)v7,
               lpData);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        return v8;
      }
    }
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6C,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmsupport.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180050b54  mov     [rsp+arg_8], rbx
0x180050b59  push    rdi
0x180050b5a  sub     rsp, 60h
0x180050b5e  mov     rax, cs:__security_cookie
0x180050b65  xor     rax, rsp
0x180050b68  mov     [rsp+68h+var_10], rax
0x180050b6d  mov     ebx, ecx
0x180050b6f  xorps   xmm0, xmm0
0x180050b72  movups  xmmword ptr [rsp+68h+lpSubKey], xmm0
0x180050b77  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180050b7f  movdqu  [rsp+68h+var_20], xmm1
0x180050b85  xor     eax, eax
0x180050b87  mov     word ptr [rsp+68h+lpSubKey], ax
0x180050b8c  lea     rcx, [rsp+68h+lpSubKey]
0x180050b91  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x180050b96  mov     edi, eax
0x180050b98  test    eax, eax
0x180050b9a  jns     short loc_180050BC7
0x180050b9c  mov     rcx, [rsp+68h]; this
0x180050ba1  mov     r9d, eax; char *
0x180050ba4  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\biometrics\\serv"...
0x180050bab  mov     edx, 49h ; 'I'; void *
0x180050bb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050bb5  nop
0x180050bb6  lea     rcx, [rsp+68h+lpSubKey]
0x180050bbb  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180050bc0  mov     eax, edi
0x180050bc2  jmp     loc_180050CF1
0x180050bc7  lea     rdx, aSensorinfo; "SensorInfo\\"
0x180050bce  lea     rcx, [rsp+68h+lpSubKey]; Src
0x180050bd3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180050bd8  test    ebx, ebx
0x180050bda  jz      loc_180050C74
0x180050be0  cmp     ebx, 1
0x180050be3  jz      loc_180050C74
0x180050be9  cmp     ebx, 0FFFFFFFFh
0x180050bec  jz      short loc_180050C1E
0x180050bee  mov     rcx, [rsp+68h]; this
0x180050bf3  mov     ebx, 80070057h
0x180050bf8  mov     r9d, ebx; char *
0x180050bfb  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\biometrics\\serv"...
0x180050c02  mov     edx, 67h ; 'g'; void *
0x180050c07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c0c  nop
0x180050c0d  lea     rcx, [rsp+68h+lpSubKey]
0x180050c12  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180050c17  mov     eax, ebx
0x180050c19  jmp     loc_180050CF1
0x180050c1e  lea     rdx, [rsp+68h+lpSubKey]
0x180050c23  cmp     qword ptr [rsp+68h+var_20+8], 7
0x180050c29  cmova   rdx, [rsp+68h+lpSubKey]; lpSubKey
0x180050c2f  lea     r8, aTpmsupported; "TpmSupported"
0x180050c36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050c3d  call    cs:__imp_RegDeleteKeyValueW
0x180050c43  test    eax, eax
0x180050c45  jz      loc_180050CDF
0x180050c4b  mov     rcx, [rsp+68h]; this
0x180050c50  mov     r9d, eax; char *
0x180050c53  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\biometrics\\serv"...
0x180050c5a  mov     edx, 54h ; 'T'; void *
0x180050c5f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180050c64  mov     ebx, eax
0x180050c66  lea     rcx, [rsp+68h+lpSubKey]
0x180050c6b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180050c70  mov     eax, ebx
0x180050c72  jmp     short loc_180050CF1
0x180050c74  mov     [rsp+68h+Data], ebx
0x180050c78  lea     rdx, [rsp+68h+lpSubKey]
0x180050c7d  cmp     qword ptr [rsp+68h+var_20+8], 7
0x180050c83  cmova   rdx, [rsp+68h+lpSubKey]; lpSubKey
0x180050c89  mov     r9d, 4; dwType
0x180050c8f  mov     [rsp+68h+cbData], r9d; cbData
0x180050c94  lea     rax, [rsp+68h+Data]
0x180050c99  mov     [rsp+68h+lpData], rax; unsigned int
0x180050c9e  lea     r8, aTpmsupported; "TpmSupported"
0x180050ca5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050cac  call    cs:__imp_RegSetKeyValueW
0x180050cb2  test    eax, eax
0x180050cb4  jz      short loc_180050CDF
0x180050cb6  mov     rcx, [rsp+68h]; this
0x180050cbb  mov     r9d, eax; char *
0x180050cbe  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\biometrics\\serv"...
0x180050cc5  mov     edx, 63h ; 'c'; void *
0x180050cca  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180050ccf  mov     ebx, eax
0x180050cd1  lea     rcx, [rsp+68h+lpSubKey]
0x180050cd6  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180050cdb  mov     eax, ebx
0x180050cdd  jmp     short loc_180050CF1
0x180050cdf  lea     rcx, [rsp+68h+lpSubKey]
0x180050ce4  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180050ce9  xor     eax, eax
0x180050ceb  jmp     short loc_180050CF1
0x180050ced  mov     eax, [rsp+68h+Data]
0x180050cf1  mov     rcx, [rsp+68h+var_10]
0x180050cf6  xor     rcx, rsp; StackCookie
0x180050cf9  call    __security_check_cookie
0x180050cfe  mov     rbx, [rsp+68h+arg_8]
0x180050d03  add     rsp, 60h
0x180050d07  pop     rdi
0x180050d08  retn
```
