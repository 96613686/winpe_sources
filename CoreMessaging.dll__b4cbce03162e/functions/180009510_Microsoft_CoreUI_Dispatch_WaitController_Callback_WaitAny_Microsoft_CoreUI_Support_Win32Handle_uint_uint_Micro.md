# Microsoft::CoreUI::Dispatch::WaitController::Callback_WaitAny(Microsoft::CoreUI::Support::Win32Handle *,uint,uint,Microsoft::CoreUI::WaitFlags,bool,CFlat::Ref<uint>)

- ea: `0x180009510`
- end: `0x180009741`
- name: `?Callback_WaitAny@WaitController@Dispatch@CoreUI@Microsoft@@QEAA?AW4WaitStatus@234@PEAUWin32Handle@Support@34@IIW4WaitFlags@34@_NU?$Ref@I@CFlat@@@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800091b0`

## callees

- `0x180009510`
- `0x180009750`
- `0x18008ae1c`
- `0x18009d670`
- `0x18009e054`
- `0x1800a236c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800095c1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800095c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800095de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009601`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009601`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009613`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009613`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009547`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000958f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800095f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009547`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000958f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800095f7`
- `combase!__imp_CoBeginProcessEvents` at `0x180009644`
- `combase!__imp_CoBeginProcessEvents` at `0x180009644`
- `combase!__imp_CoMsgWaitInProcessEvents` at `0x180009667`
- `combase!__imp_CoMsgWaitInProcessEvents` at `0x180009667`
- `combase!__imp_CoEndProcessEvents` at `0x180009678`
- `combase!__imp_CoEndProcessEvents` at `0x180009678`

## pseudocode

```c
__int64 __fastcall Microsoft::CoreUI::Dispatch::WaitController::Callback_WaitAny(
        __int64 a1,
        const HANDLE *a2,
        unsigned int a3,
        DWORD a4,
        char a5,
        char a6,
        DWORD *a7)
{
  __int64 v8; // r15
  __int64 v11; // r8
  BOOL bAlertable; // edi
  void *v13; // rcx
  DWORD v14; // r15d
  char v15; // r12
  _QWORD *Value; // rbx
  unsigned int v17; // r14d
  DWORD v18; // edi
  __int64 v19; // rsi
  int v20; // ecx
  const char16_t *v21; // rcx
  __int64 v23; // [rsp+30h] [rbp-B8h]
  _BYTE v24[96]; // [rsp+40h] [rbp-A8h] BYREF

  v8 = a3;
  v11 = *(_QWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 56LL);
  bAlertable = a5 & 1;
  v13 = *(void **)(a1 + 88);
  a2[v8] = v13;
  if ( !v13 )
    CFlat::Abandonment::Fail(0);
  LODWORD(v23) = -1;
  v14 = v8 + 1;
  HIDWORD(v23) = v14;
  v15 = *(_BYTE *)(*(_QWORD *)(v11 + 48) + 40LL);
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  v17 = 0;
  Value[2] = 0;
  CFlat::EntryExit::OnBeginCallToNative(Value);
  if ( !v15 || a6 )
  {
    v18 = WaitForMultipleObjectsEx(v14, a2, 0, a4, bAlertable);
  }
  else
  {
    memset_0(v24, 0, sizeof(v24));
    CoBeginProcessEvents(v24);
    v18 = CoMsgWaitInProcessEvents(v24, v14, a2, a4, 7423, 2 * bAlertable, v23, Value);
    CoEndProcessEvents(v24);
  }
  v19 = Value[11];
  if ( v19 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
    v20 = *(_DWORD *)(v19 + 60);
    *(_DWORD *)(v19 + 60) = v20 + 1;
    if ( !v20 )
    {
      *(_QWORD *)(v19 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
      *(_DWORD *)(v19 + 72) = GetCurrentThreadId();
    }
    if ( !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
      CFlat::Abandonment::Fail(v21);
  }
  Value[2] = 0;
  if ( v18 >= v14 )
  {
    if ( v18 >= 0x80 && v18 < v14 + 128 )
    {
      *a7 = v18 - 128;
      return 128;
    }
    else
    {
      *a7 = 64;
      if ( v18 == v14 )
      {
        return 43962;
      }
      else if ( v18 == 192 )
      {
        return 192;
      }
      else if ( v18 == 258 )
      {
        return 258;
      }
      else
      {
        return (unsigned int)-1;
      }
    }
  }
  else
  {
    *a7 = v18;
  }
  return v17;
}

```

## disassembly

```asm
0x180009510  push    rbx
0x180009512  push    rsi
0x180009513  push    rdi
0x180009514  push    r12
0x180009516  push    r13
0x180009518  push    r14
0x18000951a  push    r15
0x18000951c  sub     rsp, 0B0h
0x180009523  mov     rax, cs:__security_cookie
0x18000952a  xor     rax, rsp
0x18000952d  mov     [rsp+0E8h+var_48], rax
0x180009535  mov     r13d, r9d
0x180009538  mov     r15d, r8d
0x18000953b  mov     rsi, rdx
0x18000953e  mov     rbx, rcx
0x180009541  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180009547  call    cs:__imp_TlsGetValue
0x18000954d  mov     rdx, [rax+30h]
0x180009551  mov     r8, [rdx+38h]
0x180009555  mov     edi, dword ptr [rsp+0E8h+arg_20]
0x18000955c  and     edi, 1
0x18000955f  mov     rcx, [rbx+58h]; char16_t *
0x180009563  mov     [rsi+r15*8], rcx
0x180009567  test    rcx, rcx
0x18000956a  jz      loc_180009705
0x180009570  mov     [rsp+0E8h+var_B8], 0FFFFFFFFh
0x180009578  inc     r15d
0x18000957b  mov     [rsp+0E8h+var_B4], r15d
0x180009580  mov     rax, [r8+30h]
0x180009584  movzx   r12d, byte ptr [rax+28h]
0x180009589  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000958f  call    cs:__imp_TlsGetValue
0x180009595  mov     rbx, rax
0x180009598  mov     [rsp+0E8h+var_B0], rax
0x18000959d  xor     r14d, r14d
0x1800095a0  mov     [rax+10h], r14
0x1800095a4  mov     rcx, rax; void *
0x1800095a7  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x1800095ac  test    r12b, r12b
0x1800095af  jnz     short loc_180009623
0x1800095b1  mov     [rsp+0E8h+bAlertable], edi; bAlertable
0x1800095b5  mov     r9d, r13d; dwMilliseconds
0x1800095b8  xor     r8d, r8d; bWaitAll
0x1800095bb  mov     rdx, rsi; lpHandles
0x1800095be  mov     ecx, r15d; nCount
0x1800095c1  call    cs:__imp_WaitForMultipleObjectsEx
0x1800095c7  mov     edi, eax
0x1800095c9  mov     [rsp+0E8h+var_B8], eax
0x1800095cd  mov     rsi, [rbx+58h]
0x1800095d1  test    rsi, rsi
0x1800095d4  jz      loc_180009683
0x1800095da  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800095de  call    cs:__imp_EnterCriticalSection
0x1800095e4  mov     ecx, [rsi+3Ch]
0x1800095e7  lea     eax, [rcx+1]
0x1800095ea  mov     [rsi+3Ch], eax
0x1800095ed  test    ecx, ecx
0x1800095ef  jnz     short loc_18000960A
0x1800095f1  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800095f7  call    cs:__imp_TlsGetValue
0x1800095fd  mov     [rsi+40h], rax
0x180009601  call    cs:__imp_GetCurrentThreadId
0x180009607  mov     [rsi+48h], eax
0x18000960a  mov     rdx, rbx; lpTlsValue
0x18000960d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180009613  call    cs:__imp_TlsSetValue
0x180009619  test    eax, eax
0x18000961b  jnz     short loc_180009683
0x18000961d  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180009623  cmp     [rsp+0E8h+arg_28], 0
0x18000962b  jnz     short loc_1800095B1
0x18000962d  xor     edx, edx; Val
0x18000962f  mov     r8d, 60h ; '`'; Size
0x180009635  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18000963a  call    memset_0
0x18000963f  lea     rcx, [rsp+0E8h+var_A8]
0x180009644  call    cs:__imp_CoBeginProcessEvents
0x18000964a  lea     eax, [rdi+rdi]
0x18000964d  mov     [rsp+0E8h+var_C0], eax
0x180009651  mov     [rsp+0E8h+bAlertable], 1CFFh
0x180009659  mov     r9d, r13d
0x18000965c  mov     r8, rsi
0x18000965f  mov     edx, r15d
0x180009662  lea     rcx, [rsp+0E8h+var_A8]
0x180009667  call    cs:__imp_CoMsgWaitInProcessEvents
0x18000966d  mov     edi, eax
0x18000966f  mov     [rsp+0E8h+var_B8], eax
0x180009673  lea     rcx, [rsp+0E8h+var_A8]
0x180009678  call    cs:__imp_CoEndProcessEvents
0x18000967e  jmp     loc_1800095CD
0x180009683  mov     [rbx+10h], r14
0x180009687  jmp     short loc_180009695
0x180009689  xor     r14d, r14d
0x18000968c  mov     edi, [rsp+0E8h+var_B8]
0x180009690  mov     r15d, [rsp+0E8h+var_B4]
0x180009695  cmp     edi, r15d
0x180009698  jnb     short loc_1800096CA
0x18000969a  mov     rax, [rsp+0E8h+arg_30]
0x1800096a2  mov     [rax], edi
0x1800096a4  mov     eax, r14d
0x1800096a7  mov     rcx, [rsp+0E8h+var_48]
0x1800096af  xor     rcx, rsp; StackCookie
0x1800096b2  call    __security_check_cookie
0x1800096b7  add     rsp, 0B0h
0x1800096be  pop     r15
0x1800096c0  pop     r14
0x1800096c2  pop     r13
0x1800096c4  pop     r12
0x1800096c6  pop     rdi
0x1800096c7  pop     rsi
0x1800096c8  pop     rbx
0x1800096c9  retn
0x1800096ca  cmp     edi, 80h
0x1800096d0  jb      short loc_1800096DD
0x1800096d2  lea     eax, [r15+80h]
0x1800096d9  cmp     edi, eax
0x1800096db  jb      short loc_180009713
0x1800096dd  mov     rax, [rsp+0E8h+arg_30]
0x1800096e5  mov     dword ptr [rax], 40h ; '@'
0x1800096eb  cmp     edi, r15d
0x1800096ee  jz      short loc_18000970B
0x1800096f0  cmp     edi, 0C0h
0x1800096f6  jz      short loc_18000972B
0x1800096f8  cmp     edi, 102h
0x1800096fe  jnz     short loc_180009736
0x180009700  mov     r14d, edi
0x180009703  jmp     short loc_1800096A4
0x180009705  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000970b  mov     r14d, 0ABBAh
0x180009711  jmp     short loc_1800096A4
0x180009713  lea     ecx, [rdi-80h]; struct _EXCEPTION_POINTERS *
0x180009716  mov     rax, [rsp+0E8h+arg_30]
0x18000971e  mov     [rax], ecx
0x180009720  mov     r14d, 80h
0x180009726  jmp     loc_1800096A4
0x18000972b  mov     r14d, 0C0h
0x180009731  jmp     loc_1800096A4
0x180009736  mov     r14d, 0FFFFFFFFh
0x18000973c  jmp     loc_1800096A4
0x1800c9330  push    rbp
0x1800c9332  sub     rsp, 30h
0x1800c9336  mov     rbp, rdx
0x1800c9339  mov     rdx, [rbp+38h]; this
0x1800c933d  call    ?UnexpectedStructuredExceptionFilter@ExceptionHandling@CFlat@@SAHPEAU_EXCEPTION_POINTERS@@PEAX@Z; CFlat::ExceptionHandling::UnexpectedStructuredExceptionFilter(_EXCEPTION_POINTERS *,void *)
0x1800c9342  nop
0x1800c9343  add     rsp, 30h
0x1800c9347  pop     rbp
0x1800c9348  retn
```
