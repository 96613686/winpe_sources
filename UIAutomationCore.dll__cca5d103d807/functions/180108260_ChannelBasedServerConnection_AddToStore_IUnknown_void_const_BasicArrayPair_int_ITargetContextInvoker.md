# ChannelBasedServerConnection::AddToStore(IUnknown *,void const *,BasicArrayPair<int> *,ITargetContextInvoker *)

- ea: `0x180108260`
- end: `0x1801087df`
- name: `?AddToStore@ChannelBasedServerConnection@@UEAAHPEAUIUnknown@@PEBXPEAU?$BasicArrayPair@H@@PEAUITargetContextInvoker@@@Z`
- size: `1407`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002f580`
- `0x180032724`
- `0x1800c2068`
- `0x180108260`
- `0x1801087e8`
- `0x180108838`
- `0x180108960`
- `0x180108d84`
- `0x180108e28`
- `0x1801e8380`
- `0x1801e88a0`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1801087c7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1801087c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801083dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801083dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18010854d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18010854d`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1801085f3`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1801085f3`

## string_xrefs

- `0x1801086ec`: `onecore\windows\accessibletech\uiautomationcore\BulkFetch.h`
- `0x180108575`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1801086b8`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1801087a3`: `onecore\windows\accessibletech\uiautomationcore\serverconnection.cpp`
- `0x1801086d0`: `onecore\windows\accessibletech\uiautomationcore\objectreferencemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ChannelBasedServerConnection::AddToStore(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned int *a4,
        __int64 a5)
{
  volatile signed __int64 *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // r12
  int *v13; // rsi
  _QWORD *v14; // rdi
  unsigned int v15; // ebx
  __int64 v16; // r15
  unsigned __int64 v17; // rax
  _DWORD *v18; // r8
  __int64 i; // rdx
  void *v20; // rbx
  int v21; // eax
  int *v22; // r13
  int v23; // r9d
  __int64 v24; // rdx
  unsigned __int64 j; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 *v28; // rcx
  int *v29; // rax
  __int64 *v30; // r15
  _DWORD *v31; // rsi
  __int64 v32; // rdx
  float v33; // xmm0_4
  __int64 v34; // rcx
  float v35; // xmm1_4
  __int64 v36; // r8
  _QWORD *v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 *v40; // r8
  unsigned int v41; // ebx
  int v42; // eax
  signed __int64 v43; // rcx
  signed __int32 v44; // r8d
  signed __int64 v45; // r8
  bool v47; // zf
  signed __int64 v48; // rax
  volatile signed __int64 **v49; // rax
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rax
  __int64 v53; // r9
  __int64 *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // [rsp+20h] [rbp-40h] BYREF
  volatile signed __int64 *v57; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v58[4]; // [rsp+30h] [rbp-30h] BYREF
  _DWORD *v59; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 ThreadDpiAwarenessContext; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v62; // [rsp+A8h] [rbp+48h] BYREF

  v62 = a2;
  if ( !*(_QWORD *)(a1 + 144) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x372,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
      (const char *)0x8000FFFFLL,
      v56);
  v9 = 0;
  v57 = 0;
  if ( a3 == &NodeMarker )
  {
    wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(&v56, &v62);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 32LL))(v56);
    if ( !v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
        (const char *)0x8000FFFFLL,
        v56);
    v11 = a2;
    v12 = *(_QWORD *)(v10 + 264);
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  else
  {
    ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext(retaddr);
    v49 = (volatile signed __int64 **)MakeCom<PatternUnkWrapper,IUnknown * &,DPI_AWARENESS_CONTEXT__ *>(
                                        v58,
                                        &v62,
                                        &ThreadDpiAwarenessContext);
    v9 = *v49;
    *v49 = 0;
    v57 = v9;
    if ( v58[0] )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IPatternUnkWrapper>::Release();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 8LL))(v62);
    wil::com_ptr_t<PatternUnkWrapper,wil::err_exception_policy>::query<IUnknown>(&v57, &ThreadDpiAwarenessContext);
    v11 = ThreadDpiAwarenessContext;
    if ( ThreadDpiAwarenessContext )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)ThreadDpiAwarenessContext + 16LL))(ThreadDpiAwarenessContext);
    v12 = a5;
  }
  v13 = *(int **)(a1 + 144);
  if ( !v13[20] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\objectreferencemanager.cpp",
      (const char *)0x80004005LL,
      v56);
  v14 = operator new(0x40u);
  ThreadDpiAwarenessContext = (__int64)v14;
  *v14 = 0;
  v14[1] = 0;
  v14[2] = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  *((_DWORD *)v14 + 6) = 0;
  v14[4] = a3;
  v14[5] = v12;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  *((_DWORD *)v14 + 12) = 0;
  v14[7] = 0;
  if ( a4 )
  {
    v15 = *a4;
    v16 = *((_QWORD *)a4 + 1);
    v17 = 4LL * *a4;
    if ( !is_mul_ok(*a4, 4u) )
      v17 = -1;
    v18 = operator new[](v17, (const struct std::nothrow_t *)std::nothrow);
    if ( v18 )
    {
      for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
        v18[i] = *(_DWORD *)(v16 + 4 * i);
      v14[7] = v18;
      *((_DWORD *)v14 + 12) = v15;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\BulkFetch.h",
        (const char *)0x8007000ELL,
        v56);
    }
  }
  WaitForSingleObject(*((HANDLE *)v13 + 9), 0xFFFFFFFF);
  v20 = (void *)*((_QWORD *)v13 + 9);
  v58[2] = v20;
  *((_DWORD *)v14 + 6) = *v13;
  v21 = *v13;
  if ( *v13 == 0x7FFFFFFF )
  {
    *v13 = 0x80000000;
  }
  else
  {
    *v13 = v21 + 1;
    if ( v21 == -1 )
      *v13 = 1;
  }
  v22 = v13 + 2;
  v23 = *((_DWORD *)v14 + 6);
  LODWORD(ThreadDpiAwarenessContext) = v23;
  LODWORD(v58[0]) = v23;
  v58[1] = v14;
  v24 = 0xCBF29CE484222325uLL;
  for ( j = 0; j < 4; ++j )
    v24 = 0x100000001B3LL * (*((unsigned __int8 *)v58 + j) ^ (unsigned __int64)v24);
  v58[0] = v24;
  v26 = *((_QWORD *)v13 + 7) & v24;
  v27 = *((_QWORD *)v13 + 4);
  v28 = *(__int64 **)(v27 + 16 * v26 + 8);
  v29 = v13 + 4;
  v30 = (__int64 *)*((_QWORD *)v13 + 2);
  if ( v28 != v30 )
  {
    while ( v23 != *((_DWORD *)v28 + 4) )
    {
      if ( v28 == *(__int64 **)(v27 + 16 * v26) )
      {
        v30 = v28;
        v29 = v13 + 4;
        goto LABEL_29;
      }
      v28 = (__int64 *)v28[1];
    }
    goto LABEL_39;
  }
LABEL_29:
  if ( *((_QWORD *)v13 + 3) == 0x7FFFFFFFFFFFFFFLL )
    std::_Xlength_error("unordered_map/set too long");
  v58[3] = v29;
  v59 = 0;
  v31 = operator new(0x20u);
  v59 = v31;
  v31[4] = ThreadDpiAwarenessContext;
  *((_QWORD *)v31 + 3) = v14;
  v32 = *((_QWORD *)v22 + 2) + 1LL;
  if ( v32 < 0 )
    v33 = (float)(v32 & 1 | (unsigned int)((unsigned __int64)v32 >> 1))
        + (float)(v32 & 1 | (unsigned int)((unsigned __int64)v32 >> 1));
  else
    v33 = (float)(int)v32;
  v34 = *((_QWORD *)v22 + 7);
  if ( v34 < 0 )
  {
    v55 = *((_QWORD *)v22 + 7) & 1LL | ((unsigned __int64)v34 >> 1);
    v35 = (float)(int)v55 + (float)(int)v55;
  }
  else
  {
    v35 = (float)(int)v34;
  }
  if ( (float)(v33 / v35) > *(float *)v22 )
  {
    v52 = std::_Hash<std::_Umap_traits<int,ObjectReferenceManager::Item *,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,ObjectReferenceManager::Item *>>,0>>::_Desired_grow_bucket_count(v22);
    std::_Hash<std::_Umap_traits<int,ObjectReferenceManager::Item *,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,ObjectReferenceManager::Item *>>,0>>::_Forced_rehash(
      v22,
      v52);
    v36 = v58[0];
    v53 = *((_QWORD *)v22 + 3);
    v54 = *(__int64 **)(v53 + 16LL * (*((_QWORD *)v22 + 6) & v58[0]) + 8);
    v30 = (__int64 *)*((_QWORD *)v22 + 1);
    if ( v54 != v30 )
    {
      while ( 1 )
      {
        if ( v31[4] == *((_DWORD *)v54 + 4) )
        {
          v30 = (__int64 *)*v54;
          goto LABEL_36;
        }
        if ( v54 == *(__int64 **)(v53 + 16LL * (*((_QWORD *)v22 + 6) & v58[0])) )
          break;
        v54 = (__int64 *)v54[1];
      }
      v30 = v54;
    }
  }
  else
  {
    v36 = v58[0];
  }
LABEL_36:
  v37 = (_QWORD *)v30[1];
  ++*((_QWORD *)v22 + 2);
  *(_QWORD *)v31 = v30;
  *((_QWORD *)v31 + 1) = v37;
  *v37 = v31;
  v30[1] = (__int64)v31;
  v38 = *((_QWORD *)v22 + 3);
  v39 = 2 * (v36 & *((_QWORD *)v22 + 6));
  v40 = *(__int64 **)(v38 + 16 * (v36 & *((_QWORD *)v22 + 6)));
  if ( v40 == *((__int64 **)v22 + 1) )
  {
    *(_QWORD *)(v38 + 8 * v39) = v31;
    goto LABEL_38;
  }
  if ( v40 == v30 )
  {
    *(_QWORD *)(v38 + 8 * v39) = v31;
    goto LABEL_39;
  }
  if ( *(_QWORD **)(v38 + 8 * v39 + 8) == v37 )
LABEL_38:
    *(_QWORD *)(v38 + 8 * v39 + 8) = v31;
LABEL_39:
  if ( v20 )
    ReleaseMutex(v20);
  v41 = *((_DWORD *)v14 + 6);
  v42 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 32LL))(v12, v62);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x391,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\serverconnection.cpp",
      (const char *)(unsigned int)v42,
      v56);
  if ( v9 )
  {
    v43 = *((_QWORD *)v9 + 8);
    while ( v43 >= 0 )
    {
      if ( (_DWORD)v43 == 0x7FFFFFFF )
        return v41;
      v45 = v43 - 1;
      v48 = _InterlockedCompareExchange64(v9 + 8, v43 - 1, v43);
      v47 = v43 == v48;
      v43 = v48;
      if ( v47 )
        goto LABEL_49;
    }
    do
      v44 = *(_DWORD *)(2 * v43 + 0x10);
    while ( v44 != 0x7FFFFFFF
         && v44 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v43 + 16), v44 - 1, v44) );
    v45 = (unsigned int)(v44 - 1);
LABEL_49:
    if ( !(_DWORD)v45 )
    {
      (*(void (__fastcall **)(volatile signed __int64 *, __int64, signed __int64, __int64))(*v9 + 48))(
        v9,
        1,
        v45,
        0x7FFFFFFF);
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
          Microsoft::WRL::Details::ModuleBase::module_,
          *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
          v50,
          v51);
    }
  }
  return v41;
}

```

## disassembly

```asm
0x180108260  mov     [rsp-38h+arg_10], rbx
0x180108265  mov     [rsp-38h+arg_8], rdx
0x18010826a  push    rbp
0x18010826b  push    rsi
0x18010826c  push    rdi
0x18010826d  push    r12
0x18010826f  push    r13
0x180108271  push    r14
0x180108273  push    r15
0x180108275  mov     rbp, rsp
0x180108278  sub     rsp, 60h
0x18010827c  mov     r13, r9
0x18010827f  mov     r15, r8
0x180108282  mov     rdi, rdx
0x180108285  mov     rsi, rcx
0x180108288  xor     r12d, r12d
0x18010828b  mov     rcx, [rbp+38h]; this
0x18010828f  cmp     [rsi+90h], r12
0x180108296  jz      loc_1801086B2
0x18010829c  mov     r14d, r12d
0x18010829f  mov     [rbp+var_38], r12
0x1801082a3  lea     rax, ?NodeMarker@@3HA; int NodeMarker
0x1801082aa  cmp     r8, rax
0x1801082ad  jnz     loc_1801085F3
0x1801082b3  lea     rdx, [rbp+arg_8]
0x1801082b7  lea     rcx, [rbp+var_40]
0x1801082bb  call    ??$com_query@VIUiaNode@@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@wil@@YA?AV?$com_ptr_t@VIUiaNode@@Uerr_exception_policy@wil@@@0@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Z; wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(Microsoft::WRL::ComPtr<IUnknown> &)
0x1801082c0  nop
0x1801082c1  mov     rcx, [rbp+var_40]
0x1801082c5  mov     rax, [rcx]
0x1801082c8  mov     rax, [rax+20h]
0x1801082cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801082d1  mov     rcx, [rbp+38h]; this
0x1801082d5  test    rax, rax
0x1801082d8  jz      loc_18010879D
0x1801082de  mov     rbx, rdi
0x1801082e1  mov     r12, [rax+108h]
0x1801082e8  mov     rcx, [rbp+var_40]
0x1801082ec  test    rcx, rcx
0x1801082ef  jz      short loc_1801082FE
0x1801082f1  mov     rax, [rcx]
0x1801082f4  mov     rax, [rax+10h]
0x1801082f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801082fd  nop
0x1801082fe  mov     rsi, [rsi+90h]
0x180108305  mov     rcx, [rbp+38h]; this
0x180108309  cmp     dword ptr [rsi+50h], 0
0x18010830d  jz      loc_1801086CA
0x180108313  mov     ecx, 40h ; '@'; Size
0x180108318  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010831d  mov     rdi, rax
0x180108320  mov     [rbp+arg_0], rax
0x180108324  mov     qword ptr [rax], 0
0x18010832b  mov     qword ptr [rax+8], 0
0x180108333  mov     [rax+10h], rbx
0x180108337  test    rbx, rbx
0x18010833a  jz      short loc_18010834C
0x18010833c  mov     rdx, [rbx]
0x18010833f  mov     rcx, rbx
0x180108342  mov     rax, [rdx+8]
0x180108346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010834b  nop
0x18010834c  mov     dword ptr [rdi+18h], 0
0x180108353  mov     [rdi+20h], r15
0x180108357  mov     [rdi+28h], r12
0x18010835b  test    r12, r12
0x18010835e  jz      short loc_180108371
0x180108360  mov     rax, [r12]
0x180108364  mov     rcx, r12
0x180108367  mov     rax, [rax+8]
0x18010836b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108370  nop
0x180108371  mov     dword ptr [rdi+30h], 0
0x180108378  mov     qword ptr [rdi+38h], 0
0x180108380  test    r13, r13
0x180108383  jz      short loc_1801083D6
0x180108385  mov     ebx, [r13+0]
0x180108389  mov     r15, [r13+8]
0x18010838d  mov     eax, 4
0x180108392  mul     rbx
0x180108395  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010839c  cmovb   rax, rcx
0x1801083a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801083a7  mov     rcx, rax; unsigned __int64
0x1801083aa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801083af  mov     r8, rax
0x1801083b2  test    rax, rax
0x1801083b5  jz      loc_1801086E2
0x1801083bb  xor     edx, edx
0x1801083bd  test    ebx, ebx
0x1801083bf  jz      short loc_1801083CF
0x1801083c1  mov     eax, [r15+rdx*4]
0x1801083c5  mov     [r8+rdx*4], eax
0x1801083c9  inc     edx
0x1801083cb  cmp     edx, ebx
0x1801083cd  jb      short loc_1801083C1
0x1801083cf  mov     [rdi+38h], r8
0x1801083d3  mov     [rdi+30h], ebx
0x1801083d6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801083d9  mov     rcx, [rsi+48h]; hHandle
0x1801083dd  call    cs:__imp_WaitForSingleObject
0x1801083e3  mov     rbx, [rsi+48h]
0x1801083e7  mov     [rbp+var_20], rbx
0x1801083eb  mov     eax, [rsi]
0x1801083ed  mov     [rdi+18h], eax
0x1801083f0  mov     eax, [rsi]
0x1801083f2  cmp     eax, 7FFFFFFFh
0x1801083f7  jnz     short loc_180108401
0x1801083f9  mov     dword ptr [rsi], 80000000h
0x1801083ff  jmp     short loc_18010840C
0x180108401  add     eax, 1
0x180108404  mov     [rsi], eax
0x180108406  jz      loc_1801087B5
0x18010840c  lea     r13, [rsi+8]
0x180108410  mov     r9d, [rdi+18h]
0x180108414  mov     dword ptr [rbp+arg_0], r9d
0x180108418  mov     dword ptr [rbp+var_30], r9d
0x18010841c  mov     [rbp+var_28], rdi
0x180108420  mov     rdx, 0CBF29CE484222325h
0x18010842a  xor     ecx, ecx
0x18010842c  movzx   eax, byte ptr [rbp+rcx+var_30]
0x180108431  xor     rdx, rax
0x180108434  mov     r8, 100000001B3h
0x18010843e  imul    rdx, r8
0x180108442  inc     rcx
0x180108445  cmp     rcx, 4
0x180108449  jb      short loc_18010842C
0x18010844b  mov     [rbp+var_30], rdx
0x18010844f  and     rdx, [r13+30h]
0x180108453  mov     r8, [r13+18h]
0x180108457  mov     rax, rdx
0x18010845a  add     rax, rax
0x18010845d  mov     rcx, [r8+rax*8+8]
0x180108462  lea     rax, [r13+8]
0x180108466  mov     r15, [rax]
0x180108469  cmp     rcx, r15
0x18010846c  jz      short loc_180108491
0x18010846e  add     rdx, rdx
0x180108471  mov     rax, [r8+rdx*8]
0x180108475  cmp     r9d, [rcx+10h]
0x180108479  jz      loc_180108545
0x18010847f  cmp     rcx, rax
0x180108482  jz      short loc_18010848A
0x180108484  mov     rcx, [rcx+8]
0x180108488  jmp     short loc_180108475
0x18010848a  mov     r15, rcx
0x18010848d  lea     rax, [r13+8]
0x180108491  mov     rcx, 7FFFFFFFFFFFFFFh
0x18010849b  cmp     [r13+10h], rcx
0x18010849f  jz      loc_1801087C0
0x1801084a5  mov     [rbp+var_18], rax
0x1801084a9  mov     [rbp+var_10], 0
0x1801084b1  mov     ecx, 20h ; ' '; Size
0x1801084b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801084bb  mov     rsi, rax
0x1801084be  mov     [rbp+var_10], rax
0x1801084c2  mov     eax, dword ptr [rbp+arg_0]
0x1801084c5  mov     [rsi+10h], eax
0x1801084c8  mov     [rsi+18h], rdi
0x1801084cc  mov     rdx, [r13+10h]
0x1801084d0  add     rdx, 1
0x1801084d4  xorps   xmm0, xmm0
0x1801084d7  js      loc_180108766
0x1801084dd  cvtsi2ss xmm0, rdx
0x1801084e2  mov     rcx, [r13+38h]
0x1801084e6  xorps   xmm1, xmm1
0x1801084e9  test    rcx, rcx
0x1801084ec  js      loc_180108783
0x1801084f2  cvtsi2ss xmm1, rcx
0x1801084f7  divss   xmm0, xmm1
0x1801084fb  comiss  xmm0, dword ptr [r13+0]
0x180108500  ja      loc_180108702
0x180108506  mov     r8, [rbp+var_30]
0x18010850a  mov     rdx, [r15+8]
0x18010850e  inc     qword ptr [r13+10h]
0x180108512  mov     [rsi], r15
0x180108515  mov     [rsi+8], rdx
0x180108519  mov     [rdx], rsi
0x18010851c  mov     [r15+8], rsi
0x180108520  mov     rcx, [r13+18h]
0x180108524  mov     rax, [r13+30h]
0x180108528  and     rax, r8
0x18010852b  add     rax, rax
0x18010852e  mov     r8, [rcx+rax*8]
0x180108532  cmp     r8, [r13+8]
0x180108536  jnz     loc_180108666
0x18010853c  mov     [rcx+rax*8], rsi
0x180108540  mov     [rcx+rax*8+8], rsi
0x180108545  test    rbx, rbx
0x180108548  jz      short loc_180108553
0x18010854a  mov     rcx, rbx; hMutex
0x18010854d  call    cs:__imp_ReleaseMutex
0x180108553  mov     ebx, [rdi+18h]
0x180108556  mov     rax, [r12]
0x18010855a  mov     rdx, [rbp+arg_8]
0x18010855e  mov     rcx, r12
0x180108561  mov     rax, [rax+20h]
0x180108565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010856a  mov     rcx, [rbp+38h]; this
0x18010856e  test    eax, eax
0x180108570  jns     short loc_180108587
0x180108572  mov     r9d, eax; char *
0x180108575  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x18010857c  mov     edx, 391h; void *
0x180108581  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180108587  test    r14, r14
0x18010858a  jz      short loc_1801085C0
0x18010858c  mov     rcx, [r14+40h]
0x180108590  mov     r9d, 7FFFFFFFh
0x180108596  test    rcx, rcx
0x180108599  jns     short loc_1801085DA
0x18010859b  mov     r8d, [rcx+rcx+10h]
0x1801085a0  cmp     r8d, r9d
0x1801085a3  jz      short loc_1801085B4
0x1801085a5  lea     edx, [r8-1]
0x1801085a9  mov     eax, r8d
0x1801085ac  lock cmpxchg [rcx+rcx+10h], edx
0x1801085b2  jnz     short loc_18010859B
0x1801085b4  dec     r8d
0x1801085b7  test    r8d, r8d
0x1801085ba  jz      loc_180108678
0x1801085c0  mov     eax, ebx
0x1801085c2  mov     rbx, [rsp+60h+arg_10]
0x1801085ca  add     rsp, 60h
0x1801085ce  pop     r15
0x1801085d0  pop     r14
0x1801085d2  pop     r13
0x1801085d4  pop     r12
0x1801085d6  pop     rdi
0x1801085d7  pop     rsi
0x1801085d8  pop     rbp
0x1801085d9  retn
0x1801085da  cmp     ecx, r9d
0x1801085dd  jz      short loc_1801085C0
0x1801085df  lea     r8, [rcx-1]
0x1801085e3  mov     rax, rcx
0x1801085e6  lock cmpxchg [r14+40h], r8
0x1801085ec  mov     rcx, rax
0x1801085ef  jz      short loc_1801085B7
0x1801085f1  jmp     short loc_180108596
0x1801085f3  call    cs:__imp_GetThreadDpiAwarenessContext
0x1801085f9  nop
0x1801085fa  mov     [rbp+arg_0], rax
0x1801085fe  lea     r8, [rbp+arg_0]
0x180108602  lea     rdx, [rbp+arg_8]
0x180108606  lea     rcx, [rbp+var_30]
0x18010860a  call    ??$MakeCom@VPatternUnkWrapper@@AEAPEAUIUnknown@@PEAUDPI_AWARENESS_CONTEXT__@@@@YA?AV?$com_ptr_t@VPatternUnkWrapper@@Uerr_exception_policy@wil@@@wil@@AEAPEAUIUnknown@@$$QEAPEAUDPI_AWARENESS_CONTEXT__@@@Z; MakeCom<PatternUnkWrapper,IUnknown * &,DPI_AWARENESS_CONTEXT__ *>(IUnknown * &,DPI_AWARENESS_CONTEXT__ * &&)
0x18010860f  mov     r14, [rax]
0x180108612  mov     [rax], r12
0x180108615  mov     [rbp+var_38], r14
0x180108619  mov     rcx, [rbp+var_30]
0x18010861d  test    rcx, rcx
0x180108620  jz      short loc_180108627
0x180108622  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@VIPatternUnkWrapper@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IPatternUnkWrapper>::Release(void)
0x180108627  mov     rcx, [rbp+arg_8]
0x18010862b  mov     rax, [rcx]
0x18010862e  mov     rax, [rax+8]
0x180108632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108637  lea     rdx, [rbp+arg_0]
0x18010863b  lea     rcx, [rbp+var_38]
0x18010863f  call    ??$query@UIUnknown@@@?$com_ptr_t@VPatternUnkWrapper@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<PatternUnkWrapper,wil::err_exception_policy>::query<IUnknown>(void)
0x180108644  mov     rbx, [rbp+arg_0]
0x180108648  test    rbx, rbx
0x18010864b  jz      short loc_18010865D
0x18010864d  mov     rax, [rbx]
0x180108650  mov     rcx, rbx
0x180108653  mov     rax, [rax+10h]
0x180108657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010865c  nop
0x18010865d  mov     r12, [rbp+arg_20]
0x180108661  jmp     loc_1801082FE
0x180108666  cmp     r8, r15
0x180108669  jnz     loc_1801087CE
0x18010866f  mov     [rcx+rax*8], rsi
0x180108673  jmp     loc_180108545
0x180108678  test    r14, r14
0x18010867b  jz      short loc_180108691
0x18010867d  mov     rax, [r14]
0x180108680  mov     edx, 1
0x180108685  mov     rcx, r14
0x180108688  mov     rax, [rax+30h]
0x18010868c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108691  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180108698  test    rcx, rcx
0x18010869b  jz      loc_1801085C0
0x1801086a1  mov     rdx, [rcx]
0x1801086a4  mov     rax, [rdx+10h]
0x1801086a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801086ad  jmp     loc_1801085C0
0x1801086b2  mov     r9d, 8000FFFFh; char *
0x1801086b8  lea     r8, aOnecoreWindows_115; "onecore\\windows\\accessibletech\\uiaut"...
0x1801086bf  mov     edx, 372h; void *
0x1801086c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801086ca  mov     r9d, 80004005h; char *
0x1801086d0  lea     r8, aOnecoreWindows_50; "onecore\\windows\\accessibletech\\uiaut"...
0x1801086d7  mov     edx, 48h ; 'H'; void *
0x1801086dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801086e2  mov     rcx, [rbp+38h]; this
0x1801086e6  mov     r9d, 8007000Eh; char *
0x1801086ec  lea     r8, aOnecoreWindows_159; "onecore\\windows\\accessibletech\\uiaut"...
  ... truncated ...
```
