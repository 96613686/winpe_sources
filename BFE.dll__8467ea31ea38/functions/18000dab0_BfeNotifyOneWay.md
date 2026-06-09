# BfeNotifyOneWay

- ea: `0x18000dab0`
- end: `0x18000dfec`
- name: `BfeNotifyOneWay`
- size: `1340`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `11`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180011290`
- `0x180025234`
- `0x180026450`
- `0x18002a400`
- `0x18002a720`
- `0x18003ceb8`
- `0x180049908`
- `0x180065454`
- `0x18006d840`
- `0x18006dde8`
- `0x180071220`

## callees

- `0x18000dab0`
- `0x18000e000`
- `0x18000e3f0`
- `0x18000e4e0`
- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x180012950`
- `0x180012b54`
- `0x180018b74`
- `0x18002a9f8`
- `0x18004e230`
- `0x1800540ec`
- `0x1800542bc`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dcaf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dcaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dae6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dae6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dcdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dcdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000de4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000db2d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000df53`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000df7c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000dfce`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000df53`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000df7c`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000dfce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbcd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcfe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dbcd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dcfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de08`

## string_xrefs

- `0x18000dc4e`: `BfeNotifyEntryCreate`
- `0x18000dbea`: `WfpMidlObjectCopy`
- `0x18000dc28`: `BfeNotifyCopy`

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
  int v18; // r8d
  LPCRITICAL_SECTION *SpinCount; // rcx
  int v20; // r8d
  DWORD LastError; // eax
  int v23; // r8d
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
      if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
      {
        v30 = v12;
        v37 = &v30;
        v35 = "BfeNotifyOneWay";
        v36 = 16;
        v38 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
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
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v30 = v12;
      v37 = &v30;
      v35 = "WfpMidlObjectCopy";
      v36 = 18;
      v38 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
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
      if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
      {
        v30 = v12;
        v37 = &v30;
        v35 = "SetEvent";
        v36 = 9;
        v38 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
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
0x18000dab0  mov     [rsp-8+arg_10], rbx
0x18000dab5  push    rbp
0x18000dab6  push    rsi
0x18000dab7  push    rdi
0x18000dab8  push    r12
0x18000daba  push    r13
0x18000dabc  push    r14
0x18000dabe  push    r15
0x18000dac0  lea     rbp, [rsp-27h]
0x18000dac5  sub     rsp, 90h
0x18000dacc  mov     rax, cs:__security_cookie
0x18000dad3  xor     rax, rsp
0x18000dad6  mov     [rbp+57h+var_40], rax
0x18000dada  xor     esi, esi
0x18000dadc  mov     r14, rdx
0x18000dadf  mov     [rbp+57h+var_78], rsi
0x18000dae3  mov     rdi, rcx
0x18000dae6  call    cs:__imp_EnterCriticalSection
0x18000daec  mov     eax, [rdi+34h]
0x18000daef  lea     r12, WPP_GLOBAL_Control
0x18000daf6  lea     r13, aBfenotifyonewa; "BfeNotifyOneWay"
0x18000dafd  cmp     [rdi+38h], eax
0x18000db00  jnb     loc_18000DF12
0x18000db06  mov     r12d, [rdi+30h]
0x18000db0a  mov     [rbp+57h+var_88], rsi
0x18000db0e  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000db13  mov     edx, 8; dwFlags
0x18000db18  test    eax, eax
0x18000db1a  jnz     loc_18000DC80
0x18000db20  mov     rcx, cs:gWfpHeap; hHeap
0x18000db27  mov     r8d, 18h; dwBytes
0x18000db2d  call    cs:__imp_HeapAlloc
0x18000db33  mov     [rbp+57h+var_88], rax
0x18000db37  mov     r13, rax
0x18000db3a  test    rax, rax
0x18000db3d  jz      loc_18000DF90
0x18000db43  xor     ebx, ebx
0x18000db45  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000db4b  jnz     loc_18000DFC2
0x18000db51  test    rbx, rbx
0x18000db54  jnz     loc_18000DFE0
0x18000db5a  xor     eax, eax
0x18000db5c  lea     r9, [rbp+57h+var_90]
0x18000db60  lea     r8, [rbp+57h+lpMem]
0x18000db64  mov     [rbp+57h+lpMem], rax
0x18000db68  mov     rdx, r14
0x18000db6b  mov     [rbp+57h+var_90], eax
0x18000db6e  lea     rcx, BFE_NOTIFY_MARSHAL_Encode
0x18000db75  mov     [r13+10h], rax
0x18000db79  call    WfpMidlObjectEncode
0x18000db7e  mov     r14, [rbp+57h+lpMem]
0x18000db82  mov     rbx, rax
0x18000db85  test    rax, rax
0x18000db88  jnz     short loc_18000DBA4
0x18000db8a  mov     r8d, [rbp+57h+var_90]
0x18000db8e  lea     r9, [r13+10h]
0x18000db92  mov     rdx, r14
0x18000db95  lea     rcx, BFE_NOTIFY_MARSHAL_Decode
0x18000db9c  call    WfpMidlObjectDecode
0x18000dba1  mov     rbx, rax
0x18000dba4  mov     [rbp+57h+lpMem], r14
0x18000dba8  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000dbad  test    eax, eax
0x18000dbaf  jnz     loc_18000DC9A
0x18000dbb5  cmp     cs:gWfpTrackHeapBytes, esi
0x18000dbbb  jnz     loc_18000DF67
0x18000dbc1  mov     rcx, cs:gWfpHeap; hHeap
0x18000dbc8  mov     r8, r14; lpMem
0x18000dbcb  xor     edx, edx; dwFlags
0x18000dbcd  call    cs:__imp_HeapFree
0x18000dbd3  test    rbx, rbx
0x18000dbd6  jz      loc_18000DEA5
0x18000dbdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbe3  lea     r12, WPP_GLOBAL_Control
0x18000dbea  lea     r14, aWfpmidlobjectc; "WfpMidlObjectCopy"
0x18000dbf1  cmp     rcx, r12
0x18000dbf4  jz      short loc_18000DC1C
0x18000dbf6  cmp     byte ptr [rcx+19h], 2
0x18000dbfa  jb      short loc_18000DC1C
0x18000dbfc  test    byte ptr [rcx+1Ch], 1
0x18000dc00  jz      short loc_18000DC1C
0x18000dc02  mov     rcx, [rcx+10h]
0x18000dc06  mov     edx, 1Ah
0x18000dc0b  mov     [rsp+0C0h+var_98], ebx
0x18000dc0f  xor     r9d, r9d
0x18000dc12  mov     [rsp+0C0h+var_A0], r14
0x18000dc17  call    WPP_SF_Ssd
0x18000dc1c  cmp     cs:gWfpLogUserModeErrors, esi
0x18000dc22  jnz     loc_18000DDB5
0x18000dc28  lea     rdx, aBfenotifycopy; "BfeNotifyCopy"
0x18000dc2f  mov     rcx, rbx
0x18000dc32  call    WfpReportError
0x18000dc37  test    r13, r13
0x18000dc3a  jz      short loc_18000DC45
0x18000dc3c  lea     rcx, [r13+10h]
0x18000dc40  call    WfpMemFree
0x18000dc45  lea     rcx, [rbp+57h+var_88]
0x18000dc49  call    WfpMemFree
0x18000dc4e  lea     rdx, aBfenotifyentry; "BfeNotifyEntryCreate"
0x18000dc55  mov     rcx, rbx
0x18000dc58  call    WfpReportError
0x18000dc5d  test    rbx, rbx
0x18000dc60  jnz     loc_18000DE41
0x18000dc66  cmp     dword ptr [rdi+54h], 0
0x18000dc6a  jz      short loc_18000DCA8
0x18000dc6c  mov     rcx, [rdi+48h]
0x18000dc70  lea     rax, [rdi+40h]
0x18000dc74  cmp     [rcx], rax
0x18000dc77  jz      short loc_18000DCC6
0x18000dc79  mov     ecx, 3
0x18000dc7e  int     29h; Win8: RtlFailFast(ecx)
0x18000dc80  lea     r8, [rbp+57h+var_88]
0x18000dc84  mov     ecx, 18h; dwBytes
0x18000dc89  call    WfpMemAlloc25B
0x18000dc8e  mov     r13, [rbp+57h+var_88]
0x18000dc92  mov     rbx, rax
0x18000dc95  jmp     loc_18000DB51
0x18000dc9a  lea     rcx, [rbp+57h+lpMem]
0x18000dc9e  call    WfpMemFree25B
0x18000dca3  jmp     loc_18000DBD3
0x18000dca8  mov     rcx, [rdi+0D8h]; hEvent
0x18000dcaf  call    cs:__imp_SetEvent
0x18000dcb5  test    eax, eax
0x18000dcb7  jz      loc_18000DE08
0x18000dcbd  mov     dword ptr [rdi+54h], 1
0x18000dcc4  jmp     short loc_18000DC6C
0x18000dcc6  mov     [rsi+8], rcx
0x18000dcca  mov     [rsi], rax
0x18000dccd  mov     [rcx], rsi
0x18000dcd0  mov     rcx, rdi; lpCriticalSection
0x18000dcd3  mov     [rax+8], rsi
0x18000dcd7  inc     dword ptr [rdi+38h]
0x18000dcda  inc     dword ptr [rdi+30h]
0x18000dcdd  call    cs:__imp_LeaveCriticalSection
0x18000dce3  jmp     short loc_18000DD3F
0x18000dce5  cmp     cs:gWfpTrackHeapBytes, 0
0x18000dcec  jnz     loc_18000DF3E
0x18000dcf2  mov     rcx, cs:gWfpHeap; hHeap
0x18000dcf9  mov     r8, rsi; lpMem
0x18000dcfc  xor     edx, edx; dwFlags
0x18000dcfe  call    cs:__imp_HeapFree
0x18000dd04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd0b  cmp     rcx, r12
0x18000dd0e  jz      short loc_18000DD36
0x18000dd10  cmp     byte ptr [rcx+19h], 2
0x18000dd14  jb      short loc_18000DD36
0x18000dd16  test    byte ptr [rcx+1Ch], 1
0x18000dd1a  jz      short loc_18000DD36
0x18000dd1c  mov     rcx, [rcx+10h]
0x18000dd20  mov     edx, 1Ah
0x18000dd25  mov     [rsp+0C0h+var_98], ebx
0x18000dd29  xor     r9d, r9d
0x18000dd2c  mov     [rsp+0C0h+var_A0], r13
0x18000dd31  call    WPP_SF_Ssd
0x18000dd36  cmp     cs:gWfpLogUserModeErrors, 0
0x18000dd3d  jnz     short loc_18000DD69
0x18000dd3f  mov     rax, rbx
0x18000dd42  mov     rcx, [rbp+57h+var_40]
0x18000dd46  xor     rcx, rsp; StackCookie
0x18000dd49  call    __security_check_cookie
0x18000dd4e  mov     rbx, [rsp+0C0h+arg_10]
0x18000dd56  add     rsp, 90h
0x18000dd5d  pop     r15
0x18000dd5f  pop     r14
0x18000dd61  pop     r13
0x18000dd63  pop     r12
0x18000dd65  pop     rdi
0x18000dd66  pop     rsi
0x18000dd67  pop     rbp
0x18000dd68  retn
0x18000dd69  test    cs:byte_1800F30F5, 1
0x18000dd70  jz      short loc_18000DD3F
0x18000dd72  lea     rax, [rbp+57h+var_90]
0x18000dd76  mov     [rbp+57h+var_90], ebx
0x18000dd79  mov     [rbp+57h+var_50], rax
0x18000dd7d  lea     rdx, WFP_USERMODE_ERROR
0x18000dd84  lea     rax, [rbp+57h+var_70]
0x18000dd88  mov     [rbp+57h+var_60], r13
0x18000dd8c  mov     r9d, 3
0x18000dd92  mov     [rsp+0C0h+var_A0], rax
0x18000dd97  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000dd9e  mov     [rbp+57h+var_58], 10h
0x18000dda6  mov     [rbp+57h+var_48], 4
0x18000ddae  call    McGenEventWrite_EtwEventWriteTransfer
0x18000ddb3  jmp     short loc_18000DD3F
0x18000ddb5  test    cs:byte_1800F30F5, 1
0x18000ddbc  jz      loc_18000DC28
0x18000ddc2  lea     rax, [rbp+57h+var_90]
0x18000ddc6  mov     [rbp+57h+var_90], ebx
0x18000ddc9  mov     [rbp+57h+var_50], rax
0x18000ddcd  lea     rdx, WFP_USERMODE_ERROR
0x18000ddd4  lea     rax, [rbp+57h+var_70]
0x18000ddd8  mov     [rbp+57h+var_60], r14
0x18000dddc  mov     r9d, 3
0x18000dde2  mov     [rsp+0C0h+var_A0], rax
0x18000dde7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000ddee  mov     [rbp+57h+var_58], 12h
0x18000ddf6  mov     [rbp+57h+var_48], 4
0x18000ddfe  call    McGenEventWrite_EtwEventWriteTransfer
0x18000de03  jmp     loc_18000DC28
0x18000de08  call    cs:__imp_GetLastError
0x18000de0e  mov     ebx, eax
0x18000de10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de17  lea     r14, aSetevent; "SetEvent"
0x18000de1e  cmp     rcx, r12
0x18000de21  jz      short loc_18000DE29
0x18000de23  cmp     byte ptr [rcx+19h], 2
0x18000de27  jnb     short loc_18000DE83
0x18000de29  cmp     cs:gWfpLogUserModeErrors, 0
0x18000de30  jnz     loc_18000DEBF
0x18000de36  test    ebx, ebx
0x18000de38  jg      loc_18000DF30
0x18000de3e  movsxd  rbx, ebx
0x18000de41  lea     r13, aBfenotifyonewa; "BfeNotifyOneWay"
0x18000de48  mov     rcx, rdi; lpCriticalSection
0x18000de4b  call    cs:__imp_LeaveCriticalSection
0x18000de51  test    rbx, rbx
0x18000de54  jz      loc_18000DD3F
0x18000de5a  test    rsi, rsi
0x18000de5d  jz      short loc_18000DE68
0x18000de5f  lea     rcx, [rsi+10h]
0x18000de63  call    WfpMemFree
0x18000de68  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000de6d  test    eax, eax
0x18000de6f  jz      loc_18000DCE5
0x18000de75  lea     rcx, [rbp+57h+var_78]
0x18000de79  call    WfpMemFree25B
0x18000de7e  jmp     loc_18000DD04
0x18000de83  test    byte ptr [rcx+1Ch], 1
0x18000de87  jz      short loc_18000DE29
0x18000de89  mov     rcx, [rcx+10h]
0x18000de8d  mov     edx, 17h
0x18000de92  mov     [rsp+0C0h+var_98], ebx
0x18000de96  xor     r9d, r9d
0x18000de99  mov     [rsp+0C0h+var_A0], r14
0x18000de9e  call    WPP_SF_SsD
0x18000dea3  jmp     short loc_18000DE29
0x18000dea5  mov     rax, [r13+10h]
0x18000dea9  mov     rsi, r13
0x18000deac  mov     [rbp+57h+var_78], r13
0x18000deb0  mov     [rax], r12d
0x18000deb3  lea     r12, WPP_GLOBAL_Control
0x18000deba  jmp     loc_18000DC66
0x18000debf  test    cs:byte_1800F30F5, 1
0x18000dec6  jz      loc_18000DE36
0x18000decc  lea     rax, [rbp+57h+var_90]
0x18000ded0  mov     [rbp+57h+var_90], ebx
0x18000ded3  mov     [rbp+57h+var_50], rax
0x18000ded7  lea     rdx, WFP_USERMODE_ERROR
0x18000dede  lea     rax, [rbp+57h+var_70]
0x18000dee2  mov     [rbp+57h+var_60], r14
0x18000dee6  mov     r9d, 3
0x18000deec  mov     [rsp+0C0h+var_A0], rax
0x18000def1  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18000def8  mov     [rbp+57h+var_58], 9
0x18000df00  mov     [rbp+57h+var_48], 4
0x18000df08  call    McGenEventWrite_EtwEventWriteTransfer
0x18000df0d  jmp     loc_18000DE36
0x18000df12  mov     rcx, rdi
0x18000df15  call    BfeNotifyDropped
0x18000df1a  mov     r8d, 80320019h
0x18000df20  mov     rdx, r13
0x18000df23  call    WfpReportSysErrorAsWinError
0x18000df28  mov     rbx, rax
0x18000df2b  jmp     loc_18000DE48
0x18000df30  movzx   ebx, bx
0x18000df33  or      ebx, 80070000h
0x18000df39  jmp     loc_18000DE3E
0x18000df3e  test    rsi, rsi
0x18000df41  jz      loc_18000DCF2
0x18000df47  mov     rcx, cs:gWfpHeap; hHeap
0x18000df4e  mov     r8, rsi; lpMem
0x18000df51  xor     edx, edx; dwFlags
0x18000df53  call    cs:__imp_HeapSize
0x18000df59  neg     eax
0x18000df5b  lock add cs:gWfpHeapBytesAllocated, eax
0x18000df62  jmp     loc_18000DCF2
0x18000df67  test    r14, r14
0x18000df6a  jz      loc_18000DBC1
0x18000df70  mov     rcx, cs:gWfpHeap; hHeap
0x18000df77  mov     r8, r14; lpMem
0x18000df7a  xor     edx, edx; dwFlags
0x18000df7c  call    cs:__imp_HeapSize
0x18000df82  neg     eax
0x18000df84  lock add cs:gWfpHeapBytesAllocated, eax
0x18000df8b  jmp     loc_18000DBC1
0x18000df90  mov     r8d, 0C0000017h
0x18000df96  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000df9d  call    WfpReportSysErrorAsNtStatus
0x18000dfa2  mov     rbx, rax
0x18000dfa5  test    rax, rax
0x18000dfa8  jz      loc_18000DB51
0x18000dfae  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18000dfb5  mov     rcx, rax
0x18000dfb8  call    WfpReportError
0x18000dfbd  jmp     loc_18000DB51
0x18000dfc2  mov     rcx, cs:gWfpHeap; hHeap
0x18000dfc9  mov     r8, rax; lpMem
0x18000dfcc  xor     edx, edx; dwFlags
0x18000dfce  call    cs:__imp_HeapSize
  ... truncated ...
```
