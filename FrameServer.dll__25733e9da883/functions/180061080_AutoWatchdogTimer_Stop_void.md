# AutoWatchdogTimer::Stop(void)

- ea: `0x180061080`
- end: `0x1800611ae`
- name: `?Stop@AutoWatchdogTimer@@UEAAXXZ`
- size: `302`
- prototype: `void __fastcall(AutoWatchdogTimer *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800549e4`
- `0x1800a2670`
- `0x1800a55d0`
- `0x1800abb70`
- `0x1800ac210`

## callees

- `0x18005654c`
- `0x18005659c`
- `0x180061080`
- `0x1800618a8`
- `0x180061e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800611a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061096`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061096`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800610ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800610ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800610c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800610c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800610b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800610b1`
- `MFPlat!MFGetSystemTime` at `0x180061102`
- `MFPlat!MFGetSystemTime` at `0x180061102`

## pseudocode

```c
void __fastcall AutoWatchdogTimer::Stop(AutoWatchdogTimer *this)
{
  struct _TP_TIMER *v2; // rcx
  bool v3; // zf
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // edx
  int v7; // ecx
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 OpString; // rax
  __int64 v11; // rdx
  __int64 v12; // r8

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 8), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 8));
    v3 = *((_BYTE *)this + 736) == 0;
    *((_QWORD *)this + 8) = 0;
    if ( v3 && ((unsigned __int8)byte_18010EC4D >= 8u || (Microsoft_Windows_MF_FrameServerEnableBits & 1) != 0) )
    {
      v4 = *((_QWORD *)this + 26);
      v5 = MFGetSystemTime() - v4;
      v8 = -v5;
      if ( v5 > 0 )
        LOBYTE(v8) = v5;
      if ( (Microsoft_Windows_MF_FrameServerEnableBits & 1) != 0 )
        McTemplateU0qxqx_EventWriteTransfer(
          v7,
          v6,
          *((_DWORD *)this + 14),
          *((_QWORD *)this + 9),
          *((_DWORD *)this + 13),
          v8);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        GetScopeString(*((unsigned int *)this + 14));
        OpString = GetOpString(*((unsigned int *)this + 13), v9);
        WPP_SF_qssqDiS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          OpString,
          v12,
          *((_QWORD *)this + 9),
          *((_DWORD *)this + 20),
          v8,
          v11);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180061080  mov     [rsp+arg_0], rbx
0x180061085  mov     [rsp+arg_8], rsi
0x18006108a  push    rdi
0x18006108b  sub     rsp, 50h
0x18006108f  mov     rdi, rcx
0x180061092  add     rcx, 8; lpCriticalSection
0x180061096  call    cs:__imp_EnterCriticalSection
0x18006109c  mov     rcx, [rdi+40h]; pti
0x1800610a0  test    rcx, rcx
0x1800610a3  jz      loc_180061194
0x1800610a9  xor     r9d, r9d; msWindowLength
0x1800610ac  xor     r8d, r8d; msPeriod
0x1800610af  xor     edx, edx; pftDueTime
0x1800610b1  call    cs:__imp_SetThreadpoolTimer
0x1800610b7  mov     rcx, [rdi+40h]; pti
0x1800610bb  mov     edx, 1; fCancelPendingCallbacks
0x1800610c0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800610c6  mov     rcx, [rdi+40h]; pti
0x1800610ca  call    cs:__imp_CloseThreadpoolTimer
0x1800610d0  cmp     byte ptr [rdi+2E0h], 0
0x1800610d7  mov     qword ptr [rdi+40h], 0
0x1800610df  jnz     loc_180061194
0x1800610e5  cmp     cs:byte_18010EC4D, 8
0x1800610ec  jnb     short loc_1800610FB
0x1800610ee  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, 1
0x1800610f5  jz      loc_180061194
0x1800610fb  mov     rbx, [rdi+0D0h]
0x180061102  call    cs:__imp_MFGetSystemTime
0x180061108  sub     rax, rbx
0x18006110b  mov     rbx, rax
0x18006110e  neg     rbx
0x180061111  cmovs   rbx, rax
0x180061115  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, 1
0x18006111c  jz      short loc_180061137
0x18006111e  mov     eax, [rdi+34h]
0x180061121  mov     r9, [rdi+48h]
0x180061125  mov     r8d, [rdi+38h]
0x180061129  mov     [rsp+58h+var_30], rbx
0x18006112e  mov     dword ptr [rsp+58h+var_38], eax
0x180061132  call    McTemplateU0qxqx_EventWriteTransfer
0x180061137  cmp     cs:byte_18010EC4D, 8
0x18006113e  jb      short loc_180061194
0x180061140  mov     ecx, [rdi+38h]
0x180061143  lea     rdx, [rdi+0D8h]
0x18006114a  call    GetScopeString
0x18006114f  mov     ecx, [rdi+34h]
0x180061152  mov     r8, rax
0x180061155  call    GetOpString
0x18006115a  mov     rcx, cs:WPP_GLOBAL_Control
0x180061161  mov     r9, rdi
0x180061164  mov     [rsp+58h+var_10], rdx; __int64
0x180061169  mov     edx, [rdi+50h]
0x18006116c  mov     qword ptr [rsp+58h+var_18], rbx; char
0x180061171  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180061178  mov     dword ptr [rsp+58h+var_20], edx; char
0x18006117c  mov     rdx, [rdi+48h]
0x180061180  mov     qword ptr [rsp+58h+var_28], rdx; char
0x180061185  mov     [rsp+58h+var_30], r8; __int64
0x18006118a  mov     [rsp+58h+var_38], rax; __int64
0x18006118f  call    WPP_SF_qssqDiS
0x180061194  lea     rcx, [rdi+8]
0x180061198  mov     rbx, [rsp+58h+arg_0]
0x18006119d  mov     rsi, [rsp+58h+arg_8]
0x1800611a2  add     rsp, 50h
0x1800611a6  pop     rdi
0x1800611a7  jmp     cs:__imp_LeaveCriticalSection
```
