# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)

- ea: `0x1800021d0`
- end: `0x180002b41`
- name: `??$IsPublishedForUser_Internal@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@0AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z`
- size: `2417`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001d4c`
- `0x180001f78`
- `0x180016364`

## callees

- `0x1800021d0`
- `0x180002b48`
- `0x180007d54`
- `0x180009434`
- `0x18000d72c`
- `0x18000ef74`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800025d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002733`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000285a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800025d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002733`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000285a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800025a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800025fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800026fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000282d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800025a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800025fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800026fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000282d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800026d8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800026d8`

## string_xrefs

- `0x18000244c`: `ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings on demand succeeded, but mappings are not there. package moniker %s. group moniker %s. user sid %s. result %d.`
- `0x1800024c2`: `ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings on demand failed. package moniker %s. group moniker %s. user sid %s. result %d.`
- `0x1800027c0`: `ConfigurationManager::IsPublishedForUser_Internal() - Group %s is published for the user and so is package %s for sid %s.`
- `0x180002a33`: `ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings for globally-published package succeeded, but mappings are not there. package moniker %s. group moniker %s. user sid %s. result %d.`
- `0x180002ad0`: `ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings for globally-published package failed. package moniker %s. group moniker %s. user sid %s. result %d.`

## pseudocode

```c
char __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING **a2,
        _QWORD *a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v5; // eax
  const UNICODE_STRING **v8; // r15
  __int64 v9; // rdi
  __int64 v10; // r9
  __int64 v11; // rax
  _DWORD *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // eax
  wchar_t *Buffer; // rdx
  int v17; // edi
  unsigned int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // eax
  wchar_t *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  int *v31; // rdx
  unsigned int v32; // eax
  wchar_t *v33; // r9
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // eax
  int *v38; // rdx
  unsigned int v39; // eax
  wchar_t *v40; // r9
  volatile signed __int32 *v41; // rbx
  bool v42; // di
  volatile signed __int32 *v44; // rbx
  __int64 v45; // rax
  _DWORD *v46; // rbx
  int v47; // ebx
  int v48; // eax
  PVOID v49; // rcx
  unsigned int v50; // eax
  __int64 v51; // rdx
  unsigned int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  unsigned int v55; // eax
  __int64 v56; // rcx
  int v57; // r13d
  const UNICODE_STRING *v58; // rdi
  char *v59; // r15
  const UNICODE_STRING **i; // rbx
  const UNICODE_STRING *v61; // rax
  unsigned int v62; // eax
  __int64 v63; // r8
  __int64 v64; // rax
  __int64 v65; // rcx
  unsigned int v66; // eax
  int *v67; // rdx
  unsigned int v68; // eax
  wchar_t *v69; // r9
  volatile signed __int32 *v70; // rbx
  int v71; // r10d
  unsigned int v72; // ecx
  __int64 v73; // r9
  __int64 v74; // rax
  __int64 v75; // rcx
  unsigned int v76; // eax
  __int64 v77; // r8
  unsigned int v78; // eax
  wchar_t *v79; // rdx
  int User; // edi
  unsigned int v81; // eax
  __int64 v82; // r8
  __int64 v83; // rax
  __int64 v84; // rcx
  unsigned int v85; // eax
  int *v86; // rdx
  unsigned int v87; // eax
  wchar_t *v88; // r9
  __int64 v89; // r8
  __int64 v90; // rax
  __int64 v91; // rcx
  unsigned int v92; // eax
  int *v93; // rdx
  unsigned int v94; // eax
  wchar_t *v95; // r9
  volatile signed __int32 *v96; // rbx
  __int128 v97; // [rsp+48h] [rbp-31h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  __int64 v100; // [rsp+78h] [rbp-1h] BYREF
  PVOID v101; // [rsp+80h] [rbp+7h]
  struct _UNICODE_STRING v102; // [rsp+88h] [rbp+Fh] BYREF
  char v105; // [rsp+E8h] [rbp+6Fh] BYREF

  v5 = *(_DWORD *)a4 >> 1;
  v8 = a2;
  v9 = a1;
  v97 = 0;
  if ( v5 <= 0xFFFF && (_WORD)v5 )
    v10 = *(_QWORD *)(a4 + 8);
  else
    LODWORD(v10) = 0;
  v11 = a3[1];
  if ( v11 && *(_DWORD *)(v11 + 8) && (v12 = (_DWORD *)*a3) != 0 && (v13 = *v12 >> 1, v13 <= 0xFFFF) && (_WORD)v13 )
    v14 = *((_QWORD *)v12 + 1);
  else
    LODWORD(v14) = 0;
  v15 = *(_DWORD *)&(*a2)->Length >> 1;
  if ( v15 <= 0xFFFF && (_WORD)v15 )
    Buffer = (*a2)->Buffer;
  else
    LODWORD(Buffer) = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(
              v9,
              (_DWORD)Buffer,
              v14,
              v10,
              (__int64)&v97) < 0 )
  {
    v45 = a3[1];
    v105 = 0;
    if ( v45 )
    {
      if ( *(_DWORD *)(v45 + 8) )
      {
        v46 = (_DWORD *)*a3;
        if ( *a3 )
        {
          P[0] = 0;
          P[1] = 0;
          RtlInitUnicodeString(&DestinationString, 0);
          v47 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
                  v9,
                  P,
                  v46,
                  &v105);
          if ( P[1] )
            ExFreePoolWithTag(P[1], 0);
          if ( v47 >= 0 )
          {
            if ( v105 )
            {
              P[0] = 0;
              P[1] = 0;
              RtlInitUnicodeString(&DestinationString, 0);
              v48 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
                      v9,
                      *v8,
                      P,
                      &v105);
              v49 = P[1];
              goto LABEL_134;
            }
            v50 = *(_DWORD *)a4 >> 1;
            if ( v50 <= 0xFFFF && (_WORD)v50 )
              v51 = *(_QWORD *)(a4 + 8);
            else
              v51 = 0;
            v52 = *(_DWORD *)*a3 >> 1;
            if ( v52 <= 0xFFFF && (_WORD)v52 )
              v53 = *(_QWORD *)(*a3 + 8LL);
            else
              v53 = 0;
            if ( (int)Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::is_group_entitled_to_user(
                        v53,
                        v51) >= 0 )
            {
              v54 = *a3;
              *(_OWORD *)P = 0;
              v55 = *(_DWORD *)v54 >> 1;
              if ( v55 <= 0xFFFF && (_WORD)v55 )
                v56 = *(_QWORD *)(v54 + 8);
              else
                v56 = 0;
              v57 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
                      v56,
                      P);
              if ( v57 >= 0 )
              {
                v58 = *v8;
                v59 = (char *)P[0] + 24;
                for ( i = (const UNICODE_STRING **)*((_QWORD *)P[0] + 6); ; i = (const UNICODE_STRING **)i[3] )
                {
                  if ( i == (const UNICODE_STRING **)v59 )
                  {
                    v8 = a2;
                    LODWORD(v9) = a1;
                    goto LABEL_129;
                  }
                  if ( *i )
                  {
                    v61 = i[1];
                    if ( v61 )
                    {
                      if ( LODWORD(v61->Buffer) && !RtlCompareUnicodeString(*i + 1, v58 + 1, 1u) )
                        break;
                    }
                  }
                }
                v100 = 0;
                v101 = 0;
                RtlInitUnicodeString(&v102, 0);
                v8 = a2;
                LODWORD(v9) = a1;
                v57 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
                        a1,
                        *a2,
                        &v100,
                        &v105);
                if ( v101 )
                  ExFreePoolWithTag(v101, 0);
                if ( !v105 )
                {
                  v62 = *(_DWORD *)a4 >> 1;
                  if ( v62 <= 0xFFFF && (_WORD)v62 )
                    v63 = *(_QWORD *)(a4 + 8);
                  else
                    v63 = 0;
                  v64 = a3[1];
                  if ( v64 && *(_DWORD *)(v64 + 8) && (v65 = *a3) != 0 )
                  {
                    v66 = *(_DWORD *)v65 >> 1;
                    if ( v66 <= 0xFFFF && (_WORD)v66 )
                      v67 = *(int **)(v65 + 8);
                    else
                      v67 = 0;
                  }
                  else
                  {
                    v67 = &dword_18001E3EC;
                  }
                  v68 = *(_DWORD *)&(*a2)->Length >> 1;
                  if ( v68 <= 0xFFFF && (_WORD)v68 )
                    v69 = (*a2)->Buffer;
                  else
                    v69 = 0;
                  LogWrite(
                    2,
                    0,
                    L"ConfigurationManager::IsPublishedForUser_Internal() - Group %s is published for the user and so is p"
                     "ackage %s for sid %s.",
                    v69,
                    v67,
                    v63);
                }
              }
LABEL_129:
              v70 = (volatile signed __int32 *)P[1];
              if ( P[1] )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)P[1] + 2) )
                {
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
                  if ( !_InterlockedDecrement(v70 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 16LL))(v70);
                }
              }
LABEL_136:
              if ( v57 >= 0 && v105 )
              {
                v71 = VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(
                        64,
                        a5);
                v72 = *(_DWORD *)a4 >> 1;
                if ( v71 >= 0 )
                {
                  if ( v72 <= 0xFFFF && (_WORD)v72 )
                    v73 = *(_QWORD *)(a4 + 8);
                  else
                    LODWORD(v73) = 0;
                  v74 = a3[1];
                  if ( v74
                    && *(_DWORD *)(v74 + 8)
                    && (v75 = *a3) != 0
                    && (v76 = *(_DWORD *)v75 >> 1, v76 <= 0xFFFF)
                    && (_WORD)v76 )
                  {
                    v77 = *(_QWORD *)(v75 + 8);
                  }
                  else
                  {
                    LODWORD(v77) = 0;
                  }
                  v78 = *(_DWORD *)&(*v8)->Length >> 1;
                  if ( v78 <= 0xFFFF && (_WORD)v78 )
                    v79 = (*v8)->Buffer;
                  else
                    LODWORD(v79) = 0;
                  User = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(
                           v9,
                           (_DWORD)v79,
                           v77,
                           v73,
                           (__int64)&v97);
                  if ( User < 0 )
                  {
                    v81 = *(_DWORD *)a4 >> 1;
                    if ( v81 <= 0xFFFF && (_WORD)v81 )
                      v82 = *(_QWORD *)(a4 + 8);
                    else
                      v82 = 0;
                    v83 = a3[1];
                    if ( v83 && *(_DWORD *)(v83 + 8) && (v84 = *a3) != 0 )
                    {
                      v85 = *(_DWORD *)v84 >> 1;
                      if ( v85 <= 0xFFFF && (_WORD)v85 )
                        v86 = *(int **)(v84 + 8);
                      else
                        v86 = 0;
                    }
                    else
                    {
                      v86 = &dword_18001E3EC;
                    }
                    v87 = *(_DWORD *)&(*v8)->Length >> 1;
                    if ( v87 <= 0xFFFF && (_WORD)v87 )
                      v88 = (*v8)->Buffer;
                    else
                      v88 = 0;
                    LogWrite(
                      1,
                      0,
                      L"ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings for globally-pu"
                       "blished package succeeded, but mappings are not there. package moniker %s. group moniker %s. user"
                       " sid %s. result %d.",
                      v88,
                      v86,
                      v82,
                      User);
                  }
                  v41 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
                  v42 = User >= 0;
                  if ( !*((_QWORD *)&v97 + 1) )
                    return v42;
LABEL_70:
                  if ( !_InterlockedDecrement(v41 + 2) )
                  {
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
                    if ( !_InterlockedDecrement(v41 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                  return v42;
                }
                if ( v72 <= 0xFFFF && (_WORD)v72 )
                  v89 = *(_QWORD *)(a4 + 8);
                else
                  v89 = 0;
                v90 = a3[1];
                if ( v90 && *(_DWORD *)(v90 + 8) && (v91 = *a3) != 0 )
                {
                  v92 = *(_DWORD *)v91 >> 1;
                  if ( v92 <= 0xFFFF && (_WORD)v92 )
                    v93 = *(int **)(v91 + 8);
                  else
                    v93 = 0;
                }
                else
                {
                  v93 = &dword_18001E3EC;
                }
                v94 = *(_DWORD *)&(*v8)->Length >> 1;
                if ( v94 <= 0xFFFF && (_WORD)v94 )
                  v95 = (*v8)->Buffer;
                else
                  v95 = 0;
                LogWrite(
                  1,
                  0,
                  L"ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings for globally-publis"
                   "hed package failed. package moniker %s. group moniker %s. user sid %s. result %d.",
                  v95,
                  v93,
                  v89,
                  v71);
              }
            }
          }
          v96 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
          if ( *((_QWORD *)&v97 + 1) )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL)) )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 8LL))(v96);
              if ( !_InterlockedDecrement(v96 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v96 + 16LL))(v96);
            }
          }
          return 0;
        }
      }
    }
    v100 = 0;
    v101 = 0;
    RtlInitUnicodeString(&v102, 0);
    v48 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedGlobally<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            v9,
            *v8,
            &v100,
            &v105);
    v49 = v101;
LABEL_134:
    v57 = v48;
    if ( v49 )
      ExFreePoolWithTag(v49, 0);
    goto LABEL_136;
  }
  if ( *(_BYTE *)(v97 + 185) )
  {
    v17 = VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(
            128,
            a5);
    v18 = *(_DWORD *)a4 >> 1;
    if ( v17 < 0 )
    {
      if ( v18 <= 0xFFFF && (_WORD)v18 )
        v34 = *(_QWORD *)(a4 + 8);
      else
        v34 = 0;
      v35 = a3[1];
      if ( v35 && *(_DWORD *)(v35 + 8) && (v36 = *a3) != 0 )
      {
        v37 = *(_DWORD *)v36 >> 1;
        if ( v37 <= 0xFFFF && (_WORD)v37 )
          v38 = *(int **)(v36 + 8);
        else
          v38 = 0;
      }
      else
      {
        v38 = &dword_18001E3EC;
      }
      v39 = *(_DWORD *)&(*v8)->Length >> 1;
      if ( v39 <= 0xFFFF && (_WORD)v39 )
        v40 = (*v8)->Buffer;
      else
        v40 = 0;
      LogWrite(
        1,
        0,
        L"ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings on demand failed. package mon"
         "iker %s. group moniker %s. user sid %s. result %d.",
        v40,
        v38,
        v34,
        v17);
    }
    else
    {
      if ( v18 <= 0xFFFF && (_WORD)v18 )
        v19 = *(_QWORD *)(a4 + 8);
      else
        LODWORD(v19) = 0;
      v20 = a3[1];
      if ( v20 && *(_DWORD *)(v20 + 8) && (v21 = *a3) != 0 && (v22 = *(_DWORD *)v21 >> 1, v22 <= 0xFFFF) && (_WORD)v22 )
        v23 = *(_QWORD *)(v21 + 8);
      else
        LODWORD(v23) = 0;
      v24 = *(_DWORD *)&(*v8)->Length >> 1;
      if ( v24 <= 0xFFFF && (_WORD)v24 )
        v25 = (*v8)->Buffer;
      else
        LODWORD(v25) = 0;
      v17 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(
              a1,
              (_DWORD)v25,
              v23,
              v19,
              (__int64)&v97);
      if ( v17 < 0 )
      {
        v26 = *(_DWORD *)a4 >> 1;
        if ( v26 <= 0xFFFF && (_WORD)v26 )
          v27 = *(_QWORD *)(a4 + 8);
        else
          v27 = 0;
        v28 = a3[1];
        if ( v28 && *(_DWORD *)(v28 + 8) && (v29 = *a3) != 0 )
        {
          v30 = *(_DWORD *)v29 >> 1;
          if ( v30 <= 0xFFFF && (_WORD)v30 )
            v31 = *(int **)(v29 + 8);
          else
            v31 = 0;
        }
        else
        {
          v31 = &dword_18001E3EC;
        }
        v32 = *(_DWORD *)&(*v8)->Length >> 1;
        if ( v32 <= 0xFFFF && (_WORD)v32 )
          v33 = (*v8)->Buffer;
        else
          v33 = 0;
        LogWrite(
          1,
          0,
          L"ConfigurationManager::IsPublishedForUser_Internal() - Request to generate mappings on demand succeeded, but ma"
           "ppings are not there. package moniker %s. group moniker %s. user sid %s. result %d.",
          v33,
          v31,
          v27,
          v17);
      }
    }
    v41 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
    v42 = v17 >= 0;
    if ( !*((_QWORD *)&v97 + 1) )
      return v42;
    goto LABEL_70;
  }
  v44 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
  if ( *((_QWORD *)&v97 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
      if ( !_InterlockedDecrement(v44 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 16LL))(v44);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800021d0  mov     rax, rsp
0x1800021d3  mov     [rax+20h], rbx
0x1800021d7  mov     [rax+10h], rdx
0x1800021db  mov     [rax+8], rcx
0x1800021df  push    rbp
0x1800021e0  push    rsi
0x1800021e1  push    rdi
0x1800021e2  push    r12
0x1800021e4  push    r13
0x1800021e6  push    r14
0x1800021e8  push    r15
0x1800021ea  lea     rbp, [rax-57h]
0x1800021ee  sub     rsp, 90h
0x1800021f5  mov     eax, [r9]
0x1800021f8  xor     r13d, r13d
0x1800021fb  shr     eax, 1
0x1800021fd  mov     ebx, 0FFFFh
0x180002202  xorps   xmm0, xmm0
0x180002205  mov     r12, r9
0x180002208  mov     r14, r8
0x18000220b  mov     r15, rdx
0x18000220e  mov     rdi, rcx
0x180002211  movdqu  [rbp+4Fh+var_80], xmm0
0x180002216  cmp     eax, ebx
0x180002218  ja      short loc_180002225
0x18000221a  test    ax, ax
0x18000221d  jz      short loc_180002225
0x18000221f  mov     r9, [r9+8]
0x180002223  jmp     short loc_180002228
0x180002225  mov     r9, r13
0x180002228  mov     rax, [r8+8]
0x18000222c  test    rax, rax
0x18000222f  jz      short loc_180002253
0x180002231  mov     eax, [rax+8]
0x180002234  test    eax, eax
0x180002236  jz      short loc_180002253
0x180002238  mov     rcx, [r8]
0x18000223b  test    rcx, rcx
0x18000223e  jz      short loc_180002253
0x180002240  mov     eax, [rcx]
0x180002242  shr     eax, 1
0x180002244  cmp     eax, ebx
0x180002246  ja      short loc_180002253
0x180002248  test    ax, ax
0x18000224b  jz      short loc_180002253
0x18000224d  mov     r8, [rcx+8]
0x180002251  jmp     short loc_180002256
0x180002253  mov     r8, r13
0x180002256  mov     rcx, [rdx]
0x180002259  mov     eax, [rcx]
0x18000225b  shr     eax, 1
0x18000225d  cmp     eax, ebx
0x18000225f  ja      short loc_18000226C
0x180002261  test    ax, ax
0x180002264  jz      short loc_18000226C
0x180002266  mov     rdx, [rcx+8]
0x18000226a  jmp     short loc_18000226F
0x18000226c  mov     rdx, r13
0x18000226f  lea     rax, [rbp+4Fh+var_80]
0x180002273  mov     rcx, rdi
0x180002276  mov     [rsp+0C0h+var_A0], rax
0x18000227b  call    ?FindUser@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180002280  test    eax, eax
0x180002282  js      loc_18000256E
0x180002288  mov     rax, qword ptr [rbp+4Fh+var_80]
0x18000228c  cmp     [rax+0B9h], r13b
0x180002293  jz      loc_180002527
0x180002299  mov     eax, [r12]
0x18000229d  shr     eax, 1
0x18000229f  cmp     eax, ebx
0x1800022a1  ja      short loc_1800022AF
0x1800022a3  test    ax, ax
0x1800022a6  jz      short loc_1800022AF
0x1800022a8  mov     r10, [r12+8]
0x1800022ad  jmp     short loc_1800022B2
0x1800022af  mov     r10, r13
0x1800022b2  mov     rcx, [r14+8]
0x1800022b6  test    rcx, rcx
0x1800022b9  jz      short loc_1800022E1
0x1800022bb  mov     eax, [rcx+8]
0x1800022be  mov     rcx, [r14+8]
0x1800022c2  test    eax, eax
0x1800022c4  jz      short loc_1800022E1
0x1800022c6  mov     rdx, [r14]
0x1800022c9  test    rdx, rdx
0x1800022cc  jz      short loc_1800022E1
0x1800022ce  mov     eax, [rdx]
0x1800022d0  shr     eax, 1
0x1800022d2  cmp     eax, ebx
0x1800022d4  ja      short loc_1800022E1
0x1800022d6  test    ax, ax
0x1800022d9  jz      short loc_1800022E1
0x1800022db  mov     r8, [rdx+8]
0x1800022df  jmp     short loc_1800022E4
0x1800022e1  mov     r8, r13
0x1800022e4  test    rcx, rcx
0x1800022e7  jz      short loc_1800022FC
0x1800022e9  mov     eax, [rcx+8]
0x1800022ec  test    eax, eax
0x1800022ee  jz      short loc_1800022FC
0x1800022f0  cmp     [r14], r13
0x1800022f3  jz      short loc_1800022FC
0x1800022f5  mov     eax, 4
0x1800022fa  jmp     short loc_18000232D
0x1800022fc  mov     r9, [r15]
0x1800022ff  mov     eax, [r9]
0x180002302  shr     eax, 1
0x180002304  cmp     eax, ebx
0x180002306  ja      short loc_180002313
0x180002308  test    ax, ax
0x18000230b  jz      short loc_180002313
0x18000230d  mov     r9, [r9+8]
0x180002311  jmp     short loc_180002316
0x180002313  mov     r9, r13
0x180002316  mov     rax, r9
0x180002319  neg     rax
0x18000231c  mov     eax, 4
0x180002321  sbb     ecx, ecx
0x180002323  and     ecx, 0FFFFFFFEh
0x180002326  add     eax, ecx
0x180002328  test    r9, r9
0x18000232b  jnz     short loc_180002330
0x18000232d  mov     r9, r8
0x180002330  mov     edx, [rbp+4Fh+arg_20]
0x180002333  xor     r8d, r8d
0x180002336  mov     byte ptr [rsp+38h], 1
0x18000233b  mov     ecx, 80h
0x180002340  mov     dword ptr [rsp+0C0h+var_90], eax
0x180002344  mov     [rsp+0C0h+var_98], r13d
0x180002349  mov     [rsp+0C0h+var_A0], r10
0x18000234e  call    ?SendNotification@?$VEMgrNotifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJKKKPEB_W0KK_N@Z; VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(ulong,ulong,ulong,wchar_t const *,wchar_t const *,ulong,ulong,bool)
0x180002353  mov     edi, eax
0x180002355  mov     eax, [r12]
0x180002359  shr     eax, 1
0x18000235b  test    edi, edi
0x18000235d  js      loc_180002455
0x180002363  cmp     eax, ebx
0x180002365  ja      short loc_180002373
0x180002367  test    ax, ax
0x18000236a  jz      short loc_180002373
0x18000236c  mov     r9, [r12+8]
0x180002371  jmp     short loc_180002376
0x180002373  mov     r9, r13
0x180002376  mov     rax, [r14+8]
0x18000237a  test    rax, rax
0x18000237d  jz      short loc_1800023A1
0x18000237f  mov     eax, [rax+8]
0x180002382  test    eax, eax
0x180002384  jz      short loc_1800023A1
0x180002386  mov     rcx, [r14]
0x180002389  test    rcx, rcx
0x18000238c  jz      short loc_1800023A1
0x18000238e  mov     eax, [rcx]
0x180002390  shr     eax, 1
0x180002392  cmp     eax, ebx
0x180002394  ja      short loc_1800023A1
0x180002396  test    ax, ax
0x180002399  jz      short loc_1800023A1
0x18000239b  mov     r8, [rcx+8]
0x18000239f  jmp     short loc_1800023A4
0x1800023a1  mov     r8, r13
0x1800023a4  mov     rcx, [r15]
0x1800023a7  mov     eax, [rcx]
0x1800023a9  shr     eax, 1
0x1800023ab  cmp     eax, ebx
0x1800023ad  ja      short loc_1800023BA
0x1800023af  test    ax, ax
0x1800023b2  jz      short loc_1800023BA
0x1800023b4  mov     rdx, [rcx+8]
0x1800023b8  jmp     short loc_1800023BD
0x1800023ba  mov     rdx, r13
0x1800023bd  mov     rcx, [rbp+4Fh+arg_0]
0x1800023c1  lea     rax, [rbp+4Fh+var_80]
0x1800023c5  mov     [rsp+0C0h+var_A0], rax
0x1800023ca  call    ?FindUser@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800023cf  mov     edi, eax
0x1800023d1  test    eax, eax
0x1800023d3  jns     loc_1800024D8
0x1800023d9  mov     eax, [r12]
0x1800023dd  shr     eax, 1
0x1800023df  cmp     eax, ebx
0x1800023e1  ja      short loc_1800023EF
0x1800023e3  test    ax, ax
0x1800023e6  jz      short loc_1800023EF
0x1800023e8  mov     r8, [r12+8]
0x1800023ed  jmp     short loc_1800023F2
0x1800023ef  mov     r8, r13
0x1800023f2  mov     rax, [r14+8]
0x1800023f6  test    rax, rax
0x1800023f9  jz      short loc_180002422
0x1800023fb  mov     eax, [rax+8]
0x1800023fe  test    eax, eax
0x180002400  jz      short loc_180002422
0x180002402  mov     rcx, [r14]
0x180002405  test    rcx, rcx
0x180002408  jz      short loc_180002422
0x18000240a  mov     eax, [rcx]
0x18000240c  shr     eax, 1
0x18000240e  cmp     eax, ebx
0x180002410  ja      short loc_18000241D
0x180002412  test    ax, ax
0x180002415  jz      short loc_18000241D
0x180002417  mov     rdx, [rcx+8]
0x18000241b  jmp     short loc_180002429
0x18000241d  mov     rdx, r13
0x180002420  jmp     short loc_180002429
0x180002422  lea     rdx, dword_18001E3EC
0x180002429  mov     r9, [r15]
0x18000242c  mov     eax, [r9]
0x18000242f  shr     eax, 1
0x180002431  cmp     eax, ebx
0x180002433  ja      short loc_180002440
0x180002435  test    ax, ax
0x180002438  jz      short loc_180002440
0x18000243a  mov     r9, [r9+8]
0x18000243e  jmp     short loc_180002443
0x180002440  mov     r9, r13
0x180002443  mov     dword ptr [rsp+0C0h+var_90], edi
0x180002447  mov     qword ptr [rsp+0C0h+var_98], r8
0x18000244c  lea     r8, aConfigurationm_0; "ConfigurationManager::IsPublishedForUse"...
0x180002453  jmp     short loc_1800024C9
0x180002455  cmp     eax, ebx
0x180002457  ja      short loc_180002465
0x180002459  test    ax, ax
0x18000245c  jz      short loc_180002465
0x18000245e  mov     r8, [r12+8]
0x180002463  jmp     short loc_180002468
0x180002465  mov     r8, r13
0x180002468  mov     rax, [r14+8]
0x18000246c  test    rax, rax
0x18000246f  jz      short loc_180002498
0x180002471  mov     eax, [rax+8]
0x180002474  test    eax, eax
0x180002476  jz      short loc_180002498
0x180002478  mov     rcx, [r14]
0x18000247b  test    rcx, rcx
0x18000247e  jz      short loc_180002498
0x180002480  mov     eax, [rcx]
0x180002482  shr     eax, 1
0x180002484  cmp     eax, ebx
0x180002486  ja      short loc_180002493
0x180002488  test    ax, ax
0x18000248b  jz      short loc_180002493
0x18000248d  mov     rdx, [rcx+8]
0x180002491  jmp     short loc_18000249F
0x180002493  mov     rdx, r13
0x180002496  jmp     short loc_18000249F
0x180002498  lea     rdx, dword_18001E3EC
0x18000249f  mov     r9, [r15]
0x1800024a2  mov     eax, [r9]
0x1800024a5  shr     eax, 1
0x1800024a7  cmp     eax, ebx
0x1800024a9  ja      short loc_1800024B6
0x1800024ab  test    ax, ax
0x1800024ae  jz      short loc_1800024B6
0x1800024b0  mov     r9, [r9+8]
0x1800024b4  jmp     short loc_1800024B9
0x1800024b6  mov     r9, r13
0x1800024b9  mov     dword ptr [rsp+0C0h+var_90], edi
0x1800024bd  mov     qword ptr [rsp+0C0h+var_98], r8
0x1800024c2  lea     r8, aConfigurationm_2; "ConfigurationManager::IsPublishedForUse"...
0x1800024c9  mov     [rsp+0C0h+var_A0], rdx
0x1800024ce  xor     edx, edx
0x1800024d0  lea     ecx, [rdx+1]
0x1800024d3  call    LogWrite
0x1800024d8  mov     rbx, qword ptr [rbp+4Fh+var_80+8]
0x1800024dc  shr     edi, 1Fh
0x1800024df  xor     dil, 1
0x1800024e3  test    rbx, rbx
0x1800024e6  jz      short loc_18000251F
0x1800024e8  or      esi, 0FFFFFFFFh
0x1800024eb  mov     eax, esi
0x1800024ed  lock xadd [rbx+8], eax
0x1800024f2  add     eax, esi
0x1800024f4  jnz     short loc_18000251F
0x1800024f6  mov     rax, [rbx]
0x1800024f9  mov     rcx, rbx
0x1800024fc  mov     rax, [rax+8]
0x180002500  call    _guard_dispatch_icall
0x180002505  mov     eax, esi
0x180002507  lock xadd [rbx+0Ch], eax
0x18000250c  add     eax, esi
0x18000250e  jnz     short loc_18000251F
0x180002510  mov     rax, [rbx]
0x180002513  mov     rcx, rbx
0x180002516  mov     rax, [rax+10h]
0x18000251a  call    _guard_dispatch_icall
0x18000251f  mov     al, dil
0x180002522  jmp     loc_180002B25
0x180002527  mov     rbx, qword ptr [rbp+4Fh+var_80+8]
0x18000252b  test    rbx, rbx
0x18000252e  jz      short loc_180002567
0x180002530  or      esi, 0FFFFFFFFh
0x180002533  mov     eax, esi
0x180002535  lock xadd [rbx+8], eax
0x18000253a  add     eax, esi
0x18000253c  jnz     short loc_180002567
0x18000253e  mov     rax, [rbx]
0x180002541  mov     rcx, rbx
0x180002544  mov     rax, [rax+8]
  ... truncated ...
```
