# SHDisplayNameFromScopeAndSubQueries(IScope *,IShellItemArray *,ulong,ulong,_SIGDN,ushort * *)

- ea: `0x18001d0f8`
- end: `0x18001d462`
- name: `?SHDisplayNameFromScopeAndSubQueries@@YAJPEAUIScope@@PEAUIShellItemArray@@KKW4_SIGDN@@PEAPEAG@Z`
- size: `874`
- prototype: `__int64 __fastcall(struct IScope *, struct IShellItemArray *, unsigned int, unsigned int, enum _SIGDN, LPWSTR *ppwsz)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019218`
- `0x18002cd68`

## callees

- `0x180003790`
- `0x180010fcc`
- `0x180012060`
- `0x180013374`
- `0x180013d68`
- `0x1800141ec`
- `0x18001d0f8`
- `0x18001d5f0`
- `0x18001e694`
- `0x18001fba8`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001d416`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001d416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d20f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d20f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d362`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d425`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d425`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SHDisplayNameFromScopeAndSubQueries(
        struct IScope *a1,
        struct IShellItemArray *a2,
        unsigned int a3,
        unsigned int a4,
        enum _SIGDN a5,
        LPWSTR *ppwsz)
{
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // r12
  int appended; // edi
  unsigned __int16 *v13; // r13
  struct IUnknown *v14; // rdx
  __int64 v15; // r8
  unsigned int i; // ebx
  enum _SIGDN v17; // edx
  HDPA v18; // rbx
  enum _SIGDN v19; // r14d
  int v20; // ecx
  const WCHAR *Ptr; // rax
  const unsigned __int16 *v22; // rdx
  HRESULT v23; // eax
  unsigned int v25; // [rsp+30h] [rbp-51h]
  LPVOID pv; // [rsp+48h] [rbp-39h] BYREF
  struct IScopeItem *v27; // [rsp+50h] [rbp-31h] BYREF
  HDPA hdpa; // [rsp+58h] [rbp-29h] BYREF
  LPCWSTR psz; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 *v30; // [rsp+68h] [rbp-19h] BYREF
  unsigned __int16 *v31; // [rsp+70h] [rbp-11h] BYREF
  unsigned __int64 v32; // [rsp+78h] [rbp-9h] BYREF
  struct _tagpropertykey v33; // [rsp+88h] [rbp+7h] BYREF
  unsigned int v34; // [rsp+E8h] [rbp+67h] BYREF
  unsigned int v35; // [rsp+F0h] [rbp+6Fh] BYREF

  v35 = a4;
  v34 = a3;
  v8 = 0;
  hdpa = 0;
  if ( !(unsigned int)CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::Create(&hdpa, 5) )
  {
    appended = -2147024882;
    goto LABEL_46;
  }
  psz = 0;
  v11 = 260;
  appended = _AllocArray<unsigned short,CTLocalAllocPolicy>(v10, v9, 260, &psz);
  if ( appended >= 0 )
  {
    a5 = SIGDN_NORMALDISPLAY;
    v13 = (unsigned __int16 *)psz;
    v31 = (unsigned __int16 *)psz;
    v32 = 260;
    if ( a2 )
    {
      v35 = 0;
      appended = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v35);
      if ( v35 )
      {
        while ( appended >= 0 )
        {
          v27 = 0;
          appended = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IScopeItem **))a2->lpVtbl->GetItemAt)(
                       a2,
                       v8,
                       &v27);
          if ( appended >= 0 )
          {
            pv = 0;
            appended = (*(__int64 (__fastcall **)(struct IScopeItem *, __int64, LPVOID *))(*(_QWORD *)v27 + 40LL))(
                         v27,
                         2147844096LL,
                         &pv);
            if ( appended >= 0 )
            {
              v34 = 4;
              if ( (int)SHMapUrlToZone((const unsigned __int16 *)pv, v14, v15, &v34) < 0
                || v34
                || (CoTaskMemFree(pv),
                    appended = (*(__int64 (__fastcall **)(struct IScopeItem *, _QWORD, LPVOID *))(*(_QWORD *)v27 + 40LL))(
                                 v27,
                                 0,
                                 &pv),
                    appended >= 0) )
              {
                appended = CDPA_Base<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::AppendPtr(&hdpa, pv);
                if ( appended < 0 )
                  CoTaskMemFree(pv);
              }
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v27 + 16LL))(v27);
          }
          if ( ++v8 >= v35 )
            goto LABEL_15;
        }
        v8 = 0;
LABEL_30:
        v18 = hdpa;
        v19 = a5;
        while ( 1 )
        {
          v20 = v18 ? *(_DWORD *)v18 : 0;
          if ( (int)v8 >= v20 )
            break;
          Ptr = (const WCHAR *)g_pfn_DPA_GetPtr(v18, (int)v8);
          appended = _AppendNext(Ptr, v22, v13, v11, v19, v25, &v31, &v32);
          if ( appended >= 0 )
            v19 = 1;
          ++v8;
          v13 = v31;
          v11 = v32;
        }
        if ( appended == -2147024774 )
        {
          appended = 1;
        }
        else if ( appended < 0 )
        {
LABEL_43:
          LocalFree((HLOCAL)psz);
          goto LABEL_44;
        }
        v23 = SHStrDupW(psz, ppwsz);
        if ( v23 < 0 )
          appended = v23;
        goto LABEL_43;
      }
LABEL_15:
      v8 = 0;
      if ( appended < 0 )
        goto LABEL_30;
    }
    if ( a1 )
    {
      pv = 0;
      appended = (*(__int64 (__fastcall **)(struct IScope *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)a1 + 64LL))(
                   a1,
                   0,
                   &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                   &pv);
      if ( appended >= 0 )
      {
        v35 = 0;
        appended = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)pv + 24LL))(pv, &v35);
        for ( i = 0; appended >= 0; ++i )
        {
          if ( i >= v35 )
            break;
          v27 = 0;
          appended = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IScopeItem **))(*(_QWORD *)pv + 32LL))(
                       pv,
                       i,
                       &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                       &v27);
          if ( appended >= 0 )
          {
            v34 = 0;
            appended = (*(__int64 (__fastcall **)(struct IScopeItem *, unsigned int *))(*(_QWORD *)v27 + 32LL))(
                         v27,
                         &v34);
            if ( appended >= 0 && v34 == 1 )
            {
              v30 = 0;
              memset(&v33, 0, sizeof(v33));
              appended = _GetScopeItemName(v27, v17, &v33, (LPVOID *)&v30);
              if ( appended >= 0 )
              {
                appended = CDPA_Base<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::AppendPtr(&hdpa, v30);
                if ( appended < 0 )
                  CoTaskMemFree(v30);
              }
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v27 + 16LL))(v27);
          }
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
    }
    goto LABEL_30;
  }
LABEL_44:
  CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::DestroyCallback(&hdpa);
LABEL_46:
  CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>(&hdpa);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18001d0f8  mov     rax, rsp
0x18001d0fb  mov     [rax+8], rbx
0x18001d0ff  mov     [rax+10h], rsi
0x18001d103  mov     [rax+20h], r9d
0x18001d107  mov     [rax+18h], r8d
0x18001d10b  push    rbp
0x18001d10c  push    rdi
0x18001d10d  push    r12
0x18001d10f  push    r13
0x18001d111  push    r14
0x18001d113  lea     rbp, [rax-4Fh]
0x18001d117  sub     rsp, 0A0h
0x18001d11e  mov     rbx, rdx
0x18001d121  mov     r14, rcx
0x18001d124  xor     esi, esi
0x18001d126  mov     [rbp+47h+hdpa], rsi
0x18001d12a  lea     edx, [rsi+5]
0x18001d12d  lea     rcx, [rbp+47h+hdpa]
0x18001d131  call    ?Create@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyRelease@UICondition@@@@@@QEAAHH@Z; CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::Create(int)
0x18001d136  test    eax, eax
0x18001d138  jz      loc_18001D436
0x18001d13e  mov     [rbp+47h+psz], rsi
0x18001d142  lea     r9, [rbp+47h+psz]
0x18001d146  mov     r12d, 104h
0x18001d14c  mov     r8d, r12d
0x18001d14f  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18001d154  mov     edi, eax
0x18001d156  test    eax, eax
0x18001d158  js      loc_18001D42B
0x18001d15e  mov     [rbp+47h+arg_20], esi
0x18001d161  mov     r13, [rbp+47h+psz]
0x18001d165  mov     [rbp+47h+var_58], r13
0x18001d169  mov     [rbp+47h+var_50], r12
0x18001d16d  test    rbx, rbx
0x18001d170  jz      loc_18001D273
0x18001d176  mov     [rbp+47h+arg_18], esi
0x18001d179  mov     rax, [rbx]
0x18001d17c  lea     rdx, [rbp+47h+arg_18]
0x18001d180  mov     rcx, rbx
0x18001d183  mov     rax, [rax+38h]
0x18001d187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d18c  mov     edi, eax
0x18001d18e  cmp     [rbp+47h+arg_18], esi
0x18001d191  jbe     loc_18001D269
0x18001d197  test    edi, edi
0x18001d199  js      loc_18001D394
0x18001d19f  mov     [rbp+47h+var_78], 0
0x18001d1a7  mov     rax, [rbx]
0x18001d1aa  lea     r8, [rbp+47h+var_78]
0x18001d1ae  mov     edx, esi
0x18001d1b0  mov     rcx, rbx
0x18001d1b3  mov     rax, [rax+40h]
0x18001d1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1bc  mov     edi, eax
0x18001d1be  test    eax, eax
0x18001d1c0  js      loc_18001D25E
0x18001d1c6  mov     [rbp+47h+pv], 0
0x18001d1ce  mov     rcx, [rbp+47h+var_78]
0x18001d1d2  mov     rax, [rcx]
0x18001d1d5  lea     r8, [rbp+47h+pv]
0x18001d1d9  mov     edx, 80058000h
0x18001d1de  mov     rax, [rax+28h]
0x18001d1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1e7  mov     edi, eax
0x18001d1e9  test    eax, eax
0x18001d1eb  js      short loc_18001D24E
0x18001d1ed  mov     [rbp+47h+arg_10], 4
0x18001d1f4  lea     r9, [rbp+47h+arg_10]; unsigned int *
0x18001d1f8  mov     rcx, [rbp+47h+pv]; unsigned __int16 *
0x18001d1fc  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x18001d201  test    eax, eax
0x18001d203  js      short loc_18001D231
0x18001d205  cmp     [rbp+47h+arg_10], 0
0x18001d209  jnz     short loc_18001D231
0x18001d20b  mov     rcx, [rbp+47h+pv]; pv
0x18001d20f  call    cs:__imp_CoTaskMemFree
0x18001d215  mov     rcx, [rbp+47h+var_78]
0x18001d219  mov     rax, [rcx]
0x18001d21c  lea     r8, [rbp+47h+pv]
0x18001d220  xor     edx, edx
0x18001d222  mov     rax, [rax+28h]
0x18001d226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d22b  mov     edi, eax
0x18001d22d  test    eax, eax
0x18001d22f  js      short loc_18001D24E
0x18001d231  mov     rdx, [rbp+47h+pv]
0x18001d235  lea     rcx, [rbp+47h+hdpa]
0x18001d239  call    ?AppendPtr@?$CDPA_Base@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@QEAAJPEAVCLibraryInfo@@PEAH@Z; CDPA_Base<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::AppendPtr(CLibraryInfo *,int *)
0x18001d23e  mov     edi, eax
0x18001d240  test    eax, eax
0x18001d242  jns     short loc_18001D24E
0x18001d244  mov     rcx, [rbp+47h+pv]; pv
0x18001d248  call    cs:__imp_CoTaskMemFree
0x18001d24e  mov     rcx, [rbp+47h+var_78]
0x18001d252  mov     rax, [rcx]
0x18001d255  mov     rax, [rax+10h]
0x18001d259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d25e  inc     esi
0x18001d260  cmp     esi, [rbp+47h+arg_18]
0x18001d263  jb      loc_18001D197
0x18001d269  xor     esi, esi
0x18001d26b  test    edi, edi
0x18001d26d  js      loc_18001D396
0x18001d273  test    r14, r14
0x18001d276  jz      loc_18001D396
0x18001d27c  mov     [rbp+47h+pv], rsi
0x18001d280  mov     rax, [r14]
0x18001d283  lea     r9, [rbp+47h+pv]
0x18001d287  lea     r8, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x18001d28e  xor     edx, edx
0x18001d290  mov     rcx, r14
0x18001d293  mov     rax, [rax+40h]
0x18001d297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d29c  mov     edi, eax
0x18001d29e  test    eax, eax
0x18001d2a0  js      loc_18001D396
0x18001d2a6  mov     [rbp+47h+arg_18], esi
0x18001d2a9  mov     rcx, [rbp+47h+pv]
0x18001d2ad  mov     rax, [rcx]
0x18001d2b0  lea     rdx, [rbp+47h+arg_18]
0x18001d2b4  mov     rax, [rax+18h]
0x18001d2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2bd  mov     edi, eax
0x18001d2bf  mov     ebx, esi
0x18001d2c1  test    eax, eax
0x18001d2c3  js      loc_18001D382
0x18001d2c9  cmp     ebx, [rbp+47h+arg_18]
0x18001d2cc  jnb     loc_18001D382
0x18001d2d2  mov     [rbp+47h+var_78], rsi
0x18001d2d6  mov     rcx, [rbp+47h+pv]
0x18001d2da  mov     rax, [rcx]
0x18001d2dd  lea     r9, [rbp+47h+var_78]
0x18001d2e1  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18001d2e8  mov     edx, ebx
0x18001d2ea  mov     rax, [rax+20h]
0x18001d2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f3  mov     edi, eax
0x18001d2f5  test    eax, eax
0x18001d2f7  js      short loc_18001D378
0x18001d2f9  mov     [rbp+47h+arg_10], esi
0x18001d2fc  mov     rcx, [rbp+47h+var_78]
0x18001d300  mov     rax, [rcx]
0x18001d303  lea     rdx, [rbp+47h+arg_10]
0x18001d307  mov     rax, [rax+20h]
0x18001d30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d310  mov     edi, eax
0x18001d312  test    eax, eax
0x18001d314  js      short loc_18001D368
0x18001d316  cmp     [rbp+47h+arg_10], 1
0x18001d31a  jnz     short loc_18001D368
0x18001d31c  mov     [rbp+47h+var_60], rsi
0x18001d320  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18001d327  movaps  xmmword ptr [rbp+47h+var_40.fmtid.Data1], xmm0
0x18001d32b  mov     eax, cs:PKEY_Null.pid
0x18001d331  mov     [rbp+47h+var_40.pid], eax
0x18001d334  lea     r9, [rbp+47h+var_60]; unsigned __int16 **
0x18001d338  lea     r8, [rbp+47h+var_40]; struct _tagpropertykey
0x18001d33c  mov     rcx, [rbp+47h+var_78]; struct IScopeItem *
0x18001d340  call    ?_GetScopeItemName@@YAJPEAUIScopeItem@@W4_SIGDN@@U_tagpropertykey@@PEAPEAG@Z; _GetScopeItemName(IScopeItem *,_SIGDN,_tagpropertykey,ushort * *)
0x18001d345  mov     edi, eax
0x18001d347  test    eax, eax
0x18001d349  js      short loc_18001D368
0x18001d34b  mov     rdx, [rbp+47h+var_60]
0x18001d34f  lea     rcx, [rbp+47h+hdpa]
0x18001d353  call    ?AppendPtr@?$CDPA_Base@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@QEAAJPEAVCLibraryInfo@@PEAH@Z; CDPA_Base<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::AppendPtr(CLibraryInfo *,int *)
0x18001d358  mov     edi, eax
0x18001d35a  test    eax, eax
0x18001d35c  jns     short loc_18001D368
0x18001d35e  mov     rcx, [rbp+47h+var_60]; pv
0x18001d362  call    cs:__imp_CoTaskMemFree
0x18001d368  mov     rcx, [rbp+47h+var_78]
0x18001d36c  mov     rax, [rcx]
0x18001d36f  mov     rax, [rax+10h]
0x18001d373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d378  inc     ebx
0x18001d37a  test    edi, edi
0x18001d37c  jns     loc_18001D2C9
0x18001d382  mov     rcx, [rbp+47h+pv]
0x18001d386  mov     rax, [rcx]
0x18001d389  mov     rax, [rax+10h]
0x18001d38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d392  jmp     short loc_18001D396
0x18001d394  xor     esi, esi
0x18001d396  mov     rbx, [rbp+47h+hdpa]
0x18001d39a  mov     r14d, [rbp+47h+arg_20]
0x18001d39e  mov     edx, 1
0x18001d3a3  mov     eax, edi
0x18001d3a5  test    rbx, rbx
0x18001d3a8  jz      short loc_18001D3AE
0x18001d3aa  mov     ecx, [rbx]
0x18001d3ac  jmp     short loc_18001D3B0
0x18001d3ae  xor     ecx, ecx
0x18001d3b0  cmp     esi, ecx
0x18001d3b2  jge     short loc_18001D3FE
0x18001d3b4  movsxd  rdx, esi; i
0x18001d3b7  mov     rcx, rbx; hdpa
0x18001d3ba  call    cs:g_pfn_DPA_GetPtr
0x18001d3c0  lea     rcx, [rbp+47h+var_50]
0x18001d3c4  mov     [rsp+0C0h+var_88], rcx; unsigned __int64 *
0x18001d3c9  lea     rcx, [rbp+47h+var_58]
0x18001d3cd  mov     [rsp+0C0h+var_90], rcx; unsigned __int16 **
0x18001d3d2  mov     [rsp+0C0h+var_A0], r14d; int
0x18001d3d7  mov     r9, r12; unsigned __int64
0x18001d3da  mov     r8, r13; unsigned __int16 *
0x18001d3dd  mov     rcx, rax; pszSrc
0x18001d3e0  call    ?_AppendNext@@YAJPEBG0PEAG_KHKPEAPEAGPEA_K@Z; _AppendNext(ushort const *,ushort const *,ushort *,unsigned __int64,int,ulong,ushort * *,unsigned __int64 *)
0x18001d3e5  mov     edi, eax
0x18001d3e7  test    eax, eax
0x18001d3e9  mov     edx, 1
0x18001d3ee  cmovns  r14d, edx
0x18001d3f2  add     esi, edx
0x18001d3f4  mov     r13, [rbp+47h+var_58]
0x18001d3f8  mov     r12, [rbp+47h+var_50]
0x18001d3fc  jmp     short loc_18001D3A3
0x18001d3fe  cmp     edi, 8007007Ah
0x18001d404  jnz     short loc_18001D40A
0x18001d406  mov     edi, edx
0x18001d408  jmp     short loc_18001D40E
0x18001d40a  test    eax, eax
0x18001d40c  js      short loc_18001D421
0x18001d40e  mov     rdx, [rbp+47h+ppwsz]; ppwsz
0x18001d412  mov     rcx, [rbp+47h+psz]; psz
0x18001d416  call    cs:__imp_SHStrDupW
0x18001d41c  test    eax, eax
0x18001d41e  cmovs   edi, eax
0x18001d421  mov     rcx, [rbp+47h+psz]; hMem
0x18001d425  call    cs:__imp_LocalFree
0x18001d42b  lea     rcx, [rbp+47h+hdpa]
0x18001d42f  call    ?DestroyCallback@?$CDPA@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAAXP6AHPEAU_ITEMID_CHILD@@PEAX@Z1@Z; CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::DestroyCallback(int (*)(_ITEMID_CHILD *,void *),void *)
0x18001d434  jmp     short loc_18001D43B
0x18001d436  mov     edi, 8007000Eh
0x18001d43b  lea     rcx, [rbp+47h+hdpa]
0x18001d43f  call    ??1?$CDPA_Base@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAA@XZ; CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>(void)
0x18001d444  mov     eax, edi
0x18001d446  lea     r11, [rsp+0C0h+var_20]
0x18001d44e  mov     rbx, [r11+30h]
0x18001d452  mov     rsi, [r11+38h]
0x18001d456  mov     rsp, r11
0x18001d459  pop     r14
0x18001d45b  pop     r13
0x18001d45d  pop     r12
0x18001d45f  pop     rdi
0x18001d460  pop     rbp
0x18001d461  retn
```
