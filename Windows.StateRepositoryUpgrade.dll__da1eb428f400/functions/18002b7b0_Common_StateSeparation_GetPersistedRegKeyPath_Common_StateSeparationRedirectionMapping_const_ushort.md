# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x18002b7b0`
- end: `0x18002bb72`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `962`
- prototype: `__int64 __fastcall(Common **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e620`
- `0x18002bb78`

## callees

- `0x180003d50`
- `0x1800043b4`
- `0x180007f7c`
- `0x18000a3c0`
- `0x18000f62c`
- `0x180017670`
- `0x18002b474`
- `0x18002b4ac`
- `0x18002b4cc`
- `0x18002b57c`
- `0x18002b608`
- `0x18002b6d0`
- `0x18002b7b0`
- `0x18002bfb0`
- `0x18002bfe0`
- `0x18002d2dc`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b942`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b942`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002b8e7`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18002b8e7`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18002ba82`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18002ba82`

## string_xrefs

- `0x18002b935`: `kernelbase.dll`
- `0x18002b7f1`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002b865`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002b91a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002b9d4`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002ba16`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002baed`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18002b954`: `GetPersistedRegistryLocationW`

## pseudocode

```c
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
  Common *v22; // rdx
  Common *v23; // rcx
  unsigned __int16 *v24; // rdi
  unsigned int v25; // eax
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  Common *v29; // rdx
  int v30; // eax
  const unsigned __int16 *v31; // rdx
  int v32; // eax
  unsigned __int64 v33; // r9
  __int64 v34; // rdx
  unsigned __int64 v35; // rdx
  unsigned __int16 **v36; // r8
  int TableContext; // [rsp+20h] [rbp-60h]
  _BYTE v38[8]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD Buffer[2]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v40; // [rsp+48h] [rbp-38h] BYREF
  int v41; // [rsp+58h] [rbp-28h]
  __int128 v42; // [rsp+60h] [rbp-20h] BYREF
  int v43; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  unsigned __int8 NewElement; // [rsp+C0h] [rbp+40h] BYREF
  size_t Size; // [rsp+C8h] [rbp+48h] BYREF

  NewElement = 0;
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
  if ( !NewElement )
  {
    IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (const unsigned __int16 *)a2, v5);
    if ( IsStateSeparationEnabled < 0 )
    {
      v6 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  wil::RtlAcquireSRWLockShared(&NewElement, &qword_18004C0F8);
  if ( Block )
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
  wil::RtlAcquireSRWLockExclusive(v38, &qword_18004C0F8);
  if ( !Block )
  {
    v13 = (struct _RTL_AVL_TABLE *)operator new(0x78u);
    v13[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    v13[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    RtlInitializeGenericTableAvl(
      v13,
      Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapFree,
      0);
    Block = v13;
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
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v38);
      return v17;
    }
LABEL_32:
    v17 = 0;
    goto LABEL_38;
  }
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v19 = Library;
  if ( Library )
  {
    GetPersistedRegistryLocationW = GetProcAddress_0(Library, "GetPersistedRegistryLocationW");
    v21 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetPersistedRegistryLocationW;
    if ( GetPersistedRegistryLocationW )
    {
      v22 = a1[1];
      v23 = *a1;
      LODWORD(Size) = 0;
      v24 = 0;
      v25 = ((__int64 (__fastcall *)(Common *, Common *, _QWORD, _QWORD))GetPersistedRegistryLocationW)(v23, v22, 0, 0);
      if ( v25 == 234 )
      {
        v24 = (unsigned __int16 *)operator new((unsigned int)Size);
        operator delete(0, v26);
        v25 = v21(*a1, a1[1], v24, (unsigned int)Size);
      }
      if ( v25 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v25,
                (unsigned int)&Size);
        v28 = v24;
      }
      else
      {
        *a2 = v24;
        v29 = *a1;
        v40 = 0;
        v41 = 0;
        v30 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v40, (const unsigned __int16 *)v29);
        v17 = v30;
        if ( v30 >= 0 )
        {
          v31 = *a2;
          v43 = 0;
          v42 = 0;
          v32 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v42, v31);
          v17 = v32;
          if ( v32 >= 0 )
          {
            Buffer[0] = *((_QWORD *)&v40 + 1);
            Buffer[1] = *((_QWORD *)&v42 + 1);
            NewElement = 0;
            if ( RtlInsertElementGenericTableAvl(Block, Buffer, 0x10u, &NewElement) )
            {
              v17 = NewElement == 0 ? 0x800702BA : 0;
              if ( NewElement )
              {
                *((_QWORD *)&v40 + 1) = 0;
                LODWORD(v40) = 0;
                v41 = 0;
                *((_QWORD *)&v42 + 1) = 0;
                LODWORD(v42) = 0;
                v43 = 0;
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v42);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v40);
                operator delete(0, v35);
                Common::AutoHandleCloseModule<HINSTANCE__ *>(v19);
                goto LABEL_32;
              }
            }
            else
            {
              v17 = -2147024882;
            }
            v33 = v17;
            v34 = 347;
          }
          else
          {
            v33 = (unsigned int)v32;
            v34 = 346;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v34,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)v33,
            (int)&Size);
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v42);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)(unsigned int)v30,
            (int)&Size);
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v40);
        v28 = 0;
      }
      operator delete(v28, v27);
      Common::AutoHandleCloseModule<HINSTANCE__ *>(v19);
      goto LABEL_38;
    }
  }
  Common::AutoHandleCloseModule<HINSTANCE__ *>(v19);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v38);
  IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (const unsigned __int16 *)a2, v36);
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
0x18002b7b0  mov     [rsp-28h+arg_0], rbx
0x18002b7b5  mov     [rsp-28h+arg_8], rsi
0x18002b7ba  push    rbp
0x18002b7bb  push    rdi
0x18002b7bc  push    r12
0x18002b7be  push    r14
0x18002b7c0  push    r15
0x18002b7c2  mov     rbp, rsp
0x18002b7c5  sub     rsp, 80h
0x18002b7cc  mov     rsi, rcx
0x18002b7cf  xor     r12d, r12d
0x18002b7d2  lea     rcx, [rbp+NewElement]; bool *
0x18002b7d6  mov     [rbp+NewElement], r12b
0x18002b7da  mov     r14, rdx
0x18002b7dd  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18002b7e2  mov     ebx, eax
0x18002b7e4  test    eax, eax
0x18002b7e6  jns     short loc_18002B807
0x18002b7e8  mov     edx, 115h; void *
0x18002b7ed  mov     rcx, [rbp+28h]; this
0x18002b7f1  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002b7f8  mov     r9d, ebx; char *
0x18002b7fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b800  mov     eax, ebx
0x18002b802  jmp     loc_18002BB56
0x18002b807  cmp     [rbp+NewElement], r12b
0x18002b80b  jnz     short loc_18002B82A
0x18002b80d  mov     rcx, [rsi+8]; this
0x18002b811  mov     rdx, r14; unsigned __int16 *
0x18002b814  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18002b819  mov     ebx, eax
0x18002b81b  test    eax, eax
0x18002b81d  jns     loc_18002BB54
0x18002b823  mov     edx, 119h
0x18002b828  jmp     short loc_18002B7ED
0x18002b82a  lea     rdx, qword_18004C0F8
0x18002b831  lea     rcx, [rbp+NewElement]
0x18002b835  call    ?RtlAcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b83a  cmp     cs:Block, r12
0x18002b841  jz      short loc_18002B88C
0x18002b843  mov     rdx, [rsi]
0x18002b846  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18002b84b  test    rax, rax
0x18002b84e  jz      short loc_18002B88C
0x18002b850  mov     rdx, r14; unsigned __int16 *
0x18002b853  mov     rcx, rax; this
0x18002b856  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18002b85b  mov     ebx, eax
0x18002b85d  test    eax, eax
0x18002b85f  jns     short loc_18002B87B
0x18002b861  mov     rcx, [rbp+28h]; this
0x18002b865  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002b86c  mov     r9d, eax; char *
0x18002b86f  mov     edx, 122h; void *
0x18002b874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b879  jmp     short loc_18002B87E
0x18002b87b  mov     ebx, r12d
0x18002b87e  lea     rcx, [rbp+NewElement]
0x18002b882  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b887  jmp     loc_18002B800
0x18002b88c  lea     rcx, [rbp+NewElement]
0x18002b890  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b895  lea     rdx, qword_18004C0F8
0x18002b89c  lea     rcx, [rbp+var_50]
0x18002b8a0  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18002b8a5  cmp     cs:Block, r12
0x18002b8ac  jnz     short loc_18002B8F4
0x18002b8ae  mov     ecx, 78h ; 'x'; Size
0x18002b8b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b8b8  mov     rbx, rax
0x18002b8bb  mov     qword ptr [rsp+80h+TableContext], r12; int
0x18002b8c0  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x18002b8c7  mov     rcx, rbx; Table
0x18002b8ca  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEBG@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18002b8d1  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18002b8d8  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18002b8df  mov     [rbx+68h], rax
0x18002b8e3  mov     [rbx+70h], rax
0x18002b8e7  call    cs:__imp_RtlInitializeGenericTableAvl
0x18002b8ed  mov     cs:Block, rbx
0x18002b8f4  mov     rdx, [rsi]
0x18002b8f7  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18002b8fc  test    rax, rax
0x18002b8ff  jz      short loc_18002B933
0x18002b901  mov     rdx, r14; unsigned __int16 *
0x18002b904  mov     rcx, rax; this
0x18002b907  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18002b90c  mov     esi, eax
0x18002b90e  test    eax, eax
0x18002b910  jns     loc_18002BAD7
0x18002b916  mov     rcx, [rbp+28h]; this
0x18002b91a  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002b921  mov     r9d, eax; char *
0x18002b924  mov     edx, 131h; void *
0x18002b929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b92e  jmp     loc_18002BB1A
0x18002b933  xor     edx, edx; hFile
0x18002b935  lea     rcx, LibFileName; "kernelbase.dll"
0x18002b93c  mov     r8d, 800h; dwFlags
0x18002b942  call    cs:__imp_LoadLibraryExW
0x18002b948  mov     rbx, rax
0x18002b94b  test    rax, rax
0x18002b94e  jz      loc_18002BB27
0x18002b954  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x18002b95b  mov     rcx, rax; hModule
0x18002b95e  call    GetProcAddress_0
0x18002b963  mov     r15, rax
0x18002b966  test    rax, rax
0x18002b969  jz      loc_18002BB27
0x18002b96f  mov     rdx, [rsi+8]
0x18002b973  lea     rax, [rbp+Size]
0x18002b977  mov     rcx, [rsi]
0x18002b97a  xor     r9d, r9d
0x18002b97d  mov     qword ptr [rsp+80h+TableContext], rax
0x18002b982  xor     r8d, r8d
0x18002b985  mov     rax, r15
0x18002b988  mov     dword ptr [rbp+Size], r12d
0x18002b98c  mov     rdi, r12
0x18002b98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b994  cmp     eax, 0EAh
0x18002b999  jnz     short loc_18002B9CC
0x18002b99b  mov     ecx, dword ptr [rbp+Size]; Size
0x18002b99e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b9a3  xor     ecx, ecx; void *
0x18002b9a5  mov     rdi, rax
0x18002b9a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b9ad  mov     r9d, dword ptr [rbp+Size]
0x18002b9b1  lea     rax, [rbp+Size]
0x18002b9b5  mov     rdx, [rsi+8]
0x18002b9b9  mov     r8, rdi
0x18002b9bc  mov     rcx, [rsi]
0x18002b9bf  mov     qword ptr [rsp+80h+TableContext], rax; int
0x18002b9c4  mov     rax, r15
0x18002b9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9cc  test    eax, eax
0x18002b9ce  jz      short loc_18002B9F2
0x18002b9d0  mov     rcx, [rbp+28h]; this
0x18002b9d4  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002b9db  mov     r9d, eax; char *
0x18002b9de  mov     edx, 153h; void *
0x18002b9e3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b9e8  mov     esi, eax
0x18002b9ea  mov     rcx, rdi
0x18002b9ed  jmp     loc_18002BB0D
0x18002b9f2  mov     [r14], rdi
0x18002b9f5  lea     rcx, [rbp+var_38]; this
0x18002b9f9  mov     rdx, [rsi]; unsigned __int16 *
0x18002b9fc  xorps   xmm0, xmm0
0x18002b9ff  movups  [rbp+var_38], xmm0
0x18002ba03  mov     [rbp+var_28], r12d
0x18002ba07  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002ba0c  mov     esi, eax
0x18002ba0e  test    eax, eax
0x18002ba10  jns     short loc_18002BA2F
0x18002ba12  mov     rcx, [rbp+28h]; this
0x18002ba16  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002ba1d  mov     r9d, eax; char *
0x18002ba20  mov     edx, 158h; void *
0x18002ba25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba2a  jmp     loc_18002BB02
0x18002ba2f  mov     rdx, [r14]; unsigned __int16 *
0x18002ba32  lea     rcx, [rbp+var_20]; this
0x18002ba36  xorps   xmm0, xmm0
0x18002ba39  mov     [rbp+var_10], r12d
0x18002ba3d  movups  [rbp+var_20], xmm0
0x18002ba41  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18002ba46  mov     esi, eax
0x18002ba48  test    eax, eax
0x18002ba4a  jns     short loc_18002BA59
0x18002ba4c  mov     r9d, eax
0x18002ba4f  mov     edx, 15Ah
0x18002ba54  jmp     loc_18002BAE9
0x18002ba59  mov     rax, qword ptr [rbp+var_38+8]
0x18002ba5d  lea     r9, [rbp+NewElement]; NewElement
0x18002ba61  mov     rcx, cs:Block; Table
0x18002ba68  lea     rdx, [rbp+Buffer]; Buffer
0x18002ba6c  mov     [rbp+Buffer], rax
0x18002ba70  mov     r8d, 10h; BufferSize
0x18002ba76  mov     rax, qword ptr [rbp+var_20+8]
0x18002ba7a  mov     [rbp+var_40], rax
0x18002ba7e  mov     [rbp+NewElement], r12b
0x18002ba82  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18002ba88  test    rax, rax
0x18002ba8b  jz      short loc_18002BADC
0x18002ba8d  mov     al, [rbp+NewElement]
0x18002ba90  neg     al
0x18002ba92  sbb     esi, esi
0x18002ba94  not     esi
0x18002ba96  and     esi, 800702BAh
0x18002ba9c  jl      short loc_18002BAE1
0x18002ba9e  lea     rcx, [rbp+var_20]; this
0x18002baa2  mov     qword ptr [rbp+var_38+8], r12
0x18002baa6  mov     dword ptr [rbp+var_38], r12d
0x18002baaa  mov     [rbp+var_28], r12d
0x18002baae  mov     qword ptr [rbp+var_20+8], r12
0x18002bab2  mov     dword ptr [rbp+var_20], r12d
0x18002bab6  mov     [rbp+var_10], r12d
0x18002baba  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002babf  lea     rcx, [rbp+var_38]; this
0x18002bac3  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bac8  xor     ecx, ecx; void *
0x18002baca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002bacf  mov     rcx, rbx
0x18002bad2  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18002bad7  mov     esi, r12d
0x18002bada  jmp     short loc_18002BB1A
0x18002badc  mov     esi, 8007000Eh
0x18002bae1  mov     r9d, esi; char *
0x18002bae4  mov     edx, 15Bh; void *
0x18002bae9  mov     rcx, [rbp+28h]; this
0x18002baed  lea     r8, aOnecoreBaseApp_26; "onecore\\base\\appmodel\\common\\states"...
0x18002baf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002baf9  lea     rcx, [rbp+var_20]; this
0x18002bafd  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bb02  lea     rcx, [rbp+var_38]; this
0x18002bb06  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18002bb0b  xor     ecx, ecx; void *
0x18002bb0d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002bb12  mov     rcx, rbx
0x18002bb15  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18002bb1a  lea     rcx, [rbp+var_50]
0x18002bb1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bb23  mov     eax, esi
0x18002bb25  jmp     short loc_18002BB56
0x18002bb27  mov     rcx, rbx
0x18002bb2a  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18002bb2f  lea     rcx, [rbp+var_50]
0x18002bb33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002bb38  mov     rcx, [rsi+8]; this
0x18002bb3c  mov     rdx, r14; unsigned __int16 *
0x18002bb3f  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18002bb44  mov     ebx, eax
0x18002bb46  test    eax, eax
0x18002bb48  jns     short loc_18002BB54
0x18002bb4a  mov     edx, 165h
0x18002bb4f  jmp     loc_18002B7ED
0x18002bb54  xor     eax, eax
0x18002bb56  lea     r11, [rsp+80h+var_s0]
0x18002bb5e  mov     rbx, [r11+30h]
0x18002bb62  mov     rsi, [r11+38h]
0x18002bb66  mov     rsp, r11
0x18002bb69  pop     r15
0x18002bb6b  pop     r14
0x18002bb6d  pop     r12
0x18002bb6f  pop     rdi
0x18002bb70  pop     rbp
0x18002bb71  retn
```
