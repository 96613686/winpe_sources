# IoCallKernelDriverQueryLoop(ulong,uchar *,ulong,uchar * *,ulong *,int *)

- ea: `0x1800023f0`
- end: `0x1800027a5`
- name: `?IoCallKernelDriverQueryLoop@@YAJKPEAEKPEAPEAEPEAKPEAH@Z`
- size: `949`
- prototype: `int(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, int *)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001dd0`
- `0x180002bd0`
- `0x180012f40`
- `0x180018b80`
- `0x180018d90`
- `0x180018e90`
- `0x180019070`
- `0x1800192a0`

## callees

- `0x180002040`
- `0x1800022cc`
- `0x1800023f0`
- `0x1800041d0`
- `0x18001b79d`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000260d`
- `ntdll!RtlAllocateHeap` at `0x18000260d`
- `ntdll!NtDeviceIoControlFile` at `0x18000253e`
- `ntdll!NtDeviceIoControlFile` at `0x18000253e`
- `ntdll!RtlFreeHeap` at `0x1800025ef`
- `ntdll!RtlFreeHeap` at `0x1800025ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d1`

## pseudocode

```c
NTSTATUS __fastcall IoCallKernelDriverQueryLoop(
        int a1,
        unsigned __int8 *a2,
        unsigned int a3,
        PVOID *a4,
        unsigned int *a5,
        int *a6)
{
  NTSTATUS v6; // r15d
  unsigned int v7; // eax
  NTSTATUS result; // eax
  PVOID Heap; // rsi
  unsigned int v12; // r13d
  unsigned __int8 *InputBuffer; // r14
  ULONG InputBufferLength; // r12d
  ULONG OutputBufferLength; // ecx
  NTSTATUS *OutputBuffer; // r13
  NTSTATUS v17; // eax
  unsigned int Information; // r14d
  unsigned int v19; // [rsp+50h] [rbp-78h]
  unsigned int v20; // [rsp+54h] [rbp-74h] BYREF
  unsigned int *v21; // [rsp+58h] [rbp-70h]
  unsigned int v22; // [rsp+60h] [rbp-68h]
  int v23; // [rsp+64h] [rbp-64h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-60h] BYREF
  char Src; // [rsp+78h] [rbp-50h] BYREF
  char v26; // [rsp+80h] [rbp-48h] BYREF

  v6 = 0;
  v7 = a3;
  v22 = a3;
  v23 = a1;
  v21 = a5;
  v20 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a4 )
  {
    Heap = *a4;
    if ( *a4 )
    {
      v12 = *a5;
    }
    else
    {
      Heap = 0;
      v12 = 384;
    }
    v19 = v12;
    while ( 1 )
    {
      if ( !*a4 )
      {
        if ( Heap )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
        if ( !Heap )
          return -1073741801;
        v7 = v22;
        a1 = v23;
      }
      IoStatusBlock = 0;
      if ( a2 && v7 < 8 )
      {
        *v21 = v12;
LABEL_56:
        v6 = -1073741595;
        goto LABEL_57;
      }
      InputBuffer = (unsigned __int8 *)&v26;
      InputBufferLength = 8;
      if ( a2 )
      {
        InputBuffer = a2;
        InputBufferLength = v7;
      }
      *(_DWORD *)InputBuffer = 439041101;
      *((_DWORD *)InputBuffer + 1) = a1;
      if ( Heap && (OutputBufferLength = v12, v20 = v12, v12 >= 8) )
      {
        OutputBuffer = (NTSTATUS *)Heap;
      }
      else
      {
        OutputBufferLength = 8;
        OutputBuffer = (NTSTATUS *)&Src;
        v20 = 8;
      }
      if ( !g_hIoDevice )
      {
        EnterCriticalSection(&g_csIoInitialize);
        if ( !g_hIoDevice )
          v6 = _IoOpenDevice();
        LeaveCriticalSection(&g_csIoInitialize);
        if ( v6 < 0 )
          goto LABEL_50;
        OutputBufferLength = v20;
        v6 = 0;
      }
      v17 = NtDeviceIoControlFile(
              g_hIoDevice,
              0,
              0,
              0,
              &IoStatusBlock,
              0x390400u,
              InputBuffer,
              InputBufferLength,
              OutputBuffer,
              OutputBufferLength);
      Information = IoStatusBlock.Information;
      if ( v17 < 0 )
      {
        if ( v17 == -1073741789 )
          goto LABEL_55;
        if ( v17 != -2147483643 )
        {
          v12 = v19;
          v6 = v17;
LABEL_42:
          *v21 = v12;
          if ( v17 < 0 )
          {
LABEL_57:
            if ( Heap && !*a4 )
              BCryptFree(Heap);
            return v6;
          }
LABEL_22:
          if ( a6 )
            *a6 = *a4 == 0;
          *a4 = Heap;
          return v6;
        }
        if ( LODWORD(IoStatusBlock.Information) < 4 )
          goto LABEL_55;
        v6 = *OutputBuffer;
        if ( *OutputBuffer == -1073741789 )
        {
          if ( LODWORD(IoStatusBlock.Information) != 8 )
            goto LABEL_55;
          v12 = OutputBuffer[1];
          v19 = v12;
        }
        else
        {
          if ( LODWORD(IoStatusBlock.Information) != 4 )
          {
LABEL_55:
            *v21 = v19;
            goto LABEL_56;
          }
LABEL_50:
          v12 = v19;
        }
        v17 = v6;
        if ( v6 != -1073741789 )
          goto LABEL_42;
        goto LABEL_52;
      }
      if ( Heap && v19 >= LODWORD(IoStatusBlock.Information) )
      {
        if ( OutputBuffer == (NTSTATUS *)&Src )
          memcpy_0(Heap, OutputBuffer, LODWORD(IoStatusBlock.Information));
        *v21 = Information;
        goto LABEL_22;
      }
      v17 = -1073741789;
      v19 = IoStatusBlock.Information;
      v6 = -1073741789;
      v12 = IoStatusBlock.Information;
LABEL_52:
      if ( *a4 )
        goto LABEL_42;
      v7 = v22;
      v6 = 0;
      a1 = v23;
    }
  }
  result = IoCallKernelDriver(a1, a2, a3, 0, &v20);
  if ( result == -1073741789 )
    *a5 = v20;
  return result;
}

```

## disassembly

```asm
0x1800023f0  push    rbx
0x1800023f2  push    rbp
0x1800023f3  push    rdi
0x1800023f4  push    r14
0x1800023f6  push    r15
0x1800023f8  sub     rsp, 0A0h
0x1800023ff  mov     rax, cs:__security_cookie
0x180002406  xor     rax, rsp
0x180002409  mov     [rsp+0C8h+var_40], rax
0x180002411  mov     rdi, [rsp+0C8h+arg_28]
0x180002419  xor     r15d, r15d
0x18000241c  mov     r14, [rsp+0C8h+arg_20]
0x180002424  mov     eax, r8d
0x180002427  mov     [rsp+0C8h+var_68], eax
0x18000242b  mov     rbx, r9
0x18000242e  mov     [rsp+0C8h+var_64], ecx
0x180002432  mov     rbp, rdx
0x180002435  mov     [rsp+0C8h+var_70], r14
0x18000243a  mov     [rsp+0C8h+var_74], r15d
0x18000243f  test    rdi, rdi
0x180002442  jz      short loc_180002447
0x180002444  mov     [rdi], r15d
0x180002447  test    rbx, rbx
0x18000244a  jnz     short loc_180002478
0x18000244c  lea     rdx, [rsp+0C8h+var_74]
0x180002451  xor     r9d, r9d; unsigned __int8 *
0x180002454  mov     [rsp+0C8h+IoStatusBlock], rdx; unsigned int *
0x180002459  mov     rdx, rbp; unsigned __int8 *
0x18000245c  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x180002461  cmp     eax, 0C0000023h
0x180002466  jnz     loc_1800025B8
0x18000246c  mov     ecx, [rsp+0C8h+var_74]
0x180002470  mov     [r14], ecx
0x180002473  jmp     loc_1800025B8
0x180002478  mov     [rsp+0C8h+arg_0], rsi
0x180002480  mov     rsi, [r9]
0x180002483  mov     [rsp+0C8h+var_38], r13
0x18000248b  test    rsi, rsi
0x18000248e  jz      loc_180002759
0x180002494  mov     r13d, [r14]
0x180002497  mov     [rsp+0C8h+var_78], r13d
0x18000249c  mov     [rsp+0C8h+var_30], r12
0x1800024a4  cmp     qword ptr [rbx], 0
0x1800024a8  jz      loc_1800025D8
0x1800024ae  xorps   xmm0, xmm0
0x1800024b1  movups  xmmword ptr [rsp+0C8h+var_60], xmm0
0x1800024b6  test    rbp, rbp
0x1800024b9  jnz     loc_18000264B
0x1800024bf  test    rbp, rbp
0x1800024c2  lea     r14, [rsp+0C8h+var_48]
0x1800024ca  mov     r12d, 8
0x1800024d0  cmovnz  r14, rbp
0x1800024d4  cmovnz  r12d, eax
0x1800024d8  mov     dword ptr [r14], 1A2B3C4Dh
0x1800024df  mov     [r14+4], ecx
0x1800024e3  test    rsi, rsi
0x1800024e6  jnz     loc_180002632
0x1800024ec  mov     ecx, 8
0x1800024f1  lea     r13, [rsp+0C8h+Src]
0x1800024f6  mov     [rsp+0C8h+var_74], ecx
0x1800024fa  mov     rax, cs:?g_hIoDevice@@3REAXEA; void * g_hIoDevice
0x180002501  test    rax, rax
0x180002504  jz      loc_1800026CA
0x18000250a  mov     [rsp+0C8h+OutputBufferLength], ecx; OutputBufferLength
0x18000250e  lea     rax, [rsp+0C8h+var_60]
0x180002513  mov     rcx, cs:?g_hIoDevice@@3REAXEA; FileHandle
0x18000251a  xor     r9d, r9d; ApcContext
0x18000251d  mov     [rsp+0C8h+OutputBuffer], r13; OutputBuffer
0x180002522  xor     r8d, r8d; ApcRoutine
0x180002525  mov     [rsp+0C8h+InputBufferLength], r12d; InputBufferLength
0x18000252a  xor     edx, edx; Event
0x18000252c  mov     [rsp+0C8h+InputBuffer], r14; InputBuffer
0x180002531  mov     [rsp+0C8h+IoControlCode], 390400h; IoControlCode
0x180002539  mov     [rsp+0C8h+IoStatusBlock], rax; IoStatusBlock
0x18000253e  call    cs:__imp_NtDeviceIoControlFile
0x180002545  nop     dword ptr [rax+rax+00h]
0x18000254a  mov     r14d, dword ptr [rsp+0C8h+var_60.Information]
0x18000254f  test    eax, eax
0x180002551  js      loc_180002661
0x180002557  test    rsi, rsi
0x18000255a  jz      loc_18000272F
0x180002560  cmp     [rsp+0C8h+var_78], r14d
0x180002565  jb      loc_18000272F
0x18000256b  lea     rax, [rsp+0C8h+Src]
0x180002570  cmp     r13, rax
0x180002573  jnz     short loc_180002583
0x180002575  mov     r8d, r14d; Size
0x180002578  mov     rdx, r13; Src
0x18000257b  mov     rcx, rsi; void *
0x18000257e  call    memcpy_0
0x180002583  mov     rcx, [rsp+0C8h+var_70]
0x180002588  mov     [rcx], r14d
0x18000258b  test    rdi, rdi
0x18000258e  jz      short loc_18000259A
0x180002590  xor     ecx, ecx
0x180002592  cmp     [rbx], rcx
0x180002595  setz    cl
0x180002598  mov     [rdi], ecx
0x18000259a  mov     [rbx], rsi
0x18000259d  mov     eax, r15d
0x1800025a0  mov     r12, [rsp+0C8h+var_30]
0x1800025a8  mov     r13, [rsp+0C8h+var_38]
0x1800025b0  mov     rsi, [rsp+0C8h+arg_0]
0x1800025b8  mov     rcx, [rsp+0C8h+var_40]
0x1800025c0  xor     rcx, rsp; StackCookie
0x1800025c3  call    __security_check_cookie
0x1800025c8  add     rsp, 0A0h
0x1800025cf  pop     r15
0x1800025d1  pop     r14
0x1800025d3  pop     rdi
0x1800025d4  pop     rbp
0x1800025d5  pop     rbx
0x1800025d6  retn
0x1800025d8  test    rsi, rsi
0x1800025db  jz      short loc_1800025FB
0x1800025dd  mov     rcx, gs:60h
0x1800025e6  mov     r8, rsi; P
0x1800025e9  xor     edx, edx; Flags
0x1800025eb  mov     rcx, [rcx+30h]; HeapHandle
0x1800025ef  call    cs:__imp_RtlFreeHeap
0x1800025f6  nop     dword ptr [rax+rax+00h]
0x1800025fb  mov     rcx, gs:60h
0x180002604  xor     edx, edx; Flags
0x180002606  mov     r8d, r13d; Size
0x180002609  mov     rcx, [rcx+30h]; HeapHandle
0x18000260d  call    cs:__imp_RtlAllocateHeap
0x180002614  nop     dword ptr [rax+rax+00h]
0x180002619  mov     rsi, rax
0x18000261c  test    rax, rax
0x18000261f  jz      loc_180002715
0x180002625  mov     eax, [rsp+0C8h+var_68]
0x180002629  mov     ecx, [rsp+0C8h+var_64]
0x18000262d  jmp     loc_1800024AE
0x180002632  mov     ecx, r13d
0x180002635  mov     [rsp+0C8h+var_74], ecx
0x180002639  cmp     r13d, 8
0x18000263d  jb      loc_1800024EC
0x180002643  mov     r13, rsi
0x180002646  jmp     loc_1800024FA
0x18000264b  cmp     eax, 8
0x18000264e  jnb     loc_1800024BF
0x180002654  mov     rcx, [rsp+0C8h+var_70]
0x180002659  mov     [rcx], r13d
0x18000265c  jmp     loc_180002772
0x180002661  cmp     eax, 0C0000023h
0x180002666  jz      loc_180002767
0x18000266c  cmp     eax, 80000005h
0x180002671  jnz     loc_180002798
0x180002677  cmp     r14d, 4
0x18000267b  jb      loc_180002767
0x180002681  mov     r15d, [r13+0]
0x180002685  cmp     r15d, 0C0000023h
0x18000268c  jnz     loc_18000271F
0x180002692  cmp     r14d, 8
0x180002696  jnz     loc_180002767
0x18000269c  mov     r13d, [r13+4]
0x1800026a0  mov     [rsp+0C8h+var_78], r13d
0x1800026a5  mov     eax, r15d
0x1800026a8  cmp     r15d, 0C0000023h
0x1800026af  jz      loc_18000273F
0x1800026b5  mov     rcx, [rsp+0C8h+var_70]
0x1800026ba  mov     [rcx], r13d
0x1800026bd  test    eax, eax
0x1800026bf  jns     loc_18000258B
0x1800026c5  jmp     loc_180002778
0x1800026ca  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800026d1  call    cs:__imp_EnterCriticalSection
0x1800026d8  nop     dword ptr [rax+rax+00h]
0x1800026dd  mov     rax, cs:?g_hIoDevice@@3REAXEA; void * g_hIoDevice
0x1800026e4  test    rax, rax
0x1800026e7  jnz     short loc_1800026F1
0x1800026e9  call    ?_IoOpenDevice@@YAJXZ; _IoOpenDevice(void)
0x1800026ee  mov     r15d, eax
0x1800026f1  lea     rcx, ?g_csIoInitialize@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800026f8  call    cs:__imp_LeaveCriticalSection
0x1800026ff  nop     dword ptr [rax+rax+00h]
0x180002704  test    r15d, r15d
0x180002707  js      short loc_180002725
0x180002709  mov     ecx, [rsp+0C8h+var_74]
0x18000270d  xor     r15d, r15d
0x180002710  jmp     loc_18000250A
0x180002715  mov     eax, 0C0000017h
0x18000271a  jmp     loc_1800025A0
0x18000271f  cmp     r14d, 4
0x180002723  jnz     short loc_180002767
0x180002725  mov     r13d, [rsp+0C8h+var_78]
0x18000272a  jmp     loc_1800026A5
0x18000272f  mov     eax, 0C0000023h
0x180002734  mov     [rsp+0C8h+var_78], r14d
0x180002739  mov     r15d, eax
0x18000273c  mov     r13d, r14d
0x18000273f  cmp     qword ptr [rbx], 0
0x180002743  jnz     loc_1800026B5
0x180002749  mov     eax, [rsp+0C8h+var_68]
0x18000274d  xor     r15d, r15d
0x180002750  mov     ecx, [rsp+0C8h+var_64]
0x180002754  jmp     loc_1800024A4
0x180002759  mov     rsi, r15
0x18000275c  mov     r13d, 180h
0x180002762  jmp     loc_180002497
0x180002767  mov     rcx, [rsp+0C8h+var_70]
0x18000276c  mov     eax, [rsp+0C8h+var_78]
0x180002770  mov     [rcx], eax
0x180002772  mov     r15d, 0C00000E5h
0x180002778  test    rsi, rsi
0x18000277b  jz      loc_18000259D
0x180002781  cmp     qword ptr [rbx], 0
0x180002785  jnz     loc_18000259D
0x18000278b  mov     rcx, rsi
0x18000278e  call    BCryptFree
0x180002793  jmp     loc_18000259D
0x180002798  mov     r13d, [rsp+0C8h+var_78]
0x18000279d  mov     r15d, eax
0x1800027a0  jmp     loc_1800026B5
```
