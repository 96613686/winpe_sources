# CConstraintModelResourceManager::Shutdown(void)

- ea: `0x180105124`
- end: `0x1801051e4`
- name: `?Shutdown@CConstraintModelResourceManager@@AEAAXXZ`
- size: `192`
- prototype: `void __fastcall(CConstraintModelResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180102400`

## callees

- `0x1800382ac`
- `0x18005917c`
- `0x180104d40`
- `0x180105124`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180105187`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180105187`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18010517a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18010517a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180105168`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180105168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801051b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801051d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801051b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801051d0`

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
0x180105124  push    rbx
0x180105126  sub     rsp, 30h
0x18010512a  cmp     qword ptr [rcx+0B0h], 0
0x180105132  mov     rbx, rcx
0x180105135  jz      short loc_180105198
0x180105137  lea     rdx, [rcx+0C0h]
0x18010513e  lea     rcx, [rsp+38h+var_18]
0x180105143  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180105148  lea     rcx, [rsp+38h+var_18]; this
0x18010514d  mov     dword ptr [rbx+118h], 1
0x180105157  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18010515c  mov     rcx, [rbx+0B0h]; pwa
0x180105163  xor     r8d, r8d; pftTimeout
0x180105166  xor     edx, edx; h
0x180105168  call    cs:__imp_SetThreadpoolWait
0x18010516e  mov     rcx, [rbx+0B0h]; pwa
0x180105175  mov     edx, 1; fCancelPendingCallbacks
0x18010517a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180105180  mov     rcx, [rbx+0B0h]; pwa
0x180105187  call    cs:__imp_CloseThreadpoolWait
0x18010518d  mov     qword ptr [rbx+0B0h], 0
0x180105198  mov     rcx, rbx; this
0x18010519b  call    ?ReleaseAllResources@CConstraintModelResourceManager@@AEAAXXZ; CConstraintModelResourceManager::ReleaseAllResources(void)
0x1801051a0  mov     rcx, [rbx+0B8h]; hObject
0x1801051a7  lea     rax, [rcx-1]
0x1801051ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801051af  ja      short loc_1801051C2
0x1801051b1  call    cs:__imp_CloseHandle
0x1801051b7  mov     qword ptr [rbx+0B8h], 0
0x1801051c2  mov     rcx, [rbx+40h]; hObject
0x1801051c6  lea     rax, [rcx-1]
0x1801051ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801051ce  ja      short loc_1801051DE
0x1801051d0  call    cs:__imp_CloseHandle
0x1801051d6  mov     qword ptr [rbx+40h], 0
0x1801051de  add     rsp, 30h
0x1801051e2  pop     rbx
0x1801051e3  retn
```
