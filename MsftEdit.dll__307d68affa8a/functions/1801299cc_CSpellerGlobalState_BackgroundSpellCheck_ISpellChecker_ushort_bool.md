# CSpellerGlobalState::BackgroundSpellCheck(ISpellChecker *,ushort *,bool)

- ea: `0x1801299cc`
- end: `0x180129a88`
- name: `?BackgroundSpellCheck@CSpellerGlobalState@@AEAAJPEAUISpellChecker@@PEAG_N@Z`
- size: `188`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this, struct ISpellChecker *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d237c`

## callees

- `0x1800d29d8`
- `0x1801299cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180129a65`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180129a38`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180129a38`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180129a49`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180129a49`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180129a54`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180129a54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180129a5d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180129a5d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1801299f5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x1801299f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180129a16`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::BackgroundSpellCheck(
        CSpellerGlobalState *this,
        IUnknown *a2,
        unsigned __int16 *a3,
        char a4)
{
  HRESULT v5; // eax
  void *v6; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v8; // rdi
  signed int LastError; // eax

  *((_QWORD *)this + 39) = a3;
  *((_BYTE *)this + 305) = a4;
  v5 = CoMarshalInterThreadInterfaceInStream(&GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b, a2, (LPSTREAM *)this + 41);
  *((_DWORD *)this + 17) = v5;
  if ( v5 >= 0 )
  {
    CSpellerGlobalState::FreeSpellCheckErrors(this);
    v6 = (void *)*((_QWORD *)this + 40);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)this + 40) = 0;
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       CSpellerGlobalState::SpellCheckThreadProc,
                       this,
                       (PTP_CALLBACK_ENVIRON)((char *)this + 152));
    v8 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      WaitForThreadpoolWorkCallbacks(v8, 0);
      CloseThreadpoolWork(v8);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *((_DWORD *)this + 17) = LastError;
    }
  }
  return *((unsigned int *)this + 17);
}

```

## disassembly

```asm
0x1801299cc  mov     [rsp+arg_0], rbx
0x1801299d1  push    rdi
0x1801299d2  sub     rsp, 20h
0x1801299d6  mov     [rcx+138h], r8
0x1801299dd  mov     rbx, rcx
0x1801299e0  lea     r8, [rcx+148h]; ppStm
0x1801299e7  mov     [rcx+131h], r9b
0x1801299ee  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x1801299f5  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1801299fb  mov     [rbx+44h], eax
0x1801299fe  test    eax, eax
0x180129a00  js      short loc_180129A7A
0x180129a02  mov     rcx, rbx; this
0x180129a05  call    ?FreeSpellCheckErrors@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::FreeSpellCheckErrors(void)
0x180129a0a  mov     rcx, [rbx+140h]; pv
0x180129a11  test    rcx, rcx
0x180129a14  jz      short loc_180129A27
0x180129a16  call    cs:__imp_CoTaskMemFree
0x180129a1c  mov     qword ptr [rbx+140h], 0
0x180129a27  lea     r8, [rbx+98h]; pcbe
0x180129a2e  mov     rdx, rbx; pv
0x180129a31  lea     rcx, ?SpellCheckThreadProc@CSpellerGlobalState@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180129a38  call    cs:__imp_CreateThreadpoolWork
0x180129a3e  mov     rdi, rax
0x180129a41  test    rax, rax
0x180129a44  jz      short loc_180129A65
0x180129a46  mov     rcx, rax; pwk
0x180129a49  call    cs:__imp_SubmitThreadpoolWork
0x180129a4f  xor     edx, edx; fCancelPendingCallbacks
0x180129a51  mov     rcx, rdi; pwk
0x180129a54  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180129a5a  mov     rcx, rdi; pwk
0x180129a5d  call    cs:__imp_CloseThreadpoolWork
0x180129a63  jmp     short loc_180129A7A
0x180129a65  call    cs:__imp_GetLastError
0x180129a6b  test    eax, eax
0x180129a6d  jle     short loc_180129A77
0x180129a6f  movzx   eax, ax
0x180129a72  or      eax, 80070000h
0x180129a77  mov     [rbx+44h], eax
0x180129a7a  mov     eax, [rbx+44h]
0x180129a7d  mov     rbx, [rsp+28h+arg_0]
0x180129a82  add     rsp, 20h
0x180129a86  pop     rdi
0x180129a87  retn
```
