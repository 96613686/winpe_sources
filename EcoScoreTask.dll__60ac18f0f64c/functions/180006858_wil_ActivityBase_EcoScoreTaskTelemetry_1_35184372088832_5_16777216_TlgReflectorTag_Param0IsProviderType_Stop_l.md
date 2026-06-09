# wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180006858`
- end: `0x180006a2d`
- name: `?Stop@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800073f0`

## callees

- `0x1800018dc`
- `0x180004d4c`
- `0x180005760`
- `0x180006858`
- `0x180007260`
- `0x180007c62`
- `0x180007c90`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006914`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000699a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006914`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000699a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800068bd`

## string_xrefs

- `0x1800069b5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // edi
  RTL_SRWLOCK *v4; // rcx
  int v5; // edi
  __int64 result; // rax
  __int64 v7; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 *v11; // rcx
  const struct wil::FailureInfo *v12; // rdx
  DWORD v13; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v15; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v16[32]; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v17; // [rsp+70h] [rbp-39h]
  __int64 v18; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v20; // [rsp+88h] [rbp-21h]
  DWORD *v21; // [rsp+90h] [rbp-19h]
  __int64 v22; // [rsp+98h] [rbp-11h]
  void *retaddr; // [rsp+108h] [rbp+5Fh]

  wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v16, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v16, v12);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = SRWLock;
  v5 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v5;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( v5 )
  {
    result = (__int64)EcoScoreTaskTelemetry::Provider();
    v7 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (result & 0x200000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        v9 = *(_QWORD *)(a1 + 272);
        v13 = CurrentThreadId;
        LODWORD(SRWLock) = 0;
        v21 = &v13;
        v15 = 0x1000000;
        p_SRWLock = &SRWLock;
        v22 = 4;
        v17 = &v15;
        v20 = 4;
        v18 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v7, byte_18000AFE5, v9 + 8, 0, 5, v16);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v10 = a1 + 288;
    if ( *(_DWORD *)(v10 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v11 = *(__int64 **)v10;
    *(_DWORD *)(v10 + 24) = 0;
    while ( 1 )
    {
      result = *v11;
      if ( !*v11 )
        break;
      if ( result == v10 )
      {
        result = *(_QWORD *)(v10 + 16);
        *v11 = result;
        break;
      }
      v11 = (__int64 *)(result + 16);
      *(_QWORD *)v10 = result + 16;
    }
    *(_QWORD *)v10 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006858  mov     [rsp-8+arg_8], rbx
0x18000685d  mov     [rsp-8+arg_10], rdi
0x180006862  push    rbp
0x180006863  lea     rbp, [rsp-57h]
0x180006868  sub     rsp, 100h
0x18000686f  mov     rax, cs:__security_cookie
0x180006876  xor     rax, rsp
0x180006879  mov     [rbp+57h+var_10], rax
0x18000687d  lea     rdx, [rbp+57h+SRWLock]
0x180006881  mov     rbx, rcx
0x180006884  call    ?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180006889  mov     rax, [rbx+110h]
0x180006890  mov     edi, [rax+0F8h]
0x180006896  cmp     edi, 1
0x180006899  jl      loc_180006A12
0x18000689f  cmp     dword ptr [rax+48h], 0
0x1800068a3  jl      short loc_1800068AC
0x1800068a5  mov     dword ptr [rax+48h], 0
0x1800068ac  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800068b0  dec     edi
0x1800068b2  mov     [rax+0F8h], edi
0x1800068b8  test    rcx, rcx
0x1800068bb  jz      short loc_1800068C3
0x1800068bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800068c3  test    edi, edi
0x1800068c5  jnz     short loc_1800068DB
0x1800068c7  mov     rax, [rbx]
0x1800068ca  mov     rcx, rbx
0x1800068cd  mov     rax, [rax+8]
0x1800068d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d6  jmp     loc_18000698A
0x1800068db  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x1800068e0  mov     rdi, rax
0x1800068e3  mov     ecx, [rax]
0x1800068e5  cmp     ecx, 5
0x1800068e8  jbe     loc_18000698A
0x1800068ee  mov     rax, [rax+18h]
0x1800068f2  mov     rdx, 200000000000h
0x1800068fc  mov     rcx, [rdi+10h]
0x180006900  test    rdx, rcx
0x180006903  jz      loc_18000698A
0x180006909  mov     rcx, rax
0x18000690c  and     rcx, rdx
0x18000690f  cmp     rcx, rax
0x180006912  jnz     short loc_18000698A
0x180006914  call    cs:__imp_GetCurrentThreadId
0x18000691a  mov     r8, [rbx+110h]
0x180006921  lea     rdx, byte_18000AFE5
0x180006928  mov     [rbp+57h+var_D0], eax
0x18000692b  add     r8, 8
0x18000692f  lea     rax, [rbp+57h+var_D0]
0x180006933  mov     dword ptr [rbp+57h+SRWLock], 0
0x18000693a  mov     [rbp+57h+var_70], rax
0x18000693e  xor     r9d, r9d
0x180006941  lea     rax, [rbp+57h+SRWLock]
0x180006945  mov     [rbp+57h+var_C0], 1000000h
0x18000694d  mov     [rbp+57h+var_80], rax
0x180006951  mov     rcx, rdi
0x180006954  lea     rax, [rbp+57h+var_C0]
0x180006958  mov     [rbp+57h+var_68], 4
0x180006960  mov     [rbp+57h+var_90], rax
0x180006964  lea     rax, [rbp+57h+var_B0]
0x180006968  mov     [rsp+100h+var_D8], rax
0x18000696d  mov     [rsp+100h+var_E0], 5
0x180006975  mov     [rbp+57h+var_78], 4
0x18000697d  mov     [rbp+57h+var_88], 8
0x180006985  call    _tlgWriteTransfer_EventWriteTransfer
0x18000698a  cmp     dword ptr [rbx+138h], 0
0x180006991  jz      short loc_1800069F1
0x180006993  add     rbx, 120h
0x18000699a  call    cs:__imp_GetCurrentThreadId
0x1800069a0  cmp     [rbx+18h], eax
0x1800069a3  jz      short loc_1800069C1
0x1800069a5  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800069ac  test    rax, rax
0x1800069af  jz      short loc_1800069C1
0x1800069b1  mov     rdx, [rbp+5Fh]
0x1800069b5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800069bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c1  mov     rcx, [rbx]
0x1800069c4  mov     dword ptr [rbx+18h], 0
0x1800069cb  jmp     short loc_1800069D9
0x1800069cd  cmp     rax, rbx
0x1800069d0  jz      short loc_1800069E3
0x1800069d2  lea     rcx, [rax+10h]
0x1800069d6  mov     [rbx], rcx
0x1800069d9  mov     rax, [rcx]
0x1800069dc  test    rax, rax
0x1800069df  jnz     short loc_1800069CD
0x1800069e1  jmp     short loc_1800069EA
0x1800069e3  mov     rax, [rbx+10h]
0x1800069e7  mov     [rcx], rax
0x1800069ea  mov     qword ptr [rbx], 0
0x1800069f1  mov     rcx, [rbp+57h+var_10]
0x1800069f5  xor     rcx, rsp; StackCookie
0x1800069f8  call    __security_check_cookie
0x1800069fd  lea     r11, [rsp+100h+var_s0]
0x180006a05  mov     rbx, [r11+18h]
0x180006a09  mov     rdi, [r11+20h]
0x180006a0d  mov     rsp, r11
0x180006a10  pop     rbp
0x180006a11  retn
0x180006a12  xor     edx, edx; Val
0x180006a14  lea     rcx, [rbp+57h+var_B0]; void *
0x180006a18  mov     r8d, 98h; Size
0x180006a1e  call    memset_0
0x180006a23  lea     rcx, [rbp+57h+var_B0]; this
0x180006a27  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
