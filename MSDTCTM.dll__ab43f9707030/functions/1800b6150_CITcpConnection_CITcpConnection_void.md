# CITcpConnection::~CITcpConnection(void)

- ea: `0x1800b6150`
- end: `0x1800b62cf`
- name: `??1CITcpConnection@@QEAA@XZ`
- size: `383`
- prototype: `void __fastcall(CITcpConnection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b65c0`

## callees

- `0x1800240f0`
- `0x1800b6150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b62ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b62bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b62ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b62bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b620f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b620f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b618f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b618f`
- `WS2_32!__imp_closesocket` at `0x1800b623e`
- `WS2_32!__imp_closesocket` at `0x1800b623e`

## pseudocode

```c
void __fastcall CITcpConnection::~CITcpConnection(CITcpConnection *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  char *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  void *v7; // rcx
  SOCKET v8; // rcx

  *(_QWORD *)this = &CITcpConnection::`vftable'{for `ITcpConnection'};
  *((_QWORD *)this + 1) = &CITcpConnection::`vftable'{for `ICompletion'};
  *((_QWORD *)this + 2) = &CITcpConnection::`vftable'{for `ITimerNotify'};
  *((_QWORD *)this + 3) = &CITcpConnection::`vftable'{for `IMutex'};
  EnterCriticalSection(&stru_180153C20);
  v2 = (_QWORD *)((char *)this + 1040);
  v3 = *((_QWORD *)this + 132);
  v4 = (char *)this + 1064;
  if ( *(CITcpConnection **)(v3 + 16) == (CITcpConnection *)((char *)this + 1040) )
    *(_QWORD *)(v3 + 16) = *(_QWORD *)v4;
  v5 = *((_QWORD *)this + 132);
  if ( *(_QWORD **)(v5 + 24) == v2 )
    *(_QWORD *)(v5 + 24) = *((_QWORD *)this + 134);
  v6 = *((_QWORD *)this + 134);
  if ( v6 )
    *(_QWORD *)(v6 + 24) = *(_QWORD *)v4;
  if ( *(_QWORD *)v4 )
    *(_QWORD *)(*(_QWORD *)v4 + 32LL) = *((_QWORD *)this + 134);
  --*(_DWORD *)(*((_QWORD *)this + 132) + 8LL);
  *((_QWORD *)this + 132) = 0;
  *(_QWORD *)v4 = 0;
  *((_QWORD *)this + 134) = 0;
  *((_DWORD *)this + 270) = 0;
  LeaveCriticalSection(&stru_180153C20);
  v7 = (void *)*((_QWORD *)this + 128);
  if ( v7 )
  {
    operator delete(v7);
    *((_QWORD *)this + 128) = 0;
  }
  v8 = *((_QWORD *)this + 21);
  if ( v8 != -1 )
  {
    closesocket(v8);
    *((_QWORD *)this + 21) = -1;
  }
  *v2 = &UTStaticLink2<CTxPhaseZero *>::`vftable';
  *((_QWORD *)this + 115) = &UTStaticList<CImpITransactionTracker *>::`vftable';
  *((_QWORD *)this + 108) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 95) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 82) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 69) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 56) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 43) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 30) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)this + 14) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  *((_QWORD *)this + 7) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x1800b6150  mov     [rsp+arg_0], rbx
0x1800b6155  push    rdi
0x1800b6156  sub     rsp, 20h
0x1800b615a  mov     rbx, rcx
0x1800b615d  lea     rax, ??_7CITcpConnection@@6BITcpConnection@@@; const CITcpConnection::`vftable'{for `ITcpConnection'}
0x1800b6164  mov     [rcx], rax
0x1800b6167  lea     rax, ??_7CITcpConnection@@6BICompletion@@@; const CITcpConnection::`vftable'{for `ICompletion'}
0x1800b616e  mov     [rcx+8], rax
0x1800b6172  lea     rax, ??_7CITcpConnection@@6BITimerNotify@@@; const CITcpConnection::`vftable'{for `ITimerNotify'}
0x1800b6179  mov     [rcx+10h], rax
0x1800b617d  lea     rax, ??_7CITcpConnection@@6BIMutex@@@; const CITcpConnection::`vftable'{for `IMutex'}
0x1800b6184  mov     [rcx+18h], rax
0x1800b6188  lea     rcx, stru_180153C20; lpCriticalSection
0x1800b618f  call    cs:__imp_EnterCriticalSection
0x1800b6195  lea     rdi, [rbx+410h]
0x1800b619c  mov     rdx, [rdi+10h]
0x1800b61a0  lea     rcx, [rdi+18h]
0x1800b61a4  cmp     [rdx+10h], rdi
0x1800b61a8  jnz     short loc_1800B61B1
0x1800b61aa  mov     rax, [rcx]
0x1800b61ad  mov     [rdx+10h], rax
0x1800b61b1  mov     rdx, [rdi+10h]
0x1800b61b5  cmp     [rdx+18h], rdi
0x1800b61b9  jnz     short loc_1800B61C3
0x1800b61bb  mov     rax, [rdi+20h]
0x1800b61bf  mov     [rdx+18h], rax
0x1800b61c3  mov     rdx, [rdi+20h]
0x1800b61c7  test    rdx, rdx
0x1800b61ca  jz      short loc_1800B61D3
0x1800b61cc  mov     rax, [rcx]
0x1800b61cf  mov     [rdx+18h], rax
0x1800b61d3  mov     rdx, [rcx]
0x1800b61d6  test    rdx, rdx
0x1800b61d9  jz      short loc_1800B61E3
0x1800b61db  mov     rax, [rdi+20h]
0x1800b61df  mov     [rdx+20h], rax
0x1800b61e3  mov     rax, [rdi+10h]
0x1800b61e7  dec     dword ptr [rax+8]
0x1800b61ea  mov     qword ptr [rdi+10h], 0
0x1800b61f2  mov     qword ptr [rcx], 0
0x1800b61f9  mov     qword ptr [rdi+20h], 0
0x1800b6201  mov     dword ptr [rdi+28h], 0
0x1800b6208  lea     rcx, stru_180153C20; lpCriticalSection
0x1800b620f  call    cs:__imp_LeaveCriticalSection
0x1800b6215  mov     rcx, [rbx+400h]; Block
0x1800b621c  test    rcx, rcx
0x1800b621f  jz      short loc_1800B6231
0x1800b6221  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b6226  mov     qword ptr [rbx+400h], 0
0x1800b6231  mov     rcx, [rbx+0A8h]; s
0x1800b6238  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b623c  jz      short loc_1800B624F
0x1800b623e  call    cs:__imp_closesocket
0x1800b6244  mov     qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFFFh
0x1800b624f  lea     rax, ??_7?$UTStaticLink2@PEAVCTxPhaseZero@@@@6B@; const UTStaticLink2<CTxPhaseZero *>::`vftable'
0x1800b6256  mov     [rdi], rax
0x1800b6259  lea     rax, ??_7?$UTStaticList@PEAVCImpITransactionTracker@@@@6B@; const UTStaticList<CImpITransactionTracker *>::`vftable'
0x1800b6260  mov     [rbx+398h], rax
0x1800b6267  lea     rax, ??_7?$UTLink@PEAU_IOMGROVERLAP@@@@6B@; const UTLink<_IOMGROVERLAP *>::`vftable'
0x1800b626e  mov     [rbx+360h], rax
0x1800b6275  mov     [rbx+2F8h], rax
0x1800b627c  mov     [rbx+290h], rax
0x1800b6283  mov     [rbx+228h], rax
0x1800b628a  mov     [rbx+1C0h], rax
0x1800b6291  mov     [rbx+158h], rax
0x1800b6298  mov     [rbx+0F0h], rax
0x1800b629f  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800b62a6  mov     [rbx+70h], rdi
0x1800b62aa  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800b62ae  call    cs:__imp_DeleteCriticalSection
0x1800b62b4  nop
0x1800b62b5  mov     [rbx+38h], rdi
0x1800b62b9  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800b62bd  call    cs:__imp_DeleteCriticalSection
0x1800b62c3  nop
0x1800b62c4  mov     rbx, [rsp+28h+arg_0]
0x1800b62c9  add     rsp, 20h
0x1800b62cd  pop     rdi
0x1800b62ce  retn
```
