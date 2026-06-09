# Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources(uint *,HSTRING__ * * *)

- ea: `0x180049750`
- end: `0x1800499bb`
- name: `?GetRegisteredPathResources@IsolationEnvironment@1AI@Windows@@UEAAJPEAIPEAPEAPEAUHSTRING__@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, unsigned int *, HSTRING **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a464`
- `0x180011e18`
- `0x180013230`
- `0x18001355c`
- `0x180020d48`
- `0x180032e60`
- `0x18003ca08`
- `0x180045bd0`
- `0x180048c30`
- `0x180048edc`
- `0x180049750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800497ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049979`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800497ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049979`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800498a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004995d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800498a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004995d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049864`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800498f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800498f4`

## string_xrefs

- `0x18004979b`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x1800497ce`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004987a`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049999`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004983e`: `No registered paths found for agent user %s`
- `0x18004992f`: `Retrieved %u registered paths for agent user %s`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        unsigned int *a2,
        HSTRING **a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v9; // eax
  __int64 v10; // rcx
  RTL_SRWLOCK *v11; // rcx
  _QWORD *v12; // rbx
  _QWORD *v13; // rdi
  _QWORD *OwningUserRegistry; // rax
  __int64 v15; // rsi
  HSTRING *v16; // rdx
  void *v17; // rcx
  __int64 v18; // rax
  HSTRING *v19; // r8
  __int64 *v20; // rcx
  UINT32 v21; // edx
  HRESULT String; // eax
  void *v23; // rcx
  RTL_SRWLOCK *v24; // rcx
  int v25; // [rsp+20h] [rbp-40h]
  const char *v26; // [rsp+28h] [rbp-38h]
  __int64 v27; // [rsp+30h] [rbp-30h] BYREF
  __int64 v28; // [rsp+38h] [rbp-28h]
  _QWORD v29[2]; // [rsp+48h] [rbp-18h] BYREF
  char v30; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v32; // [rsp+98h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  v7 = CheckCallingProcessCohort(0, 0);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)v7,
      (int)"Calling user is not in a supported cohort",
      v26);
    return v7;
  }
  checked_srwlock::lock_shared(v6, &SRWLock);
  v9 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(this);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v9,
      v25);
LABEL_6:
    v11 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
      ReleaseSRWLockShared(v11);
    }
    return v7;
  }
  v12 = (_QWORD *)*((_QWORD *)this + 6);
  v13 = v12 + 18;
  OwningUserRegistry = (_QWORD *)AgentAccountRegistry::GetOrCreateOwningUserRegistry(
                                   v10,
                                   *(_QWORD *)(*((_QWORD *)this + 8) + 40LL) + 16LL,
                                   *(_QWORD *)(*((_QWORD *)this + 8) + 40LL) + 48LL);
  OwningUserRegistry::RecallAgentSharedPaths(OwningUserRegistry, &v27, v12 + 14);
  if ( v27 != v28 )
  {
    v15 = (unsigned int)((v28 - v27) >> 5);
    pv = CoTaskMemAlloc(8 * v15);
    v16 = (HSTRING *)pv;
    if ( pv )
    {
      v32 = 0;
      v29[0] = &pv;
      v29[1] = &v32;
      v30 = 1;
      if ( !(_DWORD)v15 )
      {
LABEL_23:
        *a2 = v15;
        *a3 = v16;
        pv = 0;
        if ( v13[3] > 7u )
          v13 = (_QWORD *)*v13;
        Log(4u, L"Retrieved %u registered paths for agent user %s", *a2, v13);
        wil::details::lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___::_lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___(v29);
        v23 = pv;
        pv = 0;
        if ( v23 )
          CoTaskMemFree(v23);
        goto LABEL_27;
      }
      v18 = 0;
      while ( 1 )
      {
        v19 = &v16[v18];
        v20 = (__int64 *)(v27 + 32LL * (unsigned int)v18);
        v21 = *((_DWORD *)v20 + 4);
        if ( (unsigned __int64)v20[3] > 7 )
          v20 = (__int64 *)*v20;
        String = WindowsCreateString((PCNZWCH)v20, v21, v19);
        v7 = String;
        if ( String < 0 )
          break;
        v16 = (HSTRING *)pv;
        v18 = (unsigned int)(v32 + 1);
        v32 = v18;
        if ( (unsigned int)v18 >= (unsigned int)v15 )
          goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)(unsigned int)String,
        v25);
      wil::details::lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___::_lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___(v29);
    }
    else
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C8,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)0x8007000ELL,
        v25);
    }
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    std::vector<std::wstring>::~vector<std::wstring>(&v27);
    goto LABEL_6;
  }
  if ( v12[21] > 7u )
    v13 = (_QWORD *)*v13;
  Log(4u, L"No registered paths found for agent user %s", v13);
LABEL_27:
  std::vector<std::wstring>::~vector<std::wstring>(&v27);
  v24 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
    ReleaseSRWLockShared(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180049750  mov     [rsp-28h+arg_0], rbx
0x180049755  push    rbp
0x180049756  push    rsi
0x180049757  push    rdi
0x180049758  push    r14
0x18004975a  push    r15
0x18004975c  mov     rbp, rsp
0x18004975f  sub     rsp, 60h
0x180049763  mov     dword ptr [rdx], 0
0x180049769  mov     r14, rdx
0x18004976c  mov     rsi, rcx
0x18004976f  mov     qword ptr [r8], 0
0x180049776  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180049778  xor     ecx, ecx; bool
0x18004977a  mov     r15, r8
0x18004977d  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180049782  mov     ebx, eax
0x180049784  test    eax, eax
0x180049786  jns     short loc_1800497B3
0x180049788  mov     rcx, [rbp+28h]; this
0x18004978c  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180049793  mov     r9d, ebx; char *
0x180049796  mov     qword ptr [rsp+60h+var_40], rax; int
0x18004979b  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800497a2  mov     edx, 1B4h; void *
0x1800497a7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800497ac  mov     eax, ebx
0x1800497ae  jmp     loc_180049981
0x1800497b3  lea     rdx, [rbp+SRWLock]
0x1800497b7  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x1800497bc  mov     rcx, rsi; this
0x1800497bf  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x1800497c4  mov     ebx, eax
0x1800497c6  test    eax, eax
0x1800497c8  jns     short loc_1800497F7
0x1800497ca  mov     rcx, [rbp+28h]; this
0x1800497ce  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800497d5  mov     r9d, eax; char *
0x1800497d8  mov     edx, 1B8h; void *
0x1800497dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800497e2  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800497e6  test    rcx, rcx
0x1800497e9  jz      short loc_1800497AC
0x1800497eb  lock dec dword ptr [rcx+0Ch]
0x1800497ef  call    cs:__imp_ReleaseSRWLockShared
0x1800497f5  jmp     short loc_1800497AC
0x1800497f7  mov     rax, [rsi+40h]
0x1800497fb  mov     rbx, [rsi+30h]
0x1800497ff  mov     rdx, [rax+28h]
0x180049803  lea     rdi, [rbx+90h]
0x18004980a  lea     r8, [rdx+30h]
0x18004980e  add     rdx, 10h
0x180049812  call    ?GetOrCreateOwningUserRegistry@AgentAccountRegistry@@QEAAAEAVOwningUserRegistry@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; AgentAccountRegistry::GetOrCreateOwningUserRegistry(std::wstring const &,std::wstring const &)
0x180049817  lea     r8, [rbx+70h]
0x18004981b  mov     rcx, rax
0x18004981e  lea     rdx, [rbp+var_30]
0x180049822  call    ?RecallAgentSharedPaths@OwningUserRegistry@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; OwningUserRegistry::RecallAgentSharedPaths(std::wstring const &)
0x180049827  mov     rax, [rbp+var_28]
0x18004982b  cmp     [rbp+var_30], rax
0x18004982f  jnz     short loc_180049854
0x180049831  cmp     qword ptr [rdi+18h], 7
0x180049836  jbe     short loc_18004983B
0x180049838  mov     rdi, [rdi]
0x18004983b  mov     r8, rdi
0x18004983e  lea     rdx, aNoRegisteredPa; "No registered paths found for agent use"...
0x180049845  mov     ecx, 4; unsigned __int8
0x18004984a  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004984f  jmp     loc_180049963
0x180049854  sub     rax, [rbp+var_30]
0x180049858  sar     rax, 5
0x18004985c  mov     ecx, eax
0x18004985e  shl     rcx, 3; cb
0x180049862  mov     esi, eax
0x180049864  call    cs:__imp_CoTaskMemAlloc
0x18004986a  mov     [rbp+pv], rax
0x18004986e  mov     rdx, rax
0x180049871  test    rax, rax
0x180049874  jnz     short loc_1800498B8
0x180049876  mov     rcx, [rbp+28h]; this
0x18004987a  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049881  mov     ebx, 8007000Eh
0x180049886  mov     edx, 1C8h; void *
0x18004988b  mov     r9d, ebx; char *
0x18004988e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049893  mov     rcx, [rbp+pv]; pv
0x180049897  mov     [rbp+pv], 0
0x18004989f  test    rcx, rcx
0x1800498a2  jz      short loc_1800498AA
0x1800498a4  call    cs:__imp_CoTaskMemFree
0x1800498aa  lea     rcx, [rbp+var_30]
0x1800498ae  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800498b3  jmp     loc_1800497E2
0x1800498b8  mov     [rbp+arg_8], 0
0x1800498bf  lea     rax, [rbp+pv]
0x1800498c3  mov     [rbp+var_18], rax
0x1800498c7  lea     rax, [rbp+arg_8]
0x1800498cb  mov     [rbp+var_10], rax
0x1800498cf  mov     [rbp+var_8], 1
0x1800498d3  test    esi, esi
0x1800498d5  jz      short loc_180049914
0x1800498d7  xor     eax, eax
0x1800498d9  mov     ecx, eax
0x1800498db  lea     r8, [rdx+rax*8]; string
0x1800498df  shl     rcx, 5
0x1800498e3  add     rcx, [rbp+var_30]
0x1800498e7  cmp     qword ptr [rcx+18h], 7
0x1800498ec  mov     edx, [rcx+10h]; length
0x1800498ef  jbe     short loc_1800498F4
0x1800498f1  mov     rcx, [rcx]; sourceString
0x1800498f4  call    cs:__imp_WindowsCreateString
0x1800498fa  mov     ebx, eax
0x1800498fc  test    eax, eax
0x1800498fe  js      loc_180049995
0x180049904  mov     eax, [rbp+arg_8]
0x180049907  mov     rdx, [rbp+pv]
0x18004990b  inc     eax
0x18004990d  mov     [rbp+arg_8], eax
0x180049910  cmp     eax, esi
0x180049912  jb      short loc_1800498D9
0x180049914  mov     [r14], esi
0x180049917  mov     [r15], rdx
0x18004991a  mov     [rbp+pv], 0
0x180049922  cmp     qword ptr [rdi+18h], 7
0x180049927  jbe     short loc_18004992C
0x180049929  mov     rdi, [rdi]
0x18004992c  mov     r8d, [r14]
0x18004992f  lea     rdx, aRetrievedURegi; "Retrieved %u registered paths for agent"...
0x180049936  mov     r9, rdi
0x180049939  mov     ecx, 4; unsigned __int8
0x18004993e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180049943  lea     rcx, [rbp+var_18]
0x180049947  call    wil__details__lambda_call__Windows__AI__IsolationEnvironment__IsolationEnvironment__GetRegisteredPathResources____2____lambda_1______lambda_call__Windows__AI__IsolationEnvironment__IsolationEnvironment__GetRegisteredPathResources____2____lambda_1___
0x18004994c  mov     rcx, [rbp+pv]; pv
0x180049950  mov     [rbp+pv], 0
0x180049958  test    rcx, rcx
0x18004995b  jz      short loc_180049963
0x18004995d  call    cs:__imp_CoTaskMemFree
0x180049963  lea     rcx, [rbp+var_30]
0x180049967  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18004996c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180049970  test    rcx, rcx
0x180049973  jz      short loc_18004997F
0x180049975  lock dec dword ptr [rcx+0Ch]
0x180049979  call    cs:__imp_ReleaseSRWLockShared
0x18004997f  xor     eax, eax
0x180049981  mov     rbx, [rsp+60h+arg_0]
0x180049989  add     rsp, 60h
0x18004998d  pop     r15
0x18004998f  pop     r14
0x180049991  pop     rdi
0x180049992  pop     rsi
0x180049993  pop     rbp
0x180049994  retn
0x180049995  mov     rcx, [rbp+28h]; this
0x180049999  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800499a0  mov     r9d, ebx; char *
0x1800499a3  mov     edx, 1D9h; void *
0x1800499a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800499ad  lea     rcx, [rbp+var_18]
0x1800499b1  call    wil__details__lambda_call__Windows__AI__IsolationEnvironment__IsolationEnvironment__GetRegisteredPathResources____2____lambda_1______lambda_call__Windows__AI__IsolationEnvironment__IsolationEnvironment__GetRegisteredPathResources____2____lambda_1___
0x1800499b6  jmp     loc_180049893
```
