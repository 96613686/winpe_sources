# DatabaseManager::GetOrCreateDatabase(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,DatabaseName)

- ea: `0x1800250ec`
- end: `0x18002540c`
- name: `?GetOrCreateDatabase@DatabaseManager@@AEAA?AV?$shared_ptr@VADPDatabase@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@W4DatabaseName@@@Z`
- size: `800`
- prototype: `_QWORD *__fastcall(RTL_SRWLOCK *, _QWORD *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013180`
- `0x180017c78`

## callees

- `0x180001008`
- `0x180002250`
- `0x18000c37c`
- `0x18000e1d0`
- `0x18002438c`
- `0x18002442c`
- `0x180024678`
- `0x18002478c`
- `0x1800248a0`
- `0x180024d34`
- `0x180024f44`
- `0x1800250ec`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800253c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025130`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025130`

## string_xrefs

- `0x1800253fa`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`

## pseudocode

```c
_QWORD *__fastcall DatabaseManager::GetOrCreateDatabase(RTL_SRWLOCK *a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  RTL_SRWLOCK *v8; // r15
  _QWORD *v9; // rdx
  __int64 v10; // r9
  unsigned __int64 i; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // rsi
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rcx
  volatile signed __int32 *v19; // rsi
  _QWORD *v20; // rbx
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // esi
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  volatile signed __int32 *v28; // rsi
  volatile signed __int32 *v29; // rsi
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rcx
  char *v34; // [rsp+20h] [rbp-39h]
  char v35[8]; // [rsp+30h] [rbp-29h] BYREF
  volatile signed __int32 *v36; // [rsp+38h] [rbp-21h]
  int v37; // [rsp+40h] [rbp-19h]
  _QWORD *v38; // [rsp+48h] [rbp-11h]
  RTL_SRWLOCK *v39; // [rsp+50h] [rbp-9h]
  _BYTE v40[16]; // [rsp+58h] [rbp-1h] BYREF
  _QWORD v41[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v43; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v38 = a2;
  v8 = a1 + 8;
  AcquireSRWLockExclusive(a1 + 8);
  v39 = v8;
  *a2 = 0;
  a2[1] = 0;
  v37 = 1;
  DatabaseManager::GetDatabaseIdentifier(v41, a3, a4);
  v9 = v41;
  if ( v43 > 7 )
    v9 = (_QWORD *)v41[0];
  v10 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 2 * v42; ++i )
    v10 = 0x100000001B3LL * (*((unsigned __int8 *)v9 + i) ^ (unsigned __int64)v10);
  v12 = *(_QWORD **)(std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ADPDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ADPDatabase>>>,0>>::_Find_last<std::wstring>(
                       a1,
                       v40,
                       v41,
                       v10)
                   + 8);
  if ( !v12 || v12 == a1[1].Ptr )
  {
    v20 = v41;
    if ( v43 > 7 )
      v20 = (_QWORD *)v41[0];
    v21 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
    if ( *v21 > 5u )
    {
      *(_QWORD *)v35 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (_DWORD)v21,
        (unsigned int)byte_1801004AB,
        v22,
        v23,
        (__int64)v35);
    }
    if ( a4 )
    {
      v24 = a4 - 1;
      if ( v24 )
      {
        if ( v24 != 1 )
          wil::details::in1diag3::FailFast_UnexpectedMsg(
            retaddr,
            (void *)0xA4,
            (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
            "Invalid database name",
            v34);
        v25 = (__int64 *)std::make_shared<ActionsPolicyDatabase,std::wstring &>(v35, v41);
      }
      else
      {
        v25 = (__int64 *)std::make_shared<CustomEntityDatabase,std::wstring &>(v35, v41);
      }
    }
    else
    {
      v25 = (__int64 *)std::make_shared<SystemDatabase,std::wstring &>(v35, v41);
    }
    v26 = *v25;
    v27 = v25[1];
    *v25 = 0;
    v25[1] = 0;
    *a2 = v26;
    v28 = (volatile signed __int32 *)a2[1];
    a2[1] = v27;
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
    v29 = v36;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    (**(void (__fastcall ***)(_QWORD))*a2)(*a2);
    v30 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ADPDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ADPDatabase>>>,0>>::_Try_emplace<std::wstring const &,>(
                       a1,
                       v40,
                       v41);
    v31 = a2[1];
    if ( v31 )
      _InterlockedIncrement((volatile signed __int32 *)(v31 + 8));
    v32 = a2[1];
    *(_QWORD *)(v30 + 48) = *a2;
    v19 = *(volatile signed __int32 **)(v30 + 56);
    *(_QWORD *)(v30 + 56) = v32;
    if ( v19 )
      goto LABEL_36;
  }
  else
  {
    v13 = v41;
    if ( v43 > 7 )
      v13 = (_QWORD *)v41[0];
    v14 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
    if ( *v14 > 5u )
    {
      *(_QWORD *)v35 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (_DWORD)v14,
        (unsigned int)&dword_18010046C,
        v15,
        v16,
        (__int64)v35);
    }
    v17 = v12[7];
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    v18 = v12[7];
    *a2 = v12[6];
    v19 = (volatile signed __int32 *)a2[1];
    a2[1] = v18;
    if ( v19 )
    {
LABEL_36:
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
  }
  std::wstring::~wstring(v41);
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  return a2;
}

```

## disassembly

```asm
0x1800250ec  mov     [rsp-8+arg_18], rbx
0x1800250f1  push    rbp
0x1800250f2  push    rsi
0x1800250f3  push    rdi
0x1800250f4  push    r14
0x1800250f6  push    r15
0x1800250f8  lea     rbp, [rsp-37h]
0x1800250fd  sub     rsp, 90h
0x180025104  mov     rax, cs:__security_cookie
0x18002510b  xor     rax, rsp
0x18002510e  mov     [rbp+57h+var_28], rax
0x180025112  mov     esi, r9d
0x180025115  mov     rbx, r8
0x180025118  mov     rdi, rdx
0x18002511b  mov     r14, rcx
0x18002511e  mov     [rbp+57h+var_68], rdx
0x180025122  mov     [rbp+57h+var_70], 0
0x180025129  lea     r15, [rcx+40h]
0x18002512d  mov     rcx, r15; SRWLock
0x180025130  call    cs:__imp_AcquireSRWLockExclusive
0x180025136  mov     [rbp+57h+var_60], r15
0x18002513a  mov     qword ptr [rdi], 0
0x180025141  mov     qword ptr [rdi+8], 0
0x180025149  mov     [rbp+57h+var_70], 1
0x180025150  mov     r8d, esi
0x180025153  mov     rdx, rbx
0x180025156  lea     rcx, [rbp+57h+var_48]
0x18002515a  call    ?GetDatabaseIdentifier@DatabaseManager@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@W4DatabaseName@@@Z; DatabaseManager::GetDatabaseIdentifier(std::wstring_view const &,DatabaseName)
0x18002515f  nop
0x180025160  mov     rax, [rbp+57h+var_38]
0x180025164  lea     rdx, [rbp+57h+var_48]
0x180025168  cmp     [rbp+57h+var_30], 7
0x18002516d  cmova   rdx, [rbp+57h+var_48]
0x180025172  mov     r9, 0CBF29CE484222325h
0x18002517c  lea     r8, [rax+rax]
0x180025180  xor     ecx, ecx
0x180025182  test    r8, r8
0x180025185  jz      short loc_1800251A4
0x180025187  movzx   eax, byte ptr [rdx+rcx]
0x18002518b  xor     r9, rax
0x18002518e  mov     r10, 100000001B3h
0x180025198  imul    r9, r10
0x18002519c  inc     rcx
0x18002519f  cmp     rcx, r8
0x1800251a2  jb      short loc_180025187
0x1800251a4  lea     r8, [rbp+57h+var_48]
0x1800251a8  lea     rdx, [rbp+57h+var_58]
0x1800251ac  mov     rcx, r14
0x1800251af  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ADPDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ADPDatabase>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800251b4  mov     rbx, [rax+8]
0x1800251b8  test    rbx, rbx
0x1800251bb  jz      short loc_18002522B
0x1800251bd  cmp     rbx, [r14+8]
0x1800251c1  jz      short loc_18002522B
0x1800251c3  lea     rsi, [rbp+57h+var_48]
0x1800251c7  cmp     [rbp+57h+var_30], 7
0x1800251cc  cmova   rsi, [rbp+57h+var_48]
0x1800251d1  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x1800251d6  mov     rcx, [rax+8]
0x1800251da  mov     eax, [rcx]
0x1800251dc  cmp     eax, 5
0x1800251df  jbe     short loc_1800251FA
0x1800251e1  mov     qword ptr [rbp+57h+var_80], rsi
0x1800251e5  lea     rax, [rbp+57h+var_80]
0x1800251e9  mov     [rsp+0B0h+var_90], rax
0x1800251ee  lea     rdx, dword_18010046C
0x1800251f5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800251fa  mov     rax, [rbx+38h]
0x1800251fe  test    rax, rax
0x180025201  jz      short loc_180025207
0x180025203  lock inc dword ptr [rax+8]
0x180025207  mov     rcx, [rbx+38h]
0x18002520b  mov     rax, [rbx+30h]
0x18002520f  mov     [rdi], rax
0x180025212  mov     rsi, [rdi+8]
0x180025216  mov     [rdi+8], rcx
0x18002521a  test    rsi, rsi
0x18002521d  jz      loc_1800253B1
0x180025223  or      ebx, 0FFFFFFFFh
0x180025226  jmp     loc_18002537D
0x18002522b  lea     rbx, [rbp+57h+var_48]
0x18002522f  cmp     [rbp+57h+var_30], 7
0x180025234  cmova   rbx, [rbp+57h+var_48]
0x180025239  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x18002523e  mov     rcx, [rax+8]
0x180025242  mov     eax, [rcx]
0x180025244  cmp     eax, 5
0x180025247  jbe     short loc_180025262
0x180025249  mov     qword ptr [rbp+57h+var_80], rbx
0x18002524d  lea     rax, [rbp+57h+var_80]
0x180025251  mov     [rsp+0B0h+var_90], rax; char *
0x180025256  lea     rdx, byte_1801004AB
0x18002525d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180025262  test    esi, esi
0x180025264  jz      short loc_180025292
0x180025266  sub     esi, 1
0x180025269  jz      short loc_180025283
0x18002526b  cmp     esi, 1
0x18002526e  jnz     loc_1800253EF
0x180025274  lea     rdx, [rbp+57h+var_48]
0x180025278  lea     rcx, [rbp+57h+var_80]
0x18002527c  call    ??$make_shared@UActionsPolicyDatabase@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$shared_ptr@UActionsPolicyDatabase@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_shared<ActionsPolicyDatabase,std::wstring &>(std::wstring &)
0x180025281  jmp     short loc_18002529F
0x180025283  lea     rdx, [rbp+57h+var_48]
0x180025287  lea     rcx, [rbp+57h+var_80]
0x18002528b  call    ??$make_shared@UCustomEntityDatabase@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$shared_ptr@UCustomEntityDatabase@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_shared<CustomEntityDatabase,std::wstring &>(std::wstring &)
0x180025290  jmp     short loc_18002529F
0x180025292  lea     rdx, [rbp+57h+var_48]
0x180025296  lea     rcx, [rbp+57h+var_80]
0x18002529a  call    ??$make_shared@VSystemDatabase@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$shared_ptr@VSystemDatabase@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_shared<SystemDatabase,std::wstring &>(std::wstring &)
0x18002529f  mov     rcx, [rax]
0x1800252a2  mov     rdx, [rax+8]
0x1800252a6  mov     qword ptr [rax], 0
0x1800252ad  mov     qword ptr [rax+8], 0
0x1800252b5  mov     [rdi], rcx
0x1800252b8  mov     rsi, [rdi+8]
0x1800252bc  or      ebx, 0FFFFFFFFh
0x1800252bf  mov     [rdi+8], rdx
0x1800252c3  test    rsi, rsi
0x1800252c6  jz      short loc_1800252FB
0x1800252c8  mov     eax, ebx
0x1800252ca  lock xadd [rsi+8], eax
0x1800252cf  add     eax, ebx
0x1800252d1  jnz     short loc_1800252FB
0x1800252d3  mov     rax, [rsi]
0x1800252d6  mov     rcx, rsi
0x1800252d9  mov     rax, [rax]
0x1800252dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252e1  mov     eax, ebx
0x1800252e3  lock xadd [rsi+0Ch], eax
0x1800252e8  add     eax, ebx
0x1800252ea  jnz     short loc_1800252FB
0x1800252ec  mov     rax, [rsi]
0x1800252ef  mov     rcx, rsi
0x1800252f2  mov     rax, [rax+8]
0x1800252f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252fb  mov     rsi, [rbp+57h+var_78]
0x1800252ff  test    rsi, rsi
0x180025302  jz      short loc_180025337
0x180025304  mov     eax, ebx
0x180025306  lock xadd [rsi+8], eax
0x18002530b  add     eax, ebx
0x18002530d  jnz     short loc_180025337
0x18002530f  mov     rax, [rsi]
0x180025312  mov     rcx, rsi
0x180025315  mov     rax, [rax]
0x180025318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002531d  mov     eax, ebx
0x18002531f  lock xadd [rsi+0Ch], eax
0x180025324  add     eax, ebx
0x180025326  jnz     short loc_180025337
0x180025328  mov     rax, [rsi]
0x18002532b  mov     rcx, rsi
0x18002532e  mov     rax, [rax+8]
0x180025332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025337  mov     rcx, [rdi]
0x18002533a  mov     rax, [rcx]
0x18002533d  mov     rax, [rax]
0x180025340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025345  lea     r8, [rbp+57h+var_48]
0x180025349  lea     rdx, [rbp+57h+var_58]
0x18002534d  mov     rcx, r14
0x180025350  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ADPDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ADPDatabase>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180025355  mov     rdx, [rax]
0x180025358  mov     rax, [rdi+8]
0x18002535c  test    rax, rax
0x18002535f  jz      short loc_180025365
0x180025361  lock inc dword ptr [rax+8]
0x180025365  mov     rcx, [rdi+8]
0x180025369  mov     rax, [rdi]
0x18002536c  mov     [rdx+30h], rax
0x180025370  mov     rsi, [rdx+38h]
0x180025374  mov     [rdx+38h], rcx
0x180025378  test    rsi, rsi
0x18002537b  jz      short loc_1800253B1
0x18002537d  mov     eax, ebx
0x18002537f  lock xadd [rsi+8], eax
0x180025384  add     eax, ebx
0x180025386  jnz     short loc_1800253B1
0x180025388  mov     rax, [rsi]
0x18002538b  mov     rcx, rsi
0x18002538e  mov     rax, [rax]
0x180025391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025396  mov     eax, ebx
0x180025398  lock xadd [rsi+0Ch], eax
0x18002539d  add     eax, ebx
0x18002539f  jnz     short loc_1800253B1
0x1800253a1  mov     rax, [rsi]
0x1800253a4  mov     rcx, rsi
0x1800253a7  mov     rax, [rax+8]
0x1800253ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b0  nop
0x1800253b1  lea     rcx, [rbp+57h+var_48]
0x1800253b5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800253ba  nop
0x1800253bb  test    r15, r15
0x1800253be  jz      short loc_1800253C9
0x1800253c0  mov     rcx, r15; SRWLock
0x1800253c3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800253c9  mov     rax, rdi
0x1800253cc  mov     rcx, [rbp+57h+var_28]
0x1800253d0  xor     rcx, rsp; StackCookie
0x1800253d3  call    __security_check_cookie
0x1800253d8  mov     rbx, [rsp+0B0h+arg_18]
0x1800253e0  add     rsp, 90h
0x1800253e7  pop     r15
0x1800253e9  pop     r14
0x1800253eb  pop     rdi
0x1800253ec  pop     rsi
0x1800253ed  pop     rbp
0x1800253ee  retn
0x1800253ef  mov     rcx, [rbp+5Fh]; this
0x1800253f3  lea     r9, aInvalidDatabas_0; "Invalid database name"
0x1800253fa  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180025401  mov     edx, 0A4h; void *
0x180025406  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
