# BaseSrvCheckDOS

- ea: `0x180008938`
- end: `0x180008d9b`
- name: `BaseSrvCheckDOS`
- size: `1123`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008e70`

## callees

- `0x18000835c`
- `0x1800087b0`
- `0x180008938`
- `0x1800093e8`
- `0x1800094cc`
- `0x18000996c`
- `0x180009a60`
- `0x18000a7d0`
- `0x18000a898`
- `0x18000ab84`
- `0x18000b42c`
- `0x18000db1d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008a7b`
- `ntdll!RtlAllocateHeap` at `0x180008a7b`
- `ntdll!NtClose` at `0x1800089e2`
- `ntdll!NtClose` at `0x180008be3`
- `ntdll!NtClose` at `0x1800089e2`
- `ntdll!NtClose` at `0x180008be3`
- `ntdll!RtlEnterCriticalSection` at `0x180008997`
- `ntdll!RtlEnterCriticalSection` at `0x180008997`
- `ntdll!RtlLeaveCriticalSection` at `0x180008d74`
- `ntdll!RtlLeaveCriticalSection` at `0x180008d74`
- `ntdll!NtDuplicateObject` at `0x180008c1e`
- `ntdll!NtDuplicateObject` at `0x180008c1e`
- `ntdll!NtSetEvent` at `0x180008b48`
- `ntdll!NtSetEvent` at `0x180008c5d`
- `ntdll!NtSetEvent` at `0x180008b48`
- `ntdll!NtSetEvent` at `0x180008c5d`
- `ntdll!NtCompareTokens` at `0x1800089d0`
- `ntdll!NtCompareTokens` at `0x1800089d0`
- `CSRSRV!CsrUnlockProcess` at `0x180008c8a`
- `CSRSRV!CsrUnlockProcess` at `0x180008c8a`
- `CSRSRV!CsrLockProcessByClientId` at `0x180008ab9`
- `CSRSRV!CsrLockProcessByClientId` at `0x180008ab9`

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
  _QWORD *v20; // rdx
  int v21; // ecx
  _QWORD *v22; // rax
  __int64 v23; // rax
  __int64 v24; // [rsp+40h] [rbp-30h] BYREF
  HANDLE FirstTokenHandle; // [rsp+48h] [rbp-28h] BYREF
  __int64 v26; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  _DWORD v28[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v29; // [rsp+68h] [rbp-8h]
  unsigned __int8 Equal; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+58h] BYREF

  v27 = 0;
  v24 = 0;
  v31 = 0;
  v28[1] = 0;
  v26 = 0;
  FirstTokenHandle = 0;
  Equal = 0;
  if ( (int)BaseSrvGetUserToken(a2, 0, &FirstTokenHandle) < 0 )
    return 3221225485LL;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  ConsoleRecord = BaseSrvGetConsoleRecord(*(_QWORD *)(a1 + 8), &v27);
  v6 = v27;
  v7 = ConsoleRecord;
  if ( ConsoleRecord >= 0 )
  {
    v7 = NtCompareTokens(FirstTokenHandle, *(HANDLE *)(v27 + 80), &Equal);
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
        if ( (unsigned int)BaseSrvCopyCommand(a1, (__int64)v28) )
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
    if ( !(unsigned int)BaseSrvCopyCommand(a1, (__int64)v28) )
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
        NtDuplicateObject(*(HANDLE *)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL), v17, 0, 0, 0, 0, 1u);
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
        v7 = CsrLockProcessByClientId(a2, &v26);
        if ( v7 < 0 )
        {
          BaseSrvFreeConsoleRecord(v10);
          goto LABEL_55;
        }
        *((_DWORD *)v10 + 12) = *(_DWORD *)(v26 + 88);
        CsrUnlockProcess(v26);
        v10[10] = FirstTokenHandle;
        v28[0] = *(_DWORD *)(a1 + 16);
        v29 = v10[9];
        if ( (unsigned int)BaseSrvCopyCommand(a1, (__int64)v28) )
        {
          v19 = *(_QWORD *)(a1 + 8);
          v20 = DOSHead;
          v10[1] = v19;
          if ( v19 )
          {
            v21 = 0;
          }
          else
          {
            v21 = dword_180013060;
            if ( byte_18001367C )
            {
              v22 = v20;
              while ( v22 )
              {
                if ( v22[1] || *((_DWORD *)v22 + 13) != v21 )
                {
                  v22 = (_QWORD *)*v22;
                }
                else
                {
                  v22 = v20;
                  if ( !++v21 )
                  {
                    byte_18001367C = 1;
                    v21 = 1;
                  }
                }
              }
            }
            dword_180013060 = v21 + 1;
            if ( v21 == -1 )
            {
              byte_18001367C = 1;
              dword_180013060 = 1;
            }
          }
          v7 = 0;
          *((_DWORD *)v10 + 13) = v21;
          *(_DWORD *)a1 = v21;
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
0x180008938  mov     [rsp-38h+arg_0], rbx
0x18000893d  push    rbp
0x18000893e  push    rsi
0x18000893f  push    rdi
0x180008940  push    r12
0x180008942  push    r13
0x180008944  push    r14
0x180008946  push    r15
0x180008948  mov     rbp, rsp
0x18000894b  sub     rsp, 70h
0x18000894f  xor     r13d, r13d
0x180008952  lea     r8, [rbp+FirstTokenHandle]
0x180008956  mov     r12, rdx
0x180008959  mov     [rbp+var_18], r13
0x18000895d  mov     r14, rcx
0x180008960  mov     [rbp+var_30], r13
0x180008964  mov     rcx, r12
0x180008967  mov     [rbp+arg_18], r13
0x18000896b  xor     edx, edx
0x18000896d  mov     [rbp+var_C], r13d
0x180008971  mov     [rbp+var_20], r13
0x180008975  mov     [rbp+FirstTokenHandle], r13
0x180008979  mov     [rbp+Equal], r13b
0x18000897d  call    BaseSrvGetUserToken
0x180008982  test    eax, eax
0x180008984  jns     short loc_180008990
0x180008986  mov     eax, 0C000000Dh
0x18000898b  jmp     loc_180008D82
0x180008990  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008997  call    cs:__imp_RtlEnterCriticalSection
0x18000899e  nop     dword ptr [rax+rax+00h]
0x1800089a3  mov     rcx, [r14+8]
0x1800089a7  lea     rdx, [rbp+var_18]
0x1800089ab  call    BaseSrvGetConsoleRecord
0x1800089b0  mov     rsi, [rbp+var_18]
0x1800089b4  mov     ebx, eax
0x1800089b6  mov     r15d, 1
0x1800089bc  test    eax, eax
0x1800089be  js      loc_180008A53
0x1800089c4  mov     rdx, [rsi+50h]; SecondTokenHandle
0x1800089c8  lea     r8, [rbp+Equal]; Equal
0x1800089cc  mov     rcx, [rbp+FirstTokenHandle]; FirstTokenHandle
0x1800089d0  call    cs:__imp_NtCompareTokens
0x1800089d7  nop     dword ptr [rax+rax+00h]
0x1800089dc  mov     rcx, [rbp+FirstTokenHandle]; Handle
0x1800089e0  mov     ebx, eax
0x1800089e2  call    cs:__imp_NtClose
0x1800089e9  nop     dword ptr [rax+rax+00h]
0x1800089ee  test    ebx, ebx
0x1800089f0  js      loc_180008C72
0x1800089f6  cmp     [rbp+Equal], r13b
0x1800089fa  jz      loc_180008C72
0x180008a00  mov     rdi, [rsi+48h]
0x180008a04  mov     ecx, [rdi+8]
0x180008a07  sub     ecx, r15d
0x180008a0a  jz      loc_180008B59
0x180008a10  sub     ecx, r15d
0x180008a13  jz      loc_180008B59
0x180008a19  mov     r15d, 4
0x180008a1f  sub     ecx, 2
0x180008a22  jz      short loc_180008A29
0x180008a24  cmp     ecx, r15d
0x180008a27  jnz     short loc_180008A4D
0x180008a29  lea     rdx, [rbp+var_10]
0x180008a2d  mov     [rbp+var_10], 10h
0x180008a34  mov     rcx, r14
0x180008a37  mov     [rbp+var_8], rdi
0x180008a3b  call    BaseSrvCopyCommand
0x180008a40  test    eax, eax
0x180008a42  jnz     loc_180008ADC
0x180008a48  mov     ebx, 0C0000017h
0x180008a4d  mov     r15d, 1
0x180008a53  test    rsi, rsi
0x180008a56  jnz     loc_180008D6D
0x180008a5c  mov     rcx, gs:60h
0x180008a65  lea     ebx, [rsi+60h]
0x180008a68  mov     edx, cs:BaseSrvTag
0x180008a6e  mov     r8d, ebx; Size
0x180008a71  add     edx, 40000h; Flags
0x180008a77  mov     rcx, [rcx+30h]; HeapHandle
0x180008a7b  call    cs:__imp_RtlAllocateHeap
0x180008a82  nop     dword ptr [rax+rax+00h]
0x180008a87  mov     rdi, rax
0x180008a8a  test    rax, rax
0x180008a8d  jz      loc_180008D68
0x180008a93  mov     r8d, ebx; Size
0x180008a96  xor     edx, edx; Val
0x180008a98  mov     rcx, rax; void *
0x180008a9b  call    memset_0
0x180008aa0  call    BaseSrvAllocateDOSRecord
0x180008aa5  mov     [rdi+48h], rax
0x180008aa9  test    rax, rax
0x180008aac  jz      loc_180008D60
0x180008ab2  lea     rdx, [rbp+var_20]
0x180008ab6  mov     rcx, r12
0x180008ab9  call    cs:__imp_CsrLockProcessByClientId
0x180008ac0  nop     dword ptr [rax+rax+00h]
0x180008ac5  mov     ebx, eax
0x180008ac7  test    eax, eax
0x180008ac9  jns     loc_180008C7C
0x180008acf  mov     rcx, rdi; P
0x180008ad2  call    BaseSrvFreeConsoleRecord
0x180008ad7  jmp     loc_180008D6D
0x180008adc  mov     rcx, [rsi+10h]; SourceProcessHandle
0x180008ae0  mov     rdx, rdi
0x180008ae3  call    BaseSrvDupStandardHandles
0x180008ae8  mov     ebx, eax
0x180008aea  test    eax, eax
0x180008aec  js      loc_180008A4D
0x180008af2  lea     rdx, [rbp+arg_18]
0x180008af6  lea     rcx, [rbp+var_30]
0x180008afa  call    BaseSrvCreatePairWaitHandles
0x180008aff  mov     ebx, eax
0x180008b01  test    eax, eax
0x180008b03  jns     short loc_180008B16
0x180008b05  mov     rcx, [rsi+10h]; SourceProcessHandle
0x180008b09  mov     rdx, rdi
0x180008b0c  call    BaseSrvCloseStandardHandles
0x180008b11  jmp     loc_180008A4D
0x180008b16  mov     rax, [rbp+arg_18]
0x180008b1a  mov     [r14+18h], rax
0x180008b1e  mov     [rdi+10h], rax
0x180008b22  mov     rax, [rbp+var_30]
0x180008b26  mov     [rdi+18h], rax
0x180008b2a  mov     dword ptr [rdi+8], 1
0x180008b31  mov     [r14+0AEh], r15w
0x180008b39  mov     rcx, [rsi+20h]; EventHandle
0x180008b3d  test    rcx, rcx
0x180008b40  jz      loc_180008A4D
0x180008b46  xor     edx, edx; PreviousState
0x180008b48  call    cs:__imp_NtSetEvent
0x180008b4f  nop     dword ptr [rax+rax+00h]
0x180008b54  jmp     loc_180008A4D
0x180008b59  call    BaseSrvAllocateDOSRecord
0x180008b5e  mov     rdi, rax
0x180008b61  test    rax, rax
0x180008b64  jnz     short loc_180008B70
0x180008b66  mov     ebx, 0C0000017h
0x180008b6b  jmp     loc_180008A53
0x180008b70  lea     rdx, [rbp+var_10]
0x180008b74  mov     [rbp+var_10], 10h
0x180008b7b  mov     rcx, r14
0x180008b7e  mov     [rbp+var_8], rdi
0x180008b82  call    BaseSrvCopyCommand
0x180008b87  test    eax, eax
0x180008b89  jnz     short loc_180008B9D
0x180008b8b  mov     ebx, 0C0000017h
0x180008b90  mov     rcx, rdi
0x180008b93  call    BaseSrvFreeDOSRecord
0x180008b98  jmp     loc_180008A53
0x180008b9d  lea     rdx, [rbp+arg_18]
0x180008ba1  lea     rcx, [rbp+var_30]
0x180008ba5  call    BaseSrvCreatePairWaitHandles
0x180008baa  mov     ebx, eax
0x180008bac  test    eax, eax
0x180008bae  js      short loc_180008B90
0x180008bb0  mov     rax, [rbp+arg_18]
0x180008bb4  mov     rdx, rdi
0x180008bb7  mov     [r14+18h], rax
0x180008bbb  mov     rax, [rbp+var_30]
0x180008bbf  mov     [rdi+18h], rax
0x180008bc3  mov     rax, [rbp+arg_18]
0x180008bc7  mov     [rdi+10h], rax
0x180008bcb  mov     rcx, [rsi+10h]; SourceProcessHandle
0x180008bcf  call    BaseSrvDupStandardHandles
0x180008bd4  mov     ebx, eax
0x180008bd6  test    eax, eax
0x180008bd8  jns     short loc_180008C37
0x180008bda  mov     rcx, [rdi+18h]; Handle
0x180008bde  test    rcx, rcx
0x180008be1  jz      short loc_180008BEF
0x180008be3  call    cs:__imp_NtClose
0x180008bea  nop     dword ptr [rax+rax+00h]
0x180008bef  mov     rdx, [rdi+10h]; SourceHandle
0x180008bf3  test    rdx, rdx
0x180008bf6  jz      short loc_180008C2A
0x180008bf8  mov     rax, gs:70h
0x180008c01  xor     r9d, r9d; TargetHandle
0x180008c04  mov     [rsp+70h+Options], r15d; Options
0x180008c09  xor     r8d, r8d; TargetProcessHandle
0x180008c0c  mov     [rsp+70h+HandleAttributes], r13d; HandleAttributes
0x180008c11  mov     [rsp+70h+DesiredAccess], r13d; DesiredAccess
0x180008c16  mov     rcx, [rax+38h]
0x180008c1a  mov     rcx, [rcx+50h]; SourceProcessHandle
0x180008c1e  call    cs:__imp_NtDuplicateObject
0x180008c25  nop     dword ptr [rax+rax+00h]
0x180008c2a  mov     [rdi+18h], r13
0x180008c2e  mov     [rdi+10h], r13
0x180008c32  jmp     loc_180008B90
0x180008c37  mov     rdx, rdi
0x180008c3a  mov     rcx, rsi
0x180008c3d  call    BaseSrvAddDOSRecord
0x180008c42  mov     word ptr [r14+0AEh], 4
0x180008c4c  cmp     [rsi+28h], r13d
0x180008c50  jz      short loc_180008C69
0x180008c52  mov     rcx, [rsi+20h]; EventHandle
0x180008c56  test    rcx, rcx
0x180008c59  jz      short loc_180008C69
0x180008c5b  xor     edx, edx; PreviousState
0x180008c5d  call    cs:__imp_NtSetEvent
0x180008c64  nop     dword ptr [rax+rax+00h]
0x180008c69  mov     [rdi+8], r15d
0x180008c6d  jmp     loc_180008A53
0x180008c72  mov     ebx, 0C000000Dh
0x180008c77  jmp     loc_180008D6D
0x180008c7c  mov     rax, [rbp+var_20]
0x180008c80  mov     ecx, [rax+58h]
0x180008c83  mov     [rdi+30h], ecx
0x180008c86  mov     rcx, [rbp+var_20]
0x180008c8a  call    cs:__imp_CsrUnlockProcess
0x180008c91  nop     dword ptr [rax+rax+00h]
0x180008c96  mov     rax, [rbp+FirstTokenHandle]
0x180008c9a  lea     rdx, [rbp+var_10]
0x180008c9e  mov     [rdi+50h], rax
0x180008ca2  mov     rcx, r14
0x180008ca5  mov     eax, [r14+10h]
0x180008ca9  mov     [rbp+var_10], eax
0x180008cac  mov     rax, [rdi+48h]
0x180008cb0  mov     [rbp+var_8], rax
0x180008cb4  call    BaseSrvCopyCommand
0x180008cb9  test    eax, eax
0x180008cbb  jz      loc_180008D60
0x180008cc1  mov     rax, [r14+8]
0x180008cc5  mov     rdx, cs:DOSHead
0x180008ccc  mov     [rdi+8], rax
0x180008cd0  test    rax, rax
0x180008cd3  jnz     short loc_180008D30
0x180008cd5  cmp     cs:byte_18001367C, r13b
0x180008cdc  mov     ecx, cs:dword_180013060
0x180008ce2  jz      short loc_180008D13
0x180008ce4  mov     rax, rdx
0x180008ce7  test    rdx, rdx
0x180008cea  jz      short loc_180008D13
0x180008cec  cmp     [rax+8], r13
0x180008cf0  jnz     short loc_180008D0B
0x180008cf2  cmp     [rax+34h], ecx
0x180008cf5  jnz     short loc_180008D0B
0x180008cf7  mov     rax, rdx
0x180008cfa  add     ecx, 1
0x180008cfd  jnz     short loc_180008D0E
0x180008cff  mov     cs:byte_18001367C, r15b
0x180008d06  mov     ecx, r15d
0x180008d09  jmp     short loc_180008D0E
0x180008d0b  mov     rax, [rax]
0x180008d0e  test    rax, rax
0x180008d11  jnz     short loc_180008CEC
0x180008d13  lea     eax, [rcx+1]
0x180008d16  mov     cs:dword_180013060, eax
0x180008d1c  test    eax, eax
0x180008d1e  jnz     short loc_180008D33
0x180008d20  mov     cs:byte_18001367C, r15b
0x180008d27  mov     cs:dword_180013060, r15d
0x180008d2e  jmp     short loc_180008D33
0x180008d30  mov     ecx, r13d
0x180008d33  mov     eax, 34h ; '4'
0x180008d38  mov     r8, rdi
0x180008d3b  mov     ebx, r13d
0x180008d3e  mov     [rdi+rax], ecx
0x180008d41  mov     [r14], ecx
0x180008d44  mov     rax, [rdi+48h]
0x180008d48  mov     cs:DOSHead, rdi
0x180008d4f  mov     [rax+8], r15d
0x180008d53  mov     [rdi], rdx
0x180008d56  mov     [r14+0AEh], r15w
0x180008d5e  jmp     short loc_180008D6D
0x180008d60  mov     rcx, rdi; P
0x180008d63  call    BaseSrvFreeConsoleRecord
0x180008d68  mov     ebx, 0C0000017h
0x180008d6d  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008d74  call    cs:__imp_RtlLeaveCriticalSection
0x180008d7b  nop     dword ptr [rax+rax+00h]
0x180008d80  mov     eax, ebx
0x180008d82  mov     rbx, [rsp+70h+arg_0]
0x180008d8a  add     rsp, 70h
0x180008d8e  pop     r15
0x180008d90  pop     r14
0x180008d92  pop     r13
0x180008d94  pop     r12
0x180008d96  pop     rdi
0x180008d97  pop     rsi
0x180008d98  pop     rbp
0x180008d99  retn
```
