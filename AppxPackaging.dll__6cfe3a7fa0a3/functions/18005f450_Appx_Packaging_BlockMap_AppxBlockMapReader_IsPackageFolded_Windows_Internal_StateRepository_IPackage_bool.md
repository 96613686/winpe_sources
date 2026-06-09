# Appx::Packaging::BlockMap::AppxBlockMapReader::IsPackageFolded(Windows::Internal::StateRepository::IPackage *,bool *)

- ea: `0x18005f450`
- end: `0x18005f6dd`
- name: `?IsPackageFolded@AppxBlockMapReader@BlockMap@Packaging@Appx@@CAJPEAUIPackage@StateRepository@Internal@Windows@@PEA_N@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IPackage *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005cd3c`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18005f450`
- `0x18005f6e4`
- `0x180078150`
- `0x1800992a0`
- `0x1800ad008`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f5e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f640`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x18005f653`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x18005f653`

## string_xrefs

- `0x18005f4a1`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005f51a`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005f5b8`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005f60c`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`
- `0x18005f667`: `onecore\printscan\appxpackaging\blockmap\src\appxblockmapreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BlockMap::AppxBlockMapReader::IsPackageFolded(
        struct Windows::Internal::StateRepository::IPackage *a1,
        bool *a2)
{
  __int64 v4; // rax
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // ebx
  bool v8; // di
  __int64 *v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *); // rbx
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int PackageStatus; // eax
  unsigned int v21; // [rsp+20h] [rbp-60h]
  bool v22; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v23[7]; // [rsp+31h] [rbp-4Fh] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  int v26; // [rsp+48h] [rbp-38h] BYREF
  int v27; // [rsp+4Ch] [rbp-34h] BYREF
  __int64 v28; // [rsp+50h] [rbp-30h] BYREF
  HSTRING v29; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a2 = 0;
  v4 = *(_QWORD *)a1;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, int *))(v4 + 128))(a1, &v26);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v8 = 1;
    if ( v26 != 1 )
      return 0;
    v25 = 0;
    v10 = (__int64 *)Windows::Internal::StringReference::StringReference(&v29, (const unsigned __int16 (*)[45])v6);
    v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatics>>(
            *v10,
            (__int64)&v25);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = 418;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
        (const char *)(unsigned int)v11,
        v21);
LABEL_26:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v25);
      return (unsigned int)v7;
    }
    v13 = *(_QWORD *)a1;
    v28 = 0;
    v7 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, __int64 *))(v13 + 112))(
           a1,
           &v28);
    if ( v7 < 0 )
    {
      v14 = 423;
      goto LABEL_9;
    }
    v23[0] = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v25 + 320LL))(v25, v28, 2, v23);
    if ( v7 < 0 )
    {
      v14 = 426;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
        (const char *)(unsigned int)v7,
        v21);
      v15 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return (unsigned int)v7;
    }
    if ( !v23[0] )
    {
      v22 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, bool *))(*(_QWORD *)v25 + 320LL))(v25, v28, 1, &v22);
      v7 = v11;
      if ( v11 < 0 )
      {
        v12 = 436;
        goto LABEL_16;
      }
      if ( !v22 )
        goto LABEL_24;
      v16 = *(_QWORD *)a1;
      string = 0;
      v17 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *))(v16 + 112);
      WindowsDeleteString(0);
      string = 0;
      v18 = v17(a1, &string);
      v7 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
          (const char *)(unsigned int)v18,
          v21);
LABEL_20:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_26;
      }
      v27 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      PackageStatus = GetPackageStatus(StringRawBuffer, &v27);
      if ( PackageStatus )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1BC,
               (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
               (const char *)PackageStatus,
               v21);
        goto LABEL_20;
      }
      string = 0;
      v22 = (v27 & 0x40000) == 0;
      WindowsDeleteString(0);
      if ( !v22 )
LABEL_24:
        v8 = 0;
    }
    v7 = 0;
    *a2 = v8;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x195,
    (unsigned int)"onecore\\printscan\\appxpackaging\\blockmap\\src\\appxblockmapreader.cpp",
    (const char *)(unsigned int)v5,
    v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005f450  mov     [rsp-28h+arg_10], rbx
0x18005f455  push    rbp
0x18005f456  push    rsi
0x18005f457  push    rdi
0x18005f458  push    r14
0x18005f45a  push    r15
0x18005f45c  mov     rbp, rsp
0x18005f45f  sub     rsp, 80h
0x18005f466  mov     rax, cs:__security_cookie
0x18005f46d  xor     rax, rsp
0x18005f470  mov     [rbp+var_8], rax
0x18005f474  xor     r15d, r15d
0x18005f477  mov     r14, rdx
0x18005f47a  mov     [rdx], r15b
0x18005f47d  mov     rsi, rcx
0x18005f480  mov     rax, [rcx]
0x18005f483  lea     rdx, [rbp+var_38]
0x18005f487  mov     [rbp+var_38], r15d
0x18005f48b  mov     rax, [rax+80h]
0x18005f492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f497  mov     ebx, eax
0x18005f499  test    eax, eax
0x18005f49b  jns     short loc_18005F4BA
0x18005f49d  mov     rcx, [rbp+28h]; this
0x18005f4a1  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005f4a8  mov     r9d, eax; char *
0x18005f4ab  mov     edx, 195h; void *
0x18005f4b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f4b5  jmp     loc_18005F6B7
0x18005f4ba  mov     edi, 1
0x18005f4bf  cmp     [rbp+var_38], edi
0x18005f4c2  jz      short loc_18005F4CB
0x18005f4c4  xor     eax, eax
0x18005f4c6  jmp     loc_18005F6B9
0x18005f4cb  lea     rcx, [rbp+var_28]; string
0x18005f4cf  mov     [rbp+var_40], r15
0x18005f4d3  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x18005f4d8  lea     rdx, [rbp+var_40]
0x18005f4dc  mov     rcx, [rax]
0x18005f4df  call    ??$GetActivationFactory@V?$ComPtr@UIPackageUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageUserStatics>>)
0x18005f4e4  mov     ebx, eax
0x18005f4e6  test    eax, eax
0x18005f4e8  jns     short loc_18005F4F4
0x18005f4ea  mov     edx, 1A2h
0x18005f4ef  jmp     loc_18005F5B4
0x18005f4f4  mov     rax, [rsi]
0x18005f4f7  lea     rdx, [rbp+var_30]
0x18005f4fb  mov     rcx, rsi
0x18005f4fe  mov     [rbp+var_30], r15
0x18005f502  mov     rax, [rax+70h]
0x18005f506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f50b  mov     ebx, eax
0x18005f50d  test    eax, eax
0x18005f50f  jns     short loc_18005F54B
0x18005f511  mov     edx, 1A7h; void *
0x18005f516  mov     rcx, [rbp+28h]; this
0x18005f51a  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005f521  mov     r9d, ebx; char *
0x18005f524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f529  mov     rcx, [rbp+var_40]
0x18005f52d  test    rcx, rcx
0x18005f530  jz      loc_18005F6B7
0x18005f536  mov     [rbp+var_40], r15
0x18005f53a  mov     rax, [rcx]
0x18005f53d  mov     rax, [rax+10h]
0x18005f541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f546  jmp     loc_18005F6B7
0x18005f54b  mov     rcx, [rbp+var_40]
0x18005f54f  lea     r9, [rbp+var_4F]
0x18005f553  mov     rdx, [rbp+var_30]
0x18005f557  mov     r8d, 2
0x18005f55d  mov     [rbp+var_4F], r15b
0x18005f561  mov     rax, [rcx]
0x18005f564  mov     rax, [rax+140h]
0x18005f56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f570  mov     ebx, eax
0x18005f572  test    eax, eax
0x18005f574  jns     short loc_18005F57D
0x18005f576  mov     edx, 1AAh
0x18005f57b  jmp     short loc_18005F516
0x18005f57d  cmp     [rbp+var_4F], r15b
0x18005f581  jnz     loc_18005F6A8
0x18005f587  mov     rcx, [rbp+var_40]
0x18005f58b  lea     r9, [rbp+var_50]
0x18005f58f  mov     rdx, [rbp+var_30]
0x18005f593  mov     r8d, edi
0x18005f596  mov     [rbp+var_50], r15b
0x18005f59a  mov     rax, [rcx]
0x18005f59d  mov     rax, [rax+140h]
0x18005f5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5a9  mov     ebx, eax
0x18005f5ab  test    eax, eax
0x18005f5ad  jns     short loc_18005F5CC
0x18005f5af  mov     edx, 1B4h; void *
0x18005f5b4  mov     rcx, [rbp+28h]; this
0x18005f5b8  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005f5bf  mov     r9d, eax; char *
0x18005f5c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f5c7  jmp     loc_18005F6AE
0x18005f5cc  cmp     [rbp+var_50], r15b
0x18005f5d0  jz      loc_18005F6A5
0x18005f5d6  mov     rax, [rsi]
0x18005f5d9  xor     ecx, ecx; string
0x18005f5db  mov     [rbp+string], r15
0x18005f5df  mov     rbx, [rax+70h]
0x18005f5e3  call    cs:__imp_WindowsDeleteString
0x18005f5ea  nop     dword ptr [rax+rax+00h]
0x18005f5ef  lea     rdx, [rbp+string]
0x18005f5f3  mov     [rbp+string], r15
0x18005f5f7  mov     rcx, rsi
0x18005f5fa  mov     rax, rbx
0x18005f5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f602  mov     ebx, eax
0x18005f604  test    eax, eax
0x18005f606  jns     short loc_18005F636
0x18005f608  mov     rcx, [rbp+28h]; this
0x18005f60c  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005f613  mov     r9d, eax; char *
0x18005f616  mov     edx, 1B9h; void *
0x18005f61b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f620  mov     rcx, [rbp+string]; string
0x18005f624  call    cs:__imp_WindowsDeleteString
0x18005f62b  nop     dword ptr [rax+rax+00h]
0x18005f630  mov     [rbp+string], r15
0x18005f634  jmp     short loc_18005F6AE
0x18005f636  mov     rcx, [rbp+string]; string
0x18005f63a  xor     edx, edx; length
0x18005f63c  mov     [rbp+var_34], r15d
0x18005f640  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f647  nop     dword ptr [rax+rax+00h]
0x18005f64c  mov     rcx, rax
0x18005f64f  lea     rdx, [rbp+var_34]
0x18005f653  call    cs:__imp_GetPackageStatus
0x18005f65a  nop     dword ptr [rax+rax+00h]
0x18005f65f  test    eax, eax
0x18005f661  jz      short loc_18005F67F
0x18005f663  mov     rcx, [rbp+28h]; this
0x18005f667  lea     r8, aOnecorePrintsc_90; "onecore\\printscan\\appxpackaging\\bloc"...
0x18005f66e  mov     r9d, eax; char *
0x18005f671  mov     edx, 1BCh; void *
0x18005f676  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005f67b  mov     ebx, eax
0x18005f67d  jmp     short loc_18005F620
0x18005f67f  mov     eax, [rbp+var_34]
0x18005f682  xor     ecx, ecx; string
0x18005f684  shr     eax, 12h
0x18005f687  not     al
0x18005f689  mov     [rbp+string], r15
0x18005f68d  and     al, dil
0x18005f690  mov     [rbp+var_50], al
0x18005f693  call    cs:__imp_WindowsDeleteString
0x18005f69a  nop     dword ptr [rax+rax+00h]
0x18005f69f  cmp     [rbp+var_50], r15b
0x18005f6a3  jnz     short loc_18005F6A8
0x18005f6a5  mov     dil, r15b
0x18005f6a8  mov     ebx, r15d
0x18005f6ab  mov     [r14], dil
0x18005f6ae  lea     rcx, [rbp+var_40]
0x18005f6b2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18005f6b7  mov     eax, ebx
0x18005f6b9  mov     rcx, [rbp+var_8]
0x18005f6bd  xor     rcx, rsp; StackCookie
0x18005f6c0  call    __security_check_cookie
0x18005f6c5  mov     rbx, [rsp+80h+arg_10]
0x18005f6cd  add     rsp, 80h
0x18005f6d4  pop     r15
0x18005f6d6  pop     r14
0x18005f6d8  pop     rdi
0x18005f6d9  pop     rsi
0x18005f6da  pop     rbp
0x18005f6db  retn
```
