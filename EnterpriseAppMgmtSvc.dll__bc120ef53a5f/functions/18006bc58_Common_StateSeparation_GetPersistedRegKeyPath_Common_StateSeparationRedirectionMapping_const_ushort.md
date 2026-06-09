# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x18006bc58`
- end: `0x18006c13b`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `1251`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043c70`
- `0x1800440d0`

## callees

- `0x180001c24`
- `0x180002a56`
- `0x180002aff`
- `0x18000d3dc`
- `0x180028154`
- `0x18006b444`
- `0x18006bad4`
- `0x18006bb54`
- `0x18006bc58`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18006bef4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006bffc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c053`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c097`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c0ab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c0b9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006bef4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006bffc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c053`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c097`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c0ab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18006c0b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c062`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c0c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c0ea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c062`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c0c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006c0ea`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18006bd04`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18006bdfb`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18006bd04`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18006bdfb`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18006c033`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18006c033`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18006bdce`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18006bdce`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bd4f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bd63`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bd4f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bd63`
- `ntdll!RtlAcquireSRWLockShared` at `0x18006bcd5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18006bcd5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006c0d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006c0f9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006c0d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006c0f9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006bd72`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006bd72`

## string_xrefs

- `0x18006be78`: `kernelbase.dll`
- `0x18006bc8f`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006bd34`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006be33`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006be48`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006bf2e`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006bf50`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006bf97`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006bfdf`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006c07b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18006be96`: `GetPersistedRegistryLocationW`

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
                                 (const unsigned __int16 *)a2,
                                 v4);
    if ( IsStateSeparationEnabled < 0 )
    {
      v5 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  RtlAcquireSRWLockShared(&qword_180096EF8);
  if ( Table )
  {
    Buffer = (unsigned __int64)Common::StateSeparation::AppModelRoot;
    v7 = RtlLookupElementGenericTableAvl(Table, &Buffer);
    v9 = v7 ? (Common *)v7[1] : 0LL;
    if ( v9 )
    {
      v10 = Common::CopyStringToOutput(v9, (const unsigned __int16 *)a2, v8);
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
      RtlReleaseSRWLockShared(&qword_180096EF8);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  RtlReleaseSRWLockShared(&qword_180096EF8);
  RtlAcquireSRWLockExclusive(&qword_180096EF8);
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
      v15 = Common::CopyStringToOutput(v14, (const unsigned __int16 *)a2, v13);
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
        RtlReleaseSRWLockExclusive(&qword_180096EF8);
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
  RtlReleaseSRWLockExclusive(&qword_180096EF8);
  IsStateSeparationEnabled = Common::CopyStringToOutput(
                               (Common *)L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
                               (const unsigned __int16 *)a2,
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
0x18006bc58  mov     [rsp-28h+arg_8], rbx
0x18006bc5d  mov     [rsp-28h+NewElement], rcx
0x18006bc62  push    rbp
0x18006bc63  push    rsi
0x18006bc64  push    rdi
0x18006bc65  push    r12
0x18006bc67  push    r14
0x18006bc69  mov     rbp, rsp
0x18006bc6c  sub     rsp, 60h
0x18006bc70  lea     rcx, [rbp+NewElement]; bool *
0x18006bc74  mov     byte ptr [rbp+NewElement], 0
0x18006bc78  mov     r14, rdx
0x18006bc7b  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18006bc80  mov     ebx, eax
0x18006bc82  test    eax, eax
0x18006bc84  jns     short loc_18006BCA5
0x18006bc86  mov     edx, 115h; void *
0x18006bc8b  mov     rcx, [rbp+28h]; this
0x18006bc8f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006bc96  mov     r9d, ebx; char *
0x18006bc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bc9e  mov     eax, ebx
0x18006bca0  jmp     loc_18006C126
0x18006bca5  cmp     byte ptr [rbp+NewElement], 0
0x18006bca9  jnz     short loc_18006BCCB
0x18006bcab  mov     rcx, cs:off_180072488; this
0x18006bcb2  mov     rdx, r14; unsigned __int16 *
0x18006bcb5  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18006bcba  mov     ebx, eax
0x18006bcbc  test    eax, eax
0x18006bcbe  jns     loc_18006C124
0x18006bcc4  mov     edx, 119h
0x18006bcc9  jmp     short loc_18006BC8B
0x18006bccb  lea     r12, qword_180096EF8
0x18006bcd2  mov     rcx, r12
0x18006bcd5  call    cs:__imp_RtlAcquireSRWLockShared
0x18006bcdc  nop     dword ptr [rax+rax+00h]
0x18006bce1  mov     rcx, cs:Table; Table
0x18006bce8  test    rcx, rcx
0x18006bceb  jz      short loc_18006BD60
0x18006bced  mov     rax, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x18006bcf4  lea     rdx, [rbp+Buffer]; Buffer
0x18006bcf8  mov     qword ptr [rbp+Buffer], rax
0x18006bcfc  mov     qword ptr [rbp+Buffer+8], 0
0x18006bd04  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18006bd0b  nop     dword ptr [rax+rax+00h]
0x18006bd10  test    rax, rax
0x18006bd13  jnz     short loc_18006BD19
0x18006bd15  xor     ecx, ecx
0x18006bd17  jmp     short loc_18006BD1D
0x18006bd19  mov     rcx, [rax+8]; this
0x18006bd1d  test    rcx, rcx
0x18006bd20  jz      short loc_18006BD60
0x18006bd22  mov     rdx, r14; unsigned __int16 *
0x18006bd25  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18006bd2a  mov     ebx, eax
0x18006bd2c  test    eax, eax
0x18006bd2e  jns     short loc_18006BD4A
0x18006bd30  mov     rcx, [rbp+28h]; this
0x18006bd34  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006bd3b  mov     r9d, eax; char *
0x18006bd3e  mov     edx, 122h; void *
0x18006bd43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bd48  jmp     short loc_18006BD4C
0x18006bd4a  xor     ebx, ebx
0x18006bd4c  mov     rcx, r12
0x18006bd4f  call    cs:__imp_RtlReleaseSRWLockShared
0x18006bd56  nop     dword ptr [rax+rax+00h]
0x18006bd5b  jmp     loc_18006BC9E
0x18006bd60  mov     rcx, r12
0x18006bd63  call    cs:__imp_RtlReleaseSRWLockShared
0x18006bd6a  nop     dword ptr [rax+rax+00h]
0x18006bd6f  mov     rcx, r12
0x18006bd72  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18006bd79  nop     dword ptr [rax+rax+00h]
0x18006bd7e  mov     rbx, cs:Table
0x18006bd85  test    rbx, rbx
0x18006bd88  jnz     short loc_18006BDE1
0x18006bd8a  lea     ecx, [rbx+78h]; Size
0x18006bd8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bd92  mov     rbx, rax
0x18006bd95  test    rax, rax
0x18006bd98  jz      loc_18006BE44
0x18006bd9e  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x18006bda5  mov     qword ptr [rsp+60h+TableContext], 0; int
0x18006bdae  lea     r9, ?GenericMapFree@?$GenericMap@PEAGPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18006bdb5  mov     [rbx+68h], rax
0x18006bdb9  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18006bdc0  mov     [rbx+70h], rax
0x18006bdc4  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18006bdcb  mov     rcx, rbx; Table
0x18006bdce  call    cs:__imp_RtlInitializeGenericTableAvl
0x18006bdd5  nop     dword ptr [rax+rax+00h]
0x18006bdda  mov     cs:Table, rbx
0x18006bde1  mov     rax, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x18006bde8  lea     rdx, [rbp+Buffer]; Buffer
0x18006bdec  mov     rcx, rbx; Table
0x18006bdef  mov     qword ptr [rbp+Buffer], rax
0x18006bdf3  mov     qword ptr [rbp+Buffer+8], 0
0x18006bdfb  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18006be02  nop     dword ptr [rax+rax+00h]
0x18006be07  test    rax, rax
0x18006be0a  jz      short loc_18006BE76
0x18006be0c  mov     rcx, [rax+8]; this
0x18006be10  test    rcx, rcx
0x18006be13  jz      short loc_18006BE76
0x18006be15  mov     rdx, r14; unsigned __int16 *
0x18006be18  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18006be1d  mov     esi, eax
0x18006be1f  test    eax, eax
0x18006be21  jns     loc_18006C06E
0x18006be27  mov     r9d, eax; char *
0x18006be2a  mov     edx, 131h; void *
0x18006be2f  mov     rcx, [rbp+28h]; this
0x18006be33  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006be3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be3f  jmp     loc_18006C0D4
0x18006be44  mov     rcx, [rbp+28h]; this
0x18006be48  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006be4f  mov     esi, 8007000Eh
0x18006be54  mov     cs:Table, 0
0x18006be5f  mov     r9d, esi; char *
0x18006be62  mov     edx, 3Bh ; ';'; void *
0x18006be67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006be6c  mov     r9d, esi
0x18006be6f  mov     edx, 129h
0x18006be74  jmp     short loc_18006BE2F
0x18006be76  xor     edx, edx; hFile
0x18006be78  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006be7f  mov     r8d, 800h; dwFlags
0x18006be85  call    LoadLibraryExW_0
0x18006be8a  mov     rbx, rax
0x18006be8d  test    rax, rax
0x18006be90  jz      loc_18006C0F6
0x18006be96  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x18006be9d  mov     rcx, rax; hModule
0x18006bea0  call    GetProcAddress_0
0x18006bea5  mov     rsi, rax
0x18006bea8  test    rax, rax
0x18006beab  jz      loc_18006C0E7
0x18006beb1  mov     rdx, cs:off_180072488; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006beb8  lea     rax, [rbp+Size]
0x18006bebc  mov     rcx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x18006bec3  xor     edi, edi
0x18006bec5  mov     qword ptr [rsp+60h+TableContext], rax; int
0x18006beca  xor     r9d, r9d
0x18006becd  mov     rax, rsi
0x18006bed0  mov     dword ptr [rbp+Size], edi
0x18006bed3  xor     r8d, r8d
0x18006bed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bedb  cmp     eax, 0EAh
0x18006bee0  jnz     short loc_18006BF26
0x18006bee2  mov     ecx, dword ptr [rbp+Size]; Size
0x18006bee5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006beea  mov     rdi, rax
0x18006beed  test    rax, rax
0x18006bef0  jz      short loc_18006BF4C
0x18006bef2  xor     ecx, ecx
0x18006bef4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006befb  nop     dword ptr [rax+rax+00h]
0x18006bf00  mov     r9d, dword ptr [rbp+Size]
0x18006bf04  lea     rax, [rbp+Size]
0x18006bf08  mov     rdx, cs:off_180072488; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006bf0f  mov     r8, rdi
0x18006bf12  mov     rcx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x18006bf19  mov     qword ptr [rsp+60h+TableContext], rax; int
0x18006bf1e  mov     rax, rsi
0x18006bf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf26  test    eax, eax
0x18006bf28  jz      short loc_18006BF6E
0x18006bf2a  mov     rcx, [rbp+28h]; this
0x18006bf2e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006bf35  mov     r9d, eax; char *
0x18006bf38  mov     edx, 153h; void *
0x18006bf3d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006bf42  mov     esi, eax
0x18006bf44  mov     rcx, rdi
0x18006bf47  jmp     loc_18006C0B9
0x18006bf4c  mov     rcx, [rbp+28h]; this
0x18006bf50  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006bf57  mov     esi, 8007000Eh
0x18006bf5c  mov     edx, 14Ah; void *
0x18006bf61  mov     r9d, esi; char *
0x18006bf64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bf69  jmp     loc_18006C0B7
0x18006bf6e  mov     [r14], rdi
0x18006bf71  lea     rcx, [rbp+Buffer]; this
0x18006bf75  mov     rdx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Src
0x18006bf7c  xor     eax, eax
0x18006bf7e  xorps   xmm0, xmm0
0x18006bf81  mov     [rbp+var_20], eax
0x18006bf84  movups  [rbp+Buffer], xmm0
0x18006bf88  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18006bf8d  mov     esi, eax
0x18006bf8f  test    eax, eax
0x18006bf91  jns     short loc_18006BFBD
0x18006bf93  mov     rcx, [rbp+28h]; this
0x18006bf97  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006bf9e  mov     r9d, eax; char *
0x18006bfa1  mov     edx, 158h; void *
0x18006bfa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bfab  mov     rcx, qword ptr [rbp+Buffer+8]
0x18006bfaf  test    rcx, rcx
0x18006bfb2  jz      loc_18006C0B7
0x18006bfb8  jmp     loc_18006C0AB
0x18006bfbd  mov     rdx, [r14]; Src
0x18006bfc0  lea     rcx, [rbp+var_18]; this
0x18006bfc4  xor     eax, eax
0x18006bfc6  xorps   xmm0, xmm0
0x18006bfc9  movups  [rbp+var_18], xmm0
0x18006bfcd  mov     [rbp+var_8], eax
0x18006bfd0  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18006bfd5  mov     esi, eax
0x18006bfd7  test    eax, eax
0x18006bfd9  jns     short loc_18006C00A
0x18006bfdb  mov     rcx, [rbp+28h]; this
0x18006bfdf  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006bfe6  mov     r9d, eax; char *
0x18006bfe9  mov     edx, 15Ah; void *
0x18006bfee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bff3  mov     rcx, qword ptr [rbp+var_18+8]
0x18006bff7  test    rcx, rcx
0x18006bffa  jz      short loc_18006BFAB
0x18006bffc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006c003  nop     dword ptr [rax+rax+00h]
0x18006c008  jmp     short loc_18006BFAB
0x18006c00a  mov     rdi, qword ptr [rbp+Buffer+8]
0x18006c00e  lea     r9, [rbp+NewElement]; NewElement
0x18006c012  mov     r14, qword ptr [rbp+var_18+8]
0x18006c016  lea     rdx, [rbp+Buffer]; Buffer
0x18006c01a  mov     rcx, cs:Table; Table
0x18006c021  mov     r8d, 10h; BufferSize
0x18006c027  mov     qword ptr [rbp+Buffer], rdi
0x18006c02b  mov     qword ptr [rbp+Buffer+8], r14
0x18006c02f  mov     byte ptr [rbp+NewElement], 0
0x18006c033  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18006c03a  nop     dword ptr [rax+rax+00h]
0x18006c03f  test    rax, rax
0x18006c042  jz      short loc_18006C072
0x18006c044  cmp     byte ptr [rbp+NewElement], 0
0x18006c048  jnz     short loc_18006C051
0x18006c04a  mov     esi, 800702BAh
0x18006c04f  jmp     short loc_18006C077
0x18006c051  xor     ecx, ecx
0x18006c053  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006c05a  nop     dword ptr [rax+rax+00h]
0x18006c05f  mov     rcx, rbx; hLibModule
0x18006c062  call    cs:__imp_FreeLibrary
0x18006c069  nop     dword ptr [rax+rax+00h]
0x18006c06e  xor     esi, esi
0x18006c070  jmp     short loc_18006C0D4
0x18006c072  mov     esi, 8007000Eh
0x18006c077  mov     rcx, [rbp+28h]; this
0x18006c07b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\common\\states"...
0x18006c082  mov     r9d, esi; char *
0x18006c085  mov     edx, 15Bh; void *
0x18006c08a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c08f  test    r14, r14
0x18006c092  jz      short loc_18006C0A3
0x18006c094  mov     rcx, r14
0x18006c097  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006c09e  nop     dword ptr [rax+rax+00h]
0x18006c0a3  test    rdi, rdi
0x18006c0a6  jz      short loc_18006C0B7
0x18006c0a8  mov     rcx, rdi
0x18006c0ab  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006c0b2  nop     dword ptr [rax+rax+00h]
0x18006c0b7  xor     ecx, ecx
0x18006c0b9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18006c0c0  nop     dword ptr [rax+rax+00h]
0x18006c0c5  mov     rcx, rbx; hLibModule
0x18006c0c8  call    cs:__imp_FreeLibrary
0x18006c0cf  nop     dword ptr [rax+rax+00h]
0x18006c0d4  mov     rcx, r12
0x18006c0d7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18006c0de  nop     dword ptr [rax+rax+00h]
0x18006c0e3  mov     eax, esi
0x18006c0e5  jmp     short loc_18006C126
0x18006c0e7  mov     rcx, rbx; hLibModule
0x18006c0ea  call    cs:__imp_FreeLibrary
0x18006c0f1  nop     dword ptr [rax+rax+00h]
0x18006c0f6  mov     rcx, r12
0x18006c0f9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18006c100  nop     dword ptr [rax+rax+00h]
0x18006c105  mov     rcx, cs:off_180072488; this
0x18006c10c  mov     rdx, r14; unsigned __int16 *
0x18006c10f  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18006c114  mov     ebx, eax
0x18006c116  test    eax, eax
0x18006c118  jns     short loc_18006C124
0x18006c11a  mov     edx, 165h
0x18006c11f  jmp     loc_18006BC8B
0x18006c124  xor     eax, eax
0x18006c126  mov     rbx, [rsp+60h+arg_8]
0x18006c12e  add     rsp, 60h
0x18006c132  pop     r14
0x18006c134  pop     r12
0x18006c136  pop     rdi
0x18006c137  pop     rsi
0x18006c138  pop     rbp
  ... truncated ...
```
