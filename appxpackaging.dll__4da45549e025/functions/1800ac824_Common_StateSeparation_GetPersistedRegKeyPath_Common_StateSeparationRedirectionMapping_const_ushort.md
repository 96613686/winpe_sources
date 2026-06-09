# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x1800ac824`
- end: `0x1800acc12`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `1006`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800acc18`

## callees

- `0x1800059f0`
- `0x1800133fc`
- `0x1800538c8`
- `0x1800600ec`
- `0x1800603c0`
- `0x180074678`
- `0x1800992c4`
- `0x180099880`
- `0x18009d3c4`
- `0x1800ac590`
- `0x1800ac5dc`
- `0x1800ac638`
- `0x1800ac718`
- `0x1800ac824`
- `0x1800ad008`
- `0x1800ad038`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acaa4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acbac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acbcf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acaa4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acbac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800acbcf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ac9cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ac9cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac9f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac9f1`

## string_xrefs

- `0x1800ac9c4`: `kernelbase.dll`
- `0x1800ac860`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800ac8de`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800ac95d`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800ac9a7`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800aca85`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800acae1`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800acb2a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800acb72`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800ac9e7`: `GetPersistedRegistryLocationW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(
        const struct Common::StateSeparationRedirectionMapping *a1,
        unsigned __int16 **a2)
{
  int IsStateSeparationEnabled; // ebx
  unsigned __int16 **v4; // r8
  __int64 v5; // rdx
  Common *v7; // rax
  unsigned __int16 **v8; // r8
  int v9; // eax
  struct _RTL_AVL_TABLE *v10; // rax
  __int64 v11; // rdx
  unsigned int v12; // esi
  __int64 v13; // r9
  __int64 v14; // rdx
  Common *v15; // rax
  unsigned __int16 **v16; // r8
  int v17; // eax
  HMODULE Library; // rax
  HMODULE v19; // rbx
  FARPROC ProcAddress; // rsi
  unsigned __int16 *v21; // rdi
  unsigned int v22; // eax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // rcx
  int v26; // eax
  void *v27; // rcx
  int v28; // eax
  void *v29; // r14
  void *v30; // rdi
  int v31; // eax
  unsigned __int64 v32; // rdx
  unsigned __int16 **v33; // r8
  int v34; // [rsp+20h] [rbp-50h]
  void *v35[2]; // [rsp+40h] [rbp-30h] BYREF
  int v36; // [rsp+50h] [rbp-20h]
  void *v37[2]; // [rsp+58h] [rbp-18h] BYREF
  int v38; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  const struct Common::StateSeparationRedirectionMapping *v40; // [rsp+A0h] [rbp+30h] BYREF
  char v41; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v42; // [rsp+B8h] [rbp+48h]

  v40 = a1;
  LOBYTE(v40) = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&v40);
  if ( IsStateSeparationEnabled < 0 )
  {
    v5 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      v34);
    return (unsigned int)IsStateSeparationEnabled;
  }
  if ( !(_BYTE)v40 )
  {
    IsStateSeparationEnabled = Common::CopyStringToOutput(
                                 (Common *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx",
                                 (const unsigned __int16 *)a2,
                                 v4);
    if ( IsStateSeparationEnabled < 0 )
    {
      v5 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  wil::RtlAcquireSRWLockShared(&v40, &qword_18016A540);
  if ( qword_18016A548 )
  {
    v7 = (Common *)Common::GenericMap<unsigned short const *,IAppxFile *>::Find(
                     qword_18016A548,
                     Common::StateSeparation::AppxRoot);
    if ( v7 )
    {
      v9 = Common::CopyStringToOutput(v7, (const unsigned __int16 *)a2, v8);
      IsStateSeparationEnabled = v9;
      if ( v9 >= 0 )
        IsStateSeparationEnabled = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v9,
          v34);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v40);
  wil::RtlAcquireSRWLockExclusive(&v41, &qword_18016A540);
  v10 = qword_18016A548;
  if ( !qword_18016A548 )
  {
    v40 = (const struct Common::StateSeparationRedirectionMapping *)operator new(0x78u);
    v10 = (struct _RTL_AVL_TABLE *)Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMap<unsigned short const *,unsigned short const *>(
                                     v40,
                                     v11,
                                     Common::DeallocateArray<unsigned short const *>,
                                     Common::DeallocateArray<unsigned short const *>);
    qword_18016A548 = v10;
    if ( !v10 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)0x8007000ELL,
        v34);
      v13 = 2147942414LL;
      v14 = 297;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)v13,
        v34);
LABEL_43:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v41);
      return v12;
    }
  }
  v15 = (Common *)Common::GenericMap<unsigned short const *,IAppxFile *>::Find(v10, Common::StateSeparation::AppxRoot);
  if ( v15 )
  {
    v17 = Common::CopyStringToOutput(v15, (const unsigned __int16 *)a2, v16);
    v12 = v17;
    if ( v17 < 0 )
    {
      v13 = (unsigned int)v17;
      v14 = 305;
      goto LABEL_20;
    }
LABEL_42:
    v12 = 0;
    goto LABEL_43;
  }
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v19 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetPersistedRegistryLocationW");
    if ( ProcAddress )
    {
      v21 = 0;
      v42 = 0;
      LODWORD(v40) = 0;
      v22 = ((__int64 (__fastcall *)(unsigned __int16 *const, const wchar_t *, _QWORD, _QWORD))ProcAddress)(
              Common::StateSeparation::AppxRoot,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx",
              0,
              0);
      if ( v22 == 234 )
      {
        v21 = (unsigned __int16 *)operator new[]((unsigned int)v40);
        operator delete(0, v23);
        v42 = v21;
        v22 = ((__int64 (__fastcall *)(unsigned __int16 *const, const wchar_t *, unsigned __int16 *, _QWORD))ProcAddress)(
                Common::StateSeparation::AppxRoot,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx",
                v21,
                (unsigned int)v40);
      }
      if ( v22 )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v22,
                (unsigned int)&v40);
        v25 = v21;
LABEL_27:
        operator delete(v25, v24);
        FreeLibrary(v19);
        goto LABEL_43;
      }
      *a2 = v21;
      *(_OWORD *)v35 = 0;
      v36 = 0;
      v26 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v35, Common::StateSeparation::AppxRoot);
      v12 = v26;
      if ( v26 >= 0 )
      {
        *(_OWORD *)v37 = 0;
        v38 = 0;
        v28 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v37, *a2);
        v12 = v28;
        if ( v28 >= 0 )
        {
          v29 = v37[1];
          v30 = v35[1];
          v31 = Common::GenericMap<unsigned short const *,unsigned short const *>::Insert(
                  qword_18016A548,
                  v35[1],
                  v37[1]);
          v12 = v31;
          if ( v31 >= 0 )
          {
            operator delete(0, v32);
            FreeLibrary(v19);
            goto LABEL_42;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15B,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)(unsigned int)v31,
            (int)&v40);
          if ( v29 )
            operator delete(v29, v24);
          if ( !v30 )
            goto LABEL_32;
          v27 = v30;
          goto LABEL_31;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v28,
          (int)&v40);
        if ( v37[1] )
          operator delete(v37[1], v24);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v26,
          (int)&v40);
      }
      v27 = v35[1];
      if ( !v35[1] )
      {
LABEL_32:
        v25 = 0;
        goto LABEL_27;
      }
LABEL_31:
      operator delete(v27, v24);
      goto LABEL_32;
    }
  }
  if ( v19 )
    FreeLibrary(v19);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v41);
  IsStateSeparationEnabled = Common::CopyStringToOutput(
                               (Common *)L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx",
                               (const unsigned __int16 *)a2,
                               v33);
  if ( IsStateSeparationEnabled < 0 )
  {
    v5 = 357;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800ac824  mov     [rsp-28h+arg_0], rcx
0x1800ac829  push    rbp
0x1800ac82a  push    rbx
0x1800ac82b  push    rsi
0x1800ac82c  push    rdi
0x1800ac82d  push    r14
0x1800ac82f  mov     rbp, rsp
0x1800ac832  sub     rsp, 70h
0x1800ac836  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1800ac83e  mov     r14, rdx
0x1800ac841  mov     byte ptr [rbp+arg_0], 0
0x1800ac845  lea     rcx, [rbp+arg_0]; bool *
0x1800ac849  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1800ac84e  mov     ebx, eax
0x1800ac850  test    eax, eax
0x1800ac852  jns     short loc_1800AC873
0x1800ac854  mov     edx, 115h; void *
0x1800ac859  mov     rcx, [rbp+28h]; this
0x1800ac85d  mov     r9d, ebx; char *
0x1800ac860  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800ac867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac86c  mov     eax, ebx
0x1800ac86e  jmp     loc_1800ACC06
0x1800ac873  cmp     byte ptr [rbp+arg_0], 0
0x1800ac877  jnz     short loc_1800AC899
0x1800ac879  mov     rdx, r14; unsigned __int16 *
0x1800ac87c  mov     rcx, cs:off_180111CE0; this
0x1800ac883  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800ac888  mov     ebx, eax
0x1800ac88a  test    eax, eax
0x1800ac88c  jns     loc_1800ACC04
0x1800ac892  mov     edx, 119h
0x1800ac897  jmp     short loc_1800AC859
0x1800ac899  lea     rdx, qword_18016A540
0x1800ac8a0  lea     rcx, [rbp+arg_0]
0x1800ac8a4  call    ?RtlAcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockShared(_RTL_SRWLOCK *)
0x1800ac8a9  mov     rcx, cs:qword_18016A548
0x1800ac8b0  test    rcx, rcx
0x1800ac8b3  jz      short loc_1800AC901
0x1800ac8b5  mov     rdx, cs:?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppxRoot
0x1800ac8bc  call    ?Find@?$GenericMap@PEBGPEAUIAppxFile@@@Common@@QEAAPEAUIAppxFile@@PEBG@Z; Common::GenericMap<ushort const *,IAppxFile *>::Find(ushort const *)
0x1800ac8c1  test    rax, rax
0x1800ac8c4  jz      short loc_1800AC901
0x1800ac8c6  mov     rdx, r14; unsigned __int16 *
0x1800ac8c9  mov     rcx, rax; this
0x1800ac8cc  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800ac8d1  mov     ebx, eax
0x1800ac8d3  test    eax, eax
0x1800ac8d5  jns     short loc_1800AC8F1
0x1800ac8d7  mov     rcx, [rbp+28h]; this
0x1800ac8db  mov     r9d, eax; char *
0x1800ac8de  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800ac8e5  mov     edx, 122h; void *
0x1800ac8ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac8ef  jmp     short loc_1800AC8F3
0x1800ac8f1  xor     ebx, ebx
0x1800ac8f3  lea     rcx, [rbp+arg_0]
0x1800ac8f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ac8fc  jmp     loc_1800AC86C
0x1800ac901  lea     rcx, [rbp+arg_0]
0x1800ac905  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800ac90a  lea     rdx, qword_18016A540
0x1800ac911  lea     rcx, [rbp+arg_10]
0x1800ac915  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800ac91a  nop
0x1800ac91b  mov     rax, cs:qword_18016A548
0x1800ac922  test    rax, rax
0x1800ac925  jnz     short loc_1800AC976
0x1800ac927  lea     ecx, [rax+78h]; Size
0x1800ac92a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ac92f  mov     [rbp+arg_0], rax
0x1800ac933  lea     r8, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x1800ac93a  mov     r9, r8
0x1800ac93d  mov     rcx, rax
0x1800ac940  call    ??0?$GenericMap@PEBGPEBG@Common@@QEAA@P6A?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@ZP6AXPEBG@Z4@Z; Common::GenericMap<ushort const *,ushort const *>::GenericMap<ushort const *,ushort const *>(_RTL_GENERIC_COMPARE_RESULTS (*)(_RTL_AVL_TABLE *,void *,void *),void (*)(ushort const *),void (*)(ushort const *))
0x1800ac945  mov     cs:qword_18016A548, rax
0x1800ac94c  test    rax, rax
0x1800ac94f  jnz     short loc_1800AC976
0x1800ac951  mov     rcx, [rbp+28h]; this
0x1800ac955  mov     esi, 8007000Eh
0x1800ac95a  mov     r9d, esi; char *
0x1800ac95d  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800ac964  lea     edx, [rax+3Bh]; void *
0x1800ac967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac96c  mov     r9d, esi
0x1800ac96f  mov     edx, 129h
0x1800ac974  jmp     short loc_1800AC9A7
0x1800ac976  mov     rdx, cs:?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppxRoot
0x1800ac97d  mov     rcx, rax
0x1800ac980  call    ?Find@?$GenericMap@PEBGPEAUIAppxFile@@@Common@@QEAAPEAUIAppxFile@@PEBG@Z; Common::GenericMap<ushort const *,IAppxFile *>::Find(ushort const *)
0x1800ac985  test    rax, rax
0x1800ac988  jz      short loc_1800AC9BC
0x1800ac98a  mov     rdx, r14; unsigned __int16 *
0x1800ac98d  mov     rcx, rax; this
0x1800ac990  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800ac995  mov     esi, eax
0x1800ac997  test    eax, eax
0x1800ac999  jns     loc_1800ACBB8
0x1800ac99f  mov     r9d, eax; char *
0x1800ac9a2  mov     edx, 131h; void *
0x1800ac9a7  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800ac9ae  mov     rcx, [rbp+28h]; this
0x1800ac9b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac9b7  jmp     loc_1800ACBBA
0x1800ac9bc  xor     edx, edx; hFile
0x1800ac9be  mov     r8d, 800h; dwFlags
0x1800ac9c4  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ac9cb  call    cs:__imp_LoadLibraryExW
0x1800ac9d2  nop     dword ptr [rax+rax+00h]
0x1800ac9d7  mov     rbx, rax
0x1800ac9da  mov     [rbp+var_38], rax
0x1800ac9de  test    rax, rax
0x1800ac9e1  jz      loc_1800ACBC7
0x1800ac9e7  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x1800ac9ee  mov     rcx, rax; hModule
0x1800ac9f1  call    cs:__imp_GetProcAddress
0x1800ac9f8  nop     dword ptr [rax+rax+00h]
0x1800ac9fd  mov     rsi, rax
0x1800aca00  test    rax, rax
0x1800aca03  jz      loc_1800ACBC7
0x1800aca09  xor     edi, edi
0x1800aca0b  mov     [rbp+arg_18], rdi
0x1800aca0f  mov     dword ptr [rbp+arg_0], edi
0x1800aca12  lea     rax, [rbp+arg_0]
0x1800aca16  mov     qword ptr [rsp+70h+var_50], rax
0x1800aca1b  xor     r9d, r9d
0x1800aca1e  xor     r8d, r8d
0x1800aca21  mov     rdx, cs:off_180111CE0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aca28  mov     rcx, cs:?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppxRoot
0x1800aca2f  mov     rax, rsi
0x1800aca32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aca37  cmp     eax, 0EAh
0x1800aca3c  jnz     short loc_1800ACA7A
0x1800aca3e  mov     ecx, dword ptr [rbp+arg_0]; unsigned __int64
0x1800aca41  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800aca46  mov     rdi, rax
0x1800aca49  xor     ecx, ecx; void *
0x1800aca4b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800aca50  mov     [rbp+arg_18], rdi
0x1800aca54  lea     rax, [rbp+arg_0]
0x1800aca58  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800aca5d  mov     r9d, dword ptr [rbp+arg_0]
0x1800aca61  mov     r8, rdi
0x1800aca64  mov     rdx, cs:off_180111CE0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aca6b  mov     rcx, cs:?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppxRoot
0x1800aca72  mov     rax, rsi
0x1800aca75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aca7a  test    eax, eax
0x1800aca7c  jz      short loc_1800ACAB5
0x1800aca7e  mov     rcx, [rbp+28h]; this
0x1800aca82  mov     r9d, eax; char *
0x1800aca85  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800aca8c  mov     edx, 153h; void *
0x1800aca91  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800aca96  mov     esi, eax
0x1800aca98  mov     rcx, rdi; void *
0x1800aca9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800acaa0  nop
0x1800acaa1  mov     rcx, rbx; hLibModule
0x1800acaa4  call    cs:__imp_FreeLibrary
0x1800acaab  nop     dword ptr [rax+rax+00h]
0x1800acab0  jmp     loc_1800ACBBA
0x1800acab5  mov     [r14], rdi
0x1800acab8  xor     eax, eax
0x1800acaba  xorps   xmm0, xmm0
0x1800acabd  movups  xmmword ptr [rbp+var_30], xmm0
0x1800acac1  mov     [rbp+var_20], eax
0x1800acac4  mov     rdx, cs:?AppxRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; unsigned __int16 *
0x1800acacb  lea     rcx, [rbp+var_30]; this
0x1800acacf  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800acad4  mov     esi, eax
0x1800acad6  test    eax, eax
0x1800acad8  jns     short loc_1800ACB05
0x1800acada  mov     rcx, [rbp+28h]; this
0x1800acade  mov     r9d, eax; char *
0x1800acae1  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800acae8  mov     edx, 158h; void *
0x1800acaed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800acaf2  mov     rcx, [rbp+var_30+8]; void *
0x1800acaf6  test    rcx, rcx
0x1800acaf9  jz      short loc_1800ACB01
0x1800acafb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800acb00  nop
0x1800acb01  xor     ecx, ecx
0x1800acb03  jmp     short loc_1800ACA9B
0x1800acb05  xor     eax, eax
0x1800acb07  xorps   xmm0, xmm0
0x1800acb0a  movups  xmmword ptr [rbp+var_18], xmm0
0x1800acb0e  mov     [rbp+var_8], eax
0x1800acb11  mov     rdx, [r14]; unsigned __int16 *
0x1800acb14  lea     rcx, [rbp+var_18]; this
0x1800acb18  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800acb1d  mov     esi, eax
0x1800acb1f  test    eax, eax
0x1800acb21  jns     short loc_1800ACB4B
0x1800acb23  mov     rcx, [rbp+28h]; this
0x1800acb27  mov     r9d, eax; char *
0x1800acb2a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800acb31  mov     edx, 15Ah; void *
0x1800acb36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800acb3b  mov     rcx, [rbp+var_18+8]; void *
0x1800acb3f  test    rcx, rcx
0x1800acb42  jz      short loc_1800ACAF2
0x1800acb44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800acb49  jmp     short loc_1800ACAF2
0x1800acb4b  mov     r14, [rbp+var_18+8]
0x1800acb4f  mov     r8, r14
0x1800acb52  mov     rdi, [rbp+var_30+8]
0x1800acb56  mov     rdx, rdi
0x1800acb59  mov     rcx, cs:qword_18016A548
0x1800acb60  call    ?Insert@?$GenericMap@PEBGPEBG@Common@@QEAAJPEBG0@Z; Common::GenericMap<ushort const *,ushort const *>::Insert(ushort const *,ushort const *)
0x1800acb65  mov     esi, eax
0x1800acb67  test    eax, eax
0x1800acb69  jns     short loc_1800ACBA1
0x1800acb6b  mov     rcx, [rbp+28h]; this
0x1800acb6f  mov     r9d, eax; char *
0x1800acb72  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\common\\states"...
0x1800acb79  mov     edx, 15Bh; void *
0x1800acb7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800acb83  test    r14, r14
0x1800acb86  jz      short loc_1800ACB90
0x1800acb88  mov     rcx, r14; void *
0x1800acb8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800acb90  test    rdi, rdi
0x1800acb93  jz      loc_1800ACB01
0x1800acb99  mov     rcx, rdi
0x1800acb9c  jmp     loc_1800ACAFB
0x1800acba1  xor     ecx, ecx; void *
0x1800acba3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800acba8  nop
0x1800acba9  mov     rcx, rbx; hLibModule
0x1800acbac  call    cs:__imp_FreeLibrary
0x1800acbb3  nop     dword ptr [rax+rax+00h]
0x1800acbb8  xor     esi, esi
0x1800acbba  lea     rcx, [rbp+arg_10]
0x1800acbbe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800acbc3  mov     eax, esi
0x1800acbc5  jmp     short loc_1800ACC06
0x1800acbc7  test    rbx, rbx
0x1800acbca  jz      short loc_1800ACBDC
0x1800acbcc  mov     rcx, rbx; hLibModule
0x1800acbcf  call    cs:__imp_FreeLibrary
0x1800acbd6  nop     dword ptr [rax+rax+00h]
0x1800acbdb  nop
0x1800acbdc  lea     rcx, [rbp+arg_10]
0x1800acbe0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800acbe5  mov     rdx, r14; unsigned __int16 *
0x1800acbe8  mov     rcx, cs:off_180111CE0; this
0x1800acbef  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800acbf4  mov     ebx, eax
0x1800acbf6  test    eax, eax
0x1800acbf8  jns     short loc_1800ACC04
0x1800acbfa  mov     edx, 165h
0x1800acbff  jmp     loc_1800AC859
0x1800acc04  xor     eax, eax
0x1800acc06  add     rsp, 70h
0x1800acc0a  pop     r14
0x1800acc0c  pop     rdi
0x1800acc0d  pop     rsi
0x1800acc0e  pop     rbx
0x1800acc0f  pop     rbp
0x1800acc10  retn
```
