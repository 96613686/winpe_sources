# GetBatchedChunkDataFromFilter(IFilter *,wchar_t const *,uint,tagCHUNKDATA *,uint *,ulong *)

- ea: `0x14001e68c`
- end: `0x14001ea84`
- name: `?GetBatchedChunkDataFromFilter@@YAJPEAUIFilter@@PEB_WIPEAUtagCHUNKDATA@@PEAIPEAK@Z`
- size: `1016`
- prototype: `__int64 __fastcall(struct IFilter *, const wchar_t *, unsigned int, struct tagCHUNKDATA *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001e600`

## callees

- `0x1400030a0`
- `0x1400034b0`
- `0x140005205`
- `0x140006890`
- `0x140009f14`
- `0x14000b5c4`
- `0x14000b8bc`
- `0x14000cc34`
- `0x14000d80c`
- `0x14000e064`
- `0x14000e158`
- `0x1400165bc`
- `0x140016d14`
- `0x14001e68c`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001ea30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001ea66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001ea30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001ea66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001e8a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001e8a3`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x14001e9e9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x14001e9e9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001ea16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001ea4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001ea16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001ea4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetBatchedChunkDataFromFilter(
        struct IFilter *a1,
        const wchar_t *a2,
        unsigned int a3,
        struct tagCHUNKDATA *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  unsigned int v6; // r15d
  struct IFilter *v7; // rdi
  unsigned int *v8; // rsi
  unsigned int v9; // r12d
  __int64 v10; // rbx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  _WORD *v14; // r14
  unsigned int v15; // r13d
  char *v16; // rsi
  int v17; // edi
  bool v18; // zf
  unsigned int v19; // edi
  void *v20; // rax
  void **v21; // rdx
  struct IFilterVtbl *lpVtbl; // rax
  PROPVARIANT *v24; // rcx
  HRESULT v25; // eax
  HRESULT v26; // edi
  PROPVARIANT *v27; // rcx
  int v28; // [rsp+20h] [rbp-C8h]
  PROPVARIANT *pvarSrc; // [rsp+28h] [rbp-C0h] BYREF
  void *v30; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+38h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-A8h]
  struct IFilter *v33; // [rsp+48h] [rbp-A0h]
  struct tagCHUNKDATA *v34; // [rsp+50h] [rbp-98h]
  unsigned int *v35; // [rsp+58h] [rbp-90h]
  unsigned int *v36; // [rsp+60h] [rbp-88h]
  PROPVARIANT **p_pvarSrc; // [rsp+68h] [rbp-80h] BYREF
  __int64 v38; // [rsp+70h] [rbp-78h] BYREF
  char v39; // [rsp+78h] [rbp-70h]
  __int64 v40; // [rsp+80h] [rbp-68h]
  void *Src[2]; // [rsp+88h] [rbp-60h] BYREF
  int v42; // [rsp+98h] [rbp-50h]
  unsigned __int64 v43; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v40 = -2;
  v34 = a4;
  v6 = a3;
  v32 = a3;
  v7 = a1;
  v33 = a1;
  v8 = a5;
  v35 = a5;
  v36 = a6;
  v9 = 0;
  *a5 = 0;
  *a6 = 0;
  v10 = 0;
  v31 = 0;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    if ( v11 )
    {
      v12 = _open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEB_WK_N_Z(&v31);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
          (const char *)(unsigned int)v12,
          v28);
        goto LABEL_33;
      }
      v10 = v31;
    }
  }
  v14 = operator new[](0x20000u, (const struct std::nothrow_t *)&std::nothrow);
  v30 = v14;
  if ( v14 )
  {
    v15 = 0;
    while ( 1 )
    {
      if ( v9 >= v6
        || v10
        && (unsigned __int8)_is_signaled___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NXZ(&v31) )
      {
        goto LABEL_32;
      }
      ++*v8;
      v16 = (char *)v34 + 104 * v9;
      *((_DWORD *)v16 + 16) = ((__int64 (__fastcall *)(struct IFilter *, char *))v7->lpVtbl->GetChunk)(v7, v16);
      *(_OWORD *)(v16 + 72) = 0;
      *((_QWORD *)v16 + 11) = 0;
      if ( *((int *)v16 + 16) < 0 )
        goto LABEL_32;
      if ( *((_DWORD *)v16 + 2) == 1 )
      {
        std::wstring::wstring((__int64)Src);
        do
        {
          v28 = 0xFFFF;
          try
          {
            v17 = ((__int64 (*)(void))v7->lpVtbl->GetText)();
            if ( v17 >= 0 )
            {
              v14[0xFFFF] = 0;
              std::_WChar_traits<wchar_t>::length(v14);
              std::wstring::_Append<wchar_t>(Src);
            }
            if ( v17 != -2147215615 )
              *((_DWORD *)v16 + 24) = v17;
          }
          catch ( ... )
          {
            indexer::result::details::result_from_caught_exception<1>();
          }
          if ( v17 < 0 )
            break;
          v18 = v17 == 268041;
          v7 = v33;
        }
        while ( !v18 );
        v19 = 2 * v42 + 2;
        if ( (unsigned int)(2 * v42) < 0xFFFFFFFE && v19 != 2 )
        {
          *((_WORD *)v16 + 36) = 31;
          v20 = CoTaskMemAlloc(v19);
          *((_QWORD *)v16 + 10) = v20;
          if ( !v20 )
          {
            v13 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x69,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
              (const char *)0x8007000ELL,
              0xFFFF);
            std::wstring::_Tidy_deallocate((__int64)Src);
            goto LABEL_10;
          }
          v21 = Src;
          if ( v43 > 7 )
            v21 = (void **)Src[0];
          memcpy_0(v20, v21, v19);
          v15 += v19;
          if ( v15 > 0x40000 )
          {
            std::wstring::_Tidy_deallocate((__int64)Src);
LABEL_32:
            *v36 = v15;
            std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(&v30);
            v13 = 0;
            goto LABEL_33;
          }
        }
        std::wstring::_Tidy_deallocate((__int64)Src);
      }
      else if ( *((_DWORD *)v16 + 2) == 2 )
      {
        pvarSrc = 0;
        lpVtbl = v7->lpVtbl;
        p_pvarSrc = &pvarSrc;
        v38 = 0;
        v39 = 1;
        *((_DWORD *)v16 + 24) = ((__int64 (__fastcall *)(struct IFilter *, __int64 *))lpVtbl->GetValue)(v7, &v38);
        wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pvarSrc);
        v24 = pvarSrc;
        if ( pvarSrc )
        {
          v25 = PropVariantCopy((PROPVARIANT *)v16 + 9, pvarSrc);
          v26 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7C,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
              (const char *)(unsigned int)v25,
              v28);
            PropVariantClear(pvarSrc);
            v27 = pvarSrc;
            pvarSrc = 0;
            if ( v27 )
              CoTaskMemFree(v27);
            std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(&v30);
            v13 = v26;
            goto LABEL_33;
          }
          PropVariantClear(pvarSrc);
          v24 = pvarSrc;
        }
        pvarSrc = 0;
        if ( v24 )
          CoTaskMemFree(v24);
      }
      ++v9;
      v7 = v33;
      v8 = v35;
      v6 = v32;
    }
  }
  v13 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x38,
    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\mssrch\\gather\\include\\batchchunk.hxx",
    (const char *)0x8007000ELL,
    v28);
LABEL_10:
  std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(&v30);
LABEL_33:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
  return v13;
}

```

## disassembly

```asm
0x14001e68c  mov     rax, rsp
0x14001e68f  push    rbx
0x14001e690  push    rsi
0x14001e691  push    rdi
0x14001e692  push    r12
0x14001e694  push    r13
0x14001e696  push    r14
0x14001e698  push    r15
0x14001e69a  sub     rsp, 0B0h
0x14001e6a1  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x14001e6a9  mov     rax, cs:__security_cookie
0x14001e6b0  xor     rax, rsp
0x14001e6b3  mov     [rsp+0E8h+var_40], rax
0x14001e6bb  mov     [rsp+0E8h+var_98], r9
0x14001e6c0  mov     r15d, r8d
0x14001e6c3  mov     [rsp+0E8h+var_A8], r8d
0x14001e6c8  mov     rdi, rcx
0x14001e6cb  mov     [rsp+0E8h+var_A0], rcx
0x14001e6d0  mov     rsi, [rsp+0E8h+arg_20]
0x14001e6d8  mov     [rsp+0E8h+var_90], rsi
0x14001e6dd  mov     rax, [rsp+0E8h+arg_28]
0x14001e6e5  mov     [rsp+0E8h+var_88], rax
0x14001e6ea  xor     r12d, r12d
0x14001e6ed  mov     [rsi], r12d
0x14001e6f0  mov     [rax], r12d
0x14001e6f3  mov     ebx, r12d
0x14001e6f6  mov     [rsp+0E8h+var_B0], rbx
0x14001e6fb  test    rdx, rdx
0x14001e6fe  jz      short loc_14001E749
0x14001e700  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e704  inc     rax
0x14001e707  cmp     [rdx+rax*2], r12w
0x14001e70c  jnz     short loc_14001E704
0x14001e70e  test    rax, rax
0x14001e711  jz      short loc_14001E749
0x14001e713  lea     rcx, [rsp+0E8h+var_B0]
0x14001e718  call    ?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEB_WK_N@Z
0x14001e71d  mov     ebx, eax
0x14001e71f  test    eax, eax
0x14001e721  jns     short loc_14001E744
0x14001e723  mov     rcx, [rsp+0E8h]; this
0x14001e72b  mov     r9d, eax; char *
0x14001e72e  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x14001e735  mov     edx, 31h ; '1'; void *
0x14001e73a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e73f  jmp     loc_14001E936
0x14001e744  mov     rbx, [rsp+0E8h+var_B0]
0x14001e749  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001e750  mov     ecx, 20000h; unsigned __int64
0x14001e755  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001e75a  mov     r14, rax
0x14001e75d  mov     [rsp+0E8h+var_B8], rax
0x14001e762  test    rax, rax
0x14001e765  jnz     short loc_14001E796
0x14001e767  mov     rcx, [rsp+0E8h]; this
0x14001e76f  mov     ebx, 8007000Eh
0x14001e774  mov     r9d, ebx; char *
0x14001e777  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x14001e77e  lea     edx, [rax+38h]; void *
0x14001e781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e786  nop
0x14001e787  lea     rcx, [rsp+0E8h+var_B8]
0x14001e78c  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x14001e791  jmp     loc_14001E936
0x14001e796  mov     r13d, r12d
0x14001e799  cmp     r12d, r15d
0x14001e79c  jnb     loc_14001E922
0x14001e7a2  test    rbx, rbx
0x14001e7a5  jz      short loc_14001E7B9
0x14001e7a7  lea     rcx, [rsp+0E8h+var_B0]
0x14001e7ac  call    ?is_signaled@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NXZ
0x14001e7b1  test    al, al
0x14001e7b3  jnz     loc_14001E922
0x14001e7b9  inc     dword ptr [rsi]
0x14001e7bb  mov     eax, r12d
0x14001e7be  imul    rsi, rax, 68h ; 'h'
0x14001e7c2  add     rsi, [rsp+0E8h+var_98]
0x14001e7c7  mov     rax, [rdi]
0x14001e7ca  mov     rdx, rsi
0x14001e7cd  mov     rcx, rdi
0x14001e7d0  mov     rax, [rax+20h]
0x14001e7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e7d9  mov     [rsi+40h], eax
0x14001e7dc  lea     r15, [rsi+48h]
0x14001e7e0  xorps   xmm0, xmm0
0x14001e7e3  xor     eax, eax
0x14001e7e5  movups  xmmword ptr [r15], xmm0
0x14001e7e9  mov     [r15+10h], rax
0x14001e7ed  xor     edx, edx
0x14001e7ef  cmp     [rsi+40h], edx
0x14001e7f2  jl      loc_14001E922
0x14001e7f8  cmp     dword ptr [rsi+8], 1
0x14001e7fc  jnz     loc_14001E995
0x14001e802  lea     rcx, [rsp+0E8h+Src]
0x14001e80a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14001e80f  nop
0x14001e810  mov     [rsp+0E8h+var_C8], 0FFFFh; int
0x14001e818  mov     rax, [rdi]
0x14001e81b  mov     r8, r14
0x14001e81e  lea     rdx, [rsp+0E8h+var_C8]
0x14001e823  mov     rcx, rdi
0x14001e826  mov     rax, [rax+28h]
0x14001e82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e82f  mov     edi, eax
0x14001e831  test    eax, eax
0x14001e833  js      short loc_14001E865
0x14001e835  cmp     [rsp+0E8h+var_C8], 0FFFFh
0x14001e83d  ja      short loc_14001E865
0x14001e83f  mov     edx, [rsp+0E8h+var_C8]
0x14001e843  xor     ecx, ecx
0x14001e845  mov     [r14+rdx*2], cx
0x14001e84a  mov     rcx, r14
0x14001e84d  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x14001e852  mov     r8, rax
0x14001e855  mov     rdx, r14
0x14001e858  lea     rcx, [rsp+0E8h+Src]; Src
0x14001e860  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14001e865  cmp     edi, 80041701h
0x14001e86b  jz      short loc_14001E870
0x14001e86d  mov     [rsi+60h], edi
0x14001e870  test    edi, edi
0x14001e872  js      short loc_14001E881
0x14001e874  cmp     edi, 41709h
0x14001e87a  mov     rdi, [rsp+0E8h+var_A0]
0x14001e87f  jnz     short loc_14001E810
0x14001e881  mov     eax, [rsp+0E8h+var_50]
0x14001e888  lea     edi, ds:2[rax*2]
0x14001e88f  cmp     edi, 2
0x14001e892  jbe     loc_14001E965
0x14001e898  mov     word ptr [r15], 1Fh
0x14001e89e  mov     r15d, edi
0x14001e8a1  mov     ecx, edi; cb
0x14001e8a3  call    cs:__imp_CoTaskMemAlloc
0x14001e8a9  mov     [rsi+50h], rax
0x14001e8ad  test    rax, rax
0x14001e8b0  jnz     short loc_14001E8E4
0x14001e8b2  mov     rcx, [rsp+0E8h]; this
0x14001e8ba  mov     ebx, 8007000Eh
0x14001e8bf  mov     r9d, ebx; char *
0x14001e8c2  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x14001e8c9  lea     edx, [rax+69h]; void *
0x14001e8cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001e8d1  nop
0x14001e8d2  lea     rcx, [rsp+0E8h+Src]
0x14001e8da  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001e8df  jmp     loc_14001E787
0x14001e8e4  lea     rdx, [rsp+0E8h+Src]
0x14001e8ec  cmp     [rsp+0E8h+var_48], 7
0x14001e8f5  cmova   rdx, [rsp+0E8h+Src]; Src
0x14001e8fe  mov     r8, r15; Size
0x14001e901  mov     rcx, rax; void *
0x14001e904  call    memcpy_0
0x14001e909  add     r13d, edi
0x14001e90c  cmp     r13d, 40000h
0x14001e913  jbe     short loc_14001E965
0x14001e915  lea     rcx, [rsp+0E8h+Src]
0x14001e91d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001e922  mov     rax, [rsp+0E8h+var_88]
0x14001e927  mov     [rax], r13d
0x14001e92a  lea     rcx, [rsp+0E8h+var_B8]
0x14001e92f  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x14001e934  xor     ebx, ebx
0x14001e936  lea     rcx, [rsp+0E8h+var_B0]
0x14001e93b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001e940  mov     eax, ebx
0x14001e942  mov     rcx, [rsp+0E8h+var_40]
0x14001e94a  xor     rcx, rsp; StackCookie
0x14001e94d  call    __security_check_cookie
0x14001e952  add     rsp, 0B0h
0x14001e959  pop     r15
0x14001e95b  pop     r14
0x14001e95d  pop     r13
0x14001e95f  pop     r12
0x14001e961  pop     rdi
0x14001e962  pop     rsi
0x14001e963  pop     rbx
0x14001e964  retn
0x14001e965  lea     rcx, [rsp+0E8h+Src]
0x14001e96d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001e972  jmp     loc_14001EA6C
0x14001e977  lea     rcx, [rsp+0E8h+Src]
0x14001e97f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001e984  nop
0x14001e985  lea     rcx, [rsp+0E8h+var_B8]
0x14001e98a  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x14001e98f  mov     ebx, [rsp+0E8h+var_C8]
0x14001e993  jmp     short loc_14001E936
0x14001e995  cmp     dword ptr [rsi+8], 2
0x14001e999  jnz     loc_14001EA6C
0x14001e99f  mov     [rsp+0E8h+pvarSrc], rdx
0x14001e9a4  mov     rax, [rdi]
0x14001e9a7  lea     rcx, [rsp+0E8h+pvarSrc]
0x14001e9ac  mov     [rsp+0E8h+var_80], rcx
0x14001e9b1  mov     [rsp+0E8h+var_78], rdx
0x14001e9b6  mov     [rsp+0E8h+var_70], 1
0x14001e9bb  lea     rdx, [rsp+0E8h+var_78]
0x14001e9c0  mov     rcx, rdi
0x14001e9c3  mov     rax, [rax+30h]
0x14001e9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e9cc  mov     [rsi+60h], eax
0x14001e9cf  lea     rcx, [rsp+0E8h+var_80]
0x14001e9d4  call    ??1?$out_param_t@V?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x14001e9d9  mov     rcx, [rsp+0E8h+pvarSrc]
0x14001e9de  test    rcx, rcx
0x14001e9e1  jz      short loc_14001EA58
0x14001e9e3  mov     rdx, rcx; pvarSrc
0x14001e9e6  mov     rcx, r15; pvarDest
0x14001e9e9  call    cs:__imp_PropVariantCopy
0x14001e9ef  mov     edi, eax
0x14001e9f1  test    eax, eax
0x14001e9f3  jns     short loc_14001EA48
0x14001e9f5  mov     rcx, [rsp+0E8h]; this
0x14001e9fd  mov     r9d, eax; char *
0x14001ea00  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\Search\\mss"...
0x14001ea07  mov     edx, 7Ch ; '|'; void *
0x14001ea0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001ea11  mov     rcx, [rsp+0E8h+pvarSrc]; pvar
0x14001ea16  call    cs:__imp_PropVariantClear
0x14001ea1c  nop
0x14001ea1d  mov     rcx, [rsp+0E8h+pvarSrc]; pv
0x14001ea22  mov     [rsp+0E8h+pvarSrc], 0
0x14001ea2b  test    rcx, rcx
0x14001ea2e  jz      short loc_14001EA37
0x14001ea30  call    cs:__imp_CoTaskMemFree
0x14001ea36  nop
0x14001ea37  lea     rcx, [rsp+0E8h+var_B8]
0x14001ea3c  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x14001ea41  mov     ebx, edi
0x14001ea43  jmp     loc_14001E936
0x14001ea48  mov     rcx, [rsp+0E8h+pvarSrc]; pvar
0x14001ea4d  call    cs:__imp_PropVariantClear
0x14001ea53  mov     rcx, [rsp+0E8h+pvarSrc]; pv
0x14001ea58  mov     [rsp+0E8h+pvarSrc], 0
0x14001ea61  test    rcx, rcx
0x14001ea64  jz      short loc_14001EA6C
0x14001ea66  call    cs:__imp_CoTaskMemFree
0x14001ea6c  inc     r12d
0x14001ea6f  mov     rdi, [rsp+0E8h+var_A0]
0x14001ea74  mov     rsi, [rsp+0E8h+var_90]
0x14001ea79  mov     r15d, [rsp+0E8h+var_A8]
0x14001ea7e  jmp     loc_14001E799
```
