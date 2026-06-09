# CSearchQueryHelper::GenerateSQLFromUserQuery(wchar_t const *,wchar_t * *)

- ea: `0x1800564f0`
- end: `0x1800567f8`
- name: `?GenerateSQLFromUserQuery@CSearchQueryHelper@@UEAAJPEB_WPEAPEA_W@Z`
- size: `776`
- prototype: `int(CSearchQueryHelper *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015a40`
- `0x180034e80`
- `0x18003b8f4`
- `0x1800564f0`
- `0x18005c9f4`
- `0x18005daf0`
- `0x180072eb0`
- `0x18007334c`
- `0x1800733fc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005672e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005672e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056774`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056774`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056555`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800565f6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056555`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800565f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800565a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005661c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800565a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005661c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005655b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800565fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056734`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005655b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800565fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056734`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800566b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800566b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005676a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005676a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSearchQueryHelper::GenerateSQLFromUserQuery(
        CSearchQueryHelper *this,
        const wchar_t *a2,
        wchar_t **a3)
{
  _QWORD *v6; // r14
  int InitializedQueryParser; // ebx
  enum tagSTRUCTURED_QUERY_SYNTAX ParserSyntax; // eax
  unsigned int v9; // edx
  CSearchQueryHelper *v10; // rcx
  const struct _GUID *v11; // r8
  __int64 v12; // rcx
  size_t *v13; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  const struct _GUID *v17; // [rsp+38h] [rbp-41h]
  __int64 v18; // [rsp+50h] [rbp-29h] BYREF
  struct IVirtualPropertyArray *v19; // [rsp+58h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  struct ICondition *v21; // [rsp+68h] [rbp-11h] BYREF
  __int64 v22; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v23[2]; // [rsp+78h] [rbp-1h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp+Fh] BYREF

  if ( a3 )
  {
    *a3 = 0;
    if ( (unsigned int)CSearchQueryHelper::_IsEmptyString(a2) )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v6 = (_QWORD *)((char *)this + 112);
      if ( *((_QWORD *)this + 14) )
        goto LABEL_7;
      InitializedQueryParser = 0;
      pv = (char *)this + 16;
      AcquireSRWLockExclusive((PSRWLOCK)this + 2);
      *((_DWORD *)this + 6) = GetCurrentThreadId();
      if ( !*v6 )
      {
        ParserSyntax = _QueryParserSyntax(*((enum _SEARCH_QUERY_SYNTAX *)this + 11));
        InitializedQueryParser = CSearchQueryHelper::_GetInitializedQueryParser(
                                   *((CSearchQueryHelper **)this + 6),
                                   *((const wchar_t **)this + 10),
                                   *((_WORD *)this + 18),
                                   *((_DWORD *)this + 8),
                                   ParserSyntax,
                                   v9,
                                   *((wchar_t **)this + 6),
                                   v17,
                                   (void **)this + 14);
      }
      ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
      if ( InitializedQueryParser >= 0 )
      {
LABEL_7:
        v19 = 0;
        InitializedQueryParser = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct IVirtualPropertyArray **))(*(_QWORD *)*v6 + 112LL))(
                                   *v6,
                                   &GUID_9ceeb9b5_229a_4eef_8a34_0c54935574d5,
                                   &v19);
        if ( InitializedQueryParser >= 0 )
        {
          if ( *((_QWORD *)this + 15) )
            goto LABEL_12;
          pv = (char *)this + 16;
          AcquireSRWLockExclusive((PSRWLOCK)this + 2);
          *((_DWORD *)this + 6) = GetCurrentThreadId();
          if ( !*((_QWORD *)this + 15) )
            InitializedQueryParser = CSearchQueryHelper::_GetInitializedSqlGenerator(v10, v19, v11, (void **)this + 15);
          ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
          if ( InitializedQueryParser >= 0 )
          {
LABEL_12:
            v18 = 0;
            InitializedQueryParser = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, __int64 *))(**((_QWORD **)this + 14) + 24LL))(
                                       *((_QWORD *)this + 14),
                                       a2,
                                       0,
                                       &v18);
            if ( InitializedQueryParser >= 0 )
            {
              v23[0] = 0;
              InitializedQueryParser = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v18 + 56LL))(
                                         v18,
                                         v23,
                                         0);
              if ( InitializedQueryParser >= 0 )
              {
                v22 = 0;
                InitializedQueryParser = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
                                           v18,
                                           &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                                           &v22);
                if ( InitializedQueryParser >= 0 )
                {
                  SystemTime = 0;
                  GetLocalTime(&SystemTime);
                  v21 = 0;
                  InitializedQueryParser = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct _SYSTEMTIME *, GUID *, struct ICondition **))(*(_QWORD *)v22 + 120LL))(
                                             v22,
                                             v23[0],
                                             8,
                                             &SystemTime,
                                             &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                             &v21);
                  if ( InitializedQueryParser >= 0 )
                  {
                    pv = 0;
                    InitializedQueryParser = _AllocArray<wchar_t,CTCoAllocPolicy>(v12, 1, 0x10000u, &pv);
                    if ( InitializedQueryParser >= 0 )
                    {
                      v23[1] = (char *)this + 16;
                      AcquireSRWLockShared((PSRWLOCK)this + 2);
                      *((_DWORD *)this + 7) = GetCurrentThreadId();
                      v13 = (size_t *)pv;
                      InitializedQueryParser = CSearchQueryHelper::_GenerateSql(this, v21, v19, (wchar_t *)pv);
                      if ( InitializedQueryParser >= 0 )
                        InitializedQueryParser = _AllocString<CTCoAllocPolicy>(v15, v14, v13, a3);
                      CoTaskMemFree(v13);
                      ReleaseSRWLockShared((PSRWLOCK)this + 2);
                    }
                    ((void (__fastcall *)(struct ICondition *))v21->lpVtbl->Release)(v21);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                }
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
          }
          (*(void (__fastcall **)(struct IVirtualPropertyArray *))(*(_QWORD *)v19 + 16LL))(v19);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)InitializedQueryParser;
}

```

## disassembly

```asm
0x1800564f0  push    rbp
0x1800564f2  push    rbx
0x1800564f3  push    rsi
0x1800564f4  push    rdi
0x1800564f5  push    r12
0x1800564f7  push    r14
0x1800564f9  push    r15
0x1800564fb  lea     rbp, [rsp-27h]
0x180056500  sub     rsp, 0A0h
0x180056507  mov     rax, cs:__security_cookie
0x18005650e  xor     rax, rsp
0x180056511  mov     [rbp+57h+var_38], rax
0x180056515  mov     r15, r8
0x180056518  mov     r12, rdx
0x18005651b  mov     rdi, rcx
0x18005651e  test    r8, r8
0x180056521  jz      loc_1800567D3
0x180056527  mov     qword ptr [r8], 0
0x18005652e  mov     rcx, rdx; wchar_t *
0x180056531  call    ?_IsEmptyString@CSearchQueryHelper@@CAHPEB_W@Z; CSearchQueryHelper::_IsEmptyString(wchar_t const *)
0x180056536  test    eax, eax
0x180056538  jnz     loc_1800567CC
0x18005653e  lea     r14, [rdi+70h]
0x180056542  cmp     qword ptr [r14], 0
0x180056546  jnz     short loc_1800565B5
0x180056548  xor     ebx, ebx
0x18005654a  lea     rsi, [rdi+10h]
0x18005654e  mov     [rbp+57h+pv], rsi
0x180056552  mov     rcx, rsi; SRWLock
0x180056555  call    cs:__imp_AcquireSRWLockExclusive
0x18005655b  call    cs:__imp_GetCurrentThreadId
0x180056561  mov     [rsi+8], eax
0x180056564  cmp     [r14], rbx
0x180056567  jnz     short loc_1800565A4
0x180056569  xor     edx, edx
0x18005656b  cmp     dword ptr [rdi+28h], 1
0x18005656f  setz    dl
0x180056572  mov     ecx, [rdi+2Ch]; enum _SEARCH_QUERY_SYNTAX
0x180056575  call    ?_QueryParserSyntax@@YA?AW4tagSTRUCTURED_QUERY_SYNTAX@@W4_SEARCH_QUERY_SYNTAX@@@Z; _QueryParserSyntax(_SEARCH_QUERY_SYNTAX)
0x18005657a  mov     [rsp+0D0h+var_90], r14; void **
0x18005657f  mov     rcx, [rdi+30h]; this
0x180056583  mov     [rsp+0D0h+var_A0], rcx; wchar_t *
0x180056588  mov     [rsp+0D0h+var_A8], edx; int
0x18005658c  mov     [rsp+0D0h+var_B0], eax; enum tagSTRUCTURED_QUERY_SYNTAX
0x180056590  mov     r9d, [rdi+20h]; unsigned int
0x180056594  movzx   r8d, word ptr [rdi+24h]; unsigned __int16
0x180056599  mov     rdx, [rdi+50h]; wchar_t *
0x18005659d  call    ?_GetInitializedQueryParser@CSearchQueryHelper@@AEAAJPEB_WGKW4tagSTRUCTURED_QUERY_SYNTAX@@H0AEBU_GUID@@PEAPEAX@Z; CSearchQueryHelper::_GetInitializedQueryParser(wchar_t const *,ushort,ulong,tagSTRUCTURED_QUERY_SYNTAX,int,wchar_t const *,_GUID const &,void * *)
0x1800565a2  mov     ebx, eax
0x1800565a4  mov     rcx, rsi; SRWLock
0x1800565a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800565ad  test    ebx, ebx
0x1800565af  js      loc_1800567D8
0x1800565b5  mov     [rbp+57h+var_78], 0
0x1800565bd  mov     rcx, [r14]
0x1800565c0  mov     rax, [rcx]
0x1800565c3  lea     r8, [rbp+57h+var_78]
0x1800565c7  lea     rdx, _GUID_9ceeb9b5_229a_4eef_8a34_0c54935574d5
0x1800565ce  mov     rax, [rax+70h]
0x1800565d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800565d7  mov     ebx, eax
0x1800565d9  test    eax, eax
0x1800565db  js      loc_1800567D8
0x1800565e1  lea     r14, [rdi+78h]
0x1800565e5  cmp     qword ptr [r14], 0
0x1800565e9  jnz     short loc_18005662A
0x1800565eb  lea     rsi, [rdi+10h]
0x1800565ef  mov     [rbp+57h+pv], rsi
0x1800565f3  mov     rcx, rsi; SRWLock
0x1800565f6  call    cs:__imp_AcquireSRWLockExclusive
0x1800565fc  call    cs:__imp_GetCurrentThreadId
0x180056602  mov     [rsi+8], eax
0x180056605  cmp     qword ptr [r14], 0
0x180056609  jnz     short loc_180056619
0x18005660b  mov     r9, r14; void **
0x18005660e  mov     rdx, [rbp+57h+var_78]; struct IVirtualPropertyArray *
0x180056612  call    ?_GetInitializedSqlGenerator@CSearchQueryHelper@@AEAAJPEAUIVirtualPropertyArray@@AEBU_GUID@@PEAPEAX@Z; CSearchQueryHelper::_GetInitializedSqlGenerator(IVirtualPropertyArray *,_GUID const &,void * *)
0x180056617  mov     ebx, eax
0x180056619  mov     rcx, rsi; SRWLock
0x18005661c  call    cs:__imp_ReleaseSRWLockExclusive
0x180056622  test    ebx, ebx
0x180056624  js      loc_1800567BA
0x18005662a  mov     [rbp+57h+var_80], 0
0x180056632  mov     rcx, [rdi+70h]
0x180056636  mov     rax, [rcx]
0x180056639  lea     r9, [rbp+57h+var_80]
0x18005663d  xor     r8d, r8d
0x180056640  mov     rdx, r12
0x180056643  mov     rax, [rax+18h]
0x180056647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005664c  mov     ebx, eax
0x18005664e  test    eax, eax
0x180056650  js      loc_1800567BA
0x180056656  mov     [rbp+57h+var_58], 0
0x18005665e  mov     rcx, [rbp+57h+var_80]
0x180056662  mov     rax, [rcx]
0x180056665  xor     r8d, r8d
0x180056668  lea     rdx, [rbp+57h+var_58]
0x18005666c  mov     rax, [rax+38h]
0x180056670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056675  mov     ebx, eax
0x180056677  test    eax, eax
0x180056679  js      loc_1800567AA
0x18005667f  mov     [rbp+57h+var_60], 0
0x180056687  mov     rcx, [rbp+57h+var_80]
0x18005668b  mov     rax, [rcx]
0x18005668e  lea     r8, [rbp+57h+var_60]
0x180056692  lea     rdx, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a
0x180056699  mov     rax, [rax]
0x18005669c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566a1  mov     ebx, eax
0x1800566a3  test    eax, eax
0x1800566a5  js      loc_18005679A
0x1800566ab  xorps   xmm0, xmm0
0x1800566ae  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800566b2  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800566b6  call    cs:__imp_GetLocalTime
0x1800566bc  mov     [rbp+57h+var_68], 0
0x1800566c4  mov     rcx, [rbp+57h+var_60]
0x1800566c8  mov     rax, [rcx]
0x1800566cb  lea     rdx, [rbp+57h+var_68]
0x1800566cf  mov     qword ptr [rsp+0D0h+var_A8], rdx
0x1800566d4  lea     r8, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800566db  mov     qword ptr [rsp+0D0h+var_B0], r8; unsigned __int64
0x1800566e0  lea     r9, [rbp+57h+SystemTime]
0x1800566e4  mov     r8d, 8
0x1800566ea  mov     rdx, [rbp+57h+var_58]
0x1800566ee  mov     rax, [rax+78h]
0x1800566f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566f7  mov     ebx, eax
0x1800566f9  test    eax, eax
0x1800566fb  js      loc_18005678A
0x180056701  mov     [rbp+57h+pv], 0
0x180056709  lea     r9, [rbp+57h+pv]
0x18005670d  mov     edx, 1
0x180056712  mov     r8d, 10000h
0x180056718  call    ??$_AllocArray@_WVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEA_W@Z; _AllocArray<wchar_t,CTCoAllocPolicy>(void *,ulong,unsigned __int64,wchar_t * *)
0x18005671d  mov     ebx, eax
0x18005671f  test    eax, eax
0x180056721  js      short loc_18005677A
0x180056723  lea     rsi, [rdi+10h]
0x180056727  mov     [rbp+57h+var_50], rsi
0x18005672b  mov     rcx, rsi; SRWLock
0x18005672e  call    cs:__imp_AcquireSRWLockShared
0x180056734  call    cs:__imp_GetCurrentThreadId
0x18005673a  mov     [rsi+0Ch], eax
0x18005673d  mov     r14, [rbp+57h+pv]
0x180056741  mov     r9, r14; wchar_t *
0x180056744  mov     r8, [rbp+57h+var_78]; struct IVirtualPropertyArray *
0x180056748  mov     rdx, [rbp+57h+var_68]; struct ICondition *
0x18005674c  mov     rcx, rdi; this
0x18005674f  call    ?_GenerateSql@CSearchQueryHelper@@AEAAJPEAUICondition@@PEAUIVirtualPropertyArray@@PEA_W_K@Z; CSearchQueryHelper::_GenerateSql(ICondition *,IVirtualPropertyArray *,wchar_t *,unsigned __int64)
0x180056754  mov     ebx, eax
0x180056756  test    eax, eax
0x180056758  js      short loc_180056767
0x18005675a  mov     r9, r15
0x18005675d  mov     r8, r14
0x180056760  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180056765  mov     ebx, eax
0x180056767  mov     rcx, r14; pv
0x18005676a  call    cs:__imp_CoTaskMemFree
0x180056770  nop
0x180056771  mov     rcx, rsi; SRWLock
0x180056774  call    cs:__imp_ReleaseSRWLockShared
0x18005677a  mov     rcx, [rbp+57h+var_68]
0x18005677e  mov     rax, [rcx]
0x180056781  mov     rax, [rax+10h]
0x180056785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005678a  mov     rcx, [rbp+57h+var_60]
0x18005678e  mov     rax, [rcx]
0x180056791  mov     rax, [rax+10h]
0x180056795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005679a  mov     rcx, [rbp+57h+var_58]
0x18005679e  mov     rax, [rcx]
0x1800567a1  mov     rax, [rax+10h]
0x1800567a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567aa  mov     rcx, [rbp+57h+var_80]
0x1800567ae  mov     rax, [rcx]
0x1800567b1  mov     rax, [rax+10h]
0x1800567b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567ba  mov     rcx, [rbp+57h+var_78]
0x1800567be  mov     rax, [rcx]
0x1800567c1  mov     rax, [rax+10h]
0x1800567c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567ca  jmp     short loc_1800567D8
0x1800567cc  mov     ebx, 80070057h
0x1800567d1  jmp     short loc_1800567D8
0x1800567d3  mov     ebx, 80004003h
0x1800567d8  mov     eax, ebx
0x1800567da  mov     rcx, [rbp+57h+var_38]
0x1800567de  xor     rcx, rsp; StackCookie
0x1800567e1  call    __security_check_cookie
0x1800567e6  add     rsp, 0A0h
0x1800567ed  pop     r15
0x1800567ef  pop     r14
0x1800567f1  pop     r12
0x1800567f3  pop     rdi
0x1800567f4  pop     rsi
0x1800567f5  pop     rbx
0x1800567f6  pop     rbp
0x1800567f7  retn
```
