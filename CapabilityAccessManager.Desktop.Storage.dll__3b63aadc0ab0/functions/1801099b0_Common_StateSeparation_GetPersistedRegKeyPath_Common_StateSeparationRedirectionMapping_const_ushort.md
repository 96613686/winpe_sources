# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x1801099b0`
- end: `0x180109dc4`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `1044`
- prototype: `__int64 __fastcall(Common **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180109dcc`

## callees

- `0x180003430`
- `0x180003b80`
- `0x1800e4be4`
- `0x1800e4c70`
- `0x1800eabf4`
- `0x180101ebc`
- `0x18010979c`
- `0x1801098c0`
- `0x1801099b0`
- `0x18010a720`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180109b79`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180109b79`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109d14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109d61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109d7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109d14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109d61`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180109d7d`
- `ntdll!RtlReleaseSRWLockShared` at `0x180109a98`
- `ntdll!RtlReleaseSRWLockShared` at `0x180109aa6`
- `ntdll!RtlReleaseSRWLockShared` at `0x180109a98`
- `ntdll!RtlReleaseSRWLockShared` at `0x180109aa6`
- `ntdll!RtlAcquireSRWLockShared` at `0x180109a2e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180109a2e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180109d6b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180109d87`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180109d6b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180109d87`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180109aaf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180109aaf`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180109ced`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180109ced`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180109b04`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180109b04`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180109a53`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180109b27`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180109a53`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180109b27`

## string_xrefs

- `0x180109b72`: `kernelbase.dll`
- `0x1801099ee`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109a80`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109b54`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109c18`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109c5b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109ca3`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109d2a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180109b8f`: `GetPersistedRegistryLocationW`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(Common **a1, unsigned __int16 **a2)
{
  int IsStateSeparationEnabled; // ebx
  unsigned __int16 **v5; // r8
  __int64 v6; // rdx
  _QWORD *v8; // rax
  unsigned __int16 **v9; // r8
  Common *v10; // rcx
  int v11; // eax
  PRTL_AVL_TABLE v12; // rbx
  PVOID v13; // rax
  unsigned __int16 **v14; // r8
  Common *v15; // rcx
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
  void *v26; // rcx
  int v27; // eax
  void *v28; // rdi
  void *v29; // r14
  unsigned __int16 **v30; // r8
  int TableContext; // [rsp+20h] [rbp-50h]
  __int128 Buffer; // [rsp+38h] [rbp-38h] BYREF
  int v33; // [rsp+48h] [rbp-28h]
  void *v34[2]; // [rsp+50h] [rbp-20h] BYREF
  int v35; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  void *NewElement; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v38; // [rsp+B8h] [rbp+48h] BYREF

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
    IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (void **)a2, v5);
    if ( IsStateSeparationEnabled < 0 )
    {
      v6 = 281;
      goto LABEL_3;
    }
    return 0;
  }
  RtlAcquireSRWLockShared(&qword_1801405F0);
  if ( qword_1801405E8 )
  {
    Buffer = (unsigned __int64)*a1;
    v8 = RtlLookupElementGenericTableAvl(qword_1801405E8, &Buffer);
    v10 = v8 ? (Common *)v8[1] : 0LL;
    if ( v10 )
    {
      v11 = Common::CopyStringToOutput(v10, (void **)a2, v9);
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
      RtlReleaseSRWLockShared(&qword_1801405F0);
      return (unsigned int)IsStateSeparationEnabled;
    }
  }
  RtlReleaseSRWLockShared(&qword_1801405F0);
  RtlAcquireSRWLockExclusive(&qword_1801405F0);
  v12 = qword_1801405E8;
  if ( !qword_1801405E8 )
  {
    v12 = (PRTL_AVL_TABLE)operator new(0x78u);
    NewElement = v12;
    v12[1].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    v12[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateArray<unsigned short const *>;
    RtlInitializeGenericTableAvl(
      v12,
      (PRTL_AVL_COMPARE_ROUTINE)Common::GenericMapCaseInsensitiveCompare,
      (PRTL_AVL_ALLOCATE_ROUTINE)Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
      (PRTL_AVL_FREE_ROUTINE)Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapFree,
      0);
    qword_1801405E8 = v12;
  }
  Buffer = (unsigned __int64)*a1;
  v13 = RtlLookupElementGenericTableAvl(v12, &Buffer);
  if ( v13 )
  {
    v15 = (Common *)*((_QWORD *)v13 + 1);
    if ( v15 )
    {
      v16 = Common::CopyStringToOutput(v15, (void **)a2, v14);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v16,
          TableContext);
LABEL_48:
        RtlReleaseSRWLockExclusive(&qword_1801405F0);
        return v17;
      }
LABEL_39:
      v17 = 0;
      goto LABEL_48;
    }
  }
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v19 = Library;
  *(_QWORD *)&Buffer = Library;
  if ( Library )
  {
    GetPersistedRegistryLocationW = GetProcAddress_0(Library, "GetPersistedRegistryLocationW");
    v21 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetPersistedRegistryLocationW;
    if ( GetPersistedRegistryLocationW )
    {
      v22 = 0;
      NewElement = 0;
      v38 = 0;
      v23 = ((__int64 (__fastcall *)(Common *, Common *, _QWORD, _QWORD))GetPersistedRegistryLocationW)(
              *a1,
              a1[1],
              0,
              0);
      if ( v23 == 234 )
      {
        v22 = (unsigned __int16 *)operator new[](v38);
        operator delete(0);
        NewElement = v22;
        v23 = v21(*a1, a1[1], v22, v38);
      }
      if ( v23 )
      {
        v17 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x153,
                (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                (const char *)v23,
                (unsigned int)&v38);
        v24 = v22;
LABEL_47:
        operator delete(v24);
        FreeLibrary(v19);
        goto LABEL_48;
      }
      *a2 = v22;
      Buffer = 0;
      v33 = 0;
      v25 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&Buffer, (const unsigned __int16 *)*a1);
      v17 = v25;
      if ( v25 >= 0 )
      {
        *(_OWORD *)v34 = 0;
        v35 = 0;
        v27 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v34, *a2);
        v17 = v27;
        if ( v27 >= 0 )
        {
          v28 = (void *)*((_QWORD *)&Buffer + 1);
          *(_QWORD *)&Buffer = *((_QWORD *)&Buffer + 1);
          v29 = v34[1];
          *((void **)&Buffer + 1) = v34[1];
          LOBYTE(NewElement) = 0;
          if ( RtlInsertElementGenericTableAvl(qword_1801405E8, &Buffer, 0x10u, (PBOOLEAN)&NewElement) )
          {
            v17 = (_BYTE)NewElement == 0 ? 0x800702BA : 0;
            if ( (_BYTE)NewElement )
            {
              operator delete(0);
              FreeLibrary(v19);
              goto LABEL_39;
            }
          }
          else
          {
            v17 = -2147024882;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15B,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)v17,
            (int)&v38);
          if ( v29 )
            operator delete(v29);
          if ( !v28 )
            goto LABEL_46;
          v26 = v28;
          goto LABEL_45;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v27,
          (int)&v38);
        if ( v34[1] )
          operator delete(v34[1]);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v25,
          (int)&v38);
      }
      v26 = (void *)*((_QWORD *)&Buffer + 1);
      if ( !*((_QWORD *)&Buffer + 1) )
      {
LABEL_46:
        v24 = 0;
        goto LABEL_47;
      }
LABEL_45:
      operator delete(v26);
      goto LABEL_46;
    }
  }
  if ( v19 )
    FreeLibrary(v19);
  RtlReleaseSRWLockExclusive(&qword_1801405F0);
  IsStateSeparationEnabled = Common::CopyStringToOutput(a1[1], (void **)a2, v30);
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
0x1801099b0  mov     [rsp-28h+arg_0], rbx
0x1801099b5  mov     [rsp-28h+arg_8], rsi
0x1801099ba  push    rbp
0x1801099bb  push    rdi
0x1801099bc  push    r13
0x1801099be  push    r14
0x1801099c0  push    r15
0x1801099c2  mov     rbp, rsp
0x1801099c5  sub     rsp, 70h
0x1801099c9  mov     r14, rdx
0x1801099cc  mov     rsi, rcx
0x1801099cf  mov     byte ptr [rbp+NewElement], 0
0x1801099d3  lea     rcx, [rbp+NewElement]; bool *
0x1801099d7  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1801099dc  mov     ebx, eax
0x1801099de  test    eax, eax
0x1801099e0  jns     short loc_180109A01
0x1801099e2  mov     edx, 115h; void *
0x1801099e7  mov     rcx, [rbp+28h]; this
0x1801099eb  mov     r9d, ebx; char *
0x1801099ee  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x1801099f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801099fa  mov     eax, ebx
0x1801099fc  jmp     loc_180109DAB
0x180109a01  cmp     byte ptr [rbp+NewElement], 0
0x180109a05  jnz     short loc_180109A24
0x180109a07  mov     rdx, r14; unsigned __int16 *
0x180109a0a  mov     rcx, [rsi+8]; this
0x180109a0e  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180109a13  mov     ebx, eax
0x180109a15  test    eax, eax
0x180109a17  jns     loc_180109DA9
0x180109a1d  mov     edx, 119h
0x180109a22  jmp     short loc_1801099E7
0x180109a24  lea     r13, qword_1801405F0
0x180109a2b  mov     rcx, r13
0x180109a2e  call    cs:__imp_RtlAcquireSRWLockShared
0x180109a34  mov     rcx, cs:qword_1801405E8; Table
0x180109a3b  test    rcx, rcx
0x180109a3e  jz      short loc_180109AA3
0x180109a40  mov     rax, [rsi]
0x180109a43  mov     qword ptr [rbp+Buffer], rax
0x180109a47  mov     qword ptr [rbp+Buffer+8], 0
0x180109a4f  lea     rdx, [rbp+Buffer]; Buffer
0x180109a53  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180109a59  test    rax, rax
0x180109a5c  jnz     short loc_180109A62
0x180109a5e  xor     ecx, ecx
0x180109a60  jmp     short loc_180109A66
0x180109a62  mov     rcx, [rax+8]; this
0x180109a66  test    rcx, rcx
0x180109a69  jz      short loc_180109AA3
0x180109a6b  mov     rdx, r14; unsigned __int16 *
0x180109a6e  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180109a73  mov     ebx, eax
0x180109a75  test    eax, eax
0x180109a77  jns     short loc_180109A93
0x180109a79  mov     rcx, [rbp+28h]; this
0x180109a7d  mov     r9d, eax; char *
0x180109a80  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109a87  mov     edx, 122h; void *
0x180109a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109a91  jmp     short loc_180109A95
0x180109a93  xor     ebx, ebx
0x180109a95  mov     rcx, r13
0x180109a98  call    cs:__imp_RtlReleaseSRWLockShared
0x180109a9e  jmp     loc_1801099FA
0x180109aa3  mov     rcx, r13
0x180109aa6  call    cs:__imp_RtlReleaseSRWLockShared
0x180109aac  mov     rcx, r13
0x180109aaf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180109ab5  mov     [rbp+var_40], r13
0x180109ab9  mov     rbx, cs:qword_1801405E8
0x180109ac0  test    rbx, rbx
0x180109ac3  jnz     short loc_180109B11
0x180109ac5  lea     ecx, [rbx+78h]; Size
0x180109ac8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180109acd  mov     rbx, rax
0x180109ad0  mov     [rbp+NewElement], rax
0x180109ad4  lea     rax, ??$DeallocateArray@PEBG@Common@@YAXPEBG@Z; Common::DeallocateArray<ushort const *>(ushort const *)
0x180109adb  mov     [rbx+68h], rax
0x180109adf  mov     [rbx+70h], rax
0x180109ae3  mov     qword ptr [rsp+70h+TableContext], 0; int
0x180109aec  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEBG@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180109af3  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180109afa  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180109b01  mov     rcx, rbx; Table
0x180109b04  call    cs:__imp_RtlInitializeGenericTableAvl
0x180109b0a  mov     cs:qword_1801405E8, rbx
0x180109b11  mov     rax, [rsi]
0x180109b14  mov     qword ptr [rbp+Buffer], rax
0x180109b18  mov     qword ptr [rbp+Buffer+8], 0
0x180109b20  lea     rdx, [rbp+Buffer]; Buffer
0x180109b24  mov     rcx, rbx; Table
0x180109b27  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180109b2d  test    rax, rax
0x180109b30  jz      short loc_180109B6A
0x180109b32  mov     rcx, [rax+8]; this
0x180109b36  test    rcx, rcx
0x180109b39  jz      short loc_180109B6A
0x180109b3b  mov     rdx, r14; unsigned __int16 *
0x180109b3e  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180109b43  mov     esi, eax
0x180109b45  test    eax, eax
0x180109b47  jns     loc_180109D1A
0x180109b4d  mov     rcx, [rbp+28h]; this
0x180109b51  mov     r9d, eax; char *
0x180109b54  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109b5b  mov     edx, 131h; void *
0x180109b60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109b65  jmp     loc_180109D68
0x180109b6a  xor     edx, edx; hFile
0x180109b6c  mov     r8d, 800h; dwFlags
0x180109b72  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180109b79  call    cs:__imp_LoadLibraryExW
0x180109b7f  mov     rbx, rax
0x180109b82  mov     qword ptr [rbp+Buffer], rax
0x180109b86  test    rax, rax
0x180109b89  jz      loc_180109D75
0x180109b8f  lea     rdx, aGetpersistedre; "GetPersistedRegistryLocationW"
0x180109b96  mov     rcx, rax; hModule
0x180109b99  call    GetProcAddress_0
0x180109b9e  mov     r15, rax
0x180109ba1  test    rax, rax
0x180109ba4  jz      loc_180109D75
0x180109baa  xor     edi, edi
0x180109bac  mov     [rbp+NewElement], rdi
0x180109bb0  mov     [rbp+arg_18], edi
0x180109bb3  lea     rax, [rbp+arg_18]
0x180109bb7  mov     qword ptr [rsp+70h+TableContext], rax
0x180109bbc  xor     r9d, r9d
0x180109bbf  xor     r8d, r8d
0x180109bc2  mov     rdx, [rsi+8]
0x180109bc6  mov     rcx, [rsi]
0x180109bc9  mov     rax, r15
0x180109bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109bd1  cmp     eax, 0EAh
0x180109bd6  jnz     short loc_180109C0D
0x180109bd8  mov     ecx, [rbp+arg_18]; unsigned __int64
0x180109bdb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180109be0  mov     rdi, rax
0x180109be3  xor     ecx, ecx; void *
0x180109be5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109bea  mov     [rbp+NewElement], rdi
0x180109bee  lea     rax, [rbp+arg_18]
0x180109bf2  mov     qword ptr [rsp+70h+TableContext], rax; int
0x180109bf7  mov     r9d, [rbp+arg_18]
0x180109bfb  mov     r8, rdi
0x180109bfe  mov     rdx, [rsi+8]
0x180109c02  mov     rcx, [rsi]
0x180109c05  mov     rax, r15
0x180109c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c0d  test    eax, eax
0x180109c0f  jz      short loc_180109C33
0x180109c11  mov     rcx, [rbp+28h]; this
0x180109c15  mov     r9d, eax; char *
0x180109c18  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109c1f  mov     edx, 153h; void *
0x180109c24  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180109c29  mov     esi, eax
0x180109c2b  mov     rcx, rdi
0x180109c2e  jmp     loc_180109D58
0x180109c33  mov     [r14], rdi
0x180109c36  xor     eax, eax
0x180109c38  xorps   xmm0, xmm0
0x180109c3b  movups  [rbp+Buffer], xmm0
0x180109c3f  mov     [rbp+var_28], eax
0x180109c42  mov     rdx, [rsi]; Src
0x180109c45  lea     rcx, [rbp+Buffer]; this
0x180109c49  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180109c4e  mov     esi, eax
0x180109c50  test    eax, eax
0x180109c52  jns     short loc_180109C7E
0x180109c54  mov     rcx, [rbp+28h]; this
0x180109c58  mov     r9d, eax; char *
0x180109c5b  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109c62  mov     edx, 158h; void *
0x180109c67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c6c  mov     rcx, qword ptr [rbp+Buffer+8]
0x180109c70  test    rcx, rcx
0x180109c73  jz      loc_180109D56
0x180109c79  jmp     loc_180109D50
0x180109c7e  xor     eax, eax
0x180109c80  xorps   xmm0, xmm0
0x180109c83  movups  xmmword ptr [rbp+var_20], xmm0
0x180109c87  mov     [rbp+var_10], eax
0x180109c8a  mov     rdx, [r14]; Src
0x180109c8d  lea     rcx, [rbp+var_20]; this
0x180109c91  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180109c96  mov     esi, eax
0x180109c98  test    eax, eax
0x180109c9a  jns     short loc_180109CC4
0x180109c9c  mov     rcx, [rbp+28h]; this
0x180109ca0  mov     r9d, eax; char *
0x180109ca3  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109caa  mov     edx, 15Ah; void *
0x180109caf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109cb4  mov     rcx, [rbp+var_20+8]; void *
0x180109cb8  test    rcx, rcx
0x180109cbb  jz      short loc_180109C6C
0x180109cbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109cc2  jmp     short loc_180109C6C
0x180109cc4  mov     rdi, qword ptr [rbp+Buffer+8]
0x180109cc8  mov     qword ptr [rbp+Buffer], rdi
0x180109ccc  mov     r14, [rbp+var_20+8]
0x180109cd0  mov     qword ptr [rbp+Buffer+8], r14
0x180109cd4  mov     byte ptr [rbp+NewElement], 0
0x180109cd8  lea     r9, [rbp+NewElement]; NewElement
0x180109cdc  mov     r8d, 10h; BufferSize
0x180109ce2  lea     rdx, [rbp+Buffer]; Buffer
0x180109ce6  mov     rcx, cs:qword_1801405E8; Table
0x180109ced  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180109cf3  test    rax, rax
0x180109cf6  jz      short loc_180109D1E
0x180109cf8  mov     al, byte ptr [rbp+NewElement]
0x180109cfb  neg     al
0x180109cfd  sbb     esi, esi
0x180109cff  not     esi
0x180109d01  and     esi, 800702BAh
0x180109d07  jl      short loc_180109D23
0x180109d09  xor     ecx, ecx; void *
0x180109d0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109d10  nop
0x180109d11  mov     rcx, rbx; hLibModule
0x180109d14  call    cs:__imp_FreeLibrary
0x180109d1a  xor     esi, esi
0x180109d1c  jmp     short loc_180109D68
0x180109d1e  mov     esi, 8007000Eh
0x180109d23  mov     rcx, [rbp+28h]; this
0x180109d27  mov     r9d, esi; char *
0x180109d2a  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\states"...
0x180109d31  mov     edx, 15Bh; void *
0x180109d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109d3b  test    r14, r14
0x180109d3e  jz      short loc_180109D48
0x180109d40  mov     rcx, r14; void *
0x180109d43  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109d48  test    rdi, rdi
0x180109d4b  jz      short loc_180109D56
0x180109d4d  mov     rcx, rdi; void *
0x180109d50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109d55  nop
0x180109d56  xor     ecx, ecx; void *
0x180109d58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180109d5d  nop
0x180109d5e  mov     rcx, rbx; hLibModule
0x180109d61  call    cs:__imp_FreeLibrary
0x180109d67  nop
0x180109d68  mov     rcx, r13
0x180109d6b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180109d71  mov     eax, esi
0x180109d73  jmp     short loc_180109DAB
0x180109d75  test    rbx, rbx
0x180109d78  jz      short loc_180109D84
0x180109d7a  mov     rcx, rbx; hLibModule
0x180109d7d  call    cs:__imp_FreeLibrary
0x180109d83  nop
0x180109d84  mov     rcx, r13
0x180109d87  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180109d8d  mov     rdx, r14; unsigned __int16 *
0x180109d90  mov     rcx, [rsi+8]; this
0x180109d94  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180109d99  mov     ebx, eax
0x180109d9b  test    eax, eax
0x180109d9d  jns     short loc_180109DA9
0x180109d9f  mov     edx, 165h
0x180109da4  jmp     loc_1801099E7
0x180109da9  xor     eax, eax
0x180109dab  lea     r11, [rsp+70h+var_s0]
0x180109db0  mov     rbx, [r11+30h]
0x180109db4  mov     rsi, [r11+38h]
0x180109db8  mov     rsp, r11
0x180109dbb  pop     r15
0x180109dbd  pop     r14
0x180109dbf  pop     r13
0x180109dc1  pop     rdi
0x180109dc2  pop     rbp
0x180109dc3  retn
```
