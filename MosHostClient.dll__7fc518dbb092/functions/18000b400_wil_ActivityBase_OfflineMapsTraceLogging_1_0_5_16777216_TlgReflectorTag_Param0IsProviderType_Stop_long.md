# wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000b400`
- end: `0x18000b5ac`
- name: `?Stop@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `428`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a810`
- `0x18000d760`
- `0x18000f0c0`
- `0x18000fdb0`

## callees

- `0x18000163c`
- `0x180002550`
- `0x180002fc4`
- `0x180005c50`
- `0x180006fc0`
- `0x180009bb4`
- `0x18000ae98`
- `0x18000b400`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b464`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b464`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b490`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b490`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b520`

## string_xrefs

- `0x18000b53b`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1)
{
  __int64 v2; // rax
  int v3; // esi
  int v4; // edi
  int v5; // esi
  const struct _tlgProvider_t *result; // rax
  const struct _tlgProvider_t *v7; // rdi
  __int64 v8; // rbx
  const struct _tlgProvider_t **v9; // rcx
  const struct wil::FailureInfo *v10; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v15; // [rsp+70h] [rbp-90h]
  __int64 v16; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+98h] [rbp-68h]
  void *retaddr; // [rsp+128h] [rbp+28h]

  wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = *(_QWORD *)(a1 + 272);
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v10);
  }
  v4 = *(_DWORD *)(v2 + 72);
  if ( v4 >= 0 )
  {
    *(_DWORD *)(v2 + 72) = 0;
    v4 = 0;
  }
  v5 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v5;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
    result = OfflineMapsTraceLogging::Provider();
    v7 = result;
    if ( *(_DWORD *)result > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v13 = 0x1000000;
      p_CurrentThreadId = &CurrentThreadId;
      v20 = 4;
      p_SRWLock = &SRWLock;
      v18 = 4;
      v15 = &v13;
      v16 = 8;
      result = (const struct _tlgProvider_t *)tlgWriteTransfer_EventWriteTransfer(
                                                v7,
                                                &unk_180017E30,
                                                *(_QWORD *)(a1 + 272) + 8LL,
                                                0,
                                                5,
                                                v14);
    }
  }
  else
  {
    result = (const struct _tlgProvider_t *)wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
                                              (_QWORD *)a1,
                                              v4);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v8 = a1 + 288;
    if ( *(_DWORD *)(v8 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v8 + 24) = 0;
    v9 = *(const struct _tlgProvider_t ***)v8;
    while ( 1 )
    {
      result = *v9;
      if ( !*v9 )
        break;
      if ( result == (const struct _tlgProvider_t *)v8 )
      {
        result = *(const struct _tlgProvider_t **)(v8 + 16);
        *v9 = result;
        break;
      }
      v9 = (const struct _tlgProvider_t **)((char *)result + 16);
      *(_QWORD *)v8 = (char *)result + 16;
    }
    *(_QWORD *)v8 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b400  push    rbp
0x18000b402  push    rbx
0x18000b403  push    rsi
0x18000b404  push    rdi
0x18000b405  lea     rbp, [rsp-8]
0x18000b40a  sub     rsp, 108h
0x18000b411  mov     rax, cs:__security_cookie
0x18000b418  xor     rax, rsp
0x18000b41b  mov     [rbp+20h+var_30], rax
0x18000b41f  mov     rbx, rcx
0x18000b422  lea     rdx, [rsp+120h+SRWLock]
0x18000b427  call    ?LockExclusive@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b42c  mov     rax, [rbx+110h]
0x18000b433  mov     esi, [rax+0F8h]
0x18000b439  cmp     esi, 1
0x18000b43c  jl      loc_18000B58F
0x18000b442  mov     edi, [rax+48h]
0x18000b445  test    edi, edi
0x18000b447  js      short loc_18000B452
0x18000b449  mov     dword ptr [rax+48h], 0
0x18000b450  xor     edi, edi
0x18000b452  dec     esi
0x18000b454  mov     [rax+0F8h], esi
0x18000b45a  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x18000b45f  test    rcx, rcx
0x18000b462  jz      short loc_18000B46A
0x18000b464  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b46a  test    esi, esi
0x18000b46c  jnz     short loc_18000B47D
0x18000b46e  mov     edx, edi
0x18000b470  mov     rcx, rbx
0x18000b473  call    ?ReportStopActivity@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000b478  jmp     loc_18000B510
0x18000b47d  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x18000b482  mov     rdi, rax
0x18000b485  mov     ecx, [rax]
0x18000b487  cmp     ecx, 5
0x18000b48a  jbe     loc_18000B510
0x18000b490  call    cs:__imp_GetCurrentThreadId
0x18000b496  mov     [rsp+120h+var_F0], eax
0x18000b49a  mov     dword ptr [rsp+120h+SRWLock], 0
0x18000b4a2  mov     [rsp+120h+var_E0], 1000000h
0x18000b4ab  lea     rax, [rsp+120h+var_F0]
0x18000b4b0  mov     [rbp+20h+var_90], rax
0x18000b4b4  mov     [rbp+20h+var_88], 4
0x18000b4bc  lea     rax, [rsp+120h+SRWLock]
0x18000b4c1  mov     [rbp+20h+var_A0], rax
0x18000b4c5  mov     [rbp+20h+var_98], 4
0x18000b4cd  lea     rax, [rsp+120h+var_E0]
0x18000b4d2  mov     [rsp+120h+var_B0], rax
0x18000b4d7  mov     [rsp+120h+var_A8], 8
0x18000b4e0  mov     r8, [rbx+110h]
0x18000b4e7  add     r8, 8
0x18000b4eb  lea     rax, [rsp+120h+var_D0]
0x18000b4f0  mov     [rsp+120h+var_F8], rax
0x18000b4f5  mov     [rsp+120h+var_100], 5
0x18000b4fd  xor     r9d, r9d
0x18000b500  lea     rdx, unk_180017E30
0x18000b507  mov     rcx, rdi
0x18000b50a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b50f  nop
0x18000b510  cmp     dword ptr [rbx+138h], 0
0x18000b517  jz      short loc_18000B577
0x18000b519  add     rbx, 120h
0x18000b520  call    cs:__imp_GetCurrentThreadId
0x18000b526  cmp     [rbx+18h], eax
0x18000b529  jz      short loc_18000B547
0x18000b52b  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000b532  test    rax, rax
0x18000b535  jz      short loc_18000B547
0x18000b537  mov     rdx, [rbp+28h]
0x18000b53b  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000b542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b547  mov     dword ptr [rbx+18h], 0
0x18000b54e  mov     rcx, [rbx]
0x18000b551  jmp     short loc_18000B55F
0x18000b553  cmp     rax, rbx
0x18000b556  jz      short loc_18000B569
0x18000b558  lea     rcx, [rax+10h]
0x18000b55c  mov     [rbx], rcx
0x18000b55f  mov     rax, [rcx]
0x18000b562  test    rax, rax
0x18000b565  jnz     short loc_18000B553
0x18000b567  jmp     short loc_18000B570
0x18000b569  mov     rax, [rbx+10h]
0x18000b56d  mov     [rcx], rax
0x18000b570  mov     qword ptr [rbx], 0
0x18000b577  mov     rcx, [rbp+20h+var_30]
0x18000b57b  xor     rcx, rsp; StackCookie
0x18000b57e  call    __security_check_cookie
0x18000b583  add     rsp, 108h
0x18000b58a  pop     rdi
0x18000b58b  pop     rsi
0x18000b58c  pop     rbx
0x18000b58d  pop     rbp
0x18000b58e  retn
0x18000b58f  xor     edx, edx; Val
0x18000b591  mov     r8d, 98h; Size
0x18000b597  lea     rcx, [rsp+120h+var_D0]; void *
0x18000b59c  call    memset_0
0x18000b5a1  lea     rcx, [rsp+120h+var_D0]; this
0x18000b5a6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
