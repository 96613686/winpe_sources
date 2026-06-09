# BipPdcReferenceRelease

- ea: `0x1800154b0`
- end: `0x18001573b`
- name: `BipPdcReferenceRelease`
- size: `651`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015378`
- `0x18001542c`
- `0x18003ad50`

## callees

- `0x1800154b0`
- `0x18006a8d4`
- `0x18006d364`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800154ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001558b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800154ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001558b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015514`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800155f1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180015514`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800155f1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800156fe`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800156fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015591`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015576`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015576`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800155c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800155c4`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180015536`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180015536`

## pseudocode

```c
void __fastcall BipPdcReferenceRelease(__int64 a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r14
  _QWORD *ThreadLocalStoragePointer; // rax
  unsigned int v10; // ebx
  __int64 v11; // r15
  DWORD CurrentThreadId; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdi
  int v17; // ebx
  __int64 v18; // rax
  __int128 v19; // xmm0
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-69h] BYREF
  __int64 v21; // [rsp+40h] [rbp-61h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-59h] BYREF
  __int128 v23; // [rsp+58h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-39h] BYREF
  int *v25; // [rsp+78h] [rbp-29h]
  int v26; // [rsp+80h] [rbp-21h]
  int v27; // [rsp+84h] [rbp-1Dh]
  __int64 *v28; // [rsp+88h] [rbp-19h]
  __int64 v29; // [rsp+90h] [rbp-11h]
  __int128 *v30; // [rsp+98h] [rbp-9h]
  __int64 v31; // [rsp+A0h] [rbp-1h]
  __int64 v32; // [rsp+A8h] [rbp+7h]
  __int64 v33; // [rsp+B0h] [rbp+Fh]

  if ( *(_QWORD *)a1 )
  {
    RtlAcquireSRWLockExclusive(a2 + 48);
    v4 = *(_QWORD *)(a2 + 144);
    *(_DWORD *)(a2 + 136) |= 0x200u;
    *(_QWORD *)(a2 + 144) = 0;
    RtlReleaseSRWLockExclusive(a2 + 48);
    if ( v4 )
    {
      if ( (int)Pdcv2ActivationClientDeactivate(v4) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v7);
      v8 = a1 + 8;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v10 = 1 << *(_DWORD *)(a1 + 16);
      SystemTimeAsFileTime = 0;
      v11 = ThreadLocalStoragePointer[(unsigned int)tls_index];
      if ( *(_DWORD *)(v11 + 4) >= v10 && IsDebuggerPresent() )
        BipSyncDebugPrintLockBug((struct _BI_LOCK *)(a1 + 8));
      RtlAcquireSRWLockExclusive(a1 + 8);
      CurrentThreadId = GetCurrentThreadId();
      *(_DWORD *)(v11 + 4) |= v10;
      *(_DWORD *)(a1 + 20) = CurrentThreadId;
      --*(_QWORD *)(a1 + 24);
      *(_DWORD *)(v11 + 8) |= v10;
      if ( *(_QWORD *)(a1 + 24) == -1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13, v15);
      if ( !*(_QWORD *)(a1 + 24) )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *(struct _FILETIME *)(a1 + 48) = SystemTimeAsFileTime;
      }
      v16 = *(_QWORD *)(a1 + 24);
      v17 = ~(1 << *(_DWORD *)(v8 + 8));
      *(_DWORD *)(v11 + 8) &= v17;
      *(_DWORD *)(v8 + 12) = 0;
      RtlReleaseSRWLockExclusive(v8);
      *(_DWORD *)(v11 + 4) &= v17;
      if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
      {
        v18 = *(_QWORD *)(a2 + 64);
        v19 = 0;
        if ( v18 )
          v19 = *(_OWORD *)(v18 + 32);
        v23 = v19;
        v30 = &v23;
        v21 = v16;
        v28 = &v21;
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)off_1800C30A0;
        v32 = a2;
        v33 = 16;
        v31 = 16;
        v29 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 3;
        UserData.Size = *(unsigned __int16 *)off_1800C30A0;
        v25 = &dword_1800B482C;
        UserData.Reserved = 2;
        v26 = 71;
        v27 = 1;
        SystemTimeAsFileTime.dwLowDateTime = (unsigned int)&TraceLoggingMetadataEnd
                                           - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
  }
}

```

## disassembly

```asm
0x1800154b0  mov     r11, rsp
0x1800154b3  push    rbp
0x1800154b4  push    rsi
0x1800154b5  push    rdi
0x1800154b6  lea     rbp, [r11-5Fh]
0x1800154ba  sub     rsp, 0E0h
0x1800154c1  mov     rax, cs:__security_cookie
0x1800154c8  xor     rax, rsp
0x1800154cb  mov     [rbp+57h+var_40], rax
0x1800154cf  cmp     qword ptr [rcx], 0
0x1800154d3  mov     rsi, rdx
0x1800154d6  mov     rdi, rcx
0x1800154d9  jz      loc_180015724
0x1800154df  mov     [r11+18h], rbx
0x1800154e3  lea     rcx, [rdx+30h]
0x1800154e7  mov     [r11-30h], r14
0x1800154eb  mov     [r11-38h], r15
0x1800154ef  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800154f5  mov     r14, [rsi+90h]
0x1800154fc  lea     rcx, [rsi+30h]
0x180015500  or      dword ptr [rsi+88h], 200h
0x18001550a  xor     r15d, r15d
0x18001550d  mov     [rsi+90h], r15
0x180015514  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001551a  test    r14, r14
0x18001551d  jz      loc_18001570C
0x180015523  mov     [rsp+0D8h], r12
0x18001552b  mov     rcx, r14
0x18001552e  mov     [rsp+0F0h+var_20], r13
0x180015536  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x18001553c  test    eax, eax
0x18001553e  jns     short loc_180015545
0x180015540  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015545  mov     ecx, [rdi+10h]
0x180015548  lea     r14, [rdi+8]
0x18001554c  mov     rax, gs:58h
0x180015555  mov     ebx, 1
0x18001555a  shl     ebx, cl
0x18001555c  mov     ecx, cs:_tls_index
0x180015562  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180015566  mov     r12d, 4
0x18001556c  mov     r15, [rax+rcx*8]
0x180015570  cmp     [r12+r15], ebx
0x180015574  jb      short loc_180015588
0x180015576  call    cs:__imp_IsDebuggerPresent
0x18001557c  test    eax, eax
0x18001557e  jz      short loc_180015588
0x180015580  mov     rcx, r14; struct _BI_LOCK *
0x180015583  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180015588  mov     rcx, r14
0x18001558b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180015591  call    cs:__imp_GetCurrentThreadId
0x180015597  or      [r12+r15], ebx
0x18001559b  mov     [r14+0Ch], eax
0x18001559f  dec     qword ptr [rdi+18h]
0x1800155a3  mov     r13d, 8
0x1800155a9  or      [r15+r13], ebx
0x1800155ad  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x1800155b2  jnz     short loc_1800155B9
0x1800155b4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800155b9  cmp     qword ptr [rdi+18h], 0
0x1800155be  jnz     short loc_1800155D2
0x1800155c0  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800155c4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800155ca  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800155ce  mov     [rdi+30h], rax
0x1800155d2  mov     ecx, [r14+8]
0x1800155d6  mov     ebx, 1
0x1800155db  mov     rdi, [rdi+18h]
0x1800155df  shl     ebx, cl
0x1800155e1  mov     rcx, r14
0x1800155e4  not     ebx
0x1800155e6  and     [r15+r13], ebx
0x1800155ea  xor     r13d, r13d
0x1800155ed  mov     [r14+0Ch], r13d
0x1800155f1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800155f7  and     [r12+r15], ebx
0x1800155fb  mov     eax, cs:dword_1800C3098
0x180015601  mov     r12, [rsp+0D8h]
0x180015609  cmp     eax, 4
0x18001560c  jbe     loc_180015704
0x180015612  mov     rcx, cs:qword_1800C30B0
0x180015619  mov     rax, cs:qword_1800C30A8
0x180015620  test    al, 3
0x180015622  jz      loc_180015704
0x180015628  mov     rax, rcx
0x18001562b  and     eax, 3
0x18001562e  cmp     rax, rcx
0x180015631  jnz     loc_180015704
0x180015637  mov     rax, [rsi+40h]
0x18001563b  xorps   xmm0, xmm0
0x18001563e  test    rax, rax
0x180015641  jz      short loc_180015647
0x180015643  movups  xmm0, xmmword ptr [rax+20h]
0x180015647  movdqa  [rbp+57h+var_A0], xmm0
0x18001564c  lea     rax, [rbp+57h+var_A0]
0x180015650  mov     [rbp+57h+var_60], rax
0x180015654  lea     rcx, _TraceLoggingMetadata
0x18001565b  lea     rax, [rbp+57h+var_B8]
0x18001565f  mov     [rbp+57h+var_B8], rdi
0x180015663  mov     [rbp+57h+var_70], rax
0x180015667  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001566b  movzx   eax, cs:word_1800B4822
0x180015672  xor     r9d, r9d; RelatedActivityId
0x180015675  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180015678  xor     r8d, r8d; ActivityId
0x18001567b  mov     rax, cs:off_1800C30A0
0x180015682  mov     [rbp+57h+UserData.Ptr], rax
0x180015686  mov     [rbp+57h+var_50], rsi
0x18001568a  mov     [rbp+57h+var_48], 10h
0x180015692  mov     [rbp+57h+var_58], 10h
0x18001569a  mov     [rbp+57h+var_68], 8
0x1800156a2  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800156a9  mov     [rbp+57h+EventDescriptor.Keyword], 3
0x1800156b1  movzx   eax, word ptr [rax]
0x1800156b4  mov     [rbp+57h+UserData.Size], eax
0x1800156b7  lea     rax, dword_1800B482C
0x1800156be  mov     [rbp+57h+var_80], rax
0x1800156c2  lea     rax, _TraceLoggingMetadataEnd
0x1800156c9  sub     eax, ecx
0x1800156cb  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x1800156d2  mov     [rbp+57h+var_78], 47h ; 'G'
0x1800156d9  mov     [rbp+57h+var_74], 1
0x1800156e0  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], eax
0x1800156e3  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800156e6  mov     rcx, cs:RegHandle; RegHandle
0x1800156ed  lea     rax, [rbp+57h+UserData]
0x1800156f1  mov     [rsp+28h], rax; UserData
0x1800156f6  mov     [rsp+0F0h+UserDataCount], 5; UserDataCount
0x1800156fe  call    cs:__imp_EventWriteTransfer
0x180015704  mov     r13, [rsp+0F0h+var_20]
0x18001570c  mov     r14, [rsp+0F0h+var_28]
0x180015714  mov     rbx, [rsp+0F0h+arg_10]
0x18001571c  mov     r15, [rsp+0F0h+var_30]
0x180015724  mov     rcx, [rbp+57h+var_40]
0x180015728  xor     rcx, rsp; StackCookie
0x18001572b  call    __security_check_cookie
0x180015730  add     rsp, 0E0h
0x180015737  pop     rdi
0x180015738  pop     rsi
0x180015739  pop     rbp
0x18001573a  retn
```
