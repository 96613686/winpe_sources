# ?CreateDefaultSecurityDescriptor@Csl@@YAJPEAXKPEAU_GENERIC_MAPPING@@0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@_E$1?DeleteSecurityObjectWrapper@Csl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z

- ea: `0x18002e95c`
- end: `0x18002ebcb`
- name: `?CreateDefaultSecurityDescriptor@Csl@@YAJPEAXKPEAU_GENERIC_MAPPING@@0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@_E$1?DeleteSecurityObjectWrapper@Csl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(PSID Sid, ACCESS_MASK AccessMask, PGENERIC_MAPPING GenericMapping, int, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018120`
- `0x180019900`
- `0x180082e18`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x18000da88`
- `0x18000dab0`
- `0x18002e95c`
- `0x18002ebd4`
- `0x18002ec00`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002e97c`
- `ntdll!RtlLengthSid` at `0x18002e97c`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e9e3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e9e3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002ea2a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002ea2a`
- `ntdll!RtlCreateAcl` at `0x18002e9c1`
- `ntdll!RtlCreateAcl` at `0x18002e9c1`
- `ntdll!RtlNewSecurityObject` at `0x18002ead7`
- `ntdll!RtlNewSecurityObject` at `0x18002ead7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002ea4d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002ea4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eb57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eaa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eb18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eb7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eaa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eb18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002eb7d`

## string_xrefs

- `0x18002e9f8`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002ea86`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002eaee`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18002eba6`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::CreateDefaultSecurityDescriptor(
        PSID Sid,
        ACCESS_MASK AccessMask,
        PGENERIC_MAPPING GenericMapping,
        void *a4,
        Csl **a5)
{
  ULONG v9; // edi
  struct _ACL *v10; // rax
  struct _ACL *v11; // r15
  NTSTATUS Acl; // eax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  int v15; // eax
  NTSTATUS v16; // eax
  void *v17; // rdx
  void *v18; // rdx
  int v19; // edi
  Csl *v20; // r12
  Csl *v21; // rcx
  Csl *v22; // r14
  DWORD LastError; // edi
  void *v24; // rdx
  int Token; // [rsp+20h] [rbp-58h]
  int Tokena; // [rsp+20h] [rbp-58h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+30h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-40h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v31; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v9 = RtlLengthSid(Sid) + 16;
  v10 = (struct _ACL *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x445,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)0x8007000ELL,
      Token);
    return v14;
  }
  memset_0(v10, 0, v9);
  Acl = RtlCreateAcl(v11, v9, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(v11, 2u, AccessMask, Sid);
    if ( Acl >= 0 )
    {
      memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      v31 = 0;
      Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( Acl >= 0 )
      {
        Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
        if ( Acl >= 0 )
        {
          hMem = 0;
          v15 = Csl::DuplicateSecurityDescriptor(SecurityDescriptor);
          v14 = v15;
          if ( v15 >= 0 )
          {
            NewDescriptor = 0;
            v16 = RtlNewSecurityObject(0, hMem, &NewDescriptor, 0, a4, GenericMapping);
            if ( v16 >= 0 )
            {
              v20 = (Csl *)NewDescriptor;
              v21 = 0;
              NewDescriptor = 0;
              v22 = *a5;
              if ( *a5 )
              {
                LastError = GetLastError();
                Csl::DeleteSecurityObjectWrapper(v22, v24);
                SetLastError(LastError);
                v21 = (Csl *)NewDescriptor;
              }
              *a5 = v20;
              if ( v21 )
                Csl::DeleteSecurityObjectWrapper(v21, v17);
              v14 = 0;
            }
            else
            {
              v19 = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x468,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                      (const char *)(unsigned int)v16,
                      Tokena);
              if ( NewDescriptor )
                Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v18);
              v14 = v19;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x45B,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
              (const char *)(unsigned int)v15,
              Token);
          }
          goto LABEL_22;
        }
        v13 = 1110;
      }
      else
      {
        v13 = 1105;
      }
    }
    else
    {
      v13 = 1098;
    }
  }
  else
  {
    v13 = 1096;
  }
  v14 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
          (const char *)(unsigned int)Acl,
          Token);
LABEL_22:
  operator delete(v11, (const struct std::nothrow_t *)8);
  return v14;
}

```

## disassembly

```asm
0x18002e95c  push    rbp
0x18002e95e  push    rbx
0x18002e95f  push    rsi
0x18002e960  push    rdi
0x18002e961  push    r12
0x18002e963  push    r13
0x18002e965  push    r14
0x18002e967  push    r15
0x18002e969  mov     rbp, rsp
0x18002e96c  sub     rsp, 78h
0x18002e970  mov     r12, r9
0x18002e973  mov     r13, r8
0x18002e976  mov     r14d, edx
0x18002e979  mov     rbx, rcx
0x18002e97c  call    cs:__imp_RtlLengthSid
0x18002e983  nop     dword ptr [rax+rax+00h]
0x18002e988  lea     edi, [rax+10h]
0x18002e98b  mov     esi, edi
0x18002e98d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e994  mov     ecx, edi; unsigned __int64
0x18002e996  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002e99b  mov     r15, rax
0x18002e99e  test    rax, rax
0x18002e9a1  jz      loc_18002EB9A
0x18002e9a7  mov     r8d, esi; Size
0x18002e9aa  xor     edx, edx; Val
0x18002e9ac  mov     rcx, rax; void *
0x18002e9af  call    memset_0
0x18002e9b4  mov     esi, 2
0x18002e9b9  mov     r8d, esi; AclRevision
0x18002e9bc  mov     edx, edi; AclSize
0x18002e9be  mov     rcx, r15; Acl
0x18002e9c1  call    cs:__imp_RtlCreateAcl
0x18002e9c8  nop     dword ptr [rax+rax+00h]
0x18002e9cd  test    eax, eax
0x18002e9cf  jns     short loc_18002E9D8
0x18002e9d1  mov     edx, 448h
0x18002e9d6  jmp     short loc_18002E9F8
0x18002e9d8  mov     r9, rbx; Sid
0x18002e9db  mov     r8d, r14d; AccessMask
0x18002e9de  mov     edx, esi; Revision
0x18002e9e0  mov     rcx, r15; Acl
0x18002e9e3  call    cs:__imp_RtlAddAccessAllowedAce
0x18002e9ea  nop     dword ptr [rax+rax+00h]
0x18002e9ef  test    eax, eax
0x18002e9f1  jns     short loc_18002EA12
0x18002e9f3  mov     edx, 44Ah; void *
0x18002e9f8  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002e9ff  mov     r9d, eax; char *
0x18002ea02  mov     rcx, [rbp+40h]; this
0x18002ea06  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002ea0b  mov     ebx, eax
0x18002ea0d  jmp     loc_18002EB8B
0x18002ea12  xorps   xmm0, xmm0
0x18002ea15  xor     eax, eax
0x18002ea17  movups  [rbp+SecurityDescriptor], xmm0
0x18002ea1b  movups  [rbp+var_28], xmm0
0x18002ea1f  mov     [rbp+var_18], rax
0x18002ea23  lea     edx, [rax+1]; Revision
0x18002ea26  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002ea2a  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002ea31  nop     dword ptr [rax+rax+00h]
0x18002ea36  test    eax, eax
0x18002ea38  jns     short loc_18002EA41
0x18002ea3a  mov     edx, 451h
0x18002ea3f  jmp     short loc_18002E9F8
0x18002ea41  xor     r9d, r9d; DaclDefaulted
0x18002ea44  mov     r8, r15; Dacl
0x18002ea47  mov     dl, 1; DaclPresent
0x18002ea49  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002ea4d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18002ea54  nop     dword ptr [rax+rax+00h]
0x18002ea59  test    eax, eax
0x18002ea5b  jns     short loc_18002EA64
0x18002ea5d  mov     edx, 456h
0x18002ea62  jmp     short loc_18002E9F8
0x18002ea64  mov     [rbp+hMem], 0
0x18002ea6c  lea     rdx, [rbp+hMem]
0x18002ea70  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18002ea74  call    ?DuplicateSecurityDescriptor@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Csl::DuplicateSecurityDescriptor(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18002ea79  mov     ebx, eax
0x18002ea7b  test    eax, eax
0x18002ea7d  jns     short loc_18002EAB5
0x18002ea7f  mov     rcx, [rbp+40h]; this
0x18002ea83  mov     r9d, eax; char *
0x18002ea86  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ea8d  mov     edx, 45Bh; void *
0x18002ea92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ea97  mov     rcx, [rbp+hMem]; hMem
0x18002ea9b  test    rcx, rcx
0x18002ea9e  jz      loc_18002EB8B
0x18002eaa4  call    cs:__imp_LocalFree
0x18002eaab  nop     dword ptr [rax+rax+00h]
0x18002eab0  jmp     loc_18002EB8B
0x18002eab5  mov     [rbp+NewDescriptor], 0
0x18002eabd  mov     [rsp+78h+GenericMapping], r13; GenericMapping
0x18002eac2  mov     [rsp+78h+Token], r12; int
0x18002eac7  xor     r9d, r9d; IsDirectoryObject
0x18002eaca  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x18002eace  mov     rbx, [rbp+hMem]
0x18002ead2  mov     rdx, rbx; CreatorDescriptor
0x18002ead5  xor     ecx, ecx; ParentDescriptor
0x18002ead7  call    cs:__imp_RtlNewSecurityObject
0x18002eade  nop     dword ptr [rax+rax+00h]
0x18002eae3  test    eax, eax
0x18002eae5  jns     short loc_18002EB28
0x18002eae7  mov     rcx, [rbp+40h]; this
0x18002eaeb  mov     r9d, eax; char *
0x18002eaee  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002eaf5  mov     edx, 468h; void *
0x18002eafa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002eaff  mov     edi, eax
0x18002eb01  mov     rcx, [rbp+NewDescriptor]; this
0x18002eb05  test    rcx, rcx
0x18002eb08  jz      short loc_18002EB10
0x18002eb0a  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x18002eb0f  nop
0x18002eb10  test    rbx, rbx
0x18002eb13  jz      short loc_18002EB24
0x18002eb15  mov     rcx, rbx; hMem
0x18002eb18  call    cs:__imp_LocalFree
0x18002eb1f  nop     dword ptr [rax+rax+00h]
0x18002eb24  mov     ebx, edi
0x18002eb26  jmp     short loc_18002EB8B
0x18002eb28  mov     r12, [rbp+NewDescriptor]
0x18002eb2c  xor     ecx, ecx
0x18002eb2e  mov     [rbp+NewDescriptor], rcx
0x18002eb32  mov     rsi, [rbp+arg_20]
0x18002eb36  mov     r14, [rsi]
0x18002eb39  test    r14, r14
0x18002eb3c  jz      short loc_18002EB67
0x18002eb3e  call    cs:__imp_GetLastError
0x18002eb45  nop     dword ptr [rax+rax+00h]
0x18002eb4a  mov     edi, eax
0x18002eb4c  mov     rcx, r14; this
0x18002eb4f  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x18002eb54  nop
0x18002eb55  mov     ecx, edi; dwErrCode
0x18002eb57  call    cs:__imp_SetLastError
0x18002eb5e  nop     dword ptr [rax+rax+00h]
0x18002eb63  mov     rcx, [rbp+NewDescriptor]; this
0x18002eb67  mov     [rsi], r12
0x18002eb6a  test    rcx, rcx
0x18002eb6d  jz      short loc_18002EB75
0x18002eb6f  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x18002eb74  nop
0x18002eb75  test    rbx, rbx
0x18002eb78  jz      short loc_18002EB89
0x18002eb7a  mov     rcx, rbx; hMem
0x18002eb7d  call    cs:__imp_LocalFree
0x18002eb84  nop     dword ptr [rax+rax+00h]
0x18002eb89  xor     ebx, ebx
0x18002eb8b  mov     edx, 8; struct std::nothrow_t *
0x18002eb90  mov     rcx, r15; void *
0x18002eb93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002eb98  jmp     short loc_18002EBB7
0x18002eb9a  mov     rcx, [rbp+40h]; this
0x18002eb9e  mov     ebx, 8007000Eh
0x18002eba3  mov     r9d, ebx; char *
0x18002eba6  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ebad  mov     edx, 445h; void *
0x18002ebb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ebb7  mov     eax, ebx
0x18002ebb9  add     rsp, 78h
0x18002ebbd  pop     r15
0x18002ebbf  pop     r14
0x18002ebc1  pop     r13
0x18002ebc3  pop     r12
0x18002ebc5  pop     rdi
0x18002ebc6  pop     rsi
0x18002ebc7  pop     rbx
0x18002ebc8  pop     rbp
0x18002ebc9  retn
```
