# FltpCompletionWorkerThread

- ea: `0x180060800`
- end: `0x180060922`
- name: `FltpCompletionWorkerThread`
- size: `290`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180006590`
- `0x180009f20`
- `0x180016f40`
- `0x180016f80`
- `0x180017fc0`
- `0x18001bb10`
- `0x180024800`
- `0x180060800`
- `0x180060930`

## import_xrefs

- `ntoskrnl!IoPropagateActivityIdToThread` at `0x18006083d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x18006083d`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800608da`
- `ntoskrnl!IoClearActivityIdThread` at `0x1800608da`

## pseudocode

```c
__int64 __fastcall FltpCompletionWorkerThread(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v3; // ebp
  __int64 v4; // r9
  __int64 v6; // [rsp+30h] [rbp-48h] BYREF
  __int128 v7; // [rsp+38h] [rbp-40h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v6 = 0;
  v7 = 0;
  v3 = IoPropagateActivityIdToThread(v1, &v7, &v6);
  if ( (*(_DWORD *)(a1 + 4) & 0x400) == 0
    || (LOBYTE(v4) = 1, (unsigned int)FltpDataScanConflictProcessing(v1, *(_QWORD *)(a1 + 104), a1, v4) != -1073741802) )
  {
    FltpPurgeAndReinstateNameCacheForPosixDelete(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 64LL) + 80LL));
    if ( (*(_DWORD *)(a1 + 4) & 0x10) != 0 )
      FltpReinstateNameCachingAllFrames(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 64LL) + 80LL), a1);
    if ( (unsigned int)FltpProcessIoCompletion(a1) != -1073741802 )
      FltpCompleteRequest(v1, *(unsigned int *)(v1 + 48));
  }
  if ( (int)FltpDbgStatus(v3, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 3981, 0) >= 0 )
    IoClearActivityIdThread(v6);
  return FltpDequeueThrottledWorkItem(0);
}

```

## disassembly

```asm
0x180060800  push    rbx
0x180060802  push    rbp
0x180060803  push    rsi
0x180060804  push    rdi
0x180060805  sub     rsp, 58h
0x180060809  mov     rax, cs:__security_cookie
0x180060810  xor     rax, rsp
0x180060813  mov     [rsp+78h+var_30], rax
0x180060818  mov     rsi, [rcx+30h]
0x18006081c  lea     r8, [rsp+78h+var_48]
0x180060821  mov     rbx, rcx
0x180060824  mov     [rsp+78h+var_48], 0
0x18006082d  xorps   xmm0, xmm0
0x180060830  lea     rdx, [rsp+78h+var_40]
0x180060835  mov     rcx, rsi
0x180060838  movups  [rsp+78h+var_40], xmm0
0x18006083d  call    cs:__imp_IoPropagateActivityIdToThread
0x180060844  nop     dword ptr [rax+rax+00h]
0x180060849  test    dword ptr [rbx+4], 400h
0x180060850  mov     ebp, eax
0x180060852  jnz     loc_180060904
0x180060858  mov     rax, [rbx+68h]
0x18006085c  mov     r9, rbx
0x18006085f  mov     r8, [rbx+30h]
0x180060863  mov     rdx, [rbx+70h]
0x180060867  mov     rcx, [rax+40h]
0x18006086b  mov     rcx, [rcx+50h]; OwnerId
0x18006086f  call    FltpPurgeAndReinstateNameCacheForPosixDelete
0x180060874  mov     eax, [rbx+4]
0x180060877  test    al, 10h
0x180060879  jz      short loc_1800608A0
0x18006087b  mov     r8, [rbx+30h]
0x18006087f  mov     rax, [rbx+68h]
0x180060883  mov     r9, r8
0x180060886  mov     rdx, [rbx+70h]
0x18006088a  mov     [rsp+78h+var_58], rbx; __int64
0x18006088f  mov     r8d, [r8+30h]
0x180060893  mov     rcx, [rax+40h]
0x180060897  mov     rcx, [rcx+50h]; OwnerId
0x18006089b  call    FltpReinstateNameCachingAllFrames
0x1800608a0  mov     rcx, rbx; __int64
0x1800608a3  call    FltpProcessIoCompletion
0x1800608a8  cmp     eax, 0C0000016h
0x1800608ad  jz      short loc_1800608BA
0x1800608af  mov     edx, [rsi+30h]
0x1800608b2  mov     rcx, rsi
0x1800608b5  call    FltpCompleteRequest
0x1800608ba  mov     r8d, 0F8Dh
0x1800608c0  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800608c7  xor     r9d, r9d
0x1800608ca  mov     ecx, ebp
0x1800608cc  call    FltpDbgStatus
0x1800608d1  test    eax, eax
0x1800608d3  js      short loc_1800608E6
0x1800608d5  mov     rcx, [rsp+78h+var_48]
0x1800608da  call    cs:__imp_IoClearActivityIdThread
0x1800608e1  nop     dword ptr [rax+rax+00h]
0x1800608e6  xor     ecx, ecx
0x1800608e8  call    FltpDequeueThrottledWorkItem
0x1800608ed  mov     rcx, [rsp+78h+var_30]
0x1800608f2  xor     rcx, rsp; StackCookie
0x1800608f5  call    __security_check_cookie
0x1800608fa  add     rsp, 58h
0x1800608fe  pop     rdi
0x1800608ff  pop     rsi
0x180060900  pop     rbp
0x180060901  pop     rbx
0x180060902  retn
0x180060904  mov     rdx, [rbx+68h]
0x180060908  mov     r9b, 1
0x18006090b  mov     r8, rbx
0x18006090e  mov     rcx, rsi
0x180060911  call    FltpDataScanConflictProcessing
0x180060916  cmp     eax, 0C0000016h
0x18006091b  jz      short loc_1800608BA
0x18006091d  jmp     loc_180060858
```
