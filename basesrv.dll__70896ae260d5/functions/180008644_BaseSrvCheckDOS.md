# BaseSrvCheckDOS

- ea: `0x180008644`
- end: `0x180008aa8`
- name: `BaseSrvCheckDOS`
- size: `1124`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b80`

## callees

- `0x180008038`
- `0x1800084bc`
- `0x180008644`
- `0x180009114`
- `0x1800091dc`
- `0x180009698`
- `0x180009788`
- `0x18000a54c`
- `0x18000a614`
- `0x18000a8fc`
- `0x18000b18c`
- `0x18000d713`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008787`
- `ntdll!RtlAllocateHeap` at `0x180008787`
- `ntdll!NtClose` at `0x1800086ee`
- `ntdll!NtClose` at `0x1800088ef`
- `ntdll!NtClose` at `0x1800086ee`
- `ntdll!NtClose` at `0x1800088ef`
- `ntdll!RtlEnterCriticalSection` at `0x1800086a3`
- `ntdll!RtlEnterCriticalSection` at `0x1800086a3`
- `ntdll!RtlLeaveCriticalSection` at `0x180008a81`
- `ntdll!RtlLeaveCriticalSection` at `0x180008a81`
- `ntdll!NtDuplicateObject` at `0x18000892a`
- `ntdll!NtDuplicateObject` at `0x18000892a`
- `ntdll!NtSetEvent` at `0x180008854`
- `ntdll!NtSetEvent` at `0x18000896d`
- `ntdll!NtSetEvent` at `0x180008854`
- `ntdll!NtSetEvent` at `0x18000896d`
- `ntdll!NtCompareTokens` at `0x1800086dc`
- `ntdll!NtCompareTokens` at `0x1800086dc`
- `CSRSRV!CsrUnlockProcess` at `0x18000899a`
- `CSRSRV!CsrUnlockProcess` at `0x18000899a`
- `CSRSRV!CsrLockProcessByClientId` at `0x1800087c5`
- `CSRSRV!CsrLockProcessByClientId` at `0x1800087c5`

## pseudocode

```c
__int64 __fastcall BaseSrvCheckDOS(__int64 a1, __int64 a2)
{
  int ConsoleRecord; // eax
  __int64 v6; // rsi
  NTSTATUS v7; // ebx
  __int64 v8; // rdi
  _QWORD *Heap; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  void *v13; // rcx
  __int64 DOSRecord; // rax
  __int64 v15; // rdi
  void *v16; // rcx
  void *v17; // rdx
  void *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // r8
  _QWORD *v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  HANDLE FirstTokenHandle; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  _DWORD v28[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v29; // [rsp+68h] [rbp-8h]
  unsigned __int8 Equal; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+58h] BYREF

  v25 = 0;
  v24 = 0;
  v31 = 0;
  v28[1] = 0;
  v27 = 0;
  FirstTokenHandle = 0;
  Equal = 0;
  if ( (int)BaseSrvGetUserToken(a2, 0, &FirstTokenHandle) < 0 )
    return 3221225485LL;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  ConsoleRecord = BaseSrvGetConsoleRecord(*(_QWORD *)(a1 + 8), &v25);
  v6 = v25;
  v7 = ConsoleRecord;
  if ( ConsoleRecord >= 0 )
  {
    v7 = NtCompareTokens(FirstTokenHandle, *(HANDLE *)(v25 + 80), &Equal);
    NtClose(FirstTokenHandle);
    if ( v7 < 0 || !Equal )
    {
      v7 = -1073741811;
      goto LABEL_55;
    }
    v8 = *(_QWORD *)(v6 + 72);
    if ( *(_DWORD *)(v8 + 8) != 1 && *(_DWORD *)(v8 + 8) != 2 )
    {
      if ( *(_DWORD *)(v8 + 8) == 4 || *(_DWORD *)(v8 + 8) == 8 )
      {
        v28[0] = 16;
        v29 = v8;
        if ( (unsigned int)BaseSrvCopyCommand(a1, v28) )
        {
          v7 = BaseSrvDupStandardHandles(*(HANDLE *)(v6 + 16));
          if ( v7 >= 0 )
          {
            v7 = BaseSrvCreatePairWaitHandles(&v24, &v31);
            if ( v7 >= 0 )
            {
              v12 = v31;
              *(_QWORD *)(a1 + 24) = v31;
              *(_QWORD *)(v8 + 16) = v12;
              *(_QWORD *)(v8 + 24) = v24;
              *(_DWORD *)(v8 + 8) = 1;
              *(_WORD *)(a1 + 174) = 4;
              v13 = *(void **)(v6 + 32);
              if ( v13 )
                NtSetEvent(v13, 0);
            }
            else
            {
              BaseSrvCloseStandardHandles(*(HANDLE *)(v6 + 16));
            }
          }
        }
        else
        {
          v7 = -1073741801;
        }
      }
      goto LABEL_12;
    }
    DOSRecord = BaseSrvAllocateDOSRecord();
    v15 = DOSRecord;
    if ( !DOSRecord )
    {
      v7 = -1073741801;
      goto LABEL_12;
    }
    v28[0] = 16;
    v29 = DOSRecord;
    if ( !(unsigned int)BaseSrvCopyCommand(a1, v28) )
    {
      v7 = -1073741801;
LABEL_26:
      BaseSrvFreeDOSRecord(v15);
      goto LABEL_12;
    }
    v7 = BaseSrvCreatePairWaitHandles(&v24, &v31);
    if ( v7 < 0 )
      goto LABEL_26;
    *(_QWORD *)(a1 + 24) = v31;
    *(_QWORD *)(v15 + 24) = v24;
    *(_QWORD *)(v15 + 16) = v31;
    v7 = BaseSrvDupStandardHandles(*(HANDLE *)(v6 + 16));
    if ( v7 < 0 )
    {
      v16 = *(void **)(v15 + 24);
      if ( v16 )
        NtClose(v16);
      v17 = *(void **)(v15 + 16);
      if ( v17 )
      {
        NtDuplicateObject(*(HANDLE *)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL), v17, 0, 0, 0, 0, 1u);
        v6 = v25;
      }
      *(_QWORD *)(v15 + 24) = 0;
      *(_QWORD *)(v15 + 16) = 0;
      goto LABEL_26;
    }
    BaseSrvAddDOSRecord(v6, v15);
    *(_WORD *)(a1 + 174) = 4;
    if ( *(_DWORD *)(v6 + 40) )
    {
      v18 = *(void **)(v6 + 32);
      if ( v18 )
        NtSetEvent(v18, 0);
    }
    *(_DWORD *)(v15 + 8) = 1;
  }
LABEL_12:
  if ( !v6 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, 0x60u);
    v10 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, 0x60u);
      v11 = BaseSrvAllocateDOSRecord();
      v10[9] = v11;
      if ( v11 )
      {
        v7 = CsrLockProcessByClientId(a2, &v27);
        if ( v7 < 0 )
        {
          BaseSrvFreeConsoleRecord(v10);
          goto LABEL_55;
        }
        *((_DWORD *)v10 + 12) = *(_DWORD *)(v27 + 88);
        CsrUnlockProcess(v27);
        v10[10] = FirstTokenHandle;
        v28[0] = *(_DWORD *)(a1 + 16);
        v29 = v10[9];
        if ( (unsigned int)BaseSrvCopyCommand(a1, v28) )
        {
          v19 = *(_QWORD *)(a1 + 8);
          v20 = DOSHead;
          v10[1] = v19;
          if ( v19 )
          {
            v22 = 0;
          }
          else
          {
            v21 = v20;
            v22 = dword_180013060;
            if ( byte_18001367C )
            {
              while ( v21 )
              {
                if ( v21[1] || *((_DWORD *)v21 + 13) != v22 )
                {
                  v21 = (_QWORD *)*v21;
                }
                else
                {
                  v21 = v20;
                  if ( !++v22 )
                  {
                    byte_18001367C = 1;
                    v22 = 1;
                  }
                }
              }
            }
            dword_180013060 = v22 + 1;
            if ( v22 == -1 )
            {
              byte_18001367C = 1;
              dword_180013060 = 1;
            }
          }
          v7 = 0;
          *((_DWORD *)v10 + 13) = v22;
          *(_DWORD *)a1 = v22;
          v23 = v10[9];
          DOSHead = v10;
          *(_DWORD *)(v23 + 8) = 1;
          *v10 = v20;
          *(_WORD *)(a1 + 174) = 1;
          goto LABEL_55;
        }
      }
      BaseSrvFreeConsoleRecord(v10);
    }
    v7 = -1073741801;
  }
LABEL_55:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008644  mov     [rsp-38h+arg_0], rbx
0x180008649  push    rbp
0x18000864a  push    rsi
0x18000864b  push    rdi
0x18000864c  push    r12
0x18000864e  push    r13
0x180008650  push    r14
0x180008652  push    r15
0x180008654  mov     rbp, rsp
0x180008657  sub     rsp, 70h
0x18000865b  xor     r13d, r13d
0x18000865e  lea     r8, [rbp+FirstTokenHandle]
0x180008662  mov     r12, rdx
0x180008665  mov     [rbp+var_28], r13
0x180008669  mov     r14, rcx
0x18000866c  mov     [rbp+var_30], r13
0x180008670  mov     rcx, r12
0x180008673  mov     [rbp+arg_18], r13
0x180008677  xor     edx, edx
0x180008679  mov     [rbp+var_C], r13d
0x18000867d  mov     [rbp+var_18], r13
0x180008681  mov     [rbp+FirstTokenHandle], r13
0x180008685  mov     [rbp+Equal], r13b
0x180008689  call    BaseSrvGetUserToken
0x18000868e  test    eax, eax
0x180008690  jns     short loc_18000869C
0x180008692  mov     eax, 0C000000Dh
0x180008697  jmp     loc_180008A8F
0x18000869c  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x1800086a3  call    cs:__imp_RtlEnterCriticalSection
0x1800086aa  nop     dword ptr [rax+rax+00h]
0x1800086af  mov     rcx, [r14+8]
0x1800086b3  lea     rdx, [rbp+var_28]
0x1800086b7  call    BaseSrvGetConsoleRecord
0x1800086bc  mov     rsi, [rbp+var_28]
0x1800086c0  mov     ebx, eax
0x1800086c2  mov     r15d, 1
0x1800086c8  test    eax, eax
0x1800086ca  js      loc_18000875F
0x1800086d0  mov     rdx, [rsi+50h]; SecondTokenHandle
0x1800086d4  lea     r8, [rbp+Equal]; Equal
0x1800086d8  mov     rcx, [rbp+FirstTokenHandle]; FirstTokenHandle
0x1800086dc  call    cs:__imp_NtCompareTokens
0x1800086e3  nop     dword ptr [rax+rax+00h]
0x1800086e8  mov     rcx, [rbp+FirstTokenHandle]; Handle
0x1800086ec  mov     ebx, eax
0x1800086ee  call    cs:__imp_NtClose
0x1800086f5  nop     dword ptr [rax+rax+00h]
0x1800086fa  test    ebx, ebx
0x1800086fc  js      loc_180008982
0x180008702  cmp     [rbp+Equal], r13b
0x180008706  jz      loc_180008982
0x18000870c  mov     rdi, [rsi+48h]
0x180008710  mov     ecx, [rdi+8]
0x180008713  sub     ecx, r15d
0x180008716  jz      loc_180008865
0x18000871c  sub     ecx, r15d
0x18000871f  jz      loc_180008865
0x180008725  mov     r15d, 4
0x18000872b  sub     ecx, 2
0x18000872e  jz      short loc_180008735
0x180008730  cmp     ecx, r15d
0x180008733  jnz     short loc_180008759
0x180008735  lea     rdx, [rbp+var_10]
0x180008739  mov     [rbp+var_10], 10h
0x180008740  mov     rcx, r14
0x180008743  mov     [rbp+var_8], rdi
0x180008747  call    BaseSrvCopyCommand
0x18000874c  test    eax, eax
0x18000874e  jnz     loc_1800087E8
0x180008754  mov     ebx, 0C0000017h
0x180008759  mov     r15d, 1
0x18000875f  test    rsi, rsi
0x180008762  jnz     loc_180008A7A
0x180008768  mov     rcx, gs:60h
0x180008771  lea     ebx, [rsi+60h]
0x180008774  mov     edx, cs:BaseSrvTag
0x18000877a  mov     r8d, ebx; Size
0x18000877d  add     edx, 40000h; Flags
0x180008783  mov     rcx, [rcx+30h]; HeapHandle
0x180008787  call    cs:__imp_RtlAllocateHeap
0x18000878e  nop     dword ptr [rax+rax+00h]
0x180008793  mov     rdi, rax
0x180008796  test    rax, rax
0x180008799  jz      loc_180008A75
0x18000879f  mov     r8d, ebx; Size
0x1800087a2  xor     edx, edx; Val
0x1800087a4  mov     rcx, rax; void *
0x1800087a7  call    memset_0
0x1800087ac  call    BaseSrvAllocateDOSRecord
0x1800087b1  mov     [rdi+48h], rax
0x1800087b5  test    rax, rax
0x1800087b8  jz      loc_180008A6D
0x1800087be  lea     rdx, [rbp+var_18]
0x1800087c2  mov     rcx, r12
0x1800087c5  call    cs:__imp_CsrLockProcessByClientId
0x1800087cc  nop     dword ptr [rax+rax+00h]
0x1800087d1  mov     ebx, eax
0x1800087d3  test    eax, eax
0x1800087d5  jns     loc_18000898C
0x1800087db  mov     rcx, rdi; P
0x1800087de  call    BaseSrvFreeConsoleRecord
0x1800087e3  jmp     loc_180008A7A
0x1800087e8  mov     rcx, [rsi+10h]; SourceProcessHandle
0x1800087ec  mov     rdx, rdi
0x1800087ef  call    BaseSrvDupStandardHandles
0x1800087f4  mov     ebx, eax
0x1800087f6  test    eax, eax
0x1800087f8  js      loc_180008759
0x1800087fe  lea     rdx, [rbp+arg_18]
0x180008802  lea     rcx, [rbp+var_30]
0x180008806  call    BaseSrvCreatePairWaitHandles
0x18000880b  mov     ebx, eax
0x18000880d  test    eax, eax
0x18000880f  jns     short loc_180008822
0x180008811  mov     rcx, [rsi+10h]; SourceProcessHandle
0x180008815  mov     rdx, rdi
0x180008818  call    BaseSrvCloseStandardHandles
0x18000881d  jmp     loc_180008759
0x180008822  mov     rax, [rbp+arg_18]
0x180008826  mov     [r14+18h], rax
0x18000882a  mov     [rdi+10h], rax
0x18000882e  mov     rax, [rbp+var_30]
0x180008832  mov     [rdi+18h], rax
0x180008836  mov     dword ptr [rdi+8], 1
0x18000883d  mov     [r14+0AEh], r15w
0x180008845  mov     rcx, [rsi+20h]; EventHandle
0x180008849  test    rcx, rcx
0x18000884c  jz      loc_180008759
0x180008852  xor     edx, edx; PreviousState
0x180008854  call    cs:__imp_NtSetEvent
0x18000885b  nop     dword ptr [rax+rax+00h]
0x180008860  jmp     loc_180008759
0x180008865  call    BaseSrvAllocateDOSRecord
0x18000886a  mov     rdi, rax
0x18000886d  test    rax, rax
0x180008870  jnz     short loc_18000887C
0x180008872  mov     ebx, 0C0000017h
0x180008877  jmp     loc_18000875F
0x18000887c  lea     rdx, [rbp+var_10]
0x180008880  mov     [rbp+var_10], 10h
0x180008887  mov     rcx, r14
0x18000888a  mov     [rbp+var_8], rdi
0x18000888e  call    BaseSrvCopyCommand
0x180008893  test    eax, eax
0x180008895  jnz     short loc_1800088A9
0x180008897  mov     ebx, 0C0000017h
0x18000889c  mov     rcx, rdi
0x18000889f  call    BaseSrvFreeDOSRecord
0x1800088a4  jmp     loc_18000875F
0x1800088a9  lea     rdx, [rbp+arg_18]
0x1800088ad  lea     rcx, [rbp+var_30]
0x1800088b1  call    BaseSrvCreatePairWaitHandles
0x1800088b6  mov     ebx, eax
0x1800088b8  test    eax, eax
0x1800088ba  js      short loc_18000889C
0x1800088bc  mov     rax, [rbp+arg_18]
0x1800088c0  mov     rdx, rdi
0x1800088c3  mov     [r14+18h], rax
0x1800088c7  mov     rax, [rbp+var_30]
0x1800088cb  mov     [rdi+18h], rax
0x1800088cf  mov     rax, [rbp+arg_18]
0x1800088d3  mov     [rdi+10h], rax
0x1800088d7  mov     rcx, [rsi+10h]; SourceProcessHandle
0x1800088db  call    BaseSrvDupStandardHandles
0x1800088e0  mov     ebx, eax
0x1800088e2  test    eax, eax
0x1800088e4  jns     short loc_180008947
0x1800088e6  mov     rcx, [rdi+18h]; Handle
0x1800088ea  test    rcx, rcx
0x1800088ed  jz      short loc_1800088FB
0x1800088ef  call    cs:__imp_NtClose
0x1800088f6  nop     dword ptr [rax+rax+00h]
0x1800088fb  mov     rdx, [rdi+10h]; SourceHandle
0x1800088ff  test    rdx, rdx
0x180008902  jz      short loc_18000893A
0x180008904  mov     rax, gs:70h
0x18000890d  xor     r9d, r9d; TargetHandle
0x180008910  mov     [rsp+70h+Options], r15d; Options
0x180008915  xor     r8d, r8d; TargetProcessHandle
0x180008918  mov     [rsp+70h+HandleAttributes], r13d; HandleAttributes
0x18000891d  mov     [rsp+70h+DesiredAccess], r13d; DesiredAccess
0x180008922  mov     rcx, [rax+38h]
0x180008926  mov     rcx, [rcx+50h]; SourceProcessHandle
0x18000892a  call    cs:__imp_NtDuplicateObject
0x180008931  nop     dword ptr [rax+rax+00h]
0x180008936  mov     rsi, [rbp+var_28]
0x18000893a  mov     [rdi+18h], r13
0x18000893e  mov     [rdi+10h], r13
0x180008942  jmp     loc_18000889C
0x180008947  mov     rdx, rdi
0x18000894a  mov     rcx, rsi
0x18000894d  call    BaseSrvAddDOSRecord
0x180008952  mov     word ptr [r14+0AEh], 4
0x18000895c  cmp     [rsi+28h], r13d
0x180008960  jz      short loc_180008979
0x180008962  mov     rcx, [rsi+20h]; EventHandle
0x180008966  test    rcx, rcx
0x180008969  jz      short loc_180008979
0x18000896b  xor     edx, edx; PreviousState
0x18000896d  call    cs:__imp_NtSetEvent
0x180008974  nop     dword ptr [rax+rax+00h]
0x180008979  mov     [rdi+8], r15d
0x18000897d  jmp     loc_18000875F
0x180008982  mov     ebx, 0C000000Dh
0x180008987  jmp     loc_180008A7A
0x18000898c  mov     rax, [rbp+var_18]
0x180008990  mov     ecx, [rax+58h]
0x180008993  mov     [rdi+30h], ecx
0x180008996  mov     rcx, [rbp+var_18]
0x18000899a  call    cs:__imp_CsrUnlockProcess
0x1800089a1  nop     dword ptr [rax+rax+00h]
0x1800089a6  mov     rax, [rbp+FirstTokenHandle]
0x1800089aa  lea     rdx, [rbp+var_10]
0x1800089ae  mov     [rdi+50h], rax
0x1800089b2  mov     rcx, r14
0x1800089b5  mov     eax, [r14+10h]
0x1800089b9  mov     [rbp+var_10], eax
0x1800089bc  mov     rax, [rdi+48h]
0x1800089c0  mov     [rbp+var_8], rax
0x1800089c4  call    BaseSrvCopyCommand
0x1800089c9  test    eax, eax
0x1800089cb  jz      loc_180008A6D
0x1800089d1  mov     rax, [r14+8]
0x1800089d5  mov     rdx, rdi
0x1800089d8  mov     r8, cs:DOSHead
0x1800089df  mov     [rdi+8], rax
0x1800089e3  test    rax, rax
0x1800089e6  jnz     short loc_180008A40
0x1800089e8  cmp     cs:byte_18001367C, r13b
0x1800089ef  mov     rax, r8
0x1800089f2  mov     ecx, cs:dword_180013060
0x1800089f8  jz      short loc_180008A23
0x1800089fa  jmp     short loc_180008A1E
0x1800089fc  cmp     [rax+8], r13
0x180008a00  jnz     short loc_180008A1B
0x180008a02  cmp     [rax+34h], ecx
0x180008a05  jnz     short loc_180008A1B
0x180008a07  mov     rax, r8
0x180008a0a  add     ecx, r15d
0x180008a0d  jnz     short loc_180008A1E
0x180008a0f  mov     cs:byte_18001367C, r15b
0x180008a16  mov     ecx, r15d
0x180008a19  jmp     short loc_180008A1E
0x180008a1b  mov     rax, [rax]
0x180008a1e  test    rax, rax
0x180008a21  jnz     short loc_1800089FC
0x180008a23  lea     eax, [rcx+1]
0x180008a26  mov     cs:dword_180013060, eax
0x180008a2c  test    eax, eax
0x180008a2e  jnz     short loc_180008A43
0x180008a30  mov     cs:byte_18001367C, r15b
0x180008a37  mov     cs:dword_180013060, r15d
0x180008a3e  jmp     short loc_180008A43
0x180008a40  mov     ecx, r13d
0x180008a43  mov     eax, 34h ; '4'
0x180008a48  mov     ebx, r13d
0x180008a4b  mov     [rax+rdx], ecx
0x180008a4e  mov     [r14], ecx
0x180008a51  mov     rax, [rdi+48h]
0x180008a55  mov     cs:DOSHead, rdi
0x180008a5c  mov     [rax+8], r15d
0x180008a60  mov     [rdi], r8
0x180008a63  mov     [r14+0AEh], r15w
0x180008a6b  jmp     short loc_180008A7A
0x180008a6d  mov     rcx, rdi; P
0x180008a70  call    BaseSrvFreeConsoleRecord
0x180008a75  mov     ebx, 0C0000017h
0x180008a7a  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008a81  call    cs:__imp_RtlLeaveCriticalSection
0x180008a88  nop     dword ptr [rax+rax+00h]
0x180008a8d  mov     eax, ebx
0x180008a8f  mov     rbx, [rsp+70h+arg_0]
0x180008a97  add     rsp, 70h
0x180008a9b  pop     r15
0x180008a9d  pop     r14
0x180008a9f  pop     r13
0x180008aa1  pop     r12
0x180008aa3  pop     rdi
0x180008aa4  pop     rsi
0x180008aa5  pop     rbp
0x180008aa6  retn
```
