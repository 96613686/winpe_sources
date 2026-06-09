# CSpellerGlobalState::BackgroundCreateNewSpeller(ulong,ISpellChecker * *)

- ea: `0x18026f380`
- end: `0x18026f436`
- name: `?BackgroundCreateNewSpeller@CSpellerGlobalState@@AEAAJKPEAPEAUISpellChecker@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int, struct ISpellChecker **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18026f840`

## callees

- `0x18026f380`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18026f3ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18026f3ca`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18026f3db`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18026f3db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18026f3e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18026f3e6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18026f3ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18026f3ef`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18026f423`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18026f423`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026f3ac`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026f3ac`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18026f40f`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18026f40f`

## pseudocode

```c
HRESULT __fastcall CSpellerGlobalState::BackgroundCreateNewSpeller(char *pv, int a2, LPVOID *a3)
{
  HRESULT result; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rdi
  IStream *v8; // rcx

  *((_DWORD *)pv + 84) = a2;
  *a3 = 0;
  result = CoMarshalInterThreadInterfaceInStream(
             &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
             *((LPUNKNOWN *)pv + 6),
             (LPSTREAM *)pv + 14);
  *((_DWORD *)pv + 17) = result;
  if ( result >= 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       CSpellerGlobalState::CreateSpellerThreadProc,
                       pv,
                       (PTP_CALLBACK_ENVIRON)(pv + 152));
    v7 = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      result = CoReleaseMarshalData(*((LPSTREAM *)pv + 14));
      goto LABEL_7;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    WaitForThreadpoolWorkCallbacks(v7, 0);
    CloseThreadpoolWork(v7);
    result = *((_DWORD *)pv + 17);
    if ( result >= 0 )
    {
      v8 = (IStream *)*((_QWORD *)pv + 15);
      if ( v8 )
      {
        result = CoGetInterfaceAndReleaseStream(v8, &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b, a3);
        *((_QWORD *)pv + 15) = 0;
LABEL_7:
        *((_DWORD *)pv + 17) = result;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18026f380  push    rbx
0x18026f382  push    rsi
0x18026f383  push    rdi
0x18026f384  push    r14
0x18026f386  sub     rsp, 28h
0x18026f38a  mov     [rcx+150h], edx
0x18026f390  mov     r14, r8
0x18026f393  mov     qword ptr [r8], 0
0x18026f39a  mov     rbx, rcx
0x18026f39d  mov     rdx, [rcx+30h]; pUnk
0x18026f3a1  lea     r8, [rcx+70h]; ppStm
0x18026f3a5  lea     rcx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; riid
0x18026f3ac  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18026f3b2  mov     [rbx+44h], eax
0x18026f3b5  test    eax, eax
0x18026f3b7  js      short loc_18026F42C
0x18026f3b9  lea     r8, [rbx+98h]; pcbe
0x18026f3c0  mov     rdx, rbx; pv
0x18026f3c3  lea     rcx, ?CreateSpellerThreadProc@CSpellerGlobalState@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18026f3ca  call    cs:__imp_CreateThreadpoolWork
0x18026f3d0  mov     rdi, rax
0x18026f3d3  test    rax, rax
0x18026f3d6  jz      short loc_18026F41F
0x18026f3d8  mov     rcx, rax; pwk
0x18026f3db  call    cs:__imp_SubmitThreadpoolWork
0x18026f3e1  xor     edx, edx; fCancelPendingCallbacks
0x18026f3e3  mov     rcx, rdi; pwk
0x18026f3e6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18026f3ec  mov     rcx, rdi; pwk
0x18026f3ef  call    cs:__imp_CloseThreadpoolWork
0x18026f3f5  mov     eax, [rbx+44h]
0x18026f3f8  test    eax, eax
0x18026f3fa  js      short loc_18026F42C
0x18026f3fc  mov     rcx, [rbx+78h]; pStm
0x18026f400  test    rcx, rcx
0x18026f403  jz      short loc_18026F42C
0x18026f405  mov     r8, r14; ppv
0x18026f408  lea     rdx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; iid
0x18026f40f  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18026f415  mov     qword ptr [rbx+78h], 0
0x18026f41d  jmp     short loc_18026F429
0x18026f41f  mov     rcx, [rbx+70h]; pStm
0x18026f423  call    cs:__imp_CoReleaseMarshalData
0x18026f429  mov     [rbx+44h], eax
0x18026f42c  add     rsp, 28h
0x18026f430  pop     r14
0x18026f432  pop     rdi
0x18026f433  pop     rsi
0x18026f434  pop     rbx
0x18026f435  retn
```
