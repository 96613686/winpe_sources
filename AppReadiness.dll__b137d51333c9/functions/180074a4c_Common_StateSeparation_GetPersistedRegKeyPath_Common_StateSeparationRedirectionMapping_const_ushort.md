# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x180074a4c`
- end: `0x180074e56`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `1034`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d8b8`

## callees

- `0x180030914`
- `0x180030d58`
- `0x18003a2b0`
- `0x18003e234`
- `0x18003eaac`
- `0x18003eab8`
- `0x18003f213`
- `0x18003f2da`
- `0x18003f2e6`
- `0x18004c1a8`
- `0x180074798`
- `0x1800747b8`
- `0x1800747f4`
- `0x180074880`
- `0x180074960`
- `0x180074a4c`
- `0x180074e5c`
- `0x180074e8c`
- `0x180079010`

## import_xrefs

- `ntdll!RtlInsertElementGenericTableAvl` at `0x180074d60`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180074d60`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180074b88`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180074b88`

## string_xrefs

- `0x180074be0`: `kernelbase.dll`
- `0x180074bfc`: `GetPersistedRegistryLocationW`
- `0x180074a89`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180074b04`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180074bc2`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180074c95`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180074cdb`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180074dc9`: `onecore\base\appmodel\common\stateseparation.cpp`

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
  __int64 v7; // rcx
  Common *v8; // rax
  unsigned __int16 **v9; // r8
  int v10; // eax
  __int64 v11; // rcx
  struct _RTL_AVL_TABLE *v12; // rbx
  Common *v13; // rax
  unsigned __int16 **v14; // r8
  int v15; // eax
  unsigned int v16; // esi
  HMODULE Library; // rax
  HMODULE v18; // rbx
  FARPROC GetPersistedRegistryLocationW; // rax
  __int64 (__fastcall *v20)(_QWORD, _QWORD, _QWORD, _QWORD); // r14
  unsigned __int16 *v21; // rdi
  unsigned int v22; // eax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // rcx
  int v26; // eax
  unsigned int v27; // edi
  unsigned __int64 v28; // rdx
  int v29; // eax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  unsigned __int64 v32; // rdx
  unsigned __int16 **v33; // r8
  int TableContext; // [rsp+20h] [rbp-50h]
  _QWORD Buffer[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v36; // [rsp+40h] [rbp-30h] BYREF
  int v37; // [rsp+50h] [rbp-20h]
  __int128 v38; // [rsp+58h] [rbp-18h] BYREF
  int v39; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  const struct Common::StateSeparationRedirectionMapping *NewElement; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v42; // [rsp+B0h] [rbp+40h] BYREF
  char v43; // [rsp+B8h] [rbp+48h] BYREF

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
  wil::RtlAcquireSRWLockShared(&NewElement, &qword_1800A4A90);
  if ( qword_1800A4A88 )
  {
    v8 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(
                     v7,
                     Common::StateSeparation::AppModelRoot);
    if ( v8 )
    {
      v10 = Common::CopyStringToOutput(v8, (const unsigned __int16 *)a2, v9);
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
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&NewElement);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&NewElement);
  wil::RtlAcquireSRWLockExclusive(&v43, &qword_1800A4A90);
  if ( !qword_1800A4A88 )
  {
    v12 = (struct _RTL_AVL_TABLE *)operator new(0x78u);
    NewElement = (const struct Common::StateSeparationRedirectionMapping *)v12;
    v12[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    v12[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    RtlInitializeGenericTableAvl(
      v12,
      Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapFree,
      0);
    qword_1800A4A88 = v12;
  }
  v13 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(
                    v11,
                    Common::StateSeparation::AppModelRoot);
  if ( v13 )
  {
    v15 = Common::CopyStringToOutput(v13, (const unsigned __int16 *)a2, v14);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)v15,
        TableContext);
LABEL_37:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
      return v16;
    }
LABEL_32:
    v16 = 0;
    goto LABEL_37;
  }
  Library = LoadLibraryExW_0(L"kernelbase.dll", 0, 0x800u);
  v18 = Library;
  Buffer[0] = Library;
  if ( Library )
  {
    GetPersistedRegistryLocationW = GetProcAddress_0(Library, "GetPersistedRegistryLocationW");
    v20 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetPersistedRegistryLocationW;
    if ( GetPersistedRegistryLocationW )
    {
      v21 = 0;
      NewElement = 0;
      v42 = 0;
      v22 = ((__int64 (__fastcall *)(unsigned __int16 *const, const wchar_t *, _QWORD, _QWORD))GetPersistedRegistryLocationW)(
              Common::StateSeparation::AppModelRoot,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
              0,
              0);
      if ( v22 == 234 )
      {
        v21 = (unsigned __int16 *)operator new[](v42);
        operator delete(0, v23);
        NewElement = (const struct Common::StateSeparationRedirectionMapping *)v21;
        v22 = v20(
                Common::StateSeparation::AppModelRoot,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
                v21,
                v42);
      }
      if ( v22 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v22,
                (unsigned int)&v42);
        v25 = v21;
      }
      else
      {
        *a2 = v21;
        v36 = 0;
        v37 = 0;
        v26 = Common::StringBuffer::SetValueFromString(
                (Common::StringBuffer *)&v36,
                Common::StateSeparation::AppModelRoot);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)(unsigned int)v26,
            (int)&v42);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
          operator delete(0, v28);
          FreeLibrary_0(v18);
          v16 = v27;
          goto LABEL_37;
        }
        v38 = 0;
        v39 = 0;
        v29 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v38, *a2);
        v16 = v29;
        if ( v29 >= 0 )
        {
          Buffer[0] = *((_QWORD *)&v36 + 1);
          Buffer[1] = *((_QWORD *)&v38 + 1);
          LOBYTE(NewElement) = 0;
          if ( RtlInsertElementGenericTableAvl(qword_1800A4A88, Buffer, 0x10u, (PBOOLEAN)&NewElement) )
          {
            v16 = (_BYTE)NewElement == 0 ? 0x800702BA : 0;
            if ( (_BYTE)NewElement )
            {
              *((_QWORD *)&v36 + 1) = 0;
              LODWORD(v36) = 0;
              v37 = 0;
              *((_QWORD *)&v38 + 1) = 0;
              LODWORD(v38) = 0;
              v39 = 0;
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v38);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
              operator delete(0, v32);
              FreeLibrary_0(v18);
              goto LABEL_32;
            }
          }
          else
          {
            v16 = -2147024882;
          }
          v30 = v16;
          v31 = 347;
        }
        else
        {
          v30 = (unsigned int)v29;
          v31 = 346;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)v30,
          (int)&v42);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v38);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
        v25 = 0;
      }
      operator delete(v25, v24);
      FreeLibrary_0(v18);
      goto LABEL_37;
    }
  }
  if ( v18 )
    FreeLibrary_0(v18);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
  IsStateSeparationEnabled = Common::CopyStringToOutput(
                               (Common *)L"Software\\Microsoft\\Windows\\CurrentVersion\\AppModel",
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
0x180074a4c  mov     [rsp-28h+arg_8], rbx
0x180074a51  mov     [rsp-28h+NewElement], rcx
0x180074a56  push    rbp
0x180074a57  push    rsi
0x180074a58  push    rdi
0x180074a59  push    r14
0x180074a5b  push    r15
0x180074a5d  mov     rbp, rsp
0x180074a60  sub     rsp, 70h
0x180074a64  mov     rsi, rdx
0x180074a67  xor     r15d, r15d
0x180074a6a  mov     byte ptr [rbp+NewElement], r15b
0x180074a6e  lea     rcx, [rbp+NewElement]; bool *
0x180074a72  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180074a77  mov     ebx, eax
0x180074a79  test    eax, eax
0x180074a7b  jns     short loc_180074A9C
0x180074a7d  mov     edx, 115h; void *
0x180074a82  mov     rcx, [rbp+28h]; this
0x180074a86  mov     r9d, ebx; char *
0x180074a89  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180074a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074a95  mov     eax, ebx
0x180074a97  jmp     loc_180074E42
0x180074a9c  cmp     byte ptr [rbp+NewElement], r15b
0x180074aa0  jnz     short loc_180074AC2
0x180074aa2  mov     rdx, rsi; unsigned __int16 *
0x180074aa5  mov     rcx, cs:off_18007F968; this
0x180074aac  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180074ab1  mov     ebx, eax
0x180074ab3  test    eax, eax
0x180074ab5  jns     loc_180074E40
0x180074abb  mov     edx, 119h
0x180074ac0  jmp     short loc_180074A82
0x180074ac2  lea     rdx, qword_1800A4A90
0x180074ac9  lea     rcx, [rbp+NewElement]
0x180074acd  call    ?RtlAcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockShared(_RTL_SRWLOCK *)
0x180074ad2  cmp     cs:qword_1800A4A88, r15
0x180074ad9  jz      short loc_180074B28
0x180074adb  mov     rdx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x180074ae2  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x180074ae7  test    rax, rax
0x180074aea  jz      short loc_180074B28
0x180074aec  mov     rdx, rsi; unsigned __int16 *
0x180074aef  mov     rcx, rax; this
0x180074af2  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180074af7  mov     ebx, eax
0x180074af9  test    eax, eax
0x180074afb  jns     short loc_180074B17
0x180074afd  mov     rcx, [rbp+28h]; this
0x180074b01  mov     r9d, eax; char *
0x180074b04  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180074b0b  mov     edx, 122h; void *
0x180074b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074b15  jmp     short loc_180074B1A
0x180074b17  mov     ebx, r15d
0x180074b1a  lea     rcx, [rbp+NewElement]
0x180074b1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180074b23  jmp     loc_180074A95
0x180074b28  lea     rcx, [rbp+NewElement]
0x180074b2c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180074b31  lea     rdx, qword_1800A4A90
0x180074b38  lea     rcx, [rbp+arg_18]
0x180074b3c  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180074b41  nop
0x180074b42  cmp     cs:qword_1800A4A88, r15
0x180074b49  jnz     short loc_180074B95
0x180074b4b  mov     ecx, 78h ; 'x'; Size
0x180074b50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074b55  mov     rbx, rax
0x180074b58  mov     [rbp+NewElement], rax
0x180074b5c  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x180074b63  mov     [rbx+68h], rax
0x180074b67  mov     [rbx+70h], rax
0x180074b6b  mov     qword ptr [rsp+70h+TableContext], r15; int
0x180074b70  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEBG@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180074b77  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180074b7e  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180074b85  mov     rcx, rbx; Table
0x180074b88  call    cs:__imp_RtlInitializeGenericTableAvl
0x180074b8e  mov     cs:qword_1800A4A88, rbx
0x180074b95  mov     rdx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x180074b9c  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x180074ba1  test    rax, rax
0x180074ba4  jz      short loc_180074BD8
0x180074ba6  mov     rdx, rsi; unsigned __int16 *
0x180074ba9  mov     rcx, rax; this
0x180074bac  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180074bb1  mov     esi, eax
0x180074bb3  test    eax, eax
0x180074bb5  jns     loc_180074DB7
0x180074bbb  mov     rcx, [rbp+28h]; this
0x180074bbf  mov     r9d, eax; char *
0x180074bc2  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180074bc9  mov     edx, 131h; void *
0x180074bce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074bd3  jmp     loc_180074DFD
0x180074bd8  xor     edx, edx; hFile
0x180074bda  mov     r8d, 800h; dwFlags
0x180074be0  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180074be7  call    LoadLibraryExW_0
0x180074bec  mov     rbx, rax
0x180074bef  mov     [rbp+Buffer], rax
0x180074bf3  test    rax, rax
0x180074bf6  jz      loc_180074E0A
0x180074bfc  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x180074c03  mov     rcx, rax; hModule
0x180074c06  call    GetProcAddress_0
0x180074c0b  mov     r14, rax
0x180074c0e  test    rax, rax
0x180074c11  jz      loc_180074E0A
0x180074c17  mov     rdi, r15
0x180074c1a  mov     [rbp+NewElement], r15
0x180074c1e  mov     [rbp+arg_10], r15d
0x180074c22  lea     rax, [rbp+arg_10]
0x180074c26  mov     qword ptr [rsp+70h+TableContext], rax
0x180074c2b  xor     r9d, r9d
0x180074c2e  xor     r8d, r8d
0x180074c31  mov     rdx, cs:off_18007F968; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180074c38  mov     rcx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x180074c3f  mov     rax, r14
0x180074c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c47  cmp     eax, 0EAh
0x180074c4c  jnz     short loc_180074C8A
0x180074c4e  mov     ecx, [rbp+arg_10]; unsigned __int64
0x180074c51  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180074c56  mov     rdi, rax
0x180074c59  xor     ecx, ecx; void *
0x180074c5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180074c60  mov     [rbp+NewElement], rdi
0x180074c64  lea     rax, [rbp+arg_10]
0x180074c68  mov     qword ptr [rsp+70h+TableContext], rax; int
0x180074c6d  mov     r9d, [rbp+arg_10]
0x180074c71  mov     r8, rdi
0x180074c74  mov     rdx, cs:off_18007F968; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180074c7b  mov     rcx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AppModelRoot
0x180074c82  mov     rax, r14
0x180074c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c8a  test    eax, eax
0x180074c8c  jz      short loc_180074CB0
0x180074c8e  mov     rcx, [rbp+28h]; this
0x180074c92  mov     r9d, eax; char *
0x180074c95  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180074c9c  mov     edx, 153h; void *
0x180074ca1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180074ca6  mov     esi, eax
0x180074ca8  mov     rcx, rdi
0x180074cab  jmp     loc_180074DEE
0x180074cb0  mov     [rsi], rdi
0x180074cb3  xorps   xmm0, xmm0
0x180074cb6  movups  [rbp+var_30], xmm0
0x180074cba  mov     [rbp+var_20], r15d
0x180074cbe  mov     rdx, cs:?AppModelRoot@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; unsigned __int16 *
0x180074cc5  lea     rcx, [rbp+var_30]; this
0x180074cc9  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180074cce  mov     edi, eax
0x180074cd0  test    eax, eax
0x180074cd2  jns     short loc_180074D0D
0x180074cd4  mov     rcx, [rbp+28h]; this
0x180074cd8  mov     r9d, eax; char *
0x180074cdb  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180074ce2  mov     edx, 158h; void *
0x180074ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074cec  lea     rcx, [rbp+var_30]; this
0x180074cf0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180074cf5  nop
0x180074cf6  xor     ecx, ecx; void *
0x180074cf8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180074cfd  nop
0x180074cfe  mov     rcx, rbx; hLibModule
0x180074d01  call    FreeLibrary_0
0x180074d06  mov     esi, edi
0x180074d08  jmp     loc_180074DFD
0x180074d0d  xorps   xmm0, xmm0
0x180074d10  movups  [rbp+var_18], xmm0
0x180074d14  mov     [rbp+var_8], r15d
0x180074d18  mov     rdx, [rsi]; unsigned __int16 *
0x180074d1b  lea     rcx, [rbp+var_18]; this
0x180074d1f  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180074d24  mov     esi, eax
0x180074d26  test    eax, eax
0x180074d28  jns     short loc_180074D37
0x180074d2a  mov     r9d, eax
0x180074d2d  mov     edx, 15Ah
0x180074d32  jmp     loc_180074DC9
0x180074d37  mov     rax, qword ptr [rbp+var_30+8]
0x180074d3b  mov     [rbp+Buffer], rax
0x180074d3f  mov     rax, qword ptr [rbp+var_18+8]
0x180074d43  mov     [rbp+var_38], rax
0x180074d47  mov     byte ptr [rbp+NewElement], r15b
0x180074d4b  lea     r9, [rbp+NewElement]; NewElement
0x180074d4f  mov     r8d, 10h; BufferSize
0x180074d55  lea     rdx, [rbp+Buffer]; Buffer
0x180074d59  mov     rcx, cs:qword_1800A4A88; Table
0x180074d60  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180074d66  test    rax, rax
0x180074d69  jz      short loc_180074DBC
0x180074d6b  mov     al, byte ptr [rbp+NewElement]
0x180074d6e  neg     al
0x180074d70  sbb     esi, esi
0x180074d72  not     esi
0x180074d74  and     esi, 800702BAh
0x180074d7a  jl      short loc_180074DC1
0x180074d7c  mov     qword ptr [rbp+var_30+8], r15
0x180074d80  mov     dword ptr [rbp+var_30], r15d
0x180074d84  mov     [rbp+var_20], r15d
0x180074d88  mov     qword ptr [rbp+var_18+8], r15
0x180074d8c  mov     dword ptr [rbp+var_18], r15d
0x180074d90  mov     [rbp+var_8], r15d
0x180074d94  lea     rcx, [rbp+var_18]; this
0x180074d98  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180074d9d  lea     rcx, [rbp+var_30]; this
0x180074da1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180074da6  nop
0x180074da7  xor     ecx, ecx; void *
0x180074da9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180074dae  nop
0x180074daf  mov     rcx, rbx; hLibModule
0x180074db2  call    FreeLibrary_0
0x180074db7  mov     esi, r15d
0x180074dba  jmp     short loc_180074DFD
0x180074dbc  mov     esi, 8007000Eh
0x180074dc1  mov     r9d, esi; char *
0x180074dc4  mov     edx, 15Bh; void *
0x180074dc9  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180074dd0  mov     rcx, [rbp+28h]; this
0x180074dd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074dd9  lea     rcx, [rbp+var_18]; this
0x180074ddd  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180074de2  lea     rcx, [rbp+var_30]; this
0x180074de6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180074deb  nop
0x180074dec  xor     ecx, ecx; void *
0x180074dee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180074df3  nop
0x180074df4  mov     rcx, rbx; hLibModule
0x180074df7  call    FreeLibrary_0
0x180074dfc  nop
0x180074dfd  lea     rcx, [rbp+arg_18]
0x180074e01  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180074e06  mov     eax, esi
0x180074e08  jmp     short loc_180074E42
0x180074e0a  test    rbx, rbx
0x180074e0d  jz      short loc_180074E18
0x180074e0f  mov     rcx, rbx; hLibModule
0x180074e12  call    FreeLibrary_0
0x180074e17  nop
0x180074e18  lea     rcx, [rbp+arg_18]
0x180074e1c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180074e21  mov     rdx, rsi; unsigned __int16 *
0x180074e24  mov     rcx, cs:off_18007F968; this
0x180074e2b  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180074e30  mov     ebx, eax
0x180074e32  test    eax, eax
0x180074e34  jns     short loc_180074E40
0x180074e36  mov     edx, 165h
0x180074e3b  jmp     loc_180074A82
0x180074e40  xor     eax, eax
0x180074e42  mov     rbx, [rsp+70h+arg_8]
0x180074e4a  add     rsp, 70h
0x180074e4e  pop     r15
0x180074e50  pop     r14
0x180074e52  pop     rdi
0x180074e53  pop     rsi
0x180074e54  pop     rbp
0x180074e55  retn
```
