# InitPlatformInfo

- ea: `0x140006de4`
- end: `0x140007046`
- name: `InitPlatformInfo`
- size: `610`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007330`

## callees

- `0x140001008`
- `0x140006c94`
- `0x140006de4`
- `0x140007735`
- `0x140007750`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140006e26`
- `ntdll!RtlInitUnicodeString` at `0x140006e26`
- `ntdll!NtQueryLicenseValue` at `0x140006e4a`
- `ntdll!NtQueryLicenseValue` at `0x140006e4a`
- `ntdll!RtlGetVersion` at `0x140006e86`
- `ntdll!RtlGetVersion` at `0x140006e86`

## string_xrefs

- `0x140006ecb`: `onecore\xbox\gameinput\common\PlatformInfo.cpp`
- `0x140006f2b`: `onecore\xbox\gameinput\common\PlatformInfo.cpp`

## pseudocode

```c
__int64 InitPlatformInfo()
{
  NTSTATUS Version; // ebx
  int v1; // r8d
  int v2; // r9d
  int v3; // r8d
  int v4; // r9d
  bool v6; // r8
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  int v8; // [rsp+44h] [rbp-BCh] BYREF
  int v9; // [rsp+48h] [rbp-B8h] BYREF
  const char *v10; // [rsp+50h] [rbp-B0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  __int16 v13; // [rsp+184h] [rbp+84h]
  __int16 v14; // [rsp+186h] [rbp+86h]

  v9 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Kernel-ProductInfo");
  Version = NtQueryLicenseValue(&DestinationString, 0, &dword_14000EC68, 4, &v9);
  if ( Version == -1073741772 )
  {
    dword_14000EC68 = 0;
  }
  else if ( Version < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2 && (qword_14000E010 & 2) != 0 && (qword_14000E018 & 2) == qword_14000E018 )
    {
      v7 = Version;
      v10 = "onecore\\xbox\\gameinput\\common\\PlatformInfo.cpp";
      v8 = 89;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)byte_14000B89B,
        v1,
        v2,
        (__int64)&v10,
        (__int64)&v8,
        (__int64)&v7);
    }
    return Version | 0x10000000u;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2 && (qword_14000E010 & 2) != 0 && (qword_14000E018 & 2) == qword_14000E018 )
    {
      v8 = Version;
      v10 = "onecore\\xbox\\gameinput\\common\\PlatformInfo.cpp";
      v7 = 99;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (unsigned int)&dword_14000B96C,
        v3,
        v4,
        (__int64)&v10,
        (__int64)&v7,
        (__int64)&v8);
    }
    return Version | 0x10000000u;
  }
  v6 = 1;
  word_14000EC6C = VersionInformation.dwMajorVersion;
  word_14000EC6E = VersionInformation.dwMinorVersion;
  word_14000EC72 = v13;
  word_14000EC74 = v14;
  word_14000EC70 = VersionInformation.dwBuildNumber;
  byte_14000E6C1 = LOWORD(VersionInformation.dwBuildNumber) >= 0x23F0u;
  byte_14000E6C5 = (unsigned int)(dword_14000EC68 - 194) <= 1;
  byte_14000E6C2 = (unsigned int)(dword_14000EC68 - 196) <= 1;
  byte_14000E6C4 = dword_14000EC68 == 192;
  if ( (unsigned int)(dword_14000EC68 - 194) > 1 && (unsigned int)(dword_14000EC68 - 196) > 1 )
    v6 = dword_14000EC68 == 192;
  byte_14000E6C3 = v6;
  InitIsInDwm();
  return 0;
}

```

## disassembly

```asm
0x140006de4  mov     [rsp-8+arg_0], rbx
0x140006de9  push    rbp
0x140006dea  lea     rbp, [rsp-0A0h]
0x140006df2  sub     rsp, 1A0h
0x140006df9  mov     rax, cs:__security_cookie
0x140006e00  xor     rax, rsp
0x140006e03  mov     [rbp+0A0h+var_10], rax
0x140006e0a  xorps   xmm0, xmm0
0x140006e0d  mov     [rsp+1A0h+var_158], 0
0x140006e15  lea     rdx, SourceString; "Kernel-ProductInfo"
0x140006e1c  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x140006e21  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x140006e26  call    cs:__imp_RtlInitUnicodeString
0x140006e2c  lea     rax, [rsp+1A0h+var_158]
0x140006e31  mov     r9d, 4
0x140006e37  lea     r8, dword_14000EC68
0x140006e3e  mov     [rsp+1A0h+var_180], rax
0x140006e43  xor     edx, edx
0x140006e45  lea     rcx, [rsp+1A0h+DestinationString]
0x140006e4a  call    cs:__imp_NtQueryLicenseValue
0x140006e50  mov     ebx, eax
0x140006e52  cmp     eax, 0C0000034h
0x140006e57  jnz     loc_140006EFB
0x140006e5d  mov     cs:dword_14000EC68, 0
0x140006e67  xor     edx, edx; Val
0x140006e69  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x140006e6e  mov     r8d, 118h; Size
0x140006e74  call    memset_0
0x140006e79  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x140006e7e  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140006e86  call    cs:__imp_RtlGetVersion
0x140006e8c  mov     ebx, eax
0x140006e8e  test    eax, eax
0x140006e90  jns     loc_140006F78
0x140006e96  mov     ecx, cs:dword_14000E000
0x140006e9c  cmp     ecx, 2
0x140006e9f  jbe     loc_140006F6D
0x140006ea5  mov     rdx, cs:qword_14000E018
0x140006eac  mov     rcx, cs:qword_14000E010
0x140006eb3  test    cl, 2
0x140006eb6  jz      loc_140006F6D
0x140006ebc  mov     rax, rdx
0x140006ebf  and     eax, 2
0x140006ec2  cmp     rax, rdx
0x140006ec5  jnz     loc_140006F6D
0x140006ecb  lea     rax, aOnecoreXboxGam_2; "onecore\\xbox\\gameinput\\common\\Platf"...
0x140006ed2  mov     [rsp+1A0h+var_15C], ebx
0x140006ed6  mov     [rsp+1A0h+var_150], rax
0x140006edb  lea     rdx, dword_14000B96C
0x140006ee2  lea     rax, [rsp+1A0h+var_15C]
0x140006ee7  mov     [rsp+1A0h+var_160], 63h ; 'c'
0x140006eef  mov     [rsp+1A0h+var_170], rax
0x140006ef4  lea     rax, [rsp+1A0h+var_160]
0x140006ef9  jmp     short loc_140006F59
0x140006efb  test    ebx, ebx
0x140006efd  jns     loc_140006E67
0x140006f03  mov     eax, cs:dword_14000E000
0x140006f09  cmp     eax, 2
0x140006f0c  jbe     short loc_140006F6D
0x140006f0e  mov     rcx, cs:qword_14000E018
0x140006f15  mov     rax, cs:qword_14000E010
0x140006f1c  test    al, 2
0x140006f1e  jz      short loc_140006F6D
0x140006f20  mov     rax, rcx
0x140006f23  and     eax, 2
0x140006f26  cmp     rax, rcx
0x140006f29  jnz     short loc_140006F6D
0x140006f2b  lea     rax, aOnecoreXboxGam_2; "onecore\\xbox\\gameinput\\common\\Platf"...
0x140006f32  mov     [rsp+1A0h+var_160], ebx
0x140006f36  mov     [rsp+1A0h+var_150], rax
0x140006f3b  lea     rdx, byte_14000B89B
0x140006f42  lea     rax, [rsp+1A0h+var_160]
0x140006f47  mov     [rsp+1A0h+var_15C], 59h ; 'Y'
0x140006f4f  mov     [rsp+1A0h+var_170], rax
0x140006f54  lea     rax, [rsp+1A0h+var_15C]
0x140006f59  mov     [rsp+1A0h+var_178], rax
0x140006f5e  lea     rax, [rsp+1A0h+var_150]
0x140006f63  mov     [rsp+1A0h+var_180], rax
0x140006f68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140006f6d  bts     ebx, 1Ch
0x140006f71  mov     eax, ebx
0x140006f73  jmp     loc_140007026
0x140006f78  movzx   eax, word ptr [rsp+1A0h+VersionInformation.dwMajorVersion]
0x140006f7d  mov     r8d, 1
0x140006f83  mov     edx, cs:dword_14000EC68
0x140006f89  movzx   ecx, word ptr [rsp+1A0h+VersionInformation.dwBuildNumber]
0x140006f8e  mov     cs:word_14000EC6C, ax
0x140006f95  movzx   eax, word ptr [rsp+1A0h+VersionInformation.dwMinorVersion]
0x140006f9a  mov     cs:word_14000EC6E, ax
0x140006fa1  movzx   eax, [rbp+0A0h+var_1C]
0x140006fa8  mov     cs:word_14000EC72, ax
0x140006faf  movzx   eax, [rbp+0A0h+var_1A]
0x140006fb6  mov     cs:word_14000EC74, ax
0x140006fbd  mov     eax, 23F0h
0x140006fc2  cmp     cx, ax
0x140006fc5  mov     cs:word_14000EC70, cx
0x140006fcc  lea     eax, [rdx-0C2h]
0x140006fd2  setnb   cs:byte_14000E6C1
0x140006fd9  cmp     eax, r8d
0x140006fdc  lea     eax, [rdx-0C4h]
0x140006fe2  setbe   cl
0x140006fe5  cmp     eax, r8d
0x140006fe8  mov     cs:byte_14000E6C5, cl
0x140006fee  setbe   r9b
0x140006ff2  cmp     edx, 0C0h
0x140006ff8  mov     cs:byte_14000E6C2, r9b
0x140006fff  setz    al
0x140007002  mov     cs:byte_14000E6C4, al
0x140007008  test    cl, cl
0x14000700a  jnz     short loc_140007018
0x14000700c  test    r9b, r9b
0x14000700f  jnz     short loc_140007018
0x140007011  test    al, al
0x140007013  jnz     short loc_140007018
0x140007015  xor     r8b, r8b
0x140007018  mov     cs:byte_14000E6C3, r8b
0x14000701f  call    InitIsInDwm
0x140007024  xor     eax, eax
0x140007026  mov     rcx, [rbp+0A0h+var_10]
0x14000702d  xor     rcx, rsp; StackCookie
0x140007030  call    __security_check_cookie
0x140007035  mov     rbx, [rsp+1A0h+arg_0]
0x14000703d  add     rsp, 1A0h
0x140007044  pop     rbp
0x140007045  retn
```
