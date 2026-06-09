# SecurityManager::PersistVTpmNvState(uchar *,uint)

- ea: `0x140273cd0`
- end: `0x14027418b`
- name: `?PersistVTpmNvState@SecurityManager@@UEAAJPEAEI@Z`
- size: `1211`
- prototype: `__int64 __fastcall(SecurityManager *this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140054508`
- `0x140054630`
- `0x14005e684`
- `0x14005e7e4`
- `0x1400b42b0`
- `0x1400c17f4`
- `0x140132940`
- `0x14013606c`
- `0x140273cd0`
- `0x1402749ac`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140273d23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140273d23`

## string_xrefs

- `0x140273e56`: `/configuration/security/keys/lkg_key_protector`
- `0x140273de0`: `/configuration/security/keys/key_protector`
- `0x140273ece`: `/configuration/security/policy/security_policy`
- `0x140273fab`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x14027407a`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x140273f44`: `/configuration/security/policy/lkg_security_policy`
- `0x140273d8e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273e04`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273e7a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273ef2`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273f68`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273fcf`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274032`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027409e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402740ed`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274158`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SecurityManager::PersistVTpmNvState(SecurityManager *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v3; // r14
  char *v6; // rbx
  void **v7; // rax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-98h]
  char *v28; // [rsp+30h] [rbp-88h] BYREF
  char *v29[2]; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-70h]
  void *v31[3]; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int8 v32[16]; // [rsp+68h] [rbp-50h] BYREF
  __int128 v33; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v3 = a3;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  if ( !a2 || !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D9,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
  v6 = (char *)this + 384;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  try
  {
    v28 = v6;
    v7 = std::vector<unsigned char>::vector<unsigned char>(v31, a2, &a2[v3]);
    std::vector<unsigned char>::operator=((char *)this + 296, v7);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v31);
    *(_OWORD *)v29 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v29, *((_QWORD *)this + 2), 1);
    v8 = (unsigned int)v29[1];
    if ( SLODWORD(v29[1]) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E3,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)LODWORD(v29[1]),
        v27);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v8;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/keys/key_protector",
            *((_QWORD *)this + 28),
            (unsigned int)(*((_DWORD *)this + 58) - *((_DWORD *)this + 56)));
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F2,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v11,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v12;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 2) + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/keys/lkg_key_protector",
            *((_QWORD *)this + 28));
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F7,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v13,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v14;
    }
    if ( *((_QWORD *)this + 35) != *((_QWORD *)this + 34) )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 2) + 144LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/policy/security_policy");
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5FE,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)(unsigned int)v15,
          0);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        return v16;
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 2) + 144LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/policy/lkg_security_policy",
              *((_QWORD *)this + 34));
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x602,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)(unsigned int)v17,
          0);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        return v18;
      }
    }
    v19 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int8 *, _QWORD))(**((_QWORD **)this + 2)
                                                                                                 + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/vtpm/vtpm_engine_nvram",
            a2,
            (unsigned int)v3);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x608,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v19,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v20;
    }
    if ( *((_DWORD *)this + 94) < 0x802u )
      goto LABEL_22;
    v21 = SecurityManager::Sha256HashData((SecurityManager *)((char *)this - 24), a2, v3, v32);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60C,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v21,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      return v22;
    }
    v23 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int8 *, __int64))(**((_QWORD **)this + 2)
                                                                                                  + 144LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/vtpm/vtpm_engine_nvram_hash",
            v32,
            32);
    v24 = v23;
    if ( v23 >= 0 )
    {
LABEL_22:
      v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2));
      v26 = v25;
      if ( v25 >= 0 )
      {
        *((_BYTE *)this + 195) = 1;
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x612,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)(unsigned int)v25,
          0);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
        result = v26;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60F,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v23,
        0);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v29);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
      result = v24;
    }
  }
  catch ( ... )
  {
    v30 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x618,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            v9);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
    return v30;
  }
  return result;
}

```

## disassembly

```asm
0x140273cd0  push    rbx
0x140273cd2  push    rsi
0x140273cd3  push    rdi
0x140273cd4  push    r14
0x140273cd6  push    r15
0x140273cd8  sub     rsp, 90h
0x140273cdf  mov     rax, cs:__security_cookie
0x140273ce6  xor     rax, rsp
0x140273ce9  mov     [rsp+0B8h+var_30], rax
0x140273cf1  mov     r14d, r8d
0x140273cf4  mov     rsi, rdx
0x140273cf7  mov     rdi, rcx
0x140273cfa  xorps   xmm0, xmm0
0x140273cfd  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x140273d02  movups  [rsp+0B8h+var_40], xmm0
0x140273d07  test    rdx, rdx
0x140273d0a  jz      loc_140274148
0x140273d10  test    r8d, r8d
0x140273d13  jz      loc_140274148
0x140273d19  lea     rbx, [rcx+180h]
0x140273d20  mov     rcx, rbx; lpCriticalSection
0x140273d23  call    cs:__imp_EnterCriticalSection
0x140273d2a  nop     dword ptr [rax+rax+00h]
0x140273d2f  mov     [rsp+0B8h+var_88], rbx
0x140273d34  lea     r8, [rsi+r14]
0x140273d38  mov     rdx, rsi
0x140273d3b  lea     rcx, [rsp+0B8h+var_68]
0x140273d40  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x140273d45  lea     rcx, [rdi+128h]
0x140273d4c  mov     rdx, rax
0x140273d4f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140273d54  lea     rcx, [rsp+0B8h+var_68]
0x140273d59  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273d5e  xorps   xmm0, xmm0
0x140273d61  movups  xmmword ptr [rsp+0B8h+var_80], xmm0
0x140273d66  mov     r8d, 1
0x140273d6c  mov     rdx, [rdi+10h]
0x140273d70  lea     rcx, [rsp+0B8h+var_80]
0x140273d75  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140273d7a  nop
0x140273d7b  mov     ebx, dword ptr [rsp+0B8h+var_80+8]
0x140273d7f  test    ebx, ebx
0x140273d81  jns     short loc_140273DBC
0x140273d83  mov     rcx, [rsp+0B8h]; this
0x140273d8b  mov     r9d, ebx; char *
0x140273d8e  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273d95  mov     edx, 5E3h; void *
0x140273d9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273d9f  nop
0x140273da0  lea     rcx, [rsp+0B8h+var_80]; this
0x140273da5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273daa  nop
0x140273dab  lea     rcx, [rsp+0B8h+var_88]
0x140273db0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273db5  mov     eax, ebx
0x140273db7  jmp     loc_14027416B
0x140273dbc  mov     rcx, [rdi+10h]
0x140273dc0  mov     rax, [rcx]
0x140273dc3  mov     r9d, [rdi+0E8h]
0x140273dca  sub     r9d, [rdi+0E0h]
0x140273dd1  mov     [rsp+0B8h+var_98], 0; int
0x140273dd9  mov     r8, [rdi+0E0h]
0x140273de0  lea     rdx, ?SECURITY_SETTING_KEY_PROTECTOR@@3QBGB; "/configuration/security/keys/key_protec"...
0x140273de7  mov     rax, [rax+90h]
0x140273dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273df3  mov     ebx, eax
0x140273df5  test    eax, eax
0x140273df7  jns     short loc_140273E32
0x140273df9  mov     rcx, [rsp+0B8h]; this
0x140273e01  mov     r9d, eax; char *
0x140273e04  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273e0b  mov     edx, 5F2h; void *
0x140273e10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273e15  nop
0x140273e16  lea     rcx, [rsp+0B8h+var_80]; this
0x140273e1b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273e20  nop
0x140273e21  lea     rcx, [rsp+0B8h+var_88]
0x140273e26  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273e2b  mov     eax, ebx
0x140273e2d  jmp     loc_14027416B
0x140273e32  mov     rcx, [rdi+10h]
0x140273e36  mov     rax, [rcx]
0x140273e39  mov     r9d, [rdi+0E8h]
0x140273e40  sub     r9d, [rdi+0E0h]
0x140273e47  mov     [rsp+0B8h+var_98], 0; int
0x140273e4f  mov     r8, [rdi+0E0h]
0x140273e56  lea     rdx, ?SECURITY_SETTING_LKG_KEY_PROTECTOR@@3QBGB; "/configuration/security/keys/lkg_key_pr"...
0x140273e5d  mov     rax, [rax+90h]
0x140273e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273e69  mov     ebx, eax
0x140273e6b  test    eax, eax
0x140273e6d  jns     short loc_140273EA8
0x140273e6f  mov     rcx, [rsp+0B8h]; this
0x140273e77  mov     r9d, eax; char *
0x140273e7a  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273e81  mov     edx, 5F7h; void *
0x140273e86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273e8b  nop
0x140273e8c  lea     rcx, [rsp+0B8h+var_80]; this
0x140273e91  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273e96  nop
0x140273e97  lea     rcx, [rsp+0B8h+var_88]
0x140273e9c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273ea1  mov     eax, ebx
0x140273ea3  jmp     loc_14027416B
0x140273ea8  mov     r8, [rdi+110h]
0x140273eaf  mov     r9, [rdi+118h]
0x140273eb6  sub     r9, r8
0x140273eb9  jz      loc_140273F96
0x140273ebf  mov     rcx, [rdi+10h]
0x140273ec3  mov     rax, [rcx]
0x140273ec6  mov     [rsp+0B8h+var_98], 0; int
0x140273ece  lea     rdx, ?SECURITY_SETTING_POLICY@@3QBGB; "/configuration/security/policy/security"...
0x140273ed5  mov     rax, [rax+90h]
0x140273edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273ee1  mov     ebx, eax
0x140273ee3  test    eax, eax
0x140273ee5  jns     short loc_140273F20
0x140273ee7  mov     rcx, [rsp+0B8h]; this
0x140273eef  mov     r9d, eax; char *
0x140273ef2  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273ef9  mov     edx, 5FEh; void *
0x140273efe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273f03  nop
0x140273f04  lea     rcx, [rsp+0B8h+var_80]; this
0x140273f09  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273f0e  nop
0x140273f0f  lea     rcx, [rsp+0B8h+var_88]
0x140273f14  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273f19  mov     eax, ebx
0x140273f1b  jmp     loc_14027416B
0x140273f20  mov     rcx, [rdi+10h]
0x140273f24  mov     rax, [rcx]
0x140273f27  mov     r9d, [rdi+118h]
0x140273f2e  sub     r9d, [rdi+110h]
0x140273f35  mov     [rsp+0B8h+var_98], 0; int
0x140273f3d  mov     r8, [rdi+110h]
0x140273f44  lea     rdx, ?SECURITY_SETTING_LKG_POLICY@@3QBGB; "/configuration/security/policy/lkg_secu"...
0x140273f4b  mov     rax, [rax+90h]
0x140273f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273f57  mov     ebx, eax
0x140273f59  test    eax, eax
0x140273f5b  jns     short loc_140273F96
0x140273f5d  mov     rcx, [rsp+0B8h]; this
0x140273f65  mov     r9d, eax; char *
0x140273f68  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273f6f  mov     edx, 602h; void *
0x140273f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273f79  nop
0x140273f7a  lea     rcx, [rsp+0B8h+var_80]; this
0x140273f7f  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273f84  nop
0x140273f85  lea     rcx, [rsp+0B8h+var_88]
0x140273f8a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273f8f  mov     eax, ebx
0x140273f91  jmp     loc_14027416B
0x140273f96  mov     rcx, [rdi+10h]
0x140273f9a  mov     rax, [rcx]
0x140273f9d  mov     [rsp+0B8h+var_98], 0; int
0x140273fa5  mov     r9d, r14d
0x140273fa8  mov     r8, rsi
0x140273fab  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x140273fb2  mov     rax, [rax+90h]
0x140273fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140273fbe  mov     ebx, eax
0x140273fc0  test    eax, eax
0x140273fc2  jns     short loc_140273FFD
0x140273fc4  mov     rcx, [rsp+0B8h]; this
0x140273fcc  mov     r9d, eax; char *
0x140273fcf  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273fd6  mov     edx, 608h; void *
0x140273fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140273fe0  nop
0x140273fe1  lea     rcx, [rsp+0B8h+var_80]; this
0x140273fe6  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273feb  nop
0x140273fec  lea     rcx, [rsp+0B8h+var_88]
0x140273ff1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140273ff6  mov     eax, ebx
0x140273ff8  jmp     loc_14027416B
0x140273ffd  cmp     dword ptr [rdi+178h], 802h
0x140274007  jb      loc_1402740CC
0x14027400d  lea     r9, [rsp+0B8h+var_50]; unsigned __int8 *
0x140274012  mov     r8d, r14d; unsigned int
0x140274015  mov     rdx, rsi; unsigned __int8 *
0x140274018  lea     rcx, [rdi-18h]; this
0x14027401c  call    ?Sha256HashData@SecurityManager@@AEAAJPEAEIQEAE@Z; SecurityManager::Sha256HashData(uchar *,uint,uchar * const)
0x140274021  mov     ebx, eax
0x140274023  test    eax, eax
0x140274025  jns     short loc_140274060
0x140274027  mov     rcx, [rsp+0B8h]; this
0x14027402f  mov     r9d, eax; char *
0x140274032  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274039  mov     edx, 60Ch; void *
0x14027403e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274043  nop
0x140274044  lea     rcx, [rsp+0B8h+var_80]; this
0x140274049  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x14027404e  nop
0x14027404f  lea     rcx, [rsp+0B8h+var_88]
0x140274054  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274059  mov     eax, ebx
0x14027405b  jmp     loc_14027416B
0x140274060  mov     rcx, [rdi+10h]
0x140274064  mov     rax, [rcx]
0x140274067  mov     [rsp+0B8h+var_98], 0; int
0x14027406f  mov     r9d, 20h ; ' '
0x140274075  lea     r8, [rsp+0B8h+var_50]
0x14027407a  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM_HASH@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x140274081  mov     rax, [rax+90h]
0x140274088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027408d  mov     ebx, eax
0x14027408f  test    eax, eax
0x140274091  jns     short loc_1402740CC
0x140274093  mov     rcx, [rsp+0B8h]; this
0x14027409b  mov     r9d, eax; char *
0x14027409e  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402740a5  mov     edx, 60Fh; void *
0x1402740aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402740af  nop
0x1402740b0  lea     rcx, [rsp+0B8h+var_80]; this
0x1402740b5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1402740ba  nop
0x1402740bb  lea     rcx, [rsp+0B8h+var_88]
0x1402740c0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1402740c5  mov     eax, ebx
0x1402740c7  jmp     loc_14027416B
0x1402740cc  mov     rcx, [rdi+10h]
0x1402740d0  mov     rax, [rcx]
0x1402740d3  mov     rax, [rax+38h]
0x1402740d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402740dc  mov     ebx, eax
0x1402740de  test    eax, eax
0x1402740e0  jns     short loc_140274118
0x1402740e2  mov     rcx, [rsp+0B8h]; this
0x1402740ea  mov     r9d, eax; char *
0x1402740ed  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402740f4  mov     edx, 612h; void *
0x1402740f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402740fe  nop
0x1402740ff  lea     rcx, [rsp+0B8h+var_80]; this
0x140274104  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140274109  nop
0x14027410a  lea     rcx, [rsp+0B8h+var_88]
0x14027410f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274114  mov     eax, ebx
0x140274116  jmp     short loc_14027416B
0x140274118  mov     byte ptr [rdi+0C3h], 1
0x14027411f  lea     rcx, [rsp+0B8h+var_80]; this
0x140274124  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140274129  nop
0x14027412a  lea     rcx, [rsp+0B8h+var_88]
0x14027412f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274134  xor     eax, eax
0x140274136  jmp     short loc_14027416B
0x140274138  lea     rcx, [rsp+0B8h+var_88]
0x14027413d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140274142  mov     eax, [rsp+0B8h+var_70]
0x140274146  jmp     short loc_14027416B
0x140274148  mov     rcx, [rsp+0B8h]; this
0x140274150  mov     ebx, 80070057h
0x140274155  mov     r9d, ebx; char *
0x140274158  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027415f  mov     edx, 5D9h; void *
0x140274164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274169  mov     eax, ebx
0x14027416b  mov     rcx, [rsp+0B8h+var_30]
0x140274173  xor     rcx, rsp; StackCookie
0x140274176  call    __security_check_cookie
0x14027417b  add     rsp, 90h
0x140274182  pop     r15
0x140274184  pop     r14
0x140274186  pop     rdi
0x140274187  pop     rsi
0x140274188  pop     rbx
0x140274189  retn
```
