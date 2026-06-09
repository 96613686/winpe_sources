# OSIntegration::DEH::FileManager::CopyFileToManagedDirectory(HSTRING__ *,HSTRING__ *,StateRepository::SignatureOrigin,OSIntegration::DEH::ManagedDirectory,HSTRING__ *)

- ea: `0x1801d6740`
- end: `0x1801d69ef`
- name: `?CopyFileToManagedDirectory@FileManager@DEH@OSIntegration@@UEAAJPEAUHSTRING__@@0W4SignatureOrigin@StateRepository@@W4ManagedDirectory@23@0@Z`
- size: `687`
- prototype: `__int64 __fastcall(__int64, HSTRING, HSTRING, int, int, HSTRING string)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1800649b4`
- `0x18009aff4`
- `0x1800bc674`
- `0x1800bfa1c`
- `0x1800d20f4`
- `0x1800f0260`
- `0x1801d6740`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d6818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d6826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d68e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d68f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d6818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d6826`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d68e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d68f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d69b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d69b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d69ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d69c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d69ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801d69c9`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801d6839`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801d6903`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801d6839`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801d6903`

## string_xrefs

- `0x1801d68b9`: `GetManagedDirectoryPath( destinationDirectory, incomingPackageMoniker, destinationDirectoryPath.GetAddressOf())`
- `0x1801d685b`: `PathAllocCombine( WindowsGetStringRawBuffer(incomingPackageRoot, nullptr), WindowsGetStringRawBuffer(relativeFilePath, nullptr), PATHCCH_ALLOW_LONG_PATHS, &sourceAbsolutePath)`
- `0x1801d67e7`: `!(wil::verify_bool((__noop(destinationDirectory < ManagedDirectory::NumDirectories), ((destinationDirectory < ManagedDirectory::NumDirectories) ? 1 : 0))))`
- `0x1801d67c7`: `IdempotentSetString(_incomingPackageRoot, incomingPackageRoot)`
- `0x1801d679d`: `OSIntegration::DEH::FileManager::CopyFileToManagedDirectory`
- `0x1801d6849`: `OSIntegration::DEH::FileManager::CopyFileToManagedDirectory`
- `0x1801d68a7`: `OSIntegration::DEH::FileManager::CopyFileToManagedDirectory`
- `0x1801d692a`: `OSIntegration::DEH::FileManager::CopyFileToManagedDirectory`
- `0x1801d6784`: `IdempotentSetString(_incomingPackageMoniker, incomingPackageMoniker)`
- `0x1801d6981`: `InitializeFileOperationInfo( HStringReference(destinationAbsolutePath).Get(), HStringReference(sourceAbsolutePath).Get(), &fileOperationInfo)`
- `0x1801d6918`: `PathAllocCombine( destinationDirectoryPath.GetRawBuffer(nullptr), WindowsGetStringRawBuffer(relativeFilePath, nullptr), PATHCCH_ALLOW_LONG_PATHS, &destinationAbsolutePath)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::FileManager::CopyFileToManagedDirectory(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        int a4,
        int a5,
        HSTRING string)
{
  int v10; // ebx
  const char *v11; // rax
  __int64 v12; // rdx
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v14; // rax
  HRESULT v15; // eax
  int ManagedDirectory; // eax
  const WCHAR *v17; // rbx
  const WCHAR *v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rdx
  const char *v21; // rax
  HSTRING v22; // rbx
  __int64 v23; // rax
  struct OSIntegration::DEH::Internal::FileOperationInfo *v24; // r9
  int v25; // eax
  __int64 v26; // rcx
  char *v28; // [rsp+28h] [rbp-71h]
  HSTRING newString; // [rsp+30h] [rbp-69h] BYREF
  PWSTR v30; // [rsp+38h] [rbp-61h] BYREF
  PWSTR ppszPathOut; // [rsp+40h] [rbp-59h] BYREF
  HSTRING__ v32[4]; // [rsp+50h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-39h] BYREF
  HSTRING_HEADER v34; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v10 = OSIntegration::DEH::FileManager::IdempotentSetString((HSTRING *)(a1 + 32), a2);
  if ( v10 < 0 )
  {
    v11 = "IdempotentSetString(_incomingPackageMoniker, incomingPackageMoniker)";
    v12 = 144;
LABEL_3:
    LODWORD(v28) = v10;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
      "OSIntegration::DEH::FileManager::CopyFileToManagedDirectory",
      v11,
      v28,
      (int)newString);
    return (unsigned int)v10;
  }
  v10 = OSIntegration::DEH::FileManager::IdempotentSetString((HSTRING *)(a1 + 48), a3);
  if ( v10 < 0 )
  {
    v11 = "IdempotentSetString(_incomingPackageRoot, incomingPackageRoot)";
    v12 = 145;
    goto LABEL_3;
  }
  *(_DWORD *)(a1 + 64) = a4;
  if ( !a5 )
  {
    ppszPathOut = 0;
    *(_DWORD *)(a1 + 72) |= 1u;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v14 = WindowsGetStringRawBuffer(a3, 0);
    v15 = PathAllocCombine(v14, StringRawBuffer, 1u, &ppszPathOut);
    v10 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v28) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
        "OSIntegration::DEH::FileManager::CopyFileToManagedDirectory",
        "PathAllocCombine( WindowsGetStringRawBuffer(incomingPackageRoot, nullptr), WindowsGetStringRawBuffer(relativeFil"
        "ePath, nullptr), PATHCCH_ALLOW_LONG_PATHS, &sourceAbsolutePath)",
        v28,
        (int)newString);
LABEL_21:
      LocalFree(ppszPathOut);
      return (unsigned int)v10;
    }
    WindowsDeleteString(0);
    newString = 0;
    ManagedDirectory = OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(a2, &newString, 0);
    v10 = ManagedDirectory;
    if ( ManagedDirectory < 0 )
    {
      LODWORD(v28) = ManagedDirectory;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
        "OSIntegration::DEH::FileManager::CopyFileToManagedDirectory",
        "GetManagedDirectoryPath( destinationDirectory, incomingPackageMoniker, destinationDirectoryPath.GetAddressOf())",
        v28,
        (int)newString);
LABEL_20:
      WindowsDeleteString(newString);
      newString = 0;
      goto LABEL_21;
    }
    v30 = 0;
    v17 = WindowsGetStringRawBuffer(string, 0);
    v18 = WindowsGetStringRawBuffer(newString, 0);
    v19 = PathAllocCombine(v18, v17, 1u, &v30);
    v10 = v19;
    if ( v19 >= 0 )
    {
      *(_OWORD *)&v32[0].unused = 0;
      v22 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader) + 24);
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34);
      v25 = OSIntegration::DEH::Internal::InitializeFileOperationInfo(
              *(OSIntegration::DEH::Internal **)(v23 + 24),
              v22,
              v32,
              v24);
      v10 = v25;
      if ( v25 >= 0 )
      {
        v26 = *(_QWORD *)(a1 + 80);
        *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)&v32[0].unused;
        v10 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v26 + 104LL))(v26, &hstringHeader);
        goto LABEL_19;
      }
      LODWORD(v28) = v25;
      v20 = 178;
      v21 = "InitializeFileOperationInfo( HStringReference(destinationAbsolutePath).Get(), HStringReference(sourceAbsolut"
            "ePath).Get(), &fileOperationInfo)";
    }
    else
    {
      LODWORD(v28) = v19;
      v20 = 171;
      v21 = "PathAllocCombine( destinationDirectoryPath.GetRawBuffer(nullptr), WindowsGetStringRawBuffer(relativeFilePath"
            ", nullptr), PATHCCH_ALLOW_LONG_PATHS, &destinationAbsolutePath)";
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
      "OSIntegration::DEH::FileManager::CopyFileToManagedDirectory",
      v21,
      v28,
      (int)newString);
LABEL_19:
    LocalFree(v30);
    goto LABEL_20;
  }
  v10 = -2147024809;
  LODWORD(v28) = -2147024809;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x95,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
    "OSIntegration::DEH::FileManager::CopyFileToManagedDirectory",
    "!(wil::verify_bool((__noop(destinationDirectory < ManagedDirectory::NumDirectories), ((destinationDirectory < Manage"
    "dDirectory::NumDirectories) ? 1 : 0))))",
    v28,
    (int)newString);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801d6740  push    rbp
0x1801d6742  push    rbx
0x1801d6743  push    rsi
0x1801d6744  push    rdi
0x1801d6745  push    r12
0x1801d6747  push    r14
0x1801d6749  push    r15
0x1801d674b  lea     rbp, [rsp-17h]
0x1801d6750  sub     rsp, 0B0h
0x1801d6757  mov     rax, cs:__security_cookie
0x1801d675e  xor     rax, rsp
0x1801d6761  mov     [rbp+47h+var_40], rax
0x1801d6765  mov     r12, [rbp+47h+string]
0x1801d6769  mov     rdi, rcx
0x1801d676c  add     rcx, 20h ; ' '; newString
0x1801d6770  mov     r15d, r9d
0x1801d6773  mov     r14, r8
0x1801d6776  mov     rsi, rdx
0x1801d6779  call    ?IdempotentSetString@FileManager@DEH@OSIntegration@@CAJAEAVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; OSIntegration::DEH::FileManager::IdempotentSetString(Microsoft::WRL::Wrappers::HString &,HSTRING__ *)
0x1801d677e  mov     ebx, eax
0x1801d6780  test    eax, eax
0x1801d6782  jns     short loc_1801D67B5
0x1801d6784  lea     rax, aIdempotentsets_2; "IdempotentSetString(_incomingPackageMon"...
0x1801d678b  mov     edx, 90h; void *
0x1801d6790  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x1801d6794  mov     [rsp+0E0h+var_C0], rax; char *
0x1801d6799  mov     rcx, [rbp+4Fh]; this
0x1801d679d  lea     r9, aOsintegrationD_78; "OSIntegration::DEH::FileManager::CopyFi"...
0x1801d67a4  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801d67ab  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801d67b0  jmp     loc_1801D69CF
0x1801d67b5  lea     rcx, [rdi+30h]; newString
0x1801d67b9  mov     rdx, r14; HSTRING
0x1801d67bc  call    ?IdempotentSetString@FileManager@DEH@OSIntegration@@CAJAEAVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; OSIntegration::DEH::FileManager::IdempotentSetString(Microsoft::WRL::Wrappers::HString &,HSTRING__ *)
0x1801d67c1  mov     ebx, eax
0x1801d67c3  test    eax, eax
0x1801d67c5  jns     short loc_1801D67D5
0x1801d67c7  lea     rax, aIdempotentsets_0; "IdempotentSetString(_incomingPackageRoo"...
0x1801d67ce  mov     edx, 91h
0x1801d67d3  jmp     short loc_1801D6790
0x1801d67d5  mov     ecx, [rbp+47h+arg_20]
0x1801d67d8  mov     [rdi+40h], r15d
0x1801d67dc  mov     r15d, 1
0x1801d67e2  cmp     ecx, r15d
0x1801d67e5  jb      short loc_1801D6803
0x1801d67e7  lea     rdx, aWilVerifyBoolN_1; "!(wil::verify_bool((__noop(destinationD"...
0x1801d67ee  mov     ebx, 80070057h
0x1801d67f3  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1801d67f7  mov     [rsp+0E0h+var_C0], rdx
0x1801d67fc  mov     edx, 95h
0x1801d6801  jmp     short loc_1801D6799
0x1801d6803  mov     eax, r15d
0x1801d6806  mov     [rbp+47h+ppszPathOut], 0
0x1801d680e  shl     eax, cl
0x1801d6810  xor     edx, edx; length
0x1801d6812  or      [rdi+48h], eax
0x1801d6815  mov     rcx, r12; string
0x1801d6818  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d681e  xor     edx, edx; length
0x1801d6820  mov     rcx, r14; string
0x1801d6823  mov     rbx, rax
0x1801d6826  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d682c  lea     r9, [rbp+47h+ppszPathOut]; ppszPathOut
0x1801d6830  mov     r8d, r15d; dwFlags
0x1801d6833  mov     rcx, rax; pszPathIn
0x1801d6836  mov     rdx, rbx; pszMore
0x1801d6839  call    cs:__imp_PathAllocCombine
0x1801d683f  mov     ebx, eax
0x1801d6841  test    eax, eax
0x1801d6843  jns     short loc_1801D6876
0x1801d6845  mov     rcx, [rbp+4Fh]; this
0x1801d6849  lea     r9, aOsintegrationD_78; "OSIntegration::DEH::FileManager::CopyFi"...
0x1801d6850  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1801d6854  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801d685b  lea     rax, aPathalloccombi_3; "PathAllocCombine( WindowsGetStringRawBu"...
0x1801d6862  mov     edx, 9Eh; void *
0x1801d6867  mov     [rsp+0E0h+var_C0], rax; char *
0x1801d686c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801d6871  jmp     loc_1801D69C5
0x1801d6876  xor     ecx, ecx; string
0x1801d6878  mov     [rbp+47h+newString], 0
0x1801d6880  call    cs:__imp_WindowsDeleteString
0x1801d6886  xor     r8d, r8d; HSTRING *
0x1801d6889  mov     [rbp+47h+newString], 0
0x1801d6891  lea     rdx, [rbp+47h+newString]; newString
0x1801d6895  mov     rcx, rsi; string
0x1801d6898  call    ??$GetManagedDirectoryPath@$0A@@FileManager@DEH@OSIntegration@@CAJPEAUHSTRING__@@PEAPEAU3@1@Z; OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1801d689d  mov     ebx, eax
0x1801d689f  test    eax, eax
0x1801d68a1  jns     short loc_1801D68D4
0x1801d68a3  mov     rcx, [rbp+4Fh]; this
0x1801d68a7  lea     r9, aOsintegrationD_78; "OSIntegration::DEH::FileManager::CopyFi"...
0x1801d68ae  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1801d68b2  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801d68b9  lea     rax, aGetmanageddire; "GetManagedDirectoryPath( destinationDir"...
0x1801d68c0  mov     edx, 0A3h; void *
0x1801d68c5  mov     [rsp+0E0h+var_C0], rax; char *
0x1801d68ca  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801d68cf  jmp     loc_1801D69B3
0x1801d68d4  xor     edx, edx; length
0x1801d68d6  mov     [rbp+47h+var_A8], 0
0x1801d68de  mov     rcx, r12; string
0x1801d68e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d68e7  mov     rcx, [rbp+47h+newString]; string
0x1801d68eb  xor     edx, edx; length
0x1801d68ed  mov     rbx, rax
0x1801d68f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d68f6  lea     r9, [rbp+47h+var_A8]; ppszPathOut
0x1801d68fa  mov     r8d, r15d; dwFlags
0x1801d68fd  mov     rcx, rax; pszPathIn
0x1801d6900  mov     rdx, rbx; pszMore
0x1801d6903  call    cs:__imp_PathAllocCombine
0x1801d6909  mov     ebx, eax
0x1801d690b  test    eax, eax
0x1801d690d  jns     short loc_1801D693D
0x1801d690f  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x1801d6913  mov     edx, 0ABh; void *
0x1801d6918  lea     rax, aPathalloccombi; "PathAllocCombine( destinationDirectoryP"...
0x1801d691f  mov     rcx, [rbp+4Fh]; this
0x1801d6923  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801d692a  lea     r9, aOsintegrationD_78; "OSIntegration::DEH::FileManager::CopyFi"...
0x1801d6931  mov     [rsp+0E0h+var_C0], rax; char *
0x1801d6936  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801d693b  jmp     short loc_1801D69A9
0x1801d693d  xorps   xmm0, xmm0
0x1801d6940  lea     rdx, [rbp+47h+ppszPathOut]
0x1801d6944  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x1801d6948  movups  xmmword ptr [rbp+47h+var_90.unused], xmm0
0x1801d694c  call    ??$?0V?$AutoPtrLocal@G@Common@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$AutoPtrLocal@G@Common@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Common::AutoPtrLocal<ushort> const &,Microsoft::WRL::Details::Dummy)
0x1801d6951  lea     rdx, [rbp+47h+var_A8]
0x1801d6955  lea     rcx, [rbp+47h+var_60]; hstringHeader
0x1801d6959  mov     rbx, [rax+18h]
0x1801d695d  call    ??$?0V?$AutoPtrLocal@G@Common@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$AutoPtrLocal@G@Common@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Common::AutoPtrLocal<ushort> const &,Microsoft::WRL::Details::Dummy)
0x1801d6962  lea     r8, [rbp+47h+var_90]; HSTRING
0x1801d6966  mov     rdx, rbx; HSTRING
0x1801d6969  mov     rcx, [rax+18h]; this
0x1801d696d  call    ?InitializeFileOperationInfo@Internal@DEH@OSIntegration@@YAJPEAUHSTRING__@@0PEAUFileOperationInfo@123@@Z; OSIntegration::DEH::Internal::InitializeFileOperationInfo(HSTRING__ *,HSTRING__ *,OSIntegration::DEH::Internal::FileOperationInfo *)
0x1801d6972  mov     ebx, eax
0x1801d6974  test    eax, eax
0x1801d6976  jns     short loc_1801D698A
0x1801d6978  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1801d697c  mov     edx, 0B2h
0x1801d6981  lea     rax, aInitializefile; "InitializeFileOperationInfo( HStringRef"...
0x1801d6988  jmp     short loc_1801D691F
0x1801d698a  mov     rcx, [rdi+50h]
0x1801d698e  lea     rdx, [rbp+47h+hstringHeader]
0x1801d6992  movaps  xmm0, xmmword ptr [rbp+47h+var_90.unused]
0x1801d6996  movdqa  xmmword ptr [rbp+47h+hstringHeader.Reserved], xmm0
0x1801d699b  mov     rax, [rcx]
0x1801d699e  mov     rax, [rax+68h]
0x1801d69a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d69a7  mov     ebx, eax
0x1801d69a9  mov     rcx, [rbp+47h+var_A8]; hMem
0x1801d69ad  call    cs:__imp_LocalFree
0x1801d69b3  mov     rcx, [rbp+47h+newString]; string
0x1801d69b7  call    cs:__imp_WindowsDeleteString
0x1801d69bd  mov     [rbp+47h+newString], 0
0x1801d69c5  mov     rcx, [rbp+47h+ppszPathOut]; hMem
0x1801d69c9  call    cs:__imp_LocalFree
0x1801d69cf  mov     eax, ebx
0x1801d69d1  mov     rcx, [rbp+47h+var_40]
0x1801d69d5  xor     rcx, rsp; StackCookie
0x1801d69d8  call    __security_check_cookie
0x1801d69dd  add     rsp, 0B0h
0x1801d69e4  pop     r15
0x1801d69e6  pop     r14
0x1801d69e8  pop     r12
0x1801d69ea  pop     rdi
0x1801d69eb  pop     rsi
0x1801d69ec  pop     rbx
0x1801d69ed  pop     rbp
0x1801d69ee  retn
```
