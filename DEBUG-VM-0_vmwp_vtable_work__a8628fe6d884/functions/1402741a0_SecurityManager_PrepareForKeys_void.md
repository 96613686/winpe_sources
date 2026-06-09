# SecurityManager::PrepareForKeys(void *)

- ea: `0x1402741a0`
- end: `0x1402747c0`
- name: `?PrepareForKeys@SecurityManager@@UEAAJPEAX@Z`
- size: `1568`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140029724`
- `0x14005e7e4`
- `0x1400b42b0`
- `0x1400d6a74`
- `0x14012eaac`
- `0x140132940`
- `0x140271d78`
- `0x140272248`
- `0x1402722b8`
- `0x140272518`
- `0x140272bf0`
- `0x140273030`
- `0x140273348`
- `0x14027398c`
- `0x1402741a0`
- `0x140274890`
- `0x140274b90`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140274257`
- `ntdll!NtQuerySystemInformation` at `0x140274257`
- `bcrypt!BCryptGenRandom` at `0x1402742ee`
- `bcrypt!BCryptGenRandom` at `0x1402742ee`
- `vid!VidSetMailboxKey` at `0x14027440e`
- `vid!VidSetMailboxKey` at `0x14027440e`
- `vid!VidGetRpcSession` at `0x14027447b`
- `vid!VidGetRpcSession` at `0x14027447b`

## string_xrefs

- `0x14027420d`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027428c`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402743c9`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274426`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274493`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402744e6`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274555`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402745db`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274641`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274693`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402746e5`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140274737`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall SecurityManager::PrepareForKeys(SecurityManager *this, void *a2)
{
  SecurityManager *v3; // rsi
  __int64 v4; // rdx
  NTSTATUS v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // edx
  int v10; // edi
  __int64 v11; // rdx
  NTSTATUS v12; // eax
  struct _GUID *v13; // rdi
  const unsigned __int16 *v14; // rdx
  int SecurityProcess; // eax
  unsigned int v16; // edi
  const char *v17; // r9
  unsigned int LastError; // ebx
  const char *v19; // r9
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // edi
  int v23; // eax
  unsigned int v24; // edi
  int v25; // eax
  unsigned int v26; // edi
  int SecurityCookie; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // edi
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // [rsp+20h] [rbp-D8h]
  int v36; // [rsp+20h] [rbp-D8h]
  ULONG ReturnLength[2]; // [rsp+30h] [rbp-C8h] BYREF
  __int128 v38; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B0h]
  __int128 v40; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-98h]
  __int128 v42; // [rsp+68h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-80h]
  __int128 SystemInformation; // [rsp+80h] [rbp-78h] BYREF
  __int128 *v45; // [rsp+90h] [rbp-68h]
  __int128 *v46; // [rsp+98h] [rbp-60h]
  __int64 v47; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-50h] BYREF
  UCHAR pbBuffer[16]; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v48 = 0;
  v47 = 0;
  v3 = (SecurityManager *)((char *)this - 24);
  if ( *((_DWORD *)this + 34) || *((_DWORD *)this + 28) || !*((_DWORD *)this + 30) && !*((_DWORD *)this + 31) )
    return 0;
  if ( !*((_QWORD *)this + 25) )
  {
    v4 = 2553;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)0x8007139FLL,
      v35);
    return 2147947423LL;
  }
  *((_QWORD *)this + 12) = a2;
  SystemInformation = 0;
  ReturnLength[0] = 0;
  v6 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, ReturnLength);
  if ( v6 >= 0 )
    v9 = SystemInformation & 1;
  else
    v9 = 0;
  v10 = v6 | 0x10000000;
  if ( v6 >= 0 )
    v10 = 0;
  if ( v10 < 0 )
  {
    v11 = 2560;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v10,
      v35);
    return (unsigned int)v10;
  }
  if ( !v9 )
  {
    VmEventWriteAndReport<std::wstring &,std::wstring &>(
      (_DWORD)this + 32,
      0,
      v7,
      v8,
      (__int64)this + 32,
      (__int64)this + 64);
    v4 = 2571;
    goto LABEL_7;
  }
  *(_OWORD *)pbBuffer = 0;
  v12 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  v10 = v12 | 0x10000000;
  if ( v12 >= 0 )
    v10 = 0;
  if ( v10 < 0 )
  {
    v11 = 2578;
    goto LABEL_15;
  }
  v42 = 0;
  v43 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  SecurityManager::UnwrapKeyProtector(v3, &v42, &v40, &v38);
  v13 = (struct _GUID *)((char *)this + 64);
  if ( *((_QWORD *)this + 11) <= 7u )
    v14 = (const unsigned __int16 *)((char *)this + 64);
  else
    v14 = *(const unsigned __int16 **)&v13->Data1;
  Vml::VmGuid::Assign((Vml::VmGuid *)&SystemInformation, v14);
  if ( *((_QWORD *)this + 11) > 7u )
    v13 = *(struct _GUID **)&v13->Data1;
  SecurityProcess = KeyManagement::CreateSecurityProcess(
                      (KeyManagement *)&SystemInformation,
                      v13,
                      *((const unsigned __int16 **)this + 25),
                      (const unsigned __int8 *)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)),
                      (struct _PS_TRUSTLET_TKSESSION_ID *)pbBuffer);
  v16 = SecurityProcess;
  if ( SecurityProcess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2A,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)SecurityProcess,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
    return v16;
  }
  if ( !(unsigned int)VidSetMailboxKey(*((_QWORD *)this + 12), pbBuffer) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA2F,
                  (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
                  v17);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
    return LastError;
  }
  if ( !(unsigned int)VidGetRpcSession(*((_QWORD *)this + 12), &v48, &v47, (char *)this + 360) )
  {
    v20 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xA34,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            v19);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
    return v20;
  }
  v21 = SecurityManager::InitializeRpcClient(v3);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA36,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v21,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
    return v22;
  }
  *(_QWORD *)&SystemInformation = v3;
  *((_QWORD *)&SystemInformation + 1) = &v47;
  v23 = lambda_2b6c794ed40287bf31308bbcd9759849_::operator()(&SystemInformation);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4C,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v23,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
    return v24;
  }
  *(_QWORD *)&SystemInformation = v3;
  *((_QWORD *)&SystemInformation + 1) = &v42;
  v45 = &v40;
  v46 = &v38;
  v25 = lambda_6c6ea953952cabd78dd0b7154551d92a_::operator()(&SystemInformation);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA72,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v25,
      v36);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
    return v26;
  }
  if ( *((_DWORD *)this + 31) )
  {
    *(_QWORD *)ReturnLength = 0;
    SecurityCookie = SecurityManager::GetSecurityCookie(this, (unsigned __int64 *)ReturnLength);
    v28 = SecurityCookie;
    if ( SecurityCookie < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA77,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)SecurityCookie,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
      return v28;
    }
    v29 = SecurityManager::InitializeEncryptionKeys(this);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7C,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v29,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
      return v30;
    }
    v31 = SecurityManager::PersistKsdState(v3);
    v32 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7E,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v31,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
      return v32;
    }
    v33 = SecurityManager::ReleaseEncryptionKeys(this);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA80,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v33,
        v36);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
      return v34;
    }
    SecurityManager::CloseKeyManagment(v3);
  }
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v38);
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v40);
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v42);
  return 0;
}

```

## disassembly

```asm
0x1402741a0  mov     r11, rsp
0x1402741a3  push    rbx
0x1402741a4  push    rsi
0x1402741a5  push    rdi
0x1402741a6  push    r14
0x1402741a8  sub     rsp, 0D8h
0x1402741af  mov     rax, cs:__security_cookie
0x1402741b6  xor     rax, rsp
0x1402741b9  mov     [rsp+0F8h+var_38], rax
0x1402741c1  mov     rbx, rcx
0x1402741c4  xor     r14d, r14d
0x1402741c7  mov     [r11-50h], r14
0x1402741cb  mov     [r11-58h], r14
0x1402741cf  lea     rsi, [rcx-18h]
0x1402741d3  cmp     [rsi+0A0h], r14d
0x1402741da  jnz     loc_1402747A0
0x1402741e0  cmp     [rcx+70h], r14d
0x1402741e4  jnz     loc_1402747A0
0x1402741ea  cmp     [rcx+78h], r14d
0x1402741ee  jnz     short loc_1402741FA
0x1402741f0  cmp     [rcx+7Ch], r14d
0x1402741f4  jz      loc_1402747A0
0x1402741fa  cmp     [rcx+0C8h], r14
0x140274201  jnz     short loc_14027422B
0x140274203  mov     edx, 9F9h; void *
0x140274208  mov     ebx, 8007139Fh
0x14027420d  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274214  mov     r9d, ebx; char *
0x140274217  mov     rcx, [rsp+0F8h]; this
0x14027421f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274224  mov     eax, ebx
0x140274226  jmp     loc_1402747A2
0x14027422b  mov     [rcx+60h], rdx
0x14027422f  xorps   xmm0, xmm0
0x140274232  movups  [rsp+0F8h+SystemInformation], xmm0
0x14027423a  mov     [rsp+0F8h+ReturnLength], r14d; void **
0x14027423f  lea     r9, [rsp+0F8h+ReturnLength]; ReturnLength
0x140274244  mov     r8d, 10h; SystemInformationLength
0x14027424a  lea     rdx, [rsp+0F8h+SystemInformation]; SystemInformation
0x140274252  mov     ecx, 0A5h; SystemInformationClass
0x140274257  call    cs:__imp_NtQuerySystemInformation
0x14027425e  nop     dword ptr [rax+rax+00h]
0x140274263  test    eax, eax
0x140274265  jns     short loc_14027426C
0x140274267  mov     edx, r14d
0x14027426a  jmp     short loc_140274277
0x14027426c  movzx   edx, byte ptr [rsp+0F8h+SystemInformation]
0x140274274  and     edx, 1
0x140274277  mov     edi, eax
0x140274279  bts     edi, 1Ch
0x14027427d  test    eax, eax
0x14027427f  cmovns  edi, r14d
0x140274283  test    edi, edi
0x140274285  jns     short loc_1402742AA
0x140274287  mov     edx, 0A00h; void *
0x14027428c  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274293  mov     r9d, edi; char *
0x140274296  mov     rcx, [rsp+0F8h]; this
0x14027429e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402742a3  mov     eax, edi
0x1402742a5  jmp     loc_1402747A2
0x1402742aa  test    edx, edx
0x1402742ac  jnz     short loc_1402742CF
0x1402742ae  lea     rax, [rbx+40h]
0x1402742b2  lea     rcx, [rbx+20h]
0x1402742b6  mov     [rsp+0F8h+var_D0], rax
0x1402742bb  mov     [rsp+0F8h+var_D8], rcx
0x1402742c0  call    ??$VmEventWriteAndReport@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@3@Z; VmEventWriteAndReport<std::wstring &,std::wstring &>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,std::wstring &,std::wstring &)
0x1402742c5  mov     edx, 0A0Bh
0x1402742ca  jmp     loc_140274208
0x1402742cf  xorps   xmm0, xmm0
0x1402742d2  movups  xmmword ptr [rsp+0F8h+pbBuffer], xmm0
0x1402742da  mov     r9d, 2; dwFlags
0x1402742e0  lea     r8d, [r9+0Eh]; cbBuffer
0x1402742e4  lea     rdx, [rsp+0F8h+pbBuffer]; pbBuffer
0x1402742ec  xor     ecx, ecx; hAlgorithm
0x1402742ee  call    cs:__imp_BCryptGenRandom
0x1402742f5  nop     dword ptr [rax+rax+00h]
0x1402742fa  mov     edi, eax
0x1402742fc  bts     edi, 1Ch
0x140274300  test    eax, eax
0x140274302  cmovns  edi, r14d
0x140274306  test    edi, edi
0x140274308  jns     short loc_140274314
0x14027430a  mov     edx, 0A12h
0x14027430f  jmp     loc_14027428C
0x140274314  xorps   xmm1, xmm1
0x140274317  movdqu  [rsp+0F8h+var_90], xmm1
0x14027431d  mov     [rsp+0F8h+var_80], r14
0x140274322  movdqu  [rsp+0F8h+var_A8], xmm1
0x140274328  mov     [rsp+0F8h+var_98], r14
0x14027432d  movdqu  [rsp+0F8h+var_C0], xmm1
0x140274333  mov     [rsp+0F8h+var_B0], r14
0x140274338  lea     r9, [rsp+0F8h+var_C0]
0x14027433d  lea     r8, [rsp+0F8h+var_A8]
0x140274342  lea     rdx, [rsp+0F8h+var_90]
0x140274347  mov     rcx, rsi
0x14027434a  call    ?UnwrapKeyProtector@SecurityManager@@AEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@00@Z; SecurityManager::UnwrapKeyProtector(std::vector<uchar> &,std::vector<uchar> &,std::vector<uchar> &)
0x14027434f  lea     rdi, [rbx+40h]
0x140274353  cmp     qword ptr [rdi+18h], 7
0x140274358  jbe     short loc_14027435F
0x14027435a  mov     rdx, [rdi]
0x14027435d  jmp     short loc_140274362
0x14027435f  mov     rdx, rdi; unsigned __int16 *
0x140274362  lea     rcx, [rsp+0F8h+SystemInformation]; this
0x14027436a  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x14027436f  mov     r8, [rbx+0C8h]; unsigned __int16 *
0x140274376  mov     r9, [rbx+0D0h]
0x14027437d  sub     r9, r8; unsigned __int8 *
0x140274380  cmp     qword ptr [rdi+18h], 7
0x140274385  jbe     short loc_14027438A
0x140274387  mov     rdi, [rdi]
0x14027438a  movaps  xmm0, [rsp+0F8h+SystemInformation]
0x140274392  movdqa  [rsp+0F8h+SystemInformation], xmm0
0x14027439b  lea     rax, [rsp+0F8h+pbBuffer]
0x1402743a3  mov     [rsp+0F8h+var_D8], rax; int
0x1402743a8  mov     rdx, rdi; struct _GUID *
0x1402743ab  lea     rcx, [rsp+0F8h+SystemInformation]; this
0x1402743b3  call    ?CreateSecurityProcess@KeyManagement@@YAJU_GUID@@PEBGPEBE_KPEAU_TRUSTLET_MAILBOX_KEY@@PEAPEAX@Z; KeyManagement::CreateSecurityProcess(_GUID,ushort const *,uchar const *,unsigned __int64,_TRUSTLET_MAILBOX_KEY *,void * *)
0x1402743b8  mov     edi, eax
0x1402743ba  test    eax, eax
0x1402743bc  jns     short loc_140274402
0x1402743be  mov     rcx, [rsp+0F8h]; this
0x1402743c6  mov     r9d, eax; char *
0x1402743c9  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402743d0  mov     edx, 0A2Ah; void *
0x1402743d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402743da  nop
0x1402743db  lea     rcx, [rsp+0F8h+var_C0]
0x1402743e0  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402743e5  nop
0x1402743e6  lea     rcx, [rsp+0F8h+var_A8]
0x1402743eb  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402743f0  nop
0x1402743f1  lea     rcx, [rsp+0F8h+var_90]
0x1402743f6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402743fb  mov     eax, edi
0x1402743fd  jmp     loc_1402747A2
0x140274402  lea     rdx, [rsp+0F8h+pbBuffer]
0x14027440a  mov     rcx, [rbx+60h]
0x14027440e  call    cs:__imp_VidSetMailboxKey
0x140274415  nop     dword ptr [rax+rax+00h]
0x14027441a  test    eax, eax
0x14027441c  jnz     short loc_140274460
0x14027441e  mov     rcx, [rsp+0F8h]; this
0x140274426  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027442d  mov     edx, 0A2Fh; void *
0x140274432  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140274437  mov     ebx, eax
0x140274439  lea     rcx, [rsp+0F8h+var_C0]
0x14027443e  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274443  nop
0x140274444  lea     rcx, [rsp+0F8h+var_A8]
0x140274449  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027444e  nop
0x14027444f  lea     rcx, [rsp+0F8h+var_90]
0x140274454  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274459  mov     eax, ebx
0x14027445b  jmp     loc_1402747A2
0x140274460  lea     r9, [rbx+168h]
0x140274467  lea     r8, [rsp+0F8h+var_58]
0x14027446f  lea     rdx, [rsp+0F8h+var_50]
0x140274477  mov     rcx, [rbx+60h]
0x14027447b  call    cs:__imp_VidGetRpcSession
0x140274482  nop     dword ptr [rax+rax+00h]
0x140274487  test    eax, eax
0x140274489  jnz     short loc_1402744CD
0x14027448b  mov     rcx, [rsp+0F8h]; this
0x140274493  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027449a  mov     edx, 0A34h; void *
0x14027449f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1402744a4  mov     ebx, eax
0x1402744a6  lea     rcx, [rsp+0F8h+var_C0]
0x1402744ab  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402744b0  nop
0x1402744b1  lea     rcx, [rsp+0F8h+var_A8]
0x1402744b6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402744bb  nop
0x1402744bc  lea     rcx, [rsp+0F8h+var_90]
0x1402744c1  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402744c6  mov     eax, ebx
0x1402744c8  jmp     loc_1402747A2
0x1402744cd  mov     rcx, rsi; this
0x1402744d0  call    ?InitializeRpcClient@SecurityManager@@AEAAJXZ; SecurityManager::InitializeRpcClient(void)
0x1402744d5  mov     edi, eax
0x1402744d7  test    eax, eax
0x1402744d9  jns     short loc_14027451F
0x1402744db  mov     rcx, [rsp+0F8h]; this
0x1402744e3  mov     r9d, eax; char *
0x1402744e6  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402744ed  mov     edx, 0A36h; void *
0x1402744f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402744f7  nop
0x1402744f8  lea     rcx, [rsp+0F8h+var_C0]
0x1402744fd  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274502  nop
0x140274503  lea     rcx, [rsp+0F8h+var_A8]
0x140274508  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027450d  nop
0x14027450e  lea     rcx, [rsp+0F8h+var_90]
0x140274513  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274518  mov     eax, edi
0x14027451a  jmp     loc_1402747A2
0x14027451f  mov     qword ptr [rsp+0F8h+SystemInformation], rsi
0x140274527  lea     rax, [rsp+0F8h+var_58]
0x14027452f  mov     qword ptr [rsp+0F8h+SystemInformation+8], rax
0x140274537  lea     rcx, [rsp+0F8h+SystemInformation]
0x14027453f  call    _lambda_2b6c794ed40287bf31308bbcd9759849___operator__
0x140274544  mov     edi, eax
0x140274546  test    eax, eax
0x140274548  jns     short loc_14027458E
0x14027454a  mov     rcx, [rsp+0F8h]; this
0x140274552  mov     r9d, eax; char *
0x140274555  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027455c  mov     edx, 0A4Ch; void *
0x140274561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274566  nop
0x140274567  lea     rcx, [rsp+0F8h+var_C0]
0x14027456c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274571  nop
0x140274572  lea     rcx, [rsp+0F8h+var_A8]
0x140274577  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027457c  nop
0x14027457d  lea     rcx, [rsp+0F8h+var_90]
0x140274582  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274587  mov     eax, edi
0x140274589  jmp     loc_1402747A2
0x14027458e  mov     qword ptr [rsp+0F8h+SystemInformation], rsi
0x140274596  lea     rax, [rsp+0F8h+var_90]
0x14027459b  mov     qword ptr [rsp+0F8h+SystemInformation+8], rax
0x1402745a3  lea     rax, [rsp+0F8h+var_A8]
0x1402745a8  mov     [rsp+0F8h+var_68], rax
0x1402745b0  lea     rax, [rsp+0F8h+var_C0]
0x1402745b5  mov     [rsp+0F8h+var_60], rax
0x1402745bd  lea     rcx, [rsp+0F8h+SystemInformation]
0x1402745c5  call    _lambda_6c6ea953952cabd78dd0b7154551d92a___operator__
0x1402745ca  mov     edi, eax
0x1402745cc  test    eax, eax
0x1402745ce  jns     short loc_140274614
0x1402745d0  mov     rcx, [rsp+0F8h]; this
0x1402745d8  mov     r9d, eax; char *
0x1402745db  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402745e2  mov     edx, 0A72h; void *
0x1402745e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402745ec  nop
0x1402745ed  lea     rcx, [rsp+0F8h+var_C0]
0x1402745f2  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402745f7  nop
0x1402745f8  lea     rcx, [rsp+0F8h+var_A8]
0x1402745fd  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274602  nop
0x140274603  lea     rcx, [rsp+0F8h+var_90]
0x140274608  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027460d  mov     eax, edi
0x14027460f  jmp     loc_1402747A2
0x140274614  cmp     [rbx+7Ch], r14d
0x140274618  jz      loc_140274776
0x14027461e  mov     qword ptr [rsp+0F8h+ReturnLength], r14
0x140274623  lea     rdx, [rsp+0F8h+ReturnLength]; unsigned __int64 *
0x140274628  mov     rcx, rbx; this
0x14027462b  call    ?GetSecurityCookie@SecurityManager@@UEAAJPEA_K@Z; SecurityManager::GetSecurityCookie(unsigned __int64 *)
0x140274630  mov     edi, eax
0x140274632  test    eax, eax
0x140274634  jns     short loc_14027467A
0x140274636  mov     rcx, [rsp+0F8h]; this
0x14027463e  mov     r9d, eax; char *
0x140274641  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140274648  mov     edx, 0A77h; void *
0x14027464d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140274652  nop
0x140274653  lea     rcx, [rsp+0F8h+var_C0]
0x140274658  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027465d  nop
0x14027465e  lea     rcx, [rsp+0F8h+var_A8]
0x140274663  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274668  nop
0x140274669  lea     rcx, [rsp+0F8h+var_90]
0x14027466e  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140274673  mov     eax, edi
0x140274675  jmp     loc_1402747A2
0x14027467a  mov     rcx, rbx; this
0x14027467d  call    ?InitializeEncryptionKeys@SecurityManager@@UEAAJXZ; SecurityManager::InitializeEncryptionKeys(void)
0x140274682  mov     edi, eax
0x140274684  test    eax, eax
0x140274686  jns     short loc_1402746CC
0x140274688  mov     rcx, [rsp+0F8h]; this
0x140274690  mov     r9d, eax; char *
0x140274693  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027469a  mov     edx, 0A7Ch; void *
0x14027469f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402746a4  nop
0x1402746a5  lea     rcx, [rsp+0F8h+var_C0]
0x1402746aa  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402746af  nop
0x1402746b0  lea     rcx, [rsp+0F8h+var_A8]
0x1402746b5  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402746ba  nop
0x1402746bb  lea     rcx, [rsp+0F8h+var_90]
0x1402746c0  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402746c5  mov     eax, edi
  ... truncated ...
```
