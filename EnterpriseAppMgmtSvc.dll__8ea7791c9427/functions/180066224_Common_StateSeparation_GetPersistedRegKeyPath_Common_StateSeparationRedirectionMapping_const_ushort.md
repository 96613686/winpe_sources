# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x180066224`
- end: `0x180066694`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `1136`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004010c`
- `0x180040510`

## callees

- `0x180001bf4`
- `0x180002a06`
- `0x180002aaf`
- `0x18000cfe8`
- `0x18002636c`
- `0x180065a64`
- `0x1800660cc`
- `0x180066144`
- `0x180066224`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180066496`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066598`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800665e3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006661b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066629`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066631`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066496`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066598`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800665e3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006661b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066629`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180066631`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800665ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006663a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066650`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800665ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006663a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180066650`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800662ca`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800663a3`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800662ca`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800663a3`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800665c9`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800665c9`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18006637c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18006637c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006630f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006631d`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006630f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006631d`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800662a1`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800662a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180066643`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180066659`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180066643`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180066659`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180066326`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180066326`

## string_xrefs

- `0x18006641a`: `kernelbase.dll`
- `0x18006625b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800662f4`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800663d5`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800663ea`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800664ca`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800664ec`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180066533`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006657b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800665ff`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180066438`: `GetPersistedRegistryLocationW`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(
        const struct Common::StateSeparationRedirectionMapping *a1,
        unsigned __int16 **a2)
{
  int IsStateSeparationEnabled; // ebx
  unsigned __int16 **v4; // r8
  __int64 v5; // rdx
  _QWORD *v7; // rax
  unsigned __int16 **v8; // r8
  Common *v9; // rcx
  int v10; // eax
  PRTL_AVL_TABLE v11; // rbx
  PVOID v12; // rax
  unsigned __int16 **v13; // r8
  Common *v14; // rcx
  int v15; // eax
  unsigned int v16; // esi
  __int64 v17; // r9
  __int64 v18; // rdx
  HMODULE Library; // rax
  HMODULE v20; // rbx
  FARPROC GetPersistedRegistryLocationW; // rax
  __int64 (__fastcall *v22)(_QWORD, _QWORD, _QWORD, _QWORD); // rsi
  unsigned __int16 *v23; // rdi
  unsigned int v24; // eax
  unsigned __int16 *v25; // rcx
  int v26; // eax
  void *v27; // rcx
  const unsigned __int16 *v28; // rdx
  int v29; // eax
  void *v30; // rdi
  void *v31; // r14
  unsigned __int16 **v32; // r8
  int TableContext; // [rsp+20h] [rbp-40h]
  __int128 Buffer; // [rsp+30h] [rbp-30h] BYREF
  int v35; // [rsp+40h] [rbp-20h]
  __int128 v36; // [rsp+48h] [rbp-18h] BYREF
  int v37; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  const struct Common::StateSeparationRedirectionMapping *NewElement; // [rsp+90h] [rbp+30h] BYREF
  size_t Size; // [rsp+A0h] [rbp+40h] BYREF

  NewElement = a1;
  LOBYTE(NewElement) = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&NewElement);
  if ( IsStateSeparationEnabled < 0 )
  {
    v5 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      TableContext);
    return (unsigned int)IsStateSeparationEnabled;
  }
  if ( !(_BYTE)NewElement )
  {
    IsStateSeparationEnabled = Common::CopyStringToOutput(
                                 (Common *)L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
                                 (unsigned __int16 *)a2,
                                 v4);
    if ( IsStateSeparationEnabled < 0 )
    {
      v5 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  RtlAcquireSRWLockShared(&qword_180090EF8);
  if ( Table )
  {
    Buffer = (unsigned __int64)Common::StateSeparation::AppModelRoot;
    v7 = RtlLookupElementGenericTableAvl(Table, &Buffer);
    v9 = v7 ? (Common *)v7[1] : 0LL;
    if ( v9 )
    {
      v10 = Common::CopyStringToOutput(v9, (unsigned __int16 *)a2, v8);
      IsStateSeparationEnabled = v10;
      if ( v10 >= 0 )
        IsStateSeparationEnabled = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v10,
          TableContext);
      RtlReleaseSRWLockShared(&qword_180090EF8);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  RtlReleaseSRWLockShared(&qword_180090EF8);
  RtlAcquireSRWLockExclusive(&qword_180090EF8);
  v11 = Table;
  if ( !Table )
  {
    v11 = (PRTL_AVL_TABLE)operator new(0x78u);
    if ( !v11 )
    {
      v16 = -2147024882;
      Table = 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)0x8007000ELL,
        TableContext);
      v17 = 2147942414LL;
      v18 = 297;
      goto LABEL_24;
    }
    v11[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    v11[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    RtlInitializeGenericTableAvl(
      v11,
      Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
      Common::GenericMap<unsigned short *,MsixPackage::Provisioning::Library::HardlinkTarget *>::GenericMapFree,
      0);
    Table = v11;
  }
  Buffer = (unsigned __int64)Common::StateSeparation::AppModelRoot;
  v12 = RtlLookupElementGenericTableAvl(v11, &Buffer);
  if ( v12 )
  {
    v14 = (Common *)*((_QWORD *)v12 + 1);
    if ( v14 )
    {
      v15 = Common::CopyStringToOutput(v14, (unsigned __int16 *)a2, v13);
      v16 = v15;
      if ( v15 < 0 )
      {
        v17 = (unsigned int)v15;
        v18 = 305;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)v17,
          TableContext);
LABEL_54:
        RtlReleaseSRWLockExclusive(&qword_180090EF8);
        return v16;
      }
LABEL_45:
      v16 = 0;
      goto LABEL_54;
    }
  }
  Library = LoadLibraryExW_0(L"kernelbase.dll", 0, 0x800u);
  v20 = Library;
  if ( Library )
  {
    GetPersistedRegistryLocationW = GetProcAddress_0(Library, "GetPersistedRegistryLocationW");
    v22 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetPersistedRegistryLocationW;
    if ( GetPersistedRegistryLocationW )
    {
      v23 = 0;
      LODWORD(Size) = 0;
      v24 = ((__int64 (__fastcall *)(unsigned __int16 *const, const wchar_t *, _QWORD, _QWORD))GetPersistedRegistryLocationW)(
              Common::StateSeparation::AppModelRoot,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
              0,
              0);
      if ( v24 == 234 )
      {
        v23 = (unsigned __int16 *)operator new((unsigned int)Size);
        if ( !v23 )
        {
          v16 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)0x8007000ELL,
            (int)&Size);
          goto LABEL_52;
        }
        operator delete[](0);
        v24 = v22(
                Common::StateSeparation::AppModelRoot,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
                v23,
                (unsigned int)Size);
      }
      if ( v24 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v24,
                (unsigned int)&Size);
        v25 = v23;
LABEL_53:
        operator delete[](v25);
        FreeLibrary(v20);
        goto LABEL_54;
      }
      *a2 = v23;
      v35 = 0;
      Buffer = 0;
      v26 = Common::StringBuffer::SetValueFromString(
              (Common::StringBuffer *)&Buffer,
              Common::StateSeparation::AppModelRoot);
      v16 = v26;
      if ( v26 >= 0 )
      {
        v28 = *a2;
        v36 = 0;
        v37 = 0;
        v29 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v36, v28);
        v16 = v29;
        if ( v29 >= 0 )
        {
          v30 = (void *)*((_QWORD *)&Buffer + 1);
          v31 = (void *)*((_QWORD *)&v36 + 1);
          *(_QWORD *)&Buffer = *((_QWORD *)&Buffer + 1);
          *((_QWORD *)&Buffer + 1) = *((_QWORD *)&v36 + 1);
          LOBYTE(NewElement) = 0;
          if ( RtlInsertElementGenericTableAvl(Table, &Buffer, 0x10u, (PBOOLEAN)&NewElement) )
          {
            if ( (_BYTE)NewElement )
            {
              operator delete[](0);
              FreeLibrary(v20);
              goto LABEL_45;
            }
            v16 = -2147024198;
          }
          else
          {
            v16 = -2147024882;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15B,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)v16,
            (int)&Size);
          if ( v31 )
            operator delete[](v31);
          if ( !v30 )
            goto LABEL_52;
          v27 = v30;
          goto LABEL_51;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v29,
          (int)&Size);
        if ( *((_QWORD *)&v36 + 1) )
          operator delete[](*((void **)&v36 + 1));
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v26,
          (int)&Size);
      }
      v27 = (void *)*((_QWORD *)&Buffer + 1);
      if ( *((_QWORD *)&Buffer + 1) )
LABEL_51:
        operator delete[](v27);
LABEL_52:
      v25 = 0;
      goto LABEL_53;
    }
    FreeLibrary(v20);
  }
  RtlReleaseSRWLockExclusive(&qword_180090EF8);
  IsStateSeparationEnabled = Common::CopyStringToOutput(
                               (Common *)L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
                               (unsigned __int16 *)a2,
                               v32);
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
0x180066224  mov     [rsp-28h+arg_8], rbx
0x180066229  mov     [rsp-28h+NewElement], rcx
0x18006622e  push    rbp
0x18006622f  push    rsi
0x180066230  push    rdi
0x180066231  push    r12
0x180066233  push    r14
0x180066235  mov     rbp, rsp
0x180066238  sub     rsp, 60h
0x18006623c  lea     rcx, [rbp+NewElement]; bool *
0x180066240  mov     byte ptr [rbp+NewElement], 0
0x180066244  mov     r14, rdx
0x180066247  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18006624c  mov     ebx, eax
0x18006624e  test    eax, eax
0x180066250  jns     short loc_180066271
0x180066252  mov     edx, 115h; void *
0x180066257  mov     rcx, [rbp+28h]; this
0x18006625b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x180066262  mov     r9d, ebx; char *
0x180066265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006626a  mov     eax, ebx
0x18006626c  jmp     loc_180066680
0x180066271  cmp     byte ptr [rbp+NewElement], 0
0x180066275  jnz     short loc_180066297
0x180066277  mov     rcx, cs:off_18006C488; this
0x18006627e  mov     rdx, r14; unsigned __int16 *
0x180066281  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180066286  mov     ebx, eax
0x180066288  test    eax, eax
0x18006628a  jns     loc_18006667E
0x180066290  mov     edx, 119h
0x180066295  jmp     short loc_180066257
0x180066297  lea     r12, qword_180090EF8
0x18006629e  mov     rcx, r12
0x1800662a1  call    cs:__imp_RtlAcquireSRWLockShared
0x1800662a7  mov     rcx, cs:Table; Table
0x1800662ae  test    rcx, rcx
0x1800662b1  jz      short loc_18006631A
0x1800662b3  mov     rax, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x1800662ba  lea     rdx, [rbp+Buffer]; Buffer
0x1800662be  mov     qword ptr [rbp+Buffer], rax
0x1800662c2  mov     qword ptr [rbp+Buffer+8], 0
0x1800662ca  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800662d0  test    rax, rax
0x1800662d3  jnz     short loc_1800662D9
0x1800662d5  xor     ecx, ecx
0x1800662d7  jmp     short loc_1800662DD
0x1800662d9  mov     rcx, [rax+8]; this
0x1800662dd  test    rcx, rcx
0x1800662e0  jz      short loc_18006631A
0x1800662e2  mov     rdx, r14; unsigned __int16 *
0x1800662e5  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800662ea  mov     ebx, eax
0x1800662ec  test    eax, eax
0x1800662ee  jns     short loc_18006630A
0x1800662f0  mov     rcx, [rbp+28h]; this
0x1800662f4  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x1800662fb  mov     r9d, eax; char *
0x1800662fe  mov     edx, 122h; void *
0x180066303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066308  jmp     short loc_18006630C
0x18006630a  xor     ebx, ebx
0x18006630c  mov     rcx, r12
0x18006630f  call    cs:__imp_RtlReleaseSRWLockShared
0x180066315  jmp     loc_18006626A
0x18006631a  mov     rcx, r12
0x18006631d  call    cs:__imp_RtlReleaseSRWLockShared
0x180066323  mov     rcx, r12
0x180066326  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18006632c  mov     rbx, cs:Table
0x180066333  test    rbx, rbx
0x180066336  jnz     short loc_180066389
0x180066338  lea     ecx, [rbx+78h]; Size
0x18006633b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066340  mov     rbx, rax
0x180066343  test    rax, rax
0x180066346  jz      loc_1800663E6
0x18006634c  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x180066353  mov     qword ptr [rsp+60h+TableContext], 0; int
0x18006635c  lea     r9, ?GenericMapFree@?$GenericMap@PEAGPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180066363  mov     [rbx+68h], rax
0x180066367  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18006636e  mov     [rbx+70h], rax
0x180066372  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180066379  mov     rcx, rbx; Table
0x18006637c  call    cs:__imp_RtlInitializeGenericTableAvl
0x180066382  mov     cs:Table, rbx
0x180066389  mov     rax, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x180066390  lea     rdx, [rbp+Buffer]; Buffer
0x180066394  mov     rcx, rbx; Table
0x180066397  mov     qword ptr [rbp+Buffer], rax
0x18006639b  mov     qword ptr [rbp+Buffer+8], 0
0x1800663a3  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800663a9  test    rax, rax
0x1800663ac  jz      short loc_180066418
0x1800663ae  mov     rcx, [rax+8]; this
0x1800663b2  test    rcx, rcx
0x1800663b5  jz      short loc_180066418
0x1800663b7  mov     rdx, r14; unsigned __int16 *
0x1800663ba  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800663bf  mov     esi, eax
0x1800663c1  test    eax, eax
0x1800663c3  jns     loc_1800665F2
0x1800663c9  mov     r9d, eax; char *
0x1800663cc  mov     edx, 131h; void *
0x1800663d1  mov     rcx, [rbp+28h]; this
0x1800663d5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x1800663dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800663e1  jmp     loc_180066640
0x1800663e6  mov     rcx, [rbp+28h]; this
0x1800663ea  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x1800663f1  mov     esi, 8007000Eh
0x1800663f6  mov     cs:Table, 0
0x180066401  mov     r9d, esi; char *
0x180066404  mov     edx, 3Bh ; ';'; void *
0x180066409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006640e  mov     r9d, esi
0x180066411  mov     edx, 129h
0x180066416  jmp     short loc_1800663D1
0x180066418  xor     edx, edx; hFile
0x18006641a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180066421  mov     r8d, 800h; dwFlags
0x180066427  call    LoadLibraryExW_0
0x18006642c  mov     rbx, rax
0x18006642f  test    rax, rax
0x180066432  jz      loc_180066656
0x180066438  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x18006643f  mov     rcx, rax; hModule
0x180066442  call    GetProcAddress_0
0x180066447  mov     rsi, rax
0x18006644a  test    rax, rax
0x18006644d  jz      loc_18006664D
0x180066453  mov     rdx, cs:off_18006C488; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006645a  lea     rax, [rbp+Size]
0x18006645e  mov     rcx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x180066465  xor     edi, edi
0x180066467  mov     qword ptr [rsp+60h+TableContext], rax; int
0x18006646c  xor     r9d, r9d
0x18006646f  mov     rax, rsi
0x180066472  mov     dword ptr [rbp+Size], edi
0x180066475  xor     r8d, r8d
0x180066478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006647d  cmp     eax, 0EAh
0x180066482  jnz     short loc_1800664C2
0x180066484  mov     ecx, dword ptr [rbp+Size]; Size
0x180066487  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006648c  mov     rdi, rax
0x18006648f  test    rax, rax
0x180066492  jz      short loc_1800664E8
0x180066494  xor     ecx, ecx
0x180066496  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006649c  mov     r9d, dword ptr [rbp+Size]
0x1800664a0  lea     rax, [rbp+Size]
0x1800664a4  mov     rdx, cs:off_18006C488; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800664ab  mov     r8, rdi
0x1800664ae  mov     rcx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x1800664b5  mov     qword ptr [rsp+60h+TableContext], rax; int
0x1800664ba  mov     rax, rsi
0x1800664bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664c2  test    eax, eax
0x1800664c4  jz      short loc_18006650A
0x1800664c6  mov     rcx, [rbp+28h]; this
0x1800664ca  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x1800664d1  mov     r9d, eax; char *
0x1800664d4  mov     edx, 153h; void *
0x1800664d9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800664de  mov     esi, eax
0x1800664e0  mov     rcx, rdi
0x1800664e3  jmp     loc_180066631
0x1800664e8  mov     rcx, [rbp+28h]; this
0x1800664ec  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x1800664f3  mov     esi, 8007000Eh
0x1800664f8  mov     edx, 14Ah; void *
0x1800664fd  mov     r9d, esi; char *
0x180066500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066505  jmp     loc_18006662F
0x18006650a  mov     [r14], rdi
0x18006650d  lea     rcx, [rbp+Buffer]; this
0x180066511  mov     rdx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Src
0x180066518  xor     eax, eax
0x18006651a  xorps   xmm0, xmm0
0x18006651d  mov     [rbp+var_20], eax
0x180066520  movups  [rbp+Buffer], xmm0
0x180066524  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180066529  mov     esi, eax
0x18006652b  test    eax, eax
0x18006652d  jns     short loc_180066559
0x18006652f  mov     rcx, [rbp+28h]; this
0x180066533  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006653a  mov     r9d, eax; char *
0x18006653d  mov     edx, 158h; void *
0x180066542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066547  mov     rcx, qword ptr [rbp+Buffer+8]
0x18006654b  test    rcx, rcx
0x18006654e  jz      loc_18006662F
0x180066554  jmp     loc_180066629
0x180066559  mov     rdx, [r14]; Src
0x18006655c  lea     rcx, [rbp+var_18]; this
0x180066560  xor     eax, eax
0x180066562  xorps   xmm0, xmm0
0x180066565  movups  [rbp+var_18], xmm0
0x180066569  mov     [rbp+var_8], eax
0x18006656c  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180066571  mov     esi, eax
0x180066573  test    eax, eax
0x180066575  jns     short loc_1800665A0
0x180066577  mov     rcx, [rbp+28h]; this
0x18006657b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x180066582  mov     r9d, eax; char *
0x180066585  mov     edx, 15Ah; void *
0x18006658a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006658f  mov     rcx, qword ptr [rbp+var_18+8]
0x180066593  test    rcx, rcx
0x180066596  jz      short loc_180066547
0x180066598  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006659e  jmp     short loc_180066547
0x1800665a0  mov     rdi, qword ptr [rbp+Buffer+8]
0x1800665a4  lea     r9, [rbp+NewElement]; NewElement
0x1800665a8  mov     r14, qword ptr [rbp+var_18+8]
0x1800665ac  lea     rdx, [rbp+Buffer]; Buffer
0x1800665b0  mov     rcx, cs:Table; Table
0x1800665b7  mov     r8d, 10h; BufferSize
0x1800665bd  mov     qword ptr [rbp+Buffer], rdi
0x1800665c1  mov     qword ptr [rbp+Buffer+8], r14
0x1800665c5  mov     byte ptr [rbp+NewElement], 0
0x1800665c9  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800665cf  test    rax, rax
0x1800665d2  jz      short loc_1800665F6
0x1800665d4  cmp     byte ptr [rbp+NewElement], 0
0x1800665d8  jnz     short loc_1800665E1
0x1800665da  mov     esi, 800702BAh
0x1800665df  jmp     short loc_1800665FB
0x1800665e1  xor     ecx, ecx
0x1800665e3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800665e9  mov     rcx, rbx; hLibModule
0x1800665ec  call    cs:__imp_FreeLibrary
0x1800665f2  xor     esi, esi
0x1800665f4  jmp     short loc_180066640
0x1800665f6  mov     esi, 8007000Eh
0x1800665fb  mov     rcx, [rbp+28h]; this
0x1800665ff  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x180066606  mov     r9d, esi; char *
0x180066609  mov     edx, 15Bh; void *
0x18006660e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066613  test    r14, r14
0x180066616  jz      short loc_180066621
0x180066618  mov     rcx, r14
0x18006661b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180066621  test    rdi, rdi
0x180066624  jz      short loc_18006662F
0x180066626  mov     rcx, rdi
0x180066629  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006662f  xor     ecx, ecx
0x180066631  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180066637  mov     rcx, rbx; hLibModule
0x18006663a  call    cs:__imp_FreeLibrary
0x180066640  mov     rcx, r12
0x180066643  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180066649  mov     eax, esi
0x18006664b  jmp     short loc_180066680
0x18006664d  mov     rcx, rbx; hLibModule
0x180066650  call    cs:__imp_FreeLibrary
0x180066656  mov     rcx, r12
0x180066659  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18006665f  mov     rcx, cs:off_18006C488; this
0x180066666  mov     rdx, r14; unsigned __int16 *
0x180066669  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18006666e  mov     ebx, eax
0x180066670  test    eax, eax
0x180066672  jns     short loc_18006667E
0x180066674  mov     edx, 165h
0x180066679  jmp     loc_180066257
0x18006667e  xor     eax, eax
0x180066680  mov     rbx, [rsp+60h+arg_8]
0x180066688  add     rsp, 60h
0x18006668c  pop     r14
0x18006668e  pop     r12
0x180066690  pop     rdi
0x180066691  pop     rsi
0x180066692  pop     rbp
0x180066693  retn
```
