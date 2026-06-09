# Microsoft::CoreUI::Dispatch::UserAdapter::DispatchNextUserQueueItemNative(bool)

- ea: `0x180015700`
- end: `0x18001583a`
- name: `?DispatchNextUserQueueItemNative@UserAdapter@Dispatch@CoreUI@Microsoft@@CA?AW4UserAdapter$DispatchedMessageCategory@234@_N@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800155ac`

## callees

- `0x180007d80`
- `0x180009750`
- `0x180015700`
- `0x1800a236c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800157b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800157b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800157eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800157eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015726`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800157ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015726`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800157ce`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!TranslateMessage` at `0x180015795`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!TranslateMessage` at `0x180015795`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x1800157a0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x1800157a0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x18001576f`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x18001576f`

## pseudocode

```c
__int64 Microsoft::CoreUI::Dispatch::UserAdapter::DispatchNextUserQueueItemNative()
{
  bool v0; // bl
  _QWORD *Value; // rsi
  unsigned int v2; // edi
  BOOL v3; // r15d
  __int64 v4; // r14
  int v5; // ecx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  tagMSG Msg; // [rsp+38h] [rbp-50h] BYREF

  v0 = 0;
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  Value[2] = 0;
  CFlat::EntryExit::OnBeginCallToNative(Value);
  memset(&Msg, 0, sizeof(Msg));
  v2 = 1;
  v3 = PeekMessageW(&Msg, 0, 0, 0, 1u);
  if ( v3 )
  {
    v0 = Msg.message == 18;
    if ( Msg.message != 18 )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
  }
  v4 = Value[11];
  if ( v4 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 16));
    v5 = *(_DWORD *)(v4 + 60);
    *(_DWORD *)(v4 + 60) = v5 + 1;
    if ( !v5 )
    {
      *(_QWORD *)(v4 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v4 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        v7,
        v6,
        v8,
        v9);
  }
  Value[2] = 0;
  if ( !v0 )
  {
    v2 = 0;
    if ( !v3 )
      return 2;
  }
  return v2;
}

```

## disassembly

```asm
0x180015700  mov     rax, rsp
0x180015703  mov     [rax+8], rbx
0x180015707  mov     [rax+18h], rsi
0x18001570b  push    rdi
0x18001570c  push    r14
0x18001570e  push    r15
0x180015710  sub     rsp, 70h
0x180015714  mov     dword ptr [rax-54h], 0
0x18001571b  xor     bl, bl
0x18001571d  mov     [rax-58h], bl
0x180015720  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180015726  call    cs:__imp_TlsGetValue
0x18001572c  mov     rsi, rax
0x18001572f  mov     [rsp+88h+arg_8], rax
0x180015737  mov     qword ptr [rax+10h], 0
0x18001573f  mov     rcx, rax; void *
0x180015742  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x180015747  xorps   xmm0, xmm0
0x18001574a  movups  xmmword ptr [rsp+88h+Msg.hwnd], xmm0
0x18001574f  movups  xmmword ptr [rsp+88h+Msg.wParam], xmm0
0x180015754  movups  xmmword ptr [rsp+88h+Msg.time], xmm0
0x180015759  mov     edi, 1
0x18001575e  mov     [rsp+88h+wRemoveMsg], edi; wRemoveMsg
0x180015762  xor     r9d, r9d; wMsgFilterMax
0x180015765  xor     r8d, r8d; wMsgFilterMin
0x180015768  xor     edx, edx; hWnd
0x18001576a  lea     rcx, [rsp+88h+Msg]; lpMsg
0x18001576f  call    cs:__imp_PeekMessageW
0x180015775  mov     r15d, eax
0x180015778  mov     [rsp+88h+var_54], eax
0x18001577c  test    eax, eax
0x18001577e  jz      short loc_1800157A6
0x180015780  cmp     [rsp+88h+Msg.message], 12h
0x180015785  setz    bl
0x180015788  mov     [rsp+88h+var_58], bl
0x18001578c  test    bl, bl
0x18001578e  jnz     short loc_1800157A6
0x180015790  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180015795  call    cs:__imp_TranslateMessage
0x18001579b  lea     rcx, [rsp+88h+Msg]; lpMsg
0x1800157a0  call    cs:__imp_DispatchMessageW
0x1800157a6  mov     r14, [rsi+58h]
0x1800157aa  test    r14, r14
0x1800157ad  jz      short loc_1800157FB
0x1800157af  lea     rcx, [r14+10h]; lpCriticalSection
0x1800157b3  call    cs:__imp_EnterCriticalSection
0x1800157b9  mov     ecx, [r14+3Ch]
0x1800157bd  lea     eax, [rcx+1]
0x1800157c0  mov     [r14+3Ch], eax
0x1800157c4  test    ecx, ecx
0x1800157c6  jnz     short loc_1800157E2
0x1800157c8  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800157ce  call    cs:__imp_TlsGetValue
0x1800157d4  mov     [r14+40h], rax
0x1800157d8  call    cs:__imp_GetCurrentThreadId
0x1800157de  mov     [r14+48h], eax
0x1800157e2  mov     rdx, rsi; lpTlsValue
0x1800157e5  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800157eb  call    cs:__imp_TlsSetValue
0x1800157f1  test    eax, eax
0x1800157f3  jnz     short loc_1800157FB
0x1800157f5  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x1800157fb  mov     qword ptr [rsi+10h], 0
0x180015803  jmp     short loc_180015813
0x180015805  mov     edi, 1
0x18001580a  mov     r15d, [rsp+88h+var_54]
0x18001580f  mov     bl, [rsp+88h+var_58]
0x180015813  test    bl, bl
0x180015815  jnz     short loc_180015822
0x180015817  xor     edi, edi
0x180015819  lea     eax, [rdi+2]
0x18001581c  test    r15d, r15d
0x18001581f  cmovz   edi, eax
0x180015822  mov     eax, edi
0x180015824  lea     r11, [rsp+88h+var_18]
0x180015829  mov     rbx, [r11+20h]
0x18001582d  mov     rsi, [r11+30h]
0x180015831  mov     rsp, r11
0x180015834  pop     r15
0x180015836  pop     r14
0x180015838  pop     rdi
0x180015839  retn
0x1800c9a9c  push    rbp
0x1800c9a9e  sub     rsp, 30h
0x1800c9aa2  mov     rbp, rdx
0x1800c9aa5  mov     rdx, [rbp+98h]; this
0x1800c9aac  call    ?UnexpectedStructuredExceptionFilter@ExceptionHandling@CFlat@@SAHPEAU_EXCEPTION_POINTERS@@PEAX@Z; CFlat::ExceptionHandling::UnexpectedStructuredExceptionFilter(_EXCEPTION_POINTERS *,void *)
0x1800c9ab1  nop
0x1800c9ab2  add     rsp, 30h
0x1800c9ab6  pop     rbp
0x1800c9ab7  retn
```
