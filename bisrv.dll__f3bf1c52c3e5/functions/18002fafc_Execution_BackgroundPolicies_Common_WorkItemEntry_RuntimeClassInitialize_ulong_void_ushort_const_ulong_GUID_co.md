# Execution::BackgroundPolicies::Common::WorkItemEntry::RuntimeClassInitialize(ulong,void *,ushort const *,ulong,_GUID const *,ushort const *,ulong,ulong,Execution::BackgroundPolicies::Common::WORK_ITEM_ENTRY_PARAMS *)

- ea: `0x18002fafc`
- end: `0x18002fe02`
- name: `?RuntimeClassInitialize@WorkItemEntry@Common@BackgroundPolicies@Execution@@QEAAJKPEAXPEBGKPEBU_GUID@@1KKPEAUWORK_ITEM_ENTRY_PARAMS@234@@Z`
- size: `774`
- prototype: `int(Execution::BackgroundPolicies::Common::WorkItemEntry *__hidden this, unsigned int, void *, const unsigned __int16 *, unsigned int, const struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int, struct Execution::BackgroundPolicies::Common::WORK_ITEM_ENTRY_PARAMS *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f680`
- `0x18008d89c`

## callees

- `0x18001a1f0`
- `0x18002fafc`
- `0x18002fe8c`
- `0x18006de78`
- `0x1800710a8`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18002fbb0`
- `ntdll!RtlValidSid` at `0x18002fbb0`
- `ntdll!RtlCopySid` at `0x18002fbef`
- `ntdll!RtlCopySid` at `0x18002fbef`
- `ntdll!RtlLengthSid` at `0x18002fbc4`
- `ntdll!RtlLengthSid` at `0x18002fbc4`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18002fcda`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x18002fcda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002fc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002fc90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002fd16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002fc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002fc90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002fd16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fd30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fd30`

## string_xrefs

- `0x18002fd6d`: `onecoreuap\base\background\bi\backgroundmanager\inc\BackgroundPolicyCommon.h`
- `0x18002fd94`: `onecoreuap\base\background\bi\backgroundmanager\inc\BackgroundPolicyCommon.h`
- `0x18002fdb6`: `onecoreuap\base\background\bi\backgroundmanager\inc\BackgroundPolicyCommon.h`

## pseudocode

```c
HRESULT __fastcall Execution::BackgroundPolicies::Common::WorkItemEntry::RuntimeClassInitialize(
        Execution::BackgroundPolicies::Common::WorkItemEntry *this,
        int a2,
        void *a3,
        WCHAR *a4,
        unsigned int a5,
        const struct _GUID *a6,
        const unsigned __int16 *sourceString,
        unsigned int a8,
        unsigned int a9,
        struct Execution::BackgroundPolicies::Common::WORK_ITEM_ENTRY_PARAMS *a10)
{
  __int128 v14; // xmm0
  int v15; // edx
  ULONG v16; // ebx
  void *v17; // rax
  NTSTATUS PackageFullNameFromKey; // eax
  struct Windows::Internal::String *v19; // r8
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rdx
  HRESULT v22; // r14d
  HRESULT PackageFamilyNameFromPsmKey; // ebx
  HSTRING v24; // rcx
  unsigned __int64 v25; // rdx
  HSTRING v26; // rcx
  HSTRING v27; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  int v32; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR v33[128]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  memset_0(v33, 0, sizeof(v33));
  v32 = 256;
  v14 = (__int128)*a6;
  *((_DWORD *)this + 21) = a8;
  *((_DWORD *)this + 22) = a5;
  *((_DWORD *)this + 30) = a9;
  *((_OWORD *)this + 2) = v14;
  *((_DWORD *)this + 23) = a2;
  *((_DWORD *)this + 20) = *(_DWORD *)a10;
  v15 = *((_DWORD *)this + 26) ^ (*((_DWORD *)this + 26) ^ (4 * *((_DWORD *)a10 + 1))) & 4;
  *((_DWORD *)this + 26) = v15;
  *((_DWORD *)this + 26) = v15 ^ ((unsigned __int8)v15 ^ (unsigned __int8)(4 * *((_DWORD *)a10 + 1))) & 8;
  if ( !RtlValidSid(a3) )
  {
    PackageFamilyNameFromPsmKey = -2147024809;
    v29 = 123;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\inc\\BackgroundPolicyCommon.h",
      (const char *)(unsigned int)PackageFamilyNameFromPsmKey,
      (int)string);
    return PackageFamilyNameFromPsmKey;
  }
  v16 = RtlLengthSid(a3);
  v17 = operator new[](v16, (const struct std::nothrow_t *)std::nothrow);
  *((_QWORD *)this + 12) = v17;
  if ( !v17 )
  {
    PackageFamilyNameFromPsmKey = -2147024882;
    v29 = 127;
    goto LABEL_26;
  }
  PackageFullNameFromKey = RtlCopySid(v16, v17, a3);
  if ( PackageFullNameFromKey < 0 )
  {
    v30 = 131;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v30,
             (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\inc\\BackgroundPolicyCommon.h",
             (const char *)(unsigned int)PackageFullNameFromKey,
             (int)string);
  }
  if ( !a4 )
  {
    PackageFamilyNameFromPsmKey = -2147467261;
LABEL_38:
    v29 = 132;
    goto LABEL_26;
  }
  v20 = -1;
  string = 0;
  v21 = -1;
  do
    ++v21;
  while ( a4[v21] );
  v22 = -2147024362;
  if ( v21 > 0xFFFFFFFF )
  {
    PackageFamilyNameFromPsmKey = -2147024362;
  }
  else
  {
    PackageFamilyNameFromPsmKey = WindowsCreateString(a4, v21, &string);
    if ( PackageFamilyNameFromPsmKey >= 0 )
    {
      v24 = (HSTRING)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = string;
      WindowsDeleteString(v24);
    }
  }
  if ( PackageFamilyNameFromPsmKey < 0 )
    goto LABEL_38;
  if ( !sourceString )
  {
    PackageFamilyNameFromPsmKey = -2147467261;
LABEL_36:
    v29 = 133;
    goto LABEL_26;
  }
  string = 0;
  v25 = -1;
  do
    ++v25;
  while ( sourceString[v25] );
  if ( v25 > 0xFFFFFFFF )
  {
    PackageFamilyNameFromPsmKey = -2147024362;
  }
  else
  {
    PackageFamilyNameFromPsmKey = WindowsCreateString(sourceString, v25, &string);
    if ( PackageFamilyNameFromPsmKey >= 0 )
    {
      v26 = (HSTRING)*((_QWORD *)this + 9);
      *((_QWORD *)this + 9) = string;
      WindowsDeleteString(v26);
    }
  }
  if ( PackageFamilyNameFromPsmKey < 0 )
    goto LABEL_36;
  PackageFamilyNameFromPsmKey = Execution::BackgroundPolicies::Common::GetPackageFamilyNameFromPsmKey(
                                  (Execution::BackgroundPolicies::Common *)a4,
                                  (const unsigned __int16 *)this + 28,
                                  v19);
  if ( PackageFamilyNameFromPsmKey < 0 )
  {
    v29 = 137;
    goto LABEL_26;
  }
  PackageFullNameFromKey = PsmGetPackageFullNameFromKey(a4, v33, &v32);
  if ( PackageFullNameFromKey < 0 )
  {
    v30 = 142;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v30,
             (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\inc\\BackgroundPolicyCommon.h",
             (const char *)(unsigned int)PackageFullNameFromKey,
             (int)string);
  }
  string = 0;
  do
    ++v20;
  while ( v33[v20] );
  if ( v20 > 0xFFFFFFFF || (v22 = WindowsCreateString(v33, v20, &string), v22 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\inc\\BackgroundPolicyCommon.h",
      (const char *)(unsigned int)v22,
      (int)string);
    return v22;
  }
  else
  {
    v27 = (HSTRING)*((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = string;
    WindowsDeleteString(v27);
    return 0;
  }
}

```

## disassembly

```asm
0x18002fafc  mov     [rsp-8+arg_8], rbx
0x18002fb01  push    rbp
0x18002fb02  push    rsi
0x18002fb03  push    rdi
0x18002fb04  push    r12
0x18002fb06  push    r13
0x18002fb08  push    r14
0x18002fb0a  push    r15
0x18002fb0c  lea     rbp, [rsp-40h]
0x18002fb11  sub     rsp, 140h
0x18002fb18  mov     rax, cs:__security_cookie
0x18002fb1f  xor     rax, rsp
0x18002fb22  mov     [rbp+70h+var_40], rax
0x18002fb26  mov     r12, [rbp+70h+sourceString]
0x18002fb2d  mov     rsi, r8
0x18002fb30  mov     ebx, edx
0x18002fb32  mov     rdi, rcx
0x18002fb35  mov     r14d, 100h
0x18002fb3b  lea     rcx, [rsp+170h+var_140]; void *
0x18002fb40  mov     r8d, r14d; Size
0x18002fb43  xor     edx, edx; Val
0x18002fb45  mov     r15, r9
0x18002fb48  call    memset_0
0x18002fb4d  mov     rcx, [rbp+70h+arg_48]
0x18002fb54  mov     rax, [rbp+70h+arg_28]
0x18002fb5b  mov     [rsp+170h+var_148], r14d
0x18002fb60  movups  xmm0, xmmword ptr [rax]
0x18002fb63  mov     eax, [rbp+70h+arg_38]
0x18002fb69  mov     [rdi+54h], eax
0x18002fb6c  mov     eax, [rbp+70h+arg_20]
0x18002fb72  mov     [rdi+58h], eax
0x18002fb75  mov     eax, [rbp+70h+arg_40]
0x18002fb7b  mov     [rdi+78h], eax
0x18002fb7e  movdqu  xmmword ptr [rdi+20h], xmm0
0x18002fb83  mov     [rdi+5Ch], ebx
0x18002fb86  mov     eax, [rcx]
0x18002fb88  mov     [rdi+50h], eax
0x18002fb8b  mov     edx, [rcx+4]
0x18002fb8e  shl     edx, 2
0x18002fb91  xor     edx, [rdi+68h]
0x18002fb94  and     edx, 4
0x18002fb97  xor     edx, [rdi+68h]
0x18002fb9a  mov     [rdi+68h], edx
0x18002fb9d  mov     eax, [rcx+4]
0x18002fba0  mov     rcx, rsi; Sid
0x18002fba3  shl     eax, 2
0x18002fba6  xor     eax, edx
0x18002fba8  and     eax, 8
0x18002fbab  xor     eax, edx
0x18002fbad  mov     [rdi+68h], eax
0x18002fbb0  call    cs:__imp_RtlValidSid
0x18002fbb6  xor     r13d, r13d
0x18002fbb9  test    al, al
0x18002fbbb  jz      loc_18002FD5F
0x18002fbc1  mov     rcx, rsi; Sid
0x18002fbc4  call    cs:__imp_RtlLengthSid
0x18002fbca  mov     ecx, eax; unsigned __int64
0x18002fbcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002fbd3  mov     ebx, eax
0x18002fbd5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002fbda  mov     [rdi+60h], rax
0x18002fbde  test    rax, rax
0x18002fbe1  jz      loc_18002FDCA
0x18002fbe7  mov     r8, rsi; SourceSid
0x18002fbea  mov     rdx, rax; DestinationSid
0x18002fbed  mov     ecx, ebx; DestinationSidLength
0x18002fbef  call    cs:__imp_RtlCopySid
0x18002fbf5  test    eax, eax
0x18002fbf7  js      loc_18002FDAD
0x18002fbfd  test    r15, r15
0x18002fc00  jz      loc_18002FDF3
0x18002fc06  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002fc0a  mov     [rsp+170h+string], r13
0x18002fc0f  mov     rdx, rsi
0x18002fc12  inc     rdx; length
0x18002fc15  cmp     [r15+rdx*2], r13w
0x18002fc1a  jnz     short loc_18002FC12
0x18002fc1c  mov     eax, 0FFFFFFFFh
0x18002fc21  mov     r14d, 80070216h
0x18002fc27  cmp     rdx, rax
0x18002fc2a  ja      loc_18002FD80
0x18002fc30  lea     r8, [rsp+170h+string]; string
0x18002fc35  mov     rcx, r15; sourceString
0x18002fc38  call    cs:__imp_WindowsCreateString
0x18002fc3e  mov     ebx, eax
0x18002fc40  test    eax, eax
0x18002fc42  js      short loc_18002FC57
0x18002fc44  mov     rax, [rsp+170h+string]
0x18002fc49  mov     rcx, [rdi+30h]; string
0x18002fc4d  mov     [rdi+30h], rax
0x18002fc51  call    cs:__imp_WindowsDeleteString
0x18002fc57  mov     eax, 0FFFFFFFFh
0x18002fc5c  test    ebx, ebx
0x18002fc5e  js      loc_18002FDF8
0x18002fc64  test    r12, r12
0x18002fc67  jz      loc_18002FDE4
0x18002fc6d  mov     [rsp+170h+string], r13
0x18002fc72  mov     rdx, rsi
0x18002fc75  inc     rdx; length
0x18002fc78  cmp     [r12+rdx*2], r13w
0x18002fc7d  jnz     short loc_18002FC75
0x18002fc7f  cmp     rdx, rax
0x18002fc82  ja      loc_18002FD88
0x18002fc88  lea     r8, [rsp+170h+string]; string
0x18002fc8d  mov     rcx, r12; sourceString
0x18002fc90  call    cs:__imp_WindowsCreateString
0x18002fc96  mov     ebx, eax
0x18002fc98  test    eax, eax
0x18002fc9a  js      short loc_18002FCAF
0x18002fc9c  mov     rax, [rsp+170h+string]
0x18002fca1  mov     rcx, [rdi+48h]; string
0x18002fca5  mov     [rdi+48h], rax
0x18002fca9  call    cs:__imp_WindowsDeleteString
0x18002fcaf  test    ebx, ebx
0x18002fcb1  js      loc_18002FDE9
0x18002fcb7  lea     rdx, [rdi+38h]; unsigned __int16 *
0x18002fcbb  mov     rcx, r15; this
0x18002fcbe  call    ?GetPackageFamilyNameFromPsmKey@Common@BackgroundPolicies@Execution@@YAJPEBGAEAVString@Internal@Windows@@@Z; Execution::BackgroundPolicies::Common::GetPackageFamilyNameFromPsmKey(ushort const *,Windows::Internal::String &)
0x18002fcc3  mov     ebx, eax
0x18002fcc5  test    eax, eax
0x18002fcc7  js      loc_18002FDD6
0x18002fccd  lea     r8, [rsp+170h+var_148]
0x18002fcd2  mov     rcx, r15
0x18002fcd5  lea     rdx, [rsp+170h+var_140]
0x18002fcda  call    cs:__imp_PsmGetPackageFullNameFromKey
0x18002fce0  test    eax, eax
0x18002fce2  js      loc_18002FDDD
0x18002fce8  mov     [rsp+170h+string], r13; int
0x18002fced  lea     rax, [rsp+170h+var_140]
0x18002fcf2  inc     rsi
0x18002fcf5  cmp     [rax+rsi*2], r13w
0x18002fcfa  jnz     short loc_18002FCF2
0x18002fcfc  mov     eax, 0FFFFFFFFh
0x18002fd01  cmp     rsi, rax
0x18002fd04  ja      loc_18002FD90
0x18002fd0a  mov     edx, esi; length
0x18002fd0c  lea     r8, [rsp+170h+string]; string
0x18002fd11  lea     rcx, [rsp+170h+var_140]; sourceString
0x18002fd16  call    cs:__imp_WindowsCreateString
0x18002fd1c  mov     r14d, eax
0x18002fd1f  test    eax, eax
0x18002fd21  js      short loc_18002FD90
0x18002fd23  mov     rax, [rsp+170h+string]
0x18002fd28  mov     rcx, [rdi+40h]; string
0x18002fd2c  mov     [rdi+40h], rax
0x18002fd30  call    cs:__imp_WindowsDeleteString
0x18002fd36  xor     eax, eax
0x18002fd38  mov     rcx, [rbp+70h+var_40]
0x18002fd3c  xor     rcx, rsp; StackCookie
0x18002fd3f  call    __security_check_cookie
0x18002fd44  mov     rbx, [rsp+170h+arg_8]
0x18002fd4c  add     rsp, 140h
0x18002fd53  pop     r15
0x18002fd55  pop     r14
0x18002fd57  pop     r13
0x18002fd59  pop     r12
0x18002fd5b  pop     rdi
0x18002fd5c  pop     rsi
0x18002fd5d  pop     rbp
0x18002fd5e  retn
0x18002fd5f  mov     ebx, 80070057h
0x18002fd64  mov     edx, 7Bh ; '{'; void *
0x18002fd69  mov     rcx, [rbp+78h]; this
0x18002fd6d  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\background\\bi\\backg"...
0x18002fd74  mov     r9d, ebx; char *
0x18002fd77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd7c  mov     eax, ebx
0x18002fd7e  jmp     short loc_18002FD38
0x18002fd80  mov     ebx, r14d
0x18002fd83  jmp     loc_18002FC5C
0x18002fd88  mov     ebx, r14d
0x18002fd8b  jmp     loc_18002FCAF
0x18002fd90  mov     rcx, [rbp+78h]; this
0x18002fd94  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\background\\bi\\backg"...
0x18002fd9b  mov     r9d, r14d; char *
0x18002fd9e  mov     edx, 90h; void *
0x18002fda3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fda8  mov     eax, r14d
0x18002fdab  jmp     short loc_18002FD38
0x18002fdad  mov     edx, 83h; void *
0x18002fdb2  mov     rcx, [rbp+78h]; this
0x18002fdb6  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\background\\bi\\backg"...
0x18002fdbd  mov     r9d, eax; char *
0x18002fdc0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002fdc5  jmp     loc_18002FD38
0x18002fdca  mov     ebx, 8007000Eh
0x18002fdcf  mov     edx, 7Fh
0x18002fdd4  jmp     short loc_18002FD69
0x18002fdd6  mov     edx, 89h
0x18002fddb  jmp     short loc_18002FD69
0x18002fddd  mov     edx, 8Eh
0x18002fde2  jmp     short loc_18002FDB2
0x18002fde4  mov     ebx, 80004003h
0x18002fde9  mov     edx, 85h
0x18002fdee  jmp     loc_18002FD69
0x18002fdf3  mov     ebx, 80004003h
0x18002fdf8  mov     edx, 84h
0x18002fdfd  jmp     loc_18002FD69
```
