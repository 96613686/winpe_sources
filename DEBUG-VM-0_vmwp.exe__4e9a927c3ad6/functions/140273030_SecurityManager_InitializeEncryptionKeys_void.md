# SecurityManager::InitializeEncryptionKeys(void)

- ea: `0x140273030`
- end: `0x140273340`
- name: `?InitializeEncryptionKeys@SecurityManager@@UEAAJXZ`
- size: `784`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1402741a0`

## callees

- `0x140034ef8`
- `0x140054508`
- `0x140054630`
- `0x14005e7e4`
- `0x140081778`
- `0x1400b42b0`
- `0x1400d6a74`
- `0x140132940`
- `0x140271e20`
- `0x140272680`
- `0x140273030`
- `0x1402c2010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x140273296`
- `bcrypt!BCryptGenRandom` at `0x140273296`
- `vid!VidInitEncryptionKeys` at `0x140273089`
- `vid!VidInitEncryptionKeys` at `0x140273089`

## string_xrefs

- `0x14027315d`: `/configuration/security/keys/encrypted_static_key`
- `0x1402731ae`: `/configuration/security/keys/encrypted_static_key`
- `0x14027306d`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402730a1`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273109`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402731cf`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027323e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402732b3`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall SecurityManager::InitializeEncryptionKeys(SecurityManager *this)
{
  const char *v3; // r9
  PUCHAR *v4; // rdi
  unsigned int v5; // esi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  int v9; // eax
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // [rsp+20h] [rbp-68h]
  unsigned int v14; // [rsp+20h] [rbp-68h]
  char *v15[2]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-48h] BYREF
  PUCHAR pbBuffer[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v18; // [rsp+58h] [rbp-30h]
  void *v19[2]; // [rsp+60h] [rbp-28h] BYREF
  __int64 v20; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( *((_BYTE *)this + 192) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6BE,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)0x8007139FLL,
      v13);
    return 2147947423LL;
  }
  if ( !(unsigned int)VidInitEncryptionKeys(*((_QWORD *)this + 12)) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6C1,
             (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
             v3);
  *((_BYTE *)this + 192) = 1;
  if ( *((_DWORD *)this + 31) )
  {
    v4 = (PUCHAR *)((char *)this + 320);
    if ( *((_QWORD *)this + 41) == *((_QWORD *)this + 40) )
    {
      *(_OWORD *)v15 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v15, *((_QWORD *)this + 2), 0);
      v5 = (unsigned int)v15[1];
      if ( SLODWORD(v15[1]) < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6CC,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)LODWORD(v15[1]),
          v13);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
        return v5;
      }
      *(_OWORD *)pbBuffer = 0;
      v18 = 0;
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(pbBuffer, 32);
      v16 = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
             *((_QWORD *)this + 2),
             L"/configuration/security/keys/encrypted_static_key",
             &v16);
      if ( (unsigned int)RepositoryKeyFound(v6) )
      {
        *(_OWORD *)v19 = 0;
        v20 = 0;
        std::vector<enum gsl::byte>::vector<enum gsl::byte>(v19, v16);
        v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void *, _QWORD))(**((_QWORD **)this + 2) + 88LL))(
               *((_QWORD *)this + 2),
               L"/configuration/security/keys/encrypted_static_key",
               v19[0],
               (unsigned int)(LODWORD(v19[1]) - LODWORD(v19[0])));
        v8 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6D9,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v7,
            v13);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v19);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
          return v8;
        }
        v9 = SecurityManager::DecryptData(
               this,
               v19[0],
               LODWORD(v19[1]) - LODWORD(v19[0]),
               pbBuffer[0],
               LODWORD(pbBuffer[1]) - LODWORD(pbBuffer[0]));
        v10 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6DF,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v9,
            v14);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v19);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
          return v10;
        }
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v19);
      }
      else
      {
        v11 = BCryptGenRandom(0, pbBuffer[0], LODWORD(pbBuffer[1]) - LODWORD(pbBuffer[0]), 2u);
        v12 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6EA,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v11,
            v13);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
          return v12;
        }
      }
      if ( v4 != pbBuffer )
        std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(v4, pbBuffer[0], pbBuffer[1] - pbBuffer[0]);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140273030  mov     [rsp+arg_8], rbx
0x140273035  mov     [rsp+arg_10], rsi
0x14027303a  push    rdi
0x14027303b  sub     rsp, 80h
0x140273042  mov     rax, cs:__security_cookie
0x140273049  xor     rax, rsp
0x14027304c  mov     [rsp+88h+var_10], rax
0x140273051  mov     rbx, rcx
0x140273054  cmp     byte ptr [rcx+0C0h], 0
0x14027305b  jz      short loc_140273085
0x14027305d  mov     rcx, [rsp+88h]; this
0x140273065  mov     ebx, 8007139Fh
0x14027306a  mov     r9d, ebx; char *
0x14027306d  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273074  mov     edx, 6BEh; void *
0x140273079  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027307e  mov     eax, ebx
0x140273080  jmp     loc_14027331D
0x140273085  mov     rcx, [rcx+60h]
0x140273089  call    cs:__imp_VidInitEncryptionKeys
0x140273090  nop     dword ptr [rax+rax+00h]
0x140273095  test    eax, eax
0x140273097  jnz     short loc_1402730B7
0x140273099  mov     rcx, [rsp+88h]; this
0x1402730a1  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402730a8  mov     edx, 6C1h; void *
0x1402730ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1402730b2  jmp     loc_14027331D
0x1402730b7  mov     byte ptr [rbx+0C0h], 1
0x1402730be  cmp     dword ptr [rbx+7Ch], 0
0x1402730c2  jz      loc_14027331B
0x1402730c8  lea     rdi, [rbx+140h]
0x1402730cf  mov     rax, [rdi+8]
0x1402730d3  cmp     rax, [rdi]
0x1402730d6  jnz     loc_140273313
0x1402730dc  xorps   xmm0, xmm0
0x1402730df  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x1402730e4  xor     r8d, r8d
0x1402730e7  mov     rdx, [rbx+10h]
0x1402730eb  lea     rcx, [rsp+88h+var_58]
0x1402730f0  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1402730f5  nop
0x1402730f6  mov     esi, dword ptr [rsp+88h+var_58+8]
0x1402730fa  test    esi, esi
0x1402730fc  jns     short loc_14027312C
0x1402730fe  mov     rcx, [rsp+88h]; this
0x140273106  mov     r9d, esi; char *
0x140273109  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273110  mov     edx, 6CCh; void *
0x140273115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027311a  nop
0x14027311b  lea     rcx, [rsp+88h+var_58]; this
0x140273120  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273125  mov     eax, esi
0x140273127  jmp     loc_14027331D
0x14027312c  xorps   xmm0, xmm0
0x14027312f  xor     eax, eax
0x140273131  movups  xmmword ptr [rsp+88h+pbBuffer], xmm0
0x140273136  mov     [rsp+88h+var_30], rax
0x14027313b  lea     edx, [rax+20h]
0x14027313e  lea     rcx, [rsp+88h+pbBuffer]
0x140273143  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140273148  nop
0x140273149  mov     [rsp+88h+var_48], 0
0x140273151  mov     rcx, [rbx+10h]
0x140273155  mov     rax, [rcx]
0x140273158  lea     r8, [rsp+88h+var_48]
0x14027315d  lea     rdx, ?SECURITY_SETTING_ENCRYPTED_STATIC_KEY@@3QBGB; "/configuration/security/keys/encrypted_"...
0x140273164  mov     rax, [rax+50h]
0x140273168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027316d  mov     ecx, eax; int
0x14027316f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x140273174  test    eax, eax
0x140273176  jz      loc_140273283
0x14027317c  xorps   xmm0, xmm0
0x14027317f  xor     eax, eax
0x140273181  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x140273186  mov     [rsp+88h+var_18], rax
0x14027318b  mov     edx, [rsp+88h+var_48]
0x14027318f  lea     rcx, [rsp+88h+var_28]
0x140273194  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140273199  nop
0x14027319a  mov     rcx, [rbx+10h]
0x14027319e  mov     r8, [rsp+88h+var_28]
0x1402731a3  mov     rax, [rcx]
0x1402731a6  mov     r9d, dword ptr [rsp+88h+var_28+8]
0x1402731ab  sub     r9d, r8d
0x1402731ae  lea     rdx, ?SECURITY_SETTING_ENCRYPTED_STATIC_KEY@@3QBGB; "/configuration/security/keys/encrypted_"...
0x1402731b5  mov     rax, [rax+58h]
0x1402731b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402731be  mov     esi, eax
0x1402731c0  test    eax, eax
0x1402731c2  jns     short loc_140273208
0x1402731c4  mov     rcx, [rsp+88h]; this
0x1402731cc  mov     r9d, eax; char *
0x1402731cf  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402731d6  mov     edx, 6D9h; void *
0x1402731db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402731e0  nop
0x1402731e1  lea     rcx, [rsp+88h+var_28]
0x1402731e6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402731eb  nop
0x1402731ec  lea     rcx, [rsp+88h+pbBuffer]
0x1402731f1  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402731f6  nop
0x1402731f7  lea     rcx, [rsp+88h+var_58]; this
0x1402731fc  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273201  mov     eax, esi
0x140273203  jmp     loc_14027331D
0x140273208  mov     r9, [rsp+88h+pbBuffer]; void *
0x14027320d  mov     rdx, [rsp+88h+var_28]; void *
0x140273212  mov     eax, dword ptr [rsp+88h+pbBuffer+8]
0x140273216  sub     eax, r9d
0x140273219  mov     r8d, dword ptr [rsp+88h+var_28+8]
0x14027321e  sub     r8d, edx; unsigned int
0x140273221  mov     [rsp+88h+var_68], eax; int
0x140273225  mov     rcx, rbx; this
0x140273228  call    ?DecryptData@SecurityManager@@UEAAJPEAXI0I@Z; SecurityManager::DecryptData(void *,uint,void *,uint)
0x14027322d  mov     ebx, eax
0x14027322f  test    eax, eax
0x140273231  jns     short loc_140273277
0x140273233  mov     rcx, [rsp+88h]; this
0x14027323b  mov     r9d, eax; char *
0x14027323e  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273245  mov     edx, 6DFh; void *
0x14027324a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027324f  nop
0x140273250  lea     rcx, [rsp+88h+var_28]
0x140273255  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027325a  nop
0x14027325b  lea     rcx, [rsp+88h+pbBuffer]
0x140273260  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273265  nop
0x140273266  lea     rcx, [rsp+88h+var_58]; this
0x14027326b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273270  mov     eax, ebx
0x140273272  jmp     loc_14027331D
0x140273277  lea     rcx, [rsp+88h+var_28]
0x14027327c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273281  jmp     short loc_1402732DE
0x140273283  mov     rdx, [rsp+88h+pbBuffer]; pbBuffer
0x140273288  mov     r8d, dword ptr [rsp+88h+pbBuffer+8]
0x14027328d  sub     r8d, edx; cbBuffer
0x140273290  xor     ecx, ecx; hAlgorithm
0x140273292  lea     r9d, [rcx+2]; dwFlags
0x140273296  call    cs:__imp_BCryptGenRandom
0x14027329d  nop     dword ptr [rax+rax+00h]
0x1402732a2  mov     ebx, eax
0x1402732a4  test    eax, eax
0x1402732a6  jns     short loc_1402732DE
0x1402732a8  mov     rcx, [rsp+88h]; this
0x1402732b0  mov     r9d, eax; char *
0x1402732b3  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402732ba  mov     edx, 6EAh; void *
0x1402732bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402732c4  nop
0x1402732c5  lea     rcx, [rsp+88h+pbBuffer]
0x1402732ca  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402732cf  nop
0x1402732d0  lea     rcx, [rsp+88h+var_58]; this
0x1402732d5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1402732da  mov     eax, ebx
0x1402732dc  jmp     short loc_14027331D
0x1402732de  lea     rax, [rsp+88h+pbBuffer]
0x1402732e3  cmp     rdi, rax
0x1402732e6  jz      short loc_1402732FE
0x1402732e8  mov     rdx, [rsp+88h+pbBuffer]
0x1402732ed  mov     r8, [rsp+88h+pbBuffer+8]
0x1402732f2  sub     r8, rdx
0x1402732f5  mov     rcx, rdi
0x1402732f8  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1402732fd  nop
0x1402732fe  lea     rcx, [rsp+88h+pbBuffer]
0x140273303  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273308  nop
0x140273309  lea     rcx, [rsp+88h+var_58]; this
0x14027330e  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273313  jmp     short loc_14027331B
0x140273315  mov     eax, [rsp+88h+var_48]
0x140273319  jmp     short loc_14027331D
0x14027331b  xor     eax, eax
0x14027331d  mov     rcx, [rsp+88h+var_10]
0x140273322  xor     rcx, rsp; StackCookie
0x140273325  call    __security_check_cookie
0x14027332a  lea     r11, [rsp+88h+var_8]
0x140273332  mov     rbx, [r11+18h]
0x140273336  mov     rsi, [r11+20h]
0x14027333a  mov     rsp, r11
0x14027333d  pop     rdi
0x14027333e  retn
```
