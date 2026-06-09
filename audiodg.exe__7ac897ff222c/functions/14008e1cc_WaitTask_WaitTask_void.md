# _WaitTask::~_WaitTask(void)

- ea: `0x14008e1cc`
- end: `0x14008e254`
- name: `??1_WaitTask@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(_WaitTask *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14008e25c`

## callees

- `0x14000f36c`
- `0x14008e1cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14008e1e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14008e1e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14008e1f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14008e1f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14008e1fe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14008e1fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008e214`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008e214`

## pseudocode

```c
void __fastcall _WaitTask::~_WaitTask(PTP_WAIT *this)
{
  struct _TP_WAIT *v2; // rcx
  PTP_WAIT v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  v2 = *this;
  if ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(v2, 1);
    if ( *this )
    {
      SetThreadpoolWait(*this, 0, 0);
      CloseThreadpoolWait(*this);
      *this = 0;
    }
  }
  v3 = this[3];
  if ( v3 )
  {
    CloseHandle(v3);
    this[3] = 0;
  }
  this[1] = 0;
  v4 = this[2];
  this[2] = 0;
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = this[2];
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x14008e1cc  push    rbx
0x14008e1ce  sub     rsp, 20h
0x14008e1d2  mov     rbx, rcx
0x14008e1d5  mov     rcx, [rcx]; pwa
0x14008e1d8  test    rcx, rcx
0x14008e1db  jz      short loc_14008E20B
0x14008e1dd  mov     edx, 1; fCancelPendingCallbacks
0x14008e1e2  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14008e1e8  mov     rcx, [rbx]; pwa
0x14008e1eb  test    rcx, rcx
0x14008e1ee  jz      short loc_14008E20B
0x14008e1f0  xor     r8d, r8d; pftTimeout
0x14008e1f3  xor     edx, edx; h
0x14008e1f5  call    cs:__imp_SetThreadpoolWait
0x14008e1fb  mov     rcx, [rbx]; pwa
0x14008e1fe  call    cs:__imp_CloseThreadpoolWait
0x14008e204  mov     qword ptr [rbx], 0
0x14008e20b  mov     rcx, [rbx+18h]; hObject
0x14008e20f  test    rcx, rcx
0x14008e212  jz      short loc_14008E222
0x14008e214  call    cs:__imp_CloseHandle
0x14008e21a  mov     qword ptr [rbx+18h], 0
0x14008e222  mov     qword ptr [rbx+8], 0
0x14008e22a  mov     rcx, [rbx+10h]; this
0x14008e22e  mov     qword ptr [rbx+10h], 0
0x14008e236  test    rcx, rcx
0x14008e239  jz      short loc_14008E240
0x14008e23b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14008e240  mov     rcx, [rbx+10h]; this
0x14008e244  test    rcx, rcx
0x14008e247  jz      short loc_14008E24E
0x14008e249  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14008e24e  add     rsp, 20h
0x14008e252  pop     rbx
0x14008e253  retn
```
