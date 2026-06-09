# CLocationAcquireBase::Dispose(void)

- ea: `0x1800b8170`
- end: `0x1800b8251`
- name: `?Dispose@CLocationAcquireBase@@UEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CLocationAcquireBase *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18010e140`
- `0x18010ebb0`
- `0x18010f6c0`
- `0x180110710`

## callees

- `0x180012194`
- `0x1800123c0`
- `0x1800451d4`
- `0x1800b8170`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b81be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b81be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b81e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b81e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b81af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b81af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b8217`

## pseudocode

```c
__int64 __fastcall CLocationAcquireBase::Dispose(CLocationAcquireBase *this)
{
  void *v2; // rcx
  struct _TP_WORK *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  _BYTE v7[16]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v7,
    (char *)this + 112);
  *((_DWORD *)this + 38) = 1;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v7);
  if ( *((_QWORD *)this + 12) )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      SetEvent(v2);
      WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 12), 1);
    }
  }
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v8,
    (char *)this + 112);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v7,
    (char *)this + 40);
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    CloseThreadpoolWork(v3);
    *((_QWORD *)this + 12) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 2) = 0;
  }
  ATL::CComPtr<ILocationProvider>::operator=((char *)this + 24, 0);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v7);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v8);
  return 0;
}

```

## disassembly

```asm
0x1800b8170  mov     [rsp+arg_0], rbx
0x1800b8175  push    rdi
0x1800b8176  sub     rsp, 40h
0x1800b817a  mov     rbx, rcx
0x1800b817d  lea     rdx, [rcx+70h]
0x1800b8181  lea     rcx, [rsp+48h+var_28]
0x1800b8186  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800b818b  lea     rcx, [rsp+48h+var_28]
0x1800b8190  mov     dword ptr [rbx+98h], 1
0x1800b819a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800b819f  cmp     qword ptr [rbx+60h], 0
0x1800b81a4  jz      short loc_1800B81C4
0x1800b81a6  mov     rcx, [rbx+8]; hEvent
0x1800b81aa  test    rcx, rcx
0x1800b81ad  jz      short loc_1800B81C4
0x1800b81af  call    cs:__imp_SetEvent
0x1800b81b5  mov     rcx, [rbx+60h]; pwk
0x1800b81b9  mov     edx, 1; fCancelPendingCallbacks
0x1800b81be  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800b81c4  lea     rdx, [rbx+70h]
0x1800b81c8  lea     rcx, [rsp+48h+var_18]
0x1800b81cd  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800b81d2  lea     rdx, [rbx+28h]
0x1800b81d6  lea     rcx, [rsp+48h+var_28]
0x1800b81db  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1800b81e0  mov     rcx, [rbx+60h]; pwk
0x1800b81e4  test    rcx, rcx
0x1800b81e7  jz      short loc_1800B81F7
0x1800b81e9  call    cs:__imp_CloseThreadpoolWork
0x1800b81ef  mov     qword ptr [rbx+60h], 0
0x1800b81f7  mov     rcx, [rbx+8]; hObject
0x1800b81fb  test    rcx, rcx
0x1800b81fe  jz      short loc_1800B820E
0x1800b8200  call    cs:__imp_CloseHandle
0x1800b8206  mov     qword ptr [rbx+8], 0
0x1800b820e  mov     rcx, [rbx+10h]; hObject
0x1800b8212  test    rcx, rcx
0x1800b8215  jz      short loc_1800B8225
0x1800b8217  call    cs:__imp_CloseHandle
0x1800b821d  mov     qword ptr [rbx+10h], 0
0x1800b8225  lea     rcx, [rbx+18h]
0x1800b8229  xor     edx, edx
0x1800b822b  call    ??4?$CComPtr@UILocationProvider@@@ATL@@QEAAPEAUILocationProvider@@PEAU2@@Z; ATL::CComPtr<ILocationProvider>::operator=(ILocationProvider *)
0x1800b8230  lea     rcx, [rsp+48h+var_28]
0x1800b8235  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800b823a  lea     rcx, [rsp+48h+var_18]
0x1800b823f  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800b8244  mov     rbx, [rsp+48h+arg_0]
0x1800b8249  xor     eax, eax
0x1800b824b  add     rsp, 40h
0x1800b824f  pop     rdi
0x1800b8250  retn
```
