# IPxlatPolicyMgrGlobals::~IPxlatPolicyMgrGlobals(void)

- ea: `0x18000d040`
- end: `0x18000d103`
- name: `??1IPxlatPolicyMgrGlobals@@QEAA@XZ`
- size: `195`
- prototype: `void __fastcall(IPxlatPolicyMgrGlobals *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000df7c`
- `0x18001865a`

## callees

- `0x18000d040`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d051`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d051`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d07f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d0d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d07f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d0d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d076`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d0c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d076`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d0c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d068`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d0b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d068`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d0b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d0f2`

## pseudocode

```c
void __fastcall IPxlatPolicyMgrGlobals::~IPxlatPolicyMgrGlobals(IPxlatPolicyMgrGlobals *this)
{
  struct _TP_WAIT *v2; // rdi
  char *v3; // rcx
  HKEY v4; // rcx
  struct _TP_WAIT *v5; // rdi
  char *v6; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 7), 0, 0);
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(v2);
  }
  v3 = (char *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  v4 = (HKEY)*((_QWORD *)this + 5);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 2), 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(v5);
  }
  v6 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  if ( *(_QWORD *)this )
    RegCloseKey(*(HKEY *)this);
}

```

## disassembly

```asm
0x18000d040  mov     [rsp+arg_0], rbx
0x18000d045  push    rdi
0x18000d046  sub     rsp, 20h
0x18000d04a  mov     rbx, rcx
0x18000d04d  add     rcx, 50h ; 'P'; lpCriticalSection
0x18000d051  call    cs:__imp_DeleteCriticalSection
0x18000d057  mov     rdi, [rbx+38h]
0x18000d05b  test    rdi, rdi
0x18000d05e  jz      short loc_18000D085
0x18000d060  xor     r8d, r8d; pftTimeout
0x18000d063  xor     edx, edx; h
0x18000d065  mov     rcx, rdi; pwa
0x18000d068  call    cs:__imp_SetThreadpoolWait
0x18000d06e  mov     edx, 1; fCancelPendingCallbacks
0x18000d073  mov     rcx, rdi; pwa
0x18000d076  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d07c  mov     rcx, rdi; pwa
0x18000d07f  call    cs:__imp_CloseThreadpoolWait
0x18000d085  mov     rcx, [rbx+30h]; hObject
0x18000d089  lea     rax, [rcx-1]
0x18000d08d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d091  ja      short loc_18000D099
0x18000d093  call    cs:__imp_CloseHandle
0x18000d099  mov     rcx, [rbx+28h]; hKey
0x18000d09d  test    rcx, rcx
0x18000d0a0  jz      short loc_18000D0A8
0x18000d0a2  call    cs:__imp_RegCloseKey
0x18000d0a8  mov     rdi, [rbx+10h]
0x18000d0ac  test    rdi, rdi
0x18000d0af  jz      short loc_18000D0D6
0x18000d0b1  xor     r8d, r8d; pftTimeout
0x18000d0b4  xor     edx, edx; h
0x18000d0b6  mov     rcx, rdi; pwa
0x18000d0b9  call    cs:__imp_SetThreadpoolWait
0x18000d0bf  mov     edx, 1; fCancelPendingCallbacks
0x18000d0c4  mov     rcx, rdi; pwa
0x18000d0c7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d0cd  mov     rcx, rdi; pwa
0x18000d0d0  call    cs:__imp_CloseThreadpoolWait
0x18000d0d6  mov     rcx, [rbx+8]; hObject
0x18000d0da  lea     rax, [rcx-1]
0x18000d0de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d0e2  ja      short loc_18000D0EA
0x18000d0e4  call    cs:__imp_CloseHandle
0x18000d0ea  mov     rcx, [rbx]; hKey
0x18000d0ed  test    rcx, rcx
0x18000d0f0  jz      short loc_18000D0F8
0x18000d0f2  call    cs:__imp_RegCloseKey
0x18000d0f8  mov     rbx, [rsp+28h+arg_0]
0x18000d0fd  add     rsp, 20h
0x18000d101  pop     rdi
0x18000d102  retn
```
