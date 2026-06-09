# CAudioSessionManager::CapabilityAccessCheck(ushort const *,ulong,bool *)

- ea: `0x1800b1c84`
- end: `0x1800b1e9d`
- name: `?CapabilityAccessCheck@CAudioSessionManager@@CAJPEBGKPEA_N@Z`
- size: `537`
- prototype: `__int64 __fastcall(PCWSTR sourceString, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b1a54`

## callees

- `0x1800126bc`
- `0x18001d788`
- `0x1800b1c84`
- `0x1800cf8c0`
- `0x1800ea1c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1d80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1dc4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1d80`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1dc4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b1d06`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b1d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1dd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1d93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1dd7`

## string_xrefs

- `0x1800b1cc9`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800b1d19`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800b1e0b`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAudioSessionManager::CapabilityAccessCheck(
        PCWSTR sourceString,
        const unsigned __int16 *a2,
        bool *a3)
{
  unsigned int v4; // r14d
  unsigned int v6; // ebx
  __int64 v7; // rbx
  int ActivationFactory; // eax
  __int64 v9; // r13
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rbx
  HSTRING v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-69h]
  __int64 v17; // [rsp+40h] [rbp-49h] BYREF
  int v18; // [rsp+48h] [rbp-41h] BYREF
  __int64 v19; // [rsp+50h] [rbp-39h] BYREF
  __int64 (__fastcall *v20)(__int64, HSTRING, HSTRING, _QWORD); // [rsp+58h] [rbp-31h]
  HSTRING v21; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER v22; // [rsp+68h] [rbp-21h] BYREF
  HSTRING string; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = (unsigned int)a2;
  if ( (_DWORD)a2 )
  {
    v19 = 0;
    v7 = *(_QWORD *)Windows::Internal::StringReference::StringReference(&v21, (const unsigned __int16 (*)[51])a2);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v19);
    v6 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v17 = 0;
      v9 = v19;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _QWORD))(*(_QWORD *)v19 + 56LL);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( c_szCapabilityMicrophone[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        LODWORD(v11) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(c_szCapabilityMicrophone, v11, &hstringHeader, &string);
      v12 = string;
      do
        ++v10;
      while ( sourceString[v10] );
      if ( v10 > 0xFFFFFFFF )
      {
        LODWORD(v10) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(sourceString, v10, &v22, &v21);
      v13 = v20(v9, v21, v12, v4);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v18 = 3;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 152LL))(v17, &v18);
        v6 = v13;
        if ( v13 >= 0 )
        {
          *a3 = v18 == 3;
          Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
          v6 = 0;
          goto LABEL_19;
        }
        v14 = 1126;
      }
      else
      {
        v14 = 1123;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
        (const char *)(unsigned int)v13,
        0);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45B,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v16);
    }
LABEL_19:
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
    return v6;
  }
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x457,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosessionmanager.cpp",
    (const char *)0x80070057LL,
    v16);
  return v6;
}

```

## disassembly

```asm
0x1800b1c84  mov     [rsp-8+arg_18], rbx
0x1800b1c89  push    rbp
0x1800b1c8a  push    rsi
0x1800b1c8b  push    rdi
0x1800b1c8c  push    r12
0x1800b1c8e  push    r13
0x1800b1c90  push    r14
0x1800b1c92  push    r15
0x1800b1c94  lea     rbp, [rsp-27h]
0x1800b1c99  sub     rsp, 0B0h
0x1800b1ca0  mov     rax, cs:__security_cookie
0x1800b1ca7  xor     rax, rsp
0x1800b1caa  mov     [rbp+57h+var_40], rax
0x1800b1cae  mov     r12, r8
0x1800b1cb1  mov     r14d, edx
0x1800b1cb4  mov     r15, rcx
0x1800b1cb7  xor     edi, edi
0x1800b1cb9  test    edx, edx
0x1800b1cbb  jnz     short loc_1800B1CDF
0x1800b1cbd  mov     rcx, [rbp+5Fh]; this
0x1800b1cc1  mov     ebx, 80070057h
0x1800b1cc6  mov     r9d, ebx; char *
0x1800b1cc9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800b1cd0  mov     edx, 457h; void *
0x1800b1cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1cda  jmp     loc_1800B1E74
0x1800b1cdf  mov     [rbp+57h+var_90], rdi
0x1800b1ce3  lea     rcx, [rbp+57h+var_80]; string
0x1800b1ce7  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x1800b1cec  mov     rbx, [rax]
0x1800b1cef  lea     rcx, [rbp+57h+var_90]
0x1800b1cf3  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b1cf8  lea     r8, [rbp+57h+var_90]
0x1800b1cfc  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x1800b1d03  mov     rcx, rbx
0x1800b1d06  call    cs:__imp_RoGetActivationFactory
0x1800b1d0c  mov     ebx, eax
0x1800b1d0e  test    eax, eax
0x1800b1d10  jns     short loc_1800B1D2F
0x1800b1d12  mov     rcx, [rbp+5Fh]; this
0x1800b1d16  mov     r9d, eax; char *
0x1800b1d19  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800b1d20  mov     edx, 45Bh; void *
0x1800b1d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1d2a  jmp     loc_1800B1E6B
0x1800b1d2f  mov     [rbp+57h+var_A0], rdi
0x1800b1d33  mov     r13, [rbp+57h+var_90]
0x1800b1d37  mov     rax, [r13+0]
0x1800b1d3b  mov     rax, [rax+38h]
0x1800b1d3f  mov     [rbp+57h+var_88], rax
0x1800b1d43  lea     rcx, [rbp+57h+var_A0]
0x1800b1d47  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b1d4c  mov     rsi, cs:?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x1800b1d53  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b1d57  mov     rbx, rdi
0x1800b1d5a  xor     eax, eax
0x1800b1d5c  inc     rbx
0x1800b1d5f  cmp     [rsi+rbx*2], ax
0x1800b1d63  jnz     short loc_1800B1D5C
0x1800b1d65  mov     eax, 0FFFFFFFFh
0x1800b1d6a  cmp     rbx, rax
0x1800b1d6d  jbe     short loc_1800B1D86
0x1800b1d6f  mov     ebx, eax
0x1800b1d71  xor     r9d, r9d; lpArguments
0x1800b1d74  xor     r8d, r8d; nNumberOfArguments
0x1800b1d77  lea     edx, [r9+1]; dwExceptionFlags
0x1800b1d7b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b1d80  call    cs:__imp_RaiseException
0x1800b1d86  lea     r9, [rbp+57h+string]; string
0x1800b1d8a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800b1d8e  mov     edx, ebx; length
0x1800b1d90  mov     rcx, rsi; sourceString
0x1800b1d93  call    cs:__imp_WindowsCreateStringReference
0x1800b1d99  mov     rbx, [rbp+57h+string]
0x1800b1d9d  xor     esi, esi
0x1800b1d9f  inc     rdi
0x1800b1da2  cmp     [r15+rdi*2], si
0x1800b1da7  jnz     short loc_1800B1D9F
0x1800b1da9  mov     eax, 0FFFFFFFFh
0x1800b1dae  cmp     rdi, rax
0x1800b1db1  jbe     short loc_1800B1DCA
0x1800b1db3  mov     edi, eax
0x1800b1db5  xor     r9d, r9d; lpArguments
0x1800b1db8  xor     r8d, r8d; nNumberOfArguments
0x1800b1dbb  lea     edx, [r9+1]; dwExceptionFlags
0x1800b1dbf  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b1dc4  call    cs:__imp_RaiseException
0x1800b1dca  lea     r9, [rbp+57h+var_80]; string
0x1800b1dce  lea     r8, [rbp+57h+var_78]; hstringHeader
0x1800b1dd2  mov     edx, edi; length
0x1800b1dd4  mov     rcx, r15; sourceString
0x1800b1dd7  call    cs:__imp_WindowsCreateStringReference
0x1800b1ddd  lea     rax, [rbp+57h+var_A0]
0x1800b1de1  mov     [rsp+0E0h+var_B8], rax
0x1800b1de6  mov     [rsp+0E0h+var_C0], esi; int
0x1800b1dea  mov     r9d, r14d
0x1800b1ded  mov     r8, rbx
0x1800b1df0  mov     rdx, [rbp+57h+var_80]
0x1800b1df4  mov     rcx, r13
0x1800b1df7  mov     rax, [rbp+57h+var_88]
0x1800b1dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e00  mov     ebx, eax
0x1800b1e02  test    eax, eax
0x1800b1e04  jns     short loc_1800B1E2A
0x1800b1e06  mov     edx, 463h; void *
0x1800b1e0b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800b1e12  mov     r9d, eax; char *
0x1800b1e15  mov     rcx, [rbp+5Fh]; this
0x1800b1e19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1e1e  nop
0x1800b1e1f  lea     rcx, [rbp+57h+var_A0]
0x1800b1e23  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b1e28  jmp     short loc_1800B1E6B
0x1800b1e2a  mov     [rbp+57h+var_98], 3
0x1800b1e31  mov     rcx, [rbp+57h+var_A0]
0x1800b1e35  mov     rax, [rcx]
0x1800b1e38  lea     rdx, [rbp+57h+var_98]
0x1800b1e3c  mov     rax, [rax+98h]
0x1800b1e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e48  mov     ebx, eax
0x1800b1e4a  test    eax, eax
0x1800b1e4c  jns     short loc_1800B1E55
0x1800b1e4e  mov     edx, 466h
0x1800b1e53  jmp     short loc_1800B1E0B
0x1800b1e55  cmp     [rbp+57h+var_98], 3
0x1800b1e59  setz    al
0x1800b1e5c  mov     [r12], al
0x1800b1e60  lea     rcx, [rbp+57h+var_A0]
0x1800b1e64  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b1e69  mov     ebx, esi
0x1800b1e6b  lea     rcx, [rbp+57h+var_90]
0x1800b1e6f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b1e74  mov     eax, ebx
0x1800b1e76  mov     rcx, [rbp+57h+var_40]
0x1800b1e7a  xor     rcx, rsp; StackCookie
0x1800b1e7d  call    __security_check_cookie
0x1800b1e82  mov     rbx, [rsp+0E0h+arg_18]
0x1800b1e8a  add     rsp, 0B0h
0x1800b1e91  pop     r15
0x1800b1e93  pop     r14
0x1800b1e95  pop     r13
0x1800b1e97  pop     r12
0x1800b1e99  pop     rdi
0x1800b1e9a  pop     rsi
0x1800b1e9b  pop     rbp
0x1800b1e9c  retn
```
