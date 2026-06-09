# CStartMenuPathCompleteQueryCache::WaitForLock(IUnknown *)

- ea: `0x180030cdc`
- end: `0x180030d9c`
- name: `?WaitForLock@CStartMenuPathCompleteQueryCache@@QEAAJPEAUIUnknown@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(CStartMenuPathCompleteQueryCache *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800370e0`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180030cdc`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180030d16`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180030d16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030d89`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180030d58`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180030d58`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStartMenuPathCompleteQueryCache::WaitForLock(HANDLE *this, struct IUnknown *a2)
{
  IUnknown *v3; // r10
  unsigned int v4; // ebx
  char *v5; // rcx
  HANDLE Handles[2]; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp+10h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+20h] BYREF

  hObject = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppvOut);
  if ( IUnknown_QueryService(v3, &IID_IObjectWithCancelEvent, &GUID_f279b885_0ae9_4b85_ac06_ddecf9408941, &ppvOut) >= 0 )
    (*(void (__fastcall **)(void *, HANDLE *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &hObject);
  Handles[0] = this[2];
  Handles[1] = hObject;
  v4 = WaitForMultipleObjects((hObject != 0) + 1, Handles, 0, 0xFFFFFFFF) != 0 ? 0x800704C7 : 0;
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppvOut);
  v5 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  return v4;
}

```

## disassembly

```asm
0x180030cdc  mov     [rsp-8+arg_8], rbx
0x180030ce1  push    rbp
0x180030ce2  mov     rbp, rsp
0x180030ce5  sub     rsp, 30h
0x180030ce9  mov     r10, rdx
0x180030cec  mov     rbx, rcx
0x180030cef  mov     [rbp+hObject], 0
0x180030cf7  lea     rcx, [rbp+ppvOut]; void *
0x180030cfb  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180030d00  nop
0x180030d01  lea     r9, [rbp+ppvOut]; ppvOut
0x180030d05  lea     r8, _GUID_f279b885_0ae9_4b85_ac06_ddecf9408941; riid
0x180030d0c  lea     rdx, IID_IObjectWithCancelEvent; guidService
0x180030d13  mov     rcx, r10; punk
0x180030d16  call    cs:__imp_IUnknown_QueryService
0x180030d1c  test    eax, eax
0x180030d1e  js      short loc_180030D34
0x180030d20  mov     rcx, [rbp+ppvOut]
0x180030d24  mov     rax, [rcx]
0x180030d27  lea     rdx, [rbp+hObject]
0x180030d2b  mov     rax, [rax+18h]
0x180030d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d34  mov     rax, [rbx+10h]
0x180030d38  mov     [rbp+Handles], rax
0x180030d3c  mov     rax, [rbp+hObject]
0x180030d40  mov     [rbp+var_8], rax
0x180030d44  neg     rax
0x180030d47  sbb     ecx, ecx
0x180030d49  neg     ecx
0x180030d4b  inc     ecx; nCount
0x180030d4d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180030d51  xor     r8d, r8d; bWaitAll
0x180030d54  lea     rdx, [rbp+Handles]; lpHandles
0x180030d58  call    cs:__imp_WaitForMultipleObjects
0x180030d5e  nop
0x180030d5f  neg     eax
0x180030d61  sbb     ebx, ebx
0x180030d63  and     ebx, 800704C7h
0x180030d69  lea     rcx, [rbp+ppvOut]
0x180030d6d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180030d72  nop
0x180030d73  mov     rcx, [rbp+hObject]; hObject
0x180030d77  mov     [rbp+hObject], 0
0x180030d7f  lea     rdx, [rcx-1]
0x180030d83  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180030d87  ja      short loc_180030D8F
0x180030d89  call    cs:__imp_CloseHandle
0x180030d8f  mov     eax, ebx
0x180030d91  mov     rbx, [rsp+30h+arg_8]
0x180030d96  add     rsp, 30h
0x180030d9a  pop     rbp
0x180030d9b  retn
```
