# ParseSecurityDescriptor(void *,ulong *,void * *,void * *,_ACL * *,_ACL * *)

- ea: `0x14006e330`
- end: `0x14006e4cd`
- name: `?ParseSecurityDescriptor@@YAJPEAXPEAKPEAPEAX2PEAPEAU_ACL@@3@Z`
- size: `413`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, unsigned int *@<rdx>, void **@<r8>, void **@<r9>, struct _ACL **, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006dfb4`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006e330`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14006e3dd`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14006e3dd`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14006e3bb`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14006e3bb`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14006e39c`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14006e39c`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14006e384`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14006e384`
- `KERNEL32!IsDebuggerPresent` at `0x14006e437`
- `KERNEL32!IsDebuggerPresent` at `0x14006e437`

## string_xrefs

- `0x14006e414`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`
- `0x14006e41b`: `secinfoTemp != 0`
- `0x14006e404`: `ParseSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall ParseSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        unsigned int *a2,
        void **a3,
        void **a4,
        struct _ACL **a5,
        struct _ACL **a6)
{
  BOOL SecurityDescriptorOwner; // ebx
  int v11; // edi
  unsigned int v12; // ebx
  struct _ACL *v13; // rcx
  WINBOOL bOwnerDefaulted; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-2Ch] BYREF
  PACL pDacl; // [rsp+48h] [rbp-28h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-20h] BYREF
  PSID pOwner; // [rsp+58h] [rbp-18h] BYREF
  PSID pGroup; // [rsp+60h] [rbp-10h] BYREF

  bDaclPresent = 0;
  bOwnerDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  SecurityDescriptorOwner = GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted);
  v11 = SecurityDescriptorOwner | 2;
  if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted) )
    v11 = SecurityDescriptorOwner;
  if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) && bDaclPresent )
    v11 |= 4u;
  if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bDaclPresent, &pSacl, &bOwnerDefaulted) && bDaclPresent )
    v11 |= 8u;
  if ( v11 )
  {
    v12 = 0;
    v13 = pDacl;
    *a2 = v11;
    *a5 = v13;
    *a6 = pSacl;
    *a3 = pOwner;
    *a4 = pGroup;
  }
  else
  {
    v12 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
      0x47Eu,
      L"ParseSecurityDescriptor",
      L"CBRAEx",
      L"secinfoTemp != 0",
      -2147024809);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
        1150,
        L"ParseSecurityDescriptor",
        L"CBRAEx",
        L"secinfoTemp != 0",
        -2147024809);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
        1150,
        L"ParseSecurityDescriptor",
        L"CBRAEx",
        L"secinfoTemp != 0",
        -2147024809);
  }
  return v12;
}

```

## disassembly

```asm
0x14006e330  push    rbp
0x14006e332  push    rbx
0x14006e333  push    rsi
0x14006e334  push    rdi
0x14006e335  push    r12
0x14006e337  push    r14
0x14006e339  push    r15
0x14006e33b  mov     rbp, rsp
0x14006e33e  sub     rsp, 70h
0x14006e342  mov     r15, r8
0x14006e345  mov     [rbp+bDaclPresent], 0
0x14006e34c  mov     r12, rdx
0x14006e34f  mov     [rbp+bOwnerDefaulted], 0
0x14006e356  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x14006e35a  mov     [rbp+pOwner], 0
0x14006e362  lea     rdx, [rbp+pOwner]; pOwner
0x14006e366  mov     [rbp+pGroup], 0
0x14006e36e  mov     r14, r9
0x14006e371  mov     [rbp+pDacl], 0
0x14006e379  mov     rsi, rcx
0x14006e37c  mov     [rbp+pSacl], 0
0x14006e384  call    cs:__imp_GetSecurityDescriptorOwner
0x14006e38a  xor     ebx, ebx
0x14006e38c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x14006e390  test    eax, eax
0x14006e392  lea     rdx, [rbp+pGroup]; pGroup
0x14006e396  mov     rcx, rsi; pSecurityDescriptor
0x14006e399  setnz   bl
0x14006e39c  call    cs:__imp_GetSecurityDescriptorGroup
0x14006e3a2  mov     edi, ebx
0x14006e3a4  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x14006e3a8  or      edi, 2
0x14006e3ab  lea     r8, [rbp+pDacl]; pDacl
0x14006e3af  test    eax, eax
0x14006e3b1  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x14006e3b5  mov     rcx, rsi; pSecurityDescriptor
0x14006e3b8  cmovz   edi, ebx
0x14006e3bb  call    cs:__imp_GetSecurityDescriptorDacl
0x14006e3c1  test    eax, eax
0x14006e3c3  jz      short loc_14006E3CE
0x14006e3c5  cmp     [rbp+bDaclPresent], 0
0x14006e3c9  jz      short loc_14006E3CE
0x14006e3cb  or      edi, 4
0x14006e3ce  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x14006e3d2  mov     rcx, rsi; pSecurityDescriptor
0x14006e3d5  lea     r8, [rbp+pSacl]; pSacl
0x14006e3d9  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x14006e3dd  call    cs:__imp_GetSecurityDescriptorSacl
0x14006e3e3  test    eax, eax
0x14006e3e5  jz      short loc_14006E3F0
0x14006e3e7  cmp     [rbp+bDaclPresent], 0
0x14006e3eb  jz      short loc_14006E3F0
0x14006e3ed  or      edi, 8
0x14006e3f0  test    edi, edi
0x14006e3f2  jnz     loc_14006E492
0x14006e3f8  mov     ebx, 80070057h
0x14006e3fd  lea     r12, aCbraex; "CBRAEx"
0x14006e404  lea     r14, aParsesecurityd; "ParseSecurityDescriptor"
0x14006e40b  mov     [rsp+70h+var_48], ebx; int
0x14006e40f  mov     edi, 47Eh
0x14006e414  lea     rsi, aTermsrvWmsSrcC_27; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006e41b  lea     r15, aSecinfotemp0; "secinfoTemp != 0"
0x14006e422  mov     r9, r12; unsigned __int16 *
0x14006e425  mov     r8, r14; unsigned __int16 *
0x14006e428  mov     [rsp+70h+var_50], r15; unsigned __int16 *
0x14006e42d  mov     edx, edi; unsigned int
0x14006e42f  mov     rcx, rsi; unsigned __int16 *
0x14006e432  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006e437  call    cs:__imp_IsDebuggerPresent
0x14006e43d  test    eax, eax
0x14006e43f  jz      short loc_14006E46D
0x14006e441  mov     [rsp+70h+var_38], ebx
0x14006e445  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006e44c  mov     [rsp+70h+var_40], r15
0x14006e451  mov     r9d, edi
0x14006e454  mov     qword ptr [rsp+70h+var_48], r12
0x14006e459  mov     r8, rsi
0x14006e45c  mov     ecx, 2; unsigned __int8
0x14006e461  mov     [rsp+70h+var_50], r14
0x14006e466  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006e46b  jmp     short loc_14006E4BC
0x14006e46d  mov     dword ptr [rsp+70h+var_40], ebx
0x14006e471  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006e478  mov     qword ptr [rsp+70h+var_48], r15
0x14006e47d  mov     r9, r14
0x14006e480  mov     r8d, edi
0x14006e483  mov     [rsp+70h+var_50], r12
0x14006e488  mov     rdx, rsi
0x14006e48b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006e490  jmp     short loc_14006E4BC
0x14006e492  mov     rdx, [rbp+arg_20]
0x14006e496  xor     ebx, ebx
0x14006e498  mov     rcx, [rbp+pDacl]
0x14006e49c  mov     [r12], edi
0x14006e4a0  mov     [rdx], rcx
0x14006e4a3  mov     rcx, [rbp+pSacl]
0x14006e4a7  mov     rdx, [rbp+arg_28]
0x14006e4ab  mov     [rdx], rcx
0x14006e4ae  mov     rcx, [rbp+pOwner]
0x14006e4b2  mov     [r15], rcx
0x14006e4b5  mov     rcx, [rbp+pGroup]
0x14006e4b9  mov     [r14], rcx
0x14006e4bc  mov     eax, ebx
0x14006e4be  add     rsp, 70h
0x14006e4c2  pop     r15
0x14006e4c4  pop     r14
0x14006e4c6  pop     r12
0x14006e4c8  pop     rdi
0x14006e4c9  pop     rsi
0x14006e4ca  pop     rbx
0x14006e4cb  pop     rbp
0x14006e4cc  retn
```
