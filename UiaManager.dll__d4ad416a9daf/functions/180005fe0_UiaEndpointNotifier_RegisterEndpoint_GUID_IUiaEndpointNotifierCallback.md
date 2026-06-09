# UiaEndpointNotifier::RegisterEndpoint(_GUID,IUiaEndpointNotifierCallback *)

- ea: `0x180005fe0`
- end: `0x180006564`
- name: `?RegisterEndpoint@UiaEndpointNotifier@@UEAAJU_GUID@@PEAUIUiaEndpointNotifierCallback@@@Z`
- size: `1412`
- prototype: `__int64 __fastcall(UiaEndpointNotifier *__hidden this, struct _GUID *__struct_ptr, struct IUiaEndpointNotifierCallback *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800054f8`
- `0x180005fe0`
- `0x18000656c`
- `0x1800065c4`
- `0x180006edc`
- `0x18000a940`
- `0x1800188ac`
- `0x180031540`
- `0x180043a8c`
- `0x180070868`
- `0x180091010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800064fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006507`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800064fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006507`
- `msvcp_win!_Mtx_lock` at `0x18000611a`
- `msvcp_win!_Mtx_lock` at `0x18000611a`
- `msvcp_win!_Mtx_unlock` at `0x180006330`
- `msvcp_win!_Mtx_unlock` at `0x180006330`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006515`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006068`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006068`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006031`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006031`

## string_xrefs

- `0x18000641f`: `onecore\windows\accessibletech\uiamanager\dll\uiaendpointnotifier.cpp`
- `0x180006459`: `onecore\windows\accessibletech\uiamanager\dll\uiaendpointnotifier.cpp`
- `0x1800064e4`: `onecore\internal\sdk\inc\wil\opensource/wil/com.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UiaEndpointNotifier::RegisterEndpoint(
        UiaEndpointNotifier *this,
        struct _GUID *a2,
        struct IUiaEndpointNotifierCallback *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // esi
  LPVOID v8; // r15
  __int64 (__fastcall *v9)(LPVOID, struct _GUID *, _QWORD, struct IUiaEndpointNotifierCallback *); // r12
  __int64 v10; // rcx
  DWORD CurrentProcessId; // eax
  int v12; // eax
  unsigned int v13; // esi
  char *v14; // r9
  __m128i v15; // xmm6
  __int64 (__fastcall **v16)(char *, GUID *, __int64 *); // rax
  int v17; // esi
  char v18; // si
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r15
  unsigned __int64 v24; // xmm0_8
  unsigned __int64 v25; // r13
  _QWORD *v26; // rcx
  __int64 v27; // rax
  __m128i *v28; // r12
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  float v32; // xmm0_4
  float v33; // xmm1_4
  __m128i **v34; // rdx
  __int64 v35; // r13
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  LPVOID v39; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  LPVOID v44; // rcx
  LPVOID v45; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  __int64 v48; // [rsp+30h] [rbp-48h] BYREF
  __int64 v49[3]; // [rsp+38h] [rbp-40h] BYREF
  struct _GUID v50; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  LPVOID v52; // [rsp+D8h] [rbp+60h] BYREF

  v52 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  v6 = CoCreateInstance(&CLSID_UiaManager, 0, 4u, &GUID_05286245_d789_4e02_97c9_f27f01db10ca, &v52);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiaendpointnotifier.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    v44 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return v7;
  }
  else
  {
    v8 = v52;
    v9 = *(__int64 (__fastcall **)(LPVOID, struct _GUID *, _QWORD, struct IUiaEndpointNotifierCallback *))(*(_QWORD *)v52 + 24LL);
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      *((_QWORD *)this + 4) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    CurrentProcessId = GetCurrentProcessId();
    v50 = *a2;
    ppva = (_DWORD)this + 32;
    v12 = v9(v8, &v50, CurrentProcessId, a3);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiaendpointnotifier.cpp",
        (const char *)(unsigned int)v12,
        ppva);
      v45 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
      }
      return v13;
    }
    else
    {
      v14 = (char *)this + 8;
      if ( this == (UiaEndpointNotifier *)48 )
        v14 = 0;
      v15 = *(__m128i *)a2;
      v50 = *a2;
      v48 = 0;
      v16 = *(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v14;
      v49[0] = 0;
      v17 = (*v16)(v14, &GUID_00000038_0000_0000_c000_000000000046, v49);
      if ( v17 >= 0 )
        v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49[0] + 24LL))(v49[0], &v48);
      if ( v49[0] )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49[0] + 16LL))(v49[0]);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x795,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/com.h",
          (const char *)(unsigned int)v17,
          ppva);
      v18 = 0;
      if ( _Mtx_lock((_Mtx_t)UiaEndpointNotifierInProcManager::s_inProcEndpointIdMap) )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      if ( !std::_Mutex_base::_Verify_ownership_levels((std::_Mutex_base *)UiaEndpointNotifierInProcManager::s_inProcEndpointIdMap) )
      {
        std::_Throw_Cpp_error(6);
        __debugbreak();
      }
      v20 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(v19, &v50);
      v21 = std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Find<_GUID>(
              &dword_1800C4820,
              &v50,
              v20);
      v22 = v21;
      v23 = qword_1800C4828;
      if ( v21 == qword_1800C4828 )
      {
        v24 = _mm_srli_si128(v15, 8).m128i_u64[0];
        v25 = v15.m128i_u32[0]
            + v50.Data2
            + v50.Data3
            + (unsigned __int8)v24
            + (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 9))
            + (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 10))
            + (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 11))
            + (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 12))
            + (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 13))
            + (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 14))
            + (unsigned __int64)(unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v15, 15));
        v26 = *(_QWORD **)(qword_1800C4838 + 16 * (qword_1800C4850 & v25) + 8);
        if ( v26 == (_QWORD *)qword_1800C4828 )
        {
LABEL_21:
          if ( qword_1800C4830 == 0x666666666666666LL )
            std::_Xlength_error("unordered_map/set too long");
          v28 = (__m128i *)operator new(0x28u);
          v28[1] = v15;
          v29 = v48;
          v48 = 0;
          v28[2].m128i_i64[0] = v29;
          v30 = qword_1800C4830;
          v31 = qword_1800C4830 + 1;
          if ( qword_1800C4830 + 1 < 0 )
            v32 = (float)(int)(v31 & 1 | (v31 >> 1)) + (float)(int)(v31 & 1 | (v31 >> 1));
          else
            v32 = (float)(int)v31;
          if ( qword_1800C4858 < 0 )
            v33 = (float)(qword_1800C4858 & 1 | (unsigned int)((unsigned __int64)qword_1800C4858 >> 1))
                + (float)(qword_1800C4858 & 1 | (unsigned int)((unsigned __int64)qword_1800C4858 >> 1));
          else
            v33 = (float)(int)qword_1800C4858;
          if ( (float)(v32 / v33) > *(float *)&dword_1800C4820 )
          {
            std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Rehash_for_1(&dword_1800C4820);
            v23 = *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(
                               &dword_1800C4820,
                               &v50,
                               &v28[1],
                               v25);
            v30 = qword_1800C4830;
          }
          v34 = *(__m128i ***)(v23 + 8);
          qword_1800C4830 = v30 + 1;
          v28->m128i_i64[0] = v23;
          v28->m128i_i64[1] = (__int64)v34;
          *v34 = v28;
          *(_QWORD *)(v23 + 8) = v28;
          v35 = 2 * (qword_1800C4850 & v25);
          v36 = qword_1800C4838;
          v37 = *(_QWORD *)(qword_1800C4838 + 8 * v35);
          if ( v37 == qword_1800C4828 )
          {
            *(_QWORD *)(qword_1800C4838 + 8 * v35) = v28;
            *(_QWORD *)(v36 + 8 * v35 + 8) = v28;
          }
          else if ( v37 == v23 )
          {
            *(_QWORD *)(qword_1800C4838 + 8 * v35) = v28;
          }
          else if ( *(__m128i ***)(qword_1800C4838 + 8 * v35 + 8) == v34 )
          {
            *(_QWORD *)(qword_1800C4838 + 8 * v35 + 8) = v28;
          }
        }
        else
        {
          while ( 1 )
          {
            v27 = v15.m128i_i64[0] - v26[2];
            if ( v15.m128i_i64[0] == v26[2] )
              v27 = v24 - v26[3];
            if ( !v27 )
              break;
            if ( v26 == *(_QWORD **)(qword_1800C4838 + 16 * (qword_1800C4850 & v25)) )
            {
              v23 = (__int64)v26;
              goto LABEL_21;
            }
            v26 = (_QWORD *)v26[1];
          }
        }
      }
      else
      {
        v41 = *(_QWORD *)(v21 + 32);
        *(_QWORD *)(v22 + 32) = 0;
        v49[0] = v41;
        v18 = 1;
        v42 = v48;
        v48 = 0;
        v43 = *(_QWORD *)(v22 + 32);
        *(_QWORD *)(v22 + 32) = v42;
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      _Mtx_unlock((_Mtx_t)UiaEndpointNotifierInProcManager::s_inProcEndpointIdMap);
      if ( v18 && v49[0] )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49[0] + 16LL))(v49[0]);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      if ( *((struct IUiaEndpointNotifierCallback **)this + 5) != a3 )
      {
        if ( a3 )
          (*(void (__fastcall **)(struct IUiaEndpointNotifierCallback *))(*(_QWORD *)a3 + 8LL))(a3);
        v38 = *((_QWORD *)this + 5);
        *((_QWORD *)this + 5) = a3;
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
      *((struct _GUID *)this + 3) = *a2;
      v39 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180005fe0  push    rbp
0x180005fe2  push    rbx
0x180005fe3  push    rsi
0x180005fe4  push    rdi
0x180005fe5  push    r12
0x180005fe7  push    r13
0x180005fe9  push    r14
0x180005feb  push    r15
0x180005fed  mov     rbp, rsp
0x180005ff0  sub     rsp, 78h
0x180005ff4  movaps  [rsp+78h+var_18], xmm6
0x180005ff9  mov     rdi, r8
0x180005ffc  mov     r14, rdx
0x180005fff  mov     rbx, rcx
0x180006002  xor     r13d, r13d
0x180006005  mov     [rbp+arg_18], r13
0x180006009  lea     rcx, [rbp+arg_18]
0x18000600d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006012  lea     rax, [rbp+arg_18]
0x180006016  mov     qword ptr [rsp+78h+ppv], rax; int
0x18000601b  lea     r9, _GUID_05286245_d789_4e02_97c9_f27f01db10ca; riid
0x180006022  xor     edx, edx; pUnkOuter
0x180006024  mov     r8d, 4; dwClsContext
0x18000602a  lea     rcx, CLSID_UiaManager; rclsid
0x180006031  call    cs:__imp_CoCreateInstance
0x180006037  mov     esi, eax
0x180006039  test    eax, eax
0x18000603b  js      loc_180006418
0x180006041  mov     r15, [rbp+arg_18]
0x180006045  mov     rax, [r15]
0x180006048  mov     r12, [rax+18h]
0x18000604c  lea     rsi, [rbx+20h]
0x180006050  mov     rcx, [rsi]
0x180006053  test    rcx, rcx
0x180006056  jz      short loc_180006068
0x180006058  mov     [rsi], r13
0x18000605b  mov     rax, [rcx]
0x18000605e  mov     rax, [rax+10h]
0x180006062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006067  nop
0x180006068  call    cs:__imp_GetCurrentProcessId
0x18000606e  movups  xmm0, xmmword ptr [r14]
0x180006072  movaps  [rbp+var_28], xmm0
0x180006076  mov     qword ptr [rsp+78h+ppv], rsi; int
0x18000607b  mov     r9, rdi
0x18000607e  mov     r8d, eax
0x180006081  lea     rdx, [rbp+var_28]
0x180006085  mov     rcx, r15
0x180006088  mov     rax, r12
0x18000608b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006090  mov     esi, eax
0x180006092  test    eax, eax
0x180006094  js      loc_180006452
0x18000609a  lea     rcx, [rbx-30h]
0x18000609e  lea     r9, [rbx+8]
0x1800060a2  test    rcx, rcx
0x1800060a5  cmovz   r9, r13
0x1800060a9  movups  xmm6, xmmword ptr [r14]
0x1800060ad  movaps  [rbp+var_28], xmm6
0x1800060b1  mov     [rbp+var_48], r13
0x1800060b5  mov     rax, [r9]
0x1800060b8  mov     [rbp+var_40], r13
0x1800060bc  lea     r8, [rbp+var_40]
0x1800060c0  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x1800060c7  mov     rcx, r9
0x1800060ca  mov     rax, [rax]
0x1800060cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d2  mov     esi, eax
0x1800060d4  test    eax, eax
0x1800060d6  js      short loc_1800060EE
0x1800060d8  mov     rcx, [rbp+var_40]
0x1800060dc  mov     rax, [rcx]
0x1800060df  lea     rdx, [rbp+var_48]
0x1800060e3  mov     rax, [rax+18h]
0x1800060e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ec  mov     esi, eax
0x1800060ee  mov     rcx, [rbp+var_40]
0x1800060f2  test    rcx, rcx
0x1800060f5  jz      short loc_180006104
0x1800060f7  mov     rax, [rcx]
0x1800060fa  mov     rax, [rax+10h]
0x1800060fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006103  nop
0x180006104  mov     rcx, [rbp+40h]; this
0x180006108  test    esi, esi
0x18000610a  js      loc_1800064E1
0x180006110  xor     sil, sil
0x180006113  lea     rcx, ?s_inProcEndpointIdMap@UiaEndpointNotifierInProcManager@@0V?$SmartLeak@V?$ThreadSafeMap@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@@@A; _Mtx_t
0x18000611a  call    cs:__imp__Mtx_lock
0x180006120  test    eax, eax
0x180006122  jnz     loc_1800064F6
0x180006128  lea     rcx, ?s_inProcEndpointIdMap@UiaEndpointNotifierInProcManager@@0V?$SmartLeak@V?$ThreadSafeMap@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@@@A; this
0x18000612f  call    ?_Verify_ownership_levels@_Mutex_base@std@@IEAA_NXZ; std::_Mutex_base::_Verify_ownership_levels(void)
0x180006134  test    al, al
0x180006136  jz      loc_180006502
0x18000613c  lea     rdx, [rbp+var_28]
0x180006140  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x180006145  mov     r8, rax
0x180006148  lea     rdx, [rbp+var_28]
0x18000614c  lea     rcx, dword_1800C4820
0x180006153  call    ??$_Find@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Find<_GUID>(_GUID const &,unsigned __int64)
0x180006158  mov     rcx, rax
0x18000615b  mov     r15, cs:qword_1800C4828
0x180006162  cmp     rax, r15
0x180006165  jnz     loc_1800063D6
0x18000616b  movdqa  xmm0, xmm6
0x18000616f  psrldq  xmm0, 0Fh
0x180006174  movd    eax, xmm0
0x180006178  movzx   r13d, al
0x18000617c  movdqa  xmm0, xmm6
0x180006180  psrldq  xmm0, 0Eh
0x180006185  movd    eax, xmm0
0x180006189  movzx   eax, al
0x18000618c  add     r13, rax
0x18000618f  movdqa  xmm0, xmm6
0x180006193  psrldq  xmm0, 0Dh
0x180006198  movd    eax, xmm0
0x18000619c  movzx   ecx, al
0x18000619f  add     r13, rcx
0x1800061a2  movdqa  xmm0, xmm6
0x1800061a6  psrldq  xmm0, 0Ch
0x1800061ab  movd    eax, xmm0
0x1800061af  movzx   ecx, al
0x1800061b2  add     r13, rcx
0x1800061b5  movdqa  xmm0, xmm6
0x1800061b9  psrldq  xmm0, 0Bh
0x1800061be  movd    eax, xmm0
0x1800061c2  movzx   ecx, al
0x1800061c5  add     r13, rcx
0x1800061c8  movdqa  xmm0, xmm6
0x1800061cc  psrldq  xmm0, 0Ah
0x1800061d1  movd    eax, xmm0
0x1800061d5  movzx   ecx, al
0x1800061d8  add     r13, rcx
0x1800061db  movdqa  xmm0, xmm6
0x1800061df  psrldq  xmm0, 9
0x1800061e4  movd    eax, xmm0
0x1800061e8  movzx   ecx, al
0x1800061eb  add     r13, rcx
0x1800061ee  movdqa  xmm0, xmm6
0x1800061f2  psrldq  xmm0, 8
0x1800061f7  movq    r9, xmm0
0x1800061fc  movzx   eax, r9b
0x180006200  add     r13, rax
0x180006203  movzx   eax, word ptr [rbp+var_28+6]
0x180006207  add     r13, rax
0x18000620a  movzx   eax, word ptr [rbp+var_28+4]
0x18000620e  add     r13, rax
0x180006211  movq    r10, xmm6
0x180006216  mov     eax, r10d
0x180006219  add     r13, rax
0x18000621c  mov     rdx, r13
0x18000621f  and     rdx, cs:qword_1800C4850
0x180006226  add     rdx, rdx
0x180006229  mov     r8, cs:qword_1800C4838
0x180006230  mov     rcx, [r8+rdx*8+8]
0x180006235  cmp     rcx, r15
0x180006238  jz      short loc_180006260
0x18000623a  mov     rax, r10
0x18000623d  sub     rax, [rcx+10h]
0x180006241  jnz     short loc_18000624A
0x180006243  mov     rax, r9
0x180006246  sub     rax, [rcx+18h]
0x18000624a  test    rax, rax
0x18000624d  jz      loc_180006407
0x180006253  cmp     rcx, [r8+rdx*8]
0x180006257  jnz     loc_18000640F
0x18000625d  mov     r15, rcx
0x180006260  mov     rax, 666666666666666h
0x18000626a  cmp     cs:qword_1800C4830, rax
0x180006271  jz      loc_18000650E
0x180006277  mov     ecx, 28h ; '('; Size
0x18000627c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006281  mov     r12, rax
0x180006284  movups  xmmword ptr [rax+10h], xmm6
0x180006288  mov     rcx, [rbp+var_48]
0x18000628c  mov     [rbp+var_48], 0
0x180006294  mov     [rax+20h], rcx
0x180006298  mov     rcx, cs:qword_1800C4830
0x18000629f  lea     rdx, [rcx+1]
0x1800062a3  xorps   xmm0, xmm0
0x1800062a6  test    rdx, rdx
0x1800062a9  js      loc_1800064AD
0x1800062af  cvtsi2ss xmm0, rdx
0x1800062b4  mov     rdx, cs:qword_1800C4858
0x1800062bb  xorps   xmm1, xmm1
0x1800062be  test    rdx, rdx
0x1800062c1  js      loc_1800064C7
0x1800062c7  cvtsi2ss xmm1, rdx
0x1800062cc  divss   xmm0, xmm1
0x1800062d0  comiss  xmm0, cs:dword_1800C4820
0x1800062d7  ja      loc_18000651C
0x1800062dd  mov     rdx, [r15+8]
0x1800062e1  inc     rcx
0x1800062e4  mov     cs:qword_1800C4830, rcx
0x1800062eb  mov     [r12], r15
0x1800062ef  mov     [r12+8], rdx
0x1800062f4  mov     [rdx], r12
0x1800062f7  mov     [r15+8], r12
0x1800062fb  and     r13, cs:qword_1800C4850
0x180006302  add     r13, r13
0x180006305  mov     rax, cs:qword_1800C4838
0x18000630c  mov     rcx, [rax+r13*8]
0x180006310  cmp     rcx, cs:qword_1800C4828
0x180006317  jnz     loc_18000648C
0x18000631d  mov     [rax+r13*8], r12
0x180006321  mov     [rax+r13*8+8], r12
0x180006326  xor     r13d, r13d
0x180006329  lea     rcx, ?s_inProcEndpointIdMap@UiaEndpointNotifierInProcManager@@0V?$SmartLeak@V?$ThreadSafeMap@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@@@A; _Mtx_t
0x180006330  call    cs:__imp__Mtx_unlock
0x180006336  test    sil, sil
0x180006339  jz      short loc_180006351
0x18000633b  mov     rcx, [rbp+var_40]
0x18000633f  test    rcx, rcx
0x180006342  jz      short loc_180006351
0x180006344  mov     rax, [rcx]
0x180006347  mov     rax, [rax+10h]
0x18000634b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006350  nop
0x180006351  mov     rcx, [rbp+var_48]
0x180006355  test    rcx, rcx
0x180006358  jz      short loc_180006367
0x18000635a  mov     rax, [rcx]
0x18000635d  mov     rax, [rax+10h]
0x180006361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006366  nop
0x180006367  cmp     [rbx+28h], rdi
0x18000636b  jz      short loc_18000639C
0x18000636d  test    rdi, rdi
0x180006370  jz      short loc_180006382
0x180006372  mov     rax, [rdi]
0x180006375  mov     rcx, rdi
0x180006378  mov     rax, [rax+8]
0x18000637c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006381  nop
0x180006382  mov     rcx, [rbx+28h]
0x180006386  mov     [rbx+28h], rdi
0x18000638a  test    rcx, rcx
0x18000638d  jz      short loc_18000639C
0x18000638f  mov     rax, [rcx]
0x180006392  mov     rax, [rax+10h]
0x180006396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639b  nop
0x18000639c  movups  xmm0, xmmword ptr [r14]
0x1800063a0  movups  xmmword ptr [rbx+30h], xmm0
0x1800063a4  mov     rcx, [rbp+arg_18]
0x1800063a8  test    rcx, rcx
0x1800063ab  jz      short loc_1800063BE
0x1800063ad  mov     [rbp+arg_18], r13
0x1800063b1  mov     rax, [rcx]
0x1800063b4  mov     rax, [rax+10h]
0x1800063b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063bd  nop
0x1800063be  xor     eax, eax
0x1800063c0  movaps  xmm6, [rsp+78h+var_18]
0x1800063c5  add     rsp, 78h
0x1800063c9  pop     r15
0x1800063cb  pop     r14
0x1800063cd  pop     r13
0x1800063cf  pop     r12
0x1800063d1  pop     rdi
0x1800063d2  pop     rsi
0x1800063d3  pop     rbx
0x1800063d4  pop     rbp
0x1800063d5  retn
0x1800063d6  mov     rax, [rax+20h]
0x1800063da  mov     [rcx+20h], r13
0x1800063de  mov     [rbp+var_40], rax
0x1800063e2  mov     sil, 1
0x1800063e5  mov     rax, [rbp+var_48]
0x1800063e9  mov     [rbp+var_48], r13
0x1800063ed  mov     rdx, [rcx+20h]
0x1800063f1  mov     [rcx+20h], rax
0x1800063f5  test    rdx, rdx
0x1800063f8  jnz     loc_18000654F
0x1800063fe  jmp     loc_180006329
0x180006403  mov     [rax+r13*8], r12
0x180006407  xor     r13d, r13d
0x18000640a  jmp     loc_180006329
0x18000640f  mov     rcx, [rcx+8]
0x180006413  jmp     loc_18000623A
0x180006418  mov     rcx, [rbp+40h]; this
0x18000641c  mov     r9d, esi; char *
0x18000641f  lea     r8, aOnecoreWindows_8; "onecore\\windows\\accessibletech\\uiama"...
0x180006426  mov     edx, 1Dh; void *
0x18000642b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006430  nop
0x180006431  mov     rcx, [rbp+arg_18]
0x180006435  test    rcx, rcx
0x180006438  jz      short loc_18000644B
0x18000643a  mov     [rbp+arg_18], r13
0x18000643e  mov     rax, [rcx]
0x180006441  mov     rax, [rax+10h]
0x180006445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000644a  nop
0x18000644b  mov     eax, esi
0x18000644d  jmp     loc_1800063C0
0x180006452  mov     rcx, [rbp+40h]; this
0x180006456  mov     r9d, esi; char *
0x180006459  lea     r8, aOnecoreWindows_8; "onecore\\windows\\accessibletech\\uiama"...
  ... truncated ...
```
