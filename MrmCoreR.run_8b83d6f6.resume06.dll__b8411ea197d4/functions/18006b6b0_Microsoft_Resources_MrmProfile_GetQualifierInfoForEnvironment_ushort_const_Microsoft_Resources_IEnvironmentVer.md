# Microsoft::Resources::MrmProfile::GetQualifierInfoForEnvironment(ushort const *,Microsoft::Resources::IEnvironmentVersionInfo const *,Microsoft::Resources::IEnvironment const *,int *,ushort const * const * *,ushort const * *)

- ea: `0x18006b6b0`
- end: `0x18006b8e9`
- name: `?GetQualifierInfoForEnvironment@MrmProfile@Resources@Microsoft@@UEBAJPEBGPEBVIEnvironmentVersionInfo@23@PEBVIEnvironment@23@PEAHPEAPEBQEBGPEAPEBG@Z`
- size: `569`
- prototype: `int(Microsoft::Resources::MrmProfile *__hidden this, const unsigned __int16 *, const struct Microsoft::Resources::IEnvironmentVersionInfo *, const struct Microsoft::Resources::IEnvironment *, int *, const unsigned __int16 *const **, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028ad0`
- `0x180042f70`
- `0x18006b6b0`
- `0x18006b8f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b720`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b74f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b77a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b7c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b807`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b720`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b74f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b77a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b7c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006b807`

## pseudocode

```c
int __fastcall Microsoft::Resources::MrmProfile::GetQualifierInfoForEnvironment(
        Microsoft::Resources::MrmProfile *this,
        const unsigned __int16 *a2,
        const struct Microsoft::Resources::IEnvironmentVersionInfo *a3,
        const struct Microsoft::Resources::IEnvironment *a4,
        int *a5,
        const unsigned __int16 *const **a6,
        const unsigned __int16 **a7)
{
  const WCHAR *v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  const WCHAR *v16; // rax
  int v17; // eax
  const WCHAR *v18; // rax
  int v19; // eax
  const unsigned __int16 near *const *v20; // rax

  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v11 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct Microsoft::Resources::IEnvironment *))(*(_QWORD *)a4 + 16LL))(a4);
  v12 = CompareStringOrdinal(v11, -1, L"win://WinCore/1", -1, 1);
  if ( !(unsigned int)IntToComparison((unsigned int)(v12 - 2)) )
  {
    v13 = CompareStringOrdinal(a2, -1, L"Windows", -1, 1);
    if ( (unsigned int)IntToComparison((unsigned int)(v13 - 2)) )
    {
      v14 = CompareStringOrdinal(a2, -1, L"WindowsPhone", -1, 1);
      if ( (unsigned int)IntToComparison((unsigned int)(v14 - 2)) )
        return 0;
      *a5 = 9;
      *a6 = (const unsigned __int16 *const *)&Microsoft::Resources::WindowsPhoneEnvironment::PhoneQualifierNames;
      v20 = &Microsoft::Resources::WindowsPhoneEnvironment::PhoneToCoreQualifierMapping;
    }
    else
    {
      *a5 = 9;
      *a6 = (const unsigned __int16 *const *)&Microsoft::Resources::WindowsClientEnvironment::ClientQualifierNames;
      v20 = &Microsoft::Resources::WindowsClientEnvironment::ClientToCoreQualifierMapping;
    }
LABEL_9:
    *a7 = (const unsigned __int16 *)v20;
    return 0;
  }
  v16 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct Microsoft::Resources::IEnvironment *))(*(_QWORD *)a4 + 16LL))(a4);
  v17 = CompareStringOrdinal(v16, -1, L"win://Windows/1", -1, 1);
  if ( !(unsigned int)IntToComparison((unsigned int)(v17 - 2)) )
  {
    if ( (unsigned int)DefString_CompareWithOptions(a2, L"WinCore", 1) )
      return 0;
    *a5 = 12;
    *a6 = (const unsigned __int16 *const *)&Microsoft::Resources::CoreEnvironment::QualifierNames;
    v20 = (const unsigned __int16 near *const *)&Microsoft::Resources::WindowsClientEnvironment::CoreToClientQualifierMapping;
    goto LABEL_9;
  }
  v18 = (const WCHAR *)(*(__int64 (__fastcall **)(const struct Microsoft::Resources::IEnvironment *))(*(_QWORD *)a4 + 16LL))(a4);
  v19 = CompareStringOrdinal(v18, -1, L"win://WindowsPhone/1", -1, 1);
  if ( !(unsigned int)IntToComparison((unsigned int)(v19 - 2)) )
  {
    if ( (unsigned int)DefString_CompareWithOptions(a2, L"WinCore", 1) )
      return 0;
    *a5 = 12;
    *a6 = (const unsigned __int16 *const *)&Microsoft::Resources::CoreEnvironment::QualifierNames;
    v20 = (const unsigned __int16 near *const *)&Microsoft::Resources::WindowsPhoneEnvironment::CoreToPhoneQualifierMapping;
    goto LABEL_9;
  }
  return Microsoft::Resources::CoreProfile::GetQualifierInfoForEnvironment(this, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x18006b6b0  push    rbx
0x18006b6b2  push    rbp
0x18006b6b3  push    rsi
0x18006b6b4  push    rdi
0x18006b6b5  push    r12
0x18006b6b7  push    r14
0x18006b6b9  push    r15
0x18006b6bb  sub     rsp, 40h
0x18006b6bf  mov     rbx, [rsp+78h+arg_20]
0x18006b6c7  mov     r12, rcx
0x18006b6ca  mov     rdi, [rsp+78h+arg_28]
0x18006b6d2  mov     rcx, r9
0x18006b6d5  mov     rsi, [rsp+78h+arg_30]
0x18006b6dd  mov     r14, r9
0x18006b6e0  mov     r15, r8
0x18006b6e3  mov     rbp, rdx
0x18006b6e6  mov     dword ptr [rbx], 0
0x18006b6ec  mov     qword ptr [rdi], 0
0x18006b6f3  mov     qword ptr [rsi], 0
0x18006b6fa  mov     rax, [r9]
0x18006b6fd  mov     rax, [rax+10h]
0x18006b701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b706  or      ecx, 0FFFFFFFFh
0x18006b709  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006b711  mov     r9d, ecx; cchCount2
0x18006b714  lea     r8, aWinWincore1; "win://WinCore/1"
0x18006b71b  mov     edx, ecx; cchCount1
0x18006b71d  mov     rcx, rax; lpString1
0x18006b720  call    cs:__imp_CompareStringOrdinal
0x18006b726  lea     ecx, [rax-2]
0x18006b729  call    _IntToComparison
0x18006b72e  test    eax, eax
0x18006b730  jnz     short loc_18006B7A1
0x18006b732  or      r14d, 0FFFFFFFFh
0x18006b736  lea     r15d, [rax+1]
0x18006b73a  mov     r9d, r14d; cchCount2
0x18006b73d  mov     [rsp+78h+bIgnoreCase], r15d; bIgnoreCase
0x18006b742  mov     edx, r14d; cchCount1
0x18006b745  lea     r8, aWindows; "Windows"
0x18006b74c  mov     rcx, rbp; lpString1
0x18006b74f  call    cs:__imp_CompareStringOrdinal
0x18006b755  lea     ecx, [rax-2]
0x18006b758  call    _IntToComparison
0x18006b75d  test    eax, eax
0x18006b75f  jz      loc_18006B842
0x18006b765  mov     r9d, r14d; cchCount2
0x18006b768  mov     [rsp+78h+bIgnoreCase], r15d; bIgnoreCase
0x18006b76d  lea     r8, aWindowsphone; "WindowsPhone"
0x18006b774  mov     edx, r14d; cchCount1
0x18006b777  mov     rcx, rbp; lpString1
0x18006b77a  call    cs:__imp_CompareStringOrdinal
0x18006b780  lea     ecx, [rax-2]
0x18006b783  call    _IntToComparison
0x18006b788  test    eax, eax
0x18006b78a  jz      loc_18006B861
0x18006b790  xor     eax, eax
0x18006b792  add     rsp, 40h
0x18006b796  pop     r15
0x18006b798  pop     r14
0x18006b79a  pop     r12
0x18006b79c  pop     rdi
0x18006b79d  pop     rsi
0x18006b79e  pop     rbp
0x18006b79f  pop     rbx
0x18006b7a0  retn
0x18006b7a1  mov     rax, [r14]
0x18006b7a4  mov     rcx, r14
0x18006b7a7  mov     rax, [rax+10h]
0x18006b7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7b0  or      edx, 0FFFFFFFFh; cchCount1
0x18006b7b3  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006b7bb  mov     r9d, edx; cchCount2
0x18006b7be  lea     r8, aWinWindows1; "win://Windows/1"
0x18006b7c5  mov     rcx, rax; lpString1
0x18006b7c8  call    cs:__imp_CompareStringOrdinal
0x18006b7ce  lea     ecx, [rax-2]
0x18006b7d1  call    _IntToComparison
0x18006b7d6  test    eax, eax
0x18006b7d8  jz      loc_18006B87A
0x18006b7de  mov     rax, [r14]
0x18006b7e1  mov     rcx, r14
0x18006b7e4  mov     rax, [rax+10h]
0x18006b7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7ed  or      ecx, 0FFFFFFFFh
0x18006b7f0  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006b7f8  mov     r9d, ecx; cchCount2
0x18006b7fb  lea     r8, aWinWindowsphon; "win://WindowsPhone/1"
0x18006b802  mov     edx, ecx; cchCount1
0x18006b804  mov     rcx, rax; lpString1
0x18006b807  call    cs:__imp_CompareStringOrdinal
0x18006b80d  lea     ecx, [rax-2]
0x18006b810  call    _IntToComparison
0x18006b815  test    eax, eax
0x18006b817  jz      loc_18006B8B0
0x18006b81d  mov     [rsp+78h+var_48], rsi; unsigned __int16 **
0x18006b822  mov     r9, r14; struct Microsoft::Resources::IEnvironment *
0x18006b825  mov     [rsp+78h+var_50], rdi; unsigned __int16 ***
0x18006b82a  mov     r8, r15; struct Microsoft::Resources::IEnvironmentVersionInfo *
0x18006b82d  mov     rdx, rbp; unsigned __int16 *
0x18006b830  mov     qword ptr [rsp+78h+bIgnoreCase], rbx; int *
0x18006b835  mov     rcx, r12; this
0x18006b838  call    ?GetQualifierInfoForEnvironment@CoreProfile@Resources@Microsoft@@UEBAJPEBGPEBVIEnvironmentVersionInfo@23@PEBVIEnvironment@23@PEAHPEAPEBQEBGPEAPEBG@Z; Microsoft::Resources::CoreProfile::GetQualifierInfoForEnvironment(ushort const *,Microsoft::Resources::IEnvironmentVersionInfo const *,Microsoft::Resources::IEnvironment const *,int *,ushort const * const * *,ushort const * *)
0x18006b83d  jmp     loc_18006B792
0x18006b842  lea     rax, ?ClientQualifierNames@WindowsClientEnvironment@Resources@Microsoft@@3QBQEBGB; ushort const * const near * const Microsoft::Resources::WindowsClientEnvironment::ClientQualifierNames
0x18006b849  mov     dword ptr [rbx], 9
0x18006b84f  mov     [rdi], rax
0x18006b852  lea     rax, ?ClientToCoreQualifierMapping@WindowsClientEnvironment@Resources@Microsoft@@3QBGB; ushort const near * const Microsoft::Resources::WindowsClientEnvironment::ClientToCoreQualifierMapping
0x18006b859  mov     [rsi], rax
0x18006b85c  jmp     loc_18006B790
0x18006b861  lea     rax, ?PhoneQualifierNames@WindowsPhoneEnvironment@Resources@Microsoft@@3QBQEBGB; ushort const * const near * const Microsoft::Resources::WindowsPhoneEnvironment::PhoneQualifierNames
0x18006b868  mov     dword ptr [rbx], 9
0x18006b86e  mov     [rdi], rax
0x18006b871  lea     rax, ?PhoneToCoreQualifierMapping@WindowsPhoneEnvironment@Resources@Microsoft@@3QBGB; ushort const near * const Microsoft::Resources::WindowsPhoneEnvironment::PhoneToCoreQualifierMapping
0x18006b878  jmp     short loc_18006B859
0x18006b87a  mov     r8d, 1
0x18006b880  lea     rdx, aWincore; "WinCore"
0x18006b887  mov     rcx, rbp
0x18006b88a  call    DefString_CompareWithOptions
0x18006b88f  test    eax, eax
0x18006b891  jnz     loc_18006B790
0x18006b897  lea     rax, ?QualifierNames@CoreEnvironment@Resources@Microsoft@@3QBQEBGB; ushort const * const near * const Microsoft::Resources::CoreEnvironment::QualifierNames
0x18006b89e  mov     dword ptr [rbx], 0Ch
0x18006b8a4  mov     [rdi], rax
0x18006b8a7  lea     rax, ?CoreToClientQualifierMapping@WindowsClientEnvironment@Resources@Microsoft@@3QBGB; ushort const near * const Microsoft::Resources::WindowsClientEnvironment::CoreToClientQualifierMapping
0x18006b8ae  jmp     short loc_18006B859
0x18006b8b0  mov     r8d, 1
0x18006b8b6  lea     rdx, aWincore; "WinCore"
0x18006b8bd  mov     rcx, rbp
0x18006b8c0  call    DefString_CompareWithOptions
0x18006b8c5  test    eax, eax
0x18006b8c7  jnz     loc_18006B790
0x18006b8cd  lea     rax, ?QualifierNames@CoreEnvironment@Resources@Microsoft@@3QBQEBGB; ushort const * const near * const Microsoft::Resources::CoreEnvironment::QualifierNames
0x18006b8d4  mov     dword ptr [rbx], 0Ch
0x18006b8da  mov     [rdi], rax
0x18006b8dd  lea     rax, ?CoreToPhoneQualifierMapping@WindowsPhoneEnvironment@Resources@Microsoft@@3QBGB; ushort const near * const Microsoft::Resources::WindowsPhoneEnvironment::CoreToPhoneQualifierMapping
0x18006b8e4  jmp     loc_18006B859
```
