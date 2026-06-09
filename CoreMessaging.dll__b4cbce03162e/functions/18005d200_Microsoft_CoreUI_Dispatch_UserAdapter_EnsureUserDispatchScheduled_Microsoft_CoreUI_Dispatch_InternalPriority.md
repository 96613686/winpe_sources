# Microsoft::CoreUI::Dispatch::UserAdapter::EnsureUserDispatchScheduled(Microsoft::CoreUI::Dispatch::InternalPriority)

- ea: `0x18005d200`
- end: `0x18005d3c2`
- name: `?EnsureUserDispatchScheduled@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z`
- size: `450`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008354`
- `0x18005bde8`
- `0x18005cf2c`
- `0x18005d190`
- `0x18005da8c`

## callees

- `0x18000b018`
- `0x18000b0bc`
- `0x180039dbc`
- `0x18005d200`
- `0x18005d3d0`
- `0x18005d75c`
- `0x18008ae1c`
- `0x18009e054`
- `0x1800a2108`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d28c`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d28c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d314`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d314`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005d233`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005d233`

## string_xrefs

- `0x18005d39d`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::EnsureUserDispatchScheduled(__int64 a1, int a2)
{
  bool v4; // si
  __int64 v5; // r14
  const char16_t *v6; // rcx
  _QWORD *Value; // rdi
  struct Microsoft::CoreUI::Dispatch::DeferredUserDispatcher *v8; // rbx
  int v9; // eax
  unsigned __int64 v10; // rbp
  _QWORD *v11; // rax
  int v12; // edi
  __int64 v13; // rbp
  __int64 v14; // rcx
  __int64 result; // rax
  DWORD CurrentThreadId; // eax
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  size_t Count; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(a1 + 48) == 3
    && Microsoft::CoreUI::Dispatch::ThreadContext::get_IsCurrentThreadDispatchThread(*(Microsoft::CoreUI::Dispatch::ThreadContext **)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 48LL));
  v5 = *(_QWORD *)(a1 + 40);
  if ( v4 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v17 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 48LL);
    if ( CurrentThreadId != *(_DWORD *)(v17 + 176) )
      CFlat::Abandonment::Fail((const char16_t *)v17);
  }
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  if ( !Value )
    CFlat::Abandonment::Fail(v6);
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 32));
  v8 = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread();
  if ( !*((_DWORD *)v8 + 52) )
  {
    LODWORD(Count) = 0;
    v9 = ULongLongToUInt(0x20u, (unsigned int *)&Count);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
        (const char *)(unsigned int)v9,
        v18);
    v10 = (unsigned int)Count;
    v11 = calloc((unsigned int)Count, 1u);
    if ( !v11 )
      CFlat::Abandonment::OutOfMemory(v10);
    v11[3] = Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback;
    v11[2] = 0;
    *v11 = Value[10];
    *((_BYTE *)v11 + 8) = 2;
    Value[10] = v11;
  }
  v12 = 4;
  if ( (unsigned int)(*((_DWORD *)v8 + 52) + 1) > 4 )
    v12 = *((_DWORD *)v8 + 52) + 1;
  v13 = *((int *)v8 + 2);
  if ( v12 != (_DWORD)v13 )
  {
    Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(v8, (unsigned int)v12);
    if ( v12 > (int)v13 )
      memset_0((void *)(*(_QWORD *)v8 + 24 * v13), 0, 24LL * (v12 - (int)v13));
  }
  v14 = *((int *)v8 + 52);
  *((_DWORD *)v8 + 52) = v14 + 1;
  v14 *= 3;
  result = *(_QWORD *)v8;
  *(_DWORD *)(result + 8 * v14) = a2;
  *(_QWORD *)(result + 8 * v14 + 8) = v5;
  *(_BYTE *)(result + 8 * v14 + 16) = v4;
  *(_DWORD *)(result + 8 * v14 + 20) = 0;
  return result;
}

```

## disassembly

```asm
0x18005d200  push    rbx
0x18005d202  push    rbp
0x18005d203  push    rsi
0x18005d204  push    rdi
0x18005d205  push    r14
0x18005d207  push    r15
0x18005d209  sub     rsp, 28h
0x18005d20d  mov     r15d, edx
0x18005d210  mov     rdi, rcx
0x18005d213  cmp     dword ptr [rcx+30h], 3
0x18005d217  jz      loc_18005D338
0x18005d21d  xor     sil, sil
0x18005d220  mov     r14, [rdi+28h]
0x18005d224  test    sil, sil
0x18005d227  jnz     loc_18005D314
0x18005d22d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18005d233  call    cs:__imp_TlsGetValue
0x18005d239  mov     rdi, rax
0x18005d23c  test    rax, rax
0x18005d23f  jnz     short loc_18005D247
0x18005d241  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d247  lock inc dword ptr [r14+20h]
0x18005d24c  call    ?GetForCurrentThread@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAPEAV1234@XZ; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::GetForCurrentThread(void)
0x18005d251  mov     rbx, rax
0x18005d254  cmp     dword ptr [rax+0D0h], 0
0x18005d25b  jnz     short loc_18005D2C0
0x18005d25d  mov     dword ptr [rsp+58h+Count], 0
0x18005d265  lea     rdx, [rsp+58h+Count]; unsigned int *
0x18005d26a  mov     ecx, 20h ; ' '; unsigned __int64
0x18005d26f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005d274  mov     rcx, [rsp+58h]; this
0x18005d279  test    eax, eax
0x18005d27b  js      loc_18005D39A
0x18005d281  mov     ebp, dword ptr [rsp+58h+Count]
0x18005d285  mov     edx, 1; Size
0x18005d28a  mov     ecx, ebp; Count
0x18005d28c  call    cs:__imp_calloc
0x18005d292  mov     rdx, rax
0x18005d295  test    rax, rax
0x18005d298  jz      loc_18005D3AF
0x18005d29e  lea     rax, ?DeferredScheduleDispatchCallback@DeferredUserDispatcher@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z; Microsoft::CoreUI::Dispatch::DeferredUserDispatcher::DeferredScheduleDispatchCallback(void *)
0x18005d2a5  mov     [rdx+18h], rax
0x18005d2a9  mov     qword ptr [rdx+10h], 0
0x18005d2b1  mov     rax, [rdi+50h]
0x18005d2b5  mov     [rdx], rax
0x18005d2b8  mov     byte ptr [rdx+8], 2
0x18005d2bc  mov     [rdi+50h], rdx
0x18005d2c0  mov     eax, [rbx+0D0h]
0x18005d2c6  inc     eax
0x18005d2c8  mov     edi, 4
0x18005d2cd  cmp     eax, edi
0x18005d2cf  cmova   edi, eax
0x18005d2d2  movsxd  rbp, dword ptr [rbx+8]
0x18005d2d6  cmp     edi, ebp
0x18005d2d8  jnz     short loc_18005D359
0x18005d2da  movsxd  rcx, dword ptr [rbx+0D0h]
0x18005d2e1  lea     eax, [rcx+1]
0x18005d2e4  mov     [rbx+0D0h], eax
0x18005d2ea  lea     rcx, [rcx+rcx*2]
0x18005d2ee  mov     rax, [rbx]
0x18005d2f1  mov     [rax+rcx*8], r15d
0x18005d2f5  mov     [rax+rcx*8+8], r14
0x18005d2fa  mov     [rax+rcx*8+10h], sil
0x18005d2ff  mov     dword ptr [rax+rcx*8+14h], 0
0x18005d307  add     rsp, 28h
0x18005d30b  pop     r15
0x18005d30d  pop     r14
0x18005d30f  pop     rdi
0x18005d310  pop     rsi
0x18005d311  pop     rbp
0x18005d312  pop     rbx
0x18005d313  retn
0x18005d314  call    cs:__imp_GetCurrentThreadId
0x18005d31a  mov     rcx, [rdi+20h]
0x18005d31e  mov     rdx, [rcx+20h]
0x18005d322  mov     rcx, [rdx+30h]; char16_t *
0x18005d326  cmp     eax, [rcx+0B0h]
0x18005d32c  jz      loc_18005D22D
0x18005d332  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18005d338  mov     rax, [rcx+20h]
0x18005d33c  mov     rcx, [rax+20h]
0x18005d340  mov     rcx, [rcx+30h]; this
0x18005d344  call    ?get_IsCurrentThreadDispatchThread@ThreadContext@Dispatch@CoreUI@Microsoft@@QEAA_NXZ; Microsoft::CoreUI::Dispatch::ThreadContext::get_IsCurrentThreadDispatchThread(void)
0x18005d349  test    al, al
0x18005d34b  jz      loc_18005D21D
0x18005d351  mov     sil, 1
0x18005d354  jmp     loc_18005D220
0x18005d359  mov     rcx, rbx
0x18005d35c  test    edi, edi
0x18005d35e  jz      short loc_18005D3B8
0x18005d360  mov     edx, edi
0x18005d362  call    ?Resize@?$GlobalVectorF@UDeferredUserCall@Dispatch@CoreUI@Microsoft@@@Engine@Cn@@IEAAXH@Z; Cn::Engine::GlobalVectorF<Microsoft::CoreUI::Dispatch::DeferredUserCall>::Resize(int)
0x18005d367  cmp     edi, ebp
0x18005d369  jle     loc_18005D2DA
0x18005d36f  sub     edi, ebp
0x18005d371  movsxd  rax, edi
0x18005d374  lea     r8, [rax+rax*2]
0x18005d378  shl     r8, 3; Size
0x18005d37c  lea     rcx, ds:0[rbp*2]
0x18005d384  add     rcx, rbp
0x18005d387  mov     rax, [rbx]
0x18005d38a  lea     rcx, [rax+rcx*8]; void *
0x18005d38e  xor     edx, edx; Val
0x18005d390  call    memset_0
0x18005d395  jmp     loc_18005D2DA
0x18005d39a  mov     r9d, eax; char *
0x18005d39d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005d3a4  mov     edx, 10Fh; void *
0x18005d3a9  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005d3af  mov     rcx, rbp; unsigned __int64
0x18005d3b2  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
0x18005d3b8  call    ?RemoveAll@?$GlobalVectorF@PEAUPortInfo@@@Engine@Cn@@QEAAXXZ; Cn::Engine::GlobalVectorF<PortInfo *>::RemoveAll(void)
0x18005d3bd  jmp     loc_18005D2DA
```
