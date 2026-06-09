# CStartMenuControlPanelResultSetManager::_EnsureChildResultSetManager(void)

- ea: `0x1800335dc`
- end: `0x18003375d`
- name: `?_EnsureChildResultSetManager@CStartMenuControlPanelResultSetManager@@AEAAJXZ`
- size: `385`
- prototype: `__int64 __fastcall(CStartMenuControlPanelResultSetManager *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b070`
- `0x18002bd80`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x18002850c`
- `0x1800319f8`
- `0x1800335dc`
- `0x180038bc0`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x1800336cc`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800336cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800335f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800335f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003374a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003374a`

## pseudocode

```c
__int64 __fastcall CStartMenuControlPanelResultSetManager::_EnsureChildResultSetManager(
        CStartMenuControlPanelResultSetManager *this)
{
  int v2; // ebx
  void (__fastcall ***v3)(_QWORD, GUID *, struct IServiceProvider **); // rcx
  const struct _GUID *v5; // [rsp+30h] [rbp-20h]
  struct IServiceProvider *v6[2]; // [rsp+40h] [rbp-10h] BYREF
  void *ppv; // [rsp+80h] [rbp+30h] BYREF
  struct IResultShape *v8; // [rsp+88h] [rbp+38h] BYREF
  void *v9; // [rsp+90h] [rbp+40h] BYREF
  struct IShellItem *v10; // [rsp+98h] [rbp+48h] BYREF

  v2 = 1;
  AcquireSRWLockExclusive((PSRWLOCK)this + 11);
  if ( ATL::CComPtrBase<IResultSetManager>::operator!((_QWORD *)this + 18) )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v8);
    v2 = s_CreateChildShape(*((_QWORD *)this + 7), &v8);
    if ( v2 >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v6);
      v3 = (void (__fastcall ***)(_QWORD, GUID *, struct IServiceProvider **))*((_QWORD *)this + 3);
      if ( v3 )
        (**v3)(v3, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v6);
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v10);
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v9);
      v2 = CStartMenuControlPanelResultSetManager::_CreateControlPanelTasksResults(
             (const unsigned __int16 **)this,
             v6[0],
             (struct IUnknown *)v8,
             *((IUnknown **)this + 8),
             *((struct INamedPropertyStore **)this + 9),
             &v10,
             v5,
             &v9);
      if ( v2 >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
        v2 = SHCoCreateInstance(0, &CLSID_ResultSetManager, 0, &GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8, &ppv);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(void *, void *, struct IResultShape *, struct IShellItem *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 v9,
                 v8,
                 v10);
          if ( v2 >= 0 )
            v2 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))ppv)(
                   ppv,
                   &GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330,
                   (char *)this + 144);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v9);
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v10);
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)v6);
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v8);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 11);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800335dc  push    rbp
0x1800335de  push    rbx
0x1800335df  push    rsi
0x1800335e0  push    rdi
0x1800335e1  push    r14
0x1800335e3  mov     rbp, rsp
0x1800335e6  sub     rsp, 50h
0x1800335ea  mov     rdi, rcx
0x1800335ed  mov     ebx, 1
0x1800335f2  add     rcx, 58h ; 'X'; SRWLock
0x1800335f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800335fc  lea     r14, [rdi+90h]
0x180033603  mov     rcx, r14
0x180033606  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x18003360b  test    al, al
0x18003360d  jz      loc_180033746
0x180033613  lea     rcx, [rbp+arg_8]; void *
0x180033617  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003361c  nop
0x18003361d  lea     rdx, [rbp+arg_8]
0x180033621  mov     rcx, [rdi+38h]
0x180033625  call    s_CreateChildShape
0x18003362a  mov     ebx, eax
0x18003362c  test    eax, eax
0x18003362e  js      loc_18003373D
0x180033634  lea     rcx, [rbp+var_10]; void *
0x180033638  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003363d  nop
0x18003363e  mov     rcx, [rdi+18h]
0x180033642  test    rcx, rcx
0x180033645  jz      short loc_18003365D
0x180033647  mov     rax, [rcx]
0x18003364a  lea     r8, [rbp+var_10]
0x18003364e  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180033655  mov     rax, [rax]
0x180033658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003365d  lea     rcx, [rbp+arg_18]; void *
0x180033661  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033666  nop
0x180033667  lea     rcx, [rbp+arg_10]; void *
0x18003366b  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180033670  nop
0x180033671  lea     rax, [rbp+arg_10]
0x180033675  mov     [rsp+50h+var_18], rax; void **
0x18003367a  lea     rax, [rbp+arg_18]
0x18003367e  mov     [rsp+50h+var_28], rax; struct IShellItem **
0x180033683  mov     rax, [rdi+48h]
0x180033687  mov     [rsp+50h+ppv], rax; struct INamedPropertyStore *
0x18003368c  mov     r9, [rdi+40h]; struct ICondition *
0x180033690  mov     r8, [rbp+arg_8]; struct IResultShape *
0x180033694  mov     rdx, [rbp+var_10]; struct IServiceProvider *
0x180033698  mov     rcx, rdi; this
0x18003369b  call    ?_CreateControlPanelTasksResults@CStartMenuControlPanelResultSetManager@@AEAAJPEAUIServiceProvider@@PEAUIResultShape@@PEAUICondition@@PEAUINamedPropertyStore@@PEAPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; CStartMenuControlPanelResultSetManager::_CreateControlPanelTasksResults(IServiceProvider *,IResultShape *,ICondition *,INamedPropertyStore *,IShellItem * *,_GUID const &,void * *)
0x1800336a0  mov     ebx, eax
0x1800336a2  test    eax, eax
0x1800336a4  js      short loc_18003371F
0x1800336a6  lea     rcx, [rbp+arg_0]; void *
0x1800336aa  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800336af  nop
0x1800336b0  lea     rax, [rbp+arg_0]
0x1800336b4  mov     [rsp+50h+ppv], rax; ppv
0x1800336b9  lea     r9, _GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8; riid
0x1800336c0  xor     r8d, r8d; pUnkOuter
0x1800336c3  lea     rdx, CLSID_ResultSetManager; pclsid
0x1800336ca  xor     ecx, ecx; pszCLSID
0x1800336cc  call    cs:__imp_SHCoCreateInstance
0x1800336d2  mov     ebx, eax
0x1800336d4  test    eax, eax
0x1800336d6  js      short loc_180033715
0x1800336d8  mov     rcx, [rbp+arg_0]
0x1800336dc  mov     rax, [rcx]
0x1800336df  mov     r9, [rbp+arg_18]
0x1800336e3  mov     r8, [rbp+arg_8]
0x1800336e7  mov     rdx, [rbp+arg_10]
0x1800336eb  mov     rax, [rax+18h]
0x1800336ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336f4  mov     ebx, eax
0x1800336f6  test    eax, eax
0x1800336f8  js      short loc_180033715
0x1800336fa  mov     rcx, [rbp+arg_0]
0x1800336fe  mov     rax, [rcx]
0x180033701  mov     r8, r14
0x180033704  lea     rdx, _GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330
0x18003370b  mov     rax, [rax]
0x18003370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033713  mov     ebx, eax
0x180033715  lea     rcx, [rbp+arg_0]
0x180033719  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003371e  nop
0x18003371f  lea     rcx, [rbp+arg_10]
0x180033723  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033728  nop
0x180033729  lea     rcx, [rbp+arg_18]
0x18003372d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033732  nop
0x180033733  lea     rcx, [rbp+var_10]
0x180033737  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003373c  nop
0x18003373d  lea     rcx, [rbp+arg_8]
0x180033741  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180033746  lea     rcx, [rdi+58h]; SRWLock
0x18003374a  call    cs:__imp_ReleaseSRWLockExclusive
0x180033750  mov     eax, ebx
0x180033752  add     rsp, 50h
0x180033756  pop     r14
0x180033758  pop     rdi
0x180033759  pop     rsi
0x18003375a  pop     rbx
0x18003375b  pop     rbp
0x18003375c  retn
```
