# MpDlpShouldCheckMappedFileOperation

- ea: `0x14007451c`
- end: `0x1400748a5`
- name: `MpDlpShouldCheckMappedFileOperation`
- size: `905`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14006e7d0`

## callees

- `0x1400051bc`
- `0x140011890`
- `0x1400118d0`
- `0x140011900`
- `0x140011bc0`
- `0x14007451c`
- `0x140077138`
- `0x140085d24`
- `0x1400868a0`

## import_xrefs

- `ntoskrnl!MmCanFileBeTruncated` at `0x14007460c`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14007460c`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140074577`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140074577`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400747e8`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400747e8`
- `ntoskrnl!ExQueryDepthSList` at `0x14007483c`
- `ntoskrnl!ExQueryDepthSList` at `0x14007483c`
- `ntoskrnl!KeBugCheck` at `0x14007480c`
- `ntoskrnl!KeBugCheck` at `0x14007480c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14007486b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14007486b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400747b8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400747b8`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074679`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140074679`
- `FLTMGR!FltAcquirePushLockShared` at `0x1400745c8`
- `FLTMGR!FltAcquirePushLockShared` at `0x1400745c8`
- `FLTMGR!FltReleasePushLock` at `0x1400747a2`
- `FLTMGR!FltReleasePushLock` at `0x1400747a2`

## pseudocode

```c
char __fastcall MpDlpShouldCheckMappedFileOperation(struct _KPROCESS *a1, __int64 a2, PSLIST_ENTRY *a3)
{
  int v5; // ebx
  unsigned int v6; // r15d
  PSLIST_ENTRY v7; // rdi
  unsigned __int64 *v8; // rcx
  _QWORD **v9; // r13
  _QWORD *v10; // r12
  _QWORD *v11; // rsi
  SECTION_OBJECT_POINTERS *v12; // rcx
  PEPROCESS v13; // rdx
  char *v14; // rbx
  union _SLIST_HEADER *v15; // rcx
  __int16 v16; // ax
  char *v17; // rsi
  USHORT v18; // bx
  USHORT DepthSList; // ax
  char IsFileMappedInProcess; // [rsp+30h] [rbp-68h]
  unsigned __int64 *PushLock; // [rsp+38h] [rbp-60h]
  PEPROCESS Process; // [rsp+48h] [rbp-50h] BYREF
  union _LARGE_INTEGER NewFileSize; // [rsp+50h] [rbp-48h] BYREF

  IsFileMappedInProcess = 0;
  Process = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( !a2 )
    return 0;
  if ( a1 )
    goto LABEL_5;
  if ( PsLookupProcessByProcessId(*(HANDLE *)(a2 + 24), &Process) < 0 )
    return 0;
  _InterlockedIncrement64(&ObTotalReferences);
LABEL_5:
  if ( a3 )
    *a3 = 0;
  if ( *(_BYTE *)(a2 + 224) )
  {
    v8 = (unsigned __int64 *)((char *)MpDlpData + 8);
    v9 = (_QWORD **)((char *)MpDlpData + 16);
  }
  else
  {
    v8 = (unsigned __int64 *)(a2 + 200);
    v9 = (_QWORD **)(a2 + 208);
  }
  PushLock = v8;
  FltAcquirePushLockShared(v8);
  v10 = *v9;
  while ( v10 != v9 )
  {
    v11 = v10;
    v10 = (_QWORD *)*v10;
    if ( (v11[2] & 1) == 0 )
    {
      NewFileSize.QuadPart = 0;
      v12 = (SECTION_OBJECT_POINTERS *)v11[6];
      if ( v12 && v12->DataSectionObject && MmCanFileBeTruncated(v12, &NewFileSize) )
      {
        *((_DWORD *)v11 + 4) |= 1u;
        v11[6] = 0;
      }
      else
      {
        v13 = Process;
        if ( a1 )
          v13 = a1;
        IsFileMappedInProcess = MpIsFileMappedInProcess((PCUNICODE_STRING)v11 + 2, v13);
        if ( IsFileMappedInProcess == 1 )
        {
          if ( !a3 )
            break;
          if ( !v7 )
          {
            v14 = (char *)MpDlpData + 144;
            v15 = (union _SLIST_HEADER *)((char *)MpDlpData + 144);
            ++*((_DWORD *)MpDlpData + 41);
            v7 = ExpInterlockedPopEntrySList(v15);
            if ( !v7 )
            {
              ++*((_DWORD *)v14 + 6);
              v7 = (PSLIST_ENTRY)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))v14 + 6))(
                                   *((unsigned int *)v14 + 9),
                                   *((unsigned int *)v14 + 11),
                                   *((unsigned int *)v14 + 10),
                                   v14);
            }
            if ( !v7 )
            {
              v5 = -1073741670;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  88,
                  WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                  KeGetCurrentThread(),
                  -1073741670);
              }
              break;
            }
            LODWORD(v7[1].Next) = 0;
            HIDWORD(v7[1].Next) = 254;
            memset(&v7[1].Next + 1, 0, 0xFEu);
            v16 = WORD2(v7[1].Next);
            *v7 = 0;
            WORD1(v7->Next) = v16;
            *((_QWORD *)&v7->Next + 1) = (char *)v7 + 24;
          }
          v6 += *((unsigned __int16 *)v11 + 16) + 2;
          if ( v6 > 0xFFFE )
          {
            v5 = -1073741562;
            break;
          }
          if ( v6 > (unsigned __int64)HIDWORD(v7[1].Next) - 2 )
          {
            _mm_lfence();
            v5 = MpDlpReallocMappedFileNamesArray(v7, v6 + 2);
            if ( v5 < 0 )
              break;
          }
          else
          {
            v5 = 0;
          }
          memmove(
            (void *)(*((_QWORD *)&v7->Next + 1) + LOWORD(v7->Next)),
            (const void *)v11[5],
            *((unsigned __int16 *)v11 + 16));
          LOWORD(v7->Next) += *((_WORD *)v11 + 16) + 2;
        }
      }
    }
  }
  FltReleasePushLock(PushLock);
  if ( Process )
  {
    ObfDereferenceObject(Process);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  if ( v7 )
  {
    if ( v5 < 0 )
    {
      _mm_lfence();
      MpDlpCleanupMappedFileNamesArray(v7);
      v17 = (char *)MpDlpData + 144;
      ++*((_DWORD *)MpDlpData + 43);
      v18 = *((_WORD *)v17 + 8);
      DepthSList = ExQueryDepthSList((PSLIST_HEADER)v17);
      _mm_lfence();
      if ( DepthSList < v18 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v17, v7);
      }
      else
      {
        ++*((_DWORD *)v17 + 8);
        (*((void (__fastcall **)(PSLIST_ENTRY, char *))v17 + 7))(v7, v17);
      }
    }
    else
    {
      *a3 = v7;
    }
  }
  return IsFileMappedInProcess;
}

```

## disassembly

```asm
0x14007451c  mov     [rsp+arg_18], rbx
0x140074521  push    rbp
0x140074522  push    rsi
0x140074523  push    rdi
0x140074524  push    r12
0x140074526  push    r13
0x140074528  push    r14
0x14007452a  push    r15
0x14007452c  sub     rsp, 60h
0x140074530  mov     rax, cs:__security_cookie
0x140074537  xor     rax, rsp
0x14007453a  mov     [rsp+98h+var_40], rax
0x14007453f  xor     esi, esi
0x140074541  mov     [rsp+98h+Object], rcx
0x140074546  mov     [rsp+98h+var_68], sil
0x14007454b  mov     r14, r8
0x14007454e  mov     [rsp+98h+Process], rsi
0x140074553  mov     rbp, rdx
0x140074556  mov     rax, rcx
0x140074559  mov     ebx, esi
0x14007455b  mov     r15d, esi
0x14007455e  mov     edi, esi
0x140074560  test    rdx, rdx
0x140074563  jz      loc_14007487D
0x140074569  test    rax, rax
0x14007456c  jnz     short loc_140074593
0x14007456e  mov     rcx, [rbp+18h]; ProcessId
0x140074572  lea     rdx, [rsp+98h+Process]; Process
0x140074577  call    cs:__imp_PsLookupProcessByProcessId
0x14007457e  nop     dword ptr [rax+rax+00h]
0x140074583  test    eax, eax
0x140074585  js      loc_14007487D
0x14007458b  lock inc cs:ObTotalReferences
0x140074593  test    r14, r14
0x140074596  jz      short loc_14007459B
0x140074598  mov     [r14], rsi
0x14007459b  cmp     [rbp+0E0h], sil
0x1400745a2  jz      short loc_1400745B5
0x1400745a4  mov     rax, cs:MpDlpData
0x1400745ab  lea     rcx, [rax+8]
0x1400745af  lea     r13, [rax+10h]
0x1400745b3  jmp     short loc_1400745C3
0x1400745b5  lea     rcx, [rbp+0C8h]; PushLock
0x1400745bc  lea     r13, [rbp+0D0h]
0x1400745c3  mov     [rsp+98h+PushLock], rcx
0x1400745c8  call    cs:__imp_FltAcquirePushLockShared
0x1400745cf  nop     dword ptr [rax+rax+00h]
0x1400745d4  mov     r12, [r13+0]
0x1400745d8  cmp     r12, r13
0x1400745db  jz      loc_14007479D
0x1400745e1  mov     rsi, r12
0x1400745e4  mov     r12, [r12]
0x1400745e8  mov     eax, [rsi+10h]
0x1400745eb  test    al, 1
0x1400745ed  jnz     short loc_1400745D8
0x1400745ef  mov     qword ptr [rsp+98h+NewFileSize], 0
0x1400745f8  mov     rcx, [rsi+30h]; SectionPointer
0x1400745fc  test    rcx, rcx
0x1400745ff  jz      short loc_14007462A
0x140074601  cmp     qword ptr [rcx], 0
0x140074605  jz      short loc_14007462A
0x140074607  lea     rdx, [rsp+98h+NewFileSize]; NewFileSize
0x14007460c  call    cs:__imp_MmCanFileBeTruncated
0x140074613  nop     dword ptr [rax+rax+00h]
0x140074618  test    al, al
0x14007461a  jz      short loc_14007462A
0x14007461c  or      dword ptr [rsi+10h], 1
0x140074620  mov     qword ptr [rsi+30h], 0
0x140074628  jmp     short loc_1400745D8
0x14007462a  mov     rax, [rsp+98h+Object]
0x14007462f  lea     rcx, [rsi+20h]; String1
0x140074633  mov     rdx, [rsp+98h+Process]
0x140074638  test    rax, rax
0x14007463b  mov     r8, [rbp+0F8h]
0x140074642  cmovnz  rdx, rax; Object
0x140074646  call    MpIsFileMappedInProcess
0x14007464b  mov     [rsp+98h+var_68], al
0x14007464f  cmp     al, 1
0x140074651  jnz     short loc_1400745D8
0x140074653  test    r14, r14
0x140074656  jz      loc_14007479D
0x14007465c  test    rdi, rdi
0x14007465f  jnz     loc_1400746E5
0x140074665  mov     rbx, cs:MpDlpData
0x14007466c  add     rbx, 90h
0x140074673  mov     rcx, rbx; ListHead
0x140074676  inc     dword ptr [rbx+14h]
0x140074679  call    cs:__imp_ExpInterlockedPopEntrySList
0x140074680  nop     dword ptr [rax+rax+00h]
0x140074685  mov     rdi, rax
0x140074688  test    rax, rax
0x14007468b  jnz     short loc_1400746AA
0x14007468d  inc     dword ptr [rbx+18h]
0x140074690  mov     r9, rbx
0x140074693  mov     edx, [rbx+2Ch]
0x140074696  mov     rax, [rbx+30h]
0x14007469a  mov     r8d, [rbx+28h]
0x14007469e  mov     ecx, [rbx+24h]
0x1400746a1  call    cs:__guard_dispatch_icall_fptr
0x1400746a7  mov     rdi, rax
0x1400746aa  test    rdi, rdi
0x1400746ad  jz      loc_14007474A
0x1400746b3  mov     eax, 0FEh
0x1400746b8  mov     dword ptr [rdi+10h], 0
0x1400746bf  lea     rbx, [rdi+18h]
0x1400746c3  mov     [rdi+14h], eax
0x1400746c6  mov     r8d, eax; Size
0x1400746c9  mov     rcx, rbx; void *
0x1400746cc  xor     edx, edx; Val
0x1400746ce  call    memset
0x1400746d3  movzx   eax, word ptr [rdi+14h]
0x1400746d7  xorps   xmm0, xmm0
0x1400746da  movups  xmmword ptr [rdi], xmm0
0x1400746dd  mov     [rdi+2], ax
0x1400746e1  mov     [rdi+8], rbx
0x1400746e5  movzx   eax, word ptr [rsi+20h]
0x1400746e9  add     r15d, 2
0x1400746ed  add     r15d, eax
0x1400746f0  cmp     r15d, 0FFFEh
0x1400746f7  ja      loc_140074798
0x1400746fd  mov     ecx, [rdi+14h]
0x140074700  sub     rcx, 2
0x140074704  mov     eax, r15d
0x140074707  cmp     rax, rcx
0x14007470a  ja      short loc_140074710
0x14007470c  xor     ebx, ebx
0x14007470e  jmp     short loc_140074725
0x140074710  lfence
0x140074713  lea     edx, [r15+2]
0x140074717  mov     rcx, rdi
0x14007471a  call    MpDlpReallocMappedFileNamesArray
0x14007471f  mov     ebx, eax
0x140074721  test    eax, eax
0x140074723  js      short loc_14007479D
0x140074725  movzx   ecx, word ptr [rdi]
0x140074728  add     rcx, [rdi+8]; void *
0x14007472c  movzx   r8d, word ptr [rsi+20h]; Size
0x140074731  mov     rdx, [rsi+28h]; Src
0x140074735  call    memmove
0x14007473a  movzx   ecx, word ptr [rsi+20h]
0x14007473e  add     cx, 2
0x140074742  add     [rdi], cx
0x140074745  jmp     loc_1400745D8
0x14007474a  mov     ebx, 0C000009Ah
0x14007474f  mov     rax, cs:WPP_GLOBAL_Control
0x140074756  lea     rcx, WPP_GLOBAL_Control
0x14007475d  cmp     rax, rcx
0x140074760  jz      short loc_14007479D
0x140074762  mov     eax, [rax+2Ch]
0x140074765  test    al, 1
0x140074767  jz      short loc_14007479D
0x140074769  mov     r9, gs:188h
0x140074772  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140074779  mov     rcx, cs:WPP_GLOBAL_Control
0x140074780  mov     edx, 58h ; 'X'
0x140074785  mov     [rsp+98h+var_78], 0C000009Ah
0x14007478d  mov     rcx, [rcx+18h]
0x140074791  call    WPP_SF_qD
0x140074796  jmp     short loc_14007479D
0x140074798  mov     ebx, 0C0000106h
0x14007479d  mov     rcx, [rsp+98h+PushLock]; PushLock
0x1400747a2  call    cs:__imp_FltReleasePushLock
0x1400747a9  nop     dword ptr [rax+rax+00h]
0x1400747ae  mov     rcx, [rsp+98h+Process]; Object
0x1400747b3  test    rcx, rcx
0x1400747b6  jz      short loc_1400747F9
0x1400747b8  call    cs:__imp_ObfDereferenceObject
0x1400747bf  nop     dword ptr [rax+rax+00h]
0x1400747c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400747c8  lock xadd cs:ObTotalReferences, rax
0x1400747d1  cmp     rax, 1
0x1400747d5  jns     short loc_1400747F9
0x1400747d7  mov     rax, cs:MpData
0x1400747de  mov     ecx, [rax+364h]
0x1400747e4  test    ecx, ecx
0x1400747e6  jns     short loc_1400747F9
0x1400747e8  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400747ef  nop     dword ptr [rax+rax+00h]
0x1400747f4  test    al, al
0x1400747f6  jnz     short loc_140074807
0x1400747f8  int     3; Trap to Debugger
0x1400747f9  test    rdi, rdi
0x1400747fc  jz      short loc_140074877
0x1400747fe  test    ebx, ebx
0x140074800  js      short loc_140074819
0x140074802  mov     [r14], rdi
0x140074805  jmp     short loc_140074877
0x140074807  mov     ecx, 1; BugCheckCode
0x14007480c  call    cs:__imp_KeBugCheck
0x140074819  lfence
0x14007481c  mov     rcx, rdi
0x14007481f  call    MpDlpCleanupMappedFileNamesArray
0x140074824  mov     rsi, cs:MpDlpData
0x14007482b  add     rsi, 90h
0x140074832  mov     rcx, rsi; SListHead
0x140074835  inc     dword ptr [rsi+1Ch]
0x140074838  movzx   ebx, word ptr [rsi+10h]
0x14007483c  call    cs:__imp_ExQueryDepthSList
0x140074843  nop     dword ptr [rax+rax+00h]
0x140074848  lfence
0x14007484b  cmp     ax, bx
0x14007484e  jb      short loc_140074865
0x140074850  inc     dword ptr [rsi+20h]
0x140074853  mov     rdx, rsi
0x140074856  mov     rax, [rsi+38h]
0x14007485a  mov     rcx, rdi
0x14007485d  call    cs:__guard_dispatch_icall_fptr
0x140074863  jmp     short loc_140074877
0x140074865  mov     rdx, rdi; ListEntry
0x140074868  mov     rcx, rsi; ListHead
0x14007486b  call    cs:__imp_ExpInterlockedPushEntrySList
0x140074872  nop     dword ptr [rax+rax+00h]
0x140074877  mov     al, [rsp+98h+var_68]
0x14007487b  jmp     short loc_14007487F
0x14007487d  xor     al, al
0x14007487f  mov     rcx, [rsp+98h+var_40]
0x140074884  xor     rcx, rsp; StackCookie
0x140074887  call    __security_check_cookie
0x14007488c  mov     rbx, [rsp+98h+arg_18]
0x140074894  add     rsp, 60h
0x140074898  pop     r15
0x14007489a  pop     r14
0x14007489c  pop     r13
0x14007489e  pop     r12
0x1400748a0  pop     rdi
0x1400748a1  pop     rsi
0x1400748a2  pop     rbp
0x1400748a3  retn
```
