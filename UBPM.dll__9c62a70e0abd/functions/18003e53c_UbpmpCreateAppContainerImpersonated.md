# UbpmpCreateAppContainerImpersonated

- ea: `0x18003e53c`
- end: `0x18003e8a7`
- name: `UbpmpCreateAppContainerImpersonated`
- size: `875`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, PSID pSourceSid@<rdx>, PSID pSid1@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001eaf4`

## callees

- `0x18000fbf0`
- `0x1800103c0`
- `0x1800150c0`
- `0x1800191a0`
- `0x1800351ec`
- `0x1800373c0`
- `0x18003e53c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003e61e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003e61e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003e866`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003e866`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003e6d0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003e6d0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003e5d3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003e7b6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003e5d3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003e7b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003e880`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003e880`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003e5b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003e5b8`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18003e75e`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18003e75e`
- `USERENV!DeleteAppContainerProfile` at `0x18003e7fe`
- `USERENV!DeleteAppContainerProfile` at `0x18003e7fe`
- `USERENV!CreateAppContainerProfile` at `0x18003e741`
- `USERENV!CreateAppContainerProfile` at `0x18003e741`

## pseudocode

```c
__int64 __fastcall UbpmpCreateAppContainerImpersonated(
        unsigned __int16 *a1,
        PSID pSourceSid,
        PSID pSid1,
        int a4,
        __int64 a5,
        struct _LIST_ENTRY **a6)
{
  int v7; // r12d
  PSID v8; // r13
  struct _LIST_ENTRY *Flink; // rdi
  __int64 v11; // rbp
  struct _LIST_ENTRY *v12; // r14
  struct _LIST_ENTRY *v13; // rbx
  __int64 v14; // rbp
  DWORD LengthSid; // edi
  unsigned __int16 *v16; // rax
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  struct _LIST_ENTRY *v23; // rdx
  int AppContainerProfile; // ebp
  struct _LIST_ENTRY *v25; // rax
  PSID pSid2[9]; // [rsp+30h] [rbp-48h] BYREF

  pSid2[0] = 0;
  v7 = a4;
  v8 = pSid1;
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_ContainerProfilesListLock);
  Flink = g_leContainerProfilesListHead.Flink;
  v11 = -1;
  if ( g_leContainerProfilesListHead.Flink != &g_leContainerProfilesListHead )
  {
    do
    {
      v12 = Flink->Flink;
      if ( CompareStringW(0x7Fu, 1u, a1, -1, (PCNZWCH)&Flink[2], -1) == 2 )
      {
        v13 = Flink;
        if ( EqualSid(pSourceSid, Flink[1].Blink) )
          break;
      }
      Flink = v12;
      v13 = 0;
    }
    while ( v12 != &g_leContainerProfilesListHead );
    v7 = a4;
    v8 = pSid1;
    if ( v13 )
      goto LABEL_35;
  }
  do
    ++v11;
  while ( a1[v11] );
  v14 = (unsigned int)(2 * v11 + 2);
  LengthSid = GetLengthSid(pSourceSid);
  v16 = (unsigned __int16 *)UbpmAlloc((unsigned int)v14 + LengthSid + 40);
  v13 = (struct _LIST_ENTRY *)v16;
  if ( v16 )
  {
    if ( (int)StringCbCopyW(v16 + 16, (unsigned int)v14, a1) < 0 )
    {
      v20 = 14;
      v17 = 14;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v22 = 83;
LABEL_19:
      WPP_SF_d(v21[2], v22, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 14);
LABEL_31:
      UBPM_MIDL_user_free(v13, v18, v19, v20);
      goto LABEL_36;
    }
    v23 = (struct _LIST_ENTRY *)((char *)v13 + v14 + 40);
    v13[1].Blink = v23;
    if ( !CopySid(LengthSid, v23, pSourceSid) )
    {
      v20 = 14;
      v17 = 14;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v22 = 84;
      goto LABEL_19;
    }
    AppContainerProfile = CreateAppContainerProfile(a1, a1, a1, a5, v7, pSid2);
    if ( AppContainerProfile == -2147024713 )
      AppContainerProfile = DeriveAppContainerSidFromAppContainerName(a1, pSid2);
    if ( AppContainerProfile < 0 )
    {
      v17 = (unsigned __int16)AppContainerProfile;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          (_DWORD)a1,
          AppContainerProfile);
      goto LABEL_31;
    }
    if ( !EqualSid(v8, pSid2[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          (_DWORD)a1,
          AppContainerProfile);
      DeleteAppContainerProfile(a1);
      v17 = 5;
      goto LABEL_31;
    }
    v25 = off_18004F150[0];
    if ( off_18004F150[0]->Flink != &g_leContainerProfilesListHead )
      __fastfail(3u);
    v13->Flink = &g_leContainerProfilesListHead;
    v13->Blink = v25;
    v25->Flink = v13;
    off_18004F150[0] = v13;
LABEL_35:
    _InterlockedIncrement64((volatile signed __int64 *)&v13[1]);
    v17 = 0;
    *a6 = v13;
    goto LABEL_36;
  }
  v17 = 14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, 14);
LABEL_36:
  if ( pSid2[0] )
    FreeSid(pSid2[0]);
  dword_1800500A0 = 0;
  RtlReleaseSRWLockExclusive(&g_ContainerProfilesListLock);
  return v17;
}

```

## disassembly

```asm
0x18003e53c  mov     rax, rsp
0x18003e53f  mov     [rax+8], rbx
0x18003e543  mov     [rax+20h], r9d
0x18003e547  mov     [rax+18h], r8
0x18003e54b  push    rbp
0x18003e54c  push    rsi
0x18003e54d  push    rdi
0x18003e54e  push    r12
0x18003e550  push    r13
0x18003e552  push    r14
0x18003e554  push    r15
0x18003e556  sub     rsp, 40h
0x18003e55a  mov     rsi, rcx
0x18003e55d  xor     r14d, r14d
0x18003e560  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18003e567  mov     [rax-48h], r14
0x18003e56b  mov     r12d, r9d
0x18003e56e  mov     r13, r8
0x18003e571  mov     r15, rdx
0x18003e574  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18003e579  mov     rdi, cs:?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003e580  lea     rax, ?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003e587  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18003e58b  cmp     rdi, rax
0x18003e58e  jz      short loc_18003E60A
0x18003e590  xor     r12d, r12d
0x18003e593  lea     r13, ?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003e59a  mov     r14, [rdi]
0x18003e59d  lea     rax, [rdi+20h]
0x18003e5a1  mov     edx, 1; dwCmpFlags
0x18003e5a6  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x18003e5aa  mov     r9d, ebp; cchCount1
0x18003e5ad  mov     [rsp+78h+lpString2], rax; lpString2
0x18003e5b2  mov     r8, rsi; lpString1
0x18003e5b5  lea     ecx, [rdx+7Eh]; Locale
0x18003e5b8  call    cs:__imp_CompareStringW
0x18003e5bf  nop     dword ptr [rax+rax+00h]
0x18003e5c4  cmp     eax, 2
0x18003e5c7  jnz     short loc_18003E5E3
0x18003e5c9  mov     rdx, [rdi+18h]; pSid2
0x18003e5cd  mov     rcx, r15; pSid1
0x18003e5d0  mov     rbx, rdi
0x18003e5d3  call    cs:__imp_EqualSid
0x18003e5da  nop     dword ptr [rax+rax+00h]
0x18003e5df  test    eax, eax
0x18003e5e1  jnz     short loc_18003E5EE
0x18003e5e3  mov     rdi, r14
0x18003e5e6  mov     rbx, r12
0x18003e5e9  cmp     r14, r13
0x18003e5ec  jnz     short loc_18003E59A
0x18003e5ee  mov     r12d, [rsp+78h+arg_18]
0x18003e5f6  mov     r13, [rsp+78h+arg_10]
0x18003e5fe  test    rbx, rbx
0x18003e601  jnz     loc_18003E846
0x18003e607  xor     r14d, r14d
0x18003e60a  inc     rbp
0x18003e60d  cmp     [rsi+rbp*2], r14w
0x18003e612  jnz     short loc_18003E60A
0x18003e614  mov     rcx, r15; pSid
0x18003e617  lea     ebp, ds:2[rbp*2]
0x18003e61e  call    cs:__imp_GetLengthSid
0x18003e625  nop     dword ptr [rax+rax+00h]
0x18003e62a  mov     edi, eax
0x18003e62c  lea     ecx, [rax+28h]
0x18003e62f  add     ecx, ebp; Size
0x18003e631  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18003e636  mov     rbx, rax
0x18003e639  test    rax, rax
0x18003e63c  jnz     short loc_18003E67E
0x18003e63e  lea     r9d, [rax+0Eh]
0x18003e642  mov     edi, r9d
0x18003e645  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e64c  lea     rax, WPP_GLOBAL_Control
0x18003e653  cmp     rcx, rax
0x18003e656  jz      loc_18003E85C
0x18003e65c  test    byte ptr [rcx+1Ch], 1
0x18003e660  jz      loc_18003E85C
0x18003e666  mov     rcx, [rcx+10h]
0x18003e66a  lea     edx, [rbx+52h]
0x18003e66d  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003e674  call    WPP_SF_d
0x18003e679  jmp     loc_18003E85C
0x18003e67e  lea     rcx, [rax+20h]; unsigned __int16 *
0x18003e682  mov     edx, ebp; unsigned __int64
0x18003e684  mov     r8, rsi; unsigned __int16 *
0x18003e687  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e68c  test    eax, eax
0x18003e68e  jns     short loc_18003E6C0
0x18003e690  mov     r9d, 0Eh
0x18003e696  mov     edi, r9d
0x18003e699  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6a0  lea     rax, WPP_GLOBAL_Control
0x18003e6a7  cmp     rcx, rax
0x18003e6aa  jz      loc_18003E80F
0x18003e6b0  test    byte ptr [rcx+1Ch], 1
0x18003e6b4  jz      loc_18003E80F
0x18003e6ba  lea     edx, [r9+45h]
0x18003e6be  jmp     short loc_18003E70C
0x18003e6c0  lea     rdx, [rbx+28h]
0x18003e6c4  mov     r8, r15; pSourceSid
0x18003e6c7  add     rdx, rbp; pDestinationSid
0x18003e6ca  mov     ecx, edi; nDestinationSidLength
0x18003e6cc  mov     [rbx+18h], rdx
0x18003e6d0  call    cs:__imp_CopySid
0x18003e6d7  nop     dword ptr [rax+rax+00h]
0x18003e6dc  test    eax, eax
0x18003e6de  jnz     short loc_18003E721
0x18003e6e0  lea     r9d, [rax+0Eh]
0x18003e6e4  mov     edi, r9d
0x18003e6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e6ee  lea     rax, WPP_GLOBAL_Control
0x18003e6f5  cmp     rcx, rax
0x18003e6f8  jz      loc_18003E80F
0x18003e6fe  test    byte ptr [rcx+1Ch], 1
0x18003e702  jz      loc_18003E80F
0x18003e708  lea     edx, [r9+46h]
0x18003e70c  mov     rcx, [rcx+10h]
0x18003e710  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003e717  call    WPP_SF_d
0x18003e71c  jmp     loc_18003E80F
0x18003e721  mov     r9, [rsp+78h+arg_20]
0x18003e729  lea     rax, [rsp+78h+pSid2]
0x18003e72e  mov     qword ptr [rsp+78h+cchCount2], rax
0x18003e733  mov     r8, rsi
0x18003e736  mov     rdx, rsi
0x18003e739  mov     dword ptr [rsp+78h+lpString2], r12d
0x18003e73e  mov     rcx, rsi
0x18003e741  call    cs:__imp_CreateAppContainerProfile
0x18003e748  nop     dword ptr [rax+rax+00h]
0x18003e74d  mov     ebp, eax
0x18003e74f  cmp     eax, 800700B7h
0x18003e754  jnz     short loc_18003E76C
0x18003e756  lea     rdx, [rsp+78h+pSid2]
0x18003e75b  mov     rcx, rsi
0x18003e75e  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18003e765  nop     dword ptr [rax+rax+00h]
0x18003e76a  mov     ebp, eax
0x18003e76c  test    ebp, ebp
0x18003e76e  jns     short loc_18003E7AE
0x18003e770  movzx   edi, bp
0x18003e773  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e77a  lea     rax, WPP_GLOBAL_Control
0x18003e781  cmp     rcx, rax
0x18003e784  jz      loc_18003E80F
0x18003e78a  test    byte ptr [rcx+1Ch], 1
0x18003e78e  jz      short loc_18003E80F
0x18003e790  mov     rcx, [rcx+10h]
0x18003e794  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003e79b  mov     edx, 55h ; 'U'
0x18003e7a0  mov     dword ptr [rsp+78h+lpString2], ebp
0x18003e7a4  mov     r9, rsi
0x18003e7a7  call    WPP_SF_SL
0x18003e7ac  jmp     short loc_18003E80F
0x18003e7ae  mov     rdx, [rsp+78h+pSid2]; pSid2
0x18003e7b3  mov     rcx, r13; pSid1
0x18003e7b6  call    cs:__imp_EqualSid
0x18003e7bd  nop     dword ptr [rax+rax+00h]
0x18003e7c2  test    eax, eax
0x18003e7c4  jnz     short loc_18003E819
0x18003e7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e7cd  lea     rax, WPP_GLOBAL_Control
0x18003e7d4  cmp     rcx, rax
0x18003e7d7  jz      short loc_18003E7FB
0x18003e7d9  test    byte ptr [rcx+1Ch], 1
0x18003e7dd  jz      short loc_18003E7FB
0x18003e7df  mov     rcx, [rcx+10h]
0x18003e7e3  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18003e7ea  mov     edx, 56h ; 'V'
0x18003e7ef  mov     dword ptr [rsp+78h+lpString2], ebp
0x18003e7f3  mov     r9, rsi
0x18003e7f6  call    WPP_SF_SL
0x18003e7fb  mov     rcx, rsi
0x18003e7fe  call    cs:__imp_DeleteAppContainerProfile
0x18003e805  nop     dword ptr [rax+rax+00h]
0x18003e80a  mov     edi, 5
0x18003e80f  mov     rcx, rbx
0x18003e812  call    UBPM_MIDL_user_free
0x18003e817  jmp     short loc_18003E85C
0x18003e819  mov     rax, cs:off_18004F150
0x18003e820  lea     rcx, ?g_leContainerProfilesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leContainerProfilesListHead
0x18003e827  cmp     [rax], rcx
0x18003e82a  jz      short loc_18003E833
0x18003e82c  mov     ecx, 3
0x18003e831  int     29h; Win8: RtlFailFast(ecx)
0x18003e833  mov     [rbx], rcx
0x18003e836  mov     [rbx+8], rax
0x18003e83a  mov     [rax], rbx
0x18003e83d  mov     cs:off_18004F150, rbx
0x18003e844  jmp     short loc_18003E849
0x18003e846  xor     r14d, r14d
0x18003e849  lock inc qword ptr [rbx+10h]
0x18003e84e  mov     rax, [rsp+78h+arg_28]
0x18003e856  mov     edi, r14d
0x18003e859  mov     [rax], rbx
0x18003e85c  mov     rcx, [rsp+78h+pSid2]; pSid
0x18003e861  test    rcx, rcx
0x18003e864  jz      short loc_18003E872
0x18003e866  call    cs:__imp_FreeSid
0x18003e86d  nop     dword ptr [rax+rax+00h]
0x18003e872  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_ContainerProfilesListLock
0x18003e879  mov     cs:dword_1800500A0, r14d
0x18003e880  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003e887  nop     dword ptr [rax+rax+00h]
0x18003e88c  mov     rbx, [rsp+78h+arg_0]
0x18003e894  mov     eax, edi
0x18003e896  add     rsp, 40h
0x18003e89a  pop     r15
0x18003e89c  pop     r14
0x18003e89e  pop     r13
0x18003e8a0  pop     r12
0x18003e8a2  pop     rdi
0x18003e8a3  pop     rsi
0x18003e8a4  pop     rbp
0x18003e8a5  retn
```
