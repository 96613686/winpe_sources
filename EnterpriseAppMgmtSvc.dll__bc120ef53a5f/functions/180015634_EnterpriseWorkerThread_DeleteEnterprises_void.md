# EnterpriseWorkerThread::DeleteEnterprises(void)

- ea: `0x180015634`
- end: `0x180015964`
- name: `?DeleteEnterprises@EnterpriseWorkerThread@@AEAAJXZ`
- size: `816`
- prototype: `__int64 __fastcall(EnterpriseWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800175bc`

## callees

- `0x180002544`
- `0x1800069dc`
- `0x180006ac0`
- `0x1800137c8`
- `0x180015634`
- `0x18001ac50`
- `0x18001b024`
- `0x18001b63c`
- `0x18001c818`
- `0x18006c8c6`
- `0x18006c910`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800158f2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800158f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015718`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800158dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001592d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800158dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001592d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001566a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800157cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001566a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800157cd`

## string_xrefs

- `0x180015768`: `Failed to delete enterprise from database in EnterpriseWorkerThread::DeleteEnterprises.`
- `0x1800156f7`: `EnumInstalledApplications failed in EnterpriseWorkerThread::DeleteEnterprises.`

## pseudocode

```c
__int64 __fastcall EnterpriseWorkerThread::DeleteEnterprises(EnterpriseWorkerThread *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  int v3; // esi
  char *v4; // rbx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int i; // edi
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  char *v18; // rdi
  _QWORD *v19; // rax
  unsigned int v21; // [rsp+30h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-81h] BYREF
  int v23; // [rsp+40h] [rbp-79h] BYREF
  GUID Buf2; // [rsp+50h] [rbp-69h] BYREF
  struct _GUID v25; // [rsp+60h] [rbp-59h] BYREF
  GUID v26; // [rsp+70h] [rbp-49h] BYREF
  __int128 Buf1; // [rsp+80h] [rbp-39h] BYREF
  __int128 v28; // [rsp+90h] [rbp-29h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-19h] BYREF
  GUID *v30; // [rsp+B0h] [rbp-9h]
  __int64 v31; // [rsp+B8h] [rbp-1h]
  GUID *p_Buf2; // [rsp+C0h] [rbp+7h]
  __int64 v33; // [rsp+C8h] [rbp+Fh]
  int *v34; // [rsp+D0h] [rbp+17h]
  __int64 v35; // [rsp+D8h] [rbp+1Fh]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v3 = 0;
  v4 = (char *)*((_QWORD *)this + 31);
  while ( v4 != (char *)this + 248 )
  {
    v26 = (GUID)*((_OWORD *)v4 + 1);
    v21 = 0;
    pv = 0;
    Buf2 = GUID_NULL;
    v25 = (struct _GUID)*((_OWORD *)v4 + 1);
    v5 = EnrollmentManager::EnumInstalledApplications(&v25, &Buf2, (struct _GUID **)&pv, &v21, 0, 1);
    if ( v5 >= 0 )
    {
      if ( v21 && *((_QWORD *)this + 30) )
      {
        v4 = *(char **)v4;
      }
      else
      {
        Buf2 = v26;
        v8 = EnrollmentManager::DeleteRecord(0, &Buf2, v7);
        if ( v8 >= 0 )
        {
          if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x40) != 0 )
          {
            v30 = &v26;
            v31 = 16;
            McGenEventWrite_EventWriteTransfer(v9, EnterpriseAppMgmtSvcUnenrollComplete, v10, 2);
          }
        }
        else
        {
          if ( v3 >= 0 )
            v3 = v8;
          if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v9,
              EnterpriseAppMgmtSvcError,
              L"Failed to delete enterprise from database in EnterpriseWorkerThread::DeleteEnterprises.",
              (unsigned int)v8);
        }
        Buf2 = v26;
        *(_QWORD *)&v25.Data1 = 0;
        v21 = 0;
        EnterCriticalSection(v2);
        if ( *((_DWORD *)this + 32) )
        {
          v11 = tlx::replace<_GUID,&void tlx::_delete_array<_GUID>(_GUID *)>(&v25);
          if ( (int)EnrollmentManager::EnumeratePrimaryKeys(v12, v11, &v21) >= 0 )
          {
            for ( i = 0; i < v21; ++i )
            {
              v28 = *(_OWORD *)(*(_QWORD *)&v25.Data1 + 16LL * i);
              Buf1 = 0;
              v29 = v28;
              if ( (int)EnrollmentManager::RetrieveGUID(1, &v29, 3, &Buf1) >= 0 && !memcmp_0(&Buf1, &Buf2, 0x10u) )
              {
                v29 = v28;
                v15 = EnrollmentManager::DeleteRecord(1, &v29, v14);
                if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 1) != 0 )
                {
                  v23 = v15;
                  v30 = (GUID *)&v28;
                  v31 = 16;
                  p_Buf2 = &Buf2;
                  v33 = 16;
                  v34 = &v23;
                  v35 = 4;
                  McGenEventWrite_EventWriteTransfer(v16, EnterpriseAppMgmtSvcClearEntryFromEnterpriseId, v17, 4);
                }
              }
            }
          }
        }
        LeaveCriticalSection(v2);
        if ( *(_QWORD *)&v25.Data1 )
          operator delete[](*(void **)&v25.Data1);
        v18 = *(char **)v4;
        v19 = (_QWORD *)*((_QWORD *)v4 + 1);
        *v19 = *(_QWORD *)v4;
        *((_QWORD *)v18 + 1) = v19;
        operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
        --*((_QWORD *)this + 33);
        v4 = v18;
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
0x180015634  mov     [rsp-8+arg_8], rbx
0x180015639  mov     [rsp-8+arg_10], rsi
0x18001563e  push    rbp
0x18001563f  push    rdi
0x180015640  push    r13
0x180015642  push    r14
0x180015644  push    r15
0x180015646  lea     rbp, [rsp-37h]
0x18001564b  sub     rsp, 0F0h
0x180015652  mov     rax, cs:__security_cookie
0x180015659  xor     rax, rsp
0x18001565c  mov     [rbp+57h+var_30], rax
0x180015660  mov     r14, rcx
0x180015663  lea     r15, [rcx+58h]
0x180015667  mov     rcx, r15; lpCriticalSection
0x18001566a  call    cs:__imp_EnterCriticalSection
0x180015671  nop     dword ptr [rax+rax+00h]
0x180015676  xor     esi, esi
0x180015678  lea     r13, [r14+0F8h]
0x18001567f  mov     rbx, [r13+0]
0x180015683  cmp     rbx, r13
0x180015686  jz      loc_18001592A
0x18001568c  movups  xmm0, xmmword ptr [rbx+10h]
0x180015690  movdqu  [rbp+57h+var_A0], xmm0
0x180015695  mov     [rsp+110h+var_E0], 0
0x18001569d  mov     [rsp+110h+pv], 0
0x1800156a6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800156ad  movdqu  [rbp+57h+Buf2], xmm0
0x1800156b2  movups  xmm0, xmmword ptr [rbx+10h]
0x1800156b6  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x1800156bb  mov     [rsp+110h+var_E8], 1; int
0x1800156c3  mov     [rsp+110h+var_F0], 0; int
0x1800156cb  lea     r9, [rsp+110h+var_E0]; unsigned int *
0x1800156d0  lea     r8, [rsp+110h+pv]; struct _GUID **
0x1800156d5  lea     rdx, [rbp+57h+Buf2]; struct _GUID
0x1800156d9  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x1800156dd  call    ?EnumInstalledApplications@EnrollmentManager@@SAJU_GUID@@0PEAPEAU2@PEAKHH@Z; EnrollmentManager::EnumInstalledApplications(_GUID,_GUID,_GUID * *,ulong *,int,int)
0x1800156e2  test    eax, eax
0x1800156e4  jns     short loc_180015729
0x1800156e6  test    esi, esi
0x1800156e8  cmovns  esi, eax
0x1800156eb  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x1800156f2  jz      short loc_18001570A
0x1800156f4  mov     r9d, eax
0x1800156f7  lea     r8, aEnuminstalleda; "EnumInstalledApplications failed in Ent"...
0x1800156fe  lea     rdx, EnterpriseAppMgmtSvcError
0x180015705  call    McTemplateU0zq_EventWriteTransfer
0x18001570a  mov     rcx, [rsp+110h+pv]; pv
0x18001570f  test    rcx, rcx
0x180015712  jz      loc_180015683
0x180015718  call    cs:__imp_CoTaskMemFree
0x18001571f  nop     dword ptr [rax+rax+00h]
0x180015724  jmp     loc_180015683
0x180015729  cmp     [rsp+110h+var_E0], 0
0x18001572e  jz      short loc_18001573F
0x180015730  cmp     qword ptr [r14+0F0h], 0
0x180015738  jz      short loc_18001573F
0x18001573a  mov     rbx, [rbx]
0x18001573d  jmp     short loc_18001570A
0x18001573f  movaps  xmm0, [rbp+57h+var_A0]
0x180015743  movdqa  [rbp+57h+Buf2], xmm0
0x180015748  lea     rdx, [rbp+57h+Buf2]
0x18001574c  xor     ecx, ecx
0x18001574e  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x180015753  test    eax, eax
0x180015755  jns     short loc_18001577D
0x180015757  test    esi, esi
0x180015759  cmovns  esi, eax
0x18001575c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180015763  jz      short loc_1800157B1
0x180015765  mov     r9d, eax
0x180015768  lea     r8, aFailedToDelete; "Failed to delete enterprise from databa"...
0x18001576f  lea     rdx, EnterpriseAppMgmtSvcError
0x180015776  call    McTemplateU0zq_EventWriteTransfer
0x18001577b  jmp     short loc_1800157B1
0x18001577d  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 40h
0x180015784  jz      short loc_1800157B1
0x180015786  lea     rax, [rbp+57h+var_A0]
0x18001578a  mov     [rbp+57h+var_60], rax
0x18001578e  mov     [rbp+57h+var_58], 10h
0x180015796  lea     rax, [rbp+57h+var_70]
0x18001579a  mov     qword ptr [rsp+110h+var_F0], rax
0x18001579f  mov     r9d, 2
0x1800157a5  lea     rdx, EnterpriseAppMgmtSvcUnenrollComplete
0x1800157ac  call    McGenEventWrite_EventWriteTransfer
0x1800157b1  movaps  xmm0, [rbp+57h+var_A0]
0x1800157b5  movdqa  [rbp+57h+Buf2], xmm0
0x1800157ba  mov     qword ptr [rbp+57h+var_B0.Data1], 0
0x1800157c2  mov     [rsp+110h+var_E0], 0
0x1800157ca  mov     rcx, r15; lpCriticalSection
0x1800157cd  call    cs:__imp_EnterCriticalSection
0x1800157d4  nop     dword ptr [rax+rax+00h]
0x1800157d9  cmp     dword ptr [r14+80h], 0
0x1800157e1  jz      loc_1800158DA
0x1800157e7  lea     rcx, [rbp+57h+var_B0]
0x1800157eb  call    ??$replace@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_GUID@@AEAV?$auto_array_ptr@U_GUID@@$1??$_delete_array@U_GUID@@@tlx@@YAXPEAU1@@Z@0@@Z; tlx::replace<_GUID,&tlx::_delete_array<_GUID>(_GUID *)>(tlx::auto_array_ptr<_GUID,&tlx::_delete_array<_GUID>(_GUID *)> &)
0x1800157f0  mov     rdx, rax
0x1800157f3  lea     r8, [rsp+110h+var_E0]
0x1800157f8  call    ?EnumeratePrimaryKeys@EnrollmentManager@@SAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z; EnrollmentManager::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)
0x1800157fd  test    eax, eax
0x1800157ff  js      loc_1800158DA
0x180015805  xor     edi, edi
0x180015807  cmp     [rsp+110h+var_E0], edi
0x18001580b  jbe     loc_1800158DA
0x180015811  mov     ecx, edi
0x180015813  add     rcx, rcx
0x180015816  mov     rax, qword ptr [rbp+57h+var_B0.Data1]
0x18001581a  movups  xmm1, xmmword ptr [rax+rcx*8]
0x18001581e  movaps  [rbp+57h+var_80], xmm1
0x180015822  xorps   xmm0, xmm0
0x180015825  movups  [rbp+57h+Buf1], xmm0
0x180015829  movdqa  [rbp+57h+var_70], xmm1
0x18001582e  mov     r8d, 3
0x180015834  lea     r9, [rbp+57h+Buf1]
0x180015838  lea     rdx, [rbp+57h+var_70]
0x18001583c  lea     ecx, [r8-2]
0x180015840  call    ?RetrieveGUID@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@GPEAU3@@Z; EnrollmentManager::RetrieveGUID(TABLEID,_GUID,ushort,_GUID *)
0x180015845  test    eax, eax
0x180015847  js      loc_1800158CE
0x18001584d  mov     r8d, 10h; Size
0x180015853  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180015857  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18001585b  call    memcmp_0
0x180015860  test    eax, eax
0x180015862  jnz     short loc_1800158CE
0x180015864  movaps  xmm0, [rbp+57h+var_80]
0x180015868  movdqa  [rbp+57h+var_70], xmm0
0x18001586d  lea     rdx, [rbp+57h+var_70]
0x180015871  lea     ecx, [rax+1]
0x180015874  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x180015879  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 1
0x180015880  jz      short loc_1800158CE
0x180015882  mov     [rbp+57h+var_D0], eax
0x180015885  lea     rax, [rbp+57h+var_80]
0x180015889  mov     [rbp+57h+var_60], rax
0x18001588d  mov     [rbp+57h+var_58], 10h
0x180015895  lea     rax, [rbp+57h+Buf2]
0x180015899  mov     [rbp+57h+var_50], rax
0x18001589d  mov     [rbp+57h+var_48], 10h
0x1800158a5  lea     rax, [rbp+57h+var_D0]
0x1800158a9  mov     [rbp+57h+var_40], rax
0x1800158ad  mov     edx, 4
0x1800158b2  mov     [rbp+57h+var_38], rdx
0x1800158b6  lea     rax, [rbp+57h+var_70]
0x1800158ba  mov     qword ptr [rsp+110h+var_F0], rax
0x1800158bf  mov     r9d, edx
0x1800158c2  lea     rdx, EnterpriseAppMgmtSvcClearEntryFromEnterpriseId
0x1800158c9  call    McGenEventWrite_EventWriteTransfer
0x1800158ce  inc     edi
0x1800158d0  cmp     edi, [rsp+110h+var_E0]
0x1800158d4  jb      loc_180015811
0x1800158da  mov     rcx, r15; lpCriticalSection
0x1800158dd  call    cs:__imp_LeaveCriticalSection
0x1800158e4  nop     dword ptr [rax+rax+00h]
0x1800158e9  mov     rcx, qword ptr [rbp+57h+var_B0.Data1]
0x1800158ed  test    rcx, rcx
0x1800158f0  jz      short loc_1800158FE
0x1800158f2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800158f9  nop     dword ptr [rax+rax+00h]
0x1800158fe  mov     rdi, [rbx]
0x180015901  mov     rax, [rbx+8]
0x180015905  mov     [rax], rdi
0x180015908  mov     [rdi+8], rax
0x18001590c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015913  mov     rcx, rbx; void *
0x180015916  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001591b  dec     qword ptr [r14+108h]
0x180015922  mov     rbx, rdi
0x180015925  jmp     loc_18001570A
0x18001592a  mov     rcx, r15; lpCriticalSection
0x18001592d  call    cs:__imp_LeaveCriticalSection
0x180015934  nop     dword ptr [rax+rax+00h]
0x180015939  mov     eax, esi
0x18001593b  mov     rcx, [rbp+57h+var_30]
0x18001593f  xor     rcx, rsp; StackCookie
0x180015942  call    __security_check_cookie
0x180015947  lea     r11, [rsp+110h+var_20]
0x18001594f  mov     rbx, [r11+38h]
0x180015953  mov     rsi, [r11+40h]
0x180015957  mov     rsp, r11
0x18001595a  pop     r15
0x18001595c  pop     r14
0x18001595e  pop     r13
0x180015960  pop     rdi
0x180015961  pop     rbp
0x180015962  retn
```
