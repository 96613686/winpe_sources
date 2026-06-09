# TraceLog::Providers::Reliability::NamedCallContextActivity::StartActivity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180020720`
- end: `0x1800208d0`
- name: `?StartActivity@NamedCallContextActivity@Reliability@Providers@TraceLog@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `432`
- prototype: `int __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001ff88`

## callees

- `0x180001d7c`
- `0x1800032a0`
- `0x180007af0`
- `0x180010810`
- `0x1800203f8`
- `0x180020720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020796`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020796`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002089e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002089e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020775`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180020775`

## pseudocode

```c
int __fastcall TraceLog::Providers::Reliability::NamedCallContextActivity::StartActivity(__int64 a1, const WCHAR *a2)
{
  __int64 v4; // rsi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *Local; // rax
  const struct _tlgProvider_t *v7; // rsi
  __int64 v8; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // eax
  const struct _tlgProvider_t **v14; // rbx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v19; // [rsp+60h] [rbp+7h]
  __int64 v20; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v22; // [rsp+78h] [rbp+1Fh]
  const WCHAR *v23; // [rsp+80h] [rbp+27h]
  int v24; // [rsp+88h] [rbp+2Fh]
  int v25; // [rsp+8Ch] [rbp+33h]

  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  if ( *(_DWORD *)TraceLog::Providers::Reliability::Provider() <= 4u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  v5 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  Local = TraceLog::Providers::Reliability::Provider();
  v7 = Local;
  v8 = *(unsigned int *)Local;
  if ( (unsigned int)v8 > 4 )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v17 = 0x1000000;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    if ( a2 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v13 = 2 * v12 + 2;
    }
    else
    {
      a2 = &SubKey;
      v13 = 2;
    }
    v24 = v13;
    v23 = a2;
    p_SRWLock = &SRWLock;
    v25 = 0;
    v19 = &v17;
    v22 = 4;
    v20 = 8;
    LODWORD(Local) = tlgWriteTransfer_EventWriteTransfer(v7, byte_18003D483, v10 + 8, v11, 5, v18);
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v14 = (const struct _tlgProvider_t **)(a1 + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (const struct _tlgProvider_t *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                               v8,
                                               1);
      *v14 = Local;
      if ( Local )
      {
        *(_QWORD *)(a1 + 304) = *(_QWORD *)Local;
        *(_QWORD *)Local = v14;
        LODWORD(Local) = GetCurrentThreadId();
        *(_DWORD *)(a1 + 312) = (_DWORD)Local;
      }
    }
    else
    {
      *v14 = 0;
    }
  }
  return (int)Local;
}

```

## disassembly

```asm
0x180020720  mov     [rsp-8+arg_8], rbx
0x180020725  mov     [rsp-8+arg_10], rsi
0x18002072a  push    rbp
0x18002072b  push    rdi
0x18002072c  push    r14
0x18002072e  lea     rbp, [rsp-47h]
0x180020733  sub     rsp, 0A0h
0x18002073a  mov     rax, cs:__security_cookie
0x180020741  xor     rax, rsp
0x180020744  mov     [rbp+57h+var_20], rax
0x180020748  mov     rbx, rdx
0x18002074b  mov     rdi, rcx
0x18002074e  lea     rdx, [rbp+57h+SRWLock]
0x180020752  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020757  mov     rsi, [rdi+110h]
0x18002075e  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180020763  mov     r8d, [rax]
0x180020766  cmp     r8d, 4
0x18002076a  jbe     short loc_18002077D
0x18002076c  lea     rdx, [rsi+8]; ActivityId
0x180020770  mov     ecx, 3; ControlCode
0x180020775  call    cs:__imp_EventActivityIdControl
0x18002077b  jmp     short loc_180020784
0x18002077d  xorps   xmm0, xmm0
0x180020780  movups  xmmword ptr [rsi+8], xmm0
0x180020784  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180020788  xor     r14d, r14d
0x18002078b  mov     dword ptr [rsi], 1
0x180020791  test    rcx, rcx
0x180020794  jz      short loc_18002079C
0x180020796  call    cs:__imp_ReleaseSRWLockExclusive
0x18002079c  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x1800207a1  mov     rsi, rax
0x1800207a4  mov     ecx, [rax]
0x1800207a6  cmp     ecx, 4
0x1800207a9  jbe     loc_18002086C
0x1800207af  cmp     qword ptr [rbx+18h], 7
0x1800207b4  jbe     short loc_1800207B9
0x1800207b6  mov     rbx, [rbx]
0x1800207b9  call    cs:__imp_GetCurrentThreadId
0x1800207bf  mov     r8, [rdi+110h]
0x1800207c6  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800207c9  mov     [rbp+57h+var_78], 1000000h
0x1800207d1  cmp     [r8+4], r14b
0x1800207d5  jz      short loc_1800207F2
0x1800207d7  lea     r9, [r8+18h]
0x1800207db  cmp     [r9], r14d
0x1800207de  jnz     short loc_1800207F5
0x1800207e0  cmp     [r9+4], r14d
0x1800207e4  jnz     short loc_1800207F5
0x1800207e6  cmp     [r9+8], r14d
0x1800207ea  jnz     short loc_1800207F5
0x1800207ec  cmp     [r9+0Ch], r14d
0x1800207f0  jnz     short loc_1800207F5
0x1800207f2  mov     r9, r14
0x1800207f5  test    rbx, rbx
0x1800207f8  jz      short loc_180020811
0x1800207fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800207fe  inc     rax
0x180020801  cmp     [rbx+rax*2], r14w
0x180020806  jnz     short loc_1800207FE
0x180020808  lea     eax, ds:2[rax*2]
0x18002080f  jmp     short loc_18002081D
0x180020811  lea     rbx, SubKey
0x180020818  mov     eax, 2
0x18002081d  mov     [rbp+57h+var_28], eax
0x180020820  lea     rdx, byte_18003D483
0x180020827  lea     rax, [rbp+57h+SRWLock]
0x18002082b  mov     [rbp+57h+var_30], rbx
0x18002082f  mov     [rbp+57h+var_40], rax
0x180020833  add     r8, 8
0x180020837  lea     rax, [rbp+57h+var_78]
0x18002083b  mov     [rbp+57h+var_24], r14d
0x18002083f  mov     [rbp+57h+var_50], rax
0x180020843  mov     rcx, rsi
0x180020846  lea     rax, [rbp+57h+var_70]
0x18002084a  mov     [rbp+57h+var_38], 4
0x180020852  mov     [rsp+0B0h+var_88], rax
0x180020857  mov     [rsp+0B0h+var_90], 5
0x18002085f  mov     [rbp+57h+var_48], 8
0x180020867  call    _tlgWriteTransfer_EventWriteTransfer
0x18002086c  cmp     [rdi+138h], r14d
0x180020873  jnz     short loc_1800208AC
0x180020875  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002087c  lea     rbx, [rdi+120h]
0x180020883  jz      short loc_1800208A9
0x180020885  mov     dl, 1
0x180020887  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002088c  mov     [rbx], rax
0x18002088f  test    rax, rax
0x180020892  jz      short loc_1800208AC
0x180020894  mov     rcx, [rax]
0x180020897  mov     [rbx+10h], rcx
0x18002089b  mov     [rax], rbx
0x18002089e  call    cs:__imp_GetCurrentThreadId
0x1800208a4  mov     [rbx+18h], eax
0x1800208a7  jmp     short loc_1800208AC
0x1800208a9  mov     [rbx], r14
0x1800208ac  mov     rcx, [rbp+57h+var_20]
0x1800208b0  xor     rcx, rsp; StackCookie
0x1800208b3  call    __security_check_cookie
0x1800208b8  lea     r11, [rsp+0B0h+var_10]
0x1800208c0  mov     rbx, [r11+28h]
0x1800208c4  mov     rsi, [r11+30h]
0x1800208c8  mov     rsp, r11
0x1800208cb  pop     r14
0x1800208cd  pop     rdi
0x1800208ce  pop     rbp
0x1800208cf  retn
```
