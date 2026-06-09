# DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity(void)

- ea: `0x18004830c`
- end: `0x1800485dc`
- name: `?DetermineCallerIdentity@CallerIdentity@Library@DeviceCastle@@QEAAJXZ`
- size: `720`
- prototype: `__int64 __fastcall(DeviceCastle::Library::CallerIdentity *__hidden this)`
- caller_count: `12`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066d50`
- `0x1800692f0`
- `0x180069550`
- `0x180069780`
- `0x1800699d0`
- `0x180069c00`
- `0x180069e00`
- `0x18006a000`
- `0x18006abb0`
- `0x18006ae30`
- `0x18006b050`
- `0x18006bc20`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180013014`
- `0x180013274`
- `0x18004830c`
- `0x1800485e4`
- `0x180048904`
- `0x18004bf9c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004837c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004837c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004843b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004843b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048359`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048359`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048372`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800485b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800485b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800483af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800483ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800483af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800483ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048433`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004859e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048433`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004859e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004845b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004845b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeviceCastle::Library::CallerIdentity::DetermineCallerIdentity(
        DeviceCastle::Library::CallerIdentity *this)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int CallerPackageFamilyName; // ebx
  DWORD v5; // ebx
  void *v6; // rax
  HLOCAL v7; // rsi
  DWORD v8; // ebx
  PSID *v9; // rax
  __int64 v10; // r8
  HLOCAL v11; // r9
  char **v12; // rcx
  unsigned __int64 v13; // rdx
  char *v14; // rsi
  __int64 v15; // rbx
  unsigned __int8 (__fastcall ***v16)(_QWORD); // rax
  __int64 v17; // r8
  unsigned __int16 *v18; // rbx
  const unsigned __int16 *v19; // r8
  DWORD TokenInformationLength; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v24[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v25; // [rsp+58h] [rbp-18h]
  unsigned __int64 v26; // [rsp+60h] [rbp-10h]

  TokenInformationLength = 0;
  hMem = 0;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v26 = 7;
  LOWORD(v24[0]) = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    goto LABEL_2;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    CallerPackageFamilyName = LastError;
    if ( LastError != 122 )
    {
LABEL_3:
      if ( LastError > 0 )
        CallerPackageFamilyName = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_30;
    }
  }
  (*(void (__fastcall **)(DeviceCastle::Library::CallerIdentity *, _QWORD))(*(_QWORD *)this + 72LL))(
    this,
    TokenInformationLength);
  v5 = TokenInformationLength;
  v6 = (void *)(*(__int64 (__fastcall **)(DeviceCastle::Library::CallerIdentity *))(*(_QWORD *)this + 8LL))(this);
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, v5, &TokenInformationLength) )
    goto LABEL_2;
  (*(void (__fastcall **)(DeviceCastle::Library::CallerIdentity *, _QWORD))(*(_QWORD *)this + 88LL))(
    this,
    TokenInformationLength);
  v7 = hMem;
  if ( hMem )
  {
    v8 = GetLastError();
    LocalFree(v7);
    SetLastError(v8);
  }
  hMem = 0;
  v9 = (PSID *)(*(__int64 (__fastcall **)(DeviceCastle::Library::CallerIdentity *))(*(_QWORD *)this + 16LL))(this);
  if ( !ConvertSidToStringSidW(*v9, (LPWSTR *)&hMem) )
  {
LABEL_2:
    LastError = GetLastError();
    CallerPackageFamilyName = LastError;
    goto LABEL_3;
  }
  v11 = hMem;
  v12 = (char **)((char *)this + 32);
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)hMem + v13) );
  if ( v13 > *((_QWORD *)this + 7) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v12,
      v13,
      v10,
      hMem);
  }
  else
  {
    if ( *((_QWORD *)this + 7) <= 7u )
      v14 = (char *)this + 32;
    else
      v14 = *v12;
    *((_QWORD *)this + 6) = v13;
    v15 = 2 * v13;
    memmove_0(v14, v11, 2 * v13);
    *(_WORD *)&v14[v15] = 0;
  }
  CallerPackageFamilyName = GetCallerPackageFamilyName(TokenHandle, v24);
  if ( CallerPackageFamilyName < 0 || !v25 )
  {
    v16 = (unsigned __int8 (__fastcall ***)(_QWORD))(***((__int64 (__fastcall ****)(_QWORD))DeviceCastle::Library::Internal::g_pCastleInstance
                                                       + 16))(*((_QWORD *)DeviceCastle::Library::Internal::g_pCastleInstance
                                                              + 16));
    if ( !(**v16)(v16) )
      goto LABEL_30;
    if ( v26 < 0x18 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        v24,
        24,
        v17,
        L"_Device Castle Internal_");
    }
    else
    {
      v18 = v24[0];
      v25 = 24;
      memmove_0(v24[0], L"_Device Castle Internal_", 0x30u);
      v18[24] = 0;
    }
    DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(
      DeviceCastle::Library::Internal::g_pCastleInstance,
      4u,
      0,
      L"Application Family Name unavailable: using testing key.");
  }
  v19 = (const unsigned __int16 *)v24;
  if ( v26 > 7 )
    v19 = v24[0];
  CallerPackageFamilyName = DeviceCastle::Library::CallerIdentity::ForceIdentity(
                              this,
                              (const unsigned __int16 *)hMem,
                              v19);
  if ( CallerPackageFamilyName >= 0 )
    CallerPackageFamilyName = 0;
LABEL_30:
  std::wstring::~wstring(v24);
  if ( hMem )
    LocalFree(hMem);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)CallerPackageFamilyName;
}

```

## disassembly

```asm
0x18004830c  mov     [rsp-18h+arg_8], rbx
0x180048311  mov     [rsp-18h+arg_10], rsi
0x180048316  push    rbp
0x180048317  push    rdi
0x180048318  push    r14
0x18004831a  mov     rbp, rsp
0x18004831d  sub     rsp, 70h
0x180048321  mov     rax, cs:__security_cookie
0x180048328  xor     rax, rsp
0x18004832b  mov     [rbp+var_8], rax
0x18004832f  mov     rdi, rcx
0x180048332  xor     r14d, r14d
0x180048335  mov     [rbp+TokenInformationLength], r14d
0x180048339  mov     [rbp+hMem], r14
0x18004833d  xorps   xmm0, xmm0
0x180048340  movups  xmmword ptr [rbp+var_28], xmm0
0x180048344  mov     [rbp+var_18], r14
0x180048348  mov     [rbp+var_10], 7
0x180048350  mov     word ptr [rbp+var_28], r14w
0x180048355  mov     [rbp+TokenHandle], r14
0x180048359  call    cs:__imp_GetCurrentThread
0x18004835f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180048363  lea     esi, [r14+1]
0x180048367  mov     r8d, esi; OpenAsSelf
0x18004836a  mov     edx, 20008h; DesiredAccess
0x18004836f  mov     rcx, rax; ThreadHandle
0x180048372  call    cs:__imp_OpenThreadToken
0x180048378  test    eax, eax
0x18004837a  jnz     short loc_18004839A
0x18004837c  call    cs:__imp_GetLastError
0x180048382  mov     ebx, eax
0x180048384  test    eax, eax
0x180048386  jle     loc_18004858B
0x18004838c  movzx   ebx, ax
0x18004838f  or      ebx, 80070000h
0x180048395  jmp     loc_18004858B
0x18004839a  lea     rax, [rbp+TokenInformationLength]
0x18004839e  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800483a3  xor     r9d, r9d; TokenInformationLength
0x1800483a6  xor     r8d, r8d; TokenInformation
0x1800483a9  mov     edx, esi; TokenInformationClass
0x1800483ab  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800483af  call    cs:__imp_GetTokenInformation
0x1800483b5  test    eax, eax
0x1800483b7  jnz     short loc_1800483C6
0x1800483b9  call    cs:__imp_GetLastError
0x1800483bf  mov     ebx, eax
0x1800483c1  cmp     eax, 7Ah ; 'z'
0x1800483c4  jnz     short loc_180048384
0x1800483c6  mov     rax, [rdi]
0x1800483c9  mov     edx, [rbp+TokenInformationLength]
0x1800483cc  mov     rcx, rdi
0x1800483cf  mov     rax, [rax+48h]
0x1800483d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483d8  mov     ebx, [rbp+TokenInformationLength]
0x1800483db  mov     rax, [rdi]
0x1800483de  mov     rcx, rdi
0x1800483e1  mov     rax, [rax+8]
0x1800483e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483ea  lea     rcx, [rbp+TokenInformationLength]
0x1800483ee  mov     [rsp+70h+ReturnLength], rcx; ReturnLength
0x1800483f3  mov     r9d, ebx; TokenInformationLength
0x1800483f6  mov     r8, rax; TokenInformation
0x1800483f9  mov     edx, esi; TokenInformationClass
0x1800483fb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800483ff  call    cs:__imp_GetTokenInformation
0x180048405  test    eax, eax
0x180048407  jz      loc_18004837C
0x18004840d  mov     rax, [rdi]
0x180048410  mov     edx, [rbp+TokenInformationLength]
0x180048413  mov     rcx, rdi
0x180048416  mov     rax, [rax+58h]
0x18004841a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004841f  mov     rsi, [rbp+hMem]
0x180048423  test    rsi, rsi
0x180048426  jz      short loc_180048441
0x180048428  call    cs:__imp_GetLastError
0x18004842e  mov     ebx, eax
0x180048430  mov     rcx, rsi; hMem
0x180048433  call    cs:__imp_LocalFree
0x180048439  mov     ecx, ebx; dwErrCode
0x18004843b  call    cs:__imp_SetLastError
0x180048441  mov     [rbp+hMem], r14
0x180048445  mov     rax, [rdi]
0x180048448  mov     rcx, rdi
0x18004844b  mov     rax, [rax+10h]
0x18004844f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048454  lea     rdx, [rbp+hMem]; StringSid
0x180048458  mov     rcx, [rax]; Sid
0x18004845b  call    cs:__imp_ConvertSidToStringSidW
0x180048461  test    eax, eax
0x180048463  jz      loc_18004837C
0x180048469  mov     r9, [rbp+hMem]
0x18004846d  lea     rcx, [rdi+20h]
0x180048471  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180048475  inc     rdx
0x180048478  cmp     [r9+rdx*2], r14w
0x18004847d  jnz     short loc_180048475
0x18004847f  cmp     rdx, [rcx+18h]
0x180048483  ja      short loc_1800484B1
0x180048485  cmp     qword ptr [rcx+18h], 7
0x18004848a  jbe     short loc_180048491
0x18004848c  mov     rsi, [rcx]
0x18004848f  jmp     short loc_180048494
0x180048491  mov     rsi, rcx
0x180048494  mov     [rcx+10h], rdx
0x180048498  lea     rbx, [rdx+rdx]
0x18004849c  mov     r8, rbx; Size
0x18004849f  mov     rdx, r9; Src
0x1800484a2  mov     rcx, rsi; void *
0x1800484a5  call    memmove_0
0x1800484aa  mov     [rbx+rsi], r14w
0x1800484af  jmp     short loc_1800484B6
0x1800484b1  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x1800484b6  lea     rdx, [rbp+var_28]
0x1800484ba  mov     rcx, [rbp+TokenHandle]
0x1800484be  call    GetCallerPackageFamilyName
0x1800484c3  mov     ebx, eax
0x1800484c5  test    eax, eax
0x1800484c7  js      short loc_1800484D3
0x1800484c9  cmp     [rbp+var_18], r14
0x1800484cd  jnz     loc_180048569
0x1800484d3  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; DeviceCastle::Library::DeviceCastleInternal * DeviceCastle::Library::Internal::g_pCastleInstance
0x1800484da  mov     rdx, [rcx+80h]
0x1800484e1  mov     rcx, [rdx]
0x1800484e4  mov     rax, [rcx]
0x1800484e7  mov     rcx, rdx
0x1800484ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484ef  mov     rdx, rax
0x1800484f2  mov     rcx, [rax]
0x1800484f5  mov     rax, [rcx]
0x1800484f8  mov     rcx, rdx
0x1800484fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048500  test    al, al
0x180048502  jz      loc_18004858B
0x180048508  mov     edx, 18h
0x18004850d  cmp     [rbp+var_10], rdx
0x180048511  jb      short loc_18004853F
0x180048513  lea     rbx, [rbp+var_28]
0x180048517  cmp     [rbp+var_10], 7
0x18004851c  cmova   rbx, [rbp+var_28]
0x180048521  mov     [rbp+var_18], rdx
0x180048525  lea     r8d, [rdx+18h]; Size
0x180048529  lea     rdx, aDeviceCastleIn; "_Device Castle Internal_"
0x180048530  mov     rcx, rbx; void *
0x180048533  call    memmove_0
0x180048538  mov     [rbx+30h], r14w
0x18004853d  jmp     short loc_18004854F
0x18004853f  lea     r9, aDeviceCastleIn; "_Device Castle Internal_"
0x180048546  lea     rcx, [rbp+var_28]
0x18004854a  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x18004854f  lea     r9, aApplicationFam; "Application Family Name unavailable: us"...
0x180048556  xor     r8d, r8d; struct DeviceCastle::Library::CallerIdentity *
0x180048559  lea     edx, [r8+4]; unsigned int
0x18004855d  mov     rcx, cs:?g_pCastleInstance@Internal@Library@DeviceCastle@@3PEAVDeviceCastleInternal@23@EA; this
0x180048564  call    ?LogFormattedMessage@DeviceCastleInternal@Library@DeviceCastle@@QEBAXKPEAVCallerIdentity@23@PEBGZZ; DeviceCastle::Library::DeviceCastleInternal::LogFormattedMessage(ulong,DeviceCastle::Library::CallerIdentity *,ushort const *,...)
0x180048569  lea     r8, [rbp+var_28]
0x18004856d  cmp     [rbp+var_10], 7
0x180048572  cmova   r8, [rbp+var_28]; unsigned __int16 *
0x180048577  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x18004857b  mov     rcx, rdi; this
0x18004857e  call    ?ForceIdentity@CallerIdentity@Library@DeviceCastle@@QEAAJPEBG0@Z; DeviceCastle::Library::CallerIdentity::ForceIdentity(ushort const *,ushort const *)
0x180048583  mov     ebx, eax
0x180048585  test    eax, eax
0x180048587  cmovns  ebx, r14d
0x18004858b  lea     rcx, [rbp+var_28]
0x18004858f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048594  nop
0x180048595  mov     rcx, [rbp+hMem]; hMem
0x180048599  test    rcx, rcx
0x18004859c  jz      short loc_1800485A5
0x18004859e  call    cs:__imp_LocalFree
0x1800485a4  nop
0x1800485a5  mov     rcx, [rbp+TokenHandle]; hObject
0x1800485a9  lea     rax, [rcx-1]
0x1800485ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800485b1  ja      short loc_1800485B9
0x1800485b3  call    cs:__imp_CloseHandle
0x1800485b9  mov     eax, ebx
0x1800485bb  mov     rcx, [rbp+var_8]
0x1800485bf  xor     rcx, rsp; StackCookie
0x1800485c2  call    __security_check_cookie
0x1800485c7  lea     r11, [rsp+70h+var_s0]
0x1800485cc  mov     rbx, [r11+28h]
0x1800485d0  mov     rsi, [r11+30h]
0x1800485d4  mov     rsp, r11
0x1800485d7  pop     r14
0x1800485d9  pop     rdi
0x1800485da  pop     rbp
0x1800485db  retn
```
