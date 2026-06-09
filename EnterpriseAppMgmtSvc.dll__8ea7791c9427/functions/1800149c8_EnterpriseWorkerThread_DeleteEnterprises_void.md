# EnterpriseWorkerThread::DeleteEnterprises(void)

- ea: `0x1800149c8`
- end: `0x180014cd3`
- name: `?DeleteEnterprises@EnterpriseWorkerThread@@AEAAJXZ`
- size: `779`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800167f8`

## callees

- `0x180002514`
- `0x180006780`
- `0x180006858`
- `0x180012d84`
- `0x1800149c8`
- `0x1800199e4`
- `0x180019d8c`
- `0x18001a374`
- `0x18001b4bc`
- `0x180066da6`
- `0x180066df0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c6e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014aa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ca3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ca3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014b55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014b55`

## string_xrefs

- `0x180014af0`: `Failed to delete enterprise from database in EnterpriseWorkerThread::DeleteEnterprises.`
- `0x180014a85`: `EnumInstalledApplications failed in EnterpriseWorkerThread::DeleteEnterprises.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseWorkerThread::DeleteEnterprises(EnterpriseWorkerThread *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  int v3; // esi
  char *v4; // rbx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  void **v10; // rax
  __int64 v11; // rcx
  unsigned int i; // edi
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  char *v16; // rdi
  _QWORD *v17; // rax
  unsigned int v19; // [rsp+30h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-81h] BYREF
  int v21; // [rsp+40h] [rbp-79h] BYREF
  GUID Buf2; // [rsp+50h] [rbp-69h] BYREF
  struct _GUID v23; // [rsp+60h] [rbp-59h] BYREF
  GUID v24; // [rsp+70h] [rbp-49h] BYREF
  __int128 Buf1; // [rsp+80h] [rbp-39h] BYREF
  __int128 v26; // [rsp+90h] [rbp-29h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-19h] BYREF
  GUID *v28; // [rsp+B0h] [rbp-9h]
  __int64 v29; // [rsp+B8h] [rbp-1h]
  GUID *p_Buf2; // [rsp+C0h] [rbp+7h]
  __int64 v31; // [rsp+C8h] [rbp+Fh]
  int *v32; // [rsp+D0h] [rbp+17h]
  __int64 v33; // [rsp+D8h] [rbp+1Fh]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v3 = 0;
  v4 = (char *)*((_QWORD *)this + 31);
  while ( v4 != (char *)this + 248 )
  {
    v24 = (GUID)*((_OWORD *)v4 + 1);
    v19 = 0;
    pv = 0;
    Buf2 = GUID_NULL;
    v23 = (struct _GUID)*((_OWORD *)v4 + 1);
    v5 = EnrollmentManager::EnumInstalledApplications(&v23, &Buf2, (struct _GUID **)&pv, &v19, 0, 1);
    if ( v5 >= 0 )
    {
      if ( v19 && *((_QWORD *)this + 30) )
      {
        v4 = *(char **)v4;
      }
      else
      {
        Buf2 = v24;
        v7 = EnrollmentManager::DeleteRecord(0, &Buf2);
        if ( v7 >= 0 )
        {
          if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x40) != 0 )
          {
            v28 = &v24;
            v29 = 16;
            McGenEventWrite_EventWriteTransfer(v8, EnterpriseAppMgmtSvcUnenrollComplete, v9, 2, &v27);
          }
        }
        else
        {
          if ( v3 >= 0 )
            v3 = v7;
          if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v8,
              EnterpriseAppMgmtSvcError,
              L"Failed to delete enterprise from database in EnterpriseWorkerThread::DeleteEnterprises.",
              (unsigned int)v7);
        }
        Buf2 = v24;
        *(_QWORD *)&v23.Data1 = 0;
        v19 = 0;
        EnterCriticalSection(v2);
        if ( *((_DWORD *)this + 32) )
        {
          v10 = tlx::replace<_GUID,&void tlx::_delete_array<_GUID>(_GUID *)>((void **)&v23);
          if ( (int)EnrollmentManager::EnumeratePrimaryKeys(v11, (GUID **)v10, &v19) >= 0 )
          {
            for ( i = 0; i < v19; ++i )
            {
              v26 = *(_OWORD *)(*(_QWORD *)&v23.Data1 + 16LL * i);
              Buf1 = 0;
              v27 = v26;
              if ( (int)EnrollmentManager::RetrieveGUID(1u, (__int64)&v27, 3, &Buf1) >= 0
                && !memcmp_0(&Buf1, &Buf2, 0x10u) )
              {
                v27 = v26;
                v13 = EnrollmentManager::DeleteRecord(1, &v27);
                if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 1) != 0 )
                {
                  v21 = v13;
                  v28 = (GUID *)&v26;
                  v29 = 16;
                  p_Buf2 = &Buf2;
                  v31 = 16;
                  v32 = &v21;
                  v33 = 4;
                  McGenEventWrite_EventWriteTransfer(v14, EnterpriseAppMgmtSvcClearEntryFromEnterpriseId, v15, 4, &v27);
                }
              }
            }
          }
        }
        LeaveCriticalSection(v2);
        if ( *(_QWORD *)&v23.Data1 )
          operator delete[](*(void **)&v23.Data1);
        v16 = *(char **)v4;
        v17 = (_QWORD *)*((_QWORD *)v4 + 1);
        *v17 = *(_QWORD *)v4;
        *((_QWORD *)v16 + 1) = v17;
        operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
        --*((_QWORD *)this + 33);
        v4 = v16;
      }
    }
    else
    {
      if ( v3 >= 0 )
        v3 = v5;
      if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v6,
          EnterpriseAppMgmtSvcError,
          L"EnumInstalledApplications failed in EnterpriseWorkerThread::DeleteEnterprises.",
          (unsigned int)v5);
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  LeaveCriticalSection(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800149c8  mov     [rsp-8+arg_8], rbx
0x1800149cd  mov     [rsp-8+arg_10], rsi
0x1800149d2  push    rbp
0x1800149d3  push    rdi
0x1800149d4  push    r13
0x1800149d6  push    r14
0x1800149d8  push    r15
0x1800149da  lea     rbp, [rsp-37h]
0x1800149df  sub     rsp, 0F0h
0x1800149e6  mov     rax, cs:__security_cookie
0x1800149ed  xor     rax, rsp
0x1800149f0  mov     [rbp+57h+var_30], rax
0x1800149f4  mov     r14, rcx
0x1800149f7  lea     r15, [rcx+58h]
0x1800149fb  mov     rcx, r15; lpCriticalSection
0x1800149fe  call    cs:__imp_EnterCriticalSection
0x180014a04  xor     esi, esi
0x180014a06  lea     r13, [r14+0F8h]
0x180014a0d  mov     rbx, [r13+0]
0x180014a11  cmp     rbx, r13
0x180014a14  jz      loc_180014CA0
0x180014a1a  movups  xmm0, xmmword ptr [rbx+10h]
0x180014a1e  movdqu  [rbp+57h+var_A0], xmm0
0x180014a23  mov     [rsp+110h+var_E0], 0
0x180014a2b  mov     [rsp+110h+pv], 0
0x180014a34  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014a3b  movdqu  [rbp+57h+Buf2], xmm0
0x180014a40  movups  xmm0, xmmword ptr [rbx+10h]
0x180014a44  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180014a49  mov     [rsp+110h+var_E8], 1; int
0x180014a51  mov     [rsp+110h+var_F0], 0; int
0x180014a59  lea     r9, [rsp+110h+var_E0]; unsigned int *
0x180014a5e  lea     r8, [rsp+110h+pv]; struct _GUID **
0x180014a63  lea     rdx, [rbp+57h+Buf2]; struct _GUID
0x180014a67  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x180014a6b  call    ?EnumInstalledApplications@EnrollmentManager@@SAJU_GUID@@0PEAPEAU2@PEAKHH@Z; EnrollmentManager::EnumInstalledApplications(_GUID,_GUID,_GUID * *,ulong *,int,int)
0x180014a70  test    eax, eax
0x180014a72  jns     short loc_180014AB1
0x180014a74  test    esi, esi
0x180014a76  cmovns  esi, eax
0x180014a79  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180014a80  jz      short loc_180014A98
0x180014a82  mov     r9d, eax
0x180014a85  lea     r8, aEnuminstalleda; "EnumInstalledApplications failed in Ent"...
0x180014a8c  lea     rdx, EnterpriseAppMgmtSvcError
0x180014a93  call    McTemplateU0zq_EventWriteTransfer
0x180014a98  mov     rcx, [rsp+110h+pv]; pv
0x180014a9d  test    rcx, rcx
0x180014aa0  jz      loc_180014A11
0x180014aa6  call    cs:__imp_CoTaskMemFree
0x180014aac  jmp     loc_180014A11
0x180014ab1  cmp     [rsp+110h+var_E0], 0
0x180014ab6  jz      short loc_180014AC7
0x180014ab8  cmp     qword ptr [r14+0F0h], 0
0x180014ac0  jz      short loc_180014AC7
0x180014ac2  mov     rbx, [rbx]
0x180014ac5  jmp     short loc_180014A98
0x180014ac7  movaps  xmm0, [rbp+57h+var_A0]
0x180014acb  movdqa  [rbp+57h+Buf2], xmm0
0x180014ad0  lea     rdx, [rbp+57h+Buf2]
0x180014ad4  xor     ecx, ecx
0x180014ad6  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x180014adb  test    eax, eax
0x180014add  jns     short loc_180014B05
0x180014adf  test    esi, esi
0x180014ae1  cmovns  esi, eax
0x180014ae4  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180014aeb  jz      short loc_180014B39
0x180014aed  mov     r9d, eax
0x180014af0  lea     r8, aFailedToDelete; "Failed to delete enterprise from databa"...
0x180014af7  lea     rdx, EnterpriseAppMgmtSvcError
0x180014afe  call    McTemplateU0zq_EventWriteTransfer
0x180014b03  jmp     short loc_180014B39
0x180014b05  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 40h
0x180014b0c  jz      short loc_180014B39
0x180014b0e  lea     rax, [rbp+57h+var_A0]
0x180014b12  mov     [rbp+57h+var_60], rax
0x180014b16  mov     [rbp+57h+var_58], 10h
0x180014b1e  lea     rax, [rbp+57h+var_70]
0x180014b22  mov     qword ptr [rsp+110h+var_F0], rax
0x180014b27  mov     r9d, 2
0x180014b2d  lea     rdx, EnterpriseAppMgmtSvcUnenrollComplete
0x180014b34  call    McGenEventWrite_EventWriteTransfer
0x180014b39  movaps  xmm0, [rbp+57h+var_A0]
0x180014b3d  movdqa  [rbp+57h+Buf2], xmm0
0x180014b42  mov     qword ptr [rbp+57h+var_B0.Data1], 0
0x180014b4a  mov     [rsp+110h+var_E0], 0
0x180014b52  mov     rcx, r15; lpCriticalSection
0x180014b55  call    cs:__imp_EnterCriticalSection
0x180014b5b  cmp     dword ptr [r14+80h], 0
0x180014b63  jz      loc_180014C5C
0x180014b69  lea     rcx, [rbp+57h+var_B0]
0x180014b6d  call    ??$replace@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_GUID@@AEAV?$auto_array_ptr@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_GUID,&tlx::_delete_array<_GUID>(_GUID *)>(tlx::auto_array_ptr<_GUID,&tlx::_delete_array<_GUID>(_GUID *)> &)
0x180014b72  mov     rdx, rax
0x180014b75  lea     r8, [rsp+110h+var_E0]
0x180014b7a  call    ?EnumeratePrimaryKeys@EnrollmentManager@@SAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z; EnrollmentManager::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)
0x180014b7f  test    eax, eax
0x180014b81  js      loc_180014C5C
0x180014b87  xor     edi, edi
0x180014b89  cmp     [rsp+110h+var_E0], edi
0x180014b8d  jbe     loc_180014C5C
0x180014b93  mov     ecx, edi
0x180014b95  add     rcx, rcx
0x180014b98  mov     rax, qword ptr [rbp+57h+var_B0.Data1]
0x180014b9c  movups  xmm1, xmmword ptr [rax+rcx*8]
0x180014ba0  movaps  [rbp+57h+var_80], xmm1
0x180014ba4  xorps   xmm0, xmm0
0x180014ba7  movups  [rbp+57h+Buf1], xmm0
0x180014bab  movdqa  [rbp+57h+var_70], xmm1
0x180014bb0  mov     r8d, 3
0x180014bb6  lea     r9, [rbp+57h+Buf1]
0x180014bba  lea     rdx, [rbp+57h+var_70]
0x180014bbe  lea     ecx, [r8-2]
0x180014bc2  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x180014bc7  test    eax, eax
0x180014bc9  js      loc_180014C50
0x180014bcf  mov     r8d, 10h; Size
0x180014bd5  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180014bd9  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180014bdd  call    memcmp_0
0x180014be2  test    eax, eax
0x180014be4  jnz     short loc_180014C50
0x180014be6  movaps  xmm0, [rbp+57h+var_80]
0x180014bea  movdqa  [rbp+57h+var_70], xmm0
0x180014bef  lea     rdx, [rbp+57h+var_70]
0x180014bf3  lea     ecx, [rax+1]
0x180014bf6  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x180014bfb  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 1
0x180014c02  jz      short loc_180014C50
0x180014c04  mov     [rbp+57h+var_D0], eax
0x180014c07  lea     rax, [rbp+57h+var_80]
0x180014c0b  mov     [rbp+57h+var_60], rax
0x180014c0f  mov     [rbp+57h+var_58], 10h
0x180014c17  lea     rax, [rbp+57h+Buf2]
0x180014c1b  mov     [rbp+57h+var_50], rax
0x180014c1f  mov     [rbp+57h+var_48], 10h
0x180014c27  lea     rax, [rbp+57h+var_D0]
0x180014c2b  mov     [rbp+57h+var_40], rax
0x180014c2f  mov     edx, 4
0x180014c34  mov     [rbp+57h+var_38], rdx
0x180014c38  lea     rax, [rbp+57h+var_70]
0x180014c3c  mov     qword ptr [rsp+110h+var_F0], rax
0x180014c41  mov     r9d, edx
0x180014c44  lea     rdx, EnterpriseAppMgmtSvcClearEntryFromEnterpriseId
0x180014c4b  call    McGenEventWrite_EventWriteTransfer
0x180014c50  inc     edi
0x180014c52  cmp     edi, [rsp+110h+var_E0]
0x180014c56  jb      loc_180014B93
0x180014c5c  mov     rcx, r15; lpCriticalSection
0x180014c5f  call    cs:__imp_LeaveCriticalSection
0x180014c65  mov     rcx, qword ptr [rbp+57h+var_B0.Data1]
0x180014c69  test    rcx, rcx
0x180014c6c  jz      short loc_180014C74
0x180014c6e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014c74  mov     rdi, [rbx]
0x180014c77  mov     rax, [rbx+8]
0x180014c7b  mov     [rax], rdi
0x180014c7e  mov     [rdi+8], rax
0x180014c82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014c89  mov     rcx, rbx; void *
0x180014c8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014c91  dec     qword ptr [r14+108h]
0x180014c98  mov     rbx, rdi
0x180014c9b  jmp     loc_180014A98
0x180014ca0  mov     rcx, r15; lpCriticalSection
0x180014ca3  call    cs:__imp_LeaveCriticalSection
0x180014ca9  mov     eax, esi
0x180014cab  mov     rcx, [rbp+57h+var_30]
0x180014caf  xor     rcx, rsp; StackCookie
0x180014cb2  call    __security_check_cookie
0x180014cb7  lea     r11, [rsp+110h+var_20]
0x180014cbf  mov     rbx, [r11+38h]
0x180014cc3  mov     rsi, [r11+40h]
0x180014cc7  mov     rsp, r11
0x180014cca  pop     r15
0x180014ccc  pop     r14
0x180014cce  pop     r13
0x180014cd0  pop     rdi
0x180014cd1  pop     rbp
0x180014cd2  retn
```
