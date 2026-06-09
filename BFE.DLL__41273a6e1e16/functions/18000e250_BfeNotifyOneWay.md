# BfeNotifyOneWay

- ea: `0x18000e250`
- end: `0x18000e7d2`
- name: `BfeNotifyOneWay`
- size: `1410`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `11`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180011c50`
- `0x18001e064`
- `0x18001fd24`
- `0x180027c20`
- `0x18002bb10`
- `0x18002be30`
- `0x18003e908`
- `0x1800678c8`
- `0x18006ff30`
- `0x1800704e8`
- `0x180073a08`

## callees

- `0x18000e250`
- `0x18000e7e0`
- `0x18000ebf0`
- `0x18000ecf0`
- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x1800133a0`
- `0x1800135ac`
- `0x1800197d0`
- `0x18002c130`
- `0x18004fb50`
- `0x180055f04`
- `0x1800560f8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e461`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e461`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e286`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e286`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e495`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e616`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e495`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e616`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e2d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e2d3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e727`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e756`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e7ae`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e727`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e756`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000e7ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e4bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e4bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5cd`

## string_xrefs

- `0x18000e400`: `BfeNotifyEntryCreate`
- `0x18000e39c`: `WfpMidlObjectCopy`
- `0x18000e3da`: `BfeNotifyCopy`

## pseudocode

```c
__int64 __fastcall BfeNotifyOneWay(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  LONG LockCount; // r12d
  struct _RTL_CRITICAL_SECTION *v9; // rax
  __int64 v10; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // r13
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  void *v17; // r14
  __int64 v18; // r8
  LPCRITICAL_SECTION *SpinCount; // rcx
  __int64 v20; // r8
  DWORD LastError; // eax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  LONG *OwningThread; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // [rsp+30h] [rbp-39h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+38h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-29h] BYREF
  struct _RTL_CRITICAL_SECTION *v33; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v34[16]; // [rsp+50h] [rbp-19h] BYREF
  const char *v35; // [rsp+60h] [rbp-9h]
  __int64 v36; // [rsp+68h] [rbp-1h]
  unsigned int *v37; // [rsp+70h] [rbp+7h]
  __int64 v38; // [rsp+78h] [rbp+Fh]

  v2 = 0;
  v33 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[1].OwningThread) >= lpCriticalSection[1].RecursionCount )
  {
    BfeNotifyDropped(lpCriticalSection);
    v12 = WfpReportSysErrorAsWinError(v28, "BfeNotifyOneWay", 2150760473LL);
LABEL_48:
    LeaveCriticalSection(lpCriticalSection);
    if ( v12 )
    {
      if ( v2 )
        WfpMemFree(&v2->OwningThread);
      if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v25, v24, v26) )
      {
        WfpMemFree25B(&v33);
      }
      else
      {
        if ( gWfpTrackHeapBytes && v2 )
          _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v2));
        HeapFree(gWfpHeap, 0, v2);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v20, 0, (__int64)"BfeNotifyOneWay", v12);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v30 = v12;
        v37 = &v30;
        v35 = "BfeNotifyOneWay";
        v36 = 16;
        v38 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v20,
          3,
          (__int64)v34);
      }
    }
    return v12;
  }
  LockCount = lpCriticalSection[1].LockCount;
  v31 = 0;
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v6, v5, v7) )
  {
    v11 = v31;
    v12 = WfpMemAlloc25B(0x18u);
  }
  else
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(gWfpHeap, 8u, 0x18u);
    v31 = v9;
    v11 = v9;
    if ( v9 )
    {
      v12 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v9));
    }
    else
    {
      v29 = WfpReportSysErrorAsNtStatus(v10, "HeapAlloc", 3221225495LL);
      v12 = v29;
      if ( v29 )
        WfpReportError(v29, "WfpMemAlloc");
    }
  }
  if ( v12 )
  {
LABEL_19:
    if ( v11 )
      WfpMemFree(&v11->OwningThread);
    WfpMemFree(&v31);
    WfpReportError(v12, "BfeNotifyEntryCreate");
    goto LABEL_48;
  }
  lpMem = 0;
  v30 = 0;
  v11->OwningThread = 0;
  v13 = WfpMidlObjectEncode(
          (void (__fastcall *)(handle_t, _QWORD *))&BFE_NOTIFY_MARSHAL_Encode,
          a2,
          &lpMem,
          (char *)&v30);
  v17 = lpMem;
  v12 = v13;
  if ( !v13 )
    v12 = WfpMidlObjectDecode(
            (void (__fastcall *)(handle_t, _QWORD *))&BFE_NOTIFY_MARSHAL_Decode,
            (char *)lpMem,
            v30,
            &v11->OwningThread);
  lpMem = v17;
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v15, v14, v16) )
  {
    WfpMemFree25B(&lpMem);
  }
  else
  {
    if ( gWfpTrackHeapBytes && v17 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v17));
    HeapFree(gWfpHeap, 0, v17);
  }
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v18, 0, (__int64)"WfpMidlObjectCopy", v12);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v30 = v12;
      v37 = &v30;
      v35 = "WfpMidlObjectCopy";
      v36 = 18;
      v38 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        v18,
        3,
        (__int64)v34);
    }
    WfpReportError(v12, "BfeNotifyCopy");
    goto LABEL_19;
  }
  OwningThread = (LONG *)v11->OwningThread;
  v2 = v11;
  v33 = v11;
  *OwningThread = LockCount;
  if ( !HIDWORD(lpCriticalSection[2].DebugInfo) )
  {
    if ( !SetEvent(lpCriticalSection[5].OwningThread) )
    {
      LastError = GetLastError();
      LODWORD(v12) = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v23, 0, (__int64)"SetEvent", LastError);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v30 = v12;
        v37 = &v30;
        v35 = "SetEvent";
        v36 = 9;
        v38 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v23,
          3,
          (__int64)v34);
      }
      if ( (int)v12 > 0 )
        LODWORD(v12) = (unsigned __int16)v12 | 0x80070000;
      v12 = (int)v12;
      goto LABEL_48;
    }
    HIDWORD(lpCriticalSection[2].DebugInfo) = 1;
  }
  SpinCount = (LPCRITICAL_SECTION *)lpCriticalSection[1].SpinCount;
  if ( *SpinCount != (LPCRITICAL_SECTION)&lpCriticalSection[1].LockSemaphore )
    __fastfail(3u);
  *(_QWORD *)&v11->LockCount = SpinCount;
  v11->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&lpCriticalSection[1].LockSemaphore;
  *SpinCount = v11;
  lpCriticalSection[1].SpinCount = (ULONG_PTR)v11;
  ++LODWORD(lpCriticalSection[1].OwningThread);
  ++lpCriticalSection[1].LockCount;
  LeaveCriticalSection(lpCriticalSection);
  return v12;
}

```

## disassembly

```asm
0x18000e250  mov     [rsp-8+arg_10], rbx
0x18000e255  push    rbp
0x18000e256  push    rsi
0x18000e257  push    rdi
0x18000e258  push    r12
0x18000e25a  push    r13
0x18000e25c  push    r14
0x18000e25e  push    r15
0x18000e260  lea     rbp, [rsp-27h]
0x18000e265  sub     rsp, 90h
0x18000e26c  mov     rax, cs:__security_cookie
0x18000e273  xor     rax, rsp
0x18000e276  mov     [rbp+57h+var_40], rax
0x18000e27a  xor     esi, esi
0x18000e27c  mov     r14, rdx
0x18000e27f  mov     [rbp+57h+var_78], rsi
0x18000e283  mov     rdi, rcx
0x18000e286  call    cs:__imp_EnterCriticalSection
0x18000e28d  nop     dword ptr [rax+rax+00h]
0x18000e292  mov     eax, [rdi+34h]
0x18000e295  lea     r12, WPP_GLOBAL_Control
0x18000e29c  lea     r13, aBfenotifyonewa; "BfeNotifyOneWay"
0x18000e2a3  cmp     [rdi+38h], eax
0x18000e2a6  jnb     loc_18000E6E6
0x18000e2ac  mov     r12d, [rdi+30h]
0x18000e2b0  mov     [rbp+57h+var_88], rsi
0x18000e2b4  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000e2b9  mov     edx, 8; dwFlags
0x18000e2be  test    eax, eax
0x18000e2c0  jnz     loc_18000E432
0x18000e2c6  mov     rcx, cs:gWfpHeap; hHeap
0x18000e2cd  mov     r8d, 18h; dwBytes
0x18000e2d3  call    cs:__imp_HeapAlloc
0x18000e2da  nop     dword ptr [rax+rax+00h]
0x18000e2df  mov     [rbp+57h+var_88], rax
0x18000e2e3  mov     r13, rax
0x18000e2e6  test    rax, rax
0x18000e2e9  jz      loc_18000E770
0x18000e2ef  xor     ebx, ebx
0x18000e2f1  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000e2f7  jnz     loc_18000E7A2
0x18000e2fd  test    rbx, rbx
0x18000e300  jnz     loc_18000E7C6
0x18000e306  xor     eax, eax
0x18000e308  lea     r9, [rbp+57h+var_90]
0x18000e30c  lea     r8, [rbp+57h+lpMem]
0x18000e310  mov     [rbp+57h+lpMem], rax
0x18000e314  mov     rdx, r14
0x18000e317  mov     [rbp+57h+var_90], eax
0x18000e31a  lea     rcx, BFE_NOTIFY_MARSHAL_Encode
0x18000e321  mov     [r13+10h], rax
0x18000e325  call    WfpMidlObjectEncode
0x18000e32a  mov     r14, [rbp+57h+lpMem]
0x18000e32e  mov     rbx, rax
0x18000e331  test    rax, rax
0x18000e334  jnz     short loc_18000E350
0x18000e336  mov     r8d, [rbp+57h+var_90]
0x18000e33a  lea     r9, [r13+10h]
0x18000e33e  mov     rdx, r14
0x18000e341  lea     rcx, BFE_NOTIFY_MARSHAL_Decode
0x18000e348  call    WfpMidlObjectDecode
0x18000e34d  mov     rbx, rax
0x18000e350  mov     [rbp+57h+lpMem], r14
0x18000e354  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000e359  test    eax, eax
0x18000e35b  jnz     loc_18000E44C
0x18000e361  cmp     cs:gWfpTrackHeapBytes, esi
0x18000e367  jnz     loc_18000E741
0x18000e36d  mov     rcx, cs:gWfpHeap; hHeap
0x18000e374  mov     r8, r14; lpMem
0x18000e377  xor     edx, edx; dwFlags
0x18000e379  call    cs:__imp_HeapFree
0x18000e380  nop     dword ptr [rax+rax+00h]
0x18000e385  test    rbx, rbx
0x18000e388  jz      loc_18000E679
0x18000e38e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e395  lea     r12, WPP_GLOBAL_Control
0x18000e39c  lea     r14, aWfpmidlobjectc; "WfpMidlObjectCopy"
0x18000e3a3  cmp     rcx, r12
0x18000e3a6  jz      short loc_18000E3CE
0x18000e3a8  cmp     byte ptr [rcx+19h], 2
0x18000e3ac  jb      short loc_18000E3CE
0x18000e3ae  test    byte ptr [rcx+1Ch], 1
0x18000e3b2  jz      short loc_18000E3CE
0x18000e3b4  mov     rcx, [rcx+10h]
0x18000e3b8  mov     edx, 1Ah
0x18000e3bd  mov     [rsp+0C0h+var_98], ebx
0x18000e3c1  xor     r9d, r9d
0x18000e3c4  mov     [rsp+0C0h+var_A0], r14
0x18000e3c9  call    WPP_SF_Ssd
0x18000e3ce  cmp     cs:gWfpLogUserModeErrors, esi
0x18000e3d4  jnz     loc_18000E57A
0x18000e3da  lea     rdx, aBfenotifycopy; "BfeNotifyCopy"
0x18000e3e1  mov     rcx, rbx
0x18000e3e4  call    WfpReportError
0x18000e3e9  test    r13, r13
0x18000e3ec  jz      short loc_18000E3F7
0x18000e3ee  lea     rcx, [r13+10h]
0x18000e3f2  call    WfpMemFree
0x18000e3f7  lea     rcx, [rbp+57h+var_88]
0x18000e3fb  call    WfpMemFree
0x18000e400  lea     rdx, aBfenotifyentry; "BfeNotifyEntryCreate"
0x18000e407  mov     rcx, rbx
0x18000e40a  call    WfpReportError
0x18000e40f  test    rbx, rbx
0x18000e412  jnz     loc_18000E60C
0x18000e418  cmp     dword ptr [rdi+54h], 0
0x18000e41c  jz      short loc_18000E45A
0x18000e41e  mov     rcx, [rdi+48h]
0x18000e422  lea     rax, [rdi+40h]
0x18000e426  cmp     [rcx], rax
0x18000e429  jz      short loc_18000E47E
0x18000e42b  mov     ecx, 3
0x18000e430  int     29h; Win8: RtlFailFast(ecx)
0x18000e432  lea     r8, [rbp+57h+var_88]
0x18000e436  mov     ecx, 18h; dwBytes
0x18000e43b  call    WfpMemAlloc25B
0x18000e440  mov     r13, [rbp+57h+var_88]
0x18000e444  mov     rbx, rax
0x18000e447  jmp     loc_18000E2FD
0x18000e44c  lea     rcx, [rbp+57h+lpMem]
0x18000e450  call    WfpMemFree25B
0x18000e455  jmp     loc_18000E385
0x18000e45a  mov     rcx, [rdi+0D8h]; hEvent
0x18000e461  call    cs:__imp_SetEvent
0x18000e468  nop     dword ptr [rax+rax+00h]
0x18000e46d  test    eax, eax
0x18000e46f  jz      loc_18000E5CD
0x18000e475  mov     dword ptr [rdi+54h], 1
0x18000e47c  jmp     short loc_18000E41E
0x18000e47e  mov     [rsi+8], rcx
0x18000e482  mov     [rsi], rax
0x18000e485  mov     [rcx], rsi
0x18000e488  mov     rcx, rdi; lpCriticalSection
0x18000e48b  mov     [rax+8], rsi
0x18000e48f  inc     dword ptr [rdi+38h]
0x18000e492  inc     dword ptr [rdi+30h]
0x18000e495  call    cs:__imp_LeaveCriticalSection
0x18000e49c  nop     dword ptr [rax+rax+00h]
0x18000e4a1  jmp     short loc_18000E503
0x18000e4a3  cmp     cs:gWfpTrackHeapBytes, 0
0x18000e4aa  jnz     loc_18000E712
0x18000e4b0  mov     rcx, cs:gWfpHeap; hHeap
0x18000e4b7  mov     r8, rsi; lpMem
0x18000e4ba  xor     edx, edx; dwFlags
0x18000e4bc  call    cs:__imp_HeapFree
0x18000e4c3  nop     dword ptr [rax+rax+00h]
0x18000e4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4cf  cmp     rcx, r12
0x18000e4d2  jz      short loc_18000E4FA
0x18000e4d4  cmp     byte ptr [rcx+19h], 2
0x18000e4d8  jb      short loc_18000E4FA
0x18000e4da  test    byte ptr [rcx+1Ch], 1
0x18000e4de  jz      short loc_18000E4FA
0x18000e4e0  mov     rcx, [rcx+10h]
0x18000e4e4  mov     edx, 1Ah
0x18000e4e9  mov     [rsp+0C0h+var_98], ebx
0x18000e4ed  xor     r9d, r9d
0x18000e4f0  mov     [rsp+0C0h+var_A0], r13
0x18000e4f5  call    WPP_SF_Ssd
0x18000e4fa  cmp     cs:gWfpLogUserModeErrors, 0
0x18000e501  jnz     short loc_18000E52E
0x18000e503  mov     rax, rbx
0x18000e506  mov     rcx, [rbp+57h+var_40]
0x18000e50a  xor     rcx, rsp; StackCookie
0x18000e50d  call    __security_check_cookie
0x18000e512  mov     rbx, [rsp+0C0h+arg_10]
0x18000e51a  add     rsp, 90h
0x18000e521  pop     r15
0x18000e523  pop     r14
0x18000e525  pop     r13
0x18000e527  pop     r12
0x18000e529  pop     rdi
0x18000e52a  pop     rsi
0x18000e52b  pop     rbp
0x18000e52c  retn
0x18000e52e  test    cs:byte_1800F6115, 1
0x18000e535  jz      short loc_18000E503
0x18000e537  lea     rax, [rbp+57h+var_90]
0x18000e53b  mov     [rbp+57h+var_90], ebx
0x18000e53e  mov     [rbp+57h+var_50], rax
0x18000e542  lea     rdx, WFP_USERMODE_ERROR
0x18000e549  lea     rax, [rbp+57h+var_70]
0x18000e54d  mov     [rbp+57h+var_60], r13
0x18000e551  mov     r9d, 3
0x18000e557  mov     [rsp+0C0h+var_A0], rax
0x18000e55c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000e563  mov     [rbp+57h+var_58], 10h
0x18000e56b  mov     [rbp+57h+var_48], 4
0x18000e573  call    McGenEventWrite_EtwEventWriteTransfer
0x18000e578  jmp     short loc_18000E503
0x18000e57a  test    cs:byte_1800F6115, 1
0x18000e581  jz      loc_18000E3DA
0x18000e587  lea     rax, [rbp+57h+var_90]
0x18000e58b  mov     [rbp+57h+var_90], ebx
0x18000e58e  mov     [rbp+57h+var_50], rax
0x18000e592  lea     rdx, WFP_USERMODE_ERROR
0x18000e599  lea     rax, [rbp+57h+var_70]
0x18000e59d  mov     [rbp+57h+var_60], r14
0x18000e5a1  mov     r9d, 3
0x18000e5a7  mov     [rsp+0C0h+var_A0], rax
0x18000e5ac  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000e5b3  mov     [rbp+57h+var_58], 12h
0x18000e5bb  mov     [rbp+57h+var_48], 4
0x18000e5c3  call    McGenEventWrite_EtwEventWriteTransfer
0x18000e5c8  jmp     loc_18000E3DA
0x18000e5cd  call    cs:__imp_GetLastError
0x18000e5d4  nop     dword ptr [rax+rax+00h]
0x18000e5d9  mov     ebx, eax
0x18000e5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5e2  lea     r14, aSetevent; "SetEvent"
0x18000e5e9  cmp     rcx, r12
0x18000e5ec  jz      short loc_18000E5F4
0x18000e5ee  cmp     byte ptr [rcx+19h], 2
0x18000e5f2  jnb     short loc_18000E654
0x18000e5f4  cmp     cs:gWfpLogUserModeErrors, 0
0x18000e5fb  jnz     loc_18000E693
0x18000e601  test    ebx, ebx
0x18000e603  jg      loc_18000E704
0x18000e609  movsxd  rbx, ebx
0x18000e60c  lea     r13, aBfenotifyonewa; "BfeNotifyOneWay"
0x18000e613  mov     rcx, rdi; lpCriticalSection
0x18000e616  call    cs:__imp_LeaveCriticalSection
0x18000e61d  nop     dword ptr [rax+rax+00h]
0x18000e622  test    rbx, rbx
0x18000e625  jz      loc_18000E503
0x18000e62b  test    rsi, rsi
0x18000e62e  jz      short loc_18000E639
0x18000e630  lea     rcx, [rsi+10h]
0x18000e634  call    WfpMemFree
0x18000e639  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000e63e  test    eax, eax
0x18000e640  jz      loc_18000E4A3
0x18000e646  lea     rcx, [rbp+57h+var_78]
0x18000e64a  call    WfpMemFree25B
0x18000e64f  jmp     loc_18000E4C8
0x18000e654  test    byte ptr [rcx+1Ch], 1
0x18000e658  jz      short loc_18000E5F4
0x18000e65a  mov     rcx, [rcx+10h]
0x18000e65e  mov     edx, 17h
0x18000e663  mov     [rsp+0C0h+var_98], ebx
0x18000e667  xor     r9d, r9d
0x18000e66a  mov     [rsp+0C0h+var_A0], r14
0x18000e66f  call    WPP_SF_SsD
0x18000e674  jmp     loc_18000E5F4
0x18000e679  mov     rax, [r13+10h]
0x18000e67d  mov     rsi, r13
0x18000e680  mov     [rbp+57h+var_78], r13
0x18000e684  mov     [rax], r12d
0x18000e687  lea     r12, WPP_GLOBAL_Control
0x18000e68e  jmp     loc_18000E418
0x18000e693  test    cs:byte_1800F6115, 1
0x18000e69a  jz      loc_18000E601
0x18000e6a0  lea     rax, [rbp+57h+var_90]
0x18000e6a4  mov     [rbp+57h+var_90], ebx
0x18000e6a7  mov     [rbp+57h+var_50], rax
0x18000e6ab  lea     rdx, WFP_USERMODE_ERROR
0x18000e6b2  lea     rax, [rbp+57h+var_70]
0x18000e6b6  mov     [rbp+57h+var_60], r14
0x18000e6ba  mov     r9d, 3
0x18000e6c0  mov     [rsp+0C0h+var_A0], rax
0x18000e6c5  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000e6cc  mov     [rbp+57h+var_58], 9
0x18000e6d4  mov     [rbp+57h+var_48], 4
0x18000e6dc  call    McGenEventWrite_EtwEventWriteTransfer
0x18000e6e1  jmp     loc_18000E601
0x18000e6e6  mov     rcx, rdi
0x18000e6e9  call    BfeNotifyDropped
0x18000e6ee  mov     r8d, 80320019h
0x18000e6f4  mov     rdx, r13
0x18000e6f7  call    WfpReportSysErrorAsWinError
0x18000e6fc  mov     rbx, rax
0x18000e6ff  jmp     loc_18000E613
0x18000e704  movzx   ebx, bx
0x18000e707  or      ebx, 80070000h
0x18000e70d  jmp     loc_18000E609
0x18000e712  test    rsi, rsi
0x18000e715  jz      loc_18000E4B0
0x18000e71b  mov     rcx, cs:gWfpHeap; hHeap
0x18000e722  mov     r8, rsi; lpMem
0x18000e725  xor     edx, edx; dwFlags
0x18000e727  call    cs:__imp_HeapSize
0x18000e72e  nop     dword ptr [rax+rax+00h]
0x18000e733  neg     eax
0x18000e735  lock add cs:gWfpHeapBytesAllocated, eax
0x18000e73c  jmp     loc_18000E4B0
0x18000e741  test    r14, r14
0x18000e744  jz      loc_18000E36D
0x18000e74a  mov     rcx, cs:gWfpHeap; hHeap
0x18000e751  mov     r8, r14; lpMem
0x18000e754  xor     edx, edx; dwFlags
0x18000e756  call    cs:__imp_HeapSize
0x18000e75d  nop     dword ptr [rax+rax+00h]
0x18000e762  neg     eax
0x18000e764  lock add cs:gWfpHeapBytesAllocated, eax
0x18000e76b  jmp     loc_18000E36D
0x18000e770  mov     r8d, 0C0000017h
0x18000e776  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000e77d  call    WfpReportSysErrorAsNtStatus
0x18000e782  mov     rbx, rax
  ... truncated ...
```
