# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x1800b8ecc`
- end: `0x1800b92a9`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `989`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b92b0`

## callees

- `0x1800094e4`
- `0x1800099d4`
- `0x180009f34`
- `0x18000a2fa`
- `0x18000ad8c`
- `0x1800153f0`
- `0x18001ab9c`
- `0x18003970c`
- `0x1800b89b0`
- `0x1800b8c18`
- `0x1800b8c38`
- `0x1800b8c74`
- `0x1800b8d00`
- `0x1800b8de0`
- `0x1800b8ecc`
- `0x1800b968c`
- `0x1800b96bc`
- `0x1800b9d04`
- `0x1800c7010`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x1800b9008`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800b9008`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800b91ae`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800b91ae`

## string_xrefs

- `0x1800b905c`: `kernelbase.dll`
- `0x1800b8f10`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800b8f84`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800b903e`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800b9103`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800b9145`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800b9217`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800b9078`: `GetPersistedRegistryLocationW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(Common **a1, unsigned __int16 **a2)
{
  int IsStateSeparationEnabled; // ebx
  unsigned __int16 **v5; // r8
  __int64 v6; // rdx
  __int64 v8; // rcx
  Common *v9; // rax
  unsigned __int16 **v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  struct _RTL_AVL_TABLE *v13; // rbx
  Common *v14; // rax
  unsigned __int16 **v15; // r8
  int v16; // eax
  unsigned int v17; // esi
  HMODULE Library; // rax
  HMODULE v19; // rbx
  FARPROC GetPersistedRegistryLocationW; // rax
  __int64 (__fastcall *v21)(_QWORD, _QWORD, _QWORD, _QWORD); // r15
  unsigned __int16 *v22; // rdi
  unsigned int v23; // eax
  unsigned __int16 *v24; // rcx
  int v25; // eax
  int v26; // eax
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  unsigned __int16 **v29; // r8
  int TableContext; // [rsp+20h] [rbp-60h]
  _BYTE v31[8]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD Buffer[2]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v33; // [rsp+48h] [rbp-38h] BYREF
  int v34; // [rsp+58h] [rbp-28h]
  __int128 v35; // [rsp+60h] [rbp-20h] BYREF
  int v36; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  void *NewElement; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v39; // [rsp+C8h] [rbp+48h] BYREF

  LOBYTE(NewElement) = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&NewElement);
  if ( IsStateSeparationEnabled < 0 )
  {
    v6 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      TableContext);
    return (unsigned int)IsStateSeparationEnabled;
  }
  if ( !(_BYTE)NewElement )
  {
    IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (const unsigned __int16 *)a2, v5);
    if ( IsStateSeparationEnabled < 0 )
    {
      v6 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  wil::RtlAcquireSRWLockShared(&NewElement, &qword_1801691F8);
  if ( qword_1801691F0 )
  {
    v9 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(v8, *a1);
    if ( v9 )
    {
      v11 = Common::CopyStringToOutput(v9, (const unsigned __int16 *)a2, v10);
      IsStateSeparationEnabled = v11;
      if ( v11 >= 0 )
        IsStateSeparationEnabled = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v11,
          TableContext);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&NewElement);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&NewElement);
  wil::RtlAcquireSRWLockExclusive(v31, &qword_1801691F8);
  if ( !qword_1801691F0 )
  {
    v13 = (struct _RTL_AVL_TABLE *)operator new(0x78u);
    NewElement = v13;
    v13[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    v13[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    RtlInitializeGenericTableAvl(
      v13,
      Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapFree,
      0);
    qword_1801691F0 = v13;
  }
  v14 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(v12, *a1);
  if ( v14 )
  {
    v16 = Common::CopyStringToOutput(v14, (const unsigned __int16 *)a2, v15);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)v16,
        TableContext);
LABEL_38:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
      return v17;
    }
LABEL_32:
    v17 = 0;
    goto LABEL_38;
  }
  Library = LoadLibraryExW_0(L"kernelbase.dll", 0, 0x800u);
  v19 = Library;
  Buffer[0] = Library;
  if ( Library )
  {
    GetPersistedRegistryLocationW = GetProcAddress_0(Library, "GetPersistedRegistryLocationW");
    v21 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetPersistedRegistryLocationW;
    if ( GetPersistedRegistryLocationW )
    {
      v22 = 0;
      NewElement = 0;
      v39 = 0;
      v23 = ((__int64 (__fastcall *)(Common *, Common *, _QWORD, _QWORD))GetPersistedRegistryLocationW)(
              *a1,
              a1[1],
              0,
              0);
      if ( v23 == 234 )
      {
        v22 = (unsigned __int16 *)operator new[](v39);
        operator delete(0);
        NewElement = v22;
        v23 = v21(*a1, a1[1], v22, v39);
      }
      if ( v23 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v23,
                (unsigned int)&v39);
        v24 = v22;
      }
      else
      {
        *a2 = v22;
        v33 = 0;
        v34 = 0;
        v25 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v33, (const unsigned __int16 *)*a1);
        v17 = v25;
        if ( v25 >= 0 )
        {
          v35 = 0;
          v36 = 0;
          v26 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v35, *a2);
          v17 = v26;
          if ( v26 >= 0 )
          {
            Buffer[0] = *((_QWORD *)&v33 + 1);
            Buffer[1] = *((_QWORD *)&v35 + 1);
            LOBYTE(NewElement) = 0;
            if ( RtlInsertElementGenericTableAvl(qword_1801691F0, Buffer, 0x10u, (PBOOLEAN)&NewElement) )
            {
              v17 = (_BYTE)NewElement == 0 ? 0x800702BA : 0;
              if ( (_BYTE)NewElement )
              {
                *((_QWORD *)&v33 + 1) = 0;
                LODWORD(v33) = 0;
                v34 = 0;
                *((_QWORD *)&v35 + 1) = 0;
                LODWORD(v35) = 0;
                v36 = 0;
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v35);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v33);
                operator delete(0);
                FreeLibrary_0(v19);
                goto LABEL_32;
              }
            }
            else
            {
              v17 = -2147024882;
            }
            v27 = v17;
            v28 = 347;
          }
          else
          {
            v27 = (unsigned int)v26;
            v28 = 346;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)v27,
            (int)&v39);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v35);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)(unsigned int)v25,
            (int)&v39);
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v33);
        v24 = 0;
      }
      operator delete(v24);
      FreeLibrary_0(v19);
      goto LABEL_38;
    }
  }
  if ( v19 )
    FreeLibrary_0(v19);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
  IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (const unsigned __int16 *)a2, v29);
  if ( IsStateSeparationEnabled < 0 )
  {
    v6 = 357;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b8ecc  mov     [rsp-28h+arg_0], rbx
0x1800b8ed1  mov     [rsp-28h+arg_8], rsi
0x1800b8ed6  push    rbp
0x1800b8ed7  push    rdi
0x1800b8ed8  push    r12
0x1800b8eda  push    r14
0x1800b8edc  push    r15
0x1800b8ede  mov     rbp, rsp
0x1800b8ee1  sub     rsp, 80h
0x1800b8ee8  mov     r14, rdx
0x1800b8eeb  mov     rsi, rcx
0x1800b8eee  xor     r12d, r12d
0x1800b8ef1  mov     byte ptr [rbp+NewElement], r12b
0x1800b8ef5  lea     rcx, [rbp+NewElement]; bool *
0x1800b8ef9  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1800b8efe  mov     ebx, eax
0x1800b8f00  test    eax, eax
0x1800b8f02  jns     short loc_1800B8F23
0x1800b8f04  mov     edx, 115h; void *
0x1800b8f09  mov     rcx, [rbp+28h]; this
0x1800b8f0d  mov     r9d, ebx; char *
0x1800b8f10  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1800b8f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8f1c  mov     eax, ebx
0x1800b8f1e  jmp     loc_1800B928D
0x1800b8f23  cmp     byte ptr [rbp+NewElement], r12b
0x1800b8f27  jnz     short loc_1800B8F46
0x1800b8f29  mov     rdx, r14; unsigned __int16 *
0x1800b8f2c  mov     rcx, [rsi+8]; this
0x1800b8f30  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800b8f35  mov     ebx, eax
0x1800b8f37  test    eax, eax
0x1800b8f39  jns     loc_1800B928B
0x1800b8f3f  mov     edx, 119h
0x1800b8f44  jmp     short loc_1800B8F09
0x1800b8f46  lea     rdx, qword_1801691F8
0x1800b8f4d  lea     rcx, [rbp+NewElement]
0x1800b8f51  call    ?RtlAcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockShared(_RTL_SRWLOCK *)
0x1800b8f56  cmp     cs:qword_1801691F0, r12
0x1800b8f5d  jz      short loc_1800B8FA8
0x1800b8f5f  mov     rdx, [rsi]
0x1800b8f62  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x1800b8f67  test    rax, rax
0x1800b8f6a  jz      short loc_1800B8FA8
0x1800b8f6c  mov     rdx, r14; unsigned __int16 *
0x1800b8f6f  mov     rcx, rax; this
0x1800b8f72  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800b8f77  mov     ebx, eax
0x1800b8f79  test    eax, eax
0x1800b8f7b  jns     short loc_1800B8F97
0x1800b8f7d  mov     rcx, [rbp+28h]; this
0x1800b8f81  mov     r9d, eax; char *
0x1800b8f84  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1800b8f8b  mov     edx, 122h; void *
0x1800b8f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8f95  jmp     short loc_1800B8F9A
0x1800b8f97  mov     ebx, r12d
0x1800b8f9a  lea     rcx, [rbp+NewElement]
0x1800b8f9e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800b8fa3  jmp     loc_1800B8F1C
0x1800b8fa8  lea     rcx, [rbp+NewElement]
0x1800b8fac  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800b8fb1  lea     rdx, qword_1801691F8
0x1800b8fb8  lea     rcx, [rbp+var_50]
0x1800b8fbc  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800b8fc1  nop
0x1800b8fc2  cmp     cs:qword_1801691F0, r12
0x1800b8fc9  jnz     short loc_1800B9015
0x1800b8fcb  mov     ecx, 78h ; 'x'; Size
0x1800b8fd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b8fd5  mov     rbx, rax
0x1800b8fd8  mov     [rbp+NewElement], rax
0x1800b8fdc  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x1800b8fe3  mov     [rbx+68h], rax
0x1800b8fe7  mov     [rbx+70h], rax
0x1800b8feb  mov     qword ptr [rsp+80h+TableContext], r12; int
0x1800b8ff0  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEBG@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800b8ff7  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800b8ffe  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800b9005  mov     rcx, rbx; Table
0x1800b9008  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800b900e  mov     cs:qword_1801691F0, rbx
0x1800b9015  mov     rdx, [rsi]
0x1800b9018  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x1800b901d  test    rax, rax
0x1800b9020  jz      short loc_1800B9054
0x1800b9022  mov     rdx, r14; unsigned __int16 *
0x1800b9025  mov     rcx, rax; this
0x1800b9028  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800b902d  mov     esi, eax
0x1800b902f  test    eax, eax
0x1800b9031  jns     loc_1800B9205
0x1800b9037  mov     rcx, [rbp+28h]; this
0x1800b903b  mov     r9d, eax; char *
0x1800b903e  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1800b9045  mov     edx, 131h; void *
0x1800b904a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b904f  jmp     loc_1800B924B
0x1800b9054  xor     edx, edx; hFile
0x1800b9056  mov     r8d, 800h; dwFlags
0x1800b905c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800b9063  call    LoadLibraryExW_0
0x1800b9068  mov     rbx, rax
0x1800b906b  mov     [rbp+Buffer], rax
0x1800b906f  test    rax, rax
0x1800b9072  jz      loc_1800B9258
0x1800b9078  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x1800b907f  mov     rcx, rax; hModule
0x1800b9082  call    GetProcAddress_0
0x1800b9087  mov     r15, rax
0x1800b908a  test    rax, rax
0x1800b908d  jz      loc_1800B9258
0x1800b9093  mov     rdi, r12
0x1800b9096  mov     [rbp+NewElement], r12
0x1800b909a  mov     [rbp+arg_18], r12d
0x1800b909e  lea     rax, [rbp+arg_18]
0x1800b90a2  mov     qword ptr [rsp+80h+TableContext], rax
0x1800b90a7  xor     r9d, r9d
0x1800b90aa  xor     r8d, r8d
0x1800b90ad  mov     rdx, [rsi+8]
0x1800b90b1  mov     rcx, [rsi]
0x1800b90b4  mov     rax, r15
0x1800b90b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b90bc  cmp     eax, 0EAh
0x1800b90c1  jnz     short loc_1800B90F8
0x1800b90c3  mov     ecx, [rbp+arg_18]; unsigned __int64
0x1800b90c6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b90cb  mov     rdi, rax
0x1800b90ce  xor     ecx, ecx; Block
0x1800b90d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b90d5  mov     [rbp+NewElement], rdi
0x1800b90d9  lea     rax, [rbp+arg_18]
0x1800b90dd  mov     qword ptr [rsp+80h+TableContext], rax; int
0x1800b90e2  mov     r9d, [rbp+arg_18]
0x1800b90e6  mov     r8, rdi
0x1800b90e9  mov     rdx, [rsi+8]
0x1800b90ed  mov     rcx, [rsi]
0x1800b90f0  mov     rax, r15
0x1800b90f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b90f8  test    eax, eax
0x1800b90fa  jz      short loc_1800B911E
0x1800b90fc  mov     rcx, [rbp+28h]; this
0x1800b9100  mov     r9d, eax; char *
0x1800b9103  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1800b910a  mov     edx, 153h; void *
0x1800b910f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b9114  mov     esi, eax
0x1800b9116  mov     rcx, rdi
0x1800b9119  jmp     loc_1800B923C
0x1800b911e  mov     [r14], rdi
0x1800b9121  xorps   xmm0, xmm0
0x1800b9124  movups  [rbp+var_38], xmm0
0x1800b9128  mov     [rbp+var_28], r12d
0x1800b912c  mov     rdx, [rsi]; unsigned __int16 *
0x1800b912f  lea     rcx, [rbp+var_38]; this
0x1800b9133  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800b9138  mov     esi, eax
0x1800b913a  test    eax, eax
0x1800b913c  jns     short loc_1800B915B
0x1800b913e  mov     rcx, [rbp+28h]; this
0x1800b9142  mov     r9d, eax; char *
0x1800b9145  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1800b914c  mov     edx, 158h; void *
0x1800b9151  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b9156  jmp     loc_1800B9230
0x1800b915b  xorps   xmm0, xmm0
0x1800b915e  movups  [rbp+var_20], xmm0
0x1800b9162  mov     [rbp+var_10], r12d
0x1800b9166  mov     rdx, [r14]; unsigned __int16 *
0x1800b9169  lea     rcx, [rbp+var_20]; this
0x1800b916d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800b9172  mov     esi, eax
0x1800b9174  test    eax, eax
0x1800b9176  jns     short loc_1800B9185
0x1800b9178  mov     r9d, eax
0x1800b917b  mov     edx, 15Ah
0x1800b9180  jmp     loc_1800B9217
0x1800b9185  mov     rax, qword ptr [rbp+var_38+8]
0x1800b9189  mov     [rbp+Buffer], rax
0x1800b918d  mov     rax, qword ptr [rbp+var_20+8]
0x1800b9191  mov     [rbp+var_40], rax
0x1800b9195  mov     byte ptr [rbp+NewElement], r12b
0x1800b9199  lea     r9, [rbp+NewElement]; NewElement
0x1800b919d  mov     r8d, 10h; BufferSize
0x1800b91a3  lea     rdx, [rbp+Buffer]; Buffer
0x1800b91a7  mov     rcx, cs:qword_1801691F0; Table
0x1800b91ae  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800b91b4  test    rax, rax
0x1800b91b7  jz      short loc_1800B920A
0x1800b91b9  mov     al, byte ptr [rbp+NewElement]
0x1800b91bc  neg     al
0x1800b91be  sbb     esi, esi
0x1800b91c0  not     esi
0x1800b91c2  and     esi, 800702BAh
0x1800b91c8  jl      short loc_1800B920F
0x1800b91ca  mov     qword ptr [rbp+var_38+8], r12
0x1800b91ce  mov     dword ptr [rbp+var_38], r12d
0x1800b91d2  mov     [rbp+var_28], r12d
0x1800b91d6  mov     qword ptr [rbp+var_20+8], r12
0x1800b91da  mov     dword ptr [rbp+var_20], r12d
0x1800b91de  mov     [rbp+var_10], r12d
0x1800b91e2  lea     rcx, [rbp+var_20]; this
0x1800b91e6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800b91eb  lea     rcx, [rbp+var_38]; this
0x1800b91ef  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800b91f4  nop
0x1800b91f5  xor     ecx, ecx; Block
0x1800b91f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b91fc  nop
0x1800b91fd  mov     rcx, rbx; hLibModule
0x1800b9200  call    FreeLibrary_0
0x1800b9205  mov     esi, r12d
0x1800b9208  jmp     short loc_1800B924B
0x1800b920a  mov     esi, 8007000Eh
0x1800b920f  mov     r9d, esi; char *
0x1800b9212  mov     edx, 15Bh; void *
0x1800b9217  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1800b921e  mov     rcx, [rbp+28h]; this
0x1800b9222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b9227  lea     rcx, [rbp+var_20]; this
0x1800b922b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800b9230  lea     rcx, [rbp+var_38]; this
0x1800b9234  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800b9239  nop
0x1800b923a  xor     ecx, ecx; Block
0x1800b923c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b9241  nop
0x1800b9242  mov     rcx, rbx; hLibModule
0x1800b9245  call    FreeLibrary_0
0x1800b924a  nop
0x1800b924b  lea     rcx, [rbp+var_50]
0x1800b924f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800b9254  mov     eax, esi
0x1800b9256  jmp     short loc_1800B928D
0x1800b9258  test    rbx, rbx
0x1800b925b  jz      short loc_1800B9266
0x1800b925d  mov     rcx, rbx; hLibModule
0x1800b9260  call    FreeLibrary_0
0x1800b9265  nop
0x1800b9266  lea     rcx, [rbp+var_50]
0x1800b926a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800b926f  mov     rdx, r14; unsigned __int16 *
0x1800b9272  mov     rcx, [rsi+8]; this
0x1800b9276  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x1800b927b  mov     ebx, eax
0x1800b927d  test    eax, eax
0x1800b927f  jns     short loc_1800B928B
0x1800b9281  mov     edx, 165h
0x1800b9286  jmp     loc_1800B8F09
0x1800b928b  xor     eax, eax
0x1800b928d  lea     r11, [rsp+80h+var_s0]
0x1800b9295  mov     rbx, [r11+30h]
0x1800b9299  mov     rsi, [r11+38h]
0x1800b929d  mov     rsp, r11
0x1800b92a0  pop     r15
0x1800b92a2  pop     r14
0x1800b92a4  pop     r12
0x1800b92a6  pop     rdi
0x1800b92a7  pop     rbp
0x1800b92a8  retn
```
