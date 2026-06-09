# CAudioSessionManager::CapabilityAccessCheck(ushort const *,ulong,bool *)

- ea: `0x1800aff94`
- end: `0x1800b01ad`
- name: `?CapabilityAccessCheck@CAudioSessionManager@@CAJPEBGKPEA_N@Z`
- size: `537`
- prototype: `__int64 __fastcall(PCWSTR sourceString, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800afd64`

## callees

- `0x18001280c`
- `0x18001d8d8`
- `0x1800aff94`
- `0x1800cd8d0`
- `0x1800e9a40`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b0090`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b00d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b0090`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b00d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b0016`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b0016`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b00a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b00e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b00a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b00e7`

## string_xrefs

- `0x1800affd9`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800b0029`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800b011b`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`

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
0x1800aff94  mov     [rsp-8+arg_18], rbx
0x1800aff99  push    rbp
0x1800aff9a  push    rsi
0x1800aff9b  push    rdi
0x1800aff9c  push    r12
0x1800aff9e  push    r13
0x1800affa0  push    r14
0x1800affa2  push    r15
0x1800affa4  lea     rbp, [rsp-27h]
0x1800affa9  sub     rsp, 0B0h
0x1800affb0  mov     rax, cs:__security_cookie
0x1800affb7  xor     rax, rsp
0x1800affba  mov     [rbp+57h+var_40], rax
0x1800affbe  mov     r12, r8
0x1800affc1  mov     r14d, edx
0x1800affc4  mov     r15, rcx
0x1800affc7  xor     edi, edi
0x1800affc9  test    edx, edx
0x1800affcb  jnz     short loc_1800AFFEF
0x1800affcd  mov     rcx, [rbp+5Fh]; this
0x1800affd1  mov     ebx, 80070057h
0x1800affd6  mov     r9d, ebx; char *
0x1800affd9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800affe0  mov     edx, 457h; void *
0x1800affe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800affea  jmp     loc_1800B0184
0x1800affef  mov     [rbp+57h+var_90], rdi
0x1800afff3  lea     rcx, [rbp+57h+var_80]; string
0x1800afff7  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x1800afffc  mov     rbx, [rax]
0x1800affff  lea     rcx, [rbp+57h+var_90]
0x1800b0003  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b0008  lea     r8, [rbp+57h+var_90]
0x1800b000c  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x1800b0013  mov     rcx, rbx
0x1800b0016  call    cs:__imp_RoGetActivationFactory
0x1800b001c  mov     ebx, eax
0x1800b001e  test    eax, eax
0x1800b0020  jns     short loc_1800B003F
0x1800b0022  mov     rcx, [rbp+5Fh]; this
0x1800b0026  mov     r9d, eax; char *
0x1800b0029  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800b0030  mov     edx, 45Bh; void *
0x1800b0035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b003a  jmp     loc_1800B017B
0x1800b003f  mov     [rbp+57h+var_A0], rdi
0x1800b0043  mov     r13, [rbp+57h+var_90]
0x1800b0047  mov     rax, [r13+0]
0x1800b004b  mov     rax, [rax+38h]
0x1800b004f  mov     [rbp+57h+var_88], rax
0x1800b0053  lea     rcx, [rbp+57h+var_A0]
0x1800b0057  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b005c  mov     rsi, cs:?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x1800b0063  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b0067  mov     rbx, rdi
0x1800b006a  xor     eax, eax
0x1800b006c  inc     rbx
0x1800b006f  cmp     [rsi+rbx*2], ax
0x1800b0073  jnz     short loc_1800B006C
0x1800b0075  mov     eax, 0FFFFFFFFh
0x1800b007a  cmp     rbx, rax
0x1800b007d  jbe     short loc_1800B0096
0x1800b007f  mov     ebx, eax
0x1800b0081  xor     r9d, r9d; lpArguments
0x1800b0084  xor     r8d, r8d; nNumberOfArguments
0x1800b0087  lea     edx, [r9+1]; dwExceptionFlags
0x1800b008b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b0090  call    cs:__imp_RaiseException
0x1800b0096  lea     r9, [rbp+57h+string]; string
0x1800b009a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800b009e  mov     edx, ebx; length
0x1800b00a0  mov     rcx, rsi; sourceString
0x1800b00a3  call    cs:__imp_WindowsCreateStringReference
0x1800b00a9  mov     rbx, [rbp+57h+string]
0x1800b00ad  xor     esi, esi
0x1800b00af  inc     rdi
0x1800b00b2  cmp     [r15+rdi*2], si
0x1800b00b7  jnz     short loc_1800B00AF
0x1800b00b9  mov     eax, 0FFFFFFFFh
0x1800b00be  cmp     rdi, rax
0x1800b00c1  jbe     short loc_1800B00DA
0x1800b00c3  mov     edi, eax
0x1800b00c5  xor     r9d, r9d; lpArguments
0x1800b00c8  xor     r8d, r8d; nNumberOfArguments
0x1800b00cb  lea     edx, [r9+1]; dwExceptionFlags
0x1800b00cf  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b00d4  call    cs:__imp_RaiseException
0x1800b00da  lea     r9, [rbp+57h+var_80]; string
0x1800b00de  lea     r8, [rbp+57h+var_78]; hstringHeader
0x1800b00e2  mov     edx, edi; length
0x1800b00e4  mov     rcx, r15; sourceString
0x1800b00e7  call    cs:__imp_WindowsCreateStringReference
0x1800b00ed  lea     rax, [rbp+57h+var_A0]
0x1800b00f1  mov     [rsp+0E0h+var_B8], rax
0x1800b00f6  mov     [rsp+0E0h+var_C0], esi; int
0x1800b00fa  mov     r9d, r14d
0x1800b00fd  mov     r8, rbx
0x1800b0100  mov     rdx, [rbp+57h+var_80]
0x1800b0104  mov     rcx, r13
0x1800b0107  mov     rax, [rbp+57h+var_88]
0x1800b010b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0110  mov     ebx, eax
0x1800b0112  test    eax, eax
0x1800b0114  jns     short loc_1800B013A
0x1800b0116  mov     edx, 463h; void *
0x1800b011b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800b0122  mov     r9d, eax; char *
0x1800b0125  mov     rcx, [rbp+5Fh]; this
0x1800b0129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b012e  nop
0x1800b012f  lea     rcx, [rbp+57h+var_A0]
0x1800b0133  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b0138  jmp     short loc_1800B017B
0x1800b013a  mov     [rbp+57h+var_98], 3
0x1800b0141  mov     rcx, [rbp+57h+var_A0]
0x1800b0145  mov     rax, [rcx]
0x1800b0148  lea     rdx, [rbp+57h+var_98]
0x1800b014c  mov     rax, [rax+98h]
0x1800b0153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0158  mov     ebx, eax
0x1800b015a  test    eax, eax
0x1800b015c  jns     short loc_1800B0165
0x1800b015e  mov     edx, 466h
0x1800b0163  jmp     short loc_1800B011B
0x1800b0165  cmp     [rbp+57h+var_98], 3
0x1800b0169  setz    al
0x1800b016c  mov     [r12], al
0x1800b0170  lea     rcx, [rbp+57h+var_A0]
0x1800b0174  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b0179  mov     ebx, esi
0x1800b017b  lea     rcx, [rbp+57h+var_90]
0x1800b017f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800b0184  mov     eax, ebx
0x1800b0186  mov     rcx, [rbp+57h+var_40]
0x1800b018a  xor     rcx, rsp; StackCookie
0x1800b018d  call    __security_check_cookie
0x1800b0192  mov     rbx, [rsp+0E0h+arg_18]
0x1800b019a  add     rsp, 0B0h
0x1800b01a1  pop     r15
0x1800b01a3  pop     r14
0x1800b01a5  pop     r13
0x1800b01a7  pop     r12
0x1800b01a9  pop     rdi
0x1800b01aa  pop     rsi
0x1800b01ab  pop     rbp
0x1800b01ac  retn
```
