# BfsPostCleanupOperation

- ea: `0x140001be0`
- end: `0x140001fa8`
- name: `BfsPostCleanupOperation`
- size: `968`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001320`
- `0x140001be0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001d36`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001d36`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140001e2b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140001e2b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140001cdb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140001d57`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140001cdb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140001d57`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001d09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001e0a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001e39`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001d09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001e0a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001e39`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001e64`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001f5f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001e64`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001f5f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001cc6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001d21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001d42`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001e51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001f4c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001cc6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001d21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001d42`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001e51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001f4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001d15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001e16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001e45`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001e70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001f6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001d15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001e16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001e45`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001e70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001f6b`
- `ntoskrnl!EtwWriteTransfer` at `0x140001f3b`
- `ntoskrnl!EtwWriteTransfer` at `0x140001f3b`
- `FLTMGR!FltReleaseContext` at `0x140001f7f`
- `FLTMGR!FltReleaseContext` at `0x140001f7f`
- `FLTMGR!FltQueryInformationFile` at `0x140001c62`
- `FLTMGR!FltQueryInformationFile` at `0x140001c62`
- `FLTMGR!FltFsControlFile` at `0x140001ca9`
- `FLTMGR!FltFsControlFile` at `0x140001ca9`

## pseudocode

```c
__int64 __fastcall BfsPostCleanupOperation(__int64 a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS v6; // eax
  __int64 v7; // rdi
  __int64 GlobalFileEntry; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  _DWORD v15[2]; // [rsp+40h] [rbp-79h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-71h] BYREF
  __int128 FileInformation; // [rsp+58h] [rbp-61h] BYREF
  __int64 v18; // [rsp+68h] [rbp-51h]
  struct _EVENT_DATA_DESCRIPTOR OutputBuffer[4]; // [rsp+70h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-9h] BYREF
  int *v21; // [rsp+C0h] [rbp+7h]
  int v22; // [rsp+C8h] [rbp+Fh]
  int v23; // [rsp+CCh] [rbp+13h]
  _DWORD *v24; // [rsp+D0h] [rbp+17h]
  __int64 v25; // [rsp+D8h] [rbp+1Fh]

  v18 = 0;
  FileInformation = 0;
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  if ( a3
    && *(_BYTE *)a3
    && FltQueryInformationFile(
         *(PFLT_INSTANCE *)(a2 + 24),
         *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL),
         &FileInformation,
         0x18u,
         FileStandardInformation,
         0) == -1073741533 )
  {
    v6 = FltFsControlFile(
           *(PFLT_INSTANCE *)(a2 + 24),
           *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL),
           0x9009Cu,
           0,
           0,
           OutputBuffer,
           0x40u,
           0);
    if ( v6 == -1073741533 )
    {
      v7 = a3[1];
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(&gBfsGlobalFileTable, 0);
      if ( BfsGetGlobalFileEntry(&gBfsGlobalFileTable, v7 + 8) )
      {
        ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
        KeLeaveCriticalRegion();
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(&qword_140019178, 0);
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(&gBfsGlobalFileTable, 0);
        GlobalFileEntry = BfsGetGlobalFileEntry(&gBfsGlobalFileTable, v7 + 8);
        v9 = GlobalFileEntry;
        if ( GlobalFileEntry )
        {
          if ( *(_BYTE *)(GlobalFileEntry + 40) == 1 )
          {
            *(_BYTE *)(GlobalFileEntry + 40) = 0;
            v10 = (_QWORD *)(GlobalFileEntry + 24);
            v11 = *v10;
            if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v12 = (_QWORD *)v10[1], (_QWORD *)*v12 != v10) )
LABEL_12:
              __fastfail(3u);
            *v12 = v11;
            *(_QWORD *)(v11 + 8) = v12;
            *v10 = 0;
            *(_QWORD *)(v9 + 32) = 0;
            *(_QWORD *)(v9 + 48) = 0;
            *(_QWORD *)(v9 + 56) = 0;
          }
          *(_BYTE *)(v9 + 40) = 1;
          *(_QWORD *)(v9 + 48) = qword_1400191B0;
          *(_QWORD *)(v9 + 56) = MEMORY[0xFFFFF78000000014];
          v13 = (_QWORD *)qword_1400191A8;
          if ( *(__int64 **)qword_1400191A8 != &qword_1400191A0 )
            goto LABEL_12;
          *(_QWORD *)(v9 + 24) = &qword_1400191A0;
          *(_QWORD *)(v9 + 32) = v13;
          *v13 = v9 + 24;
          qword_1400191A8 = v9 + 24;
        }
        ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
        KeLeaveCriticalRegion();
        ExReleasePushLockExclusiveEx(&qword_140019178, 0);
      }
      else
      {
        ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
      }
      KeLeaveCriticalRegion();
      goto LABEL_17;
    }
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741072 )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v15[0] = v6;
        v24 = v15;
        UserData.Ptr = (ULONGLONG)EventInformation;
        *(_DWORD *)&EventDescriptor.Level = 3;
        v25 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)EventInformation;
        v21 = &dword_140016D9C;
        UserData.Reserved = 2;
        v22 = 30;
        v23 = 1;
        v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
LABEL_17:
      KeEnterCriticalRegion();
      ExReleaseRundownProtection(&gBfsRundownProtection);
      KeLeaveCriticalRegion();
LABEL_23:
      FltReleaseContext(a3);
      return 0;
    }
  }
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( a3 )
    goto LABEL_23;
  return 0;
}

```

## disassembly

```asm
0x140001be0  push    rbp
0x140001be2  push    rbx
0x140001be3  push    rsi
0x140001be4  push    rdi
0x140001be5  push    r14
0x140001be7  lea     rbp, [rsp-37h]
0x140001bec  sub     rsp, 0F0h
0x140001bf3  mov     rax, cs:__security_cookie
0x140001bfa  xor     rax, rsp
0x140001bfd  mov     [rbp+57h+var_30], rax
0x140001c01  xorps   xmm1, xmm1
0x140001c04  xor     eax, eax
0x140001c06  mov     [rbp+57h+var_A8], rax
0x140001c0a  xorps   xmm0, xmm0
0x140001c0d  mov     rbx, r8
0x140001c10  mov     rsi, rdx
0x140001c13  mov     rdi, rcx
0x140001c16  movups  [rbp+57h+FileInformation], xmm0
0x140001c1a  movups  [rbp+57h+OutputBuffer], xmm1
0x140001c1e  movups  [rbp+57h+var_90], xmm1
0x140001c22  movups  [rbp+57h+var_80], xmm1
0x140001c26  movups  [rbp+57h+var_70], xmm1
0x140001c2a  test    r8, r8
0x140001c2d  jz      loc_140001F4C
0x140001c33  cmp     [r8], al
0x140001c36  jz      loc_140001F4C
0x140001c3c  mov     rdx, [rcx+10h]
0x140001c40  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140001c44  mov     rcx, [rsi+18h]; Instance
0x140001c48  xor     r14d, r14d
0x140001c4b  mov     [rsp+110h+LengthReturned], r14; LengthReturned
0x140001c50  mov     r9d, 18h; Length
0x140001c56  mov     [rsp+110h+FileInformationClass], 5; FileInformationClass
0x140001c5e  mov     rdx, [rdx+8]; FileObject
0x140001c62  call    cs:__imp_FltQueryInformationFile
0x140001c69  nop     dword ptr [rax+rax+00h]
0x140001c6e  cmp     eax, 0C0000123h
0x140001c73  jnz     loc_140001F4C
0x140001c79  mov     rdx, [rdi+10h]
0x140001c7d  lea     rax, [rbp+57h+OutputBuffer]
0x140001c81  mov     rcx, [rsi+18h]; Instance
0x140001c85  xor     r9d, r9d; InputBuffer
0x140001c88  mov     [rsp+110h+var_D8], r14; LengthReturned
0x140001c8d  mov     r8d, 9009Ch; FsControlCode
0x140001c93  mov     [rsp+110h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x140001c9b  mov     rdx, [rdx+8]; FileObject
0x140001c9f  mov     [rsp+110h+LengthReturned], rax; OutputBuffer
0x140001ca4  mov     [rsp+110h+FileInformationClass], r14d; InputBufferLength
0x140001ca9  call    cs:__imp_FltFsControlFile
0x140001cb0  nop     dword ptr [rax+rax+00h]
0x140001cb5  mov     ecx, eax
0x140001cb7  cmp     eax, 0C0000123h
0x140001cbc  jnz     loc_140001E81
0x140001cc2  mov     rdi, [rbx+8]
0x140001cc6  call    cs:__imp_KeEnterCriticalRegion
0x140001ccd  nop     dword ptr [rax+rax+00h]
0x140001cd2  xor     edx, edx
0x140001cd4  lea     rcx, gBfsGlobalFileTable
0x140001cdb  call    cs:__imp_ExAcquirePushLockSharedEx
0x140001ce2  nop     dword ptr [rax+rax+00h]
0x140001ce7  lea     rdx, [rdi+8]
0x140001ceb  lea     rcx, gBfsGlobalFileTable
0x140001cf2  call    BfsGetGlobalFileEntry
0x140001cf7  xor     edx, edx
0x140001cf9  lea     rcx, gBfsGlobalFileTable
0x140001d00  test    rax, rax
0x140001d03  jz      loc_140001E39
0x140001d09  call    cs:__imp_ExReleasePushLockSharedEx
0x140001d10  nop     dword ptr [rax+rax+00h]
0x140001d15  call    cs:__imp_KeLeaveCriticalRegion
0x140001d1c  nop     dword ptr [rax+rax+00h]
0x140001d21  call    cs:__imp_KeEnterCriticalRegion
0x140001d28  nop     dword ptr [rax+rax+00h]
0x140001d2d  xor     edx, edx
0x140001d2f  lea     rcx, qword_140019178
0x140001d36  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140001d3d  nop     dword ptr [rax+rax+00h]
0x140001d42  call    cs:__imp_KeEnterCriticalRegion
0x140001d49  nop     dword ptr [rax+rax+00h]
0x140001d4e  xor     edx, edx
0x140001d50  lea     rcx, gBfsGlobalFileTable
0x140001d57  call    cs:__imp_ExAcquirePushLockSharedEx
0x140001d5e  nop     dword ptr [rax+rax+00h]
0x140001d63  lea     rdx, [rdi+8]
0x140001d67  lea     rcx, gBfsGlobalFileTable
0x140001d6e  call    BfsGetGlobalFileEntry
0x140001d73  mov     rcx, rax
0x140001d76  test    rax, rax
0x140001d79  jz      loc_140001E01
0x140001d7f  cmp     byte ptr [rax+28h], 1
0x140001d83  jnz     short loc_140001DB5
0x140001d85  mov     [rax+28h], r14b
0x140001d89  add     rax, 18h
0x140001d8d  mov     rdx, [rax]
0x140001d90  cmp     [rdx+8], rax
0x140001d94  jnz     short loc_140001DE5
0x140001d96  mov     r8, [rax+8]
0x140001d9a  cmp     [r8], rax
0x140001d9d  jnz     short loc_140001DE5
0x140001d9f  mov     [r8], rdx
0x140001da2  mov     [rdx+8], r8
0x140001da6  mov     [rax], r14
0x140001da9  mov     [rcx+20h], r14
0x140001dad  mov     [rcx+30h], r14
0x140001db1  mov     [rcx+38h], r14
0x140001db5  mov     byte ptr [rcx+28h], 1
0x140001db9  lea     r8, qword_1400191A0
0x140001dc0  mov     rax, cs:qword_1400191B0
0x140001dc7  mov     [rcx+30h], rax
0x140001dcb  mov     rax, ds:0FFFFF78000000014h
0x140001dd5  mov     [rcx+38h], rax
0x140001dd9  mov     rdx, cs:qword_1400191A8
0x140001de0  cmp     [rdx], r8
0x140001de3  jz      short loc_140001DEC
0x140001de5  mov     ecx, 3
0x140001dea  int     29h; Win8: RtlFailFast(ecx)
0x140001dec  lea     rax, [rcx+18h]
0x140001df0  mov     [rax], r8
0x140001df3  mov     [rax+8], rdx
0x140001df7  mov     [rdx], rax
0x140001dfa  mov     cs:qword_1400191A8, rax
0x140001e01  xor     edx, edx
0x140001e03  lea     rcx, gBfsGlobalFileTable
0x140001e0a  call    cs:__imp_ExReleasePushLockSharedEx
0x140001e11  nop     dword ptr [rax+rax+00h]
0x140001e16  call    cs:__imp_KeLeaveCriticalRegion
0x140001e1d  nop     dword ptr [rax+rax+00h]
0x140001e22  xor     edx, edx
0x140001e24  lea     rcx, qword_140019178
0x140001e2b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140001e32  nop     dword ptr [rax+rax+00h]
0x140001e37  jmp     short loc_140001E45
0x140001e39  call    cs:__imp_ExReleasePushLockSharedEx
0x140001e40  nop     dword ptr [rax+rax+00h]
0x140001e45  call    cs:__imp_KeLeaveCriticalRegion
0x140001e4c  nop     dword ptr [rax+rax+00h]
0x140001e51  call    cs:__imp_KeEnterCriticalRegion
0x140001e58  nop     dword ptr [rax+rax+00h]
0x140001e5d  lea     rcx, gBfsRundownProtection; RunRef
0x140001e64  call    cs:__imp_ExReleaseRundownProtection
0x140001e6b  nop     dword ptr [rax+rax+00h]
0x140001e70  call    cs:__imp_KeLeaveCriticalRegion
0x140001e77  nop     dword ptr [rax+rax+00h]
0x140001e7c  jmp     loc_140001F7C
0x140001e81  mov     edx, 80000000h
0x140001e86  add     eax, edx
0x140001e88  test    edx, eax
0x140001e8a  jnz     loc_140001F4C
0x140001e90  cmp     ecx, 0C00002F0h
0x140001e96  jz      loc_140001F4C
0x140001e9c  mov     eax, cs:dword_140019000
0x140001ea2  cmp     eax, 3
0x140001ea5  jbe     short loc_140001E51
0x140001ea7  mov     [rbp+57h+var_D0], ecx
0x140001eaa  lea     rax, [rbp+57h+var_D0]
0x140001eae  mov     [rbp+57h+var_40], rax
0x140001eb2  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140001eb6  mov     rax, cs:qword_140016D92
0x140001ebd  xor     r9d, r9d; RelatedActivityId
0x140001ec0  movzx   ecx, ax
0x140001ec3  xor     r8d, r8d; ActivityId
0x140001ec6  mov     rax, cs:EventInformation
0x140001ecd  mov     [rbp+57h+UserData.Ptr], rax
0x140001ed1  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001ed4  lea     rcx, _TraceLoggingMetadata
0x140001edb  mov     [rbp+57h+var_38], 4
0x140001ee3  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001eea  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140001eee  movzx   eax, word ptr [rax]
0x140001ef1  mov     [rbp+57h+UserData.Size], eax
0x140001ef4  lea     rax, dword_140016D9C
0x140001efb  mov     [rbp+57h+var_50], rax
0x140001eff  lea     rax, _TraceLoggingMetadataEnd
0x140001f06  sub     eax, ecx
0x140001f08  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x140001f0f  mov     [rbp+57h+var_48], 1Eh
0x140001f16  mov     [rbp+57h+var_44], 1
0x140001f1d  mov     [rbp+57h+var_CC], eax
0x140001f20  mov     eax, [rbp+57h+var_CC]
0x140001f23  mov     rcx, cs:RegHandle; RegHandle
0x140001f2a  lea     rax, [rbp+57h+UserData]
0x140001f2e  mov     [rsp+110h+LengthReturned], rax; UserData
0x140001f33  mov     [rsp+110h+FileInformationClass], 3; UserDataCount
0x140001f3b  call    cs:__imp_EtwWriteTransfer
0x140001f42  nop     dword ptr [rax+rax+00h]
0x140001f47  jmp     loc_140001E51
0x140001f4c  call    cs:__imp_KeEnterCriticalRegion
0x140001f53  nop     dword ptr [rax+rax+00h]
0x140001f58  lea     rcx, gBfsRundownProtection; RunRef
0x140001f5f  call    cs:__imp_ExReleaseRundownProtection
0x140001f66  nop     dword ptr [rax+rax+00h]
0x140001f6b  call    cs:__imp_KeLeaveCriticalRegion
0x140001f72  nop     dword ptr [rax+rax+00h]
0x140001f77  test    rbx, rbx
0x140001f7a  jz      short loc_140001F8B
0x140001f7c  mov     rcx, rbx; Context
0x140001f7f  call    cs:__imp_FltReleaseContext
0x140001f86  nop     dword ptr [rax+rax+00h]
0x140001f8b  xor     eax, eax
0x140001f8d  mov     rcx, [rbp+57h+var_30]
0x140001f91  xor     rcx, rsp; StackCookie
0x140001f94  call    __security_check_cookie
0x140001f99  add     rsp, 0F0h
0x140001fa0  pop     r14
0x140001fa2  pop     rdi
0x140001fa3  pop     rsi
0x140001fa4  pop     rbx
0x140001fa5  pop     rbp
0x140001fa6  retn
```
