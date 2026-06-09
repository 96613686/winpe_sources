# CHandlerCache::_RefreshHandler(CSyncMgrID const &)

- ea: `0x180007284`
- end: `0x18000749e`
- name: `?_RefreshHandler@CHandlerCache@@AEAAJAEBVCSyncMgrID@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct CSyncMgrID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014684`

## callees

- `0x180004a60`
- `0x180005d30`
- `0x180007284`
- `0x1800074a4`
- `0x1800074e8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000740c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000740c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007333`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800072b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800072b1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180007442`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180007442`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800073b9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800073b9`

## pseudocode

```c
__int64 __fastcall CHandlerCache::_RefreshHandler(struct _RTL_CRITICAL_SECTION *this, const struct CSyncMgrID *a2)
{
  HANDLE *p_OwningThread; // r14
  int v4; // ebx
  DWORD v5; // edi
  _DWORD *p_Type; // rcx
  CHandlerInfo *v7; // rbp
  int v8; // r13d
  int v9; // r12d
  __int64 (__fastcall *v10)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD); // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  __int64 v12; // r15
  _DWORD *v13; // rax
  int i; // r14d
  __int64 (__fastcall *v15)(__int64, _QWORD); // rax
  __int64 v16; // rdi
  __int64 v17; // rdi
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF
  const struct CSyncMgrID *v20; // [rsp+78h] [rbp+10h]
  DWORD v21; // [rsp+80h] [rbp+18h]

  v20 = a2;
  p_OwningThread = &this[10].OwningThread;
  v4 = -2147024894;
  while ( 1 )
  {
    v21 = WaitForSingleObject(*p_OwningThread, 0);
    v5 = v21;
    EnterCriticalSection(this);
    p_Type = &this[1].DebugInfo->Type;
    v7 = 0;
    if ( p_Type )
    {
      v8 = *p_Type;
      v9 = 0;
      if ( (int)*p_Type > 0 )
      {
        do
        {
          v10 = (__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))qword_1800701D0;
          DebugInfo = this[1].DebugInfo;
          if ( qword_1800701D0 == -1 )
          {
            GetProcFromComCtl32(&qword_1800701D0, 332);
            v10 = (__int64 (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))qword_1800701D0;
          }
          if ( v10 )
            v12 = v10(DebugInfo, v9);
          else
            v12 = 0;
          v4 = -2147024894;
          v7 = 0;
          EnterCriticalSection(*(LPCRITICAL_SECTION *)(v12 + 48));
          v13 = *(_DWORD **)(v12 + 40);
          if ( v13 )
            LODWORD(v13) = *v13;
          dwindex = (unsigned int)v13;
          for ( i = 0; i < (int)v13; ++i )
          {
            v15 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
            v16 = *(_QWORD *)(v12 + 40);
            if ( qword_1800701D0 == -1 )
            {
              GetProcFromComCtl32(&qword_1800701D0, 332);
              v15 = (__int64 (__fastcall *)(__int64, _QWORD))qword_1800701D0;
            }
            if ( v15 )
              v17 = v15(v16, i);
            else
              v17 = 0;
            if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)v20 + 8, -1, (PCNZWCH)(v17 + 116), -1) == 2 )
            {
              v4 = 0;
              v7 = (CHandlerInfo *)v17;
              _InterlockedIncrement((volatile signed __int32 *)(v17 + 2076));
              break;
            }
            LODWORD(v13) = dwindex;
          }
          LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v12 + 48));
          if ( v4 >= 0 )
            break;
          ++v9;
        }
        while ( v9 < v8 );
        v5 = v21;
        p_OwningThread = &this[10].OwningThread;
      }
    }
    LeaveCriticalSection(this);
    if ( v4 == -2147024894 )
    {
      if ( v5 != 258 )
        goto LABEL_32;
      dwindex = 0;
      if ( CoWaitForMultipleHandles(0, 0x1F4u, 1u, p_OwningThread, &dwindex) == -2147024809 )
      {
        v4 = -2147024809;
        goto LABEL_32;
      }
    }
    if ( v4 >= 0 )
      break;
    if ( v5 != 258 )
      goto LABEL_32;
  }
  v4 = CHandlerInfo::Init(v7, 0);
  CHandlerInfo::Release(v7);
LABEL_32:
  CHandlerCache::_UpdateAggregateStatus((CHandlerCache *)this);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007284  mov     [rsp+arg_18], rbx
0x180007289  mov     [rsp+arg_8], rdx
0x18000728e  push    rbp
0x18000728f  push    rsi
0x180007290  push    rdi
0x180007291  push    r12
0x180007293  push    r13
0x180007295  push    r14
0x180007297  push    r15
0x180007299  sub     rsp, 30h
0x18000729d  mov     rsi, rcx
0x1800072a0  lea     r14, [rcx+1A0h]
0x1800072a7  mov     ebx, 80070002h
0x1800072ac  mov     rcx, [r14]; hHandle
0x1800072af  xor     edx, edx; dwMilliseconds
0x1800072b1  call    cs:__imp_WaitForSingleObject
0x1800072b7  mov     rcx, rsi; lpCriticalSection
0x1800072ba  mov     [rsp+68h+arg_10], eax
0x1800072c1  mov     edi, eax
0x1800072c3  call    cs:__imp_EnterCriticalSection
0x1800072c9  mov     rcx, [rsi+28h]
0x1800072cd  xor     ebp, ebp
0x1800072cf  test    rcx, rcx
0x1800072d2  jz      loc_180007409
0x1800072d8  mov     r13d, [rcx]
0x1800072db  xor     r12d, r12d
0x1800072de  test    r13d, r13d
0x1800072e1  jle     loc_180007409
0x1800072e7  mov     rax, cs:qword_1800701D0
0x1800072ee  mov     rbx, [rsi+28h]
0x1800072f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800072f6  jnz     short loc_180007310
0x1800072f8  mov     edx, 14Ch
0x1800072fd  lea     rcx, qword_1800701D0
0x180007304  call    _GetProcFromComCtl32
0x180007309  mov     rax, cs:qword_1800701D0
0x180007310  test    rax, rax
0x180007313  jz      short loc_180007325
0x180007315  movsxd  rdx, r12d
0x180007318  mov     rcx, rbx
0x18000731b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007320  mov     r15, rax
0x180007323  jmp     short loc_180007328
0x180007325  xor     r15d, r15d
0x180007328  mov     rcx, [r15+30h]; lpCriticalSection
0x18000732c  mov     ebx, 80070002h
0x180007331  xor     ebp, ebp
0x180007333  call    cs:__imp_EnterCriticalSection
0x180007339  mov     rax, [r15+28h]
0x18000733d  test    rax, rax
0x180007340  jz      short loc_180007344
0x180007342  mov     eax, [rax]
0x180007344  mov     [rsp+68h+dwindex], eax
0x180007348  xor     r14d, r14d
0x18000734b  cmp     r14d, eax
0x18000734e  jge     loc_1800073E1
0x180007354  mov     rax, cs:qword_1800701D0
0x18000735b  mov     rdi, [r15+28h]
0x18000735f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007363  jnz     short loc_18000737D
0x180007365  mov     edx, 14Ch
0x18000736a  lea     rcx, qword_1800701D0
0x180007371  call    _GetProcFromComCtl32
0x180007376  mov     rax, cs:qword_1800701D0
0x18000737d  test    rax, rax
0x180007380  jz      short loc_180007392
0x180007382  movsxd  rdx, r14d
0x180007385  mov     rcx, rdi
0x180007388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000738d  mov     rdi, rax
0x180007390  jmp     short loc_180007394
0x180007392  xor     edi, edi
0x180007394  mov     r8, [rsp+68h+arg_8]
0x180007399  lea     rax, [rdi+74h]
0x18000739d  or      r9d, 0FFFFFFFFh; cchCount1
0x1800073a1  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800073a9  add     r8, 10h; lpString1
0x1800073ad  mov     [rsp+68h+lpString2], rax; lpString2
0x1800073b2  lea     edx, [r9+2]; dwCmpFlags
0x1800073b6  lea     ecx, [rdx+7Eh]; Locale
0x1800073b9  call    cs:__imp_CompareStringW
0x1800073bf  sub     eax, 1
0x1800073c2  jz      short loc_1800073C9
0x1800073c4  cmp     eax, 1
0x1800073c7  jz      short loc_1800073D5
0x1800073c9  mov     eax, [rsp+68h+dwindex]
0x1800073cd  inc     r14d
0x1800073d0  jmp     loc_18000734B
0x1800073d5  xor     ebx, ebx
0x1800073d7  mov     rbp, rdi
0x1800073da  lock inc dword ptr [rdi+81Ch]
0x1800073e1  mov     rcx, [r15+30h]; lpCriticalSection
0x1800073e5  call    cs:__imp_LeaveCriticalSection
0x1800073eb  test    ebx, ebx
0x1800073ed  jns     short loc_1800073FB
0x1800073ef  inc     r12d
0x1800073f2  cmp     r12d, r13d
0x1800073f5  jl      loc_1800072E7
0x1800073fb  mov     edi, [rsp+68h+arg_10]
0x180007402  lea     r14, [rsi+1A0h]
0x180007409  mov     rcx, rsi; lpCriticalSection
0x18000740c  call    cs:__imp_LeaveCriticalSection
0x180007412  cmp     ebx, 80070002h
0x180007418  jnz     short loc_18000744F
0x18000741a  cmp     edi, 102h
0x180007420  jnz     short loc_18000747C
0x180007422  xor     ecx, ecx; dwFlags
0x180007424  mov     [rsp+68h+dwindex], 0
0x18000742c  lea     rax, [rsp+68h+dwindex]
0x180007431  mov     r9, r14; pHandles
0x180007434  mov     edx, 1F4h; dwTimeout
0x180007439  mov     [rsp+68h+lpString2], rax; lpdwindex
0x18000743e  lea     r8d, [rcx+1]; cHandles
0x180007442  call    cs:__imp_CoWaitForMultipleHandles
0x180007448  cmp     eax, 80070057h
0x18000744d  jz      short loc_180007461
0x18000744f  test    ebx, ebx
0x180007451  jns     short loc_180007468
0x180007453  cmp     edi, 102h
0x180007459  jz      loc_1800072AC
0x18000745f  jmp     short loc_18000747C
0x180007461  mov     ebx, 80070057h
0x180007466  jmp     short loc_18000747C
0x180007468  xor     edx, edx; struct ISyncMgrHandlerCollection *
0x18000746a  mov     rcx, rbp; this
0x18000746d  call    ?Init@CHandlerInfo@@QEAAJPEAUISyncMgrHandlerCollection@@@Z; CHandlerInfo::Init(ISyncMgrHandlerCollection *)
0x180007472  mov     rcx, rbp; this
0x180007475  mov     ebx, eax
0x180007477  call    ?Release@CHandlerInfo@@QEAAKXZ; CHandlerInfo::Release(void)
0x18000747c  mov     rcx, rsi; this
0x18000747f  call    ?_UpdateAggregateStatus@CHandlerCache@@AEAAXXZ; CHandlerCache::_UpdateAggregateStatus(void)
0x180007484  mov     eax, ebx
0x180007486  mov     rbx, [rsp+68h+arg_18]
0x18000748e  add     rsp, 30h
0x180007492  pop     r15
0x180007494  pop     r14
0x180007496  pop     r13
0x180007498  pop     r12
0x18000749a  pop     rdi
0x18000749b  pop     rsi
0x18000749c  pop     rbp
0x18000749d  retn
```
