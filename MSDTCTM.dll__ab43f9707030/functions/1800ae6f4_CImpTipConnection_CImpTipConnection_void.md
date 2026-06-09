# CImpTipConnection::~CImpTipConnection(void)

- ea: `0x1800ae6f4`
- end: `0x1800ae85e`
- name: `??1CImpTipConnection@@QEAA@XZ`
- size: `362`
- prototype: `void __fastcall(CImpTipConnection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ad9c0`

## callees

- `0x1800ae6f4`
- `0x1800aeae0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ae842`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ae842`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae80e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae80e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae791`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae791`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae73f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae75c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae73f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae75c`
- `msvcrt!free` at `0x1800ae779`
- `msvcrt!free` at `0x1800ae779`

## pseudocode

```c
void __fastcall CImpTipConnection::~CImpTipConnection(CImpTipConnection *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  char *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx

  *(_QWORD *)this = &CImpTipConnection::`vftable'{for `ITipConnection'};
  *((_QWORD *)this + 1) = &CImpTipConnection::`vftable'{for `ITcpConnectionSink'};
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 12) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 17) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 21);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 21) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 33);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 33) = 0;
  }
  EnterCriticalSection(&stru_180153B68);
  v6 = (_QWORD *)((char *)this + 16);
  v7 = *((_QWORD *)this + 4);
  v8 = (char *)this + 40;
  if ( *(CImpTipConnection **)(v7 + 16) == (CImpTipConnection *)((char *)this + 16) )
    *(_QWORD *)(v7 + 16) = *(_QWORD *)v8;
  v9 = *((_QWORD *)this + 4);
  if ( *(_QWORD **)(v9 + 24) == v6 )
    *(_QWORD *)(v9 + 24) = *((_QWORD *)this + 6);
  v10 = *((_QWORD *)this + 6);
  if ( v10 )
    *(_QWORD *)(v10 + 24) = *(_QWORD *)v8;
  if ( *(_QWORD *)v8 )
    *(_QWORD *)(*(_QWORD *)v8 + 32LL) = *((_QWORD *)this + 6);
  --*(_DWORD *)(*((_QWORD *)this + 4) + 8LL);
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)v8 = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  LeaveCriticalSection(&stru_180153B68);
  CTmIDString::Clear((CImpTipConnection *)((char *)this + 296));
  CTmIDString::Clear((CImpTipConnection *)((char *)this + 288));
  *((_QWORD *)this + 26) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  *v6 = &UTStaticLink2<CTxPhaseZero *>::`vftable';
}

```

## disassembly

```asm
0x1800ae6f4  mov     [rsp+arg_0], rbx
0x1800ae6f9  push    rdi
0x1800ae6fa  sub     rsp, 20h
0x1800ae6fe  mov     rbx, rcx
0x1800ae701  lea     rax, ??_7CImpTipConnection@@6BITipConnection@@@; const CImpTipConnection::`vftable'{for `ITipConnection'}
0x1800ae708  mov     [rcx], rax
0x1800ae70b  lea     rax, ??_7CImpTipConnection@@6BITcpConnectionSink@@@; const CImpTipConnection::`vftable'{for `ITcpConnectionSink'}
0x1800ae712  mov     [rcx+8], rax
0x1800ae716  mov     rcx, [rcx+60h]
0x1800ae71a  test    rcx, rcx
0x1800ae71d  jz      short loc_1800AE733
0x1800ae71f  mov     rax, [rcx]
0x1800ae722  mov     rax, [rax+10h]
0x1800ae726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae72b  mov     qword ptr [rbx+60h], 0
0x1800ae733  mov     rcx, [rbx+88h]; pv
0x1800ae73a  test    rcx, rcx
0x1800ae73d  jz      short loc_1800AE750
0x1800ae73f  call    cs:__imp_CoTaskMemFree
0x1800ae745  mov     qword ptr [rbx+88h], 0
0x1800ae750  mov     rcx, [rbx+0A8h]; pv
0x1800ae757  test    rcx, rcx
0x1800ae75a  jz      short loc_1800AE76D
0x1800ae75c  call    cs:__imp_CoTaskMemFree
0x1800ae762  mov     qword ptr [rbx+0A8h], 0
0x1800ae76d  mov     rcx, [rbx+108h]; Block
0x1800ae774  test    rcx, rcx
0x1800ae777  jz      short loc_1800AE78A
0x1800ae779  call    cs:__imp_free
0x1800ae77f  mov     qword ptr [rbx+108h], 0
0x1800ae78a  lea     rcx, stru_180153B68; lpCriticalSection
0x1800ae791  call    cs:__imp_EnterCriticalSection
0x1800ae797  lea     rdi, [rbx+10h]
0x1800ae79b  mov     rdx, [rdi+10h]
0x1800ae79f  lea     rcx, [rdi+18h]
0x1800ae7a3  cmp     [rdx+10h], rdi
0x1800ae7a7  jnz     short loc_1800AE7B0
0x1800ae7a9  mov     rax, [rcx]
0x1800ae7ac  mov     [rdx+10h], rax
0x1800ae7b0  mov     rdx, [rdi+10h]
0x1800ae7b4  cmp     [rdx+18h], rdi
0x1800ae7b8  jnz     short loc_1800AE7C2
0x1800ae7ba  mov     rax, [rdi+20h]
0x1800ae7be  mov     [rdx+18h], rax
0x1800ae7c2  mov     rdx, [rdi+20h]
0x1800ae7c6  test    rdx, rdx
0x1800ae7c9  jz      short loc_1800AE7D2
0x1800ae7cb  mov     rax, [rcx]
0x1800ae7ce  mov     [rdx+18h], rax
0x1800ae7d2  mov     rdx, [rcx]
0x1800ae7d5  test    rdx, rdx
0x1800ae7d8  jz      short loc_1800AE7E2
0x1800ae7da  mov     rax, [rdi+20h]
0x1800ae7de  mov     [rdx+20h], rax
0x1800ae7e2  mov     rax, [rdi+10h]
0x1800ae7e6  dec     dword ptr [rax+8]
0x1800ae7e9  mov     qword ptr [rdi+10h], 0
0x1800ae7f1  mov     qword ptr [rcx], 0
0x1800ae7f8  mov     qword ptr [rdi+20h], 0
0x1800ae800  mov     dword ptr [rdi+28h], 0
0x1800ae807  lea     rcx, stru_180153B68; lpCriticalSection
0x1800ae80e  call    cs:__imp_LeaveCriticalSection
0x1800ae814  lea     rcx, [rbx+128h]; this
0x1800ae81b  call    ?Clear@CTmIDString@@QEAAHXZ; CTmIDString::Clear(void)
0x1800ae820  lea     rcx, [rbx+120h]; this
0x1800ae827  call    ?Clear@CTmIDString@@QEAAHXZ; CTmIDString::Clear(void)
0x1800ae82c  nop
0x1800ae82d  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800ae834  mov     [rbx+0D0h], rax
0x1800ae83b  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x1800ae842  call    cs:__imp_DeleteCriticalSection
0x1800ae848  nop
0x1800ae849  lea     rax, ??_7?$UTStaticLink2@PEAVCTxPhaseZero@@@@6B@; const UTStaticLink2<CTxPhaseZero *>::`vftable'
0x1800ae850  mov     [rdi], rax
0x1800ae853  mov     rbx, [rsp+28h+arg_0]
0x1800ae858  add     rsp, 20h
0x1800ae85c  pop     rdi
0x1800ae85d  retn
```
