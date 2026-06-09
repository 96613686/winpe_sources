# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x18000f53c`
- end: `0x18000f8bb`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `895`
- prototype: `__int64 __fastcall(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f3e4`
- `0x180016a78`
- `0x18003ef0c`

## callees

- `0x180004920`
- `0x180007278`
- `0x180007a10`
- `0x180008db0`
- `0x18000d710`
- `0x18000f53c`
- `0x18000f8c4`
- `0x180010670`
- `0x180018248`
- `0x18001a604`
- `0x18001ed14`
- `0x18001fd80`
- `0x18001fe90`
- `0x18001ff0c`
- `0x18003e578`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f628`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000f628`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f87e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000f87e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f61f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000f61f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000f5bd`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000f5bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f6b5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000f6b5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000f699`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000f699`

## string_xrefs

- `0x18000f68c`: `kernelbase.dll`
- `0x18000f57a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f5f5`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f676`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f73a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f759`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f7aa`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f7ef`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000f6ab`: `GetPersistedRegistryLocationW`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(Common **a1, unsigned __int16 **a2)
{
  int IsStateSeparationEnabled; // ebx
  unsigned __int16 **v5; // r8
  __int64 v6; // rdx
  Common *v8; // rax
  unsigned __int16 **v9; // r8
  int v10; // eax
  Common *v11; // rcx
  int CacheMapIfNeeded; // eax
  unsigned int v13; // esi
  __int64 v14; // rdx
  Common *v15; // rax
  unsigned __int16 **v16; // r8
  HMODULE Library; // rax
  HMODULE v18; // rbx
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v20)(_QWORD, _QWORD, _QWORD, _QWORD); // rsi
  Common *v21; // rdx
  Common *v22; // rcx
  unsigned __int16 *v23; // rdi
  unsigned int v24; // eax
  unsigned __int16 *v25; // rcx
  Common *v26; // rdx
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  int v29; // eax
  __int64 v30; // rdx
  unsigned __int16 **v31; // r8
  int v32; // [rsp+20h] [rbp-50h]
  __int64 *v33; // [rsp+30h] [rbp-40h] BYREF
  __int128 v34; // [rsp+38h] [rbp-38h] BYREF
  int v35; // [rsp+48h] [rbp-28h]
  __int128 v36; // [rsp+50h] [rbp-20h] BYREF
  int v37; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  SIZE_T Size; // [rsp+B0h] [rbp+40h] BYREF
  void *v40; // [rsp+B8h] [rbp+48h] BYREF

  LOBYTE(Size) = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&Size);
  if ( IsStateSeparationEnabled < 0 )
  {
    v6 = 277;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      v32);
    return (unsigned int)IsStateSeparationEnabled;
  }
  if ( !(_BYTE)Size )
  {
    IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (void **)a2, v5);
    if ( IsStateSeparationEnabled < 0 )
    {
      v6 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  RtlAcquireSRWLockShared(&qword_180064DC0);
  Size = (SIZE_T)&qword_180064DC0;
  if ( Table )
  {
    v8 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(Table, *a1);
    if ( v8 )
    {
      v10 = Common::CopyStringToOutput(v8, (void **)a2, v9);
      IsStateSeparationEnabled = v10;
      if ( v10 >= 0 )
        IsStateSeparationEnabled = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v10,
          v32);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&Size);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  RtlReleaseSRWLockShared(&qword_180064DC0);
  RtlAcquireSRWLockExclusive(&qword_180064DC0);
  v33 = &qword_180064DC0;
  CacheMapIfNeeded = Common::CreateCacheMapIfNeeded(v11);
  v13 = CacheMapIfNeeded;
  if ( CacheMapIfNeeded < 0 )
  {
    v14 = 297;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)CacheMapIfNeeded,
      v32);
LABEL_40:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v33);
    return v13;
  }
  v15 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(Table, *a1);
  if ( v15 )
  {
    CacheMapIfNeeded = Common::CopyStringToOutput(v15, (void **)a2, v16);
    v13 = CacheMapIfNeeded;
    if ( CacheMapIfNeeded < 0 )
    {
      v14 = 305;
      goto LABEL_19;
    }
LABEL_39:
    v13 = 0;
    goto LABEL_40;
  }
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v18 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetPersistedRegistryLocationW");
    v20 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( ProcAddress )
    {
      v21 = a1[1];
      v22 = *a1;
      LODWORD(Size) = 0;
      v23 = 0;
      v24 = ((__int64 (__fastcall *)(Common *, Common *, _QWORD, _QWORD))ProcAddress)(v22, v21, 0, 0);
      if ( v24 == 234 )
      {
        v40 = 0;
        Common::GlobalHeap::Alloc((unsigned int)Size, &v40);
        v23 = (unsigned __int16 *)v40;
        if ( !v40 )
        {
          v13 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)0x8007000ELL,
            (int)&Size);
          goto LABEL_28;
        }
        Common::GlobalHeap::Free(0);
        v24 = v20(*a1, a1[1], v23, (unsigned int)Size);
      }
      if ( v24 )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v24,
                (unsigned int)&Size);
        v25 = v23;
LABEL_29:
        Common::GlobalHeap::Free(v25);
        Common::AutoHandleCloseModule<HINSTANCE__ *>(v18);
        goto LABEL_40;
      }
      *a2 = v23;
      v26 = *a1;
      v34 = 0;
      v35 = 0;
      v27 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v34, (const unsigned __int16 *)v26);
      v13 = v27;
      if ( v27 >= 0 )
      {
        v28 = *a2;
        v37 = 0;
        v36 = 0;
        v29 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v36, v28);
        v13 = v29;
        if ( v29 >= 0 )
        {
          v29 = Common::GenericMap<unsigned short const *,unsigned short const *>::Insert(
                  Table,
                  *((_QWORD *)&v34 + 1),
                  *((_QWORD *)&v36 + 1));
          v13 = v29;
          if ( v29 >= 0 )
          {
            *((_QWORD *)&v34 + 1) = 0;
            LODWORD(v34) = 0;
            v35 = 0;
            *((_QWORD *)&v36 + 1) = 0;
            LODWORD(v36) = 0;
            v37 = 0;
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v34);
            Common::GlobalHeap::Free(0);
            Common::AutoHandleCloseModule<HINSTANCE__ *>(v18);
            goto LABEL_39;
          }
          v30 = 347;
        }
        else
        {
          v30 = 346;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v29,
          (int)&Size);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v36);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v27,
          (int)&Size);
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v34);
LABEL_28:
      v25 = 0;
      goto LABEL_29;
    }
  }
  Common::AutoHandleCloseModule<HINSTANCE__ *>(v18);
  RtlReleaseSRWLockExclusive(&qword_180064DC0);
  IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (void **)a2, v31);
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
0x18000f53c  mov     [rsp-28h+arg_0], rbx
0x18000f541  mov     [rsp-28h+arg_8], rsi
0x18000f546  push    rbp
0x18000f547  push    rdi
0x18000f548  push    r12
0x18000f54a  push    r14
0x18000f54c  push    r15
0x18000f54e  mov     rbp, rsp
0x18000f551  sub     rsp, 70h
0x18000f555  mov     r14, rcx
0x18000f558  xor     r12d, r12d
0x18000f55b  lea     rcx, [rbp+Size]; bool *
0x18000f55f  mov     byte ptr [rbp+Size], r12b
0x18000f563  mov     r15, rdx
0x18000f566  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18000f56b  mov     ebx, eax
0x18000f56d  test    eax, eax
0x18000f56f  jns     short loc_18000F590
0x18000f571  mov     edx, 115h; void *
0x18000f576  mov     rcx, [rbp+28h]; this
0x18000f57a  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f581  mov     r9d, ebx; char *
0x18000f584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f589  mov     eax, ebx
0x18000f58b  jmp     loc_18000F8A2
0x18000f590  cmp     byte ptr [rbp+Size], r12b
0x18000f594  jnz     short loc_18000F5B3
0x18000f596  mov     rcx, [r14+8]; this
0x18000f59a  mov     rdx, r15; unsigned __int16 *
0x18000f59d  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18000f5a2  mov     ebx, eax
0x18000f5a4  test    eax, eax
0x18000f5a6  jns     loc_18000F8A0
0x18000f5ac  mov     edx, 119h
0x18000f5b1  jmp     short loc_18000F576
0x18000f5b3  lea     rdi, qword_180064DC0
0x18000f5ba  mov     rcx, rdi
0x18000f5bd  call    cs:__imp_RtlAcquireSRWLockShared
0x18000f5c3  mov     rcx, cs:Table
0x18000f5ca  mov     [rbp+Size], rdi
0x18000f5ce  test    rcx, rcx
0x18000f5d1  jz      short loc_18000F61C
0x18000f5d3  mov     rdx, [r14]
0x18000f5d6  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18000f5db  test    rax, rax
0x18000f5de  jz      short loc_18000F61C
0x18000f5e0  mov     rdx, r15; unsigned __int16 *
0x18000f5e3  mov     rcx, rax; this
0x18000f5e6  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18000f5eb  mov     ebx, eax
0x18000f5ed  test    eax, eax
0x18000f5ef  jns     short loc_18000F60B
0x18000f5f1  mov     rcx, [rbp+28h]; this
0x18000f5f5  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f5fc  mov     r9d, eax; char *
0x18000f5ff  mov     edx, 122h; void *
0x18000f604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f609  jmp     short loc_18000F60E
0x18000f60b  mov     ebx, r12d
0x18000f60e  lea     rcx, [rbp+Size]
0x18000f612  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f617  jmp     loc_18000F589
0x18000f61c  mov     rcx, rdi
0x18000f61f  call    cs:__imp_RtlReleaseSRWLockShared
0x18000f625  mov     rcx, rdi
0x18000f628  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000f62e  mov     [rbp+var_40], rdi
0x18000f632  call    ?CreateCacheMapIfNeeded@Common@@YAJXZ; Common::CreateCacheMapIfNeeded(void)
0x18000f637  mov     esi, eax
0x18000f639  test    eax, eax
0x18000f63b  jns     short loc_18000F644
0x18000f63d  mov     edx, 129h
0x18000f642  jmp     short loc_18000F672
0x18000f644  mov     rdx, [r14]
0x18000f647  mov     rcx, cs:Table
0x18000f64e  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18000f653  test    rax, rax
0x18000f656  jz      short loc_18000F68A
0x18000f658  mov     rdx, r15; unsigned __int16 *
0x18000f65b  mov     rcx, rax; this
0x18000f65e  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18000f663  mov     esi, eax
0x18000f665  test    eax, eax
0x18000f667  jns     loc_18000F863
0x18000f66d  mov     edx, 131h; void *
0x18000f672  mov     rcx, [rbp+28h]; this
0x18000f676  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f67d  mov     r9d, eax; char *
0x18000f680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f685  jmp     loc_18000F866
0x18000f68a  xor     edx, edx; hFile
0x18000f68c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000f693  mov     r8d, 800h; dwFlags
0x18000f699  call    cs:__imp_LoadLibraryExW
0x18000f69f  mov     rbx, rax
0x18000f6a2  test    rax, rax
0x18000f6a5  jz      loc_18000F873
0x18000f6ab  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x18000f6b2  mov     rcx, rax; hModule
0x18000f6b5  call    cs:__imp_GetProcAddress
0x18000f6bb  mov     rsi, rax
0x18000f6be  test    rax, rax
0x18000f6c1  jz      loc_18000F873
0x18000f6c7  mov     rdx, [r14+8]
0x18000f6cb  lea     rax, [rbp+Size]
0x18000f6cf  mov     rcx, [r14]
0x18000f6d2  xor     r9d, r9d
0x18000f6d5  mov     qword ptr [rsp+70h+var_50], rax; int
0x18000f6da  xor     r8d, r8d
0x18000f6dd  mov     rax, rsi
0x18000f6e0  mov     dword ptr [rbp+Size], r12d
0x18000f6e4  mov     rdi, r12
0x18000f6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ec  cmp     eax, 0EAh
0x18000f6f1  jnz     short loc_18000F732
0x18000f6f3  mov     ecx, dword ptr [rbp+Size]; Size
0x18000f6f6  lea     rdx, [rbp+arg_18]; void **
0x18000f6fa  mov     [rbp+arg_18], r12
0x18000f6fe  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x18000f703  mov     rdi, [rbp+arg_18]
0x18000f707  test    rdi, rdi
0x18000f70a  jz      short loc_18000F755
0x18000f70c  xor     ecx, ecx; void *
0x18000f70e  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000f713  mov     r9d, dword ptr [rbp+Size]
0x18000f717  lea     rax, [rbp+Size]
0x18000f71b  mov     rdx, [r14+8]
0x18000f71f  mov     r8, rdi
0x18000f722  mov     rcx, [r14]
0x18000f725  mov     qword ptr [rsp+70h+var_50], rax; int
0x18000f72a  mov     rax, rsi
0x18000f72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f732  test    eax, eax
0x18000f734  jz      short loc_18000F786
0x18000f736  mov     rcx, [rbp+28h]; this
0x18000f73a  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f741  mov     r9d, eax; char *
0x18000f744  mov     edx, 153h; void *
0x18000f749  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000f74e  mov     esi, eax
0x18000f750  mov     rcx, rdi
0x18000f753  jmp     short loc_18000F774
0x18000f755  mov     rcx, [rbp+28h]; this
0x18000f759  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f760  mov     esi, 8007000Eh
0x18000f765  mov     edx, 14Ah; void *
0x18000f76a  mov     r9d, esi; char *
0x18000f76d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f772  xor     ecx, ecx; void *
0x18000f774  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000f779  mov     rcx, rbx
0x18000f77c  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18000f781  jmp     loc_18000F866
0x18000f786  mov     [r15], rdi
0x18000f789  lea     rcx, [rbp+var_38]; this
0x18000f78d  mov     rdx, [r14]; Src
0x18000f790  xorps   xmm0, xmm0
0x18000f793  movups  [rbp+var_38], xmm0
0x18000f797  mov     [rbp+var_28], r12d
0x18000f79b  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18000f7a0  mov     esi, eax
0x18000f7a2  test    eax, eax
0x18000f7a4  jns     short loc_18000F7C9
0x18000f7a6  mov     rcx, [rbp+28h]; this
0x18000f7aa  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f7b1  mov     r9d, eax; char *
0x18000f7b4  mov     edx, 158h; void *
0x18000f7b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f7be  lea     rcx, [rbp+var_38]; this
0x18000f7c2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000f7c7  jmp     short loc_18000F772
0x18000f7c9  mov     rdx, [r15]; Src
0x18000f7cc  lea     rcx, [rbp+var_20]; this
0x18000f7d0  xorps   xmm0, xmm0
0x18000f7d3  mov     [rbp+var_10], r12d
0x18000f7d7  movups  [rbp+var_20], xmm0
0x18000f7db  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18000f7e0  mov     esi, eax
0x18000f7e2  test    eax, eax
0x18000f7e4  jns     short loc_18000F809
0x18000f7e6  mov     edx, 15Ah; void *
0x18000f7eb  mov     rcx, [rbp+28h]; this
0x18000f7ef  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x18000f7f6  mov     r9d, eax; char *
0x18000f7f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f7fe  lea     rcx, [rbp+var_20]; this
0x18000f802  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000f807  jmp     short loc_18000F7BE
0x18000f809  mov     r8, qword ptr [rbp+var_20+8]
0x18000f80d  mov     rdx, qword ptr [rbp+var_38+8]
0x18000f811  mov     rcx, cs:Table
0x18000f818  call    ?Insert@?$GenericMap@PEBGPEBG@Common@@QEAAJPEBG0@Z; Common::GenericMap<ushort const *,ushort const *>::Insert(ushort const *,ushort const *)
0x18000f81d  mov     esi, eax
0x18000f81f  test    eax, eax
0x18000f821  jns     short loc_18000F82A
0x18000f823  mov     edx, 15Bh
0x18000f828  jmp     short loc_18000F7EB
0x18000f82a  lea     rcx, [rbp+var_20]; this
0x18000f82e  mov     qword ptr [rbp+var_38+8], r12
0x18000f832  mov     dword ptr [rbp+var_38], r12d
0x18000f836  mov     [rbp+var_28], r12d
0x18000f83a  mov     qword ptr [rbp+var_20+8], r12
0x18000f83e  mov     dword ptr [rbp+var_20], r12d
0x18000f842  mov     [rbp+var_10], r12d
0x18000f846  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000f84b  lea     rcx, [rbp+var_38]; this
0x18000f84f  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000f854  xor     ecx, ecx; void *
0x18000f856  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000f85b  mov     rcx, rbx
0x18000f85e  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18000f863  mov     esi, r12d
0x18000f866  lea     rcx, [rbp+var_40]
0x18000f86a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f86f  mov     eax, esi
0x18000f871  jmp     short loc_18000F8A2
0x18000f873  mov     rcx, rbx
0x18000f876  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18000f87b  mov     rcx, rdi
0x18000f87e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000f884  mov     rcx, [r14+8]; this
0x18000f888  mov     rdx, r15; unsigned __int16 *
0x18000f88b  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18000f890  mov     ebx, eax
0x18000f892  test    eax, eax
0x18000f894  jns     short loc_18000F8A0
0x18000f896  mov     edx, 165h
0x18000f89b  jmp     loc_18000F576
0x18000f8a0  xor     eax, eax
0x18000f8a2  lea     r11, [rsp+70h+var_s0]
0x18000f8a7  mov     rbx, [r11+30h]
0x18000f8ab  mov     rsi, [r11+38h]
0x18000f8af  mov     rsp, r11
0x18000f8b2  pop     r15
0x18000f8b4  pop     r14
0x18000f8b6  pop     r12
0x18000f8b8  pop     rdi
0x18000f8b9  pop     rbp
0x18000f8ba  retn
```
