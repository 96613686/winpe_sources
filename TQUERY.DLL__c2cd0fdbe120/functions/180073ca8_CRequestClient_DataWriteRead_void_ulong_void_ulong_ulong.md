# CRequestClient::DataWriteRead(void *,ulong,void *,ulong,ulong &)

- ea: `0x180073ca8`
- end: `0x180073dd5`
- name: `?DataWriteRead@CRequestClient@@QEAAXPEAXK0KAEAK@Z`
- size: `301`
- prototype: `void(CRequestClient *__hidden this, void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `34`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800697d0`
- `0x180071680`
- `0x180072edc`
- `0x1800fe410`
- `0x1800ff540`
- `0x180105f70`
- `0x180118750`
- `0x18012f670`
- `0x18012fbd0`
- `0x1801af1a0`
- `0x1801af200`
- `0x1801af2d0`
- `0x1801af430`
- `0x1801af5a0`
- `0x1801b01a0`
- `0x1801b0b20`
- `0x1801c2140`
- `0x1801c21f0`
- `0x1801c2450`
- `0x1801c27e0`
- `0x1801c29a0`
- `0x1801c2a80`
- `0x1801c2da0`
- `0x1801c2e58`
- `0x1801c30c0`
- `0x1801c31d0`
- `0x1801c3270`
- `0x1801c3330`
- `0x1801c3520`
- `0x1801c3620`
- `0x1801c36d0`
- `0x1801c3830`
- `0x1801c3d60`
- `0x1801c3de0`

## callees

- `0x1800699a0`
- `0x180072768`
- `0x180073ca8`
- `0x180073ea0`
- `0x180073f94`
- `0x180076b30`
- `0x1800950b8`
- `0x1800eb364`
- `0x1800f66c0`
- `0x180176848`
- `0x18018e8cb`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073cfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073d13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073cfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073d7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802ba48b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073d7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073da3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802ba48b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073d24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073d24`

## string_xrefs

- `0x180073cd3`: `[Proxy] DataWriteRead msg %d, cb %d\n`
- `0x180073cdf`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1802ba4bc`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1802ba4b0`: `[Proxy] dwr eventdata triggered, _pvDataTemp: %p\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CRequestClient::DataWriteRead(
        CRequestClient *this,
        int *a2,
        DWORD a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  int v10; // r15d
  struct _RTL_CRITICAL_SECTION *v11; // rbp
  int v12; // r14d
  unsigned int *v13; // rdi
  const void *v14; // rdx
  unsigned int v15; // eax
  const wchar_t *v16; // r9
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h]

  v10 = *a2;
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
    (const wchar_t *)0x433,
    (unsigned int)L"[Proxy] DataWriteRead msg %d, cb %d\n",
    (const wchar_t *)(unsigned int)*a2,
    a3);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  v18 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v12 = 1;
  LODWORD(v19) = 1;
  HIDWORD(v19) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 30) )
  {
    CPipeClient::WriteSync(this, a2, a3);
    *((_DWORD *)this + 32) = 1;
    v12 = 0;
    v19 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
    CEventSem::Wait((CRequestClient *)((char *)this + 168), 0xFFFFFFFF, 0);
    *((_DWORD *)this + 32) = 0;
    SearchIndexerDebug::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const wchar_t *)0x441,
      (unsigned int)L"[Proxy] dwr eventdata triggered, _pvDataTemp: %p\n",
      *((const wchar_t **)this + 17));
    v14 = (const void *)*((_QWORD *)this + 17);
    if ( v14 )
    {
      v15 = *((_DWORD *)this + 36);
      if ( v15 > a5 )
        ServerResponseError();
      memcpy_0(a4, v14, v15);
      v16 = (const wchar_t *)*((unsigned int *)this + 36);
      v13 = a6;
      *a6 = (unsigned int)v16;
      SearchIndexerDebug::Verbose(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const wchar_t *)0x45E,
        (unsigned int)L"[Proxy] dwr done, other, cb: %d\n",
        v16);
    }
    else
    {
      CReleasableLock::Request((CReleasableLock *)&v18);
      v13 = a6;
      CRequestClient::ReadDirtyResponse(this, v10, a4, a5, a6);
      SearchIndexerDebug::Verbose(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const wchar_t *)0x455,
        (unsigned int)L"[Proxy] dwr done, this, cb: %d\n",
        (const wchar_t *)*a6);
      v12 = v19;
      v11 = v18;
    }
    CEventSem::Set((CRequestClient *)((char *)this + 176));
  }
  else if ( *((_DWORD *)this + 31) )
  {
    CPipeClient::WriteSync(this, a2, a3);
    v13 = a6;
    CRequestClient::ReadDirtyResponse(this, v10, a4, a5, a6);
  }
  else
  {
    v13 = a6;
    CPipeClient::TransactSync(this, a2, a3, a4, a5, a6);
  }
  CProxyMessage::ValidateOutputHeader((CProxyMessage *)a4, *v13, v10);
  if ( v12 )
    LeaveCriticalSection(v11);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
}

```

## disassembly

```asm
0x180073ca8  mov     [rsp+arg_10], rbx
0x180073cad  push    rbp
0x180073cae  push    rsi
0x180073caf  push    rdi
0x180073cb0  push    r12
0x180073cb2  push    r13
0x180073cb4  push    r14
0x180073cb6  push    r15
0x180073cb8  sub     rsp, 40h
0x180073cbc  mov     rsi, r9
0x180073cbf  mov     r12d, r8d
0x180073cc2  mov     r13, rdx
0x180073cc5  mov     rbx, rcx
0x180073cc8  mov     r15d, [rdx]
0x180073ccb  mov     dword ptr [rsp+78h+var_58], r8d
0x180073cd0  mov     r9d, r15d; wchar_t *
0x180073cd3  lea     r8, aProxyDatawrite; "[Proxy] DataWriteRead msg %d, cb %d\n"
0x180073cda  mov     edx, 433h; wchar_t *
0x180073cdf  lea     rcx, aOnecoreuapBase_173; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073ce6  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180073ceb  lea     rax, [rbx+0E8h]
0x180073cf2  mov     [rsp+78h+arg_0], rax
0x180073cfa  mov     rcx, rax; lpCriticalSection
0x180073cfd  call    cs:__imp_EnterCriticalSection
0x180073d03  nop
0x180073d04  lea     rbp, [rbx+0B8h]
0x180073d0b  mov     [rsp+78h+var_48], rbp
0x180073d10  mov     rcx, rbp; lpCriticalSection
0x180073d13  call    cs:__imp_EnterCriticalSection
0x180073d19  mov     r14d, 1
0x180073d1f  mov     dword ptr [rsp+78h+var_40], r14d
0x180073d24  call    cs:__imp_GetCurrentThreadId
0x180073d2a  mov     dword ptr [rsp+78h+var_40+4], eax
0x180073d2e  xor     edi, edi
0x180073d30  mov     r8d, r12d; nNumberOfBytesToWrite
0x180073d33  mov     rdx, r13; lpBuffer
0x180073d36  mov     rcx, rbx; this
0x180073d39  cmp     [rbx+78h], edi
0x180073d3c  jnz     loc_1802BA474
0x180073d42  cmp     [rbx+7Ch], edi
0x180073d45  jnz     short loc_180073DAA
0x180073d47  mov     rdi, [rsp+78h+arg_28]
0x180073d4f  mov     [rsp+78h+var_50], rdi; unsigned int *
0x180073d54  mov     eax, [rsp+78h+arg_20]
0x180073d5b  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180073d5f  mov     r9, rsi; void *
0x180073d62  call    ?TransactSync@CPipeClient@@IEAAXPEAXK0KAEAK@Z; CPipeClient::TransactSync(void *,ulong,void *,ulong,ulong &)
0x180073d67  mov     r8d, r15d; int
0x180073d6a  mov     edx, [rdi]; unsigned int
0x180073d6c  mov     rcx, rsi; this
0x180073d6f  call    ?ValidateOutputHeader@CProxyMessage@@QEAAXKH@Z; CProxyMessage::ValidateOutputHeader(ulong,int)
0x180073d74  nop
0x180073d75  test    r14d, r14d
0x180073d78  jz      short loc_180073D84
0x180073d7a  mov     rcx, rbp; lpCriticalSection
0x180073d7d  call    cs:__imp_LeaveCriticalSection
0x180073d83  nop
0x180073d84  mov     rcx, [rsp+78h+arg_0]
0x180073d8c  mov     rbx, [rsp+78h+arg_10]
0x180073d94  add     rsp, 40h
0x180073d98  pop     r15
0x180073d9a  pop     r14
0x180073d9c  pop     r13
0x180073d9e  pop     r12
0x180073da0  pop     rdi
0x180073da1  pop     rsi
0x180073da2  pop     rbp
0x180073da3  jmp     cs:__imp_LeaveCriticalSection
0x180073daa  call    ?WriteSync@CPipeClient@@IEAAXPEAXK@Z; CPipeClient::WriteSync(void *,ulong)
0x180073daf  nop
0x180073db0  mov     rdi, [rsp+78h+arg_28]
0x180073db8  mov     [rsp+78h+var_58], rdi; unsigned int *
0x180073dbd  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x180073dc5  mov     r8, rsi; void *
0x180073dc8  mov     edx, r15d; int
0x180073dcb  mov     rcx, rbx; this
0x180073dce  call    ?ReadDirtyResponse@CRequestClient@@AEAAXHPEAXKAEAK@Z; CRequestClient::ReadDirtyResponse(int,void *,ulong,ulong &)
0x180073dd3  jmp     short loc_180073D67
0x1802ba474  call    ?WriteSync@CPipeClient@@IEAAXPEAXK@Z; CPipeClient::WriteSync(void *,ulong)
0x1802ba479  mov     [rbx+80h], r14d
0x1802ba480  mov     r14d, edi
0x1802ba483  mov     [rsp+78h+var_40], rdi
0x1802ba488  mov     rcx, rbp; lpCriticalSection
0x1802ba48b  call    cs:__imp_LeaveCriticalSection
0x1802ba491  lea     rcx, [rbx+0A8h]; this
0x1802ba498  xor     r8d, r8d; int
0x1802ba49b  or      edx, 0FFFFFFFFh; unsigned int
0x1802ba49e  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x1802ba4a3  mov     [rbx+80h], edi
0x1802ba4a9  mov     r9, [rbx+88h]; wchar_t *
0x1802ba4b0  lea     r8, aProxyDwrEventd; "[Proxy] dwr eventdata triggered, _pvDat"...
0x1802ba4b7  mov     edx, 441h; wchar_t *
0x1802ba4bc  lea     r13, aOnecoreuapBase_173; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802ba4c3  mov     rcx, r13; this
0x1802ba4c6  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802ba4cb  lea     r12, [rbx+0B0h]
0x1802ba4d2  mov     [rsp+78h+arg_8], r12
0x1802ba4da  mov     rdx, [rbx+88h]; Src
0x1802ba4e1  test    rdx, rdx
0x1802ba4e4  jnz     short loc_1802BA536
0x1802ba4e6  lea     rcx, [rsp+78h+var_48]; this
0x1802ba4eb  call    ?Request@CReleasableLock@@QEAAXXZ; CReleasableLock::Request(void)
0x1802ba4f0  mov     rdi, [rsp+78h+arg_28]
0x1802ba4f8  mov     [rsp+78h+var_58], rdi; unsigned int *
0x1802ba4fd  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x1802ba505  mov     r8, rsi; void *
0x1802ba508  mov     edx, r15d; int
0x1802ba50b  mov     rcx, rbx; this
0x1802ba50e  call    ?ReadDirtyResponse@CRequestClient@@AEAAXHPEAXKAEAK@Z; CRequestClient::ReadDirtyResponse(int,void *,ulong,ulong &)
0x1802ba513  mov     r9d, [rdi]; wchar_t *
0x1802ba516  lea     r8, aProxyDwrDoneTh; "[Proxy] dwr done, this, cb: %d\n"
0x1802ba51d  mov     edx, 455h; wchar_t *
0x1802ba522  mov     rcx, r13; this
0x1802ba525  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802ba52a  mov     r14d, dword ptr [rsp+78h+var_40]
0x1802ba52f  mov     rbp, [rsp+78h+var_48]
0x1802ba534  jmp     short loc_1802BA577
0x1802ba536  mov     eax, [rbx+90h]
0x1802ba53c  cmp     eax, [rsp+78h+arg_20]
0x1802ba543  ja      short loc_1802BA585
0x1802ba545  mov     r8d, eax; Size
0x1802ba548  mov     rcx, rsi; void *
0x1802ba54b  call    memcpy_0
0x1802ba550  mov     r9d, [rbx+90h]; wchar_t *
0x1802ba557  mov     rdi, [rsp+78h+arg_28]
0x1802ba55f  mov     [rdi], r9d
0x1802ba562  lea     r8, aProxyDwrDoneOt; "[Proxy] dwr done, other, cb: %d\n"
0x1802ba569  mov     edx, 45Eh; wchar_t *
0x1802ba56e  mov     rcx, r13; this
0x1802ba571  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802ba576  nop
0x1802ba577  mov     rcx, r12; this
0x1802ba57a  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x1802ba57f  nop
0x1802ba580  jmp     loc_180073D67
0x1802ba585  call    ?ServerResponseError@@YAXXZ; ServerResponseError(void)
```
