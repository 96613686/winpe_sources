# Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)

- ea: `0x180058910`
- end: `0x18005901d`
- name: `?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z`
- size: `1805`
- prototype: `__int64 __usercall@<rax>(const struct Common::StateSeparationRedirectionMapping *@<rcx>, const unsigned __int16 **@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct Common::RegistryKey *)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034810`
- `0x180059030`
- `0x1800c2980`

## callees

- `0x1800145c0`
- `0x1800147a0`
- `0x1800222a0`
- `0x18004c240`
- `0x18004df24`
- `0x18004df54`
- `0x18004f0e8`
- `0x180058768`
- `0x180058790`
- `0x1800588a0`
- `0x180058910`
- `0x180059e60`
- `0x18005b460`
- `0x18005b710`
- `0x180093cec`
- `0x180188eb9`
- `0x180197010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18005895b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180058d45`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005895b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180058d45`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005893a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005893a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058d52`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058d52`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058d8b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058dd6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058d8b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058dd6`
- `ntdll!RtlFreeHeap` at `0x180058a50`
- `ntdll!RtlFreeHeap` at `0x180058af4`
- `ntdll!RtlFreeHeap` at `0x180058a50`
- `ntdll!RtlFreeHeap` at `0x180058af4`

## string_xrefs

- `0x180058d63`: `ntdll.dll`
- `0x1800589c4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058bf4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058c04`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058cf1`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058d09`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058fff`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180058e39`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180058a2a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180058e11`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180058e51`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180058ef0`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180058fc3`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetRegKeyContainingValue(
        const struct Common::StateSeparationRedirectionMapping *a1,
        const unsigned __int16 **a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        HANDLE *a6)
{
  char v9; // di
  const WCHAR *v10; // r15
  const WCHAR *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // r14
  unsigned int v15; // eax
  __int64 result; // rax
  __int64 i; // rbx
  PHANDLE v18; // rdi
  const WCHAR *v19; // rbx
  int v20; // eax
  unsigned int j; // edi
  int v22; // eax
  unsigned int v23; // r8d
  PHANDLE v24; // rdi
  int v25; // eax
  signed int v26; // ecx
  __int64 v27; // r9
  __int64 v28; // rdx
  int PersistedRegKeyPath; // eax
  unsigned int v30; // ebx
  WCHAR *v31; // rbx
  int v32; // eax
  unsigned int v33; // edi
  HKEY v34; // rcx
  int v35; // eax
  HMODULE Library; // rax
  HMODULE v37; // rbx
  __int64 (*RtlIsStateSeparationEnabled)(void); // rax
  char v39; // al
  int appended; // eax
  unsigned int v41; // edi
  void *v42; // rcx
  LSTATUS Value; // eax
  HKEY v44; // rdi
  HKEY v45; // rcx
  HKEY v46; // rdx
  bool v47; // sf
  int lpData; // [rsp+20h] [rbp-40h]
  int lpDataa; // [rsp+20h] [rbp-40h]
  int lpDatab; // [rsp+20h] [rbp-40h]
  int lpDatac; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v54; // [rsp+48h] [rbp-18h]
  PCWSTR SourceString; // [rsp+50h] [rbp-10h] BYREF
  PHANDLE v56; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v56 = a6;
  RtlAcquireSRWLockShared(&qword_18039F5E0);
  if ( byte_18039F5DC )
  {
    v9 = byte_18039F5DD;
    RtlReleaseSRWLockShared(&qword_18039F5E0);
  }
  else
  {
    RtlReleaseSRWLockShared(&qword_18039F5E0);
    RtlAcquireSRWLockExclusive(&qword_18039F5E0);
    if ( !byte_18039F5DC && (Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u), (v37 = Library) != 0) )
    {
      RtlIsStateSeparationEnabled = GetProcAddress(Library, "RtlIsStateSeparationEnabled");
      if ( RtlIsStateSeparationEnabled )
      {
        v39 = RtlIsStateSeparationEnabled();
        byte_18039F5DC = 1;
        v9 = v39 != 0;
        byte_18039F5DD = v39 != 0;
      }
      else
      {
        v9 = byte_18039F5DD;
      }
      FreeLibrary(v37);
      RtlReleaseSRWLockExclusive(&qword_18039F5E0);
    }
    else
    {
      v9 = byte_18039F5DD;
      RtlReleaseSRWLockExclusive(&qword_18039F5E0);
    }
  }
  if ( !v9 )
    goto LABEL_4;
  SourceString = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, a2, 1u, (unsigned __int16 **)&SourceString);
  v30 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      lpData);
    Common::GlobalHeap::Free((void *)SourceString);
    return v30;
  }
  v31 = (WCHAR *)SourceString;
  hKey = 0;
  v32 = Common::RegistryKey::Open((PHANDLE)&hKey, HKEY_LOCAL_MACHINE, SourceString, a5 | 0x20019);
  v33 = v32;
  if ( v32 <= -2147024895 || (unsigned int)(v32 + 2147024892) <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)(unsigned int)v32,
      lpData);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)v33,
      lpDatac);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    goto LABEL_78;
  }
  v34 = hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    Value = RegQueryValueExW(hKey, a4, 0, 0, 0, 0);
    v33 = Value;
    if ( !Value || Value == 234 )
    {
      v44 = hKey;
      v45 = 0;
      v46 = (HKEY)*a6;
      hKey = 0;
      if ( v46 != v44 )
      {
        if ( (unsigned __int64)v46 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          RegCloseKey(v46);
          v45 = hKey;
        }
        *a6 = v44;
      }
      if ( (unsigned __int64)v45 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(v45);
      Common::GlobalHeap::Free(v31);
      return 0;
    }
    if ( (unsigned int)(Value - 2) <= 1 )
      goto LABEL_92;
    v47 = Value < 0;
    if ( Value > 0 )
    {
      v33 = (unsigned __int16)Value | 0x80070000;
      v47 = 1;
    }
    if ( !v47 )
    {
LABEL_92:
      v34 = hKey;
      goto LABEL_61;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)v33,
      lpData);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
LABEL_78:
    Common::GlobalHeap::Free(v31);
    return v33;
  }
LABEL_61:
  if ( (unsigned __int64)v34 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v34);
  Common::GlobalHeap::Free(v31);
LABEL_4:
  v10 = (const WCHAR *)*((_QWORD *)a1 + 1);
  if ( !a2 )
  {
    v24 = v56;
    if ( (char *)*v56 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      RegCloseKey((HKEY)*v56);
    *v24 = 0;
    v25 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v10, v24, 0);
    v26 = v25;
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    result = 0;
    if ( v26 < 0 )
      return (unsigned int)v26;
    return result;
  }
  v54 = 0;
  *(_OWORD *)P = 0;
  if ( !v10 )
  {
    LODWORD(P[0]) = 0;
LABEL_22:
    for ( i = 0; !i && *a2; i = 1 )
    {
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)P, *a2);
      v41 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)appended,
          lpData);
        if ( P[1] )
          Common::GlobalHeap::Free(P[1]);
        return v41;
      }
    }
    v18 = v56;
    v19 = (const WCHAR *)P[1];
    if ( (char *)*v56 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      RegCloseKey((HKEY)*v56);
    *v18 = 0;
    v20 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v19, v18, 0);
    v13 = v20;
    if ( v20 > 0 )
      v13 = (unsigned __int16)v20 | 0x80070000;
    if ( (v13 & 0x80000000) != 0 )
    {
      if ( !P[1] )
        return v13;
      Common::GlobalHeap::Free(P[1]);
      return v13;
    }
    else
    {
      if ( P[1] )
        RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
      return 0;
    }
  }
  v11 = v10;
  v12 = 1073741822;
  while ( *v11 )
  {
    ++v11;
    if ( !--v12 )
    {
      v13 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        lpData);
      goto LABEL_18;
    }
  }
  v14 = (unsigned int)(1073741822 - v12);
  if ( (unsigned int)v14 > 0x7FFFFFFF )
  {
    v13 = -2147024362;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070216LL,
      lpData);
  }
  else
  {
    if ( !(_DWORD)v14 )
      goto LABEL_12;
    if ( (unsigned int)v14 <= 0x20 )
    {
      for ( j = 8; j < (unsigned int)v14; j *= 2 )
        ;
    }
    else
    {
      j = 1073741822 - v12;
    }
    if ( j > 0x3FFFFFFF )
    {
      v13 = -2147023613;
      v28 = 425;
      v27 = 2147943683LL;
    }
    else
    {
      if ( !j )
      {
        v42 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        P[1] = v42;
        if ( v42 )
        {
          Common::GlobalHeap::Free(v42);
          P[1] = 0;
          LODWORD(P[0]) = 0;
        }
        v23 = 0;
        v54 = 0;
        goto LABEL_43;
      }
      SourceString = 0;
      v22 = CommonHeapReAllocDefault(P[1], 0, 2LL * (j + 1), (void **)&SourceString);
      v13 = v22;
      if ( v22 >= 0 )
      {
        v23 = j + 1;
        P[1] = (PVOID)SourceString;
        v54 = j + 1;
        if ( LODWORD(P[0]) > j )
        {
          LODWORD(P[0]) = j;
          SourceString[j] = 0;
          goto LABEL_42;
        }
        if ( LODWORD(P[0]) < j && !LODWORD(P[0]) )
        {
          *SourceString = 0;
LABEL_42:
          v23 = v54;
        }
LABEL_43:
        if ( v23 )
        {
          v15 = v23 - 1;
          goto LABEL_13;
        }
LABEL_12:
        v15 = 0;
LABEL_13:
        if ( (unsigned int)v14 <= v15
          || (v35 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)P, v14), v13 = v35, v35 >= 0) )
        {
          LODWORD(P[0]) = v14;
          if ( (_DWORD)v14 )
            *((_WORD *)P[1] + v14) = 0;
          memcpy_0(P[1], v10, (unsigned int)(2 * v14));
          v13 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v35,
            lpData);
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x235,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)v13,
            lpDatab);
        }
        goto LABEL_17;
      }
      v27 = (unsigned int)v22;
      v28 = 458;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v27,
      lpData);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v13,
      lpDataa);
  }
LABEL_17:
  if ( (v13 & 0x80000000) == 0 )
    goto LABEL_22;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)v13,
    lpData);
  if ( P[1] )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
  return v13;
}

```

## disassembly

```asm
0x180058910  push    rbp
0x180058912  push    rbx
0x180058913  push    rsi
0x180058914  push    rdi
0x180058915  push    r13
0x180058917  push    r14
0x180058919  push    r15
0x18005891b  mov     rbp, rsp
0x18005891e  sub     rsp, 60h
0x180058922  mov     r15, [rbp+arg_28]
0x180058926  mov     rsi, rcx
0x180058929  lea     rcx, qword_18039F5E0
0x180058930  mov     [rbp+var_8], r15
0x180058934  mov     r14, r9
0x180058937  mov     r13, rdx
0x18005893a  call    cs:__imp_RtlAcquireSRWLockShared
0x180058940  cmp     cs:byte_18039F5DC, 0
0x180058947  lea     rcx, qword_18039F5E0
0x18005894e  jz      loc_180058D45
0x180058954  movzx   edi, cs:byte_18039F5DD
0x18005895b  call    cs:__imp_RtlReleaseSRWLockShared
0x180058961  mov     [rsp+60h+arg_10], r12
0x180058969  test    dil, dil
0x18005896c  jnz     loc_180058C37
0x180058972  mov     r12d, [rbp+arg_20]
0x180058976  or      r12d, 20019h
0x18005897d  mov     r15, [rsi+8]
0x180058981  test    r13, r13
0x180058984  jz      loc_180058B8E
0x18005898a  xor     r8d, r8d
0x18005898d  xor     eax, eax
0x18005898f  mov     [rbp+var_18], r8d
0x180058993  xorps   xmm0, xmm0
0x180058996  movups  xmmword ptr [rbp+P], xmm0
0x18005899a  test    r15, r15
0x18005899d  jz      loc_180058A6F
0x1800589a3  mov     r14d, 3FFFFFFEh
0x1800589a9  mov     rax, r15
0x1800589ac  mov     ecx, r14d
0x1800589af  nop
0x1800589b0  cmp     [rax], r8w
0x1800589b4  jz      short loc_1800589DF
0x1800589b6  add     rax, 2
0x1800589ba  sub     rcx, 1
0x1800589be  jnz     short loc_1800589B0
0x1800589c0  mov     rcx, [rbp+38h]; this
0x1800589c4  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x1800589cb  mov     ebx, 80070057h
0x1800589d0  mov     edx, 249h; void *
0x1800589d5  mov     r9d, ebx; char *
0x1800589d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800589dd  jmp     short loc_180058A26
0x1800589df  sub     r14d, ecx
0x1800589e2  cmp     r14d, 7FFFFFFFh
0x1800589e9  ja      loc_180058FFB
0x1800589ef  test    r14d, r14d
0x1800589f2  jnz     loc_180058B01
0x1800589f8  xor     eax, eax
0x1800589fa  cmp     r14d, eax
0x1800589fd  ja      loc_180058CD7
0x180058a03  mov     dword ptr [rbp+P], r14d
0x180058a07  test    r14d, r14d
0x180058a0a  jnz     loc_180058DFD
0x180058a10  mov     rcx, [rbp+P+8]; void *
0x180058a14  lea     r8d, [r14+r14]; Size
0x180058a18  mov     rdx, r15; Src
0x180058a1b  call    memcpy_0
0x180058a20  xor     ebx, ebx
0x180058a22  test    ebx, ebx
0x180058a24  jns     short loc_180058A72
0x180058a26  mov     rcx, [rbp+38h]; this
0x180058a2a  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x180058a31  mov     r9d, ebx; char *
0x180058a34  mov     edx, 0A7h; void *
0x180058a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058a3e  mov     r8, [rbp+P+8]; P
0x180058a42  test    r8, r8
0x180058a45  jz      short loc_180058A56
0x180058a47  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x180058a4e  xor     edx, edx; Flags
0x180058a50  call    cs:__imp_RtlFreeHeap
0x180058a56  mov     eax, ebx
0x180058a58  mov     r12, [rsp+60h+arg_10]
0x180058a60  add     rsp, 60h
0x180058a64  pop     r15
0x180058a66  pop     r14
0x180058a68  pop     r13
0x180058a6a  pop     rdi
0x180058a6b  pop     rsi
0x180058a6c  pop     rbx
0x180058a6d  pop     rbp
0x180058a6e  retn
0x180058a6f  mov     dword ptr [rbp+P], eax
0x180058a72  xor     ebx, ebx
0x180058a74  cmp     rbx, 1
0x180058a78  jnb     short loc_180058A88
0x180058a7a  mov     rdx, [r13+rbx*8+0]; unsigned __int16 *
0x180058a7f  test    rdx, rdx
0x180058a82  jnz     loc_180058E86
0x180058a88  mov     rdi, [rbp+var_8]
0x180058a8c  mov     rbx, [rbp+P+8]
0x180058a90  mov     rcx, [rdi]; hKey
0x180058a93  lea     rax, [rcx-1]
0x180058a97  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058a9b  jbe     loc_180058B84
0x180058aa1  mov     [rsp+60h+lpcbData], 0; __int64
0x180058aaa  mov     r9d, r12d
0x180058aad  xor     r8d, r8d
0x180058ab0  mov     [rsp+60h+lpData], rdi; PHANDLE
0x180058ab5  mov     rdx, rbx; SourceString
0x180058ab8  mov     qword ptr [rdi], 0
0x180058abf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058ac6  call    RegOpenKeyExInternalW
0x180058acb  mov     ebx, eax
0x180058acd  test    eax, eax
0x180058acf  jle     short loc_180058ADA
0x180058ad1  movzx   ebx, ax
0x180058ad4  or      ebx, 80070000h
0x180058ada  test    ebx, ebx
0x180058adc  js      loc_180058D22
0x180058ae2  mov     r8, [rbp+P+8]; P
0x180058ae6  test    r8, r8
0x180058ae9  jz      short loc_180058AFA
0x180058aeb  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x180058af2  xor     edx, edx; Flags
0x180058af4  call    cs:__imp_RtlFreeHeap
0x180058afa  xor     eax, eax
0x180058afc  jmp     loc_180058A58
0x180058b01  cmp     r14d, 20h ; ' '
0x180058b05  jbe     loc_180058C1D
0x180058b0b  mov     edi, r14d
0x180058b0e  cmp     edi, 3FFFFFFFh
0x180058b14  ja      loc_180058DEB
0x180058b1a  test    edi, edi
0x180058b1c  jz      loc_180058EA9
0x180058b22  lea     esi, [rdi+1]
0x180058b25  test    esi, esi
0x180058b27  jz      short loc_180058B72
0x180058b29  mov     rcx, [rbp+P+8]; Ptr
0x180058b2d  lea     r9, [rbp+SourceString]; void **
0x180058b31  mov     [rbp+SourceString], r8
0x180058b35  xor     edx, edx; unsigned __int64
0x180058b37  mov     r8d, esi
0x180058b3a  add     r8, r8; unsigned __int64
0x180058b3d  call    ?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z; CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)
0x180058b42  mov     ebx, eax
0x180058b44  test    eax, eax
0x180058b46  js      loc_180058BE8
0x180058b4c  mov     rdx, [rbp+SourceString]
0x180058b50  mov     r8d, esi
0x180058b53  mov     eax, dword ptr [rbp+P]
0x180058b56  mov     [rbp+P+8], rdx
0x180058b5a  mov     [rbp+var_18], esi
0x180058b5d  cmp     eax, edi
0x180058b5f  ja      loc_180058EDC
0x180058b65  jnb     short loc_180058B72
0x180058b67  test    eax, eax
0x180058b69  jnz     short loc_180058B72
0x180058b6b  mov     [rdx], ax
0x180058b6e  mov     r8d, [rbp+var_18]
0x180058b72  test    r8d, r8d
0x180058b75  jz      loc_1800589F8
0x180058b7b  lea     eax, [r8-1]
0x180058b7f  jmp     loc_1800589FA
0x180058b84  call    RegCloseKey
0x180058b89  jmp     loc_180058AA1
0x180058b8e  mov     rdi, [rbp+var_8]
0x180058b92  mov     rcx, [rdi]; hKey
0x180058b95  lea     rax, [rcx-1]
0x180058b99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058b9d  jbe     loc_180058D3B
0x180058ba3  mov     [rsp+60h+lpcbData], 0; __int64
0x180058bac  mov     r9d, r12d
0x180058baf  xor     r8d, r8d
0x180058bb2  mov     [rsp+60h+lpData], rdi; PHANDLE
0x180058bb7  mov     rdx, r15; SourceString
0x180058bba  mov     qword ptr [rdi], 0
0x180058bc1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058bc8  call    RegOpenKeyExInternalW
0x180058bcd  mov     ecx, eax
0x180058bcf  test    eax, eax
0x180058bd1  jle     short loc_180058BDC
0x180058bd3  movzx   ecx, ax
0x180058bd6  or      ecx, 80070000h
0x180058bdc  xor     eax, eax
0x180058bde  test    ecx, ecx
0x180058be0  cmovs   eax, ecx
0x180058be3  jmp     loc_180058A58
0x180058be8  mov     r9d, eax; char *
0x180058beb  mov     edx, 1CAh; void *
0x180058bf0  mov     rcx, [rbp+38h]; this
0x180058bf4  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x180058bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058c00  mov     rcx, [rbp+38h]; this
0x180058c04  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x180058c0b  mov     r9d, ebx; char *
0x180058c0e  mov     edx, 232h; void *
0x180058c13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058c18  jmp     loc_180058A22
0x180058c1d  mov     edi, 8
0x180058c22  cmp     r14d, edi
0x180058c25  jbe     loc_180058B0E
0x180058c2b  add     edi, edi
0x180058c2d  cmp     edi, r14d
0x180058c30  jb      short loc_180058C2B
0x180058c32  jmp     loc_180058B0E
0x180058c37  lea     r9, [rbp+SourceString]; unsigned __int16 **
0x180058c3b  mov     [rbp+SourceString], 0
0x180058c43  mov     r8d, 1; unsigned __int64
0x180058c49  mov     rdx, r13; unsigned __int16 **
0x180058c4c  mov     rcx, rsi; struct Common::StateSeparationRedirectionMapping *
0x180058c4f  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x180058c54  mov     ebx, eax
0x180058c56  test    eax, eax
0x180058c58  js      loc_180058E0D
0x180058c5e  mov     r12d, [rbp+arg_20]
0x180058c62  lea     rcx, [rbp+hKey]; this
0x180058c66  mov     rbx, [rbp+SourceString]
0x180058c6a  or      r12d, 20019h
0x180058c71  mov     r9d, r12d; unsigned int
0x180058c74  mov     [rbp+hKey], 0
0x180058c7c  mov     r8, rbx; SourceString
0x180058c7f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180058c86  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180058c8b  mov     edi, eax
0x180058c8d  cmp     eax, 80070001h
0x180058c92  jle     loc_180058E35
0x180058c98  lea     ecx, [rax+7FF8FFFCh]
0x180058c9e  cmp     ecx, 7FF8FFFBh
0x180058ca4  jbe     loc_180058E35
0x180058caa  mov     rcx, [rbp+hKey]; hKey
0x180058cae  lea     rax, [rcx-1]
0x180058cb2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058cb6  jbe     loc_180058F23
0x180058cbc  lea     rax, [rcx-1]
0x180058cc0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058cc4  jbe     loc_180058DE1
0x180058cca  mov     rcx, rbx; void *
0x180058ccd  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180058cd2  jmp     loc_18005897D
0x180058cd7  mov     edx, r14d; unsigned int
0x180058cda  lea     rcx, [rbp+P]; this
0x180058cde  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180058ce3  mov     ebx, eax
0x180058ce5  test    eax, eax
0x180058ce7  jns     loc_180058A03
0x180058ced  mov     rcx, [rbp+38h]; this
0x180058cf1  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x180058cf8  mov     r9d, eax; char *
0x180058cfb  mov     edx, 20Ch; void *
0x180058d00  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058d05  mov     rcx, [rbp+38h]; this
0x180058d09  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x180058d10  mov     r9d, ebx; char *
0x180058d13  mov     edx, 235h; void *
0x180058d18  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058d1d  jmp     loc_180058A22
0x180058d22  mov     rcx, [rbp+P+8]; void *
0x180058d26  test    rcx, rcx
0x180058d29  jz      loc_180058A56
0x180058d2f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180058d34  mov     eax, ebx
0x180058d36  jmp     loc_180058A58
0x180058d3b  call    RegCloseKey
0x180058d40  jmp     loc_180058BA3
0x180058d45  call    cs:__imp_RtlReleaseSRWLockShared
0x180058d4b  lea     rcx, qword_18039F5E0
0x180058d52  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180058d58  cmp     cs:byte_18039F5DC, 0
0x180058d5f  jnz     short loc_180058D7D
0x180058d61  xor     edx, edx; hFile
0x180058d63  lea     rcx, ModuleName; "ntdll.dll"
0x180058d6a  mov     r8d, 800h; dwFlags
0x180058d70  call    LoadLibraryExW
0x180058d75  mov     rbx, rax
0x180058d78  test    rax, rax
0x180058d7b  jnz     short loc_180058D96
0x180058d7d  movzx   edi, cs:byte_18039F5DD
0x180058d84  lea     rcx, qword_18039F5E0
0x180058d8b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180058d91  jmp     loc_180058961
0x180058d96  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x180058d9d  mov     rcx, rbx; hModule
0x180058da0  call    GetProcAddress
0x180058da5  test    rax, rax
0x180058da8  jz      loc_180058E9D
0x180058dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058db3  test    al, al
0x180058db5  mov     cs:byte_18039F5DC, 1
0x180058dbc  setnz   dil
0x180058dc0  mov     cs:byte_18039F5DD, dil
0x180058dc7  mov     rcx, rbx; hLibModule
0x180058dca  call    FreeLibrary
0x180058dcf  lea     rcx, qword_18039F5E0
0x180058dd6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180058ddc  jmp     loc_180058961
0x180058de1  call    RegCloseKey
0x180058de6  jmp     loc_180058CCA
0x180058deb  mov     ebx, 80070503h
0x180058df0  mov     edx, 1A9h
  ... truncated ...
```
