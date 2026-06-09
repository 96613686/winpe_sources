# wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002e778`
- end: `0x18002e94e`
- name: `?Stop@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002fa90`

## callees

- `0x180001c7c`
- `0x1800268ef`
- `0x18002b340`
- `0x18002befc`
- `0x18002e778`
- `0x18002f900`
- `0x1800350e0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e834`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e834`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e8bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e7dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002e7dd`

## string_xrefs

- `0x18002e8d6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
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

  wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
    result = (__int64)PowerGridForecastTaskTelemetry::Provider();
    v6 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0 && (result & 0x200000000000LL) == result )
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
        result = tlgWriteTransfer_EventWriteTransfer(v6, byte_18003E345, *(_QWORD *)(a1 + 272) + 8LL, 0, 5, v13);
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
0x18002e778  mov     [rsp-8+arg_8], rbx
0x18002e77d  mov     [rsp-8+arg_10], rdi
0x18002e782  push    rbp
0x18002e783  lea     rbp, [rsp-57h]
0x18002e788  sub     rsp, 100h
0x18002e78f  mov     rax, cs:__security_cookie
0x18002e796  xor     rax, rsp
0x18002e799  mov     [rbp+57h+var_10], rax
0x18002e79d  mov     rbx, rcx
0x18002e7a0  lea     rdx, [rbp+57h+SRWLock]
0x18002e7a4  call    ?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002e7a9  mov     rax, [rbx+110h]
0x18002e7b0  mov     edi, [rax+0F8h]
0x18002e7b6  cmp     edi, 1
0x18002e7b9  jl      loc_18002E933
0x18002e7bf  cmp     dword ptr [rax+48h], 0
0x18002e7c3  jl      short loc_18002E7CC
0x18002e7c5  mov     dword ptr [rax+48h], 0
0x18002e7cc  dec     edi
0x18002e7ce  mov     [rax+0F8h], edi
0x18002e7d4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002e7d8  test    rcx, rcx
0x18002e7db  jz      short loc_18002E7E3
0x18002e7dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18002e7e3  test    edi, edi
0x18002e7e5  jnz     short loc_18002E7FB
0x18002e7e7  mov     rax, [rbx]
0x18002e7ea  mov     rcx, rbx
0x18002e7ed  mov     rax, [rax+8]
0x18002e7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7f6  jmp     loc_18002E8AB
0x18002e7fb  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002e800  mov     rdi, rax
0x18002e803  mov     ecx, [rax]
0x18002e805  cmp     ecx, 5
0x18002e808  jbe     loc_18002E8AB
0x18002e80e  mov     rax, [rax+18h]
0x18002e812  mov     rcx, [rdi+10h]
0x18002e816  mov     rdx, 200000000000h
0x18002e820  test    rdx, rcx
0x18002e823  jz      loc_18002E8AB
0x18002e829  mov     rcx, rax
0x18002e82c  and     rcx, rdx
0x18002e82f  cmp     rcx, rax
0x18002e832  jnz     short loc_18002E8AB
0x18002e834  call    cs:__imp_GetCurrentThreadId
0x18002e83a  mov     [rbp+57h+var_D0], eax
0x18002e83d  mov     dword ptr [rbp+57h+SRWLock], 0
0x18002e844  mov     [rbp+57h+var_C0], 1000000h
0x18002e84c  lea     rax, [rbp+57h+var_D0]
0x18002e850  mov     [rbp+57h+var_70], rax
0x18002e854  mov     [rbp+57h+var_68], 4
0x18002e85c  lea     rax, [rbp+57h+SRWLock]
0x18002e860  mov     [rbp+57h+var_80], rax
0x18002e864  mov     [rbp+57h+var_78], 4
0x18002e86c  lea     rax, [rbp+57h+var_C0]
0x18002e870  mov     [rbp+57h+var_90], rax
0x18002e874  mov     [rbp+57h+var_88], 8
0x18002e87c  mov     r8, [rbx+110h]
0x18002e883  add     r8, 8
0x18002e887  lea     rax, [rbp+57h+var_B0]
0x18002e88b  mov     [rsp+100h+var_D8], rax
0x18002e890  mov     [rsp+100h+var_E0], 5
0x18002e898  xor     r9d, r9d
0x18002e89b  lea     rdx, byte_18003E345
0x18002e8a2  mov     rcx, rdi
0x18002e8a5  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e8aa  nop
0x18002e8ab  cmp     dword ptr [rbx+138h], 0
0x18002e8b2  jz      short loc_18002E912
0x18002e8b4  add     rbx, 120h
0x18002e8bb  call    cs:__imp_GetCurrentThreadId
0x18002e8c1  cmp     [rbx+18h], eax
0x18002e8c4  jz      short loc_18002E8E2
0x18002e8c6  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002e8cd  test    rax, rax
0x18002e8d0  jz      short loc_18002E8E2
0x18002e8d2  mov     rdx, [rbp+5Fh]
0x18002e8d6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002e8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8e2  mov     dword ptr [rbx+18h], 0
0x18002e8e9  mov     rcx, [rbx]
0x18002e8ec  jmp     short loc_18002E8FA
0x18002e8ee  cmp     rax, rbx
0x18002e8f1  jz      short loc_18002E904
0x18002e8f3  lea     rcx, [rax+10h]
0x18002e8f7  mov     [rbx], rcx
0x18002e8fa  mov     rax, [rcx]
0x18002e8fd  test    rax, rax
0x18002e900  jnz     short loc_18002E8EE
0x18002e902  jmp     short loc_18002E90B
0x18002e904  mov     rax, [rbx+10h]
0x18002e908  mov     [rcx], rax
0x18002e90b  mov     qword ptr [rbx], 0
0x18002e912  mov     rcx, [rbp+57h+var_10]
0x18002e916  xor     rcx, rsp; StackCookie
0x18002e919  call    __security_check_cookie
0x18002e91e  lea     r11, [rsp+100h+var_s0]
0x18002e926  mov     rbx, [r11+18h]
0x18002e92a  mov     rdi, [r11+20h]
0x18002e92e  mov     rsp, r11
0x18002e931  pop     rbp
0x18002e932  retn
0x18002e933  xor     edx, edx; Val
0x18002e935  mov     r8d, 98h; Size
0x18002e93b  lea     rcx, [rbp+57h+var_B0]; void *
0x18002e93f  call    memset_0
0x18002e944  lea     rcx, [rbp+57h+var_B0]; this
0x18002e948  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
