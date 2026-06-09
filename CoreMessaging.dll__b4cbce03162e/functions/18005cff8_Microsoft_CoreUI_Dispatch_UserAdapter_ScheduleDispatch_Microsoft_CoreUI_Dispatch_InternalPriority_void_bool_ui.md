# Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleDispatch(Microsoft::CoreUI::Dispatch::InternalPriority,void *,bool,uint)

- ea: `0x18005cff8`
- end: `0x18005d185`
- name: `?ScheduleDispatch@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@PEAX_NI@Z`
- size: `397`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008354`
- `0x18005db84`
- `0x180065bf0`
- `0x1800a63d0`

## callees

- `0x18000b018`
- `0x18000b0bc`
- `0x180039dbc`
- `0x18005cff8`
- `0x18005d75c`
- `0x18008ae1c`
- `0x18009e054`
- `0x1800a2108`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d078`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d078`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d103`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005d020`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005d020`

## string_xrefs

- `0x18005d160`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleDispatch(
        __int64 a1,
        int a2,
        __int64 a3,
        char a4,
        unsigned int a5)
{
  const char16_t *v9; // rcx
  _QWORD *Value; // rdi
  struct Microsoft::CoreUI::Dispatch::DeferredUserDispatcher *v11; // rbx
  int v12; // eax
  unsigned __int64 v13; // rsi
  _QWORD *v14; // rax
  int v15; // edi
  __int64 v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 result; // rax
  DWORD CurrentThreadId; // eax
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  size_t Count; // [rsp+78h] [rbp+20h] BYREF

  if ( a4 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 48LL);
    if ( CurrentThreadId != *(_DWORD *)(v22 + 176) )
      CFlat::Abandonment::Fail((const char16_t *)v22);
  }
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  if ( !Value )
    CFlat::Abandonment::Fail(v9);
  _InterlockedIncrement((volatile signed __int32 *)(a3 + 32));
  v11 = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread();
  if ( !*((_DWORD *)v11 + 52) )
  {
    LODWORD(Count) = 0;
    v12 = ULongLongToUInt(0x20u, (unsigned int *)&Count);
    if ( v12 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
        (const char *)(unsigned int)v12,
        v23);
    v13 = (unsigned int)Count;
    v14 = calloc((unsigned int)Count, 1u);
    if ( !v14 )
      CFlat::Abandonment::OutOfMemory(v13);
    v14[3] = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback;
    v14[2] = 0;
    *v14 = Value[10];
    *((_BYTE *)v14 + 8) = 2;
    Value[10] = v14;
  }
  v15 = 4;
  if ( (unsigned int)(*((_DWORD *)v11 + 52) + 1) > 4 )
    v15 = *((_DWORD *)v11 + 52) + 1;
  v16 = *((int *)v11 + 2);
  if ( v15 != (_DWORD)v16 )
  {
    Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(v11, (unsigned int)v15);
    if ( v15 > (int)v16 )
      memset_0((void *)(*(_QWORD *)v11 + 24 * v16), 0, 24LL * (v15 - (int)v16));
  }
  v17 = *((int *)v11 + 52);
  *((_DWORD *)v11 + 52) = v17 + 1;
  v18 = 3 * v17;
  v19 = *(_QWORD *)v11;
  *(_DWORD *)(v19 + 8 * v18) = a2;
  *(_QWORD *)(v19 + 8 * v18 + 8) = a3;
  *(_BYTE *)(v19 + 8 * v18 + 16) = a4;
  result = a5;
  *(_DWORD *)(v19 + 8 * v18 + 20) = a5;
  return result;
}

```

## disassembly

```asm
0x18005cff8  push    rbx
0x18005cffa  push    rbp
0x18005cffb  push    rsi
0x18005cffc  push    rdi
0x18005cffd  push    r14
0x18005cfff  push    r15
0x18005d001  sub     rsp, 28h
0x18005d005  mov     r14b, r9b
0x18005d008  mov     rbp, r8
0x18005d00b  mov     r15d, edx
0x18005d00e  mov     rbx, rcx
0x18005d011  test    r9b, r9b
0x18005d014  jnz     loc_18005D103
0x18005d01a  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005d020  call    cs:__imp_TlsGetValue
0x18005d026  mov     rdi, rax
0x18005d029  test    rax, rax
0x18005d02c  jnz     short loc_18005D034
0x18005d02e  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d034  lock inc dword ptr [rbp+20h]
0x18005d038  call    ?GetForCurrentThread@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAPEAV1234@XZ; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread(void)
0x18005d03d  mov     rbx, rax
0x18005d040  cmp     dword ptr [rax+0D0h], 0
0x18005d047  jnz     short loc_18005D0AC
0x18005d049  mov     dword ptr [rsp+58h+Count], 0
0x18005d051  lea     rdx, [rsp+58h+Count]; unsigned int *
0x18005d056  mov     ecx, 20h ; ' '; unsigned __int64
0x18005d05b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005d060  mov     rcx, [rsp+58h]; this
0x18005d065  test    eax, eax
0x18005d067  js      loc_18005D15D
0x18005d06d  mov     esi, dword ptr [rsp+58h+Count]
0x18005d071  mov     edx, 1; Size
0x18005d076  mov     ecx, esi; Count
0x18005d078  call    cs:__imp_calloc
0x18005d07e  mov     rdx, rax
0x18005d081  test    rax, rax
0x18005d084  jz      loc_18005D172
0x18005d08a  lea     rax, ?DeferredScheduleDispatchCallback@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *)
0x18005d091  mov     [rdx+18h], rax
0x18005d095  mov     qword ptr [rdx+10h], 0
0x18005d09d  mov     rax, [rdi+50h]
0x18005d0a1  mov     [rdx], rax
0x18005d0a4  mov     byte ptr [rdx+8], 2
0x18005d0a8  mov     [rdi+50h], rdx
0x18005d0ac  mov     eax, [rbx+0D0h]
0x18005d0b2  inc     eax
0x18005d0b4  mov     edi, 4
0x18005d0b9  cmp     eax, edi
0x18005d0bb  cmova   edi, eax
0x18005d0be  movsxd  rsi, dword ptr [rbx+8]
0x18005d0c2  cmp     edi, esi
0x18005d0c4  jnz     short loc_18005D127
0x18005d0c6  movsxd  rcx, dword ptr [rbx+0D0h]
0x18005d0cd  lea     eax, [rcx+1]
0x18005d0d0  mov     [rbx+0D0h], eax
0x18005d0d6  lea     rdx, [rcx+rcx*2]
0x18005d0da  mov     rcx, [rbx]
0x18005d0dd  mov     [rcx+rdx*8], r15d
0x18005d0e1  mov     [rcx+rdx*8+8], rbp
0x18005d0e6  mov     [rcx+rdx*8+10h], r14b
0x18005d0eb  mov     eax, [rsp+58h+arg_20]
0x18005d0f2  mov     [rcx+rdx*8+14h], eax
0x18005d0f6  add     rsp, 28h
0x18005d0fa  pop     r15
0x18005d0fc  pop     r14
0x18005d0fe  pop     rdi
0x18005d0ff  pop     rsi
0x18005d100  pop     rbp
0x18005d101  pop     rbx
0x18005d102  retn
0x18005d103  call    cs:__imp_GetCurrentThreadId
0x18005d109  mov     rcx, [rbx+20h]
0x18005d10d  mov     r10, [rcx+20h]
0x18005d111  mov     rcx, [r10+30h]; char16_t *
0x18005d115  cmp     eax, [rcx+0B0h]
0x18005d11b  jz      loc_18005D01A
0x18005d121  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d127  mov     rcx, rbx
0x18005d12a  test    edi, edi
0x18005d12c  jz      short loc_18005D17B
0x18005d12e  mov     edx, edi
0x18005d130  call    ?Resize@?$GlobalVectorF@UDeferredUserCall@Dispatch@CoreUI@Microsoft@@@Engine@Cn@@IEAAXH@Z; Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(int)
0x18005d135  cmp     edi, esi
0x18005d137  jle     short loc_18005D0C6
0x18005d139  sub     edi, esi
0x18005d13b  movsxd  rax, edi
0x18005d13e  lea     r8, [rax+rax*2]
0x18005d142  shl     r8, 3; Size
0x18005d146  lea     rcx, [rsi+rsi*2]
0x18005d14a  mov     rax, [rbx]
0x18005d14d  lea     rcx, [rax+rcx*8]; void *
0x18005d151  xor     edx, edx; Val
0x18005d153  call    memset_0
0x18005d158  jmp     loc_18005D0C6
0x18005d15d  mov     r9d, eax; char *
0x18005d160  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005d167  mov     edx, 10Fh; void *
0x18005d16c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d172  mov     rcx, rsi; unsigned __int64
0x18005d175  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
0x18005d17b  call    ?RemoveAll@?$GlobalVectorF@PEAUPortInfo@@@Engine@Cn@@QEAAXXZ; Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(void)
0x18005d180  jmp     loc_18005D0C6
```
