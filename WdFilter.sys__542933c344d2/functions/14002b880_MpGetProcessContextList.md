# MpGetProcessContextList

- ea: `0x14002b880`
- end: `0x14002bdbc`
- name: `MpGetProcessContextList`
- size: `1340`
- prototype: ``
- caller_count: `8`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002b000`
- `0x14002b0b8`
- `0x14002bffc`
- `0x14002c790`
- `0x14005ad68`
- `0x14008103c`
- `0x140084ccc`
- `0x140093bf8`

## callees

- `0x1400051bc`
- `0x1400069f4`
- `0x140007030`
- `0x14000a760`
- `0x1400118d0`
- `0x14002b880`
- `0x14002bdbc`
- `0x14002be4c`
- `0x14002c948`
- `0x140030060`
- `0x1400387f0`
- `0x14003a570`
- `0x140084068`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14002b8e7`
- `ntoskrnl!KeClearEvent` at `0x14002b8e7`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002ba16`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002ba16`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002ba44`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002ba38`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002ba38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b94f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b94f`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14002bb26`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14002bbd1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14002bb26`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14002bbd1`
- `ntoskrnl!KeSetEvent` at `0x14002bb63`
- `ntoskrnl!KeSetEvent` at `0x14002bb63`
- `ntoskrnl!KeBugCheck` at `0x14002bb8e`
- `ntoskrnl!KeBugCheck` at `0x14002bb8e`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b9e7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bb9b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b9e7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bb9b`

## pseudocode

```c
__int64 __fastcall MpGetProcessContextList(_QWORD *a1, char a2)
{
  int RunningProcesses; // eax
  int v4; // edi
  _QWORD *v5; // rbx
  unsigned int i; // r15d
  NTSTATUS v8; // ecx
  LONGLONG TimeQuadPart; // rax
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  const wchar_t *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // [rsp+28h] [rbp-58h]
  PVOID P; // [rsp+48h] [rbp-38h] BYREF
  __int64 v20; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v21; // [rsp+58h] [rbp-28h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h] BYREF
  PVOID Object; // [rsp+70h] [rbp-10h] BYREF

  P = 0;
  v21 = 0;
  v23 = 0;
  v20 = 0;
  v22 = 0;
  Object = 0;
  _InterlockedIncrement((volatile signed __int32 *)MpProcessTable + 104);
  KeClearEvent((PRKEVENT)((char *)MpProcessTable + 392));
  RunningProcesses = MpGetRunningProcesses(&P, &v21);
  v4 = RunningProcesses;
  if ( RunningProcesses < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
        KeGetCurrentThread(),
        RunningProcesses);
    }
    v5 = P;
    goto LABEL_4;
  }
  v5 = P;
  for ( i = 0; ; ++i )
  {
    if ( i >= v21 )
    {
      v4 = 0;
      *a1 = v20;
      v20 = 0;
      goto LABEL_4;
    }
    if ( v5[i] )
      break;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids, i, v5[i]);
LABEL_26:
    ;
  }
  if ( Object )
  {
    ObfDereferenceObject(Object);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        goto LABEL_40;
      __debugbreak();
    }
    Object = 0;
  }
  v8 = PsLookupProcessByProcessId((HANDLE)v5[i], (PEPROCESS *)&Object);
  if ( v8 < 0 )
  {
    if ( v8 == -1073741813 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_26;
      v15 = 45;
      v17 = -1073741813;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
        goto LABEL_26;
      v15 = 44;
      v17 = v8;
    }
    _mm_lfence();
    v5 = P;
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
      KeGetCurrentThread(),
      *((_DWORD *)P + 2 * i),
      v17);
    goto LABEL_26;
  }
  _InterlockedIncrement64(&ObTotalReferences);
  TimeQuadPart = PsGetProcessCreateTimeQuadPart((PEPROCESS)Object);
  v10 = TimeQuadPart;
  if ( Object == PsInitialSystemProcess && TimeQuadPart )
    g_bSystemProcessContextCreateTimeFixed = 1;
  if ( (int)MpGetProcessContextByIdAndCreationTime(v5[i], TimeQuadPart, &v23) < 0 )
  {
    if ( !a2 )
      goto LABEL_26;
    _mm_lfence();
    v5 = P;
    v4 = MpCreateProcessContext(*((_QWORD *)P + i), v10, 0, &v23);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v16 = 46;
LABEL_64:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v16,
          WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
          KeGetCurrentThread(),
          v4);
        v5 = P;
        goto LABEL_4;
      }
      goto LABEL_4;
    }
  }
  v4 = MpAllocateProcessContextListEntry(&v22);
  if ( v4 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v13 = *(_QWORD *)(v23 + 128);
      if ( *(_WORD *)v13 )
        v14 = *(const wchar_t **)(v13 + 8);
      else
        v14 = L"(empty)";
      WPP_SF_DqSDd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v14,
        v23,
        i,
        *(_QWORD *)(v23 + 24),
        (__int64)v14,
        v5[i],
        *(_DWORD *)(v23 + 120));
    }
    v11 = v22;
    v22 = 0;
    *(_QWORD *)(v11 + 16) = v23;
    v12 = v20;
    v23 = 0;
    v20 = v11 + 8;
    *(_QWORD *)(v11 + 8) = v12;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v16 = 47;
    goto LABEL_64;
  }
LABEL_4:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)MpProcessTable + 104, 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)((char *)MpProcessTable + 392), 0, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x7072704Du);
  if ( v23 )
    MpReleaseProcessContext(v23);
  if ( v20 )
    MpReleaseProcessContextList(&v20);
  if ( v22 )
    MpReleaseProcessContextListEntry();
  if ( Object )
  {
    ObfDereferenceObject(Object);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
LABEL_40:
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002b880  mov     [rsp-28h+arg_8], rbx
0x14002b885  mov     [rsp-28h+arg_10], rsi
0x14002b88a  push    rbp
0x14002b88b  push    rdi
0x14002b88c  push    r12
0x14002b88e  push    r13
0x14002b890  push    r15
0x14002b892  mov     rbp, rsp
0x14002b895  sub     rsp, 80h
0x14002b89c  mov     rax, cs:__security_cookie
0x14002b8a3  xor     rax, rsp
0x14002b8a6  mov     [rbp+var_8], rax
0x14002b8aa  mov     rax, cs:MpProcessTable
0x14002b8b1  xor     r12d, r12d
0x14002b8b4  mov     [rbp+P], r12
0x14002b8b8  mov     r13, rcx
0x14002b8bb  mov     [rbp+var_28], r12d
0x14002b8bf  mov     [rbp+var_18], r12
0x14002b8c3  mov     [rbp+var_30], r12
0x14002b8c7  mov     [rbp+var_20], r12
0x14002b8cb  mov     [rbp+Object], r12
0x14002b8cf  mov     [rbp+var_40], dl
0x14002b8d2  lock inc dword ptr [rax+1A0h]
0x14002b8d9  mov     rcx, cs:MpProcessTable
0x14002b8e0  add     rcx, 188h; Event
0x14002b8e7  call    cs:__imp_KeClearEvent
0x14002b8ee  nop     dword ptr [rax+rax+00h]
0x14002b8f3  lea     rdx, [rbp+var_28]
0x14002b8f7  lea     rcx, [rbp+P]
0x14002b8fb  call    MpGetRunningProcesses
0x14002b900  mov     edi, eax
0x14002b902  test    eax, eax
0x14002b904  jns     loc_14002B9B7
0x14002b90a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b911  lea     rsi, WPP_GLOBAL_Control
0x14002b918  cmp     rcx, rsi
0x14002b91b  jnz     loc_14002BC6F
0x14002b921  mov     rbx, [rbp+P]
0x14002b925  mov     rcx, cs:MpProcessTable
0x14002b92c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002b930  mov     eax, esi
0x14002b932  lock xadd [rcx+1A0h], eax
0x14002b93a  add     eax, esi
0x14002b93c  jz      loc_14002BB50
0x14002b942  test    rbx, rbx
0x14002b945  jz      short loc_14002B95B
0x14002b947  mov     edx, 7072704Dh; Tag
0x14002b94c  mov     rcx, rbx; P
0x14002b94f  call    cs:__imp_ExFreePoolWithTag
0x14002b956  nop     dword ptr [rax+rax+00h]
0x14002b95b  mov     rcx, [rbp+var_18]
0x14002b95f  test    rcx, rcx
0x14002b962  jnz     loc_14002BD9A
0x14002b968  cmp     [rbp+var_30], r12
0x14002b96c  jnz     loc_14002BDA4
0x14002b972  mov     rcx, [rbp+var_20]
0x14002b976  test    rcx, rcx
0x14002b979  jnz     loc_14002BDB2
0x14002b97f  mov     rcx, [rbp+Object]; Object
0x14002b983  test    rcx, rcx
0x14002b986  jnz     loc_14002BB9B
0x14002b98c  mov     eax, edi
0x14002b98e  mov     rcx, [rbp+var_8]
0x14002b992  xor     rcx, rsp; StackCookie
0x14002b995  call    __security_check_cookie
0x14002b99a  lea     r11, [rsp+80h+var_s0]
0x14002b9a2  mov     rbx, [r11+38h]
0x14002b9a6  mov     rsi, [r11+40h]
0x14002b9aa  mov     rsp, r11
0x14002b9ad  pop     r15
0x14002b9af  pop     r13
0x14002b9b1  pop     r12
0x14002b9b3  pop     rdi
0x14002b9b4  pop     rbp
0x14002b9b5  retn
0x14002b9b7  mov     rbx, [rbp+P]
0x14002b9bb  lea     rsi, WPP_GLOBAL_Control
0x14002b9c2  mov     r15d, r12d
0x14002b9c5  cmp     r15d, [rbp+var_28]
0x14002b9c9  jnb     loc_14002BB3C
0x14002b9cf  mov     r12d, r15d
0x14002b9d2  xor     edi, edi
0x14002b9d4  cmp     [rbx+r12*8], rdi
0x14002b9d8  jz      loc_14002BAD9
0x14002b9de  mov     rcx, [rbp+Object]; Object
0x14002b9e2  test    rcx, rcx
0x14002b9e5  jz      short loc_14002BA0E
0x14002b9e7  call    cs:__imp_ObfDereferenceObject
0x14002b9ee  nop     dword ptr [rax+rax+00h]
0x14002b9f3  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b9f7  lock xadd cs:ObTotalReferences, rax
0x14002ba00  cmp     rax, 1
0x14002ba04  js      loc_14002BB11
0x14002ba0a  mov     [rbp+Object], rdi
0x14002ba0e  mov     rcx, [rbx+r12*8]; ProcessId
0x14002ba12  lea     rdx, [rbp+Object]; Process
0x14002ba16  call    cs:__imp_PsLookupProcessByProcessId
0x14002ba1d  nop     dword ptr [rax+rax+00h]
0x14002ba22  mov     ecx, eax
0x14002ba24  test    eax, eax
0x14002ba26  js      loc_14002BCAC
0x14002ba2c  lock inc cs:ObTotalReferences
0x14002ba34  mov     rcx, [rbp+Object]; Process
0x14002ba38  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002ba3f  nop     dword ptr [rax+rax+00h]
0x14002ba44  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002ba4b  mov     rdi, rax
0x14002ba4e  mov     rdx, [rcx]
0x14002ba51  cmp     [rbp+Object], rdx
0x14002ba55  jz      loc_14002BB74
0x14002ba5b  mov     rcx, [rbx+r12*8]
0x14002ba5f  lea     r8, [rbp+var_18]
0x14002ba63  mov     rdx, rdi
0x14002ba66  call    MpGetProcessContextByIdAndCreationTime
0x14002ba6b  xor     ecx, ecx
0x14002ba6d  test    eax, eax
0x14002ba6f  jns     short loc_14002BA85
0x14002ba71  cmp     [rbp+var_40], cl
0x14002ba74  jnz     loc_14002BC33
0x14002ba7a  xor     r12d, r12d
0x14002ba7d  inc     r15d
0x14002ba80  jmp     loc_14002B9C5
0x14002ba85  lea     rcx, [rbp+var_20]
0x14002ba89  call    MpAllocateProcessContextListEntry
0x14002ba8e  xor     edx, edx
0x14002ba90  mov     edi, eax
0x14002ba92  test    eax, eax
0x14002ba94  js      loc_14002BD7D
0x14002ba9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002baa1  cmp     rcx, rsi
0x14002baa4  jz      short loc_14002BAB1
0x14002baa6  mov     eax, [rcx+2Ch]
0x14002baa9  test    al, 4
0x14002baab  jnz     loc_14002BBE7
0x14002bab1  mov     rax, [rbp+var_18]
0x14002bab5  xor     r12d, r12d
0x14002bab8  mov     rcx, [rbp+var_20]
0x14002babc  mov     [rbp+var_20], r12
0x14002bac0  mov     [rcx+10h], rax
0x14002bac4  add     rcx, 8
0x14002bac8  mov     rax, [rbp+var_30]
0x14002bacc  mov     [rbp+var_18], r12
0x14002bad0  mov     [rbp+var_30], rcx
0x14002bad4  mov     [rcx], rax
0x14002bad7  jmp     short loc_14002BA7D
0x14002bad9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bae0  cmp     rcx, rsi
0x14002bae3  jz      short loc_14002BA7A
0x14002bae5  mov     eax, [rcx+2Ch]
0x14002bae8  test    al, 4
0x14002baea  jz      short loc_14002BA7A
0x14002baec  mov     eax, [rbx+r12*8]
0x14002baf0  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x14002baf7  mov     rcx, [rcx+18h]
0x14002bafb  mov     edx, 2Bh ; '+'
0x14002bb00  mov     r9d, r15d
0x14002bb03  mov     dword ptr [rsp+80h+var_60], eax
0x14002bb07  call    WPP_SF_dd
0x14002bb0c  jmp     loc_14002BA7A
0x14002bb11  mov     rax, cs:MpData
0x14002bb18  mov     ecx, [rax+364h]
0x14002bb1e  test    ecx, ecx
0x14002bb20  jns     loc_14002BA0A
0x14002bb26  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14002bb2d  nop     dword ptr [rax+rax+00h]
0x14002bb32  test    al, al
0x14002bb34  jnz     short loc_14002BB89
0x14002bb36  int     3; Trap to Debugger
0x14002bb37  jmp     loc_14002BA0A
0x14002bb3c  mov     rax, [rbp+var_30]
0x14002bb40  mov     edi, r12d
0x14002bb43  mov     [r13+0], rax
0x14002bb47  mov     [rbp+var_30], r12
0x14002bb4b  jmp     loc_14002B925
0x14002bb50  mov     rcx, cs:MpProcessTable
0x14002bb57  xor     r8d, r8d; Wait
0x14002bb5a  add     rcx, 188h; Event
0x14002bb61  xor     edx, edx; Increment
0x14002bb63  call    cs:__imp_KeSetEvent
0x14002bb6a  nop     dword ptr [rax+rax+00h]
0x14002bb6f  jmp     loc_14002B942
0x14002bb74  test    rdi, rdi
0x14002bb77  jz      loc_14002BA5B
0x14002bb7d  mov     cs:g_bSystemProcessContextCreateTimeFixed, 1
0x14002bb84  jmp     loc_14002BA5B
0x14002bb89  mov     ecx, 1; BugCheckCode
0x14002bb8e  call    cs:__imp_KeBugCheck
0x14002bb9b  call    cs:__imp_ObfDereferenceObject
0x14002bba2  nop     dword ptr [rax+rax+00h]
0x14002bba7  mov     rax, rsi
0x14002bbaa  lock xadd cs:ObTotalReferences, rax
0x14002bbb3  add     rax, rsi
0x14002bbb6  jns     loc_14002B98C
0x14002bbbc  mov     rax, cs:MpData
0x14002bbc3  mov     ecx, [rax+364h]
0x14002bbc9  test    ecx, ecx
0x14002bbcb  jns     loc_14002B98C
0x14002bbd1  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14002bbd8  nop     dword ptr [rax+rax+00h]
0x14002bbdd  test    al, al
0x14002bbdf  jnz     short loc_14002BB89
0x14002bbe1  int     3; Trap to Debugger
0x14002bbe2  jmp     loc_14002B98C
0x14002bbe7  mov     r8, [rbp+var_18]
0x14002bbeb  mov     rax, [r8+80h]
0x14002bbf2  cmp     [rax], dx
0x14002bbf5  jbe     short loc_14002BC2A
0x14002bbf7  mov     rdx, [rax+8]
0x14002bbfb  mov     eax, [r8+78h]
0x14002bbff  mov     r9d, r15d
0x14002bc02  mov     rcx, [rcx+18h]
0x14002bc06  mov     [rsp+80h+var_48], eax
0x14002bc0a  mov     eax, [rbx+r12*8]
0x14002bc0e  mov     [rsp+80h+var_50], eax
0x14002bc12  mov     rax, [r8+18h]
0x14002bc16  mov     [rsp+80h+var_58], rdx
0x14002bc1b  mov     [rsp+80h+var_60], rax
0x14002bc20  call    WPP_SF_DqSDd
0x14002bc25  jmp     loc_14002BAB1
0x14002bc2a  lea     rdx, aEmpty; "(empty)"
0x14002bc31  jmp     short loc_14002BBFB
0x14002bc33  lfence
0x14002bc36  mov     rbx, [rbp+P]
0x14002bc3a  lea     r9, [rbp+var_18]
0x14002bc3e  xor     r8d, r8d
0x14002bc41  mov     rdx, rdi
0x14002bc44  mov     rcx, [rbx+r12*8]; ProcessId
0x14002bc48  call    MpCreateProcessContext
0x14002bc4d  mov     edi, eax
0x14002bc4f  test    eax, eax
0x14002bc51  jns     loc_14002BA85
0x14002bc57  mov     rax, cs:WPP_GLOBAL_Control
0x14002bc5e  cmp     rax, rsi
0x14002bc61  jnz     loc_14002BD36
0x14002bc67  xor     r12d, r12d
0x14002bc6a  jmp     loc_14002B925
0x14002bc6f  mov     ecx, [rcx+2Ch]
0x14002bc72  test    cl, 1
0x14002bc75  jz      loc_14002B921
0x14002bc7b  lfence
0x14002bc7e  mov     r9, gs:188h
0x14002bc87  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x14002bc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc95  mov     edx, 2Ah ; '*'
0x14002bc9a  mov     dword ptr [rsp+80h+var_60], eax
0x14002bc9e  mov     rcx, [rcx+18h]
0x14002bca2  call    WPP_SF_qD
0x14002bca7  jmp     loc_14002B921
0x14002bcac  cmp     ecx, 0C000000Bh
0x14002bcb2  jz      short loc_14002BCDA
0x14002bcb4  mov     rax, cs:WPP_GLOBAL_Control
0x14002bcbb  cmp     rax, rsi
0x14002bcbe  jz      loc_14002BA7A
0x14002bcc4  mov     eax, [rax+2Ch]
0x14002bcc7  test    al, 2
0x14002bcc9  jz      loc_14002BA7A
0x14002bccf  mov     edx, 2Ch ; ','
0x14002bcd4  mov     dword ptr [rsp+80h+var_58], ecx
0x14002bcd8  jmp     short loc_14002BD02
0x14002bcda  mov     rax, cs:WPP_GLOBAL_Control
0x14002bce1  cmp     rax, rsi
0x14002bce4  jz      loc_14002BA7A
0x14002bcea  mov     eax, [rax+2Ch]
0x14002bced  test    al, 4
0x14002bcef  jz      loc_14002BA7A
0x14002bcf5  mov     edx, 2Dh ; '-'
0x14002bcfa  mov     dword ptr [rsp+80h+var_58], 0C000000Bh
0x14002bd02  lfence
0x14002bd05  mov     r9, gs:188h
0x14002bd0e  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x14002bd15  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd1c  mov     rbx, [rbp+P]
0x14002bd20  mov     rcx, [rcx+18h]
0x14002bd24  mov     eax, [rbx+r12*8]
0x14002bd28  mov     dword ptr [rsp+80h+var_60], eax
0x14002bd2c  call    WPP_SF_qDD
0x14002bd31  jmp     loc_14002BA7A
0x14002bd36  mov     eax, [rax+2Ch]
0x14002bd39  test    al, 1
0x14002bd3b  jz      loc_14002BC67
0x14002bd41  mov     edx, 2Eh ; '.'
0x14002bd46  jmp     short loc_14002BD4D
0x14002bd48  mov     edx, 2Fh ; '/'
0x14002bd4d  lfence
0x14002bd50  mov     r9, gs:188h
0x14002bd59  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x14002bd60  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd67  mov     dword ptr [rsp+80h+var_60], edi
0x14002bd6b  mov     rcx, [rcx+18h]
0x14002bd6f  call    WPP_SF_qD
0x14002bd74  mov     rbx, [rbp+P]
0x14002bd78  jmp     loc_14002BC67
0x14002bd7d  mov     rax, cs:WPP_GLOBAL_Control
0x14002bd84  cmp     rax, rsi
0x14002bd87  jz      loc_14002BC67
0x14002bd8d  mov     eax, [rax+2Ch]
0x14002bd90  test    al, 1
0x14002bd92  jz      loc_14002BC67
0x14002bd98  jmp     short loc_14002BD48
0x14002bd9a  call    MpReleaseProcessContext
  ... truncated ...
```
