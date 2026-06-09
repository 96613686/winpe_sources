# ContainerManager::RefreshContainers(DSM_REFRESH_TYPE,ushort const *)

- ea: `0x18001870c`
- end: `0x180018bb0`
- name: `?RefreshContainers@ContainerManager@@QEAAJW4DSM_REFRESH_TYPE@@PEBG@Z`
- size: `1188`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ba0c`
- `0x1800238e8`
- `0x18002e000`

## callees

- `0x18000af5c`
- `0x1800112a4`
- `0x180012a08`
- `0x180013864`
- `0x180013da8`
- `0x18001580c`
- `0x180016580`
- `0x180017a34`
- `0x18001870c`
- `0x180018bc4`
- `0x18001af70`
- `0x180022210`
- `0x18002541c`
- `0x180025798`
- `0x1800258f0`
- `0x18002ea48`
- `0x18002eb20`
- `0x18002ed44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018a51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018a51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018820`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800188aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018926`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800189b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018b7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018820`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800188aa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018926`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800189b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018b7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800189eb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800189eb`

## string_xrefs

- `0x1800187c2`: `onecoreuap\base\devices\setup\dsm\service\containermanager.cpp`
- `0x18001884c`: `onecoreuap\base\devices\setup\dsm\service\containermanager.cpp`
- `0x1800188cc`: `onecoreuap\base\devices\setup\dsm\service\containermanager.cpp`
- `0x180018956`: `onecoreuap\base\devices\setup\dsm\service\containermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ContainerManager::RefreshContainers(RTL_SRWLOCK *a1, unsigned int a2, const unsigned __int16 *a3)
{
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  int AllContainers; // eax
  int v9; // ebx
  int ConnectedContainers; // eax
  int ContainersNeedingRefresh; // eax
  __int64 j; // rdi
  HRESULT v14; // esi
  __int64 **Ptr; // rdi
  __int64 **i; // rbx
  int refreshed; // eax
  __int64 v18; // rdi
  __int64 v19; // rsi
  __int64 v20; // rax
  int v21; // eax
  int v22; // [rsp+20h] [rbp-158h]
  __int64 v23; // [rsp+30h] [rbp-148h] BYREF
  __int128 v24; // [rsp+38h] [rbp-140h]
  struct tagPROPVARIANT pvar; // [rsp+48h] [rbp-130h] BYREF
  _BYTE v26[16]; // [rsp+60h] [rbp-118h] BYREF
  _BYTE v27[176]; // [rsp+70h] [rbp-108h] BYREF
  GUID pclsid; // [rsp+120h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  memset(&pvar, 0, sizeof(pvar));
  CDsmDeviceScan::CDsmDeviceScan((CDsmDeviceScan *)v27);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>>>>>(&v23);
  if ( a2 )
  {
    v6 = a2 - 1;
    if ( a2 != 1 )
    {
      v7 = a2 - 2;
      if ( a2 == 2 )
        goto LABEL_9;
      v6 = a2 - 3;
      if ( a2 != 3 )
      {
        if ( a2 == 4 )
        {
          AcquireSRWLockShared(a1);
          *(_QWORD *)&pclsid.Data1 = a1;
          Ptr = (__int64 **)a1[2].Ptr;
          for ( i = (__int64 **)*Ptr; i != Ptr; i = (__int64 **)*i )
          {
            if ( Container::ContainerNeedsRetry((Container *)i[4]) )
            {
              if ( (_QWORD)v24 == *((_QWORD *)&v24 + 1) )
              {
                std::vector<std::shared_ptr<Container>>::_Emplace_reallocate<std::shared_ptr<Container> const &>(
                  &v23,
                  v24,
                  i + 4);
              }
              else
              {
                std::shared_ptr<Container>::shared_ptr<Container>(v24, i + 4);
                *(_QWORD *)&v24 = v24 + 16;
              }
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&pclsid);
          goto LABEL_25;
        }
        v7 = a2 - 5;
        if ( a2 != 5 )
        {
          v7 = a2 - 6;
          if ( a2 != 6 )
          {
            v7 = a2 - 7;
            if ( (unsigned int)v7 > 1 )
            {
LABEL_25:
              v9 = 0;
              for ( j = 0; (unsigned int)j < pvar.lVal; j = (unsigned int)(j + 1) )
              {
                pclsid = 0;
                v14 = CLSIDFromString(*(LPCOLESTR *)&pvar.bstrblobVal.pData[8 * j], &pclsid);
                if ( v14 >= 0 )
                {
                  refreshed = ContainerManager::RefreshContainer(a1, &pclsid, a2, a3);
                  if ( refreshed < 0 && v9 >= 0 )
                    v9 = refreshed;
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      11,
                      (unsigned int)&WPP_12025944dd5e3a7e3168b2cc2e6c0bb5_Traceguids,
                      *(_QWORD *)&pvar.bstrblobVal.pData[8 * j],
                      v14);
                  }
                  if ( v9 >= 0 )
                    v9 = v14;
                }
              }
              v18 = v23;
              v19 = v24;
              if ( v23 != (_QWORD)v24 )
              {
                do
                {
                  v20 = std::shared_ptr<Container>::shared_ptr<Container>(v26, v18);
                  v21 = ContainerManager::_RefreshContainer(a1, v20, 4);
                  if ( v21 < 0 && v9 >= 0 )
                    v9 = v21;
                  v18 += 16;
                }
                while ( v18 != v19 );
                v19 = v24;
                v18 = v23;
              }
              if ( v18 )
              {
                std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(v18, v19);
                std::_Deallocate<16>(v23, (*((_QWORD *)&v24 + 1) - v23) & 0xFFFFFFFFFFFFFFF0uLL);
                v23 = 0;
                v24 = 0;
              }
              goto LABEL_53;
            }
          }
        }
LABEL_9:
        AllContainers = CDsmDeviceScan::GetAllContainers((CDsmDeviceScan *)v7, &pvar);
        v9 = AllContainers;
        if ( AllContainers < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B,
            (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
            (const char *)(unsigned int)AllContainers,
            v22);
          if ( v23 )
          {
            std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(v23, v24);
            std::_Deallocate<16>(v23, (*((_QWORD *)&v24 + 1) - v23) & 0xFFFFFFFFFFFFFFF0uLL);
            v23 = 0;
            v24 = 0;
          }
LABEL_53:
          CDsmDeviceScan::~CDsmDeviceScan((CDsmDeviceScan *)v27);
          PropVariantClear((PROPVARIANT *)&pvar);
          return (unsigned int)v9;
        }
        goto LABEL_25;
      }
    }
    ConnectedContainers = CDsmDeviceScan::GetConnectedContainers((CDsmDeviceScan *)v6, &pvar);
    v9 = ConnectedContainers;
    if ( ConnectedContainers < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
        (const char *)(unsigned int)ConnectedContainers,
        v22);
      if ( v23 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(v23, v24);
        std::_Deallocate<16>(v23, (*((_QWORD *)&v24 + 1) - v23) & 0xFFFFFFFFFFFFFFF0uLL);
        v23 = 0;
        v24 = 0;
      }
      goto LABEL_53;
    }
    goto LABEL_25;
  }
  if ( a3 )
  {
    ContainersNeedingRefresh = CDsmDeviceScan::GetContainersNeedingRefresh((CDsmDeviceScan *)v27, a3, &pvar);
    v9 = ContainersNeedingRefresh;
    if ( ContainersNeedingRefresh < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
        (const char *)(unsigned int)ContainersNeedingRefresh,
        v22);
      if ( v23 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(v23, v24);
        std::_Deallocate<16>(v23, (*((_QWORD *)&v24 + 1) - v23) & 0xFFFFFFFFFFFFFFF0uLL);
        v23 = 0;
        v24 = 0;
      }
      goto LABEL_53;
    }
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x81,
    (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
    (const char *)0x80070057LL,
    v22);
  if ( v23 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(v23, v24);
    std::_Deallocate<16>(v23, (*((_QWORD *)&v24 + 1) - v23) & 0xFFFFFFFFFFFFFFF0uLL);
    v23 = 0;
    v24 = 0;
  }
  CDsmDeviceScan::~CDsmDeviceScan((CDsmDeviceScan *)v27);
  PropVariantClear((PROPVARIANT *)&pvar);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001870c  push    rbx
0x18001870e  push    rsi
0x18001870f  push    rdi
0x180018710  push    r12
0x180018712  push    r13
0x180018714  push    r14
0x180018716  push    r15
0x180018718  sub     rsp, 140h
0x18001871f  mov     rax, cs:__security_cookie
0x180018726  xor     rax, rsp
0x180018729  mov     [rsp+178h+var_48], rax
0x180018731  mov     r15, r8
0x180018734  mov     r13d, edx
0x180018737  mov     r14, rcx
0x18001873a  xorps   xmm0, xmm0
0x18001873d  xor     eax, eax
0x18001873f  movups  xmmword ptr [rsp+178h+pvar], xmm0
0x180018744  mov     [rsp+178h+var_120], rax
0x180018749  lea     rcx, [rsp+178h+var_108]; this
0x18001874e  call    ??0CDsmDeviceScan@@QEAA@XZ; CDsmDeviceScan::CDsmDeviceScan(void)
0x180018753  nop
0x180018754  lea     rcx, [rsp+178h+var_148]
0x180018759  call    ??$?0AEBV?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>>>>>(std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>> const &)
0x18001875e  nop
0x18001875f  mov     ecx, r13d
0x180018762  test    r13d, r13d
0x180018765  jz      loc_1800188B7
0x18001876b  sub     ecx, 1; this
0x18001876e  jz      loc_18001882D
0x180018774  sub     ecx, 1
0x180018777  jz      short loc_1800187A3
0x180018779  sub     ecx, 1
0x18001877c  jz      loc_18001882D
0x180018782  sub     ecx, 1
0x180018785  jz      loc_180018A4E
0x18001878b  sub     ecx, 1
0x18001878e  jz      short loc_1800187A3
0x180018790  sub     ecx, 1
0x180018793  jz      short loc_1800187A3
0x180018795  sub     ecx, 1; this
0x180018798  jz      short loc_1800187A3
0x18001879a  cmp     ecx, 1
0x18001879d  jnz     loc_1800189C1
0x1800187a3  lea     rdx, [rsp+178h+pvar]; struct tagPROPVARIANT *
0x1800187a8  call    ?GetAllContainers@CDsmDeviceScan@@QEAAJPEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::GetAllContainers(tagPROPVARIANT *)
0x1800187ad  mov     ebx, eax
0x1800187af  test    eax, eax
0x1800187b1  jns     loc_1800189C1
0x1800187b7  mov     rcx, [rsp+178h]; this
0x1800187bf  mov     r9d, eax; char *
0x1800187c2  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800187c9  mov     edx, 7Bh ; '{'; void *
0x1800187ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187d3  nop
0x1800187d4  mov     rcx, [rsp+178h+var_148]
0x1800187d9  test    rcx, rcx
0x1800187dc  jz      short loc_180018810
0x1800187de  mov     rdx, qword ptr [rsp+178h+var_140]
0x1800187e3  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VJob@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VJob@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VJob@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(std::shared_ptr<Job> *,std::shared_ptr<Job> * const,std::allocator<std::shared_ptr<Job>> &)
0x1800187e8  mov     rcx, [rsp+178h+var_148]
0x1800187ed  mov     rdx, qword ptr [rsp+178h+var_140+8]
0x1800187f2  sub     rdx, rcx
0x1800187f5  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800187f9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800187fe  mov     [rsp+178h+var_148], 0
0x180018807  xorps   xmm0, xmm0
0x18001880a  movdqu  [rsp+178h+var_140], xmm0
0x180018810  lea     rcx, [rsp+178h+var_108]; this
0x180018815  call    ??1CDsmDeviceScan@@UEAA@XZ; CDsmDeviceScan::~CDsmDeviceScan(void)
0x18001881a  nop
0x18001881b  lea     rcx, [rsp+178h+pvar]; pvar
0x180018820  call    cs:__imp_PropVariantClear
0x180018826  mov     eax, ebx
0x180018828  jmp     loc_180018B8C
0x18001882d  lea     rdx, [rsp+178h+pvar]; struct tagPROPVARIANT *
0x180018832  call    ?GetConnectedContainers@CDsmDeviceScan@@QEAAJPEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::GetConnectedContainers(tagPROPVARIANT *)
0x180018837  mov     ebx, eax
0x180018839  test    eax, eax
0x18001883b  jns     loc_1800189C1
0x180018841  mov     rcx, [rsp+178h]; this
0x180018849  mov     r9d, eax; char *
0x18001884c  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180018853  mov     edx, 89h; void *
0x180018858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001885d  nop
0x18001885e  mov     rcx, [rsp+178h+var_148]
0x180018863  test    rcx, rcx
0x180018866  jz      short loc_18001889A
0x180018868  mov     rdx, qword ptr [rsp+178h+var_140]
0x18001886d  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VJob@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VJob@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VJob@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(std::shared_ptr<Job> *,std::shared_ptr<Job> * const,std::allocator<std::shared_ptr<Job>> &)
0x180018872  mov     rcx, [rsp+178h+var_148]
0x180018877  mov     rdx, qword ptr [rsp+178h+var_140+8]
0x18001887c  sub     rdx, rcx
0x18001887f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180018883  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018888  mov     [rsp+178h+var_148], 0
0x180018891  xorps   xmm0, xmm0
0x180018894  movdqu  [rsp+178h+var_140], xmm0
0x18001889a  lea     rcx, [rsp+178h+var_108]; this
0x18001889f  call    ??1CDsmDeviceScan@@UEAA@XZ; CDsmDeviceScan::~CDsmDeviceScan(void)
0x1800188a4  nop
0x1800188a5  lea     rcx, [rsp+178h+pvar]; pvar
0x1800188aa  call    cs:__imp_PropVariantClear
0x1800188b0  mov     eax, ebx
0x1800188b2  jmp     loc_180018B8C
0x1800188b7  test    r15, r15
0x1800188ba  jnz     short loc_180018933
0x1800188bc  mov     rcx, [rsp+178h]; this
0x1800188c4  mov     ebx, 80070057h
0x1800188c9  mov     r9d, ebx; char *
0x1800188cc  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800188d3  mov     edx, 81h; void *
0x1800188d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188dd  nop
0x1800188de  mov     rcx, [rsp+178h+var_148]
0x1800188e3  test    rcx, rcx
0x1800188e6  jz      short loc_180018916
0x1800188e8  mov     rdx, qword ptr [rsp+178h+var_140]
0x1800188ed  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VJob@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VJob@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VJob@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(std::shared_ptr<Job> *,std::shared_ptr<Job> * const,std::allocator<std::shared_ptr<Job>> &)
0x1800188f2  mov     rcx, [rsp+178h+var_148]
0x1800188f7  mov     rdx, qword ptr [rsp+178h+var_140+8]
0x1800188fc  sub     rdx, rcx
0x1800188ff  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180018903  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018908  mov     [rsp+178h+var_148], r15
0x18001890d  xorps   xmm0, xmm0
0x180018910  movdqu  [rsp+178h+var_140], xmm0
0x180018916  lea     rcx, [rsp+178h+var_108]; this
0x18001891b  call    ??1CDsmDeviceScan@@UEAA@XZ; CDsmDeviceScan::~CDsmDeviceScan(void)
0x180018920  nop
0x180018921  lea     rcx, [rsp+178h+pvar]; pvar
0x180018926  call    cs:__imp_PropVariantClear
0x18001892c  mov     eax, ebx
0x18001892e  jmp     loc_180018B8C
0x180018933  lea     r8, [rsp+178h+pvar]; struct tagPROPVARIANT *
0x180018938  mov     rdx, r15; unsigned __int16 *
0x18001893b  lea     rcx, [rsp+178h+var_108]; this
0x180018940  call    ?GetContainersNeedingRefresh@CDsmDeviceScan@@QEAAJPEBGPEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::GetContainersNeedingRefresh(ushort const *,tagPROPVARIANT *)
0x180018945  mov     ebx, eax
0x180018947  test    eax, eax
0x180018949  jns     short loc_1800189C1
0x18001894b  mov     rcx, [rsp+178h]; this
0x180018953  mov     r9d, eax; char *
0x180018956  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001895d  mov     edx, 84h; void *
0x180018962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018967  nop
0x180018968  mov     rcx, [rsp+178h+var_148]
0x18001896d  test    rcx, rcx
0x180018970  jz      short loc_1800189A4
0x180018972  mov     rdx, qword ptr [rsp+178h+var_140]
0x180018977  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VJob@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VJob@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VJob@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(std::shared_ptr<Job> *,std::shared_ptr<Job> * const,std::allocator<std::shared_ptr<Job>> &)
0x18001897c  mov     rcx, [rsp+178h+var_148]
0x180018981  mov     rdx, qword ptr [rsp+178h+var_140+8]
0x180018986  sub     rdx, rcx
0x180018989  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001898d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018992  mov     [rsp+178h+var_148], 0
0x18001899b  xorps   xmm0, xmm0
0x18001899e  movdqu  [rsp+178h+var_140], xmm0
0x1800189a4  lea     rcx, [rsp+178h+var_108]; this
0x1800189a9  call    ??1CDsmDeviceScan@@UEAA@XZ; CDsmDeviceScan::~CDsmDeviceScan(void)
0x1800189ae  nop
0x1800189af  lea     rcx, [rsp+178h+pvar]; pvar
0x1800189b4  call    cs:__imp_PropVariantClear
0x1800189ba  mov     eax, ebx
0x1800189bc  jmp     loc_180018B8C
0x1800189c1  xor     ebx, ebx
0x1800189c3  xor     edi, edi
0x1800189c5  cmp     dword ptr [rsp+178h+pvar+8], ebx
0x1800189c9  jbe     loc_180018AE9
0x1800189cf  xorps   xmm0, xmm0
0x1800189d2  movups  xmmword ptr [rsp+178h+pclsid.Data1], xmm0
0x1800189da  lea     rdx, [rsp+178h+pclsid]; pclsid
0x1800189e2  mov     rcx, [rsp+178h+var_120]
0x1800189e7  mov     rcx, [rcx+rdi*8]; lpsz
0x1800189eb  call    cs:__imp_CLSIDFromString
0x1800189f1  mov     esi, eax
0x1800189f3  test    eax, eax
0x1800189f5  jns     loc_180018ABE
0x1800189fb  lea     rax, WPP_GLOBAL_Control
0x180018a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a09  cmp     rcx, rax
0x180018a0c  jz      short loc_180018A3F
0x180018a0e  test    dword ptr [rcx+1Ch], 100h
0x180018a15  jz      short loc_180018A3F
0x180018a17  cmp     byte ptr [rcx+19h], 2
0x180018a1b  jb      short loc_180018A3F
0x180018a1d  mov     edx, 0Bh
0x180018a22  mov     [rsp+178h+var_158], esi
0x180018a26  mov     r9, [rsp+178h+var_120]
0x180018a2b  mov     r9, [r9+rdi*8]
0x180018a2f  lea     r8, WPP_12025944dd5e3a7e3168b2cc2e6c0bb5_Traceguids
0x180018a36  mov     rcx, [rcx+10h]
0x180018a3a  call    WPP_SF_Sd
0x180018a3f  test    ebx, ebx
0x180018a41  js      loc_180018ADD
0x180018a47  mov     ebx, esi
0x180018a49  jmp     loc_180018ADD
0x180018a4e  mov     rcx, r14; SRWLock
0x180018a51  call    cs:__imp_AcquireSRWLockShared
0x180018a57  mov     qword ptr [rsp+178h+pclsid.Data1], r14
0x180018a5f  mov     rdi, [r14+10h]
0x180018a63  mov     rbx, [rdi]
0x180018a66  cmp     rbx, rdi
0x180018a69  jnz     short loc_180018A7D
0x180018a6b  lea     rcx, [rsp+178h+pclsid]
0x180018a73  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018a78  jmp     loc_1800189C1
0x180018a7d  lea     rsi, [rbx+20h]
0x180018a81  mov     rcx, [rsi]; this
0x180018a84  call    ?ContainerNeedsRetry@Container@@QEAA_NXZ; Container::ContainerNeedsRetry(void)
0x180018a89  test    al, al
0x180018a8b  jz      short loc_180018AB9
0x180018a8d  mov     rcx, qword ptr [rsp+178h+var_140]
0x180018a92  cmp     rcx, qword ptr [rsp+178h+var_140+8]
0x180018a97  jz      short loc_180018AA9
0x180018a99  mov     rdx, rsi
0x180018a9c  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180018aa1  add     qword ptr [rsp+178h+var_140], 10h
0x180018aa7  jmp     short loc_180018AB9
0x180018aa9  mov     r8, rsi
0x180018aac  mov     rdx, rcx
0x180018aaf  lea     rcx, [rsp+178h+var_148]
0x180018ab4  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VContainer@@@std@@@?$vector@V?$shared_ptr@VContainer@@@std@@V?$allocator@V?$shared_ptr@VContainer@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VContainer@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Container>>::_Emplace_reallocate<std::shared_ptr<Container> const &>(std::shared_ptr<Container> * const,std::shared_ptr<Container> const &)
0x180018ab9  mov     rbx, [rbx]
0x180018abc  jmp     short loc_180018A66
0x180018abe  mov     r9, r15
0x180018ac1  mov     r8d, r13d
0x180018ac4  lea     rdx, [rsp+178h+pclsid]
0x180018acc  mov     rcx, r14
0x180018acf  call    ?RefreshContainer@ContainerManager@@QEAAJAEBU_GUID@@W4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::RefreshContainer(_GUID const &,DSM_REFRESH_TYPE,ushort const *)
0x180018ad4  test    eax, eax
0x180018ad6  jns     short loc_180018ADD
0x180018ad8  test    ebx, ebx
0x180018ada  cmovns  ebx, eax
0x180018add  inc     edi
0x180018adf  cmp     edi, dword ptr [rsp+178h+pvar+8]
0x180018ae3  jb      loc_1800189CF
0x180018ae9  mov     rdi, [rsp+178h+var_148]
0x180018aee  mov     rsi, qword ptr [rsp+178h+var_140]
0x180018af3  cmp     rdi, rsi
0x180018af6  jz      short loc_180018B33
0x180018af8  mov     rdx, rdi
0x180018afb  lea     rcx, [rsp+178h+var_118]
0x180018b00  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180018b05  xor     r9d, r9d
0x180018b08  lea     r8d, [r9+4]
0x180018b0c  mov     rdx, rax
0x180018b0f  mov     rcx, r14
0x180018b12  call    ?_RefreshContainer@ContainerManager@@AEAAJV?$shared_ptr@VContainer@@@std@@W4DSM_REFRESH_TYPE@@PEBG@Z; ContainerManager::_RefreshContainer(std::shared_ptr<Container>,DSM_REFRESH_TYPE,ushort const *)
0x180018b17  test    eax, eax
0x180018b19  jns     short loc_180018B20
0x180018b1b  test    ebx, ebx
0x180018b1d  cmovns  ebx, eax
0x180018b20  add     rdi, 10h
0x180018b24  cmp     rdi, rsi
0x180018b27  jnz     short loc_180018AF8
0x180018b29  mov     rsi, qword ptr [rsp+178h+var_140]
0x180018b2e  mov     rdi, [rsp+178h+var_148]
0x180018b33  test    rdi, rdi
0x180018b36  jz      short loc_180018B6B
0x180018b38  mov     rdx, rsi
0x180018b3b  mov     rcx, rdi
0x180018b3e  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VJob@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VJob@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VJob@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Job>>>(std::shared_ptr<Job> *,std::shared_ptr<Job> * const,std::allocator<std::shared_ptr<Job>> &)
0x180018b43  mov     rcx, [rsp+178h+var_148]
0x180018b48  mov     rdx, qword ptr [rsp+178h+var_140+8]
0x180018b4d  sub     rdx, rcx
0x180018b50  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180018b54  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018b59  mov     [rsp+178h+var_148], 0
0x180018b62  xorps   xmm0, xmm0
0x180018b65  movdqu  [rsp+178h+var_140], xmm0
0x180018b6b  lea     rcx, [rsp+178h+var_108]; this
0x180018b70  call    ??1CDsmDeviceScan@@UEAA@XZ; CDsmDeviceScan::~CDsmDeviceScan(void)
0x180018b75  nop
0x180018b76  lea     rcx, [rsp+178h+pvar]; pvar
0x180018b7b  call    cs:__imp_PropVariantClear
0x180018b81  mov     eax, ebx
0x180018b83  jmp     short loc_180018B8C
0x180018b85  mov     eax, [rsp+178h+pclsid.Data1]
0x180018b8c  mov     rcx, [rsp+178h+var_48]
0x180018b94  xor     rcx, rsp; StackCookie
0x180018b97  call    __security_check_cookie
0x180018b9c  add     rsp, 140h
0x180018ba3  pop     r15
0x180018ba5  pop     r14
0x180018ba7  pop     r13
0x180018ba9  pop     r12
0x180018bab  pop     rdi
0x180018bac  pop     rsi
0x180018bad  pop     rbx
0x180018bae  retn
```
