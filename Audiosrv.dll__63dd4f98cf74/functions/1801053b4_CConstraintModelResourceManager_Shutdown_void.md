# CConstraintModelResourceManager::Shutdown(void)

- ea: `0x1801053b4`
- end: `0x180105474`
- name: `?Shutdown@CConstraintModelResourceManager@@AEAAXXZ`
- size: `192`
- prototype: `void __fastcall(CConstraintModelResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180102690`

## callees

- `0x18003840c`
- `0x180058cec`
- `0x180104fd0`
- `0x1801053b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180105417`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180105417`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18010540a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18010540a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801053f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801053f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180105441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180105460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180105441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180105460`

## pseudocode

```c
void __fastcall CConstraintModelResourceManager::Shutdown(CConstraintModelResourceManager *this)
{
  char *v2; // rcx
  char *v3; // rcx
  _BYTE v4[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_QWORD *)this + 22) )
  {
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      v4,
      (char *)this + 192);
    *((_DWORD *)this + 70) = 1;
    ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v4);
    SetThreadpoolWait(*((PTP_WAIT *)this + 22), 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 22), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 22));
    *((_QWORD *)this + 22) = 0;
  }
  CConstraintModelResourceManager::ReleaseAllResources(this);
  v2 = (char *)*((_QWORD *)this + 23);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 23) = 0;
  }
  v3 = (char *)*((_QWORD *)this + 8);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x1801053b4  push    rbx
0x1801053b6  sub     rsp, 30h
0x1801053ba  cmp     qword ptr [rcx+0B0h], 0
0x1801053c2  mov     rbx, rcx
0x1801053c5  jz      short loc_180105428
0x1801053c7  lea     rdx, [rcx+0C0h]
0x1801053ce  lea     rcx, [rsp+38h+var_18]
0x1801053d3  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x1801053d8  lea     rcx, [rsp+38h+var_18]; this
0x1801053dd  mov     dword ptr [rbx+118h], 1
0x1801053e7  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1801053ec  mov     rcx, [rbx+0B0h]; pwa
0x1801053f3  xor     r8d, r8d; pftTimeout
0x1801053f6  xor     edx, edx; h
0x1801053f8  call    cs:__imp_SetThreadpoolWait
0x1801053fe  mov     rcx, [rbx+0B0h]; pwa
0x180105405  mov     edx, 1; fCancelPendingCallbacks
0x18010540a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180105410  mov     rcx, [rbx+0B0h]; pwa
0x180105417  call    cs:__imp_CloseThreadpoolWait
0x18010541d  mov     qword ptr [rbx+0B0h], 0
0x180105428  mov     rcx, rbx; this
0x18010542b  call    ?ReleaseAllResources@CConstraintModelResourceManager@@AEAAXXZ; CConstraintModelResourceManager::ReleaseAllResources(void)
0x180105430  mov     rcx, [rbx+0B8h]; hObject
0x180105437  lea     rax, [rcx-1]
0x18010543b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010543f  ja      short loc_180105452
0x180105441  call    cs:__imp_CloseHandle
0x180105447  mov     qword ptr [rbx+0B8h], 0
0x180105452  mov     rcx, [rbx+40h]; hObject
0x180105456  lea     rax, [rcx-1]
0x18010545a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010545e  ja      short loc_18010546E
0x180105460  call    cs:__imp_CloseHandle
0x180105466  mov     qword ptr [rbx+40h], 0
0x18010546e  add     rsp, 30h
0x180105472  pop     rbx
0x180105473  retn
```
