# CGrepWdsResolver::_TryResolveToWDS(REUSEWHERE_MODE,IScope *,IServiceProvider *,int *,_GUID const &,void * *)

- ea: `0x1800616c0`
- end: `0x1800618ef`
- name: `?_TryResolveToWDS@CGrepWdsResolver@@AEAAJW4REUSEWHERE_MODE@@PEAUIScope@@PEAUIServiceProvider@@PEAHAEBU_GUID@@PEAPEAX@Z`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060340`

## callees

- `0x180013760`
- `0x18003c5f4`
- `0x18003cdc8`
- `0x1800616c0`
- `0x1800618f8`
- `0x180062160`
- `0x1800623f0`
- `0x180063f24`
- `0x180070088`
- `0x1800954c0`
- `0x180095534`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061720`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800618c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800618cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061720`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800618c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800618cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGrepWdsResolver::_TryResolveToWDS(
        CGrepWdsResolver *a1,
        int a2,
        struct IScope *a3,
        __int64 a4,
        _DWORD *a5,
        struct _GUID *a6,
        void **a7)
{
  void **v9; // r14
  _DWORD *v10; // r15
  int IsRootScopeCSC; // esi
  char IsEnabled; // al
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rdi
  int v16; // [rsp+20h] [rbp-40h]
  struct IObjectCollection *v17; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  BOOL v23; // [rsp+B8h] [rbp+58h] BYREF
  int v24; // [rsp+BCh] [rbp+5Ch]

  v24 = HIDWORD(a4);
  v9 = a7;
  *a7 = 0;
  v10 = a5;
  *a5 = 0;
  v23 = 0;
  IsRootScopeCSC = CGrepWdsResolver::_IsRootScopeCSC(a1, a3, &v23);
  if ( IsRootScopeCSC >= 0 )
  {
    LODWORD(a5) = 0;
    v18 = 0;
    pv = 0;
    CoTaskMemFree(0);
    CoTaskMemFree(0);
    IsRootScopeCSC = CGrepWdsResolver::_GenerateScopeString(a1, v23, (int *)&a5, &v18, (unsigned __int16 **)&pv);
    LODWORD(a7) = IsRootScopeCSC;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl);
    v13 = v18;
    v14 = (unsigned __int16 *)pv;
    if ( IsEnabled )
    {
      v17 = (struct IObjectCollection *)pv;
      v20 = v18;
      FileExplorerTelemetry::SearchConfigResolveIndexerScopeGenerated<long &,int &,int &,unsigned short const *,unsigned short const *>(
        (int *)&a7,
        &v23,
        &a5,
        (__int64 *)&v20,
        (__int64 *)&v17);
    }
    if ( IsRootScopeCSC >= 0 && (_DWORD)a5 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
      {
        v17 = 0;
        IsRootScopeCSC = CGrepWdsResolver::_CreateWDSConfigFromScopeString(
                           (unsigned __int16 *)a1,
                           v13,
                           v14,
                           a2,
                           0,
                           v10,
                           &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                           (void **)&v17);
        LODWORD(a7) = IsRootScopeCSC;
        v23 = *v10 != 0;
        FileExplorerTelemetry::SearchConfigIndexerResolveComplete<long &,int>((int *)&a7, &v23);
        if ( IsRootScopeCSC >= 0 )
        {
          LOBYTE(v23) = 0;
          LODWORD(a5) = 0;
          IsRootScopeCSC = CGrepWdsResolver::_TryResolveToCloudSearch(
                             a1,
                             (__int64 (__fastcall ***)(struct IScope *, GUID *, __int64 **))a3,
                             (bool *)&v23,
                             (unsigned int *)&a5,
                             v17);
          LODWORD(a7) = IsRootScopeCSC;
          FileExplorerTelemetry::SearchConfigCloudResolveComplete<long &,bool &,unsigned int &>(
            (int *)&a7,
            (char *)&v23,
            (int *)&a5);
          if ( IsRootScopeCSC >= 0 )
          {
            if ( v17 )
            {
              IsRootScopeCSC = ((__int64 (__fastcall *)(struct IObjectCollection *, struct _GUID *, void **))v17->lpVtbl->QueryInterface)(
                                 v17,
                                 a6,
                                 v9);
            }
            else
            {
              *v9 = 0;
              IsRootScopeCSC = 0;
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x305,
              (unsigned int)"onecoreuap\\shell\\windows.storage.search\\grepwdsproviderresolver.cpp",
              (const char *)(unsigned int)IsRootScopeCSC,
              v16);
          }
        }
        wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v17);
      }
      else
      {
        IsRootScopeCSC = CGrepWdsResolver::_CreateWDSConfigFromScopeString(
                           (unsigned __int16 *)a1,
                           v13,
                           v14,
                           a2,
                           0,
                           v10,
                           a6,
                           v9);
      }
    }
    CoTaskMemFree(v14);
    CoTaskMemFree(v13);
  }
  return (unsigned int)IsRootScopeCSC;
}

```

## disassembly

```asm
0x1800616c0  mov     [rsp-38h+arg_0], rbx
0x1800616c5  mov     qword ptr [rsp-38h+arg_18], r9
0x1800616ca  mov     [rsp-38h+arg_10], r8
0x1800616cf  push    rbp
0x1800616d0  push    rsi
0x1800616d1  push    rdi
0x1800616d2  push    r12
0x1800616d4  push    r13
0x1800616d6  push    r14
0x1800616d8  push    r15
0x1800616da  mov     rbp, rsp
0x1800616dd  sub     rsp, 60h
0x1800616e1  mov     rax, r8
0x1800616e4  mov     r13d, edx
0x1800616e7  mov     r12, rcx
0x1800616ea  xor     ebx, ebx
0x1800616ec  mov     r14, [rbp+arg_30]
0x1800616f0  mov     [r14], rbx
0x1800616f3  mov     r15, [rbp+arg_20]
0x1800616f7  mov     [r15], ebx
0x1800616fa  mov     [rbp+arg_18], ebx
0x1800616fd  lea     r8, [rbp+arg_18]; int *
0x180061701  mov     rdx, rax; struct IScope *
0x180061704  call    ?_IsRootScopeCSC@CGrepWdsResolver@@AEAAJPEAUIScope@@PEAH@Z; CGrepWdsResolver::_IsRootScopeCSC(IScope *,int *)
0x180061709  mov     esi, eax
0x18006170b  test    eax, eax
0x18006170d  js      loc_1800618D5
0x180061713  mov     dword ptr [rbp+arg_20], ebx
0x180061716  mov     [rbp+var_18], rbx
0x18006171a  mov     [rbp+pv], rbx
0x18006171e  xor     ecx, ecx; pv
0x180061720  call    cs:__imp_CoTaskMemFree
0x180061726  xor     ecx, ecx; pv
0x180061728  call    cs:__imp_CoTaskMemFree
0x18006172e  lea     rax, [rbp+pv]
0x180061732  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x180061737  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18006173b  lea     r8, [rbp+arg_20]; int *
0x18006173f  mov     edx, [rbp+arg_18]; int
0x180061742  mov     rcx, r12; this
0x180061745  call    ?_GenerateScopeString@CGrepWdsResolver@@AEAAJHPEAHPEAPEAG1@Z; CGrepWdsResolver::_GenerateScopeString(int,int *,ushort * *,ushort * *)
0x18006174a  mov     esi, eax
0x18006174c  mov     dword ptr [rbp+arg_30], eax
0x18006174f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x180061756  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x18006175b  mov     rbx, [rbp+var_18]
0x18006175f  mov     rdi, [rbp+pv]
0x180061763  test    al, al
0x180061765  jz      short loc_18006178D
0x180061767  mov     [rbp+var_20], rdi
0x18006176b  mov     [rbp+var_8], rbx
0x18006176f  lea     rax, [rbp+var_20]
0x180061773  mov     [rsp+60h+var_40], rax
0x180061778  lea     r9, [rbp+var_8]
0x18006177c  lea     r8, [rbp+arg_20]
0x180061780  lea     rdx, [rbp+arg_18]
0x180061784  lea     rcx, [rbp+arg_30]
0x180061788  call    ??$SearchConfigResolveIndexerScopeGenerated@AEAJAEAHAEAHPEBGPEBG@FileExplorerTelemetry@@SAXAEAJAEAH1$$QEAPEBG2@Z; FileExplorerTelemetry::SearchConfigResolveIndexerScopeGenerated<long &,int &,int &,ushort const *,ushort const *>(long &,int &,int &,ushort const * &&,ushort const * &&)
0x18006178d  test    esi, esi
0x18006178f  js      loc_1800618C2
0x180061795  cmp     dword ptr [rbp+arg_20], 0
0x180061799  jz      loc_1800618C2
0x18006179f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x1800617a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1800617ab  xor     ecx, ecx
0x1800617ad  test    al, al
0x1800617af  jz      loc_180061897
0x1800617b5  mov     [rbp+var_20], rcx
0x1800617b9  lea     rax, [rbp+var_20]
0x1800617bd  mov     [rsp+60h+var_28], rax
0x1800617c2  lea     rax, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x1800617c9  mov     [rsp+60h+var_30], rax
0x1800617ce  mov     [rsp+60h+var_38], r15
0x1800617d3  mov     [rsp+60h+var_40], rcx
0x1800617d8  mov     r9d, r13d
0x1800617db  mov     r8, rdi
0x1800617de  mov     rdx, rbx
0x1800617e1  mov     rcx, r12
0x1800617e4  call    ?_CreateWDSConfigFromScopeString@CGrepWdsResolver@@AEAAJPEBG0W4REUSEWHERE_MODE@@PEAUICondition@@PEAHAEBU_GUID@@PEAPEAX@Z; CGrepWdsResolver::_CreateWDSConfigFromScopeString(ushort const *,ushort const *,REUSEWHERE_MODE,ICondition *,int *,_GUID const &,void * *)
0x1800617e9  mov     esi, eax
0x1800617eb  mov     dword ptr [rbp+arg_30], eax
0x1800617ee  xor     r13d, r13d
0x1800617f1  mov     eax, r13d
0x1800617f4  cmp     [r15], r13d
0x1800617f7  setnz   al
0x1800617fa  mov     [rbp+arg_18], eax
0x1800617fd  lea     rdx, [rbp+arg_18]
0x180061801  lea     rcx, [rbp+arg_30]
0x180061805  call    ??$SearchConfigIndexerResolveComplete@AEAJH@FileExplorerTelemetry@@SAXAEAJ$$QEAH@Z; FileExplorerTelemetry::SearchConfigIndexerResolveComplete<long &,int>(long &,int &&)
0x18006180a  test    esi, esi
0x18006180c  js      short loc_18006188C
0x18006180e  mov     byte ptr [rbp+arg_18], r13b
0x180061812  mov     dword ptr [rbp+arg_20], r13d
0x180061816  mov     rax, [rbp+var_20]
0x18006181a  mov     [rsp+60h+var_40], rax; int
0x18006181f  lea     r9, [rbp+arg_20]; unsigned int *
0x180061823  lea     r8, [rbp+arg_18]; bool *
0x180061827  mov     rdx, [rbp+arg_10]; struct IScope *
0x18006182b  mov     rcx, r12; this
0x18006182e  call    ?_TryResolveToCloudSearch@CGrepWdsResolver@@AEAAJPEAUIScope@@PEA_NPEAIPEAUIObjectCollection@@@Z; CGrepWdsResolver::_TryResolveToCloudSearch(IScope *,bool *,uint *,IObjectCollection *)
0x180061833  mov     esi, eax
0x180061835  mov     dword ptr [rbp+arg_30], eax
0x180061838  lea     r8, [rbp+arg_20]
0x18006183c  lea     rdx, [rbp+arg_18]
0x180061840  lea     rcx, [rbp+arg_30]
0x180061844  call    ??$SearchConfigCloudResolveComplete@AEAJAEA_NAEAI@FileExplorerTelemetry@@SAXAEAJAEA_NAEAI@Z; FileExplorerTelemetry::SearchConfigCloudResolveComplete<long &,bool &,uint &>(long &,bool &,uint &)
0x180061849  mov     rcx, [rbp+38h]; this
0x18006184d  test    esi, esi
0x18006184f  jns     short loc_180061867
0x180061851  mov     r9d, esi; char *
0x180061854  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\windows.storage.sear"...
0x18006185b  mov     edx, 305h; void *
0x180061860  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061865  jmp     short loc_18006188C
0x180061867  mov     rcx, [rbp+var_20]
0x18006186b  test    rcx, rcx
0x18006186e  jz      short loc_180061886
0x180061870  mov     rax, [rcx]
0x180061873  mov     r8, r14
0x180061876  mov     rdx, [rbp+arg_28]
0x18006187a  mov     rax, [rax]
0x18006187d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061882  mov     esi, eax
0x180061884  jmp     short loc_18006188C
0x180061886  mov     [r14], r13
0x180061889  mov     esi, r13d
0x18006188c  lea     rcx, [rbp+var_20]
0x180061890  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180061895  jmp     short loc_1800618C2
0x180061897  mov     [rsp+60h+var_28], r14
0x18006189c  mov     rax, [rbp+arg_28]
0x1800618a0  mov     [rsp+60h+var_30], rax
0x1800618a5  mov     [rsp+60h+var_38], r15
0x1800618aa  mov     [rsp+60h+var_40], rcx
0x1800618af  mov     r9d, r13d
0x1800618b2  mov     r8, rdi
0x1800618b5  mov     rdx, rbx
0x1800618b8  mov     rcx, r12
0x1800618bb  call    ?_CreateWDSConfigFromScopeString@CGrepWdsResolver@@AEAAJPEBG0W4REUSEWHERE_MODE@@PEAUICondition@@PEAHAEBU_GUID@@PEAPEAX@Z; CGrepWdsResolver::_CreateWDSConfigFromScopeString(ushort const *,ushort const *,REUSEWHERE_MODE,ICondition *,int *,_GUID const &,void * *)
0x1800618c0  mov     esi, eax
0x1800618c2  mov     rcx, rdi; pv
0x1800618c5  call    cs:__imp_CoTaskMemFree
0x1800618cb  nop
0x1800618cc  mov     rcx, rbx; pv
0x1800618cf  call    cs:__imp_CoTaskMemFree
0x1800618d5  mov     eax, esi
0x1800618d7  mov     rbx, [rsp+60h+arg_0]
0x1800618df  add     rsp, 60h
0x1800618e3  pop     r15
0x1800618e5  pop     r14
0x1800618e7  pop     r13
0x1800618e9  pop     r12
0x1800618eb  pop     rdi
0x1800618ec  pop     rsi
0x1800618ed  pop     rbp
0x1800618ee  retn
```
