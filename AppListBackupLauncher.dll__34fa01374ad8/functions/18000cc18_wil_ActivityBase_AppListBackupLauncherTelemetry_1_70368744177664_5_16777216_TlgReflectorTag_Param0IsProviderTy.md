# wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000cc18`
- end: `0x18000cdee`
- name: `?Stop@?$ActivityBase@VAppListBackupLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000dfe0`

## callees

- `0x180001a4c`
- `0x180002300`
- `0x180002de0`
- `0x1800091f0`
- `0x180009e0c`
- `0x18000cc18`
- `0x18000de50`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cd5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cd5b`

## string_xrefs

- `0x18000cd76`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 *v8; // rcx
  const struct wil::FailureInfo *v9; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v12; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v14; // [rsp+70h] [rbp-39h]
  __int64 v15; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v17; // [rsp+88h] [rbp-21h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-19h]
  __int64 v19; // [rsp+98h] [rbp-11h]
  void *retaddr; // [rsp+108h] [rbp+5Fh]

  wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v9);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    result = (__int64)AppListBackupLauncherTelemetry::Provider();
    v6 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v12 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v19 = 4;
        p_SRWLock = &SRWLock;
        v17 = 4;
        v14 = &v12;
        v15 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v6, byte_180015481, *(_QWORD *)(a1 + 272) + 8LL, 0, 5, v13);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v7 = a1 + 288;
    if ( *(_DWORD *)(v7 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v7 + 24) = 0;
    v8 = *(__int64 **)v7;
    while ( 1 )
    {
      result = *v8;
      if ( !*v8 )
        break;
      if ( result == v7 )
      {
        result = *(_QWORD *)(v7 + 16);
        *v8 = result;
        break;
      }
      v8 = (__int64 *)(result + 16);
      *(_QWORD *)v7 = result + 16;
    }
    *(_QWORD *)v7 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000cc18  mov     [rsp-8+arg_8], rbx
0x18000cc1d  mov     [rsp-8+arg_10], rdi
0x18000cc22  push    rbp
0x18000cc23  lea     rbp, [rsp-57h]
0x18000cc28  sub     rsp, 100h
0x18000cc2f  mov     rax, cs:__security_cookie
0x18000cc36  xor     rax, rsp
0x18000cc39  mov     [rbp+57h+var_10], rax
0x18000cc3d  mov     rbx, rcx
0x18000cc40  lea     rdx, [rbp+57h+SRWLock]
0x18000cc44  call    ?LockExclusive@?$ActivityBase@VAppListBackupLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cc49  mov     rax, [rbx+110h]
0x18000cc50  mov     edi, [rax+0F8h]
0x18000cc56  cmp     edi, 1
0x18000cc59  jl      loc_18000CDD3
0x18000cc5f  cmp     dword ptr [rax+48h], 0
0x18000cc63  jl      short loc_18000CC6C
0x18000cc65  mov     dword ptr [rax+48h], 0
0x18000cc6c  dec     edi
0x18000cc6e  mov     [rax+0F8h], edi
0x18000cc74  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000cc78  test    rcx, rcx
0x18000cc7b  jz      short loc_18000CC83
0x18000cc7d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc83  test    edi, edi
0x18000cc85  jnz     short loc_18000CC9B
0x18000cc87  mov     rax, [rbx]
0x18000cc8a  mov     rcx, rbx
0x18000cc8d  mov     rax, [rax+8]
0x18000cc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc96  jmp     loc_18000CD4B
0x18000cc9b  call    ?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppListBackupLauncherTelemetry::Provider(void)
0x18000cca0  mov     rdi, rax
0x18000cca3  mov     ecx, [rax]
0x18000cca5  cmp     ecx, 5
0x18000cca8  jbe     loc_18000CD4B
0x18000ccae  mov     rax, [rax+18h]
0x18000ccb2  mov     rcx, [rdi+10h]
0x18000ccb6  mov     rdx, 400000000000h
0x18000ccc0  test    rdx, rcx
0x18000ccc3  jz      loc_18000CD4B
0x18000ccc9  mov     rcx, rax
0x18000cccc  and     rcx, rdx
0x18000cccf  cmp     rcx, rax
0x18000ccd2  jnz     short loc_18000CD4B
0x18000ccd4  call    cs:__imp_GetCurrentThreadId
0x18000ccda  mov     [rbp+57h+var_D0], eax
0x18000ccdd  mov     dword ptr [rbp+57h+SRWLock], 0
0x18000cce4  mov     [rbp+57h+var_C0], 1000000h
0x18000ccec  lea     rax, [rbp+57h+var_D0]
0x18000ccf0  mov     [rbp+57h+var_70], rax
0x18000ccf4  mov     [rbp+57h+var_68], 4
0x18000ccfc  lea     rax, [rbp+57h+SRWLock]
0x18000cd00  mov     [rbp+57h+var_80], rax
0x18000cd04  mov     [rbp+57h+var_78], 4
0x18000cd0c  lea     rax, [rbp+57h+var_C0]
0x18000cd10  mov     [rbp+57h+var_90], rax
0x18000cd14  mov     [rbp+57h+var_88], 8
0x18000cd1c  mov     r8, [rbx+110h]
0x18000cd23  add     r8, 8
0x18000cd27  lea     rax, [rbp+57h+var_B0]
0x18000cd2b  mov     [rsp+100h+var_D8], rax
0x18000cd30  mov     [rsp+100h+var_E0], 5
0x18000cd38  xor     r9d, r9d
0x18000cd3b  lea     rdx, byte_180015481
0x18000cd42  mov     rcx, rdi
0x18000cd45  call    _tlgWriteTransfer_EventWriteTransfer
0x18000cd4a  nop
0x18000cd4b  cmp     dword ptr [rbx+138h], 0
0x18000cd52  jz      short loc_18000CDB2
0x18000cd54  add     rbx, 120h
0x18000cd5b  call    cs:__imp_GetCurrentThreadId
0x18000cd61  cmp     [rbx+18h], eax
0x18000cd64  jz      short loc_18000CD82
0x18000cd66  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000cd6d  test    rax, rax
0x18000cd70  jz      short loc_18000CD82
0x18000cd72  mov     rdx, [rbp+5Fh]
0x18000cd76  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000cd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd82  mov     dword ptr [rbx+18h], 0
0x18000cd89  mov     rcx, [rbx]
0x18000cd8c  jmp     short loc_18000CD9A
0x18000cd8e  cmp     rax, rbx
0x18000cd91  jz      short loc_18000CDA4
0x18000cd93  lea     rcx, [rax+10h]
0x18000cd97  mov     [rbx], rcx
0x18000cd9a  mov     rax, [rcx]
0x18000cd9d  test    rax, rax
0x18000cda0  jnz     short loc_18000CD8E
0x18000cda2  jmp     short loc_18000CDAB
0x18000cda4  mov     rax, [rbx+10h]
0x18000cda8  mov     [rcx], rax
0x18000cdab  mov     qword ptr [rbx], 0
0x18000cdb2  mov     rcx, [rbp+57h+var_10]
0x18000cdb6  xor     rcx, rsp; StackCookie
0x18000cdb9  call    __security_check_cookie
0x18000cdbe  lea     r11, [rsp+100h+var_s0]
0x18000cdc6  mov     rbx, [r11+18h]
0x18000cdca  mov     rdi, [r11+20h]
0x18000cdce  mov     rsp, r11
0x18000cdd1  pop     rbp
0x18000cdd2  retn
0x18000cdd3  xor     edx, edx; Val
0x18000cdd5  mov     r8d, 98h; Size
0x18000cddb  lea     rcx, [rbp+57h+var_B0]; void *
0x18000cddf  call    memset_0
0x18000cde4  lea     rcx, [rbp+57h+var_B0]; this
0x18000cde8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
