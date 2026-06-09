# CViperActivity::PostAsyncRequest(CHitObj *)

- ea: `0x180062868`
- end: `0x1800629a8`
- name: `?PostAsyncRequest@CViperActivity@@QEAAJPEAVCHitObj@@@Z`
- size: `320`
- prototype: `int(CViperActivity *__hidden this, struct CHitObj *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18000a160`
- `0x18000ca50`
- `0x1800629b0`

## callees

- `0x18006251c`
- `0x1800626e8`
- `0x180062868`
- `0x180062b00`
- `0x180064010`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x18006290d`
- `ADVAPI32!RevertToSelf` at `0x180062990`
- `ADVAPI32!RevertToSelf` at `0x18006290d`
- `ADVAPI32!RevertToSelf` at `0x180062990`
- `KERNEL32!LeaveCriticalSection` at `0x180062964`
- `KERNEL32!LeaveCriticalSection` at `0x180062964`
- `KERNEL32!EnterCriticalSection` at `0x18006292f`
- `KERNEL32!EnterCriticalSection` at `0x18006292f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18006288f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18006288f`

## pseudocode

```c
__int64 __fastcall CViperActivity::PostAsyncRequest(struct IServiceActivity **this, struct CHitObj *a2)
{
  char *v4; // rax
  char *v5; // rbx
  _QWORD *v6; // rax
  int v7; // edi
  CViperReqManager *v8; // rcx

  ((void (__fastcall *)(struct IServiceActivity **))(*this)->lpVtbl)(this);
  v4 = (char *)ALLOC_CACHE_HANDLER::Alloc(CViperAsyncRequest::sm_pach);
  v5 = v4;
  if ( !v4 )
  {
    v7 = -2147024882;
    RevertToSelf();
    return (unsigned int)v7;
  }
  v6 = v4 + 16;
  v5[70] = 0;
  *((_DWORD *)v5 + 17) &= 0xF9FFFFFF;
  *(_QWORD *)v5 = &CViperAsyncRequest::`vftable'{for `IServiceCall'};
  *((_QWORD *)v5 + 1) = &CViperAsyncRequest::`vftable'{for `IAsyncErrorNotify'};
  *v6 = &CViperAsyncRequest::`vftable'{for `CDblLink'};
  v6[2] = v6;
  v6[1] = v6;
  *((_DWORD *)v5 + 10) = 1;
  *((_QWORD *)v5 + 6) = 0;
  *((_QWORD *)v5 + 7) = 0;
  *((_DWORD *)v5 + 16) = 0;
  _InterlockedIncrement(&g_nViperRequests);
  v7 = CViperAsyncRequest::Init((CViperAsyncRequest *)v5, a2, this[1]);
  RevertToSelf();
  if ( v7 < 0 )
    goto LABEL_3;
  EnterCriticalSection(&stru_18007D2E8);
  v7 = CViperReqManager::AddReqObj(v8, (struct CViperAsyncRequest *)v5);
  if ( v7 >= 0 )
  {
    *((_DWORD *)v5 + 17) |= 0x4000000u;
    v7 = ((__int64 (__fastcall *)(struct IServiceActivity *, char *))this[1]->lpVtbl->AsynchronousCall)(this[1], v5);
  }
  LeaveCriticalSection(&stru_18007D2E8);
  if ( v7 < 0
    && (unsigned int)CViperReqManager::RemoveReqObj(
                       (CViperReqManager *)&g_ViperReqMgr,
                       (struct CViperAsyncRequest *)v5,
                       0) )
  {
    *((_DWORD *)v5 + 17) &= ~0x4000000u;
LABEL_3:
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180062868  mov     [rsp+arg_0], rbx
0x18006286d  mov     [rsp+arg_8], rsi
0x180062872  push    rdi
0x180062873  sub     rsp, 20h
0x180062877  mov     rax, [rcx]
0x18006287a  mov     rdi, rdx
0x18006287d  mov     rsi, rcx
0x180062880  mov     rax, [rax]
0x180062883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062888  mov     rcx, cs:?sm_pach@CViperAsyncRequest@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CViperAsyncRequest::sm_pach
0x18006288f  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180062895  mov     rbx, rax
0x180062898  test    rax, rax
0x18006289b  jz      loc_18006298B
0x1800628a1  add     rax, 10h
0x1800628a5  mov     byte ptr [rbx+46h], 0
0x1800628a9  and     dword ptr [rbx+44h], 0F9FFFFFFh
0x1800628b0  lea     rcx, ??_7CViperAsyncRequest@@6BIServiceCall@@@; const CViperAsyncRequest::`vftable'{for `IServiceCall'}
0x1800628b7  mov     [rbx], rcx
0x1800628ba  lea     rcx, ??_7CViperAsyncRequest@@6BIAsyncErrorNotify@@@; const CViperAsyncRequest::`vftable'{for `IAsyncErrorNotify'}
0x1800628c1  mov     [rbx+8], rcx
0x1800628c5  lea     rcx, ??_7CViperAsyncRequest@@6BCDblLink@@@; const CViperAsyncRequest::`vftable'{for `CDblLink'}
0x1800628cc  mov     [rax], rcx
0x1800628cf  mov     [rax+10h], rax
0x1800628d3  mov     [rax+8], rax
0x1800628d7  mov     dword ptr [rbx+28h], 1
0x1800628de  mov     qword ptr [rbx+30h], 0
0x1800628e6  mov     qword ptr [rbx+38h], 0
0x1800628ee  mov     dword ptr [rbx+40h], 0
0x1800628f5  lock inc cs:?g_nViperRequests@@3JC; long volatile g_nViperRequests
0x1800628fc  mov     r8, [rsi+8]; struct IServiceActivity *
0x180062900  mov     rdx, rdi; struct CHitObj *
0x180062903  mov     rcx, rbx; this
0x180062906  call    ?Init@CViperAsyncRequest@@AEAAJPEAVCHitObj@@PEAUIServiceActivity@@@Z; CViperAsyncRequest::Init(CHitObj *,IServiceActivity *)
0x18006290b  mov     edi, eax
0x18006290d  call    cs:__imp_RevertToSelf
0x180062913  test    edi, edi
0x180062915  jns     short loc_180062928
0x180062917  mov     rax, [rbx]
0x18006291a  mov     rcx, rbx
0x18006291d  mov     rax, [rax+10h]
0x180062921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062926  jmp     short loc_180062996
0x180062928  lea     rcx, stru_18007D2E8; lpCriticalSection
0x18006292f  call    cs:__imp_EnterCriticalSection
0x180062935  mov     rdx, rbx; struct CViperAsyncRequest *
0x180062938  call    ?AddReqObj@CViperReqManager@@QEAAJPEAVCViperAsyncRequest@@@Z; CViperReqManager::AddReqObj(CViperAsyncRequest *)
0x18006293d  mov     edi, eax
0x18006293f  test    eax, eax
0x180062941  js      short loc_18006295D
0x180062943  bts     dword ptr [rbx+44h], 1Ah
0x180062948  mov     rdx, rbx
0x18006294b  mov     rcx, [rsi+8]
0x18006294f  mov     rax, [rcx]
0x180062952  mov     rax, [rax+20h]
0x180062956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006295b  mov     edi, eax
0x18006295d  lea     rcx, stru_18007D2E8; lpCriticalSection
0x180062964  call    cs:__imp_LeaveCriticalSection
0x18006296a  test    edi, edi
0x18006296c  jns     short loc_180062996
0x18006296e  xor     r8d, r8d; int
0x180062971  lea     rcx, ?g_ViperReqMgr@@3VCViperReqManager@@A; this
0x180062978  mov     rdx, rbx; struct CViperAsyncRequest *
0x18006297b  call    ?RemoveReqObj@CViperReqManager@@QEAAHPEAVCViperAsyncRequest@@H@Z; CViperReqManager::RemoveReqObj(CViperAsyncRequest *,int)
0x180062980  test    eax, eax
0x180062982  jz      short loc_180062996
0x180062984  btr     dword ptr [rbx+44h], 1Ah
0x180062989  jmp     short loc_180062917
0x18006298b  mov     edi, 8007000Eh
0x180062990  call    cs:__imp_RevertToSelf
0x180062996  mov     rbx, [rsp+28h+arg_0]
0x18006299b  mov     eax, edi
0x18006299d  mov     rsi, [rsp+28h+arg_8]
0x1800629a2  add     rsp, 20h
0x1800629a6  pop     rdi
0x1800629a7  retn
```
