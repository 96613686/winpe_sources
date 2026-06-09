# Microsoft::Resources::CStringResolverInternal::_ResurrectPriBuilder(void)

- ea: `0x1800ab138`
- end: `0x1800ab2c0`
- name: `?_ResurrectPriBuilder@CStringResolverInternal@Resources@Microsoft@@AEAAJXZ`
- size: `392`
- prototype: `__int64 __fastcall(Microsoft::Resources::CStringResolverInternal *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800aa698`
- `0x1800aa7c0`

## callees

- `0x18000f8fc`
- `0x1800204c0`
- `0x18002c8d0`
- `0x18009ba7c`
- `0x18009cb24`
- `0x1800ab138`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab1bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab1bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab1cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab1cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ab229`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ab229`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ab238`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ab238`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Resources::CStringResolverInternal::_ResurrectPriBuilder(
        Microsoft::Resources::CStringResolverInternal *this)
{
  int v2; // eax
  int QualifierSetBuilder; // edi
  __int64 v4; // rdx
  struct Microsoft::Resources::Build::PriFileMerger *v5; // rbp
  unsigned __int64 v6; // r9
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  struct Microsoft::Resources::Build::DecisionInfoQualifierSetBuilder **v9; // rdi
  __int64 v10; // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  Microsoft::Resources::Build::PriSectionBuilder *v12; // rcx
  int v14; // [rsp+20h] [rbp-48h]
  const int *v15; // [rsp+30h] [rbp-38h] BYREF
  struct Microsoft::Resources::Build::PriFileMerger *v16; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v15 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UserLanguageProfileQVProvider>::`vftable';
  v16 = 0;
  v2 = Microsoft::Resources::Build::PriFileMerger::CreateInstance(
         *(struct Microsoft::Resources::CoreProfile **)this,
         &v16);
  QualifierSetBuilder = v2;
  if ( v2 < 0 )
  {
    v4 = 343;
LABEL_5:
    v6 = (unsigned int)v2;
    goto LABEL_6;
  }
  v5 = v16;
  v2 = Microsoft::Resources::Build::PriFileMerger::InitWithPri(v16, *((_QWORD *)this + 4), *((_QWORD *)this + 5));
  QualifierSetBuilder = v2;
  if ( v2 < 0 )
  {
    v4 = 345;
    goto LABEL_5;
  }
  v7 = (void *)*((_QWORD *)this + 4);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v9 = (struct Microsoft::Resources::Build::DecisionInfoQualifierSetBuilder **)((char *)this + 24);
  v10 = *((_QWORD *)this + 3);
  if ( v10 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 56LL))(v10, 1);
  *v9 = 0;
  v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  if ( v11 )
    (**v11)(v11, 1);
  *((_QWORD *)this + 1) = 0;
  if ( GetFileAttributesW((LPCWSTR)this + 56) != -1 )
    DeleteFileW((LPCWSTR)this + 56);
  if ( *((int *)v5 + 6) >= 2 )
  {
    *((_QWORD *)this + 1) = *((_QWORD *)v5 + 1);
    *((_QWORD *)v5 + 1) = 0;
    *((_DWORD *)v5 + 6) = 5;
    v12 = *(Microsoft::Resources::Build::PriSectionBuilder **)(*((_QWORD *)this + 1) + 96LL);
    *((_QWORD *)this + 2) = v12;
    QualifierSetBuilder = Microsoft::Resources::Build::PriSectionBuilder::GetQualifierSetBuilder(v12, v9);
  }
  else
  {
    QualifierSetBuilder = -2147020579;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
      (const char *)0x800710DDLL,
      v14);
  }
  *((_DWORD *)this + 18) = 0;
  if ( QualifierSetBuilder >= 0 )
  {
    QualifierSetBuilder = 0;
    goto LABEL_21;
  }
  v6 = (unsigned int)QualifierSetBuilder;
  v4 = 370;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\stringresolver\\src\\cstringresolverinternal.cpp",
    (const char *)v6,
    v14);
LABEL_21:
  Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>::~AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>(&v15);
  return (unsigned int)QualifierSetBuilder;
}

```

## disassembly

```asm
0x1800ab138  push    rbx
0x1800ab13a  push    rbp
0x1800ab13b  push    rsi
0x1800ab13c  push    rdi
0x1800ab13d  sub     rsp, 48h
0x1800ab141  mov     rbx, rcx
0x1800ab144  lea     rax, ??_7?$AutoDeletePtr@VUserLanguageProfileQVProvider@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UserLanguageProfileQVProvider>::`vftable'
0x1800ab14b  mov     [rsp+68h+var_38], rax
0x1800ab150  mov     [rsp+68h+var_30], 0
0x1800ab159  lea     rdx, [rsp+68h+var_30]; struct Microsoft::Resources::Build::PriFileMerger **
0x1800ab15e  mov     rcx, [rcx]; struct Microsoft::Resources::CoreProfile *
0x1800ab161  call    ?CreateInstance@PriFileMerger@Build@Resources@Microsoft@@SAJPEAVCoreProfile@34@PEAPEAV1234@@Z; Microsoft::Resources::Build::PriFileMerger::CreateInstance(Microsoft::Resources::CoreProfile *,Microsoft::Resources::Build::PriFileMerger * *)
0x1800ab166  mov     edi, eax
0x1800ab168  test    eax, eax
0x1800ab16a  jns     short loc_1800AB173
0x1800ab16c  mov     edx, 157h
0x1800ab171  jmp     short loc_1800AB19B
0x1800ab173  mov     rax, [rbx]
0x1800ab176  mov     [rsp+68h+var_40], rax
0x1800ab17b  mov     r8, [rbx+28h]
0x1800ab17f  mov     rdx, [rbx+20h]
0x1800ab183  mov     rbp, [rsp+68h+var_30]
0x1800ab188  mov     rcx, rbp
0x1800ab18b  call    ?InitWithPri@PriFileMerger@Build@Resources@Microsoft@@QEAAJPEBE_KW4PriMergeFlags@1234@PEBGPEAVCoreProfile@34@@Z; Microsoft::Resources::Build::PriFileMerger::InitWithPri(uchar const *,unsigned __int64,Microsoft::Resources::Build::PriFileMerger::PriMergeFlags,ushort const *,Microsoft::Resources::CoreProfile *)
0x1800ab190  mov     edi, eax
0x1800ab192  test    eax, eax
0x1800ab194  jns     short loc_1800AB1B4
0x1800ab196  mov     edx, 159h; void *
0x1800ab19b  mov     r9d, eax; char *
0x1800ab19e  mov     rcx, [rsp+68h]; this
0x1800ab1a3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\mrt\\runtime\\stringr"...
0x1800ab1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab1af  jmp     loc_1800AB2AB
0x1800ab1b4  mov     rdi, [rbx+20h]
0x1800ab1b8  test    rdi, rdi
0x1800ab1bb  jz      short loc_1800AB1D1
0x1800ab1bd  call    cs:__imp_GetProcessHeap
0x1800ab1c3  mov     r8, rdi; lpMem
0x1800ab1c6  xor     edx, edx; dwFlags
0x1800ab1c8  mov     rcx, rax; hHeap
0x1800ab1cb  call    cs:__imp_HeapFree
0x1800ab1d1  mov     qword ptr [rbx+20h], 0
0x1800ab1d9  mov     qword ptr [rbx+28h], 0
0x1800ab1e1  lea     rdi, [rbx+18h]
0x1800ab1e5  mov     rcx, [rdi]
0x1800ab1e8  mov     esi, 1
0x1800ab1ed  test    rcx, rcx
0x1800ab1f0  jz      short loc_1800AB200
0x1800ab1f2  mov     rax, [rcx]
0x1800ab1f5  mov     edx, esi
0x1800ab1f7  mov     rax, [rax+38h]
0x1800ab1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab200  mov     qword ptr [rdi], 0
0x1800ab207  mov     rcx, [rbx+8]
0x1800ab20b  test    rcx, rcx
0x1800ab20e  jz      short loc_1800AB21D
0x1800ab210  mov     rax, [rcx]
0x1800ab213  mov     edx, esi
0x1800ab215  mov     rax, [rax]
0x1800ab218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab21d  mov     qword ptr [rbx+8], 0
0x1800ab225  lea     rcx, [rbx+70h]; lpFileName
0x1800ab229  call    cs:__imp_GetFileAttributesW
0x1800ab22f  cmp     eax, 0FFFFFFFFh
0x1800ab232  jz      short loc_1800AB23E
0x1800ab234  lea     rcx, [rbx+70h]; lpFileName
0x1800ab238  call    cs:__imp_DeleteFileW
0x1800ab23e  cmp     dword ptr [rbp+18h], 2
0x1800ab242  jge     short loc_1800AB264
0x1800ab244  mov     rcx, [rsp+68h]; this
0x1800ab249  mov     edi, 800710DDh
0x1800ab24e  mov     r9d, edi; char *
0x1800ab251  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x1800ab258  mov     edx, 3F2h; void *
0x1800ab25d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab262  jmp     short loc_1800AB291
0x1800ab264  mov     rax, [rbp+8]
0x1800ab268  mov     [rbx+8], rax
0x1800ab26c  mov     qword ptr [rbp+8], 0
0x1800ab274  mov     dword ptr [rbp+18h], 5
0x1800ab27b  mov     rax, [rbx+8]
0x1800ab27f  mov     rcx, [rax+60h]; this
0x1800ab283  mov     [rbx+10h], rcx
0x1800ab287  mov     rdx, rdi; struct Microsoft::Resources::Build::DecisionInfoQualifierSetBuilder **
0x1800ab28a  call    ?GetQualifierSetBuilder@PriSectionBuilder@Build@Resources@Microsoft@@QEBAJPEAPEAVDecisionInfoQualifierSetBuilder@234@@Z; Microsoft::Resources::Build::PriSectionBuilder::GetQualifierSetBuilder(Microsoft::Resources::Build::DecisionInfoQualifierSetBuilder * *)
0x1800ab28f  mov     edi, eax
0x1800ab291  mov     dword ptr [rbx+48h], 0
0x1800ab298  test    edi, edi
0x1800ab29a  jns     short loc_1800AB2A9
0x1800ab29c  mov     r9d, edi
0x1800ab29f  mov     edx, 172h
0x1800ab2a4  jmp     loc_1800AB19E
0x1800ab2a9  xor     edi, edi
0x1800ab2ab  lea     rcx, [rsp+68h+var_38]
0x1800ab2b0  call    ??1?$AutoDeletePtr@VEnvironmentReferenceBuilder@Build@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>::~AutoDeletePtr<Microsoft::Resources::Build::EnvironmentReferenceBuilder>(void)
0x1800ab2b5  mov     eax, edi
0x1800ab2b7  add     rsp, 48h
0x1800ab2bb  pop     rdi
0x1800ab2bc  pop     rsi
0x1800ab2bd  pop     rbp
0x1800ab2be  pop     rbx
0x1800ab2bf  retn
```
