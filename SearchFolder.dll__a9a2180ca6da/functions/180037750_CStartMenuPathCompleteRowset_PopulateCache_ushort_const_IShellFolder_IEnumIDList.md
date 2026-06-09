# CStartMenuPathCompleteRowset::_PopulateCache(ushort const *,IShellFolder *,IEnumIDList *)

- ea: `0x180037750`
- end: `0x1800378d5`
- name: `?_PopulateCache@CStartMenuPathCompleteRowset@@AEAAJPEBGPEAUIShellFolder@@PEAUIEnumIDList@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(CStartMenuPathCompleteRowset *__hidden this, const unsigned __int16 *, struct IShellFolder *, struct IEnumIDList *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800370e0`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x1800120a4`
- `0x180013d68`
- `0x18002e8e4`
- `0x18002f49c`
- `0x180031730`
- `0x1800327f4`
- `0x180037750`
- `0x18004a450`
- `0x18004a530`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037783`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037783`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800377ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800377ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037795`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037795`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStartMenuPathCompleteRowset::_PopulateCache(
        CStartMenuPathCompleteRowset *this,
        const unsigned __int16 *a2,
        struct IShellFolder *a3,
        struct IEnumIDList *a4)
{
  LPVOID *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  int inserted; // ebx
  const struct _GUID *v12; // r8
  void *v13; // rsi
  __int64 v14; // rdi
  struct IShellItem2 *v16; // [rsp+20h] [rbp-10h] BYREF
  void *p; // [rsp+28h] [rbp-8h] BYREF
  int v18; // [rsp+60h] [rbp+30h] BYREF

  v8 = (LPVOID *)*((_QWORD *)this + 21);
  WaitForSingleObject(v8[2], 0xFFFFFFFF);
  CStartMenuPathCompleteQueryCache::_CleanupCache(v8);
  CoTaskMemFree(v8[4]);
  inserted = _AllocString<CTCoAllocPolicy>(v10, v9, (__int64)a2);
  ReleaseMutex(v8[2]);
  if ( inserted >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
    do
    {
      if ( NextItem(a4, a3, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)&v16) )
        break;
      v18 = 0;
      if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, int *))v16->lpVtbl->GetAttributes)(v16, 1342177280, &v18) >= 0
        && (v18 & 0x50000000) != 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&p);
        if ( (int)CStartMenuPathCompleteRowset::_CreatePropertyStoreForPathItem(this, v16, v12, &p) >= 0 )
        {
          v13 = p;
          v14 = *((_QWORD *)this + 21);
          if ( *(_QWORD *)(v14 + 24)
            || (unsigned int)CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::Create(v14 + 24, 1) )
          {
            inserted = 0;
            if ( g_pfn_DPA_GetPtrIndex(*(HDPA *)(v14 + 24), v13) == -1 )
            {
              inserted = DPA_InsertPtr(*(HDPA *)(v14 + 24), 0x7FFFFFFF, v13);
              if ( inserted >= 0 )
                (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
            }
          }
          else
          {
            inserted = -2147467259;
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&p);
      }
      ATL::CComPtrBase<IPropertyStoreCache>::Release(&v16);
    }
    while ( inserted >= 0 );
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180037750  mov     [rsp-28h+arg_8], rbx
0x180037755  mov     [rsp-28h+arg_10], rsi
0x18003775a  push    rbp
0x18003775b  push    rdi
0x18003775c  push    r12
0x18003775e  push    r14
0x180037760  push    r15
0x180037762  mov     rbp, rsp
0x180037765  sub     rsp, 30h
0x180037769  mov     r15, r9
0x18003776c  mov     r12, r8
0x18003776f  mov     rsi, rdx
0x180037772  mov     r14, rcx
0x180037775  mov     rdi, [rcx+0A8h]
0x18003777c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003777f  mov     rcx, [rdi+10h]; hHandle
0x180037783  call    cs:__imp_WaitForSingleObject
0x180037789  mov     rcx, rdi; this
0x18003778c  call    ?_CleanupCache@CStartMenuPathCompleteQueryCache@@AEAAXXZ; CStartMenuPathCompleteQueryCache::_CleanupCache(void)
0x180037791  mov     rcx, [rdi+20h]; pv
0x180037795  call    cs:__imp_CoTaskMemFree
0x18003779b  lea     r9, [rdi+20h]
0x18003779f  mov     r8, rsi
0x1800377a2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800377a7  mov     ebx, eax
0x1800377a9  mov     rcx, [rdi+10h]; hMutex
0x1800377ad  call    cs:__imp_ReleaseMutex
0x1800377b3  test    ebx, ebx
0x1800377b5  js      loc_1800378BC
0x1800377bb  lea     rcx, [rbp+var_10]; void *
0x1800377bf  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800377c4  nop
0x1800377c5  lea     r9, [rbp+var_10]; void **
0x1800377c9  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; struct _GUID *
0x1800377d0  mov     rdx, r12; struct IShellFolder *
0x1800377d3  mov     rcx, r15; struct IEnumIDList *
0x1800377d6  call    ?NextItem@@YAJPEAUIEnumIDList@@PEAUIShellFolder@@AEBU_GUID@@PEAPEAX@Z; NextItem(IEnumIDList *,IShellFolder *,_GUID const &,void * *)
0x1800377db  test    eax, eax
0x1800377dd  jnz     loc_1800378B3
0x1800377e3  mov     [rbp+arg_0], eax
0x1800377e6  mov     rcx, [rbp+var_10]
0x1800377ea  mov     rax, [rcx]
0x1800377ed  lea     r8, [rbp+arg_0]
0x1800377f1  mov     edx, 50000000h
0x1800377f6  mov     rax, [rax+30h]
0x1800377fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377ff  test    eax, eax
0x180037801  js      loc_1800378A2
0x180037807  test    [rbp+arg_0], 50000000h
0x18003780e  jz      loc_1800378A2
0x180037814  lea     rcx, [rbp+p]; void *
0x180037818  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003781d  nop
0x18003781e  lea     r9, [rbp+p]; void **
0x180037822  mov     rdx, [rbp+var_10]; struct IShellItem2 *
0x180037826  mov     rcx, r14; this
0x180037829  call    ?_CreatePropertyStoreForPathItem@CStartMenuPathCompleteRowset@@AEAAJPEAUIShellItem2@@AEBU_GUID@@PEAPEAX@Z; CStartMenuPathCompleteRowset::_CreatePropertyStoreForPathItem(IShellItem2 *,_GUID const &,void * *)
0x18003782e  test    eax, eax
0x180037830  js      short loc_180037899
0x180037832  mov     rsi, [rbp+p]
0x180037836  mov     rdi, [r14+0A8h]
0x18003783d  cmp     qword ptr [rdi+18h], 0
0x180037842  jnz     short loc_18003785D
0x180037844  mov     edx, 1
0x180037849  lea     rcx, [rdi+18h]
0x18003784d  call    ?Create@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyRelease@UICondition@@@@@@QEAAHH@Z; CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::Create(int)
0x180037852  test    eax, eax
0x180037854  jnz     short loc_18003785D
0x180037856  mov     ebx, 80004005h
0x18003785b  jmp     short loc_180037899
0x18003785d  xor     ebx, ebx
0x18003785f  mov     rdx, rsi; p
0x180037862  mov     rcx, [rdi+18h]; hdpa
0x180037866  call    cs:g_pfn_DPA_GetPtrIndex
0x18003786c  cmp     eax, 0FFFFFFFFh
0x18003786f  jnz     short loc_180037899
0x180037871  mov     r8, rsi; p
0x180037874  mov     edx, 7FFFFFFFh; i
0x180037879  mov     rcx, [rdi+18h]; hdpa
0x18003787d  call    cs:__imp_DPA_InsertPtr
0x180037883  mov     ebx, eax
0x180037885  test    eax, eax
0x180037887  js      short loc_180037899
0x180037889  mov     rax, [rsi]
0x18003788c  mov     rcx, rsi
0x18003788f  mov     rax, [rax+8]
0x180037893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037898  nop
0x180037899  lea     rcx, [rbp+p]
0x18003789d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800378a2  lea     rcx, [rbp+var_10]
0x1800378a6  call    ?Release@?$CComPtrBase@UIPropertyStoreCache@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPropertyStoreCache>::Release(void)
0x1800378ab  test    ebx, ebx
0x1800378ad  jns     loc_1800377C5
0x1800378b3  lea     rcx, [rbp+var_10]
0x1800378b7  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800378bc  mov     eax, ebx
0x1800378be  mov     rbx, [rsp+30h+arg_8]
0x1800378c3  mov     rsi, [rsp+30h+arg_10]
0x1800378c8  add     rsp, 30h
0x1800378cc  pop     r15
0x1800378ce  pop     r14
0x1800378d0  pop     r12
0x1800378d2  pop     rdi
0x1800378d3  pop     rbp
0x1800378d4  retn
```
