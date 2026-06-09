# ConstructSecurityDescriptor

- ea: `0x14000a5a0`
- end: `0x14000a990`
- name: `ConstructSecurityDescriptor`
- size: `1008`
- prototype: `__int64 __fastcall(ATL::CSecurityDesc *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e140`

## callees

- `0x140004280`
- `0x140008554`
- `0x1400086fc`
- `0x140009180`
- `0x140009230`
- `0x14000a0f8`
- `0x14000a410`
- `0x14000a5a0`
- `0x14000cd94`
- `0x14000d3bc`
- `0x140012754`
- `0x140012fa8`
- `0x140013104`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14000a647`
- `ADVAPI32!OpenThreadToken` at `0x14000a647`
- `ADVAPI32!OpenProcessToken` at `0x14000a69a`
- `ADVAPI32!OpenProcessToken` at `0x14000a69a`
- `KERNEL32!GetCurrentThread` at `0x14000a625`
- `KERNEL32!GetCurrentThread` at `0x14000a625`
- `KERNEL32!GetLastError` at `0x14000a670`
- `KERNEL32!GetLastError` at `0x14000a670`
- `KERNEL32!GetCurrentProcess` at `0x14000a681`
- `KERNEL32!GetCurrentProcess` at `0x14000a681`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
char __fastcall ConstructSecurityDescriptor(void **this)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v4; // eax
  unsigned int v6; // r8d
  unsigned __int8 v7; // r9
  unsigned int v8; // r8d
  unsigned __int8 v9; // r9
  bool v10; // di
  unsigned int v11; // r8d
  unsigned __int8 v12; // r9
  bool v13; // di
  char v14; // r8
  char v15; // r8
  HANDLE TokenHandle; // [rsp+30h] [rbp-1F8h] BYREF
  void **v17; // [rsp+38h] [rbp-1F0h] BYREF
  __int128 v18; // [rsp+40h] [rbp-1E8h]
  __int64 v19; // [rsp+50h] [rbp-1D8h]
  _QWORD v20[2]; // [rsp+58h] [rbp-1D0h] BYREF
  char v21; // [rsp+68h] [rbp-1C0h]
  int v22; // [rsp+6Ch] [rbp-1BCh]
  __int128 v23; // [rsp+70h] [rbp-1B8h]
  __int64 v24; // [rsp+80h] [rbp-1A8h]
  int v25; // [rsp+88h] [rbp-1A0h]
  _BYTE v26[128]; // [rsp+90h] [rbp-198h] BYREF
  _BYTE v27[128]; // [rsp+110h] [rbp-118h] BYREF
  _BYTE v28[128]; // [rsp+190h] [rbp-98h] BYREF

  v20[1] = 0;
  v21 = 0;
  v22 = 2;
  v20[0] = &ATL::CDacl::`vftable';
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v17 = &ATL::CAccessToken::`vftable';
  v18 = 0;
  v19 = 0;
  CurrentThread = GetCurrentThread();
  TokenHandle = 0;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    ((void (__fastcall *)(void ***))v17[1])(&v17);
    *(_QWORD *)&v18 = TokenHandle;
  }
  else
  {
    if ( GetLastError() != 1008 )
      goto LABEL_16;
    CurrentProcess = GetCurrentProcess();
    TokenHandle = 0;
    v4 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
    if ( v4 )
    {
      ((void (__fastcall *)(void ***))v17[1])(&v17);
      *(_QWORD *)&v18 = TokenHandle;
      LOBYTE(v4) = 1;
    }
    if ( !v4 )
    {
LABEL_16:
      v17 = &ATL::CAccessToken::`vftable';
      ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
      ATL::CDacl::~CDacl((ATL::CDacl *)v20);
      return 0;
    }
  }
  ATL::CSid::CSid((ATL::CSid *)v26);
  if ( ATL::CAccessToken::GetUser((ATL::CAccessToken *)&v17, (struct ATL::CSid *)v26) )
  {
    ATL::CSid::CSid((ATL::CSid *)v27);
    if ( ATL::CAccessToken::GetPrimaryGroup((ATL::CAccessToken *)&v17, (struct ATL::CSid *)v27)
      && ATL::CDacl::AddAllowedAce((ATL::CDacl *)v20, (const struct ATL::CSid *)v26, v6, v7)
      && (ATL::CSid::CSid((ATL::CSid *)v28, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 2u),
          v10 = ATL::CDacl::AddAllowedAce((ATL::CDacl *)v20, (const struct ATL::CSid *)v28, v8, v9),
          ATL::CSid::~CSid((ATL::CSid *)v28),
          v10)
      && (ATL::CSid::CSid((ATL::CSid *)v28, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 1u),
          v13 = ATL::CDacl::AddAllowedAce((ATL::CDacl *)v20, (const struct ATL::CSid *)v28, v11, v12),
          ATL::CSid::~CSid((ATL::CSid *)v28),
          v13) )
    {
      ATL::CSecurityDesc::SetDacl(this, (const struct ATL::CDacl *)v20);
      ATL::CSecurityDesc::SetOwner(this, (const struct ATL::CSid *)v26, v14);
      ATL::CSecurityDesc::SetGroup(this, (const struct ATL::CSid *)v27, v15);
      ATL::CSid::~CSid((ATL::CSid *)v27);
      ATL::CSid::~CSid((ATL::CSid *)v26);
      v17 = &ATL::CAccessToken::`vftable';
      ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
      ATL::CDacl::~CDacl((ATL::CDacl *)v20);
      return 1;
    }
    else
    {
      ATL::CSid::~CSid((ATL::CSid *)v27);
      ATL::CSid::~CSid((ATL::CSid *)v26);
      v17 = &ATL::CAccessToken::`vftable';
      ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
      ATL::CDacl::~CDacl((ATL::CDacl *)v20);
      return 0;
    }
  }
  else
  {
    ATL::CSid::~CSid((ATL::CSid *)v26);
    v17 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
    ATL::CDacl::~CDacl((ATL::CDacl *)v20);
    return 0;
  }
}

```

## disassembly

```asm
0x14000a5a0  mov     [rsp+arg_8], rbx
0x14000a5a5  mov     [rsp+arg_10], rdi
0x14000a5aa  push    r14
0x14000a5ac  sub     rsp, 220h
0x14000a5b3  mov     rax, cs:__security_cookie
0x14000a5ba  xor     rax, rsp
0x14000a5bd  mov     [rsp+228h+var_18], rax
0x14000a5c5  mov     rbx, rcx
0x14000a5c8  mov     [rsp+228h+var_1C8], 0
0x14000a5d1  mov     [rsp+228h+var_1C0], 0
0x14000a5d6  mov     [rsp+228h+var_1BC], 2
0x14000a5de  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x14000a5e5  mov     [rsp+228h+var_1D0], rax
0x14000a5ea  xorps   xmm0, xmm0
0x14000a5ed  movdqu  [rsp+228h+var_1B8], xmm0
0x14000a5f3  mov     [rsp+228h+var_1A8], 0
0x14000a5ff  mov     [rsp+228h+var_1A0], 0
0x14000a60a  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x14000a611  mov     [rsp+228h+var_1F0], r14
0x14000a616  movdqu  [rsp+228h+var_1E8], xmm0
0x14000a61c  mov     [rsp+228h+var_1D8], 0
0x14000a625  call    cs:__imp_GetCurrentThread
0x14000a62b  mov     [rsp+228h+TokenHandle], 0
0x14000a634  lea     r9, [rsp+228h+TokenHandle]; TokenHandle
0x14000a639  mov     edi, 8
0x14000a63e  lea     r8d, [rdi-7]; OpenAsSelf
0x14000a642  mov     edx, edi; DesiredAccess
0x14000a644  mov     rcx, rax; ThreadHandle
0x14000a647  call    cs:__imp_OpenThreadToken
0x14000a64d  test    eax, eax
0x14000a64f  jz      short loc_14000A670
0x14000a651  mov     rax, [rsp+228h+var_1F0]
0x14000a656  lea     rcx, [rsp+228h+var_1F0]
0x14000a65b  mov     rax, [rax+8]
0x14000a65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a664  mov     rax, [rsp+228h+TokenHandle]
0x14000a669  mov     qword ptr [rsp+228h+var_1E8], rax
0x14000a66e  jmp     short loc_14000A6CB
0x14000a670  call    cs:__imp_GetLastError
0x14000a676  cmp     eax, 3F0h
0x14000a67b  jnz     loc_14000A949
0x14000a681  call    cs:__imp_GetCurrentProcess
0x14000a687  mov     [rsp+228h+TokenHandle], 0
0x14000a690  lea     r8, [rsp+228h+TokenHandle]; TokenHandle
0x14000a695  mov     edx, edi; DesiredAccess
0x14000a697  mov     rcx, rax; ProcessHandle
0x14000a69a  call    cs:__imp_OpenProcessToken
0x14000a6a0  test    eax, eax
0x14000a6a2  jz      short loc_14000A6C3
0x14000a6a4  mov     rax, [rsp+228h+var_1F0]
0x14000a6a9  lea     rcx, [rsp+228h+var_1F0]
0x14000a6ae  mov     rax, [rax+8]
0x14000a6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6b7  mov     rax, [rsp+228h+TokenHandle]
0x14000a6bc  mov     qword ptr [rsp+228h+var_1E8], rax
0x14000a6c1  mov     al, 1
0x14000a6c3  test    al, al
0x14000a6c5  jz      loc_14000A949
0x14000a6cb  lea     rcx, [rsp+228h+var_198]; this
0x14000a6d3  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x14000a6d8  nop
0x14000a6d9  lea     rdx, [rsp+228h+var_198]; struct ATL::CSid *
0x14000a6e1  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a6e6  call    ?GetUser@CAccessToken@ATL@@QEBA_NPEAVCSid@2@@Z; ATL::CAccessToken::GetUser(ATL::CSid *)
0x14000a6eb  test    al, al
0x14000a6ed  jnz     short loc_14000A71E
0x14000a6ef  lea     rcx, [rsp+228h+var_198]; this
0x14000a6f7  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a6fc  nop
0x14000a6fd  mov     [rsp+228h+var_1F0], r14
0x14000a702  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a707  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a70c  nop
0x14000a70d  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a712  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a717  xor     al, al
0x14000a719  jmp     loc_14000A969
0x14000a71e  lea     rcx, [rsp+228h+var_118]; this
0x14000a726  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x14000a72b  nop
0x14000a72c  lea     rdx, [rsp+228h+var_118]; struct ATL::CSid *
0x14000a734  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a739  call    ?GetPrimaryGroup@CAccessToken@ATL@@QEBA_NPEAVCSid@2@@Z; ATL::CAccessToken::GetPrimaryGroup(ATL::CSid *)
0x14000a73e  test    al, al
0x14000a740  jnz     short loc_14000A77F
0x14000a742  lea     rcx, [rsp+228h+var_118]; this
0x14000a74a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a74f  nop
0x14000a750  lea     rcx, [rsp+228h+var_198]; this
0x14000a758  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a75d  nop
0x14000a75e  mov     [rsp+228h+var_1F0], r14
0x14000a763  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a768  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a76d  nop
0x14000a76e  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a773  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a778  xor     al, al
0x14000a77a  jmp     loc_14000A969
0x14000a77f  lea     rdx, [rsp+228h+var_198]; struct ATL::CSid *
0x14000a787  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a78c  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x14000a791  test    al, al
0x14000a793  jnz     short loc_14000A7D2
0x14000a795  lea     rcx, [rsp+228h+var_118]; this
0x14000a79d  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a7a2  nop
0x14000a7a3  lea     rcx, [rsp+228h+var_198]; this
0x14000a7ab  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a7b0  nop
0x14000a7b1  mov     [rsp+228h+var_1F0], r14
0x14000a7b6  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a7bb  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a7c0  nop
0x14000a7c1  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a7c6  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a7cb  xor     al, al
0x14000a7cd  jmp     loc_14000A969
0x14000a7d2  mov     [rsp+228h+var_208], 221h
0x14000a7da  mov     r9d, 20h ; ' '
0x14000a7e0  lea     r8d, [r9-1Eh]; unsigned __int8
0x14000a7e4  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x14000a7eb  lea     rcx, [rsp+228h+var_98]; this
0x14000a7f3  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x14000a7f8  nop
0x14000a7f9  lea     rdx, [rsp+228h+var_98]; struct ATL::CSid *
0x14000a801  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a806  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x14000a80b  mov     dil, al
0x14000a80e  lea     rcx, [rsp+228h+var_98]; this
0x14000a816  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a81b  test    dil, dil
0x14000a81e  jnz     short loc_14000A85D
0x14000a820  lea     rcx, [rsp+228h+var_118]; this
0x14000a828  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a82d  nop
0x14000a82e  lea     rcx, [rsp+228h+var_198]; this
0x14000a836  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a83b  nop
0x14000a83c  mov     [rsp+228h+var_1F0], r14
0x14000a841  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a846  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a84b  nop
0x14000a84c  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a851  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a856  xor     al, al
0x14000a858  jmp     loc_14000A969
0x14000a85d  mov     r9d, 12h
0x14000a863  lea     r8d, [r9-11h]; unsigned __int8
0x14000a867  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x14000a86e  lea     rcx, [rsp+228h+var_98]; this
0x14000a876  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x14000a87b  nop
0x14000a87c  lea     rdx, [rsp+228h+var_98]; struct ATL::CSid *
0x14000a884  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a889  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x14000a88e  mov     dil, al
0x14000a891  lea     rcx, [rsp+228h+var_98]; this
0x14000a899  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a89e  test    dil, dil
0x14000a8a1  jnz     short loc_14000A8E0
0x14000a8a3  lea     rcx, [rsp+228h+var_118]; this
0x14000a8ab  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a8b0  nop
0x14000a8b1  lea     rcx, [rsp+228h+var_198]; this
0x14000a8b9  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a8be  nop
0x14000a8bf  mov     [rsp+228h+var_1F0], r14
0x14000a8c4  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a8c9  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a8ce  nop
0x14000a8cf  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a8d4  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a8d9  xor     al, al
0x14000a8db  jmp     loc_14000A969
0x14000a8e0  lea     rdx, [rsp+228h+var_1D0]; struct ATL::CDacl *
0x14000a8e5  mov     rcx, rbx; this
0x14000a8e8  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x14000a8ed  lea     rdx, [rsp+228h+var_198]; struct ATL::CSid *
0x14000a8f5  mov     rcx, rbx; this
0x14000a8f8  call    ?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z; ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)
0x14000a8fd  lea     rdx, [rsp+228h+var_118]; struct ATL::CSid *
0x14000a905  mov     rcx, rbx; this
0x14000a908  call    ?SetGroup@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z; ATL::CSecurityDesc::SetGroup(ATL::CSid const &,bool)
0x14000a90d  nop
0x14000a90e  lea     rcx, [rsp+228h+var_118]; this
0x14000a916  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a91b  nop
0x14000a91c  lea     rcx, [rsp+228h+var_198]; this
0x14000a924  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14000a929  nop
0x14000a92a  mov     [rsp+228h+var_1F0], r14
0x14000a92f  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a934  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a939  nop
0x14000a93a  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a93f  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a944  nop
0x14000a945  mov     al, 1
0x14000a947  jmp     short loc_14000A969
0x14000a949  mov     [rsp+228h+var_1F0], r14
0x14000a94e  lea     rcx, [rsp+228h+var_1F0]; this
0x14000a953  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x14000a958  nop
0x14000a959  lea     rcx, [rsp+228h+var_1D0]; this
0x14000a95e  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x14000a963  xor     al, al
0x14000a965  jmp     short loc_14000A969
0x14000a967  xor     al, al
0x14000a969  mov     rcx, [rsp+228h+var_18]
0x14000a971  xor     rcx, rsp; StackCookie
0x14000a974  call    __security_check_cookie
0x14000a979  lea     r11, [rsp+228h+var_8]
0x14000a981  mov     rbx, [r11+18h]
0x14000a985  mov     rdi, [r11+20h]
0x14000a989  mov     rsp, r11
0x14000a98c  pop     r14
0x14000a98e  retn
```
