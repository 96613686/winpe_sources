# Rdp::Utils::TP::CThreadPool::CThreadPool(Rdp::Utils::TP::CThreadPool::ThreadPoolType)

- ea: `0x18000c5a0`
- end: `0x18000c7e5`
- name: `??0CThreadPool@TP@Utils@Rdp@@QEAA@W4ThreadPoolType@0123@@Z`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bed8`

## callees

- `0x180007018`
- `0x18000c5a0`
- `0x18000e82c`
- `0x18000ed7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c712`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c772`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c712`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c70a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c74f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c70a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c74f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000c664`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000c664`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000c697`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000c697`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c6c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c6dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c6c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c6dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c761`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c78e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c761`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000c78e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000c76a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000c797`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000c76a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000c797`

## string_xrefs

- `0x18000c7c1`: `onecoreuap\termsrv\rdp_bin\win\common/inc/ThreadPool.h`
- `0x18000c7d3`: `onecoreuap\termsrv\rdp_bin\win\common/inc/ThreadPool.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Rdp::Utils::TP::CThreadPool::CThreadPool(__int64 a1)
{
  char *v2; // r14
  struct _TP_CLEANUP_GROUP **v3; // r12
  __int64 v4; // rsi
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rdi
  const char *v6; // r9
  const char *v7; // r9
  struct _TP_POOL *Threadpool; // r15
  DWORD LastError; // ebx
  DWORD v10; // eax
  struct _TP_CLEANUP_GROUP *v11; // rsi
  DWORD v12; // ebx
  struct _TP_CLEANUP_GROUP *v14; // [rsp+38h] [rbp-49h] BYREF
  char v15; // [rsp+40h] [rbp-41h] BYREF
  __int128 v16; // [rsp+48h] [rbp-39h] BYREF
  __int128 v17; // [rsp+58h] [rbp-29h]
  __int128 v18; // [rsp+78h] [rbp-9h]
  __int64 v19; // [rsp+88h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  struct _TP_POOL *ptpp; // [rsp+F8h] [rbp+77h]

  *(_QWORD *)a1 = &Rdp::Utils::TP::CThreadPool::`vftable';
  *(_DWORD *)(a1 + 8) = 0;
  v2 = (char *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  v3 = (struct _TP_CLEANUP_GROUP **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  v4 = a1 + 32;
  memset_0((void *)(a1 + 32), 0, 0x48u);
  *(_QWORD *)(a1 + 104) = 2;
  *(_OWORD *)(a1 + 128) = 0;
  *(_OWORD *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 176) = -1;
  *(_DWORD *)(a1 + 180) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 192) = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    a1 + 184,
    1);
  v16 = 3u;
  v19 = 72;
  *(_QWORD *)&v18 = 0;
  *((_QWORD *)&v18 + 1) = 0x100000000LL;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  v14 = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/ThreadPool.h",
      v6);
  v17 = (unsigned __int64)ThreadpoolCleanupGroup;
  if ( *(_DWORD *)(a1 + 8) == 1 )
  {
    Threadpool = CreateThreadpool(0);
    if ( v2 == &v15 )
    {
      if ( Threadpool )
        CloseThreadpool(Threadpool);
    }
    else
    {
      ptpp = *(struct _TP_POOL **)v2;
      if ( *(_QWORD *)v2 )
      {
        LastError = GetLastError();
        CloseThreadpool(ptpp);
        SetLastError(LastError);
      }
      *(_QWORD *)v2 = Threadpool;
    }
    if ( !*(_QWORD *)v2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/ThreadPool.h",
        v7);
    *((_QWORD *)&v16 + 1) = *(_QWORD *)v2;
  }
  if ( (__int128 *)v4 != &v16 )
  {
    v10 = GetLastError();
    SetLastError(v10);
    *(_OWORD *)v4 = v16;
    *(_OWORD *)(v4 + 16) = v17;
    *(_OWORD *)(v4 + 32) = 0;
    *(_OWORD *)(v4 + 48) = v18;
    *(_QWORD *)(v4 + 64) = v19;
  }
  if ( v3 != &v14 )
  {
    v11 = *v3;
    if ( *v3 )
    {
      v12 = GetLastError();
      CloseThreadpoolCleanupGroupMembers(v11, 1, 0);
      CloseThreadpoolCleanupGroup(v11);
      SetLastError(v12);
    }
    *v3 = ThreadpoolCleanupGroup;
    ThreadpoolCleanupGroup = 0;
  }
  if ( ThreadpoolCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(ThreadpoolCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(ThreadpoolCleanupGroup);
  }
  return a1;
}

```

## disassembly

```asm
0x18000c5a0  mov     rax, rsp
0x18000c5a3  mov     [rax+10h], rbx
0x18000c5a7  mov     [rax+8], rcx
0x18000c5ab  push    rbp
0x18000c5ac  push    rsi
0x18000c5ad  push    rdi
0x18000c5ae  push    r12
0x18000c5b0  push    r13
0x18000c5b2  push    r14
0x18000c5b4  push    r15
0x18000c5b6  lea     rbp, [rax-5Fh]
0x18000c5ba  sub     rsp, 0A0h
0x18000c5c1  movaps  xmmword ptr [rax-48h], xmm6
0x18000c5c5  mov     r13, rcx
0x18000c5c8  lea     rax, ??_7CThreadPool@TP@Utils@Rdp@@6B@; const Rdp::Utils::TP::CThreadPool::`vftable'
0x18000c5cf  mov     [rcx], rax
0x18000c5d2  xor     r15d, r15d
0x18000c5d5  mov     [rcx+8], r15d
0x18000c5d9  lea     r14, [rcx+10h]
0x18000c5dd  mov     [r14], r15
0x18000c5e0  lea     r12, [rcx+18h]
0x18000c5e4  mov     [r12], r15
0x18000c5e8  lea     rsi, [rcx+20h]
0x18000c5ec  xor     edx, edx; Val
0x18000c5ee  lea     r8d, [r15+48h]; Size
0x18000c5f2  mov     rcx, rsi; void *
0x18000c5f5  call    memset_0
0x18000c5fa  lea     rax, [r13+68h]
0x18000c5fe  mov     [rbp+57h+ptpp], rax
0x18000c602  mov     qword ptr [rax], 2
0x18000c609  xorps   xmm0, xmm0
0x18000c60c  movups  xmmword ptr [rax+18h], xmm0
0x18000c610  movups  xmmword ptr [rax+28h], xmm0
0x18000c614  movups  xmmword ptr [rax+38h], xmm0
0x18000c618  mov     [rax+8], r15
0x18000c61c  mov     [rax+10h], r15
0x18000c620  mov     dword ptr [rax+48h], 0FFFFFFFFh
0x18000c627  mov     [rax+4Ch], r15d
0x18000c62b  lea     rcx, [rax+50h]
0x18000c62f  mov     [rcx], r15
0x18000c632  mov     [rax+58h], r15d
0x18000c636  lea     edi, [r15+1]
0x18000c63a  mov     edx, edi
0x18000c63c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000c641  nop
0x18000c642  mov     qword ptr [rbp+57h+var_90], 3
0x18000c64a  mov     [rbp+57h+var_50], 48h ; 'H'
0x18000c652  mov     qword ptr [rbp+57h+var_90+8], r15
0x18000c656  xorps   xmm6, xmm6
0x18000c659  mov     qword ptr [rbp+57h+var_60], r15
0x18000c65d  mov     dword ptr [rbp+57h+var_60+8], r15d
0x18000c661  mov     dword ptr [rbp+57h+var_60+0Ch], edi
0x18000c664  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18000c66a  mov     rdi, rax
0x18000c66d  mov     [rbp+57h+var_A0], rax
0x18000c671  mov     eax, r15d
0x18000c674  test    rdi, rdi
0x18000c677  setnz   al
0x18000c67a  mov     rcx, [rbp+5Fh]; this
0x18000c67e  test    eax, eax
0x18000c680  jz      loc_18000C7D3
0x18000c686  mov     qword ptr [rbp+57h+var_80], rdi
0x18000c68a  mov     qword ptr [rbp+57h+var_80+8], r15
0x18000c68e  cmp     dword ptr [r13+8], 1
0x18000c693  jnz     short loc_18000C701
0x18000c695  xor     ecx, ecx; reserved
0x18000c697  call    cs:__imp_CreateThreadpool
0x18000c69d  mov     r15, rax
0x18000c6a0  lea     rax, [rbp+57h+var_98]
0x18000c6a4  cmp     r14, rax
0x18000c6a7  jz      short loc_18000C6D4
0x18000c6a9  mov     rax, [r14]
0x18000c6ac  mov     [rbp+57h+ptpp], rax
0x18000c6b0  test    rax, rax
0x18000c6b3  jz      short loc_18000C6CF
0x18000c6b5  call    cs:__imp_GetLastError
0x18000c6bb  mov     ebx, eax
0x18000c6bd  mov     rcx, [rbp+57h+ptpp]; ptpp
0x18000c6c1  call    cs:__imp_CloseThreadpool
0x18000c6c7  mov     ecx, ebx; dwErrCode
0x18000c6c9  call    cs:__imp_SetLastError
0x18000c6cf  mov     [r14], r15
0x18000c6d2  jmp     short loc_18000C6E2
0x18000c6d4  test    r15, r15
0x18000c6d7  jz      short loc_18000C6E2
0x18000c6d9  mov     rcx, r15; ptpp
0x18000c6dc  call    cs:__imp_CloseThreadpool
0x18000c6e2  mov     rdx, [r14]
0x18000c6e5  xor     r15d, r15d
0x18000c6e8  mov     eax, r15d
0x18000c6eb  test    rdx, rdx
0x18000c6ee  setnz   al
0x18000c6f1  mov     rcx, [rbp+5Fh]; this
0x18000c6f5  test    eax, eax
0x18000c6f7  jz      loc_18000C7C1
0x18000c6fd  mov     qword ptr [rbp+57h+var_90+8], rdx
0x18000c701  lea     rax, [rbp+57h+var_90]
0x18000c705  cmp     rsi, rax
0x18000c708  jz      short loc_18000C73D
0x18000c70a  call    cs:__imp_GetLastError
0x18000c710  mov     ecx, eax; dwErrCode
0x18000c712  call    cs:__imp_SetLastError
0x18000c718  movaps  xmm0, [rbp+57h+var_90]
0x18000c71c  movups  xmmword ptr [rsi], xmm0
0x18000c71f  movaps  xmm1, [rbp+57h+var_80]
0x18000c723  movups  xmmword ptr [rsi+10h], xmm1
0x18000c727  movups  xmmword ptr [rsi+20h], xmm6
0x18000c72b  movaps  xmm0, [rbp+57h+var_60]
0x18000c72f  movups  xmmword ptr [rsi+30h], xmm0
0x18000c733  movsd   xmm1, [rbp+57h+var_50]
0x18000c738  movsd   qword ptr [rsi+40h], xmm1
0x18000c73d  lea     rax, [rbp+57h+var_A0]
0x18000c741  cmp     r12, rax
0x18000c744  jz      short loc_18000C77F
0x18000c746  mov     rsi, [r12]
0x18000c74a  test    rsi, rsi
0x18000c74d  jz      short loc_18000C778
0x18000c74f  call    cs:__imp_GetLastError
0x18000c755  mov     ebx, eax
0x18000c757  xor     r8d, r8d; pvCleanupContext
0x18000c75a  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000c75e  mov     rcx, rsi; ptpcg
0x18000c761  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000c767  mov     rcx, rsi; ptpcg
0x18000c76a  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000c770  mov     ecx, ebx; dwErrCode
0x18000c772  call    cs:__imp_SetLastError
0x18000c778  mov     [r12], rdi
0x18000c77c  mov     rdi, r15
0x18000c77f  test    rdi, rdi
0x18000c782  jz      short loc_18000C79E
0x18000c784  xor     r8d, r8d; pvCleanupContext
0x18000c787  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000c78b  mov     rcx, rdi; ptpcg
0x18000c78e  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000c794  mov     rcx, rdi; ptpcg
0x18000c797  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000c79d  nop
0x18000c79e  mov     rax, r13
0x18000c7a1  lea     r11, [rsp+0D0h+var_30]
0x18000c7a9  mov     rbx, [r11+48h]
0x18000c7ad  movaps  xmm6, xmmword ptr [r11-10h]
0x18000c7b2  mov     rsp, r11
0x18000c7b5  pop     r15
0x18000c7b7  pop     r14
0x18000c7b9  pop     r13
0x18000c7bb  pop     r12
0x18000c7bd  pop     rdi
0x18000c7be  pop     rsi
0x18000c7bf  pop     rbp
0x18000c7c0  retn
0x18000c7c1  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000c7c8  mov     edx, 0C4h; void *
0x18000c7cd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000c7d3  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18000c7da  mov     edx, 0B3h; void *
0x18000c7df  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
