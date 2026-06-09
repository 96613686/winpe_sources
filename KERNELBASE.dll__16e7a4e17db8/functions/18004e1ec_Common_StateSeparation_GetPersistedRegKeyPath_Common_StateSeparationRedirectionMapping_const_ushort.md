# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x18004e1ec`
- end: `0x18004e3f3`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `519`
- prototype: `__int64 __fastcall(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004df54`
- `0x18009484c`
- `0x18012469c`

## callees

- `0x1800145c0`
- `0x1800147a0`
- `0x1800222a0`
- `0x180032f18`
- `0x18004c240`
- `0x18004e1ec`
- `0x18004f200`
- `0x180056ec0`
- `0x180058768`
- `0x18009ce3c`
- `0x1800a7f44`
- `0x1800ab1d0`
- `0x1800e48ac`
- `0x1800f306c`
- `0x180123ab0`
- `0x180124928`
- `0x180197010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18004e256`
- `ntdll!RtlReleaseSRWLockShared` at `0x18004e256`
- `ntdll!RtlAcquireSRWLockShared` at `0x18004e23c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18004e23c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004e25f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004e25f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004e2ac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004e2ac`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18018f4dc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18018f4dc`

## string_xrefs

- `0x18004e28b`: `kernelbase.dll`
- `0x18004e31b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18004e348`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18004e385`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18004e3cc`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18018f32c`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18018f40f`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18018f431`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18018f473`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18018f509`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18018f381`: `GetPersistedRegistryLocationW`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(
        const struct Common::StateSeparationRedirectionMapping *a1,
        unsigned __int16 **a2)
{
  unsigned int IsStateSeparationEnabled; // ebx
  __int64 v5; // rcx
  Common *v6; // rcx
  int CacheMapIfNeeded; // eax
  __int64 v8; // rcx
  unsigned int v9; // esi
  Common *v10; // rax
  unsigned __int16 **v11; // r8
  HMODULE Library; // rax
  HMODULE v13; // rbx
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  Common *v20; // rax
  unsigned __int16 **v21; // r8
  int v22; // eax
  __int64 v23; // rdx
  FARPROC GetPersistedRegistryLocationW; // rax
  __int64 (__fastcall *v25)(_QWORD, _QWORD, _QWORD, _QWORD); // rsi
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned __int16 *v28; // rdi
  unsigned int v29; // eax
  unsigned __int16 *v30; // rcx
  const unsigned __int16 *v31; // rdx
  int v32; // eax
  const unsigned __int16 *v33; // rdx
  int v34; // eax
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  int v37; // [rsp+20h] [rbp-60h]
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-50h] BYREF
  _DWORD Size[5]; // [rsp+34h] [rbp-4Ch] BYREF
  int v40; // [rsp+48h] [rbp-38h]
  void *Buffer[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v42; // [rsp+60h] [rbp-20h] BYREF
  int v43; // [rsp+70h] [rbp-10h]
  __int64 *v44; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  NewElement[0] = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)NewElement);
  if ( (IsStateSeparationEnabled & 0x80000000) != 0 )
  {
    v19 = 277;
    goto LABEL_12;
  }
  if ( !NewElement[0] )
  {
    v17 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
    v40 = 0;
    *(_OWORD *)&Size[1] = 0;
    v18 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&Size[1], v17);
    IsStateSeparationEnabled = v18;
    if ( v18 >= 0 )
      goto LABEL_8;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)v18,
      v37);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&Size[1]);
    v19 = 281;
    goto LABEL_12;
  }
  RtlAcquireSRWLockShared(&qword_18039F5F0);
  Buffer[0] = &qword_18039F5F0;
  if ( Table )
  {
    v20 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(v5, *(_QWORD *)a1);
    if ( v20 )
    {
      v22 = Common::CopyStringToOutput(v20, (const unsigned __int16 *)a2, v21);
      IsStateSeparationEnabled = v22;
      if ( v22 >= 0 )
        IsStateSeparationEnabled = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x122,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v22,
          v37);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(Buffer);
      return IsStateSeparationEnabled;
    }
  }
  RtlReleaseSRWLockShared(&qword_18039F5F0);
  RtlAcquireSRWLockExclusive(&qword_18039F5F0);
  v44 = &qword_18039F5F0;
  CacheMapIfNeeded = Common::CreateCacheMapIfNeeded(v6);
  v9 = CacheMapIfNeeded;
  if ( CacheMapIfNeeded < 0 )
  {
    v23 = 297;
  }
  else
  {
    v10 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(v8, *(_QWORD *)a1);
    if ( !v10 )
    {
      Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
      v13 = Library;
      if ( !Library )
      {
LABEL_7:
        RtlReleaseSRWLockExclusive(&qword_18039F5F0);
        v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
        v40 = 0;
        *(_OWORD *)&Size[1] = 0;
        v15 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&Size[1], v14);
        IsStateSeparationEnabled = v15;
        if ( v15 >= 0 )
        {
LABEL_8:
          *a2 = *(unsigned __int16 **)&Size[3];
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v15,
          v37);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&Size[1]);
        v19 = 357;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)IsStateSeparationEnabled,
          v37);
        return IsStateSeparationEnabled;
      }
      GetPersistedRegistryLocationW = GetProcAddress(Library, "GetPersistedRegistryLocationW");
      v25 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetPersistedRegistryLocationW;
      if ( !GetPersistedRegistryLocationW )
      {
        FreeLibrary(v13);
        goto LABEL_7;
      }
      v26 = *((_QWORD *)a1 + 1);
      v27 = *(_QWORD *)a1;
      Size[0] = 0;
      v28 = 0;
      v29 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))GetPersistedRegistryLocationW)(v27, v26, 0, 0);
      if ( v29 == 234 )
      {
        Buffer[0] = 0;
        Common::GlobalHeap::Alloc(Size[0], Buffer);
        v28 = (unsigned __int16 *)Buffer[0];
        if ( !Buffer[0] )
        {
          v9 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)0x8007000ELL,
            (int)Size);
LABEL_44:
          v30 = 0;
          goto LABEL_45;
        }
        Common::GlobalHeap::Free(0);
        v29 = v25(*(_QWORD *)a1, *((_QWORD *)a1 + 1), v28, Size[0]);
      }
      if ( v29 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x153,
               (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
               (const char *)v29,
               (unsigned int)Size);
        v30 = v28;
LABEL_45:
        Common::GlobalHeap::Free(v30);
        FreeLibrary(v13);
        goto LABEL_46;
      }
      *a2 = v28;
      v31 = *(const unsigned __int16 **)a1;
      v42 = 0;
      v43 = 0;
      v32 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v42, v31);
      v9 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v32,
          (int)Size);
LABEL_43:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v42);
        goto LABEL_44;
      }
      v33 = *a2;
      v40 = 0;
      *(_OWORD *)&Size[1] = 0;
      v34 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&Size[1], v33);
      v9 = v34;
      if ( v34 < 0 )
      {
        v35 = (unsigned int)v34;
        v36 = 346;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)v35,
          (int)Size);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&Size[1]);
        goto LABEL_43;
      }
      Buffer[0] = *((void **)&v42 + 1);
      Buffer[1] = *(void **)&Size[3];
      NewElement[0] = 0;
      if ( !RtlInsertElementGenericTableAvl(Table, Buffer, 0x10u, NewElement) )
      {
        v9 = -2147024882;
        goto LABEL_41;
      }
      if ( !NewElement[0] )
      {
        v9 = -2147024198;
LABEL_41:
        v35 = v9;
        v36 = 347;
        goto LABEL_42;
      }
      *((_QWORD *)&v42 + 1) = 0;
      LODWORD(v42) = 0;
      v43 = 0;
      *(_QWORD *)&Size[3] = 0;
      Size[1] = 0;
      v40 = 0;
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&Size[1]);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v42);
      Common::GlobalHeap::Free(0);
      FreeLibrary(v13);
      goto LABEL_25;
    }
    CacheMapIfNeeded = Common::CopyStringToOutput(v10, (const unsigned __int16 *)a2, v11);
    v9 = CacheMapIfNeeded;
    if ( CacheMapIfNeeded >= 0 )
    {
LABEL_25:
      v9 = 0;
      goto LABEL_46;
    }
    v23 = 305;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)(unsigned int)CacheMapIfNeeded,
    v37);
LABEL_46:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v44);
  return v9;
}

```

## disassembly

```asm
0x18004e1ec  mov     [rsp-28h+arg_10], rbx
0x18004e1f1  mov     [rsp-28h+arg_18], rsi
0x18004e1f6  push    rbp
0x18004e1f7  push    rdi
0x18004e1f8  push    r12
0x18004e1fa  push    r14
0x18004e1fc  push    r15
0x18004e1fe  mov     rbp, rsp
0x18004e201  sub     rsp, 80h
0x18004e208  mov     r15, rcx
0x18004e20b  xor     r12d, r12d
0x18004e20e  lea     rcx, [rbp+NewElement]; bool *
0x18004e212  mov     [rbp+NewElement], r12b
0x18004e216  mov     r14, rdx
0x18004e219  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x18004e21e  mov     ebx, eax
0x18004e220  test    eax, eax
0x18004e222  js      loc_18004E33F
0x18004e228  cmp     [rbp+NewElement], r12b
0x18004e22c  jz      loc_18004E2F9
0x18004e232  lea     rdi, qword_18039F5F0
0x18004e239  mov     rcx, rdi
0x18004e23c  call    cs:__imp_RtlAcquireSRWLockShared
0x18004e242  cmp     cs:Table, r12
0x18004e249  mov     [rbp+Buffer], rdi
0x18004e24d  jnz     loc_18004E35B
0x18004e253  mov     rcx, rdi
0x18004e256  call    cs:__imp_RtlReleaseSRWLockShared
0x18004e25c  mov     rcx, rdi
0x18004e25f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004e265  mov     [rbp+var_8], rdi
0x18004e269  call    ?CreateCacheMapIfNeeded@Common@@YAJXZ; Common::CreateCacheMapIfNeeded(void)
0x18004e26e  mov     esi, eax
0x18004e270  test    eax, eax
0x18004e272  js      loc_18004E39F
0x18004e278  mov     rdx, [r15]
0x18004e27b  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18004e280  test    rax, rax
0x18004e283  jnz     loc_18004E3A9
0x18004e289  xor     edx, edx; hFile
0x18004e28b  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x18004e292  mov     r8d, 800h; dwFlags
0x18004e298  call    LoadLibraryExW
0x18004e29d  mov     rbx, rax
0x18004e2a0  test    rax, rax
0x18004e2a3  jnz     loc_18018F381
0x18004e2a9  mov     rcx, rdi
0x18004e2ac  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18004e2b2  mov     rdx, [r15+8]; unsigned __int16 *
0x18004e2b6  lea     rcx, [rbp+Size+4]; this
0x18004e2ba  xorps   xmm0, xmm0
0x18004e2bd  mov     [rbp+var_38], r12d
0x18004e2c1  movups  xmmword ptr [rbp+Size+4], xmm0
0x18004e2c5  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18004e2ca  mov     ebx, eax
0x18004e2cc  test    eax, eax
0x18004e2ce  js      loc_18004E3C8
0x18004e2d4  mov     rax, qword ptr [rbp+Size+0Ch]
0x18004e2d8  mov     [r14], rax
0x18004e2db  xor     eax, eax
0x18004e2dd  lea     r11, [rsp+80h+var_s0]
0x18004e2e5  mov     rbx, [r11+40h]
0x18004e2e9  mov     rsi, [r11+48h]
0x18004e2ed  mov     rsp, r11
0x18004e2f0  pop     r15
0x18004e2f2  pop     r14
0x18004e2f4  pop     r12
0x18004e2f6  pop     rdi
0x18004e2f7  pop     rbp
0x18004e2f8  retn
0x18004e2f9  mov     rdx, [r15+8]; unsigned __int16 *
0x18004e2fd  lea     rcx, [rbp+Size+4]; this
0x18004e301  xorps   xmm0, xmm0
0x18004e304  mov     [rbp+var_38], r12d
0x18004e308  movups  xmmword ptr [rbp+Size+4], xmm0
0x18004e30c  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18004e311  mov     ebx, eax
0x18004e313  test    eax, eax
0x18004e315  jns     short loc_18004E2D4
0x18004e317  mov     rcx, [rbp+28h]; this
0x18004e31b  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18004e322  mov     r9d, eax; char *
0x18004e325  mov     edx, 31h ; '1'; void *
0x18004e32a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e32f  lea     rcx, [rbp+Size+4]; this
0x18004e333  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004e338  mov     edx, 119h
0x18004e33d  jmp     short loc_18004E344
0x18004e33f  mov     edx, 115h; void *
0x18004e344  mov     rcx, [rbp+28h]; this
0x18004e348  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18004e34f  mov     r9d, ebx; char *
0x18004e352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e357  mov     eax, ebx
0x18004e359  jmp     short loc_18004E2DD
0x18004e35b  mov     rdx, [r15]
0x18004e35e  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18004e363  test    rax, rax
0x18004e366  jz      loc_18004E253
0x18004e36c  mov     rdx, r14; unsigned __int16 *
0x18004e36f  mov     rcx, rax; this
0x18004e372  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18004e377  mov     ebx, eax
0x18004e379  test    eax, eax
0x18004e37b  jns     loc_18018F316
0x18004e381  mov     rcx, [rbp+28h]; this
0x18004e385  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18004e38c  mov     r9d, eax; char *
0x18004e38f  mov     edx, 122h; void *
0x18004e394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e399  nop
0x18004e39a  jmp     loc_18018F319
0x18004e39f  mov     edx, 129h; void *
0x18004e3a4  jmp     loc_18018F328
0x18004e3a9  mov     rdx, r14; unsigned __int16 *
0x18004e3ac  mov     rcx, rax; this
0x18004e3af  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x18004e3b4  mov     esi, eax
0x18004e3b6  test    eax, eax
0x18004e3b8  jns     loc_18018F379
0x18004e3be  mov     edx, 131h
0x18004e3c3  jmp     loc_18018F328
0x18004e3c8  mov     rcx, [rbp+28h]; this
0x18004e3cc  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18004e3d3  mov     r9d, ebx; char *
0x18004e3d6  mov     edx, 31h ; '1'; void *
0x18004e3db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e3e0  lea     rcx, [rbp+Size+4]; this
0x18004e3e4  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18004e3e9  mov     edx, 165h
0x18004e3ee  jmp     loc_18004E344
0x18018f316  mov     ebx, r12d
0x18018f319  lea     rcx, [rbp+Buffer]
0x18018f31d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18018f322  nop
0x18018f323  jmp     loc_18004E357
0x18018f328  mov     rcx, [rbp+28h]; this
0x18018f32c  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18018f333  mov     r9d, eax; char *
0x18018f336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f33b  jmp     loc_18018F536
0x18018f340  lea     rcx, [rbp+Size+4]; this
0x18018f344  mov     qword ptr [rbp+var_20+8], r12
0x18018f348  mov     dword ptr [rbp+var_20], r12d
0x18018f34c  mov     [rbp+var_10], r12d
0x18018f350  mov     qword ptr [rbp+Size+0Ch], r12
0x18018f354  mov     dword ptr [rbp+Size+4], r12d
0x18018f358  mov     [rbp+var_38], r12d
0x18018f35c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18018f361  lea     rcx, [rbp+var_20]; this
0x18018f365  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18018f36a  xor     ecx, ecx; void *
0x18018f36c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18018f371  mov     rcx, rbx; hLibModule
0x18018f374  call    FreeLibrary
0x18018f379  mov     esi, r12d
0x18018f37c  jmp     loc_18018F536
0x18018f381  lea     rdx, aGetpersistedre_3; "GetPersistedRegistryLocationW"
0x18018f388  mov     rcx, rbx; hModule
0x18018f38b  call    GetProcAddress
0x18018f390  mov     rsi, rax
0x18018f393  test    rax, rax
0x18018f396  jz      loc_18018F546
0x18018f39c  mov     rdx, [r15+8]
0x18018f3a0  lea     rax, [rbp+Size]
0x18018f3a4  mov     rcx, [r15]
0x18018f3a7  xor     r9d, r9d
0x18018f3aa  mov     qword ptr [rsp+80h+var_60], rax; int
0x18018f3af  xor     r8d, r8d
0x18018f3b2  mov     rax, rsi
0x18018f3b5  mov     dword ptr [rbp+Size], r12d
0x18018f3b9  mov     rdi, r12
0x18018f3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f3c1  cmp     eax, 0EAh
0x18018f3c6  jnz     short loc_18018F407
0x18018f3c8  mov     ecx, dword ptr [rbp+Size]; Size
0x18018f3cb  lea     rdx, [rbp+Buffer]; void **
0x18018f3cf  mov     [rbp+Buffer], r12
0x18018f3d3  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x18018f3d8  mov     rdi, [rbp+Buffer]
0x18018f3dc  test    rdi, rdi
0x18018f3df  jz      short loc_18018F42D
0x18018f3e1  xor     ecx, ecx; void *
0x18018f3e3  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18018f3e8  mov     r9d, dword ptr [rbp+Size]
0x18018f3ec  lea     rax, [rbp+Size]
0x18018f3f0  mov     rdx, [r15+8]
0x18018f3f4  mov     r8, rdi
0x18018f3f7  mov     rcx, [r15]
0x18018f3fa  mov     qword ptr [rsp+80h+var_60], rax; int
0x18018f3ff  mov     rax, rsi
0x18018f402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f407  test    eax, eax
0x18018f409  jz      short loc_18018F44F
0x18018f40b  mov     rcx, [rbp+28h]; this
0x18018f40f  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18018f416  mov     r9d, eax; char *
0x18018f419  mov     edx, 153h; void *
0x18018f41e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018f423  mov     esi, eax
0x18018f425  mov     rcx, rdi
0x18018f428  jmp     loc_18018F529
0x18018f42d  mov     rcx, [rbp+28h]; this
0x18018f431  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18018f438  mov     esi, 8007000Eh
0x18018f43d  mov     edx, 14Ah; void *
0x18018f442  mov     r9d, esi; char *
0x18018f445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f44a  jmp     loc_18018F527
0x18018f44f  mov     [r14], rdi
0x18018f452  lea     rcx, [rbp+var_20]; this
0x18018f456  mov     rdx, [r15]; unsigned __int16 *
0x18018f459  xorps   xmm0, xmm0
0x18018f45c  movups  [rbp+var_20], xmm0
0x18018f460  mov     [rbp+var_10], r12d
0x18018f464  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18018f469  mov     esi, eax
0x18018f46b  test    eax, eax
0x18018f46d  jns     short loc_18018F48C
0x18018f46f  mov     rcx, [rbp+28h]; this
0x18018f473  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18018f47a  mov     r9d, eax; char *
0x18018f47d  mov     edx, 158h; void *
0x18018f482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f487  jmp     loc_18018F51E
0x18018f48c  mov     rdx, [r14]; unsigned __int16 *
0x18018f48f  lea     rcx, [rbp+Size+4]; this
0x18018f493  xorps   xmm0, xmm0
0x18018f496  mov     [rbp+var_38], r12d
0x18018f49a  movups  xmmword ptr [rbp+Size+4], xmm0
0x18018f49e  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18018f4a3  mov     esi, eax
0x18018f4a5  test    eax, eax
0x18018f4a7  jns     short loc_18018F4B3
0x18018f4a9  mov     r9d, eax
0x18018f4ac  mov     edx, 15Ah
0x18018f4b1  jmp     short loc_18018F505
0x18018f4b3  mov     rax, qword ptr [rbp+var_20+8]
0x18018f4b7  lea     r9, [rbp+NewElement]; NewElement
0x18018f4bb  mov     rcx, cs:Table; Table
0x18018f4c2  lea     rdx, [rbp+Buffer]; Buffer
0x18018f4c6  mov     [rbp+Buffer], rax
0x18018f4ca  mov     r8d, 10h; BufferSize
0x18018f4d0  mov     rax, qword ptr [rbp+Size+0Ch]
0x18018f4d4  mov     [rbp+var_28], rax
0x18018f4d8  mov     [rbp+NewElement], r12b
0x18018f4dc  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18018f4e2  test    rax, rax
0x18018f4e5  jz      short loc_18018F4F8
0x18018f4e7  cmp     [rbp+NewElement], r12b
0x18018f4eb  jnz     loc_18018F340
0x18018f4f1  mov     esi, 800702BAh
0x18018f4f6  jmp     short loc_18018F4FD
0x18018f4f8  mov     esi, 8007000Eh
0x18018f4fd  mov     r9d, esi; char *
0x18018f500  mov     edx, 15Bh; void *
0x18018f505  mov     rcx, [rbp+28h]; this
0x18018f509  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18018f510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018f515  lea     rcx, [rbp+Size+4]; this
0x18018f519  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18018f51e  lea     rcx, [rbp+var_20]; this
0x18018f522  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18018f527  xor     ecx, ecx; void *
0x18018f529  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18018f52e  mov     rcx, rbx; hLibModule
0x18018f531  call    FreeLibrary
0x18018f536  lea     rcx, [rbp+var_8]
0x18018f53a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18018f53f  mov     eax, esi
0x18018f541  jmp     loc_18004E2DD
0x18018f546  mov     rcx, rbx; hLibModule
0x18018f549  call    FreeLibrary
0x18018f54e  nop
0x18018f54f  jmp     loc_18004E2A9
```
