# StorageNotify::Init(void *)

- ea: `0x18001e658`
- end: `0x18001e8cc`
- name: `?Init@StorageNotify@@QEAAJPEAX@Z`
- size: `628`
- prototype: `int(StorageNotify *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025420`

## callees

- `0x180001174`
- `0x18000d030`
- `0x18001e658`
- `0x18001e8d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e89d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e89d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001e7ba`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001e7ba`
- `ntdll!RtlCreateAcl` at `0x18001e77b`
- `ntdll!RtlCreateAcl` at `0x18001e77b`
- `ntdll!RtlFreeSid` at `0x18001e874`
- `ntdll!RtlFreeSid` at `0x18001e883`
- `ntdll!RtlFreeSid` at `0x18001e874`
- `ntdll!RtlFreeSid` at `0x18001e883`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001e793`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001e7ab`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001e793`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001e7ab`
- `ntdll!RtlLengthSid` at `0x18001e72f`
- `ntdll!RtlLengthSid` at `0x18001e73b`
- `ntdll!RtlLengthSid` at `0x18001e72f`
- `ntdll!RtlLengthSid` at `0x18001e73b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001e6ec`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001e725`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001e6ec`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001e725`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001e7cc`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18001e7cc`
- `ntdll!RtlFreeHeap` at `0x18001e865`
- `ntdll!RtlFreeHeap` at `0x18001e865`
- `ntdll!RtlAllocateHeap` at `0x18001e758`
- `ntdll!RtlAllocateHeap` at `0x18001e758`

## pseudocode

```c
__int64 __fastcall StorageNotify::Init(StorageNotify *this, void *a2)
{
  ULONG v4; // ebx
  ULONG v5; // ebx
  struct _ACL *Heap; // rax
  struct _ACL *v7; // rsi
  StorageNotify *v9; // rcx
  int *v10; // r9
  StorageNotify *v11; // rcx
  int v12; // ebx
  int *v13; // r9
  StorageNotify *v14; // rcx
  StorageNotify *v15; // rcx
  int v16; // edi
  PSID Sid; // [rsp+60h] [rbp-29h] BYREF
  PSID v18; // [rsp+68h] [rbp-21h] BYREF
  int v19; // [rsp+70h] [rbp-19h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v21; // [rsp+98h] [rbp+Fh]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A0h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v23; // [rsp+A8h] [rbp+1Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  v21 = 0;
  v18 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v23.Value = 0;
  *(_WORD *)&v23.Value[4] = 256;
  RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  RtlAllocateAndInitializeSid(&v23, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v18);
  v4 = RtlLengthSid(v18);
  v5 = RtlLengthSid(Sid) + 32 + v4;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  v7 = Heap;
  if ( !Heap )
    return 3221225626LL;
  RtlCreateAcl(Heap, v5, 2u);
  RtlAddAccessAllowedAce(v7, 2u, 0x1F0003u, Sid);
  RtlAddAccessAllowedAce(v7, 2u, 0x120001u, v18);
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v7, 0);
  v12 = StorageNotify::PublishState(v9, WNF_OSWN_STORAGE_FREE_SPACE_CHANGE, *(_DWORD *)this, v10);
  if ( v12 < 0
    || (v12 = StorageNotify::PublishState(v11, WNF_OSWN_STORAGE_PRESENCE_CHANGE, *(_DWORD *)this, v13), v12 < 0)
    || (v12 = StorageNotify::PublishState(v14, WNF_OSWN_STORAGE_TEMP_CLEANUP_CHANGE, *(_DWORD *)this, v13), v12 < 0)
    || (v12 = StorageNotify::PublishState(v15, WNF_OSWN_STORAGE_VOLUME_STATUS_CHANGE, *(_DWORD *)this, v13), v12 < 0) )
  {
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      v19 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BF000,
        (__int64)word_1800A58F2,
        0,
        (__int64)v13,
        (__int64)&v19);
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v18 )
    RtlFreeSid(v18);
  v16 = 0;
  if ( v12 != -1073741772 )
    v16 = v12;
  if ( a2 )
    SetEvent(a2);
  return v16 | 0x10000000u;
}

```

## disassembly

```asm
0x18001e658  mov     [rsp-8+arg_10], rbx
0x18001e65d  push    rbp
0x18001e65e  push    rsi
0x18001e65f  push    rdi
0x18001e660  push    r12
0x18001e662  push    r14
0x18001e664  lea     rbp, [rsp-37h]
0x18001e669  sub     rsp, 0C0h
0x18001e670  mov     rax, cs:__security_cookie
0x18001e677  xor     rax, rsp
0x18001e67a  mov     [rbp+57h+var_30], rax
0x18001e67e  xor     r12d, r12d
0x18001e681  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18001e687  xor     eax, eax
0x18001e689  mov     [rbp+57h+var_80], r12
0x18001e68d  xorps   xmm0, xmm0
0x18001e690  mov     [rbp+57h+var_48], rax
0x18001e694  lea     rax, [rbp+57h+var_80]
0x18001e698  mov     [rbp+57h+var_78], r12
0x18001e69c  mov     [rsp+0E0h+Sid], rax; Sid
0x18001e6a1  lea     ebx, [r12+12h]
0x18001e6a6  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x18001e6ab  mov     r14, rdx
0x18001e6ae  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18001e6b3  mov     rdi, rcx
0x18001e6b6  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x18001e6bb  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18001e6bf  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x18001e6c4  xor     r9d, r9d; SubAuthority1
0x18001e6c7  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x18001e6cc  mov     r8d, ebx; SubAuthority0
0x18001e6cf  mov     dl, 1; SubAuthorityCount
0x18001e6d1  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x18001e6d6  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18001e6da  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x18001e6de  movups  [rbp+57h+var_58], xmm0
0x18001e6e2  mov     dword ptr [rbp+57h+var_38.Value], r12d
0x18001e6e6  mov     word ptr [rbp+57h+var_38.Value+4], 100h
0x18001e6ec  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001e6f2  lea     rax, [rbp+57h+var_78]
0x18001e6f6  xor     r9d, r9d; SubAuthority1
0x18001e6f9  mov     [rsp+0E0h+Sid], rax; Sid
0x18001e6fe  lea     rcx, [rbp+57h+var_38]; IdentifierAuthority
0x18001e702  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x18001e707  mov     r8d, ebx; SubAuthority0
0x18001e70a  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18001e70f  mov     dl, 1; SubAuthorityCount
0x18001e711  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x18001e716  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x18001e71b  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x18001e720  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x18001e725  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001e72b  mov     rcx, [rbp+57h+var_78]; Sid
0x18001e72f  call    cs:__imp_RtlLengthSid
0x18001e735  mov     rcx, [rbp+57h+var_80]; Sid
0x18001e739  mov     ebx, eax
0x18001e73b  call    cs:__imp_RtlLengthSid
0x18001e741  mov     rcx, gs:60h
0x18001e74a  xor     edx, edx; Flags
0x18001e74c  add     eax, 20h ; ' '
0x18001e74f  add     ebx, eax
0x18001e751  mov     r8d, ebx; Size
0x18001e754  mov     rcx, [rcx+30h]; HeapHandle
0x18001e758  call    cs:__imp_RtlAllocateHeap
0x18001e75e  mov     rsi, rax
0x18001e761  test    rax, rax
0x18001e764  jnz     short loc_18001E770
0x18001e766  mov     eax, 0C000009Ah
0x18001e76b  jmp     loc_18001E8A9
0x18001e770  mov     r8d, 2; AclRevision
0x18001e776  mov     edx, ebx; AclSize
0x18001e778  mov     rcx, rsi; Acl
0x18001e77b  call    cs:__imp_RtlCreateAcl
0x18001e781  mov     r9, [rbp+57h+var_80]; Sid
0x18001e785  mov     edx, 2; Revision
0x18001e78a  mov     r8d, 1F0003h; AccessMask
0x18001e790  mov     rcx, rsi; Acl
0x18001e793  call    cs:__imp_RtlAddAccessAllowedAce
0x18001e799  mov     r9, [rbp+57h+var_78]; Sid
0x18001e79d  mov     edx, 2; Revision
0x18001e7a2  mov     r8d, 120001h; AccessMask
0x18001e7a8  mov     rcx, rsi; Acl
0x18001e7ab  call    cs:__imp_RtlAddAccessAllowedAce
0x18001e7b1  mov     edx, 1; Revision
0x18001e7b6  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001e7ba  call    cs:__imp_RtlCreateSecurityDescriptor
0x18001e7c0  xor     r9d, r9d; DaclDefaulted
0x18001e7c3  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001e7c7  mov     r8, rsi; Dacl
0x18001e7ca  mov     dl, 1; DaclPresent
0x18001e7cc  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18001e7d2  mov     r8d, [rdi]; unsigned int
0x18001e7d5  mov     rdx, qword ptr cs:WNF_OSWN_STORAGE_FREE_SPACE_CHANGE.Data; struct _WNF_STATE_NAME
0x18001e7dc  call    ?PublishState@StorageNotify@@QEAAJU_WNF_STATE_NAME@@KPEAH@Z; StorageNotify::PublishState(_WNF_STATE_NAME,ulong,int *)
0x18001e7e1  mov     ebx, eax
0x18001e7e3  test    eax, eax
0x18001e7e5  js      short loc_18001E826
0x18001e7e7  mov     r8d, [rdi]; unsigned int
0x18001e7ea  mov     rdx, qword ptr cs:WNF_OSWN_STORAGE_PRESENCE_CHANGE.Data; struct _WNF_STATE_NAME
0x18001e7f1  call    ?PublishState@StorageNotify@@QEAAJU_WNF_STATE_NAME@@KPEAH@Z; StorageNotify::PublishState(_WNF_STATE_NAME,ulong,int *)
0x18001e7f6  mov     ebx, eax
0x18001e7f8  test    eax, eax
0x18001e7fa  js      short loc_18001E826
0x18001e7fc  mov     r8d, [rdi]; unsigned int
0x18001e7ff  mov     rdx, qword ptr cs:WNF_OSWN_STORAGE_TEMP_CLEANUP_CHANGE.Data; struct _WNF_STATE_NAME
0x18001e806  call    ?PublishState@StorageNotify@@QEAAJU_WNF_STATE_NAME@@KPEAH@Z; StorageNotify::PublishState(_WNF_STATE_NAME,ulong,int *)
0x18001e80b  mov     ebx, eax
0x18001e80d  test    eax, eax
0x18001e80f  js      short loc_18001E826
0x18001e811  mov     r8d, [rdi]; unsigned int
0x18001e814  mov     rdx, qword ptr cs:WNF_OSWN_STORAGE_VOLUME_STATUS_CHANGE.Data; struct _WNF_STATE_NAME
0x18001e81b  call    ?PublishState@StorageNotify@@QEAAJU_WNF_STATE_NAME@@KPEAH@Z; StorageNotify::PublishState(_WNF_STATE_NAME,ulong,int *)
0x18001e820  mov     ebx, eax
0x18001e822  test    eax, eax
0x18001e824  jns     short loc_18001E853
0x18001e826  mov     eax, cs:dword_1800BF000
0x18001e82c  cmp     eax, 5
0x18001e82f  jbe     short loc_18001E853
0x18001e831  lea     rax, [rbp+57h+var_70]
0x18001e835  mov     [rbp+57h+var_70], ebx
0x18001e838  xor     r8d, r8d
0x18001e83b  mov     qword ptr [rsp+0E0h+SubAuthority2], rax
0x18001e840  lea     rdx, word_1800A58F2
0x18001e847  lea     rcx, dword_1800BF000
0x18001e84e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001e853  mov     rcx, gs:60h
0x18001e85c  mov     r8, rsi; P
0x18001e85f  xor     edx, edx; Flags
0x18001e861  mov     rcx, [rcx+30h]; HeapHandle
0x18001e865  call    cs:__imp_RtlFreeHeap
0x18001e86b  mov     rcx, [rbp+57h+var_80]; Sid
0x18001e86f  test    rcx, rcx
0x18001e872  jz      short loc_18001E87A
0x18001e874  call    cs:__imp_RtlFreeSid
0x18001e87a  mov     rcx, [rbp+57h+var_78]; Sid
0x18001e87e  test    rcx, rcx
0x18001e881  jz      short loc_18001E889
0x18001e883  call    cs:__imp_RtlFreeSid
0x18001e889  cmp     ebx, 0C0000034h
0x18001e88f  mov     edi, r12d
0x18001e892  cmovnz  edi, ebx
0x18001e895  test    r14, r14
0x18001e898  jz      short loc_18001E8A3
0x18001e89a  mov     rcx, r14; hEvent
0x18001e89d  call    cs:__imp_SetEvent
0x18001e8a3  bts     edi, 1Ch
0x18001e8a7  mov     eax, edi
0x18001e8a9  mov     rcx, [rbp+57h+var_30]
0x18001e8ad  xor     rcx, rsp; StackCookie
0x18001e8b0  call    __security_check_cookie
0x18001e8b5  mov     rbx, [rsp+0E0h+arg_10]
0x18001e8bd  add     rsp, 0C0h
0x18001e8c4  pop     r14
0x18001e8c6  pop     r12
0x18001e8c8  pop     rdi
0x18001e8c9  pop     rsi
0x18001e8ca  pop     rbp
0x18001e8cb  retn
```
