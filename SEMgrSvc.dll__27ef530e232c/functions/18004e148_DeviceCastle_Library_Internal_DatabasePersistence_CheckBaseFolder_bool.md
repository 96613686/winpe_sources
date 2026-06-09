# DeviceCastle::Library::Internal::DatabasePersistence::CheckBaseFolder(bool *)

- ea: `0x18004e148`
- end: `0x18004e379`
- name: `?CheckBaseFolder@DatabasePersistence@Internal@Library@DeviceCastle@@CAJPEA_N@Z`
- size: `561`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `4`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049efc`
- `0x18004de90`
- `0x18004e8c8`
- `0x18004ee7c`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180013014`
- `0x180013274`
- `0x18003c35c`
- `0x180045d34`
- `0x180047250`
- `0x18004736c`
- `0x180047564`
- `0x18004e148`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e32a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e32a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e310`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004e1a9`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18004e1a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeviceCastle::Library::Internal::DatabasePersistence::CheckBaseFolder(bool *a1)
{
  HRESULT v2; // ebx
  __int64 v3; // r8
  PWSTR v4; // r9
  unsigned __int64 v5; // rsi
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  void **v10; // rdi
  __int64 v11; // rdx
  void **v12; // rcx
  DeviceCastle::Library::DeviceCastleInternal *v13; // rax
  __int128 *v14; // rcx
  __int128 v15; // xmm2
  __int128 v16; // xmm3
  const unsigned __int16 *v17; // rcx
  PWSTR ppszPath; // [rsp+20h] [rbp-48h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+28h] [rbp-40h] BYREF
  char v21; // [rsp+30h] [rbp-38h]
  void *Src[2]; // [rsp+38h] [rbp-30h] BYREF
  __int128 v23; // [rsp+48h] [rbp-20h]

  if ( !*((_BYTE *)DeviceCastle::Library::Internal::g_pCastleInstance + 80) )
  {
    *(_OWORD *)Src = 0;
    *(_QWORD *)&v23 = 0;
    *((_QWORD *)&v23 + 1) = 7;
    LOWORD(Src[0]) = 0;
    ppszPath = 0;
    v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
    if ( v2 < 0 )
    {
      std::wstring::~wstring(Src);
      if ( ppszPath )
        CoTaskMemFree(ppszPath);
      return (unsigned int)v2;
    }
    v4 = ppszPath;
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( ppszPath[v6] );
    v7 = v6 + 24;
    v8 = *((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) < v7 )
    {
      v9 = v23;
      ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_K_Z___V___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(Src);
      *(_QWORD *)&v23 = v9;
      v4 = ppszPath;
      v8 = *((_QWORD *)&v23 + 1);
    }
    do
      ++v5;
    while ( v4[v5] );
    if ( v5 > v8 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        Src,
        v5,
        v3,
        v4);
    }
    else
    {
      v10 = Src;
      if ( v8 > 7 )
        v10 = (void **)Src[0];
      *(_QWORD *)&v23 = v5;
      memmove_0(v10, v4, 2 * v5);
      *((_WORD *)v10 + v5) = 0;
    }
    std::wstring::append(Src, L"\\Microsoft");
    std::wstring::append(Src, L"\\DeviceCastle");
    v11 = v23;
    v12 = Src;
    if ( (unsigned __int64)v23 >= *((_QWORD *)&v23 + 1) )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
    }
    else
    {
      *(_QWORD *)&v23 = v23 + 1;
      if ( *((_QWORD *)&v23 + 1) > 7u )
        v12 = (void **)Src[0];
      *(_DWORD *)((char *)v12 + 2 * v11) = 92;
    }
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)DeviceCastle::Library::Internal::g_pCastleInstance + 8);
    v21 = 0;
    ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
    v13 = DeviceCastle::Library::Internal::g_pCastleInstance;
    if ( !*((_BYTE *)DeviceCastle::Library::Internal::g_pCastleInstance + 80) )
    {
      v14 = (__int128 *)((char *)DeviceCastle::Library::Internal::g_pCastleInstance + 48);
      if ( (void **)((char *)DeviceCastle::Library::Internal::g_pCastleInstance + 48) != Src )
      {
        v15 = *v14;
        v16 = *((_OWORD *)DeviceCastle::Library::Internal::g_pCastleInstance + 4);
        *v14 = *(_OWORD *)Src;
        *((_OWORD *)v13 + 4) = v23;
        *(_OWORD *)Src = v15;
        v23 = v16;
      }
      *((_BYTE *)v13 + 80) = 1;
    }
    if ( v21 )
      LeaveCriticalSection(lpCriticalSection);
    std::wstring::~wstring(Src);
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
  }
  if ( !a1 )
    return 0;
  v17 = (const unsigned __int16 *)((char *)DeviceCastle::Library::Internal::g_pCastleInstance + 48);
  if ( *((_QWORD *)DeviceCastle::Library::Internal::g_pCastleInstance + 9) > 7u )
    v17 = *(const unsigned __int16 **)v17;
  v2 = DeviceCastle::Library::Internal::Utilities::CheckFolderExistence(v17);
  if ( v2 >= 0 )
  {
    *a1 = v2 == 0;
    return 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18004e148  push    rbp
0x18004e14a  push    rbx
0x18004e14b  push    rsi
0x18004e14c  push    rdi
0x18004e14d  push    r14
0x18004e14f  push    r15
0x18004e151  mov     rbp, rsp
0x18004e154  sub     rsp, 68h
0x18004e158  mov     rax, cs:__security_cookie
0x18004e15f  xor     rax, rsp
0x18004e162  mov     [rbp+var_10], rax
0x18004e166  mov     r14, rcx
0x18004e169  xor     r15d, r15d
0x18004e16c  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x18004e173  cmp     [rax+50h], r15b
0x18004e177  jnz     loc_18004E330
0x18004e17d  xorps   xmm0, xmm0
0x18004e180  movups  xmmword ptr [rbp+Src], xmm0
0x18004e184  mov     qword ptr [rbp+var_20], r15
0x18004e188  mov     qword ptr [rbp+var_20+8], 7
0x18004e190  mov     word ptr [rbp+Src], r15w
0x18004e195  mov     [rbp+ppszPath], r15
0x18004e199  lea     r9, [rbp+ppszPath]; ppszPath
0x18004e19d  xor     r8d, r8d; hToken
0x18004e1a0  xor     edx, edx; dwFlags
0x18004e1a2  lea     rcx, FOLDERID_LocalAppData; rfid
0x18004e1a9  call    cs:__imp_SHGetKnownFolderPath
0x18004e1af  mov     ebx, eax
0x18004e1b1  test    eax, eax
0x18004e1b3  jns     short loc_18004E1D7
0x18004e1b5  lea     rcx, [rbp+Src]
0x18004e1b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e1be  nop
0x18004e1bf  mov     rcx, [rbp+ppszPath]; pv
0x18004e1c3  test    rcx, rcx
0x18004e1c6  jz      loc_18004E35E
0x18004e1cc  call    cs:__imp_CoTaskMemFree
0x18004e1d2  jmp     loc_18004E35E
0x18004e1d7  mov     r9, [rbp+ppszPath]
0x18004e1db  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004e1df  mov     rax, rsi
0x18004e1e2  inc     rax
0x18004e1e5  cmp     [r9+rax*2], r15w
0x18004e1ea  jnz     short loc_18004E1E2
0x18004e1ec  lea     rdx, [rax+18h]
0x18004e1f0  mov     rax, qword ptr [rbp+var_20+8]
0x18004e1f4  cmp     rax, rdx
0x18004e1f7  jnb     short loc_18004E215
0x18004e1f9  mov     rbx, qword ptr [rbp+var_20]
0x18004e1fd  sub     rdx, rbx
0x18004e200  lea     rcx, [rbp+Src]; Src
0x18004e204  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18004e209  mov     qword ptr [rbp+var_20], rbx
0x18004e20d  mov     r9, [rbp+ppszPath]
0x18004e211  mov     rax, qword ptr [rbp+var_20+8]
0x18004e215  inc     rsi
0x18004e218  cmp     [r9+rsi*2], r15w
0x18004e21d  jnz     short loc_18004E215
0x18004e21f  cmp     rsi, rax
0x18004e222  ja      short loc_18004E24E
0x18004e224  lea     rdi, [rbp+Src]
0x18004e228  cmp     rax, 7
0x18004e22c  cmova   rdi, [rbp+Src]
0x18004e231  mov     qword ptr [rbp+var_20], rsi
0x18004e235  lea     rbx, [rsi+rsi]
0x18004e239  mov     r8, rbx; Size
0x18004e23c  mov     rdx, r9; Src
0x18004e23f  mov     rcx, rdi; void *
0x18004e242  call    memmove_0
0x18004e247  mov     [rbx+rdi], r15w
0x18004e24c  jmp     short loc_18004E25A
0x18004e24e  mov     rdx, rsi
0x18004e251  lea     rcx, [rbp+Src]
0x18004e255  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18004e25a  lea     rdx, aMicrosoft; "\\Microsoft"
0x18004e261  lea     rcx, [rbp+Src]; Src
0x18004e265  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004e26a  lea     rdx, aDevicecastle; "\\DeviceCastle"
0x18004e271  lea     rcx, [rbp+Src]; Src
0x18004e275  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004e27a  mov     rdx, qword ptr [rbp+var_20]
0x18004e27e  lea     rcx, [rbp+Src]; Src
0x18004e282  cmp     rdx, qword ptr [rbp+var_20+8]
0x18004e286  jnb     short loc_18004E2A3
0x18004e288  lea     rax, [rdx+1]
0x18004e28c  mov     qword ptr [rbp+var_20], rax
0x18004e290  cmp     qword ptr [rbp+var_20+8], 7
0x18004e295  cmova   rcx, [rbp+Src]
0x18004e29a  mov     dword ptr [rcx+rdx*2], 5Ch ; '\'
0x18004e2a1  jmp     short loc_18004E2AE
0x18004e2a3  mov     r9d, 5Ch ; '\'
0x18004e2a9  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x18004e2ae  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x18004e2b5  add     rax, 8
0x18004e2b9  mov     [rbp+lpCriticalSection], rax
0x18004e2bd  mov     [rbp+var_38], r15b
0x18004e2c1  lea     rcx, [rbp+lpCriticalSection]; this
0x18004e2c5  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x18004e2ca  mov     rax, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x18004e2d1  cmp     [rax+50h], r15b
0x18004e2d5  jnz     short loc_18004E306
0x18004e2d7  lea     rcx, [rax+30h]
0x18004e2db  lea     rdx, [rbp+Src]
0x18004e2df  cmp     rcx, rdx
0x18004e2e2  jz      short loc_18004E302
0x18004e2e4  movups  xmm2, xmmword ptr [rcx]
0x18004e2e7  movups  xmm3, xmmword ptr [rcx+10h]
0x18004e2eb  movups  xmm0, xmmword ptr [rbp+Src]
0x18004e2ef  movups  xmmword ptr [rcx], xmm0
0x18004e2f2  movups  xmm1, [rbp+var_20]
0x18004e2f6  movups  xmmword ptr [rcx+10h], xmm1
0x18004e2fa  movups  xmmword ptr [rbp+Src], xmm2
0x18004e2fe  movups  [rbp+var_20], xmm3
0x18004e302  mov     byte ptr [rax+50h], 1
0x18004e306  cmp     [rbp+var_38], r15b
0x18004e30a  jz      short loc_18004E317
0x18004e30c  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18004e310  call    cs:__imp_LeaveCriticalSection
0x18004e316  nop
0x18004e317  lea     rcx, [rbp+Src]
0x18004e31b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e320  nop
0x18004e321  mov     rcx, [rbp+ppszPath]; pv
0x18004e325  test    rcx, rcx
0x18004e328  jz      short loc_18004E330
0x18004e32a  call    cs:__imp_CoTaskMemFree
0x18004e330  test    r14, r14
0x18004e333  jz      short loc_18004E35B
0x18004e335  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x18004e33c  add     rcx, 30h ; '0'
0x18004e340  cmp     qword ptr [rcx+18h], 7
0x18004e345  jbe     short loc_18004E34A
0x18004e347  mov     rcx, [rcx]; unsigned __int16 *
0x18004e34a  call    ?CheckFolderExistence@Utilities@Internal@Library@DeviceCastle@@SAJPEBG@Z; DeviceCastle::Library::Internal::Utilities::CheckFolderExistence(ushort const *)
0x18004e34f  mov     ebx, eax
0x18004e351  test    eax, eax
0x18004e353  js      short loc_18004E35E
0x18004e355  setz    al
0x18004e358  mov     [r14], al
0x18004e35b  mov     ebx, r15d
0x18004e35e  mov     eax, ebx
0x18004e360  mov     rcx, [rbp+var_10]
0x18004e364  xor     rcx, rsp; StackCookie
0x18004e367  call    __security_check_cookie
0x18004e36c  add     rsp, 68h
0x18004e370  pop     r15
0x18004e372  pop     r14
0x18004e374  pop     rdi
0x18004e375  pop     rsi
0x18004e376  pop     rbx
0x18004e377  pop     rbp
0x18004e378  retn
```
