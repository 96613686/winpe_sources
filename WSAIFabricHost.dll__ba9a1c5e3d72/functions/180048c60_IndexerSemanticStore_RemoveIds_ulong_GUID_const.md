# IndexerSemanticStore::RemoveIds(ulong,_GUID const *)

- ea: `0x180048c60`
- end: `0x180048f1d`
- name: `?RemoveIds@IndexerSemanticStore@@UEAAJKPEBU_GUID@@@Z`
- size: `701`
- prototype: `int(IndexerSemanticStore *__hidden this, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004ca0`
- `0x1800187b0`
- `0x180019c3c`
- `0x18002b39c`
- `0x18002b7fc`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x180032300`
- `0x1800326e8`
- `0x180048c60`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048de4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048e63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048de4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048eb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048eb9`

## string_xrefs

- `0x180048ca4`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180048c98`: `RemoveIds : idCount: %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IndexerSemanticStore::RemoveIds(IndexerSemanticStore *this, unsigned int a2, const struct _GUID *a3)
{
  __int64 v4; // r12
  unsigned int i; // r15d
  unsigned __int8 v7; // cl
  unsigned __int8 v8; // dl
  unsigned __int8 v9; // r8
  unsigned __int8 v10; // r9
  unsigned __int8 v11; // r10
  unsigned __int8 v12; // r11
  unsigned __int8 v13; // bl
  unsigned __int8 v14; // di
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  _DWORD *v20; // rbx
  struct _RTL_CRITICAL_SECTION *v21; // rdi
  struct _RTL_CRITICAL_SECTION *v22; // rbx
  const char *v23; // r9
  __int64 result; // rax
  __int128 v25; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-98h]
  _BYTE v27[8]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v28[48]; // [rsp+48h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-50h]
  _BYTE v30[24]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = a2;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0x91C,
    (unsigned int)L"RemoveIds : idCount: %lu",
    (const wchar_t *)a2);
  try
  {
    v25 = 0;
    v26 = 0;
    *(_QWORD *)v30 = v4;
    if ( (_DWORD)v4 )
      std::vector<winrt::guid>::_Reallocate<0>(&v25, v30);
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      v7 = a3[i].Data4[0];
      v8 = a3[i].Data4[1];
      v9 = a3[i].Data4[2];
      v10 = a3[i].Data4[3];
      v11 = a3[i].Data4[4];
      v12 = a3[i].Data4[5];
      v13 = a3[i].Data4[6];
      v14 = a3[i].Data4[7];
      *(_QWORD *)v30 = *(_QWORD *)&a3[i].Data1;
      v30[8] = v7;
      v30[9] = v8;
      v30[10] = v9;
      v30[11] = v10;
      v30[12] = v11;
      v30[13] = v12;
      v30[14] = v13;
      v30[15] = v14;
      if ( *((_QWORD *)&v25 + 1) == v26 )
      {
        std::vector<winrt::guid>::_Emplace_reallocate<winrt::guid>(&v25, *((_QWORD *)&v25 + 1), v30);
      }
      else
      {
        **((_OWORD **)&v25 + 1) = *(_OWORD *)v30;
        *((_QWORD *)&v25 + 1) += 16LL;
      }
    }
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v27);
    v15 = (struct _RTL_CRITICAL_SECTION *)pv;
    *(_QWORD *)v30 = pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v15 + 5);
    ++LODWORD(v15[6].DebugInfo);
    LODWORD(v15[6].SpinCount) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)v30);
    v16 = (__int64)(*((_QWORD *)&v25 + 1) - v25) >> 4;
    v17 = *((_QWORD *)this + 4);
    *(_DWORD *)v30 = 0;
    *(_OWORD *)&v30[8] = 0;
    v18 = 4;
    if ( (_DWORD)v16 )
      v18 = v25;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v17 + 136LL))(v17, v16, v18);
    if ( v19 < 0 )
      winrt::throw_hresult((unsigned int)v19, v30);
    v20 = pv;
    v21 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v20[18] |= 0x300u;
    if ( *((_QWORD *)v20 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v20 + 2, 2);
    if ( v21 )
      LeaveCriticalSection(v21);
    v22 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v22);
      CoTaskMemFree(v22);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v28);
    std::vector<winrt::guid>::~vector<winrt::guid>(&v25);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x92B,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x180048c60  mov     [rsp+arg_10], rbx
0x180048c65  mov     [rsp+arg_18], rsi
0x180048c6a  push    rdi
0x180048c6b  push    r12
0x180048c6d  push    r13
0x180048c6f  push    r14
0x180048c71  push    r15
0x180048c73  sub     rsp, 0A0h
0x180048c7a  mov     rax, cs:__security_cookie
0x180048c81  xor     rax, rsp
0x180048c84  mov     [rsp+0C8h+var_30], rax
0x180048c8c  mov     r14, r8
0x180048c8f  mov     r12d, edx
0x180048c92  mov     r13, rcx
0x180048c95  mov     r9d, r12d; wchar_t *
0x180048c98  lea     r8, aRemoveidsIdcou; "RemoveIds : idCount: %lu"
0x180048c9f  mov     edx, 91Ch; wchar_t *
0x180048ca4  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180048cab  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180048cb0  xorps   xmm0, xmm0
0x180048cb3  movdqu  [rsp+0C8h+var_A8], xmm0
0x180048cb9  mov     [rsp+0C8h+var_98], 0
0x180048cc2  mov     qword ptr [rsp+0C8h+var_48], r12
0x180048cca  test    r12d, r12d
0x180048ccd  jz      short loc_180048CE1
0x180048ccf  lea     rdx, [rsp+0C8h+var_48]
0x180048cd7  lea     rcx, [rsp+0C8h+var_A8]
0x180048cdc  call    ??$_Reallocate@$0A@@?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@AEAAXAEA_K@Z; std::vector<winrt::guid>::_Reallocate<0>(unsigned __int64 &)
0x180048ce1  xor     r15d, r15d
0x180048ce4  cmp     r15d, r12d
0x180048ce7  jnb     loc_180048DB9
0x180048ced  mov     esi, r15d
0x180048cf0  add     rsi, rsi
0x180048cf3  mov     cl, [r14+rsi*8+8]
0x180048cf8  mov     dl, [r14+rsi*8+9]
0x180048cfd  mov     r8b, [r14+rsi*8+0Ah]
0x180048d02  mov     r9b, [r14+rsi*8+0Bh]
0x180048d07  mov     r10b, [r14+rsi*8+0Ch]
0x180048d0c  mov     r11b, [r14+rsi*8+0Dh]
0x180048d11  mov     bl, [r14+rsi*8+0Eh]
0x180048d16  mov     dil, [r14+rsi*8+0Fh]
0x180048d1b  mov     eax, [r14+rsi*8]
0x180048d1f  mov     dword ptr [rsp+0C8h+var_48], eax
0x180048d26  movzx   eax, word ptr [r14+rsi*8+4]
0x180048d2c  mov     word ptr [rsp+0C8h+var_48+4], ax
0x180048d34  movzx   eax, word ptr [r14+rsi*8+6]
0x180048d3a  mov     word ptr [rsp+0C8h+var_48+6], ax
0x180048d42  mov     [rsp+0C8h+var_48+8], cl
0x180048d49  mov     [rsp+0C8h+var_48+9], dl
0x180048d50  mov     [rsp+0C8h+var_48+0Ah], r8b
0x180048d58  mov     [rsp+0C8h+var_48+0Bh], r9b
0x180048d60  mov     [rsp+0C8h+var_48+0Ch], r10b
0x180048d68  mov     [rsp+0C8h+var_48+0Dh], r11b
0x180048d70  mov     [rsp+0C8h+var_48+0Eh], bl
0x180048d77  mov     [rsp+0C8h+var_48+0Fh], dil
0x180048d7f  mov     rdx, qword ptr [rsp+0C8h+var_A8+8]
0x180048d84  cmp     rdx, [rsp+0C8h+var_98]
0x180048d89  jz      short loc_180048D9F
0x180048d8b  movups  xmm0, xmmword ptr [rsp+0C8h+var_48]
0x180048d93  movdqu  xmmword ptr [rdx], xmm0
0x180048d97  add     qword ptr [rsp+0C8h+var_A8+8], 10h
0x180048d9d  jmp     short loc_180048DB1
0x180048d9f  lea     r8, [rsp+0C8h+var_48]
0x180048da7  lea     rcx, [rsp+0C8h+var_A8]
0x180048dac  call    ??$_Emplace_reallocate@Uguid@winrt@@@?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@AEAAPEAUguid@winrt@@QEAU23@$$QEAU23@@Z; std::vector<winrt::guid>::_Emplace_reallocate<winrt::guid>(winrt::guid * const,winrt::guid &&)
0x180048db1  inc     r15d
0x180048db4  jmp     loc_180048CE4
0x180048db9  lea     rcx, [rsp+0C8h+var_88]
0x180048dbe  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180048dc3  nop
0x180048dc4  mov     rbx, [rsp+0C8h+pv]
0x180048dc9  mov     qword ptr [rsp+0C8h+var_48], rbx
0x180048dd1  test    rbx, rbx
0x180048dd4  jz      short loc_180048DDD
0x180048dd6  lock inc dword ptr [rbx+120h]
0x180048ddd  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180048de4  call    cs:__imp_EnterCriticalSection
0x180048dea  inc     dword ptr [rbx+0F0h]
0x180048df0  mov     esi, 2
0x180048df5  mov     [rbx+110h], esi
0x180048dfb  lea     rcx, [rsp+0C8h+var_48]
0x180048e03  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180048e08  mov     rdx, qword ptr [rsp+0C8h+var_A8+8]
0x180048e0d  sub     rdx, qword ptr [rsp+0C8h+var_A8]
0x180048e12  sar     rdx, 4
0x180048e16  mov     rcx, [r13+20h]
0x180048e1a  mov     dword ptr [rsp+0C8h+var_48], 0
0x180048e25  xorps   xmm0, xmm0
0x180048e28  movdqu  xmmword ptr [rsp+0C8h+var_48+8], xmm0
0x180048e31  mov     rax, [rcx]
0x180048e34  lea     r8d, [rsi+2]
0x180048e38  test    edx, edx
0x180048e3a  cmovnz  r8, qword ptr [rsp+0C8h+var_A8]
0x180048e40  mov     rax, [rax+88h]
0x180048e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e4c  test    eax, eax
0x180048e4e  js      loc_180048F0C
0x180048e54  mov     rbx, [rsp+0C8h+pv]
0x180048e59  lea     rdi, [rbx+0C8h]
0x180048e60  mov     rcx, rdi; lpCriticalSection
0x180048e63  call    cs:__imp_EnterCriticalSection
0x180048e69  or      dword ptr [rbx+48h], 300h
0x180048e70  cmp     qword ptr [rbx+0F8h], 0
0x180048e78  jz      short loc_180048E85
0x180048e7a  mov     edx, esi
0x180048e7c  lea     rcx, [rbx+8]
0x180048e80  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180048e85  test    rdi, rdi
0x180048e88  jz      short loc_180048E94
0x180048e8a  mov     rcx, rdi; lpCriticalSection
0x180048e8d  call    cs:__imp_LeaveCriticalSection
0x180048e93  nop
0x180048e94  mov     rbx, [rsp+0C8h+pv]
0x180048e99  test    rbx, rbx
0x180048e9c  jz      short loc_180048EBF
0x180048e9e  or      eax, 0FFFFFFFFh
0x180048ea1  lock xadd [rbx+120h], eax
0x180048ea9  cmp     eax, 1
0x180048eac  jnz     short loc_180048EBF
0x180048eae  mov     rcx, rbx
0x180048eb1  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180048eb6  mov     rcx, rbx; pv
0x180048eb9  call    cs:__imp_CoTaskMemFree
0x180048ebf  lea     rcx, [rsp+0C8h+var_80]; this
0x180048ec4  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180048ec9  nop
0x180048eca  lea     rcx, [rsp+0C8h+var_A8]
0x180048ecf  call    ??1?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::guid>::~vector<winrt::guid>(void)
0x180048ed4  xor     eax, eax
0x180048ed6  jmp     short loc_180048EDF
0x180048ed8  mov     eax, dword ptr [rsp+0C8h+var_48]
0x180048edf  mov     rcx, [rsp+0C8h+var_30]
0x180048ee7  xor     rcx, rsp; StackCookie
0x180048eea  call    __security_check_cookie
0x180048eef  lea     r11, [rsp+0C8h+var_28]
0x180048ef7  mov     rbx, [r11+40h]
0x180048efb  mov     rsi, [r11+48h]
0x180048eff  mov     rsp, r11
0x180048f02  pop     r15
0x180048f04  pop     r14
0x180048f06  pop     r13
0x180048f08  pop     r12
0x180048f0a  pop     rdi
0x180048f0b  retn
0x180048f0c  lea     rdx, [rsp+0C8h+var_48]
0x180048f14  mov     ecx, eax
0x180048f16  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
