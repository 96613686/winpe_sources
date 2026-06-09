# ShieldProvider::CrossContainerCommunicationManager::StartContainerActivity(void)

- ea: `0x1800c3950`
- end: `0x1800c3e52`
- name: `?StartContainerActivity@CrossContainerCommunicationManager@ShieldProvider@@UEAAJXZ`
- size: `1282`
- prototype: `__int64 __fastcall(ShieldProvider::CrossContainerCommunicationManager *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004710`
- `0x180004ae0`
- `0x18000517c`
- `0x1800080b8`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180011730`
- `0x1800c3950`
- `0x1800c3f3c`
- `0x1800ceb88`
- `0x1800d5f60`
- `0x1800d7fe4`
- `0x1800d80d8`
- `0x1800d81d0`
- `0x1800d82c4`
- `0x1800df1b0`
- `0x1800e1764`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800c3b97`
- `KERNEL32!GetLastError` at `0x1800c3b97`
- `KERNEL32!CompareStringW` at `0x1800c3a90`
- `KERNEL32!CompareStringW` at `0x1800c3a90`
- `ntdll!NtQueryInformationToken` at `0x1800c3a26`
- `ntdll!NtQueryInformationToken` at `0x1800c3a26`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3a2e`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3a2e`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800c3b8d`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800c3b8d`

## pseudocode

```c
__int64 __fastcall ShieldProvider::CrossContainerCommunicationManager::StartContainerActivity(
        ShieldProvider::CrossContainerCommunicationManager *this)
{
  signed int ContainerIdForUser; // edi
  char i; // al
  NTSTATUS v5; // eax
  signed int v6; // eax
  void *v7; // r8
  const struct std::nothrow_t *v8; // rdx
  WCHAR *v9; // rbx
  void **v10; // rdi
  unsigned __int16 *v11; // r8
  __int64 v12; // r8
  _QWORD *v13; // r15
  unsigned int v14; // r8d
  const char *v15; // r9
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  PCNZWCH lpString1; // [rsp+30h] [rbp-69h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-61h] BYREF
  __int64 v25; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v26[24]; // [rsp+48h] [rbp-51h] BYREF
  PSID TokenInformation[10]; // [rsp+60h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( ShieldProvider::IsOSWcosHost(this) )
  {
    ContainerIdForUser = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v26,
      qword_18013A0B0);
    for ( i = 1; ; i = 0 )
    {
      v26[16] = i;
      if ( !i )
        break;
      memset_0(TokenInformation, 0, 0x48u);
      ReturnLength = 0;
      v25 = 0;
      ContainerIdForUser = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v25);
      if ( ContainerIdForUser < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_78;
        v22 = 20;
LABEL_77:
        WPP_SF_d(v21[2], v22, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids, (unsigned int)ContainerIdForUser);
        goto LABEL_78;
      }
      v5 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, TokenInformation, 0x48u, &ReturnLength);
      v6 = RtlNtStatusToDosError(v5);
      ContainerIdForUser = v6;
      if ( v6 > 0 )
        ContainerIdForUser = (unsigned __int16)v6 | 0x80070000;
      if ( ContainerIdForUser < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_78;
        v22 = 21;
        goto LABEL_77;
      }
      lpString1 = 0;
      ContainerIdForUser = CommonUtil::UtilConvertSidToStringSid((CommonUtil *)&lpString1, TokenInformation[0], v7);
      if ( ContainerIdForUser < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids,
            (unsigned int)ContainerIdForUser);
        v18 = (WCHAR *)lpString1;
        if ( lpString1 )
LABEL_70:
          operator delete(v18, v8);
LABEL_78:
        CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v25);
        break;
      }
      v9 = (WCHAR *)lpString1;
      v10 = (void **)((char *)this + 88);
      if ( CompareStringW(0x7Fu, 1u, lpString1, -1, *((PCNZWCH *)this + 11), -1) != 2 )
      {
        if ( *((_BYTE *)this + 128) )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 23;
            goto LABEL_59;
          }
LABEL_60:
          if ( v9 )
            operator delete(v9, v8);
          ContainerIdForUser = 0;
          goto LABEL_78;
        }
        if ( *v10 )
        {
          operator delete(*v10, v8);
          *v10 = 0;
        }
        ContainerIdForUser = CommonUtil::UtilCoDuplicateString(
                               (ShieldProvider::CrossContainerCommunicationManager *)((char *)this + 88),
                               (unsigned __int16 **)v9,
                               v11);
        if ( ContainerIdForUser < 0 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 24;
            goto LABEL_34;
          }
          goto LABEL_35;
        }
      }
      ContainerIdForUser = CpmcGetContainerIdForUser(TokenInformation[0], (char *)this + 96);
      if ( ContainerIdForUser < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v17 = 25;
LABEL_34:
        WPP_SF_d(v16[2], v17, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids, (unsigned int)ContainerIdForUser);
        goto LABEL_35;
      }
      if ( *((_BYTE *)this + 128) )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 26;
LABEL_59:
          WPP_SF_d(v19[2], v20, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids, 0);
        }
        goto LABEL_60;
      }
      v13 = (_QWORD *)((char *)this + 112);
      ContainerIdForUser = CmsOpenContainer((char *)this + 96, v8, v12, (char *)this + 112);
      if ( ContainerIdForUser < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v17 = 27;
        goto LABEL_34;
      }
      ContainerIdForUser = CmsRegisterForContainerNotifications(
                             *v13,
                             lambda_9eea8906c5f078267edc1a8169ce3858_::_lambda_invoker_cdecl_);
      if ( ContainerIdForUser < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v17 = 28;
        goto LABEL_34;
      }
      ContainerIdForUser = CmsCreateActivity(*v13, v8, (char *)this + 120);
      if ( ContainerIdForUser < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v17 = 29;
        goto LABEL_34;
      }
      ContainerIdForUser = CmsStartActivityAsync(
                             *((_QWORD *)this + 15),
                             lambda_e0edaff45158b5ea61fd86ac1e57c592_::_lambda_invoker_cdecl_,
                             &ShieldProvider::context);
      if ( ContainerIdForUser < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v17 = 30;
        goto LABEL_34;
      }
      while ( !(unsigned __int8)wil::slim_event_t<1>::TryAcquireEvent(&dword_18013A0AC) )
      {
        LODWORD(lpString1) = 0;
        if ( !WaitOnAddress(&dword_18013A0AC, &lpString1, 4u, 0xFFFFFFFF) )
        {
          if ( GetLastError() != 1460 )
            wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xDBF, v14, v15);
          break;
        }
      }
      ContainerIdForUser = ShieldProvider::context;
      if ( ShieldProvider::context < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 31;
          goto LABEL_34;
        }
LABEL_35:
        if ( v9 )
        {
          v18 = v9;
          goto LABEL_70;
        }
        goto LABEL_78;
      }
      *((_BYTE *)this + 128) = 1;
      if ( v9 )
        operator delete(v9, v8);
      CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v25);
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v26);
    return (unsigned int)ContainerIdForUser;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1800c3950  push    rbp
0x1800c3952  push    rbx
0x1800c3953  push    rdi
0x1800c3954  push    r12
0x1800c3956  push    r14
0x1800c3958  push    r15
0x1800c395a  lea     rbp, [rsp-2Fh]
0x1800c395f  sub     rsp, 0C8h
0x1800c3966  mov     rax, cs:__security_cookie
0x1800c396d  xor     rax, rsp
0x1800c3970  mov     [rbp+57h+var_40], rax
0x1800c3974  mov     r14, rcx
0x1800c3977  call    ?IsOSWcosHost@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcosHost(void)
0x1800c397c  test    al, al
0x1800c397e  jnz     short loc_1800C39B8
0x1800c3980  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3987  lea     rax, WPP_GLOBAL_Control
0x1800c398e  cmp     rcx, rax
0x1800c3991  jz      short loc_1800C39B1
0x1800c3993  test    byte ptr [rcx+1Ch], 1
0x1800c3997  jz      short loc_1800C39B1
0x1800c3999  mov     rcx, [rcx+10h]
0x1800c399d  lea     r8, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids
0x1800c39a4  mov     edx, 13h
0x1800c39a9  xor     r9d, r9d
0x1800c39ac  call    WPP_SF_d
0x1800c39b1  xor     eax, eax
0x1800c39b3  jmp     loc_1800C3E35
0x1800c39b8  xor     edi, edi
0x1800c39ba  lea     rdx, qword_18013A0B0
0x1800c39c1  lea     rcx, [rbp+57h+var_A8]
0x1800c39c5  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c39ca  mov     al, 1
0x1800c39cc  mov     [rbp+57h+var_98], al
0x1800c39cf  test    al, al
0x1800c39d1  jz      loc_1800C3E2A
0x1800c39d7  xor     edx, edx; Val
0x1800c39d9  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1800c39dd  lea     r8d, [rdx+48h]; Size
0x1800c39e1  call    memset_0
0x1800c39e6  lea     rcx, [rbp+57h+var_B0]
0x1800c39ea  mov     [rbp+57h+var_B8], 0
0x1800c39f1  mov     [rbp+57h+var_B0], 0
0x1800c39f9  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800c39fe  mov     edi, eax
0x1800c3a00  test    eax, eax
0x1800c3a02  js      loc_1800C3DF0
0x1800c3a08  mov     r9d, 48h ; 'H'; TokenInformationLength
0x1800c3a0e  lea     rax, [rbp+57h+var_B8]
0x1800c3a12  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800c3a16  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x1800c3a1b  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800c3a22  lea     edx, [r9-47h]; TokenInformationClass
0x1800c3a26  call    cs:__imp_NtQueryInformationToken
0x1800c3a2c  mov     ecx, eax; Status
0x1800c3a2e  call    cs:__imp_RtlNtStatusToDosError
0x1800c3a34  mov     edi, eax
0x1800c3a36  test    eax, eax
0x1800c3a38  jle     short loc_1800C3A43
0x1800c3a3a  movzx   edi, ax
0x1800c3a3d  or      edi, 80070000h
0x1800c3a43  test    edi, edi
0x1800c3a45  js      loc_1800C3DD0
0x1800c3a4b  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x1800c3a4f  lea     rcx, [rbp+57h+lpString1]; this
0x1800c3a53  mov     [rbp+57h+lpString1], 0
0x1800c3a5b  call    ?UtilConvertSidToStringSid@CommonUtil@@YAJPEAPEAGPEAX@Z; CommonUtil::UtilConvertSidToStringSid(ushort * *,void *)
0x1800c3a60  mov     edi, eax
0x1800c3a62  test    eax, eax
0x1800c3a64  js      loc_1800C3D8F
0x1800c3a6a  mov     rbx, [rbp+57h+lpString1]
0x1800c3a6e  lea     rdi, [r14+58h]
0x1800c3a72  mov     rax, [rdi]
0x1800c3a75  or      r9d, 0FFFFFFFFh; cchCount1
0x1800c3a79  mov     [rsp+0F0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800c3a81  mov     r8, rbx; lpString1
0x1800c3a84  mov     [rsp+0F0h+ReturnLength], rax; lpString2
0x1800c3a89  lea     edx, [r9+2]; dwCmpFlags
0x1800c3a8d  lea     ecx, [rdx+7Eh]; Locale
0x1800c3a90  call    cs:__imp_CompareStringW
0x1800c3a96  cmp     eax, 2
0x1800c3a99  jz      short loc_1800C3AD2
0x1800c3a9b  cmp     byte ptr [r14+80h], 0
0x1800c3aa3  jnz     loc_1800C3C1D
0x1800c3aa9  mov     rcx, [rdi]; void *
0x1800c3aac  test    rcx, rcx
0x1800c3aaf  jz      short loc_1800C3ABD
0x1800c3ab1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c3ab6  mov     qword ptr [rdi], 0
0x1800c3abd  mov     rdx, rbx; unsigned __int16 **
0x1800c3ac0  mov     rcx, rdi; this
0x1800c3ac3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800c3ac8  mov     edi, eax
0x1800c3aca  test    eax, eax
0x1800c3acc  js      loc_1800C3BDB
0x1800c3ad2  mov     rcx, [rbp+57h+TokenInformation]
0x1800c3ad6  lea     rdx, [r14+60h]
0x1800c3ada  call    CpmcGetContainerIdForUser
0x1800c3adf  mov     edi, eax
0x1800c3ae1  test    eax, eax
0x1800c3ae3  js      loc_1800C3D64
0x1800c3ae9  cmp     byte ptr [r14+80h], 0
0x1800c3af1  jnz     loc_1800C3D1F
0x1800c3af7  lea     r15, [r14+70h]
0x1800c3afb  mov     r9, r15
0x1800c3afe  lea     rcx, [r14+60h]
0x1800c3b02  call    CmsOpenContainer
0x1800c3b07  mov     edi, eax
0x1800c3b09  test    eax, eax
0x1800c3b0b  js      loc_1800C3CF4
0x1800c3b11  mov     rcx, [r15]
0x1800c3b14  lea     rdx, _lambda_9eea8906c5f078267edc1a8169ce3858____lambda_invoker_cdecl_
0x1800c3b1b  call    CmsRegisterForContainerNotifications
0x1800c3b20  mov     edi, eax
0x1800c3b22  test    eax, eax
0x1800c3b24  js      loc_1800C3CC9
0x1800c3b2a  mov     rcx, [r15]
0x1800c3b2d  lea     r8, [r14+78h]
0x1800c3b31  call    CmsCreateActivity
0x1800c3b36  mov     edi, eax
0x1800c3b38  test    eax, eax
0x1800c3b3a  js      loc_1800C3C9E
0x1800c3b40  mov     rcx, [r14+78h]
0x1800c3b44  lea     r8, ?context@ShieldProvider@@3UStartActivityContext@1@A; ShieldProvider::StartActivityContext ShieldProvider::context
0x1800c3b4b  lea     rdx, _lambda_e0edaff45158b5ea61fd86ac1e57c592____lambda_invoker_cdecl_
0x1800c3b52  call    CmsStartActivityAsync
0x1800c3b57  mov     edi, eax
0x1800c3b59  test    eax, eax
0x1800c3b5b  js      loc_1800C3C77
0x1800c3b61  lea     rcx, dword_18013A0AC
0x1800c3b68  call    ?TryAcquireEvent@?$slim_event_t@$00@wil@@AEAA_NXZ; wil::slim_event_t<1>::TryAcquireEvent(void)
0x1800c3b6d  test    al, al
0x1800c3b6f  jnz     short loc_1800C3BA8
0x1800c3b71  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800c3b75  mov     dword ptr [rbp+57h+lpString1], 0
0x1800c3b7c  mov     r8d, 4; AddressSize
0x1800c3b82  lea     rdx, [rbp+57h+lpString1]; CompareAddress
0x1800c3b86  lea     rcx, dword_18013A0AC; Address
0x1800c3b8d  call    cs:__imp_WaitOnAddress
0x1800c3b93  test    eax, eax
0x1800c3b95  jnz     short loc_1800C3B61
0x1800c3b97  call    cs:__imp_GetLastError
0x1800c3b9d  cmp     eax, 5B4h
0x1800c3ba2  jnz     loc_1800C3C48
0x1800c3ba8  mov     edi, cs:?context@ShieldProvider@@3UStartActivityContext@1@A; ShieldProvider::StartActivityContext ShieldProvider::context
0x1800c3bae  test    edi, edi
0x1800c3bb0  js      loc_1800C3C57
0x1800c3bb6  mov     byte ptr [r14+80h], 1
0x1800c3bbe  test    rbx, rbx
0x1800c3bc1  jz      short loc_1800C3BCB
0x1800c3bc3  mov     rcx, rbx; void *
0x1800c3bc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c3bcb  lea     rcx, [rbp+57h+var_B0]
0x1800c3bcf  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800c3bd4  xor     al, al
0x1800c3bd6  jmp     loc_1800C39CC
0x1800c3bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3be2  lea     rax, WPP_GLOBAL_Control
0x1800c3be9  cmp     rcx, rax
0x1800c3bec  jz      short loc_1800C3C0C
0x1800c3bee  test    byte ptr [rcx+1Ch], 1
0x1800c3bf2  jz      short loc_1800C3C0C
0x1800c3bf4  mov     edx, 18h
0x1800c3bf9  mov     rcx, [rcx+10h]
0x1800c3bfd  lea     r8, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids
0x1800c3c04  mov     r9d, edi
0x1800c3c07  call    WPP_SF_d
0x1800c3c0c  test    rbx, rbx
0x1800c3c0f  jz      loc_1800C3E21
0x1800c3c15  mov     rcx, rbx
0x1800c3c18  jmp     loc_1800C3DC9
0x1800c3c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3c24  lea     rax, WPP_GLOBAL_Control
0x1800c3c2b  cmp     rcx, rax
0x1800c3c2e  jz      loc_1800C3D50
0x1800c3c34  test    byte ptr [rcx+1Ch], 1
0x1800c3c38  jz      loc_1800C3D50
0x1800c3c3e  mov     edx, 17h
0x1800c3c43  jmp     loc_1800C3D3D
0x1800c3c48  mov     rcx, [rbp+5Fh]; this
0x1800c3c4c  mov     edx, 0DBFh; void *
0x1800c3c51  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800c3c57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3c5e  lea     rax, WPP_GLOBAL_Control
0x1800c3c65  cmp     rcx, rax
0x1800c3c68  jz      short loc_1800C3C0C
0x1800c3c6a  test    byte ptr [rcx+1Ch], 1
0x1800c3c6e  jz      short loc_1800C3C0C
0x1800c3c70  mov     edx, 1Fh
0x1800c3c75  jmp     short loc_1800C3BF9
0x1800c3c77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3c7e  lea     rax, WPP_GLOBAL_Control
0x1800c3c85  cmp     rcx, rax
0x1800c3c88  jz      short loc_1800C3C0C
0x1800c3c8a  test    byte ptr [rcx+1Ch], 1
0x1800c3c8e  jz      loc_1800C3C0C
0x1800c3c94  mov     edx, 1Eh
0x1800c3c99  jmp     loc_1800C3BF9
0x1800c3c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3ca5  lea     rax, WPP_GLOBAL_Control
0x1800c3cac  cmp     rcx, rax
0x1800c3caf  jz      loc_1800C3C0C
0x1800c3cb5  test    byte ptr [rcx+1Ch], 1
0x1800c3cb9  jz      loc_1800C3C0C
0x1800c3cbf  mov     edx, 1Dh
0x1800c3cc4  jmp     loc_1800C3BF9
0x1800c3cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3cd0  lea     rax, WPP_GLOBAL_Control
0x1800c3cd7  cmp     rcx, rax
0x1800c3cda  jz      loc_1800C3C0C
0x1800c3ce0  test    byte ptr [rcx+1Ch], 1
0x1800c3ce4  jz      loc_1800C3C0C
0x1800c3cea  mov     edx, 1Ch
0x1800c3cef  jmp     loc_1800C3BF9
0x1800c3cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3cfb  lea     rax, WPP_GLOBAL_Control
0x1800c3d02  cmp     rcx, rax
0x1800c3d05  jz      loc_1800C3C0C
0x1800c3d0b  test    byte ptr [rcx+1Ch], 1
0x1800c3d0f  jz      loc_1800C3C0C
0x1800c3d15  mov     edx, 1Bh
0x1800c3d1a  jmp     loc_1800C3BF9
0x1800c3d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3d26  lea     rax, WPP_GLOBAL_Control
0x1800c3d2d  cmp     rcx, rax
0x1800c3d30  jz      short loc_1800C3D50
0x1800c3d32  test    byte ptr [rcx+1Ch], 1
0x1800c3d36  jz      short loc_1800C3D50
0x1800c3d38  mov     edx, 1Ah
0x1800c3d3d  mov     rcx, [rcx+10h]
0x1800c3d41  lea     r8, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids
0x1800c3d48  xor     r9d, r9d
0x1800c3d4b  call    WPP_SF_d
0x1800c3d50  test    rbx, rbx
0x1800c3d53  jz      short loc_1800C3D5D
0x1800c3d55  mov     rcx, rbx; void *
0x1800c3d58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c3d5d  xor     edi, edi
0x1800c3d5f  jmp     loc_1800C3E21
0x1800c3d64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3d6b  lea     rax, WPP_GLOBAL_Control
0x1800c3d72  cmp     rcx, rax
0x1800c3d75  jz      loc_1800C3C0C
0x1800c3d7b  test    byte ptr [rcx+1Ch], 1
0x1800c3d7f  jz      loc_1800C3C0C
0x1800c3d85  mov     edx, 19h
0x1800c3d8a  jmp     loc_1800C3BF9
0x1800c3d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3d96  lea     rax, WPP_GLOBAL_Control
0x1800c3d9d  cmp     rcx, rax
0x1800c3da0  jz      short loc_1800C3DC0
0x1800c3da2  test    byte ptr [rcx+1Ch], 1
0x1800c3da6  jz      short loc_1800C3DC0
0x1800c3da8  mov     rcx, [rcx+10h]
0x1800c3dac  lea     r8, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids
0x1800c3db3  mov     edx, 16h
0x1800c3db8  mov     r9d, edi
0x1800c3dbb  call    WPP_SF_d
0x1800c3dc0  mov     rcx, [rbp+57h+lpString1]; void *
0x1800c3dc4  test    rcx, rcx
0x1800c3dc7  jz      short loc_1800C3E21
0x1800c3dc9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c3dce  jmp     short loc_1800C3E21
0x1800c3dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3dd7  lea     rax, WPP_GLOBAL_Control
0x1800c3dde  cmp     rcx, rax
0x1800c3de1  jz      short loc_1800C3E21
0x1800c3de3  test    byte ptr [rcx+1Ch], 1
0x1800c3de7  jz      short loc_1800C3E21
0x1800c3de9  mov     edx, 15h
0x1800c3dee  jmp     short loc_1800C3E0E
0x1800c3df0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3df7  lea     rax, WPP_GLOBAL_Control
0x1800c3dfe  cmp     rcx, rax
0x1800c3e01  jz      short loc_1800C3E21
0x1800c3e03  test    byte ptr [rcx+1Ch], 1
0x1800c3e07  jz      short loc_1800C3E21
0x1800c3e09  mov     edx, 14h
0x1800c3e0e  mov     rcx, [rcx+10h]
0x1800c3e12  lea     r8, WPP_d3d7329f2b253521a0205aa5f2cdf738_Traceguids
0x1800c3e19  mov     r9d, edi
0x1800c3e1c  call    WPP_SF_d
0x1800c3e21  lea     rcx, [rbp+57h+var_B0]
0x1800c3e25  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800c3e2a  lea     rcx, [rbp+57h+var_A8]
0x1800c3e2e  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c3e33  mov     eax, edi
0x1800c3e35  mov     rcx, [rbp+57h+var_40]
0x1800c3e39  xor     rcx, rsp; StackCookie
0x1800c3e3c  call    __security_check_cookie
0x1800c3e41  add     rsp, 0C8h
0x1800c3e48  pop     r15
0x1800c3e4a  pop     r14
0x1800c3e4c  pop     r12
0x1800c3e4e  pop     rdi
0x1800c3e4f  pop     rbx
0x1800c3e50  pop     rbp
0x1800c3e51  retn
```
