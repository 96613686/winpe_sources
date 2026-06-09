# CHandlerCache::s_RefreshHandlerThreadProc(void *)

- ea: `0x1800047d0`
- end: `0x180004a4e`
- name: `?s_RefreshHandlerThreadProc@CHandlerCache@@CAKPEAX@Z`
- size: `638`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800047d0`
- `0x180004a60`
- `0x180004c70`
- `0x180005d30`
- `0x1800074a4`
- `0x1800074e8`
- `0x180009940`
- `0x180015af8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000493d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800049b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800049b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000493d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800049b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800049b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004834`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800048a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004834`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800048a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004828`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004828`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180004992`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180004992`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000492a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000492a`

## pseudocode

```c
__int64 __fastcall CHandlerCache::s_RefreshHandlerThreadProc(WCHAR *Parameter, __int64 a2, int a3)
{
  int v4; // ebp
  int Instance; // eax
  LPCRITICAL_SECTION v6; // rdi
  HANDLE *p_OwningThread; // rbx
  DWORD v8; // r12d
  _DWORD *p_Type; // rcx
  int v10; // r15d
  int v11; // ecx
  __int64 (__fastcall *v12)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD); // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  __int64 v14; // rsi
  int *v15; // rax
  int v16; // r14d
  __int64 (__fastcall *v17)(__int64, _QWORD); // rax
  __int64 v18; // rbx
  __int64 v19; // rbx
  __int32 v20; // esi
  int SpinCount_high; // ebx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  lpCriticalSection = 0;
  Instance = CHandlerCache::s_GetInstance((struct CHandlerCache **)&lpCriticalSection, 1, a3);
  v6 = lpCriticalSection;
  if ( Instance >= 0 )
  {
    p_OwningThread = &lpCriticalSection[10].OwningThread;
    do
    {
      v8 = WaitForSingleObject(*p_OwningThread, 0);
      EnterCriticalSection(v6);
      p_Type = &v6[1].DebugInfo->Type;
      if ( p_Type )
      {
        v10 = *p_Type;
        v11 = 0;
        LODWORD(lpCriticalSection) = 0;
        if ( v10 > 0 )
        {
          while ( 2 )
          {
            v12 = (__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))qword_1800701D0;
            DebugInfo = v6[1].DebugInfo;
            if ( qword_1800701D0 == -1 )
            {
              GetProcFromComCtl32(&qword_1800701D0, 332);
              v12 = (__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))qword_1800701D0;
              v11 = (int)lpCriticalSection;
            }
            if ( v12 )
              v14 = v12(DebugInfo, v11);
            else
              v14 = 0;
            EnterCriticalSection(*(LPCRITICAL_SECTION *)(v14 + 48));
            v15 = *(int **)(v14 + 40);
            if ( v15 )
              v16 = *v15;
            else
              v16 = 0;
            while ( v4 < v16 )
            {
              v17 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
              v18 = *(_QWORD *)(v14 + 40);
              if ( qword_1800701D0 == -1 )
              {
                GetProcFromComCtl32(&qword_1800701D0, 332);
                v17 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
              }
              if ( v17 )
                v19 = v17(v18, v4);
              else
                v19 = 0;
              if ( CompareStringW(0x7Fu, 1u, Parameter + 8, -1, (PCNZWCH)(v19 + 116), -1) == 2 )
              {
                _InterlockedIncrement((volatile signed __int32 *)(v19 + 2076));
                LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v14 + 48));
                LeaveCriticalSection(v6);
                CHandlerInfo::Init((CHandlerInfo *)v19, 0);
                CHandlerInfo::Release((CHandlerInfo *)v19);
                goto LABEL_27;
              }
              ++v4;
            }
            LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v14 + 48));
            v4 = 0;
            v11 = (_DWORD)lpCriticalSection + 1;
            LODWORD(lpCriticalSection) = v11;
            if ( v11 < v10 )
              continue;
            break;
          }
          p_OwningThread = &v6[10].OwningThread;
        }
      }
      LeaveCriticalSection(v6);
      if ( v8 != 258 )
        break;
      LODWORD(lpCriticalSection) = 0;
    }
    while ( CoWaitForMultipleHandles(0, 0x1F4u, 1u, p_OwningThread, (LPDWORD)&lpCriticalSection) != -2147024809 );
LABEL_27:
    CHandlerCache::_UpdateAggregateStatus((CHandlerCache *)v6);
  }
  _InterlockedDecrement((volatile signed __int32 *)&v6[9].SpinCount + 1);
  v20 = _InterlockedExchange((volatile __int32 *)&v6[9].SpinCount + 1, HIDWORD(v6[9].SpinCount));
  EnterCriticalSection(v6);
  SpinCount_high = HIDWORD(v6[2].SpinCount);
  LeaveCriticalSection(v6);
  if ( SpinCount_high <= 1 && !v20 )
    CHandlerCache::_Shutdown((CHandlerCache *)v6);
  if ( Parameter )
    CZeroInitNew::operator delete(Parameter);
  return 1;
}

```

## disassembly

```asm
0x1800047d0  push    r13
0x1800047d2  sub     rsp, 50h
0x1800047d6  mov     [rsp+58h+arg_8], rbx
0x1800047db  mov     r13, rcx
0x1800047de  mov     [rsp+58h+arg_10], rbp
0x1800047e3  lea     rcx, [rsp+58h+lpCriticalSection]; struct CHandlerCache **
0x1800047e8  xor     ebp, ebp
0x1800047ea  mov     [rsp+58h+arg_18], rsi
0x1800047ef  mov     dl, 1; bool
0x1800047f1  mov     [rsp+58h+lpCriticalSection], rbp
0x1800047f6  mov     [rsp+58h+var_10], rdi
0x1800047fb  call    ?s_GetInstance@CHandlerCache@@SAJPEAPEAV1@_N@Z; CHandlerCache::s_GetInstance(CHandlerCache * *,bool)
0x180004800  mov     rdi, [rsp+58h+lpCriticalSection]
0x180004805  test    eax, eax
0x180004807  js      loc_1800049E8
0x18000480d  mov     [rsp+58h+var_18], r12
0x180004812  lea     rbx, [rdi+1A0h]
0x180004819  mov     [rsp+58h+var_20], r14
0x18000481e  mov     [rsp+58h+var_28], r15
0x180004823  mov     rcx, [rbx]; hHandle
0x180004826  xor     edx, edx; dwMilliseconds
0x180004828  call    cs:__imp_WaitForSingleObject
0x18000482e  mov     rcx, rdi; lpCriticalSection
0x180004831  mov     r12d, eax
0x180004834  call    cs:__imp_EnterCriticalSection
0x18000483a  mov     rcx, [rdi+28h]
0x18000483e  test    rcx, rcx
0x180004841  jz      loc_180004962
0x180004847  mov     r15d, [rcx]
0x18000484a  mov     ecx, ebp
0x18000484c  mov     dword ptr [rsp+58h+lpCriticalSection], ecx
0x180004850  test    r15d, r15d
0x180004853  jle     loc_180004962
0x180004859  mov     rax, cs:qword_1800701D0
0x180004860  mov     rbx, [rdi+28h]
0x180004864  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004868  jnz     short loc_180004886
0x18000486a  mov     edx, 14Ch
0x18000486f  lea     rcx, qword_1800701D0
0x180004876  call    _GetProcFromComCtl32
0x18000487b  mov     rax, cs:qword_1800701D0
0x180004882  mov     ecx, dword ptr [rsp+58h+lpCriticalSection]
0x180004886  test    rax, rax
0x180004889  jz      short loc_18000489B
0x18000488b  movsxd  rdx, ecx
0x18000488e  mov     rcx, rbx
0x180004891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004896  mov     rsi, rax
0x180004899  jmp     short loc_18000489E
0x18000489b  mov     rsi, rbp
0x18000489e  mov     rcx, [rsi+30h]; lpCriticalSection
0x1800048a2  call    cs:__imp_EnterCriticalSection
0x1800048a8  mov     rax, [rsi+28h]
0x1800048ac  test    rax, rax
0x1800048af  jz      short loc_1800048B6
0x1800048b1  mov     r14d, [rax]
0x1800048b4  jmp     short loc_1800048C0
0x1800048b6  mov     r14d, ebp
0x1800048b9  nop     dword ptr [rax+00000000h]
0x1800048c0  cmp     ebp, r14d
0x1800048c3  jge     short loc_180004939
0x1800048c5  mov     rax, cs:qword_1800701D0
0x1800048cc  mov     rbx, [rsi+28h]
0x1800048d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800048d4  jnz     short loc_1800048EE
0x1800048d6  mov     edx, 14Ch
0x1800048db  lea     rcx, qword_1800701D0
0x1800048e2  call    _GetProcFromComCtl32
0x1800048e7  mov     rax, cs:qword_1800701D0
0x1800048ee  test    rax, rax
0x1800048f1  jz      short loc_180004903
0x1800048f3  movsxd  rdx, ebp
0x1800048f6  mov     rcx, rbx
0x1800048f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048fe  mov     rbx, rax
0x180004901  jmp     short loc_180004905
0x180004903  xor     ebx, ebx
0x180004905  lea     rax, [rbx+74h]
0x180004909  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180004911  lea     r8, [r13+10h]; lpString1
0x180004915  mov     [rsp+58h+lpString2], rax; lpString2
0x18000491a  mov     edx, 1; dwCmpFlags
0x18000491f  mov     r9d, 0FFFFFFFFh; cchCount1
0x180004925  mov     ecx, 7Fh; Locale
0x18000492a  call    cs:__imp_CompareStringW
0x180004930  cmp     eax, 2
0x180004933  jz      short loc_1800049A5
0x180004935  inc     ebp
0x180004937  jmp     short loc_1800048C0
0x180004939  mov     rcx, [rsi+30h]; lpCriticalSection
0x18000493d  call    cs:__imp_LeaveCriticalSection
0x180004943  mov     ecx, dword ptr [rsp+58h+lpCriticalSection]
0x180004947  mov     ebp, 0
0x18000494c  inc     ecx
0x18000494e  mov     dword ptr [rsp+58h+lpCriticalSection], ecx
0x180004952  cmp     ecx, r15d
0x180004955  jl      loc_180004859
0x18000495b  lea     rbx, [rdi+1A0h]
0x180004962  mov     rcx, rdi; lpCriticalSection
0x180004965  call    cs:__imp_LeaveCriticalSection
0x18000496b  cmp     r12d, 102h
0x180004972  jnz     short loc_1800049D1
0x180004974  lea     rax, [rsp+58h+lpCriticalSection]
0x180004979  mov     dword ptr [rsp+58h+lpCriticalSection], ebp
0x18000497d  mov     r9, rbx; pHandles
0x180004980  mov     [rsp+58h+lpString2], rax; lpdwindex
0x180004985  mov     edx, 1F4h; dwTimeout
0x18000498a  mov     r8d, 1; cHandles
0x180004990  xor     ecx, ecx; dwFlags
0x180004992  call    cs:__imp_CoWaitForMultipleHandles
0x180004998  cmp     eax, 80070057h
0x18000499d  jnz     loc_180004823
0x1800049a3  jmp     short loc_1800049D1
0x1800049a5  lock inc dword ptr [rbx+81Ch]
0x1800049ac  mov     rcx, [rsi+30h]; lpCriticalSection
0x1800049b0  call    cs:__imp_LeaveCriticalSection
0x1800049b6  mov     rcx, rdi; lpCriticalSection
0x1800049b9  call    cs:__imp_LeaveCriticalSection
0x1800049bf  xor     edx, edx; struct ISyncMgrHandlerCollection *
0x1800049c1  mov     rcx, rbx; this
0x1800049c4  call    ?Init@CHandlerInfo@@QEAAJPEAUISyncMgrHandlerCollection@@@Z; CHandlerInfo::Init(ISyncMgrHandlerCollection *)
0x1800049c9  mov     rcx, rbx; this
0x1800049cc  call    ?Release@CHandlerInfo@@QEAAKXZ; CHandlerInfo::Release(void)
0x1800049d1  mov     rcx, rdi; this
0x1800049d4  call    ?_UpdateAggregateStatus@CHandlerCache@@AEAAXXZ; CHandlerCache::_UpdateAggregateStatus(void)
0x1800049d9  mov     r15, [rsp+58h+var_28]
0x1800049de  mov     r14, [rsp+58h+var_20]
0x1800049e3  mov     r12, [rsp+58h+var_18]
0x1800049e8  lock dec dword ptr [rdi+18Ch]
0x1800049ef  mov     rcx, rdi; lpCriticalSection
0x1800049f2  mov     esi, [rdi+18Ch]
0x1800049f8  xchg    esi, [rdi+18Ch]
0x1800049fe  call    cs:__imp_EnterCriticalSection
0x180004a04  mov     ebx, [rdi+74h]
0x180004a07  mov     rcx, rdi; lpCriticalSection
0x180004a0a  call    cs:__imp_LeaveCriticalSection
0x180004a10  mov     rbp, [rsp+58h+arg_10]
0x180004a15  cmp     ebx, 1
0x180004a18  mov     rbx, [rsp+58h+arg_8]
0x180004a1d  jg      short loc_180004A2B
0x180004a1f  test    esi, esi
0x180004a21  jnz     short loc_180004A2B
0x180004a23  mov     rcx, rdi; this
0x180004a26  call    ?_Shutdown@CHandlerCache@@AEAAXXZ; CHandlerCache::_Shutdown(void)
0x180004a2b  mov     rdi, [rsp+58h+var_10]
0x180004a30  mov     rsi, [rsp+58h+arg_18]
0x180004a35  test    r13, r13
0x180004a38  jz      short loc_180004A42
0x180004a3a  mov     rcx, r13; lpMem
0x180004a3d  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180004a42  mov     eax, 1
0x180004a47  add     rsp, 50h
0x180004a4b  pop     r13
0x180004a4d  retn
```
