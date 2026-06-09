# Broker::CreateStateSecurityDescriptor(void *,ulong,void *,ulong,void * *)

- ea: `0x18000bcc0`
- end: `0x18000beec`
- name: `?CreateStateSecurityDescriptor@Broker@@YAJPEAXK0KPEAPEAX@Z`
- size: `556`
- prototype: `__int64 __usercall@<rax>(PSID Owner@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bc2c`

## callees

- `0x18000bcc0`
- `0x180015af0`
- `0x1800165c2`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x18000be25`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000be25`
- `ntdll!RtlCreateAcl` at `0x18000bd48`
- `ntdll!RtlCreateAcl` at `0x18000bd48`
- `ntdll!RtlInitializeSidEx` at `0x18000bde8`
- `ntdll!RtlInitializeSidEx` at `0x18000bde8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000be9f`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000be9f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bd6f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bdc4`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000be0b`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bd6f`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000bdc4`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000be0b`
- `ntdll!NtQueryInformationToken` at `0x18000bda0`
- `ntdll!NtQueryInformationToken` at `0x18000bda0`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000be3f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000be3f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000be56`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000be56`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000be67`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000be67`
- `ntdll!RtlFreeHeap` at `0x18000bee4`
- `ntdll!RtlFreeHeap` at `0x18000bee4`
- `ntdll!RtlAllocateHeap` at `0x18000be84`
- `ntdll!RtlAllocateHeap` at `0x18000be84`

## pseudocode

```c
__int64 __fastcall Broker::CreateStateSecurityDescriptor(PSID Owner, void *a2, __int64 a3, void *a4, _QWORD *a5)
{
  NTSTATUS v6; // ebx
  PVOID Heap; // rax
  void *v8; // rdi
  ULONG BufferLength; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-CCh] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h]
  PSID TokenInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v16; // [rsp+C4h] [rbp-3Ch]
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  _ACL Acl; // [rsp+120h] [rbp+20h] BYREF

  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  memset_0(Sid, 0, 0x44u);
  v15 = 0;
  v16 = 1280;
  v13 = 0;
  BufferLength = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v6 = RtlCreateAcl(&Acl, 0x400u, 2u);
  if ( v6 >= 0 )
  {
    if ( !Owner || (v6 = RtlAddAccessAllowedAce(&Acl, 2u, 0x80000000, Owner), v6 >= 0) )
    {
      v6 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, TokenInformation, 0x58u, &ReturnLength);
      if ( v6 >= 0 )
      {
        v6 = RtlAddAccessAllowedAce(&Acl, 2u, 0xC0010000, TokenInformation[0]);
        if ( v6 >= 0 )
        {
          v6 = RtlInitializeSidEx(Sid, &v15, 1, 18);
          if ( v6 >= 0 )
          {
            v6 = RtlAddAccessAllowedAce(&Acl, 2u, 0x80000000, Sid);
            if ( v6 >= 0 )
            {
              v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
              if ( v6 >= 0 )
              {
                v6 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Acl, 0);
                if ( v6 >= 0 )
                {
                  v6 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
                  if ( v6 >= 0 )
                  {
                    BufferLength = RtlLengthSecurityDescriptor(SecurityDescriptor);
                    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
                    v8 = Heap;
                    if ( Heap )
                    {
                      v6 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, Heap, &BufferLength);
                      if ( v6 < 0 )
                        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
                      else
                        *a5 = v8;
                    }
                    else
                    {
                      return (unsigned int)-1073741801;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000bcc0  push    rbp
0x18000bcc2  push    rbx
0x18000bcc3  push    rsi
0x18000bcc4  push    rdi
0x18000bcc5  lea     rbp, [rsp-438h]
0x18000bccd  sub     rsp, 538h
0x18000bcd4  mov     rax, cs:__security_cookie
0x18000bcdb  xor     rax, rsp
0x18000bcde  mov     [rbp+450h+var_30], rax
0x18000bce5  mov     rsi, qword ptr [rbp+450h+arg_20]
0x18000bcec  mov     rdi, rcx
0x18000bcef  lea     rcx, [rsp+550h+TokenInformation]; void *
0x18000bcf4  xor     edx, edx; Val
0x18000bcf6  mov     r8d, 58h ; 'X'; Size
0x18000bcfc  call    memset_0
0x18000bd01  xor     ebx, ebx
0x18000bd03  lea     rcx, [rbp+450h+Sid]; void *
0x18000bd07  xor     edx, edx; Val
0x18000bd09  mov     [rsp+550h+var_51C], ebx
0x18000bd0d  mov     r8d, 44h ; 'D'; Size
0x18000bd13  call    memset_0
0x18000bd18  xorps   xmm0, xmm0
0x18000bd1b  mov     [rbp+450h+var_490], ebx
0x18000bd1e  xor     eax, eax
0x18000bd20  mov     [rbp+450h+var_48C], 500h
0x18000bd26  mov     edx, 400h; AclSize
0x18000bd2b  mov     [rsp+550h+var_4F8], rax
0x18000bd30  mov     r8d, 2; AclRevision
0x18000bd36  mov     [rsp+550h+BufferLength], ebx
0x18000bd3a  lea     rcx, [rbp+450h+Acl]; Acl
0x18000bd3e  movups  [rsp+550h+SecurityDescriptor], xmm0
0x18000bd43  movups  [rsp+550h+var_508], xmm0
0x18000bd48  call    cs:__imp_RtlCreateAcl
0x18000bd4e  mov     ebx, eax
0x18000bd50  test    eax, eax
0x18000bd52  js      loc_18000BEAE
0x18000bd58  test    rdi, rdi
0x18000bd5b  jz      short loc_18000BD7F
0x18000bd5d  mov     r9, rdi; Sid
0x18000bd60  lea     rcx, [rbp+450h+Acl]; Acl
0x18000bd64  mov     edx, 2; Revision
0x18000bd69  mov     r8d, 80000000h; AccessMask
0x18000bd6f  call    cs:__imp_RtlAddAccessAllowedAce
0x18000bd75  mov     ebx, eax
0x18000bd77  test    eax, eax
0x18000bd79  js      loc_18000BEAE
0x18000bd7f  lea     rax, [rsp+550h+var_51C]
0x18000bd84  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18000bd8a  lea     r8, [rsp+550h+TokenInformation]; TokenInformation
0x18000bd8f  mov     [rsp+550h+ReturnLength], rax; ReturnLength
0x18000bd94  mov     edx, 1; TokenInformationClass
0x18000bd99  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18000bda0  call    cs:__imp_NtQueryInformationToken
0x18000bda6  mov     ebx, eax
0x18000bda8  test    eax, eax
0x18000bdaa  js      loc_18000BEAE
0x18000bdb0  mov     r9, [rsp+550h+TokenInformation]; Sid
0x18000bdb5  lea     rcx, [rbp+450h+Acl]; Acl
0x18000bdb9  mov     edx, 2; Revision
0x18000bdbe  mov     r8d, 0C0010000h; AccessMask
0x18000bdc4  call    cs:__imp_RtlAddAccessAllowedAce
0x18000bdca  mov     ebx, eax
0x18000bdcc  test    eax, eax
0x18000bdce  js      loc_18000BEAE
0x18000bdd4  mov     r9d, 12h
0x18000bdda  lea     rdx, [rbp+450h+var_490]
0x18000bdde  mov     r8d, 1
0x18000bde4  lea     rcx, [rbp+450h+Sid]
0x18000bde8  call    cs:__imp_RtlInitializeSidEx
0x18000bdee  mov     ebx, eax
0x18000bdf0  test    eax, eax
0x18000bdf2  js      loc_18000BEAE
0x18000bdf8  lea     r9, [rbp+450h+Sid]; Sid
0x18000bdfc  mov     edx, 2; Revision
0x18000be01  mov     r8d, 80000000h; AccessMask
0x18000be07  lea     rcx, [rbp+450h+Acl]; Acl
0x18000be0b  call    cs:__imp_RtlAddAccessAllowedAce
0x18000be11  mov     ebx, eax
0x18000be13  test    eax, eax
0x18000be15  js      loc_18000BEAE
0x18000be1b  mov     edx, 1; Revision
0x18000be20  lea     rcx, [rsp+550h+SecurityDescriptor]; SecurityDescriptor
0x18000be25  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000be2b  mov     ebx, eax
0x18000be2d  test    eax, eax
0x18000be2f  js      short loc_18000BEAE
0x18000be31  xor     r9d, r9d; DaclDefaulted
0x18000be34  lea     r8, [rbp+450h+Acl]; Dacl
0x18000be38  mov     dl, 1; DaclPresent
0x18000be3a  lea     rcx, [rsp+550h+SecurityDescriptor]; SecurityDescriptor
0x18000be3f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000be45  mov     ebx, eax
0x18000be47  test    eax, eax
0x18000be49  js      short loc_18000BEAE
0x18000be4b  xor     r8d, r8d; OwnerDefaulted
0x18000be4e  lea     rcx, [rsp+550h+SecurityDescriptor]; SecurityDescriptor
0x18000be53  mov     rdx, rdi; Owner
0x18000be56  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18000be5c  mov     ebx, eax
0x18000be5e  test    eax, eax
0x18000be60  js      short loc_18000BEAE
0x18000be62  lea     rcx, [rsp+550h+SecurityDescriptor]; SecurityDescriptor
0x18000be67  call    cs:__imp_RtlLengthSecurityDescriptor
0x18000be6d  mov     r8d, eax; Size
0x18000be70  xor     edx, edx; Flags
0x18000be72  mov     [rsp+550h+BufferLength], r8d
0x18000be77  mov     rcx, gs:60h
0x18000be80  mov     rcx, [rcx+30h]; HeapHandle
0x18000be84  call    cs:__imp_RtlAllocateHeap
0x18000be8a  mov     rdi, rax
0x18000be8d  test    rax, rax
0x18000be90  jz      short loc_18000BECB
0x18000be92  lea     r8, [rsp+550h+BufferLength]; BufferLength
0x18000be97  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x18000be9a  lea     rcx, [rsp+550h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18000be9f  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18000bea5  mov     ebx, eax
0x18000bea7  test    eax, eax
0x18000bea9  js      short loc_18000BED2
0x18000beab  mov     [rsi], rdi
0x18000beae  mov     eax, ebx
0x18000beb0  mov     rcx, [rbp+450h+var_30]
0x18000beb7  xor     rcx, rsp; StackCookie
0x18000beba  call    __security_check_cookie
0x18000bebf  add     rsp, 538h
0x18000bec6  pop     rdi
0x18000bec7  pop     rsi
0x18000bec8  pop     rbx
0x18000bec9  pop     rbp
0x18000beca  retn
0x18000becb  mov     ebx, 0C0000017h
0x18000bed0  jmp     short loc_18000BEAE
0x18000bed2  mov     rcx, gs:60h
0x18000bedb  mov     r8, rdi; P
0x18000bede  xor     edx, edx; Flags
0x18000bee0  mov     rcx, [rcx+30h]; HeapHandle
0x18000bee4  call    cs:__imp_RtlFreeHeap
0x18000beea  jmp     short loc_18000BEAE
```
