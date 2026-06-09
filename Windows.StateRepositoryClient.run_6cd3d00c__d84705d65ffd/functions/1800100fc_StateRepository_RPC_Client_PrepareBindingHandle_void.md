# StateRepository::RPC::Client::PrepareBindingHandle(void)

- ea: `0x1800100fc`
- end: `0x18001027c`
- name: `?PrepareBindingHandle@Client@RPC@StateRepository@@SAJXZ`
- size: `384`
- prototype: `__int64(void)`
- caller_count: `11`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010b00`
- `0x180010e50`
- `0x180010f30`
- `0x180011150`
- `0x1800112b0`
- `0x180011770`
- `0x180011940`
- `0x180011a80`
- `0x180011bc0`
- `0x180011ca0`
- `0x180011dc0`

## callees

- `0x1800075c4`
- `0x180009530`
- `0x1800100fc`
- `0x180010854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001010c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001010c`
- `RPCRT4!RpcBindingCreateW` at `0x180010205`
- `RPCRT4!RpcBindingCreateW` at `0x180010205`
- `RPCRT4!RpcBindingBind` at `0x18001023b`
- `RPCRT4!RpcBindingBind` at `0x18001023b`
- `RPCRT4!RpcBindingFree` at `0x18001024c`
- `RPCRT4!RpcBindingFree` at `0x18001024c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800101c9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800101c9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800101a9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800101a9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180010145`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180010145`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001018b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001018b`

## pseudocode

```c
__int64 StateRepository::RPC::Client::PrepareBindingHandle(void)
{
  const char *v0; // r9
  __int64 v1; // rdx
  int LastError; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int pSid; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+48h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(&StateRepository::RPC::Client::s_bindingLock);
  v12 = &StateRepository::RPC::Client::s_bindingLock;
  if ( IStateRepositoryServer_IfHandle )
    goto LABEL_20;
  if ( qword_1800356D0 )
  {
LABEL_14:
    Binding = 0;
    v4 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
    if ( v4 )
    {
      v5 = (const char *)v4;
      v6 = 56;
LABEL_16:
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v6,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
                    v5,
                    pSid);
      goto LABEL_6;
    }
    v7 = RpcBindingBind(0, Binding, qword_18002AF30);
    if ( v7 )
    {
      RpcBindingFree(&Binding);
      v5 = (const char *)v7;
      v6 = 61;
      goto LABEL_16;
    }
    IStateRepositoryServer_IfHandle = (__int64)Binding;
LABEL_20:
    v3 = 0;
    goto LABEL_21;
  }
  if ( InitializeAcl(&pDacl, 0x20u, 2u) )
  {
    if ( !AddAccessAllowedAceEx(&pDacl, 2u, 3u, 0x10000000u, &qword_180035248) )
    {
      v1 = 49;
      goto LABEL_5;
    }
    if ( !InitializeSecurityDescriptor(qword_1800356D8, 1u) )
    {
      v1 = 50;
      goto LABEL_5;
    }
    if ( !SetSecurityDescriptorDacl(qword_1800356D8, 1, &pDacl, 0) )
    {
      v1 = 51;
      goto LABEL_5;
    }
    qword_1800356D0 = (__int64)qword_1800356D8;
    goto LABEL_14;
  }
  v1 = 47;
LABEL_5:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v1,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_rpc.cpp",
                v0);
LABEL_6:
  v3 = LastError;
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  return v3;
}

```

## disassembly

```asm
0x1800100fc  push    rbx
0x1800100fe  sub     rsp, 30h
0x180010102  lea     rbx, ?s_bindingLock@Client@RPC@StateRepository@@2Vsrwlock@wil@@A; wil::srwlock StateRepository::RPC::Client::s_bindingLock
0x180010109  mov     rcx, rbx; SRWLock
0x18001010c  call    cs:__imp_AcquireSRWLockExclusive
0x180010112  cmp     cs:IStateRepositoryServer_IfHandle, 0
0x18001011a  mov     [rsp+38h+arg_8], rbx
0x18001011f  jnz     loc_180010268
0x180010125  cmp     cs:qword_1800356D0, 0
0x18001012d  jnz     loc_1800101E2
0x180010133  mov     ebx, 2
0x180010138  lea     rcx, pDacl; pAcl
0x18001013f  mov     r8d, ebx; dwAclRevision
0x180010142  lea     edx, [rbx+1Eh]; nAclLength
0x180010145  call    cs:__imp_InitializeAcl
0x18001014b  test    eax, eax
0x18001014d  jnz     short loc_18001016A
0x18001014f  lea     edx, [rbx+2Dh]; void *
0x180010152  mov     rcx, [rsp+38h]; this
0x180010157  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x18001015e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010163  mov     ebx, eax
0x180010165  jmp     loc_18001026A
0x18001016a  lea     rax, qword_180035248
0x180010171  mov     r9d, 10000000h; AccessMask
0x180010177  mov     r8d, 3; AceFlags
0x18001017d  mov     qword ptr [rsp+38h+pSid], rax; unsigned int
0x180010182  mov     edx, ebx; dwAceRevision
0x180010184  lea     rcx, pDacl; pAcl
0x18001018b  call    cs:__imp_AddAccessAllowedAceEx
0x180010191  test    eax, eax
0x180010193  jnz     short loc_18001019A
0x180010195  lea     edx, [rax+31h]
0x180010198  jmp     short loc_180010152
0x18001019a  lea     rbx, qword_1800356D8
0x1800101a1  mov     edx, 1; dwRevision
0x1800101a6  mov     rcx, rbx; pSecurityDescriptor
0x1800101a9  call    cs:__imp_InitializeSecurityDescriptor
0x1800101af  test    eax, eax
0x1800101b1  jnz     short loc_1800101B8
0x1800101b3  lea     edx, [rax+32h]
0x1800101b6  jmp     short loc_180010152
0x1800101b8  xor     r9d, r9d; bDaclDefaulted
0x1800101bb  lea     r8, pDacl; pDacl
0x1800101c2  mov     rcx, rbx; pSecurityDescriptor
0x1800101c5  lea     edx, [r9+1]; bDaclPresent
0x1800101c9  call    cs:__imp_SetSecurityDescriptorDacl
0x1800101cf  test    eax, eax
0x1800101d1  jnz     short loc_1800101DB
0x1800101d3  lea     edx, [rax+33h]
0x1800101d6  jmp     loc_180010152
0x1800101db  mov     cs:qword_1800356D0, rbx
0x1800101e2  lea     r9, [rsp+38h+Binding]; Binding
0x1800101e7  mov     [rsp+38h+Binding], 0
0x1800101f0  lea     r8, Options; Options
0x1800101f7  lea     rdx, Security; Security
0x1800101fe  lea     rcx, Template; Template
0x180010205  call    cs:__imp_RpcBindingCreateW
0x18001020b  test    eax, eax
0x18001020d  jz      short loc_18001022D
0x18001020f  mov     r9d, eax; char *
0x180010212  mov     edx, 38h ; '8'; void *
0x180010217  mov     rcx, [rsp+38h]; this
0x18001021c  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180010223  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010228  jmp     loc_180010163
0x18001022d  mov     rdx, [rsp+38h+Binding]; Binding
0x180010232  lea     r8, qword_18002AF30; IfSpec
0x180010239  xor     ecx, ecx; pAsync
0x18001023b  call    cs:__imp_RpcBindingBind
0x180010241  mov     ebx, eax
0x180010243  test    eax, eax
0x180010245  jz      short loc_18001025C
0x180010247  lea     rcx, [rsp+38h+Binding]; Binding
0x18001024c  call    cs:__imp_RpcBindingFree
0x180010252  mov     r9d, ebx
0x180010255  mov     edx, 3Dh ; '='
0x18001025a  jmp     short loc_180010217
0x18001025c  mov     rax, [rsp+38h+Binding]
0x180010261  mov     cs:IStateRepositoryServer_IfHandle, rax
0x180010268  xor     ebx, ebx
0x18001026a  lea     rcx, [rsp+38h+arg_8]
0x18001026f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010274  mov     eax, ebx
0x180010276  add     rsp, 30h
0x18001027a  pop     rbx
0x18001027b  retn
```
