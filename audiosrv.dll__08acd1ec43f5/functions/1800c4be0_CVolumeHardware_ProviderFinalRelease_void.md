# CVolumeHardware::ProviderFinalRelease(void)

- ea: `0x1800c4be0`
- end: `0x1800c4cc3`
- name: `?ProviderFinalRelease@CVolumeHardware@@UEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CVolumeHardware *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18005c154`
- `0x1800c4be0`
- `0x1800c4d0c`
- `0x1800e7b40`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c4bf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c4bf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c4c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c4c16`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c4c25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c4c25`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c4c0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c4c0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c4c2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c4c2f`

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
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_b5e572a40657351cc76f13dbfd2506e3_Traceguids, this);
    }
    (*(void (__fastcall **)(_QWORD, CVolumeHardware *))(**((_QWORD **)this + 31) + 120LL))(*((_QWORD *)this + 31), this);
    *((_DWORD *)this + 70) = 0;
  }
  ATL::CComPtrBase<IPart>::Release((char *)this + 248);
}

```

## disassembly

```asm
0x1800c4be0  mov     [rsp+arg_0], rbx
0x1800c4be5  push    rdi
0x1800c4be6  sub     rsp, 20h
0x1800c4bea  lea     rbx, [rcx+128h]
0x1800c4bf1  mov     rdi, rcx
0x1800c4bf4  mov     rcx, rbx; lpCriticalSection
0x1800c4bf7  call    cs:__imp_EnterCriticalSection
0x1800c4bfd  mov     rcx, [rbx+30h]; pti
0x1800c4c01  xor     r9d, r9d; msWindowLength
0x1800c4c04  xor     r8d, r8d; msPeriod
0x1800c4c07  mov     byte ptr [rbx+38h], 1
0x1800c4c0b  xor     edx, edx; pftDueTime
0x1800c4c0d  call    cs:__imp_SetThreadpoolTimer
0x1800c4c13  mov     rcx, rbx; lpCriticalSection
0x1800c4c16  call    cs:__imp_LeaveCriticalSection
0x1800c4c1c  mov     rcx, [rbx+30h]; pti
0x1800c4c20  mov     edx, 1; fCancelPendingCallbacks
0x1800c4c25  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c4c2b  mov     rcx, [rbx+30h]; pti
0x1800c4c2f  call    cs:__imp_CloseThreadpoolTimer
0x1800c4c35  mov     rcx, rbx; this
0x1800c4c38  call    ?LogBurst@VolumeHardwareLogger@@QEAAXXZ; VolumeHardwareLogger::LogBurst(void)
0x1800c4c3d  mov     qword ptr [rbx+40h], 0
0x1800c4c45  lea     rbx, [rdi+0F8h]
0x1800c4c4c  cmp     qword ptr [rbx], 0
0x1800c4c50  jz      short loc_1800C4CB1
0x1800c4c52  cmp     dword ptr [rdi+118h], 0
0x1800c4c59  jz      short loc_1800C4CB1
0x1800c4c5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c62  lea     rax, WPP_GLOBAL_Control
0x1800c4c69  cmp     rcx, rax
0x1800c4c6c  jz      short loc_1800C4C95
0x1800c4c6e  test    dword ptr [rcx+1Ch], 10000h
0x1800c4c75  jz      short loc_1800C4C95
0x1800c4c77  cmp     byte ptr [rcx+19h], 4
0x1800c4c7b  jb      short loc_1800C4C95
0x1800c4c7d  mov     rcx, [rcx+10h]
0x1800c4c81  lea     r8, WPP_b5e572a40657351cc76f13dbfd2506e3_Traceguids
0x1800c4c88  mov     edx, 1Bh
0x1800c4c8d  mov     r9, rdi
0x1800c4c90  call    WPP_SF_q
0x1800c4c95  mov     rcx, [rbx]
0x1800c4c98  mov     rdx, rdi
0x1800c4c9b  mov     rax, [rcx]
0x1800c4c9e  mov     rax, [rax+78h]
0x1800c4ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ca7  mov     dword ptr [rdi+118h], 0
0x1800c4cb1  mov     rcx, rbx
0x1800c4cb4  mov     rbx, [rsp+28h+arg_0]
0x1800c4cb9  add     rsp, 20h
0x1800c4cbd  pop     rdi
0x1800c4cbe  jmp     ?Release@?$CComPtrBase@UIPart@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPart>::Release(void)
```
