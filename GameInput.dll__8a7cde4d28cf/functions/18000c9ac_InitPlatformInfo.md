# InitPlatformInfo

- ea: `0x18000c9ac`
- end: `0x18000cc21`
- name: `InitPlatformInfo`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d7a4`

## callees

- `0x180001304`
- `0x18000c848`
- `0x18000c9ac`
- `0x18004c8a5`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x18000ca18`
- `ntdll!NtQueryLicenseValue` at `0x18000ca18`
- `ntdll!RtlGetVersion` at `0x18000ca5a`
- `ntdll!RtlGetVersion` at `0x18000ca5a`
- `ntdll!RtlInitUnicodeString` at `0x18000c9ee`
- `ntdll!RtlInitUnicodeString` at `0x18000c9ee`

## string_xrefs

- `0x18000caa5`: `onecore\xbox\gameinput\common\PlatformInfo.cpp`
- `0x18000cb05`: `onecore\xbox\gameinput\common\PlatformInfo.cpp`

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
  Version = NtQueryLicenseValue(&DestinationString, 0, &dword_180069F48, 4, &v9);
  if ( Version == -1073741772 )
  {
    dword_180069F48 = 0;
  }
  else if ( Version < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
    {
      v7 = Version;
      v10 = "onecore\\xbox\\gameinput\\common\\PlatformInfo.cpp";
      v8 = 89;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_180059D75,
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
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
    {
      v8 = Version;
      v10 = "onecore\\xbox\\gameinput\\common\\PlatformInfo.cpp";
      v7 = 99;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)word_18005A12A,
        v3,
        v4,
        (__int64)&v10,
        (__int64)&v7,
        (__int64)&v8);
    }
    return Version | 0x10000000u;
  }
  v6 = 1;
  word_180069F4C = VersionInformation.dwMajorVersion;
  word_180069F4E = VersionInformation.dwMinorVersion;
  word_180069F52 = v13;
  word_180069F54 = v14;
  word_180069F50 = VersionInformation.dwBuildNumber;
  byte_180069911 = LOWORD(VersionInformation.dwBuildNumber) >= 0x23F0u;
  byte_180069915 = (unsigned int)(dword_180069F48 - 194) <= 1;
  byte_180069912 = (unsigned int)(dword_180069F48 - 196) <= 1;
  byte_180069914 = dword_180069F48 == 192;
  if ( (unsigned int)(dword_180069F48 - 194) > 1 && (unsigned int)(dword_180069F48 - 196) > 1 )
    v6 = dword_180069F48 == 192;
  byte_180069913 = v6;
  InitIsInDwm();
  return 0;
}

```

## disassembly

```asm
0x18000c9ac  mov     [rsp-8+arg_0], rbx
0x18000c9b1  push    rbp
0x18000c9b2  lea     rbp, [rsp-0A0h]
0x18000c9ba  sub     rsp, 1A0h
0x18000c9c1  mov     rax, cs:__security_cookie
0x18000c9c8  xor     rax, rsp
0x18000c9cb  mov     [rbp+0A0h+var_10], rax
0x18000c9d2  xorps   xmm0, xmm0
0x18000c9d5  mov     [rsp+1A0h+var_158], 0
0x18000c9dd  lea     rdx, SourceString; "Kernel-ProductInfo"
0x18000c9e4  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x18000c9e9  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x18000c9ee  call    cs:__imp_RtlInitUnicodeString
0x18000c9f5  nop     dword ptr [rax+rax+00h]
0x18000c9fa  lea     rax, [rsp+1A0h+var_158]
0x18000c9ff  mov     r9d, 4
0x18000ca05  lea     r8, dword_180069F48
0x18000ca0c  mov     [rsp+1A0h+var_180], rax
0x18000ca11  xor     edx, edx
0x18000ca13  lea     rcx, [rsp+1A0h+DestinationString]
0x18000ca18  call    cs:__imp_NtQueryLicenseValue
0x18000ca1f  nop     dword ptr [rax+rax+00h]
0x18000ca24  mov     ebx, eax
0x18000ca26  cmp     eax, 0C0000034h
0x18000ca2b  jnz     loc_18000CAD5
0x18000ca31  mov     cs:dword_180069F48, 0
0x18000ca3b  xor     edx, edx; Val
0x18000ca3d  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x18000ca42  mov     r8d, 118h; Size
0x18000ca48  call    memset_0
0x18000ca4d  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x18000ca52  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000ca5a  call    cs:__imp_RtlGetVersion
0x18000ca61  nop     dword ptr [rax+rax+00h]
0x18000ca66  mov     ebx, eax
0x18000ca68  test    eax, eax
0x18000ca6a  jns     loc_18000CB52
0x18000ca70  mov     ecx, cs:dword_180069000
0x18000ca76  cmp     ecx, 2
0x18000ca79  jbe     loc_18000CB47
0x18000ca7f  mov     rdx, cs:qword_180069018
0x18000ca86  mov     rcx, cs:qword_180069010
0x18000ca8d  test    cl, 2
0x18000ca90  jz      loc_18000CB47
0x18000ca96  mov     rax, rdx
0x18000ca99  and     eax, 2
0x18000ca9c  cmp     rax, rdx
0x18000ca9f  jnz     loc_18000CB47
0x18000caa5  lea     rax, aOnecoreXboxGam_16; "onecore\\xbox\\gameinput\\common\\Platf"...
0x18000caac  mov     [rsp+1A0h+var_15C], ebx
0x18000cab0  mov     [rsp+1A0h+var_150], rax
0x18000cab5  lea     rdx, word_18005A12A
0x18000cabc  lea     rax, [rsp+1A0h+var_15C]
0x18000cac1  mov     [rsp+1A0h+var_160], 63h ; 'c'
0x18000cac9  mov     [rsp+1A0h+var_170], rax
0x18000cace  lea     rax, [rsp+1A0h+var_160]
0x18000cad3  jmp     short loc_18000CB33
0x18000cad5  test    ebx, ebx
0x18000cad7  jns     loc_18000CA3B
0x18000cadd  mov     eax, cs:dword_180069000
0x18000cae3  cmp     eax, 2
0x18000cae6  jbe     short loc_18000CB47
0x18000cae8  mov     rcx, cs:qword_180069018
0x18000caef  mov     rax, cs:qword_180069010
0x18000caf6  test    al, 2
0x18000caf8  jz      short loc_18000CB47
0x18000cafa  mov     rax, rcx
0x18000cafd  and     eax, 2
0x18000cb00  cmp     rax, rcx
0x18000cb03  jnz     short loc_18000CB47
0x18000cb05  lea     rax, aOnecoreXboxGam_16; "onecore\\xbox\\gameinput\\common\\Platf"...
0x18000cb0c  mov     [rsp+1A0h+var_160], ebx
0x18000cb10  mov     [rsp+1A0h+var_150], rax
0x18000cb15  lea     rdx, byte_180059D75
0x18000cb1c  lea     rax, [rsp+1A0h+var_160]
0x18000cb21  mov     [rsp+1A0h+var_15C], 59h ; 'Y'
0x18000cb29  mov     [rsp+1A0h+var_170], rax
0x18000cb2e  lea     rax, [rsp+1A0h+var_15C]
0x18000cb33  mov     [rsp+1A0h+var_178], rax
0x18000cb38  lea     rax, [rsp+1A0h+var_150]
0x18000cb3d  mov     [rsp+1A0h+var_180], rax
0x18000cb42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cb47  bts     ebx, 1Ch
0x18000cb4b  mov     eax, ebx
0x18000cb4d  jmp     loc_18000CC00
0x18000cb52  movzx   eax, word ptr [rsp+1A0h+VersionInformation.dwMajorVersion]
0x18000cb57  mov     r8d, 1
0x18000cb5d  mov     edx, cs:dword_180069F48
0x18000cb63  movzx   ecx, word ptr [rsp+1A0h+VersionInformation.dwBuildNumber]
0x18000cb68  mov     cs:word_180069F4C, ax
0x18000cb6f  movzx   eax, word ptr [rsp+1A0h+VersionInformation.dwMinorVersion]
0x18000cb74  mov     cs:word_180069F4E, ax
0x18000cb7b  movzx   eax, [rbp+0A0h+var_1C]
0x18000cb82  mov     cs:word_180069F52, ax
0x18000cb89  movzx   eax, [rbp+0A0h+var_1A]
0x18000cb90  mov     cs:word_180069F54, ax
0x18000cb97  mov     eax, 23F0h
0x18000cb9c  cmp     cx, ax
0x18000cb9f  mov     cs:word_180069F50, cx
0x18000cba6  lea     eax, [rdx-0C2h]
0x18000cbac  setnb   cs:byte_180069911
0x18000cbb3  cmp     eax, r8d
0x18000cbb6  lea     eax, [rdx-0C4h]
0x18000cbbc  setbe   cl
0x18000cbbf  cmp     eax, r8d
0x18000cbc2  mov     cs:byte_180069915, cl
0x18000cbc8  setbe   r9b
0x18000cbcc  cmp     edx, 0C0h
0x18000cbd2  mov     cs:byte_180069912, r9b
0x18000cbd9  setz    al
0x18000cbdc  mov     cs:byte_180069914, al
0x18000cbe2  test    cl, cl
0x18000cbe4  jnz     short loc_18000CBF2
0x18000cbe6  test    r9b, r9b
0x18000cbe9  jnz     short loc_18000CBF2
0x18000cbeb  test    al, al
0x18000cbed  jnz     short loc_18000CBF2
0x18000cbef  xor     r8b, r8b
0x18000cbf2  mov     cs:byte_180069913, r8b
0x18000cbf9  call    InitIsInDwm
0x18000cbfe  xor     eax, eax
0x18000cc00  mov     rcx, [rbp+0A0h+var_10]
0x18000cc07  xor     rcx, rsp; StackCookie
0x18000cc0a  call    __security_check_cookie
0x18000cc0f  mov     rbx, [rsp+1A0h+arg_0]
0x18000cc17  add     rsp, 1A0h
0x18000cc1e  pop     rbp
0x18000cc1f  retn
```
