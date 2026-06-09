# CVolumeHardware::ProviderFinalRelease(void)

- ea: `0x1800c69d0`
- end: `0x1800c6ab3`
- name: `?ProviderFinalRelease@CVolumeHardware@@UEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CVolumeHardware *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18005c5e4`
- `0x1800c69d0`
- `0x1800c6afc`
- `0x1800e82c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c69e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c69e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6a06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6a06`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6a15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c6a15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c69fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c69fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c6a1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c6a1f`

## pseudocode

```c
void __fastcall CVolumeHardware::ProviderFinalRelease(CVolumeHardware *this)
{
  char *v1; // rbx
  struct _TP_TIMER *v3; // rcx

  v1 = (char *)this + 296;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v3 = (struct _TP_TIMER *)*((_QWORD *)v1 + 6);
  v1[56] = 1;
  SetThreadpoolTimer(v3, 0, 0, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)v1);
  WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)v1 + 6), 1);
  CloseThreadpoolTimer(*((PTP_TIMER *)v1 + 6));
  VolumeHardwareLogger::LogBurst((VolumeHardwareLogger *)v1);
  *((_QWORD *)v1 + 8) = 0;
  if ( *((_QWORD *)this + 31) && *((_DWORD *)this + 70) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_b5e572a40657351cc76f13dbfd2506e3_Traceguids, this);
    }
    (*(void (__fastcall **)(_QWORD, CVolumeHardware *))(**((_QWORD **)this + 31) + 120LL))(*((_QWORD *)this + 31), this);
    *((_DWORD *)this + 70) = 0;
  }
  ATL::CComPtrBase<IPart>::Release((char *)this + 248);
}

```

## disassembly

```asm
0x1800c69d0  mov     [rsp+arg_0], rbx
0x1800c69d5  push    rdi
0x1800c69d6  sub     rsp, 20h
0x1800c69da  lea     rbx, [rcx+128h]
0x1800c69e1  mov     rdi, rcx
0x1800c69e4  mov     rcx, rbx; lpCriticalSection
0x1800c69e7  call    cs:__imp_EnterCriticalSection
0x1800c69ed  mov     rcx, [rbx+30h]; pti
0x1800c69f1  xor     r9d, r9d; msWindowLength
0x1800c69f4  xor     r8d, r8d; msPeriod
0x1800c69f7  mov     byte ptr [rbx+38h], 1
0x1800c69fb  xor     edx, edx; pftDueTime
0x1800c69fd  call    cs:__imp_SetThreadpoolTimer
0x1800c6a03  mov     rcx, rbx; lpCriticalSection
0x1800c6a06  call    cs:__imp_LeaveCriticalSection
0x1800c6a0c  mov     rcx, [rbx+30h]; pti
0x1800c6a10  mov     edx, 1; fCancelPendingCallbacks
0x1800c6a15  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c6a1b  mov     rcx, [rbx+30h]; pti
0x1800c6a1f  call    cs:__imp_CloseThreadpoolTimer
0x1800c6a25  mov     rcx, rbx; this
0x1800c6a28  call    ?LogBurst@VolumeHardwareLogger@@QEAAXXZ; VolumeHardwareLogger::LogBurst(void)
0x1800c6a2d  mov     qword ptr [rbx+40h], 0
0x1800c6a35  lea     rbx, [rdi+0F8h]
0x1800c6a3c  cmp     qword ptr [rbx], 0
0x1800c6a40  jz      short loc_1800C6AA1
0x1800c6a42  cmp     dword ptr [rdi+118h], 0
0x1800c6a49  jz      short loc_1800C6AA1
0x1800c6a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6a52  lea     rax, WPP_GLOBAL_Control
0x1800c6a59  cmp     rcx, rax
0x1800c6a5c  jz      short loc_1800C6A85
0x1800c6a5e  test    dword ptr [rcx+1Ch], 10000h
0x1800c6a65  jz      short loc_1800C6A85
0x1800c6a67  cmp     byte ptr [rcx+19h], 4
0x1800c6a6b  jb      short loc_1800C6A85
0x1800c6a6d  mov     rcx, [rcx+10h]
0x1800c6a71  lea     r8, WPP_b5e572a40657351cc76f13dbfd2506e3_Traceguids
0x1800c6a78  mov     edx, 1Bh
0x1800c6a7d  mov     r9, rdi
0x1800c6a80  call    WPP_SF_q
0x1800c6a85  mov     rcx, [rbx]
0x1800c6a88  mov     rdx, rdi
0x1800c6a8b  mov     rax, [rcx]
0x1800c6a8e  mov     rax, [rax+78h]
0x1800c6a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6a97  mov     dword ptr [rdi+118h], 0
0x1800c6aa1  mov     rcx, rbx
0x1800c6aa4  mov     rbx, [rsp+28h+arg_0]
0x1800c6aa9  add     rsp, 20h
0x1800c6aad  pop     rdi
0x1800c6aae  jmp     ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
```
