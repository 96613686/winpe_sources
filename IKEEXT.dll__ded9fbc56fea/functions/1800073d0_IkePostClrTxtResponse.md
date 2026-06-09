# IkePostClrTxtResponse

- ea: `0x1800073d0`
- end: `0x180007621`
- name: `IkePostClrTxtResponse`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800217a0`

## callees

- `0x1800037c4`
- `0x1800061ec`
- `0x1800073d0`
- `0x180008388`
- `0x180010db0`
- `0x180016534`
- `0x18004882c`
- `0x18004aa3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075fe`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800075ec`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800075ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007425`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007539`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007425`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007539`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800074d5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800074d5`

## string_xrefs

- `0x18000760a`: `TrySubmitThreadpoolCallback`

## pseudocode

```c
__int64 __fastcall IkePostClrTxtResponse(_OWORD *a1)
{
  __int64 v2; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  _OWORD *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rbp
  _OWORD *v7; // rdi
  __int64 v8; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  DWORD LastError; // eax
  __int64 v14; // rcx
  _OWORD *v15; // [rsp+38h] [rbp+10h] BYREF

  TraceLogHelper("IkePostClrTxtResponse", 1);
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v2);
  if ( IsEnabledDeviceUsageNoInline )
  {
    v6 = 0;
    v15 = HeapAlloc(gWfpHeap, 8u, 0xB0u);
    v7 = v15;
    if ( v15 )
    {
      v8 = 0;
      if ( gWfpTrackHeapAllocs )
        _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v11 = WfpReportSysErrorAsNtStatus(v10, "HeapAlloc", 3221225495LL);
      v8 = v11;
      if ( v11 )
        WfpReportError(v11, "WfpMemAlloc25B");
    }
  }
  else
  {
    v4 = HeapAlloc(gWfpHeap, 8u, 0xB0u);
    v6 = 0;
    v15 = v4;
    v7 = v4;
    if ( v4 )
    {
      v8 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v4));
    }
    else
    {
      v12 = WfpReportSysErrorAsNtStatus(v5, "HeapAlloc", 3221225495LL);
      v8 = v12;
      if ( v12 )
        WfpReportError(v12, "WfpMemAlloc");
    }
  }
  if ( v8 )
    goto LABEL_15;
  *v7 = *a1;
  v7[1] = a1[1];
  v7[2] = a1[2];
  v7[3] = a1[3];
  v7[4] = a1[4];
  v7[5] = a1[5];
  v7[6] = a1[6];
  v7[7] = a1[7];
  v7[8] = a1[8];
  v7[9] = a1[9];
  v7[10] = a1[10];
  if ( TrySubmitThreadpoolCallback(
         IkeHandleClearTextRespDispatch,
         v7,
         (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[76].LockCount) )
  {
    _InterlockedIncrement((volatile signed __int32 *)&gIkeExtGlobals[48].SpinCount + 1);
  }
  else
  {
    LastError = GetLastError();
    v6 = WfpReportSysErrorAsWinError(v14, "TrySubmitThreadpoolCallback", LastError, 1);
  }
  v8 = IkeReturnError(v6, "IkeQueueWorkItem");
  if ( v8 )
LABEL_15:
    WfpMemFree(&v15);
  TraceLogHelper("IkePostClrTxtResponse", 0);
  return IkeReturnError(v8, "IkePostClrTxtResponse");
}

```

## disassembly

```asm
0x1800073d0  mov     [rsp+arg_18], rbx
0x1800073d5  push    rsi
0x1800073d6  sub     rsp, 20h
0x1800073da  mov     rsi, rcx
0x1800073dd  mov     edx, 1
0x1800073e2  lea     rcx, aIkepostclrtxtr; "IkePostClrTxtResponse"
0x1800073e9  call    TraceLogHelper
0x1800073ee  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x1800073f4  test    al, 10h
0x1800073f6  jnz     loc_180007574
0x1800073fc  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x180007401  mov     rcx, cs:gWfpHeap; hHeap
0x180007408  mov     edx, 8; dwFlags
0x18000740d  mov     [rsp+28h+arg_0], rbp
0x180007412  mov     r8d, 0B0h; dwBytes
0x180007418  mov     [rsp+28h+arg_10], rdi
0x18000741d  test    eax, eax
0x18000741f  jnz     loc_180007539
0x180007425  call    cs:__imp_HeapAlloc
0x18000742b  xor     ebp, ebp
0x18000742d  mov     [rsp+28h+arg_8], rax
0x180007432  mov     rdi, rax
0x180007435  test    rax, rax
0x180007438  jz      loc_1800075AE
0x18000743e  mov     ebx, ebp
0x180007440  cmp     cs:gWfpTrackHeapBytes, ebx
0x180007446  jnz     loc_1800075E0
0x18000744c  test    rbx, rbx
0x18000744f  jnz     loc_180007568
0x180007455  movups  xmm0, xmmword ptr [rsi]
0x180007458  mov     rdx, rdi; pv
0x18000745b  lea     rcx, IkeHandleClearTextRespDispatch; pfns
0x180007462  movups  xmmword ptr [rdi], xmm0
0x180007465  movups  xmm1, xmmword ptr [rsi+10h]
0x180007469  movups  xmmword ptr [rdi+10h], xmm1
0x18000746d  movups  xmm0, xmmword ptr [rsi+20h]
0x180007471  movups  xmmword ptr [rdi+20h], xmm0
0x180007475  movups  xmm1, xmmword ptr [rsi+30h]
0x180007479  movups  xmmword ptr [rdi+30h], xmm1
0x18000747d  movups  xmm0, xmmword ptr [rsi+40h]
0x180007481  movups  xmmword ptr [rdi+40h], xmm0
0x180007485  movups  xmm1, xmmword ptr [rsi+50h]
0x180007489  movups  xmmword ptr [rdi+50h], xmm1
0x18000748d  movups  xmm0, xmmword ptr [rsi+60h]
0x180007491  movups  xmmword ptr [rdi+60h], xmm0
0x180007495  movups  xmm1, xmmword ptr [rsi+70h]
0x180007499  movups  xmmword ptr [rdi+70h], xmm1
0x18000749d  movups  xmm0, xmmword ptr [rsi+80h]
0x1800074a4  movups  xmmword ptr [rdi+80h], xmm0
0x1800074ab  movups  xmm1, xmmword ptr [rsi+90h]
0x1800074b2  movups  xmmword ptr [rdi+90h], xmm1
0x1800074b9  movups  xmm0, xmmword ptr [rsi+0A0h]
0x1800074c0  movups  xmmword ptr [rdi+0A0h], xmm0
0x1800074c7  mov     r8, cs:gIkeExtGlobals
0x1800074ce  add     r8, 0BE8h; pcbe
0x1800074d5  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800074db  test    eax, eax
0x1800074dd  jz      loc_1800075FE
0x1800074e3  mov     rax, cs:gIkeExtGlobals
0x1800074ea  lock inc dword ptr [rax+7A4h]
0x1800074f1  lea     rdx, aIkequeueworkit_0; "IkeQueueWorkItem"
0x1800074f8  mov     rcx, rbp
0x1800074fb  call    IkeReturnError
0x180007500  mov     rbx, rax
0x180007503  test    rax, rax
0x180007506  jnz     short loc_180007568
0x180007508  xor     edx, edx
0x18000750a  lea     rcx, aIkepostclrtxtr; "IkePostClrTxtResponse"
0x180007511  call    TraceLogHelper
0x180007516  lea     rdx, aIkepostclrtxtr; "IkePostClrTxtResponse"
0x18000751d  mov     rcx, rbx
0x180007520  mov     rdi, [rsp+28h+arg_10]
0x180007525  mov     rbp, [rsp+28h+arg_0]
0x18000752a  mov     rbx, [rsp+28h+arg_18]
0x18000752f  add     rsp, 20h
0x180007533  pop     rsi
0x180007534  jmp     IkeReturnError
0x180007539  call    cs:__imp_HeapAlloc
0x18000753f  xor     ebp, ebp
0x180007541  mov     [rsp+28h+arg_8], rax
0x180007546  mov     rdi, rax
0x180007549  test    rax, rax
0x18000754c  jz      short loc_18000757C
0x18000754e  mov     ebx, ebp
0x180007550  cmp     cs:gWfpTrackHeapAllocs, ebx
0x180007556  jz      loc_18000744C
0x18000755c  lock inc cs:gWfpNumHeapAllocs
0x180007563  jmp     loc_18000744C
0x180007568  lea     rcx, [rsp+28h+arg_8]
0x18000756d  call    WfpMemFree
0x180007572  jmp     short loc_180007508
0x180007574  and     eax, 1
0x180007577  jmp     loc_180007401
0x18000757c  mov     r8d, 0C0000017h
0x180007582  lea     rdx, aHeapalloc; "HeapAlloc"
0x180007589  call    WfpReportSysErrorAsNtStatus
0x18000758e  mov     rbx, rax
0x180007591  test    rax, rax
0x180007594  jz      loc_18000744C
0x18000759a  lea     rdx, aWfpmemalloc25b; "WfpMemAlloc25B"
0x1800075a1  mov     rcx, rax
0x1800075a4  call    WfpReportError
0x1800075a9  jmp     loc_18000744C
0x1800075ae  mov     r8d, 0C0000017h
0x1800075b4  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800075bb  call    WfpReportSysErrorAsNtStatus
0x1800075c0  mov     rbx, rax
0x1800075c3  test    rax, rax
0x1800075c6  jz      loc_18000744C
0x1800075cc  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800075d3  mov     rcx, rax
0x1800075d6  call    WfpReportError
0x1800075db  jmp     loc_18000744C
0x1800075e0  mov     rcx, cs:gWfpHeap; hHeap
0x1800075e7  mov     r8, rax; lpMem
0x1800075ea  xor     edx, edx; dwFlags
0x1800075ec  call    cs:__imp_HeapSize
0x1800075f2  lock add cs:gWfpHeapBytesAllocated, eax
0x1800075f9  jmp     loc_18000744C
0x1800075fe  call    cs:__imp_GetLastError
0x180007604  mov     r9d, 1
0x18000760a  lea     rdx, aTrysubmitthrea; "TrySubmitThreadpoolCallback"
0x180007611  mov     r8d, eax
0x180007614  call    WfpReportSysErrorAsWinError
0x180007619  mov     rbp, rax
0x18000761c  jmp     loc_1800074F1
```
