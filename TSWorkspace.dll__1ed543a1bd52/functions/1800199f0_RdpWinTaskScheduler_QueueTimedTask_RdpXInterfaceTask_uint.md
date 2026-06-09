# RdpWinTaskScheduler::QueueTimedTask(RdpXInterfaceTask *,uint)

- ea: `0x1800199f0`
- end: `0x180019b56`
- name: `?QueueTimedTask@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@PEAURdpXInterfaceTask@@I@Z`
- size: `358`
- prototype: `enum _XResult32 __high(struct RdpXInterfaceTask *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x18000ec94`
- `0x18001958c`
- `0x1800199f0`
- `0x180019fb0`
- `0x18001a008`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ad3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019aa6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019aa6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019b3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019b3b`

## pseudocode

```c
__int64 __fastcall RdpWinTaskScheduler::QueueTimedTask(__int64 a1, void (__fastcall ***a2)(void *), unsigned int a3)
{
  void (__fastcall **v3)(void *); // rax
  __int64 *v4; // rbx
  __int64 v6; // rbp
  __int64 v8; // rax
  unsigned int v9; // ebx
  unsigned int ActivityIdPrefix; // eax
  struct _TP_TIMER *ThreadpoolTimer; // r10
  DWORD LastError; // ebx
  unsigned int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  int v16; // [rsp+38h] [rbp-30h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  v3 = *a2;
  v4 = (__int64 *)(a1 + 16);
  v6 = a3;
  v15 = a1 + 16;
  pftDueTime = 0;
  (*v3)(a2);
  v8 = *v4;
  v16 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64 *))(v8 + 8))(v4);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        17,
        WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids,
        ActivityIdPrefix,
        v9,
        v9);
    }
  }
  else
  {
    ThreadpoolTimer = CreateThreadpoolTimer(
                        RdpWinTaskScheduler::staticTimerCallback,
                        a2,
                        (PTP_CALLBACK_ENVIRON)(a1 + 56));
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)(-10000 * v6);
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      LastError = GetLastError();
      v13 = RdpX_GetActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        18,
        WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids,
        v13,
        LastError);
    }
    v9 = -1;
  }
  (*a2)[1](a2);
LABEL_14:
  RdpXSafeRundownAutoDispatch::~RdpXSafeRundownAutoDispatch((RdpXSafeRundownAutoDispatch *)&v15);
  return v9;
}

```

## disassembly

```asm
0x1800199f0  push    rbx
0x1800199f2  push    rbp
0x1800199f3  push    rsi
0x1800199f4  push    rdi
0x1800199f5  sub     rsp, 48h
0x1800199f9  mov     rax, [rdx]
0x1800199fc  lea     rbx, [rcx+10h]
0x180019a00  mov     rsi, rcx
0x180019a03  mov     ebp, r8d
0x180019a06  mov     rcx, rdx
0x180019a09  mov     [rsp+68h+var_38], rbx
0x180019a0e  mov     rdi, rdx
0x180019a11  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x180019a1a  mov     rax, [rax]
0x180019a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a22  mov     rax, [rbx]
0x180019a25  mov     rcx, rbx
0x180019a28  mov     [rsp+68h+var_30], 1
0x180019a30  mov     rax, [rax+8]
0x180019a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a39  mov     ebx, eax
0x180019a3b  test    eax, eax
0x180019a3d  jz      short loc_180019A98
0x180019a3f  mov     rdx, cs:WPP_GLOBAL_Control
0x180019a46  lea     rcx, WPP_GLOBAL_Control
0x180019a4d  cmp     rdx, rcx
0x180019a50  jz      loc_180019B06
0x180019a56  test    byte ptr [rdx+44h], 10h
0x180019a5a  jz      loc_180019B06
0x180019a60  cmp     byte ptr [rdx+41h], 2
0x180019a64  jb      loc_180019B06
0x180019a6a  call    RdpX_GetActivityIdPrefix
0x180019a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a76  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x180019a7d  mov     edx, 11h
0x180019a82  mov     [rsp+68h+var_40], ebx
0x180019a86  mov     r9d, eax
0x180019a89  mov     [rsp+68h+var_48], ebx
0x180019a8d  mov     rcx, [rcx+38h]
0x180019a91  call    WPP_SF_DLD
0x180019a96  jmp     short loc_180019B06
0x180019a98  lea     r8, [rsi+38h]; pcbe
0x180019a9c  mov     rdx, rdi; pv
0x180019a9f  lea     rcx, ?staticTimerCallback@RdpWinTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019aa6  call    cs:__imp_CreateThreadpoolTimer
0x180019aac  mov     r10, rax
0x180019aaf  test    rax, rax
0x180019ab2  jnz     short loc_180019B17
0x180019ab4  mov     rax, cs:WPP_GLOBAL_Control
0x180019abb  lea     rcx, WPP_GLOBAL_Control
0x180019ac2  cmp     rax, rcx
0x180019ac5  jz      short loc_180019B03
0x180019ac7  test    byte ptr [rax+44h], 10h
0x180019acb  jz      short loc_180019B03
0x180019acd  cmp     byte ptr [rax+41h], 2
0x180019ad1  jb      short loc_180019B03
0x180019ad3  call    cs:__imp_GetLastError
0x180019ad9  mov     ebx, eax
0x180019adb  call    RdpX_GetActivityIdPrefix
0x180019ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ae7  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x180019aee  mov     edx, 12h
0x180019af3  mov     [rsp+68h+var_48], ebx
0x180019af7  mov     r9d, eax
0x180019afa  mov     rcx, [rcx+38h]
0x180019afe  call    WPP_SF_Dd
0x180019b03  or      ebx, 0FFFFFFFFh
0x180019b06  mov     rax, [rdi]
0x180019b09  mov     rcx, rdi
0x180019b0c  mov     rax, [rax+8]
0x180019b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b15  jmp     short loc_180019B41
0x180019b17  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x180019b1e  xor     r9d, r9d; msWindowLength
0x180019b21  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180019b26  mov     rcx, rax
0x180019b29  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x180019b2d  shr     rcx, 20h
0x180019b31  xor     r8d, r8d; msPeriod
0x180019b34  mov     [rsp+68h+pftDueTime.dwHighDateTime], ecx
0x180019b38  mov     rcx, r10; pti
0x180019b3b  call    cs:__imp_SetThreadpoolTimer
0x180019b41  lea     rcx, [rsp+68h+var_38]; this
0x180019b46  call    ??1RdpXSafeRundownAutoDispatch@@QEAA@XZ; RdpXSafeRundownAutoDispatch::~RdpXSafeRundownAutoDispatch(void)
0x180019b4b  mov     eax, ebx
0x180019b4d  add     rsp, 48h
0x180019b51  pop     rdi
0x180019b52  pop     rsi
0x180019b53  pop     rbp
0x180019b54  pop     rbx
0x180019b55  retn
```
