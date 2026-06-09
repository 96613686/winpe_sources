# CLanguagePackInstallerSingleton::InstallLanguage(ILanguagePackInstaller *,ushort const *,int,bool)

- ea: `0x14003ec3c`
- end: `0x14003efd6`
- name: `?InstallLanguage@CLanguagePackInstallerSingleton@@QEAAJPEAUILanguagePackInstaller@@PEBGH_N@Z`
- size: `922`
- prototype: `int(CLanguagePackInstallerSingleton *__hidden this, struct ILanguagePackInstaller *, const unsigned __int16 *, int, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14003df10`

## callees

- `0x140005f60`
- `0x14000e624`
- `0x14003e3b0`
- `0x14003e3cc`
- `0x14003ec3c`
- `0x14003f000`
- `0x14003ff9c`
- `0x1400405f8`
- `0x1400407b0`
- `0x1400408dc`
- `0x140040ebc`
- `0x140041054`
- `0x14007d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14003ee02`
- `KERNEL32!EnterCriticalSection` at `0x14003ee02`
- `KERNEL32!TlsGetValue` at `0x14003ec6c`
- `KERNEL32!TlsGetValue` at `0x14003ec6c`
- `KERNEL32!GetLastError` at `0x14003eecd`
- `KERNEL32!GetLastError` at `0x14003eecd`
- `KERNEL32!TlsSetValue` at `0x14003ec99`
- `KERNEL32!TlsSetValue` at `0x14003ec99`
- `SHLWAPI!__imp_SHCreateThread` at `0x14003eec3`
- `SHLWAPI!__imp_SHCreateThread` at `0x14003eec3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLanguagePackInstallerSingleton::InstallLanguage(
        CLanguagePackInstallerSingleton *this,
        struct ILanguagePackInstaller *a2,
        const unsigned __int16 *a3,
        int a4,
        bool a5)
{
  char v7; // r14
  __int64 *Value; // rax
  __int64 *p_TlsValue; // rdi
  PVOID *v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // rdx
  int v13; // ebx
  unsigned int v14; // edx
  char *v15; // r14
  __int64 v16; // rcx
  STRSAFE_LPWSTR *v17; // r12
  unsigned __int64 v18; // r15
  unsigned __int64 v19; // rsi
  _OWORD *v20; // rax
  __int64 v21; // rsi
  const wchar_t *v22; // r12
  signed int LastError; // eax
  __int64 v24; // rdx
  _QWORD *v25; // rdx
  unsigned int v26; // edx
  __int64 v27; // rsi
  __int64 v29; // [rsp+28h] [rbp-38h]
  __int64 TlsValue; // [rsp+30h] [rbp-30h] BYREF
  _OWORD *v31; // [rsp+38h] [rbp-28h] BYREF
  LANGUAGE_PACK_INSTALLATION *v32; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v33; // [rsp+48h] [rbp-18h]
  char *v34; // [rsp+50h] [rbp-10h] BYREF
  DWORD v36; // [rsp+B0h] [rbp+50h] BYREF
  int v37; // [rsp+B8h] [rbp+58h]

  v37 = a4;
  v7 = (char)this;
  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  v36 = -1;
  TlsValue = 0;
  if ( Value )
  {
    v33 = Value;
  }
  else
  {
    p_TlsValue = &TlsValue;
    v36 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
    v33 = &TlsValue;
  }
  ++*(_DWORD *)p_TlsValue;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v11 = 5 * *(_DWORD *)p_TlsValue;
    if ( v11 > 0x1E1 )
      v12 = 0;
    else
      v12 = 479LL - v11;
    WPP_SF_sqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
      (unsigned int)&asc_140089BC0[v12],
      v7,
      (__int64)a3);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v15 = (char *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    v34 = v15;
    if ( v15 )
    {
      *(_OWORD *)v15 = 0;
      *((_OWORD *)v15 + 1) = 0;
      *((_QWORD *)v15 + 4) = 0;
      *(_QWORD *)v15 = 0;
      *((_QWORD *)v15 + 1) = 0;
      *((_QWORD *)v15 + 2) = 0;
      *((_QWORD *)v15 + 3) = 0;
    }
    else
    {
      v15 = 0;
    }
    v32 = (LANGUAGE_PACK_INSTALLATION *)v15;
    if ( !v15 )
    {
      v13 = -2147024882;
LABEL_45:
      std::unique_ptr<LANGUAGE_PACK_INSTALLATION>::~unique_ptr<LANGUAGE_PACK_INSTALLATION>(&v32, v14);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v7 = (char)this;
      goto LABEL_46;
    }
    if ( *(struct ILanguagePackInstaller **)v15 != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(struct ILanguagePackInstaller *))(*(_QWORD *)a2 + 8LL))(a2);
      v16 = *(_QWORD *)v15;
      *(_QWORD *)v15 = a2;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    *((_DWORD *)v15 + 8) = 1;
    v17 = (STRSAFE_LPWSTR *)(v15 + 8);
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( a3[v19] );
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
            (__int64)(v15 + 8),
            v19);
    if ( v13 < 0 )
      goto LABEL_45;
    StringCchCopyNW(*v17, v19 + 1, a3, v19);
    *((_QWORD *)v15 + 2) = v19;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v34 = (char *)this + 104;
    v20 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    v21 = (__int64)v20;
    v31 = v20;
    if ( v20 )
    {
      *v20 = 0;
      v20[1] = 0;
      *(_QWORD *)v20 = 0;
      *((_QWORD *)v20 + 1) = 0;
      *((_QWORD *)v20 + 2) = 0;
    }
    else
    {
      v21 = 0;
    }
    v31 = (_OWORD *)v21;
    if ( !v21 )
    {
      v13 = -2147024882;
LABEL_44:
      std::unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>::~unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>(&v31);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v34);
      goto LABEL_45;
    }
    *(_DWORD *)(v21 + 24) = v37;
    *(_BYTE *)(v21 + 28) = a5;
    v22 = *v17;
    if ( v22 )
    {
      do
        ++v18;
      while ( v22[v18] );
      v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              v21,
              v18);
      if ( v13 < 0 )
        goto LABEL_44;
      StringCchCopyNW(*(STRSAFE_LPWSTR *)v21, v18 + 1, v22, v18);
      *(_QWORD *)(v21 + 8) = v18;
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v21);
    }
    v31 = 0;
    if ( SHCreateThread(
           (LPTHREAD_START_ROUTINE)CLanguagePackInstallerSingleton::s_LanguagePackInstallThread,
           (void *)v21,
           4u,
           0) )
    {
      goto LABEL_40;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 >= 0 )
    {
LABEL_40:
      v32 = 0;
      v13 = 0;
      v24 = *((_QWORD *)this + 19);
      if ( v24 != *((_QWORD *)this + 21)
        || (v13 = CTSimpleArray<LANGUAGE_PACK_INSTALLATION *,4294967294,CTPolicyCoTaskMem<LANGUAGE_PACK_INSTALLATION *>,CSimpleArrayStandardCompareHelper<LANGUAGE_PACK_INSTALLATION *>,CSimpleArrayStandardMergeHelper<LANGUAGE_PACK_INSTALLATION *>>::_EnsureCapacity(
                    (char *)this + 144,
                    v24 + 1),
            v13 >= 0) )
      {
        v25 = (_QWORD *)(*((_QWORD *)this + 18) + 8 * (*((_QWORD *)this + 19))++);
        if ( v25 )
          *v25 = v15;
      }
    }
    goto LABEL_44;
  }
  v13 = -2147467261;
LABEL_46:
  if ( v10 != &WPP_GLOBAL_Control && *((char *)v10 + 28) < 0 )
  {
    v26 = 5 * *(_DWORD *)p_TlsValue;
    if ( v26 > 0x1E1 )
      v27 = 0;
    else
      v27 = 479LL - v26;
    LODWORD(v29) = v13;
    WPP_SF_sqd(
      (unsigned int)v10[2],
      27,
      (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
      (unsigned int)&asc_140089BC0[v27],
      v7,
      v29,
      TlsValue,
      v31,
      v32,
      v33,
      v34);
  }
  if ( p_TlsValue )
    --*(_DWORD *)p_TlsValue;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v36);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14003ec3c  mov     [rsp-38h+arg_8], rbx
0x14003ec41  mov     [rsp-38h+arg_18], r9d
0x14003ec46  mov     [rsp-38h+arg_0], rcx
0x14003ec4b  push    rbp
0x14003ec4c  push    rsi
0x14003ec4d  push    rdi
0x14003ec4e  push    r12
0x14003ec50  push    r13
0x14003ec52  push    r14
0x14003ec54  push    r15
0x14003ec56  mov     rbp, rsp
0x14003ec59  sub     rsp, 60h
0x14003ec5d  mov     r13, r8
0x14003ec60  mov     rbx, rdx
0x14003ec63  mov     r14, rcx
0x14003ec66  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14003ec6c  call    cs:__imp_TlsGetValue
0x14003ec72  mov     rdi, rax
0x14003ec75  mov     [rbp+arg_10], 0FFFFFFFFh
0x14003ec7c  xor     r15d, r15d
0x14003ec7f  mov     [rbp+TlsValue], r15
0x14003ec83  test    rax, rax
0x14003ec86  jnz     short loc_14003ECA5
0x14003ec88  lea     rdi, [rbp+TlsValue]
0x14003ec8c  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14003ec92  mov     [rbp+arg_10], ecx
0x14003ec95  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x14003ec99  call    cs:__imp_TlsSetValue
0x14003ec9f  mov     [rbp+var_18], rdi
0x14003eca3  jmp     short loc_14003ECA9
0x14003eca5  mov     [rbp+var_18], rax
0x14003eca9  inc     dword ptr [rdi]
0x14003ecab  lea     r12, WPP_GLOBAL_Control
0x14003ecb2  mov     esi, 1DFh
0x14003ecb7  lea     r8, asc_140089BC0; "                                       "...
0x14003ecbe  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ecc5  cmp     rcx, r12
0x14003ecc8  jz      short loc_14003ED13
0x14003ecca  test    byte ptr [rcx+1Ch], 80h
0x14003ecce  jz      short loc_14003ED13
0x14003ecd0  mov     eax, [rdi]
0x14003ecd2  lea     edx, [rax+rax*4]
0x14003ecd5  cmp     edx, 1E1h
0x14003ecdb  ja      short loc_14003ECE6
0x14003ecdd  mov     eax, edx
0x14003ecdf  mov     edx, esi
0x14003ece1  sub     rdx, rax
0x14003ece4  jmp     short loc_14003ECE9
0x14003ece6  mov     rdx, r15
0x14003ece9  lea     r9, [rdx+r8]
0x14003eced  mov     edx, 1Ah
0x14003ecf2  mov     [rsp+60h+var_38], r13
0x14003ecf7  mov     [rsp+60h+var_40], r14
0x14003ecfc  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x14003ed03  mov     rcx, [rcx+10h]
0x14003ed07  call    WPP_SF_sqS
0x14003ed0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed13  test    r13, r13
0x14003ed16  jnz     short loc_14003ED22
0x14003ed18  mov     ebx, 80004003h
0x14003ed1d  jmp     loc_14003EF61
0x14003ed22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003ed29  mov     ecx, 28h ; '('; unsigned __int64
0x14003ed2e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003ed33  mov     r14, rax
0x14003ed36  mov     [rbp+var_10], rax
0x14003ed3a  test    rax, rax
0x14003ed3d  jz      short loc_14003ED62
0x14003ed3f  xorps   xmm0, xmm0
0x14003ed42  xor     eax, eax
0x14003ed44  movups  xmmword ptr [r14], xmm0
0x14003ed48  movups  xmmword ptr [r14+10h], xmm0
0x14003ed4d  mov     [r14+20h], rax
0x14003ed51  mov     [r14], r15
0x14003ed54  mov     [r14+8], r15
0x14003ed58  mov     [r14+10h], r15
0x14003ed5c  mov     [r14+18h], r15
0x14003ed60  jmp     short loc_14003ED65
0x14003ed62  mov     r14, r15
0x14003ed65  mov     [rbp+var_20], r14
0x14003ed69  test    r14, r14
0x14003ed6c  jnz     short loc_14003ED78
0x14003ed6e  mov     ebx, 8007000Eh
0x14003ed73  jmp     loc_14003EF4D
0x14003ed78  cmp     [r14], rbx
0x14003ed7b  jz      short loc_14003EDAA
0x14003ed7d  test    rbx, rbx
0x14003ed80  jz      short loc_14003ED92
0x14003ed82  mov     rax, [rbx]
0x14003ed85  mov     rcx, rbx
0x14003ed88  mov     rax, [rax+8]
0x14003ed8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ed91  nop
0x14003ed92  mov     rcx, [r14]
0x14003ed95  mov     [r14], rbx
0x14003ed98  test    rcx, rcx
0x14003ed9b  jz      short loc_14003EDAA
0x14003ed9d  mov     rax, [rcx]
0x14003eda0  mov     rax, [rax+10h]
0x14003eda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eda9  nop
0x14003edaa  mov     dword ptr [r14+20h], 1
0x14003edb2  lea     r12, [r14+8]
0x14003edb6  or      r15, 0FFFFFFFFFFFFFFFFh
0x14003edba  mov     rsi, r15
0x14003edbd  xor     eax, eax
0x14003edbf  inc     rsi
0x14003edc2  cmp     [r13+rsi*2+0], ax
0x14003edc8  jnz     short loc_14003EDBF
0x14003edca  mov     rdx, rsi
0x14003edcd  mov     rcx, r12
0x14003edd0  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14003edd5  mov     ebx, eax
0x14003edd7  test    eax, eax
0x14003edd9  js      loc_14003EF3E
0x14003eddf  lea     rdx, [rsi+1]; cchDest
0x14003ede3  mov     r9, rsi; cchToCopy
0x14003ede6  mov     r8, r13; pszSrc
0x14003ede9  mov     rcx, [r12]; pszDest
0x14003eded  call    StringCchCopyNW
0x14003edf2  mov     [r12+8], rsi
0x14003edf7  mov     r13, [rbp+arg_0]
0x14003edfb  lea     rbx, [r13+68h]
0x14003edff  mov     rcx, rbx; lpCriticalSection
0x14003ee02  call    cs:__imp_EnterCriticalSection
0x14003ee08  mov     [rbp+var_10], rbx
0x14003ee0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003ee13  mov     ecx, 20h ; ' '; unsigned __int64
0x14003ee18  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003ee1d  mov     rsi, rax
0x14003ee20  mov     [rbp+var_28], rax
0x14003ee24  xor     ecx, ecx
0x14003ee26  test    rax, rax
0x14003ee29  jz      short loc_14003EE42
0x14003ee2b  xorps   xmm0, xmm0
0x14003ee2e  movups  xmmword ptr [rax], xmm0
0x14003ee31  movups  xmmword ptr [rax+10h], xmm0
0x14003ee35  mov     [rax], rcx
0x14003ee38  mov     [rax+8], rcx
0x14003ee3c  mov     [rax+10h], rcx
0x14003ee40  jmp     short loc_14003EE45
0x14003ee42  mov     rsi, rcx
0x14003ee45  mov     [rbp+var_28], rsi
0x14003ee49  test    rsi, rsi
0x14003ee4c  jnz     short loc_14003EE5B
0x14003ee4e  mov     ebx, 8007000Eh
0x14003ee53  xor     r15d, r15d
0x14003ee56  jmp     loc_14003EF29
0x14003ee5b  mov     eax, [rbp+arg_18]
0x14003ee5e  mov     [rsi+18h], eax
0x14003ee61  mov     al, [rbp+arg_20]
0x14003ee64  mov     [rsi+1Ch], al
0x14003ee67  mov     r12, [r12]
0x14003ee6b  test    r12, r12
0x14003ee6e  jz      short loc_14003EEA3
0x14003ee70  inc     r15
0x14003ee73  cmp     [r12+r15*2], cx
0x14003ee78  jnz     short loc_14003EE70
0x14003ee7a  mov     rdx, r15
0x14003ee7d  mov     rcx, rsi
0x14003ee80  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14003ee85  mov     ebx, eax
0x14003ee87  test    eax, eax
0x14003ee89  js      short loc_14003EE53
0x14003ee8b  lea     rdx, [r15+1]; cchDest
0x14003ee8f  mov     r9, r15; cchToCopy
0x14003ee92  mov     r8, r12; pszSrc
0x14003ee95  mov     rcx, [rsi]; pszDest
0x14003ee98  call    StringCchCopyNW
0x14003ee9d  mov     [rsi+8], r15
0x14003eea1  jmp     short loc_14003EEAB
0x14003eea3  mov     rcx, rsi
0x14003eea6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14003eeab  xor     r15d, r15d
0x14003eeae  mov     [rbp+var_28], r15
0x14003eeb2  xor     r9d, r9d; pfnCallback
0x14003eeb5  lea     r8d, [r15+4]; flags
0x14003eeb9  mov     rdx, rsi; pData
0x14003eebc  lea     rcx, ?s_LanguagePackInstallThread@CLanguagePackInstallerSingleton@@SAKPEAX@Z; pfnThreadProc
0x14003eec3  call    cs:__imp_SHCreateThread
0x14003eec9  test    eax, eax
0x14003eecb  jnz     short loc_14003EEE6
0x14003eecd  call    cs:__imp_GetLastError
0x14003eed3  mov     ebx, eax
0x14003eed5  test    eax, eax
0x14003eed7  jle     short loc_14003EEE2
0x14003eed9  movzx   ebx, ax
0x14003eedc  or      ebx, 80070000h
0x14003eee2  test    ebx, ebx
0x14003eee4  js      short loc_14003EF29
0x14003eee6  lea     rsi, [r13+90h]
0x14003eeed  mov     [rbp+var_20], r15
0x14003eef1  mov     ebx, r15d
0x14003eef4  mov     rdx, [rsi+8]
0x14003eef8  cmp     rdx, [rsi+18h]
0x14003eefc  jnz     short loc_14003EF0F
0x14003eefe  inc     rdx
0x14003ef01  mov     rcx, rsi
0x14003ef04  call    ?_EnsureCapacity@?$CTSimpleArray@PEAULANGUAGE_PACK_INSTALLATION@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAULANGUAGE_PACK_INSTALLATION@@@@V?$CSimpleArrayStandardCompareHelper@PEAULANGUAGE_PACK_INSTALLATION@@@@V?$CSimpleArrayStandardMergeHelper@PEAULANGUAGE_PACK_INSTALLATION@@@@@@QEAAJ_K0@Z; CTSimpleArray<LANGUAGE_PACK_INSTALLATION *,4294967294,CTPolicyCoTaskMem<LANGUAGE_PACK_INSTALLATION *>,CSimpleArrayStandardCompareHelper<LANGUAGE_PACK_INSTALLATION *>,CSimpleArrayStandardMergeHelper<LANGUAGE_PACK_INSTALLATION *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x14003ef09  mov     ebx, eax
0x14003ef0b  test    eax, eax
0x14003ef0d  js      short loc_14003EF29
0x14003ef0f  inc     qword ptr [rsi+8]
0x14003ef13  mov     rdx, [rsi+8]
0x14003ef17  mov     rax, [rsi]
0x14003ef1a  dec     rdx
0x14003ef1d  lea     rdx, [rax+rdx*8]
0x14003ef21  test    rdx, rdx
0x14003ef24  jz      short loc_14003EF29
0x14003ef26  mov     [rdx], r14
0x14003ef29  lea     rcx, [rbp+var_28]
0x14003ef2d  call    ??1?$unique_ptr@ULANGUAGE_PACK_INSTALL_PARAMETERS@@U?$default_delete@ULANGUAGE_PACK_INSTALL_PARAMETERS@@@std@@@std@@QEAA@XZ; std::unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>::~unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>(void)
0x14003ef32  nop
0x14003ef33  lea     rcx, [rbp+var_10]; this
0x14003ef37  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x14003ef3c  jmp     short loc_14003EF41
0x14003ef3e  xor     r15d, r15d
0x14003ef41  lea     r12, WPP_GLOBAL_Control
0x14003ef48  mov     esi, 1DFh
0x14003ef4d  lea     rcx, [rbp+var_20]
0x14003ef51  call    ??1?$unique_ptr@ULANGUAGE_PACK_INSTALLATION@@U?$default_delete@ULANGUAGE_PACK_INSTALLATION@@@std@@@std@@QEAA@XZ; std::unique_ptr<LANGUAGE_PACK_INSTALLATION>::~unique_ptr<LANGUAGE_PACK_INSTALLATION>(void)
0x14003ef56  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ef5d  mov     r14, [rbp+arg_0]
0x14003ef61  cmp     rcx, r12
0x14003ef64  jz      short loc_14003EFAC
0x14003ef66  test    byte ptr [rcx+1Ch], 80h
0x14003ef6a  jz      short loc_14003EFAC
0x14003ef6c  mov     eax, [rdi]
0x14003ef6e  lea     edx, [rax+rax*4]
0x14003ef71  cmp     edx, 1E1h
0x14003ef77  ja      short loc_14003EF80
0x14003ef79  mov     eax, edx
0x14003ef7b  sub     rsi, rax
0x14003ef7e  jmp     short loc_14003EF83
0x14003ef80  mov     rsi, r15
0x14003ef83  lea     r9, asc_140089BC0; "                                       "...
0x14003ef8a  add     r9, rsi
0x14003ef8d  mov     edx, 1Bh
0x14003ef92  mov     dword ptr [rsp+60h+var_38], ebx
0x14003ef96  mov     [rsp+60h+var_40], r14
0x14003ef9b  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x14003efa2  mov     rcx, [rcx+10h]
0x14003efa6  call    WPP_SF_sqd
0x14003efab  nop
0x14003efac  test    rdi, rdi
0x14003efaf  jz      short loc_14003EFB3
0x14003efb1  dec     dword ptr [rdi]
0x14003efb3  lea     rcx, [rbp+arg_10]
0x14003efb7  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x14003efbc  mov     eax, ebx
0x14003efbe  mov     rbx, [rsp+60h+arg_8]
0x14003efc6  add     rsp, 60h
0x14003efca  pop     r15
0x14003efcc  pop     r14
0x14003efce  pop     r13
0x14003efd0  pop     r12
0x14003efd2  pop     rdi
0x14003efd3  pop     rsi
0x14003efd4  pop     rbp
0x14003efd5  retn
```
