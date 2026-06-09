# CBroker::SebBroker::DeleteEvent(Broker::ApplicationIdentity const &,_GUID const &,bool,bool)

- ea: `0x18000b3d0`
- end: `0x18000bb46`
- name: `?DeleteEvent@SebBroker@CBroker@@QEAAXAEBUApplicationIdentity@Broker@@AEBU_GUID@@_N2@Z`
- size: `1910`
- prototype: `void __fastcall(CBroker::SebBroker *this, void **, struct _GUID *)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009740`
- `0x18000a7d0`
- `0x18001fd50`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x180008c00`
- `0x18000b168`
- `0x18000b3d0`
- `0x18000c0b0`
- `0x18000c3a0`
- `0x18000c910`
- `0x18000cb50`
- `0x180013820`
- `0x180013920`
- `0x180013f60`
- `0x180019130`
- `0x180019340`
- `0x18001a99c`
- `0x18001ab64`
- `0x18001c00c`
- `0x18001cf50`
- `0x18001d364`
- `0x18001d9ac`
- `0x18001e0d8`
- `0x180022434`
- `0x18002244c`
- `0x180027010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ba63`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ba63`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b417`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b417`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b7b4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b8dc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b7b4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b8dc`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b59e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18000b59e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b41d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b41d`

## pseudocode

```c
void __fastcall CBroker::SebBroker::DeleteEvent(CBroker::SebBroker *this, void **a2, struct _GUID *a3)
{
  struct _GUID *v3; // rsi
  char v6; // r12
  char *v7; // r14
  size_t v8; // rsi
  char *v9; // rbx
  unsigned __int64 v10; // rdx
  size_t v11; // r15
  unsigned __int64 v12; // rcx
  void *v13; // rcx
  char *v14; // rdx
  _QWORD *v15; // rdx
  _QWORD *v16; // rdx
  const WCHAR *lpString2; // rax
  CBroker::SebEvent *v18; // rdi
  const WCHAR *v19; // r8
  int v20; // eax
  void *v21; // rbx
  const void *v22; // rcx
  size_t v23; // r8
  struct _RTL_SRWLOCK **ApplicationState; // rax
  struct _RTL_SRWLOCK *v25; // rdi
  volatile signed __int32 *v26; // r15
  volatile signed __int32 *v27; // rbx
  int *v28; // rsi
  __int64 v29; // rbx
  volatile signed __int32 *v30; // rdi
  __int64 *v31; // r12
  __int64 *v32; // rbx
  __int64 *v33; // r13
  char v34; // cl
  __int64 *v35; // rax
  _QWORD *v36; // rbx
  std::_Ref_count_base *v37; // rcx
  volatile signed __int32 *v38; // rbx
  char *v39; // rbx
  _QWORD *v40; // rcx
  void *v41; // rcx
  signed __int64 v42; // r15
  __int64 *v43; // rax
  void *v44; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v46; // [rsp+60h] [rbp-A0h] BYREF
  char *v47; // [rsp+70h] [rbp-90h]
  char v48; // [rsp+78h] [rbp-88h]
  DWORD CurrentThreadId; // [rsp+7Ch] [rbp-84h]
  CBroker::SebEvent *v50[2]; // [rsp+80h] [rbp-80h] BYREF
  void **pExceptionObject; // [rsp+90h] [rbp-70h] BYREF
  __int128 v52; // [rsp+98h] [rbp-68h]
  int v53; // [rsp+A8h] [rbp-58h]
  __int128 v54; // [rsp+B0h] [rbp-50h]
  void *Buf2[2]; // [rsp+C0h] [rbp-40h] BYREF
  char *v56; // [rsp+D0h] [rbp-30h]
  LPCWCH v57[2]; // [rsp+D8h] [rbp-28h] BYREF
  int cchCount2[2]; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v59; // [rsp+F0h] [rbp-10h]
  __int64 v60[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v61; // [rsp+108h] [rbp+8h]
  unsigned __int64 v62; // [rsp+110h] [rbp+10h]

  v3 = a3;
  v44 = a3;
  v47 = (char *)this + 8;
  RtlAcquireSRWLockExclusive((char *)this + 8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = 1;
  v48 = 1;
  v54 = 0;
  std::vector<_GUID>::vector<_GUID>(Buf2);
  *(_OWORD *)v57 = 0;
  *(_QWORD *)cchCount2 = 0;
  v59 = 0;
  std::wstring::_Construct_empty((__int64)v57);
  *(_OWORD *)v60 = 0;
  v61 = 0;
  v62 = 0;
  std::wstring::_Construct_empty((__int64)v60);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, v3);
  if ( Buf2 != a2 )
  {
    v7 = (char *)*a2;
    v8 = (_BYTE *)a2[1] - (_BYTE *)*a2;
    v9 = (char *)Buf2[0];
    v10 = v56 - (char *)Buf2[0];
    if ( v8 <= v56 - (char *)Buf2[0] )
    {
      v42 = (char *)Buf2[1] - (char *)Buf2[0];
      v13 = Buf2[0];
      if ( v8 > (char *)Buf2[1] - (char *)Buf2[0] )
      {
        memmove_0(Buf2[0], *a2, (char *)Buf2[1] - (char *)Buf2[0]);
        v9 = (char *)Buf2[1];
        v8 -= v42;
        v14 = &v7[v42];
        v13 = Buf2[1];
        goto LABEL_12;
      }
    }
    else
    {
      v11 = 0x7FFFFFFFFFFFFFFFLL;
      if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      v12 = v10 >> 1;
      if ( v10 <= 0x7FFFFFFFFFFFFFFFLL - (v10 >> 1) )
      {
        v11 = v12 + v10;
        if ( v12 + v10 < v8 )
          v11 = (_BYTE *)a2[1] - (_BYTE *)*a2;
      }
      if ( Buf2[0] )
      {
        std::_Deallocate<16>(Buf2[0], v10);
        *(_OWORD *)Buf2 = 0;
        v56 = 0;
      }
      v9 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v11);
      Buf2[0] = v9;
      Buf2[1] = v9;
      v56 = &v9[v11];
      v13 = v9;
    }
    v14 = v7;
LABEL_12:
    memmove_0(v13, v14, v8);
    Buf2[1] = &v9[v8];
    v3 = (struct _GUID *)v44;
  }
  v15 = a2 + 3;
  if ( v57 != (LPCWCH *)(a2 + 3) )
  {
    if ( (unsigned __int64)a2[6] > 7 )
      v15 = (_QWORD *)*v15;
    std::wstring::assign(v57, v15, a2[5]);
  }
  v16 = a2 + 7;
  if ( v60 != (__int64 *)(a2 + 7) )
  {
    if ( (unsigned __int64)a2[10] > 7 )
      v16 = (_QWORD *)*v16;
    std::wstring::assign(v60, v16, a2[9]);
  }
  v44 = (char *)this + 16;
  Broker::BrokerEventTable<CBroker::SebEvent>::Find((char *)this + 16, v50, v3);
  lpString2 = (const WCHAR *)v57;
  if ( v59 > 7 )
    lpString2 = v57[0];
  v18 = v50[0];
  v19 = (const WCHAR *)((char *)v50[0] + 32);
  if ( *((_QWORD *)v50[0] + 7) > 7u )
    v19 = *(const WCHAR **)v19;
  v20 = CompareStringEx(&LocaleName, 1u, v19, *((_DWORD *)v50[0] + 12), lpString2, cchCount2[0], 0, 0, 0);
  v21 = Buf2[0];
  if ( v20 != 2
    || (v22 = (const void *)*((_QWORD *)v18 + 1),
        v23 = *((_QWORD *)v18 + 2) - (_QWORD)v22,
        v23 < (char *)Buf2[1] - (char *)Buf2[0])
    || v23 > (char *)Buf2[1] - (char *)Buf2[0]
    || memcmp_0(v22, Buf2[0], v23) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v43 = v60;
      if ( v62 > 7 )
        v43 = (__int64 *)v60[0];
      WPP_SF__guid__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, (__int64)v43);
    }
    v52 = 0;
    v53 = 5;
    pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&pExceptionObject;
  }
  ApplicationState = (struct _RTL_SRWLOCK **)Broker::ApplicationStateTable::FindApplicationState(
                                               *((_QWORD *)this + 4),
                                               &v46,
                                               Buf2);
  v25 = *ApplicationState;
  v26 = (volatile signed __int32 *)ApplicationState[1];
  *ApplicationState = 0;
  ApplicationState[1] = 0;
  *(_QWORD *)&v54 = v25;
  *((_QWORD *)&v54 + 1) = v26;
  v27 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
  if ( *((_QWORD *)&v46 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  v28 = (int *)v50[0];
  v29 = 4LL * (unsigned int)(*((_DWORD *)v50[0] + 24) - 4096);
  if ( *(_DWORD *)((char *)v25[11].Ptr + v29) != -1 )
  {
    Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)&v46, v25 + 18, 1);
    --*(_DWORD *)((char *)v25[14].Ptr + v29);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v46);
  }
  v30 = (volatile signed __int32 *)v50[1];
  if ( (byte_180035F64[40 * v28[24] - 163840] & 1) != 0
    && (int)CBroker::SebEvent::DecRefCount((CBroker::SebEvent *)v28) >= 1 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
      v40 = WPP_GLOBAL_Control;
    }
    v39 = v47;
  }
  else
  {
    v46 = 0;
    if ( v30 )
      _InterlockedIncrement(v30 + 2);
    *(_QWORD *)&v46 = v28;
    *((_QWORD *)&v46 + 1) = v30;
    v45 = (unsigned __int64)&v46;
    v31 = (__int64 *)*((_QWORD *)this + 2);
    v32 = (__int64 *)v31[1];
    DWORD1(v52) = 0;
    v33 = v31;
    if ( !*((_BYTE *)v32 + 25) )
    {
      do
      {
        if ( memcmp_0(v32 + 4, v28 + 30, 0x10u) >= 0 )
        {
          v34 = 0;
          v33 = v32;
        }
        else
        {
          v34 = 1;
        }
        v35 = v32 + 2;
        if ( !v34 )
          v35 = v32;
        v32 = (__int64 *)*v35;
      }
      while ( !*(_BYTE *)(*v35 + 25) );
    }
    if ( *((_BYTE *)v33 + 25) || memcmp_0(v28 + 30, v33 + 4, 0x10u) < 0 || v33 == v31 )
    {
      v52 = 0;
      v53 = 3;
      pExceptionObject = &Broker::NotFound::`vftable';
      throw (Broker::NotFound *)&pExceptionObject;
    }
    v36 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>::_Extract(
            (__int64 **)v44,
            v33);
    v37 = (std::_Ref_count_base *)v36[7];
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    operator delete(v36);
    v38 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    v39 = v47;
    RtlReleaseSRWLockExclusive(v47);
    v6 = 0;
    v48 = 0;
    CBroker::SebEvent::OnDisable(v50[0], 1);
    v40 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v40 + 28) & 1) != 0 && *((_BYTE *)v40 + 25) >= 4u )
    WPP_SF_(v40[2], 29, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  if ( v30 )
  {
    if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  if ( v62 > 7 )
    std::_Deallocate<16>((void *)v60[0], 2 * v62 + 2);
  v61 = 0;
  v62 = 7;
  LOWORD(v60[0]) = 0;
  if ( v59 > 7 )
    std::_Deallocate<16>((void *)v57[0], 2 * v59 + 2);
  *(_QWORD *)cchCount2 = 0;
  v59 = 7;
  LOWORD(v57[0]) = 0;
  v41 = Buf2[0];
  if ( Buf2[0] )
  {
    v45 = v56 - (char *)Buf2[0];
    v44 = Buf2[0];
    if ( (unsigned __int64)(v56 - (char *)Buf2[0]) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v44, &v45);
      v41 = v44;
    }
    operator delete(v41);
    *(_OWORD *)Buf2 = 0;
    v56 = 0;
  }
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  if ( v6 )
    RtlReleaseSRWLockExclusive(v39);
}

```

## disassembly

```asm
0x18000b3d0  mov     [rsp-8+arg_18], rbx
0x18000b3d5  push    rbp
0x18000b3d6  push    rsi
0x18000b3d7  push    rdi
0x18000b3d8  push    r12
0x18000b3da  push    r13
0x18000b3dc  push    r14
0x18000b3de  push    r15
0x18000b3e0  lea     rbp, [rsp-30h]
0x18000b3e5  sub     rsp, 130h
0x18000b3ec  mov     rax, cs:__security_cookie
0x18000b3f3  xor     rax, rsp
0x18000b3f6  mov     [rbp+60h+var_40], rax
0x18000b3fa  mov     rsi, r8
0x18000b3fd  mov     [rsp+160h+var_110], r8
0x18000b402  mov     rdi, rdx
0x18000b405  mov     r13, rcx
0x18000b408  xor     r14d, r14d
0x18000b40b  lea     rax, [rcx+8]
0x18000b40f  mov     [rsp+160h+var_F0], rax
0x18000b414  mov     rcx, rax
0x18000b417  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b41d  call    cs:__imp_GetCurrentThreadId
0x18000b423  mov     [rsp+160h+var_E4], eax
0x18000b427  mov     r12b, 1
0x18000b42a  mov     [rsp+160h+var_E8], r12b
0x18000b42f  xorps   xmm0, xmm0
0x18000b432  movdqu  [rbp+60h+var_B0], xmm0
0x18000b437  lea     rcx, [rbp+60h+Buf2]
0x18000b43b  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18000b440  movups  xmmword ptr [rbp+60h+var_88], xmm0
0x18000b444  mov     qword ptr [rbp+60h+var_78], r14
0x18000b448  mov     [rbp+60h+var_70], r14
0x18000b44c  lea     rcx, [rbp+60h+var_88]
0x18000b450  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000b455  movups  xmmword ptr [rbp+60h+var_68], xmm0
0x18000b459  mov     [rbp+60h+var_58], r14
0x18000b45d  mov     [rbp+60h+var_50], r14
0x18000b461  lea     rcx, [rbp+60h+var_68]
0x18000b465  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000b46a  nop
0x18000b46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b472  test    [rcx+1Ch], r12b
0x18000b476  jnz     loc_18000B988
0x18000b47c  lea     rax, [rbp+60h+Buf2]
0x18000b480  cmp     rax, rdi
0x18000b483  jz      loc_18000B518
0x18000b489  mov     r14, [rdi]
0x18000b48c  mov     rsi, [rdi+8]
0x18000b490  sub     rsi, r14
0x18000b493  mov     rbx, [rbp+60h+Buf2]
0x18000b497  mov     rdx, [rbp+60h+var_90]
0x18000b49b  sub     rdx, rbx
0x18000b49e  cmp     rsi, rdx
0x18000b4a1  jbe     loc_18000B93D
0x18000b4a7  mov     r15, 7FFFFFFFFFFFFFFFh
0x18000b4b1  cmp     rsi, r15
0x18000b4b4  ja      loc_18000BA5C
0x18000b4ba  mov     rcx, rdx
0x18000b4bd  shr     rcx, 1
0x18000b4c0  mov     rax, r15
0x18000b4c3  sub     rax, rcx
0x18000b4c6  cmp     rdx, rax
0x18000b4c9  ja      short loc_18000B4D6
0x18000b4cb  lea     r15, [rcx+rdx]
0x18000b4cf  cmp     r15, rsi
0x18000b4d2  cmovb   r15, rsi
0x18000b4d6  test    rbx, rbx
0x18000b4d9  jnz     loc_18000BA6A
0x18000b4df  mov     rcx, r15
0x18000b4e2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000b4e7  mov     rbx, rax
0x18000b4ea  mov     [rbp+60h+Buf2], rax
0x18000b4ee  mov     [rbp+60h+Buf2+8], rax
0x18000b4f2  lea     rcx, [rax+r15]
0x18000b4f6  mov     [rbp+60h+var_90], rcx
0x18000b4fa  mov     rcx, rax; void *
0x18000b4fd  mov     rdx, r14; Src
0x18000b500  mov     r8, rsi; Size
0x18000b503  call    memmove_0
0x18000b508  lea     rax, [rsi+rbx]
0x18000b50c  mov     [rbp+60h+Buf2+8], rax
0x18000b510  mov     rsi, [rsp+160h+var_110]
0x18000b515  xor     r14d, r14d
0x18000b518  lea     rdx, [rdi+18h]
0x18000b51c  lea     rax, [rbp+60h+var_88]
0x18000b520  cmp     rax, rdx
0x18000b523  jnz     loc_18000BA24
0x18000b529  lea     rdx, [rdi+38h]
0x18000b52d  lea     rax, [rbp+60h+var_68]
0x18000b531  cmp     rax, rdx
0x18000b534  jnz     loc_18000BA40
0x18000b53a  lea     rax, [r13+10h]
0x18000b53e  mov     [rsp+160h+var_110], rax
0x18000b543  mov     r8, rsi
0x18000b546  lea     rdx, [rbp+60h+var_E0]
0x18000b54a  mov     rcx, rax
0x18000b54d  call    ?Find@?$BrokerEventTable@VSebEvent@CBroker@@@Broker@@QEAA?AV?$shared_ptr@VSebEvent@CBroker@@@std@@AEBU_GUID@@@Z; Broker::BrokerEventTable<CBroker::SebEvent>::Find(_GUID const &)
0x18000b552  nop
0x18000b553  mov     ecx, [rbp+60h+var_78]
0x18000b556  lea     rax, [rbp+60h+var_88]
0x18000b55a  cmp     [rbp+60h+var_70], 7
0x18000b55f  cmova   rax, [rbp+60h+var_88]
0x18000b564  mov     rdi, [rbp+60h+var_E0]
0x18000b568  lea     r8, [rdi+20h]
0x18000b56c  cmp     qword ptr [r8+18h], 7
0x18000b571  jbe     short loc_18000B576
0x18000b573  mov     r8, [r8]; lpString1
0x18000b576  mov     [rsp+160h+lParam], r14; lParam
0x18000b57b  mov     [rsp+160h+lpReserved], r14; lpReserved
0x18000b580  mov     [rsp+160h+lpVersionInformation], r14; lpVersionInformation
0x18000b585  mov     [rsp+160h+cchCount2], ecx; cchCount2
0x18000b589  mov     [rsp+160h+lpString2], rax; lpString2
0x18000b58e  mov     r9d, [rdi+30h]; cchCount1
0x18000b592  mov     edx, 1; dwCmpFlags
0x18000b597  lea     rcx, LocaleName; lpLocaleName
0x18000b59e  call    cs:__imp_CompareStringEx
0x18000b5a4  mov     rbx, [rbp+60h+Buf2]
0x18000b5a8  cmp     eax, 2
0x18000b5ab  jnz     loc_18000B9B7
0x18000b5b1  mov     rax, [rbp+60h+Buf2+8]
0x18000b5b5  sub     rax, rbx
0x18000b5b8  mov     rcx, [rdi+8]; Buf1
0x18000b5bc  mov     r8, [rdi+10h]
0x18000b5c0  sub     r8, rcx; Size
0x18000b5c3  cmp     r8, rax
0x18000b5c6  jb      loc_18000B9B7
0x18000b5cc  ja      loc_18000B9B7
0x18000b5d2  mov     rdx, rbx; Buf2
0x18000b5d5  call    memcmp_0
0x18000b5da  test    r14b, r14b
0x18000b5dd  jz      loc_18000B9AF
0x18000b5e3  lea     r8, [rbp+60h+Buf2]
0x18000b5e7  lea     rdx, [rsp+160h+var_100]
0x18000b5ec  mov     rcx, [r13+20h]
0x18000b5f0  call    ?FindApplicationState@ApplicationStateTable@Broker@@QEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::ApplicationStateTable::FindApplicationState(Broker::ApplicationIdentity const &)
0x18000b5f5  mov     rdi, [rax]
0x18000b5f8  mov     r15, [rax+8]
0x18000b5fc  mov     [rax], r14
0x18000b5ff  mov     [rax+8], r14
0x18000b603  mov     qword ptr [rbp+60h+var_B0], rdi
0x18000b607  mov     qword ptr [rbp+60h+var_B0+8], r15
0x18000b60b  mov     r14d, 0FFFFFFFFh
0x18000b611  mov     rbx, qword ptr [rsp+160h+var_100+8]
0x18000b616  test    rbx, rbx
0x18000b619  jz      short loc_18000B652
0x18000b61b  mov     eax, r14d
0x18000b61e  lock xadd [rbx+8], eax
0x18000b623  cmp     eax, 1
0x18000b626  jnz     short loc_18000B652
0x18000b628  mov     rax, [rbx]
0x18000b62b  mov     rcx, rbx
0x18000b62e  mov     rax, [rax]
0x18000b631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b636  mov     eax, r14d
0x18000b639  lock xadd [rbx+0Ch], eax
0x18000b63e  cmp     eax, 1
0x18000b641  jnz     short loc_18000B652
0x18000b643  mov     rax, [rbx]
0x18000b646  mov     rcx, rbx
0x18000b649  mov     rax, [rax+8]
0x18000b64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b652  mov     rsi, [rbp+60h+var_E0]
0x18000b656  mov     eax, [rsi+60h]
0x18000b659  sub     eax, 1000h
0x18000b65e  lea     rbx, ds:0[rax*4]
0x18000b666  mov     rax, [rdi+58h]
0x18000b66a  cmp     dword ptr [rbx+rax], 0FFFFFFFFh
0x18000b66e  jnz     loc_18000BA87
0x18000b674  movsxd  rax, dword ptr [rsi+60h]
0x18000b678  sub     rax, 1000h
0x18000b67e  lea     rax, [rax+rax*4]
0x18000b682  lea     rcx, byte_180035F64
0x18000b689  mov     rdi, [rbp+60h+var_D8]
0x18000b68d  test    byte ptr [rcx+rax*8], 1
0x18000b691  jnz     loc_18000BAB1
0x18000b697  xorps   xmm0, xmm0
0x18000b69a  movdqu  [rsp+160h+var_100], xmm0
0x18000b6a0  test    rdi, rdi
0x18000b6a3  jz      short loc_18000B6A9
0x18000b6a5  lock inc dword ptr [rdi+8]
0x18000b6a9  mov     qword ptr [rsp+160h+var_100], rsi
0x18000b6ae  mov     qword ptr [rsp+160h+var_100+8], rdi
0x18000b6b3  lea     rax, [rsp+160h+var_100]
0x18000b6b8  mov     [rsp+160h+var_108], rax
0x18000b6bd  mov     r12, [r13+10h]
0x18000b6c1  mov     rbx, [r12+8]
0x18000b6c6  xor     eax, eax
0x18000b6c8  mov     [rbp+60h+var_C4], eax
0x18000b6cb  mov     r13, r12
0x18000b6ce  cmp     [rbx+19h], al
0x18000b6d1  jnz     short loc_18000B710
0x18000b6d3  nop     dword ptr [rax+00h]
0x18000b6d7  nop     word ptr [rax+rax+00000000h]
0x18000b6e0  lea     rcx, [rbx+20h]; Buf1
0x18000b6e4  mov     r8d, 10h; Size
0x18000b6ea  lea     rdx, [rsi+78h]; Buf2
0x18000b6ee  call    memcmp_0
0x18000b6f3  test    eax, eax
0x18000b6f5  jns     loc_18000B909
0x18000b6fb  mov     cl, 1
0x18000b6fd  lea     rax, [rbx+10h]
0x18000b701  test    cl, cl
0x18000b703  cmovz   rax, rbx
0x18000b707  mov     rbx, [rax]
0x18000b70a  cmp     byte ptr [rbx+19h], 0
0x18000b70e  jz      short loc_18000B6E0
0x18000b710  cmp     byte ptr [r13+19h], 0
0x18000b715  jnz     loc_18000B913
0x18000b71b  lea     rdx, [r13+20h]; Buf2
0x18000b71f  mov     r8d, 10h; Size
0x18000b725  lea     rcx, [rsi+78h]; Buf1
0x18000b729  call    memcmp_0
0x18000b72e  test    eax, eax
0x18000b730  js      loc_18000B913
0x18000b736  cmp     r13, r12
0x18000b739  jz      loc_18000B913
0x18000b73f  mov     rdx, r13
0x18000b742  mov     rcx, [rsp+160h+var_110]
0x18000b747  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>>>,std::_Iterator_base0>)
0x18000b74c  mov     rbx, rax
0x18000b74f  mov     rcx, [rax+38h]; this
0x18000b753  test    rcx, rcx
0x18000b756  jz      short loc_18000B75D
0x18000b758  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000b75d  mov     edx, 40h ; '@'; unsigned __int64
0x18000b762  mov     rcx, rbx; void *
0x18000b765  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b76a  nop
0x18000b76b  mov     rbx, qword ptr [rsp+160h+var_100+8]
0x18000b770  test    rbx, rbx
0x18000b773  jz      short loc_18000B7AC
0x18000b775  mov     eax, r14d
0x18000b778  lock xadd [rbx+8], eax
0x18000b77d  cmp     eax, 1
0x18000b780  jnz     short loc_18000B7AC
0x18000b782  mov     rax, [rbx]
0x18000b785  mov     rcx, rbx
0x18000b788  mov     rax, [rax]
0x18000b78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b790  mov     eax, r14d
0x18000b793  lock xadd [rbx+0Ch], eax
0x18000b798  cmp     eax, 1
0x18000b79b  jnz     short loc_18000B7AC
0x18000b79d  mov     rax, [rbx]
0x18000b7a0  mov     rcx, rbx
0x18000b7a3  mov     rax, [rax+8]
0x18000b7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7ac  mov     rbx, [rsp+160h+var_F0]
0x18000b7b1  mov     rcx, rbx
0x18000b7b4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b7ba  xor     r12b, r12b
0x18000b7bd  mov     [rsp+160h+var_E8], r12b
0x18000b7c2  mov     dl, 1; bool
0x18000b7c4  mov     rcx, [rbp+60h+var_E0]; this
0x18000b7c8  call    ?OnDisable@SebEvent@CBroker@@QEAAX_N@Z; CBroker::SebEvent::OnDisable(bool)
0x18000b7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7d4  test    byte ptr [rcx+1Ch], 1
0x18000b7d8  jz      short loc_18000B7E4
0x18000b7da  cmp     byte ptr [rcx+19h], 4
0x18000b7de  jnb     loc_18000B96E
0x18000b7e4  test    rdi, rdi
0x18000b7e7  jz      short loc_18000B821
0x18000b7e9  mov     eax, r14d
0x18000b7ec  lock xadd [rdi+8], eax
0x18000b7f1  cmp     eax, 1
0x18000b7f4  jnz     short loc_18000B821
0x18000b7f6  mov     rax, [rdi]
0x18000b7f9  mov     rcx, rdi
0x18000b7fc  mov     rax, [rax]
0x18000b7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b804  mov     eax, r14d
0x18000b807  lock xadd [rdi+0Ch], eax
0x18000b80c  cmp     eax, 1
0x18000b80f  jnz     short loc_18000B821
0x18000b811  mov     rax, [rdi]
0x18000b814  mov     rcx, rdi
0x18000b817  mov     rax, [rax+8]
0x18000b81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b820  nop
0x18000b821  mov     rdx, [rbp+60h+var_50]
0x18000b825  cmp     rdx, 7
0x18000b829  ja      loc_18000BAFB
0x18000b82f  xor     edi, edi
0x18000b831  mov     [rbp+60h+var_58], rdi
0x18000b835  mov     [rbp+60h+var_50], 7
0x18000b83d  mov     word ptr [rbp+60h+var_68], di
0x18000b841  mov     rdx, [rbp+60h+var_70]
0x18000b845  cmp     rdx, 7
0x18000b849  ja      loc_18000BB11
0x18000b84f  mov     qword ptr [rbp+60h+var_78], rdi
0x18000b853  mov     [rbp+60h+var_70], 7
0x18000b85b  mov     word ptr [rbp+60h+var_88], di
0x18000b85f  mov     rcx, [rbp+60h+Buf2]; void *
0x18000b863  test    rcx, rcx
0x18000b866  jz      short loc_18000B897
0x18000b868  mov     rdx, [rbp+60h+var_90]
0x18000b86c  sub     rdx, rcx; unsigned __int64
0x18000b86f  mov     [rsp+160h+var_108], rdx
0x18000b874  mov     [rsp+160h+var_110], rcx
  ... truncated ...
```
