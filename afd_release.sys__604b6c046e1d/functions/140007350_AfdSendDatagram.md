# AfdSendDatagram

- ea: `0x140007350`
- end: `0x140007b60`
- name: `AfdSendDatagram`
- size: `2064`
- prototype: `NTSTATUS __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140005b60`
- `0x140007120`
- `0x140007350`
- `0x140008064`
- `0x14000dd60`
- `0x14000fa00`
- `0x14000ff20`
- `0x140012610`
- `0x14002fd5c`
- `0x140030950`
- `0x140032bd4`
- `0x1400445b8`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072b00`
- `0x14009304c`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140007718`
- `ntoskrnl!ExRaiseStatus` at `0x140007736`
- `ntoskrnl!ExRaiseStatus` at `0x140007754`
- `ntoskrnl!ExRaiseStatus` at `0x1400079f3`
- `ntoskrnl!ExRaiseStatus` at `0x140007718`
- `ntoskrnl!ExRaiseStatus` at `0x140007736`
- `ntoskrnl!ExRaiseStatus` at `0x140007754`
- `ntoskrnl!ExRaiseStatus` at `0x1400079f3`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140007450`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400075b6`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140007450`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400075b6`
- `ntoskrnl!IofCompleteRequest` at `0x140007b23`
- `ntoskrnl!IofCompleteRequest` at `0x140007b23`
- `ntoskrnl!IofCallDriver` at `0x1400079dd`
- `ntoskrnl!IofCallDriver` at `0x1400079dd`
- `ntoskrnl!IoIs32bitProcess` at `0x1400073f5`
- `ntoskrnl!IoIs32bitProcess` at `0x1400073f5`

## pseudocode

```c
NTSTATUS __fastcall AfdSendDatagram(PIRP Irp, __int64 a2)
{
  __int64 v4; // rsi
  NTSTATUS v5; // r14d
  __int64 v6; // rdx
  BOOLEAN v7; // al
  unsigned int v8; // r14d
  KPROCESSOR_MODE RequestorMode; // cl
  void *v10; // rdx
  unsigned int v11; // r12d
  KPROCESSOR_MODE v12; // cl
  void *v13; // rdx
  signed __int16 *BufferTag; // r14
  KPROCESSOR_MODE v15; // al
  void *v16; // rcx
  ADDRESS_FAMILY v17; // cx
  ULONG v18; // r13d
  __int64 v19; // rax
  struct _FILE_OBJECT *v21; // r12
  struct _DEVICE_OBJECT *v22; // r15
  signed __int16 *v23; // rdx
  int v24; // eax
  bool v25; // zf
  __int64 v26; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v28; // rax
  int v29; // [rsp+60h] [rbp-108h]
  int v30; // [rsp+60h] [rbp-108h]
  ULONG v31; // [rsp+64h] [rbp-104h] BYREF
  int v32; // [rsp+68h] [rbp-100h]
  void *Src; // [rsp+70h] [rbp-F8h]
  int v34; // [rsp+78h] [rbp-F0h]
  int v35; // [rsp+7Ch] [rbp-ECh]
  __int64 v36; // [rsp+80h] [rbp-E8h]
  PIRP v37; // [rsp+88h] [rbp-E0h]
  PVOID Entry; // [rsp+90h] [rbp-D8h]
  __int128 v39; // [rsp+98h] [rbp-D0h] BYREF
  __int128 v40; // [rsp+A8h] [rbp-C0h]
  _OWORD v41[7]; // [rsp+C0h] [rbp-A8h] BYREF

  v37 = Irp;
  Src = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  v39 = 0;
  v40 = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( (*(_BYTE *)(v4 + 7) & 0x10) != 0 )
  {
    v5 = -1073741816;
    v6 = 3066;
LABEL_68:
    AFDETW_TRACESENDTO(0, v6, v4);
    goto LABEL_69;
  }
  if ( *(_WORD *)v4 != 0xAFD1 || (unsigned __int8)(*(_BYTE *)(v4 + 2) - 3) > 1u )
  {
    v5 = -1073741811;
    v6 = 3028;
    goto LABEL_68;
  }
  v36 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v7 = IoIs32bitProcess(Irp);
  v8 = *(_DWORD *)(a2 + 16);
  if ( v7 )
  {
    memset(v41, 0, 56);
    if ( v8 < 0x38 )
    {
      v5 = -1073741811;
      v6 = 3031;
      goto LABEL_68;
    }
    RequestorMode = Irp->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v10 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(v41, v10, 0x38u);
    else
      RtlCopyVolatileMemory(v41, v10, 0x38u);
    v35 = DWORD1(v41[0]);
    v32 = DWORD1(v41[0]);
    Src = (void *)DWORD1(v41[3]);
    v11 = v41[3];
    v34 = v41[3];
    v29 = AfdAllocateMdlChain32(Irp, LODWORD(v41[0]), DWORD1(v41[0]), 0, &v31);
    if ( v29 < 0 )
    {
      AFDETW_TRACESENDTO(0, 3029, v4);
      v5 = v29;
LABEL_69:
      Irp->IoStatus.Information = 0;
      Irp->IoStatus.Status = v5;
      IofCompleteRequest(Irp, AfdPriorityBoost);
      return v5;
    }
  }
  else
  {
    memset(v41, 0, 0x68u);
    if ( v8 < 0x68 )
    {
      v5 = -1073741811;
      v6 = 3034;
      goto LABEL_68;
    }
    v12 = Irp->RequestorMode;
    if ( v12 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v13 = *(void **)(a2 + 32);
    if ( v12 )
      RtlCopyFromUser(v41, v13, 0x68u);
    else
      RtlCopyVolatileMemory(v41, v13, 0x68u);
    v35 = DWORD2(v41[0]);
    v32 = DWORD2(v41[0]);
    Src = *(void **)&v41[6];
    v11 = DWORD2(v41[5]);
    v34 = DWORD2(v41[5]);
    v30 = AfdAllocateMdlChain(Irp, *(_QWORD *)&v41[0], DWORD2(v41[0]), 0, &v31);
    if ( v30 < 0 )
    {
      AFDETW_TRACESENDTO(0, 3032, v4);
      v5 = v30;
      goto LABEL_69;
    }
  }
  Entry = 0;
  if ( (*(_DWORD *)(v4 + 8) & 0x10000) != 0 )
  {
    v5 = -1073741648;
    v6 = 3035;
    goto LABEL_68;
  }
  BufferTag = AfdGetBufferTag(v11, *(struct _KPROCESS **)(v4 + 48), 1);
  Entry = BufferTag;
  v15 = Irp->RequestorMode;
  v16 = (void *)*((_QWORD *)BufferTag + 5);
  if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 )
  {
    if ( v15 )
      RtlCopyFromUser(v16, Src, v11);
    else
      RtlCopyVolatileMemory(v16, Src, v11);
    if ( v11 < 2 )
      ExRaiseStatus(-1073741811);
    v17 = **((_WORD **)BufferTag + 5);
    if ( v17 >= 0x23u )
      ExRaiseStatus(-1073741503);
    if ( (int)v11 < SOCKADDR_SIZE(v17) )
      ExRaiseStatus(-1073741503);
    *(_QWORD *)&v39 = 0;
    *((_QWORD *)&v39 + 1) = Irp->MdlAddress;
    LODWORD(v40) = 0;
    v18 = v31;
    *((_QWORD *)&v40 + 1) = v31;
  }
  else
  {
    if ( v15 )
      RtlCopyFromUser(v16, Src, v11);
    else
      RtlCopyVolatileMemory(v16, Src, v11);
    v19 = *((_QWORD *)BufferTag + 5);
    if ( *(_DWORD *)v19 != 1 || v11 < (unsigned int)*(unsigned __int16 *)(v19 + 4) + 8 )
      ExRaiseStatus(-1073741811);
    *((_DWORD *)BufferTag + 8) = v11;
    *((_QWORD *)BufferTag + 3) = 0;
    *((_DWORD *)BufferTag + 4) = 0;
    *((_QWORD *)BufferTag + 1) = 0;
    *(_DWORD *)BufferTag = 0;
    v18 = v31;
  }
  AFDETW_TRACESENDTO(0, 3037, v4);
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 64)) <= 1 )
    __fastfail(0xEu);
  *(_DWORD *)(a2 + 8) = v18;
  if ( (BYTE1(xmmword_1400875E0) & 4) != 0 )
  {
    WPP_SF_qD(1034, 17, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids, *(_QWORD *)(a2 + 32), *(_DWORD *)(a2 + 16));
    if ( (BYTE1(xmmword_1400875E0) & 4) != 0 )
    {
      WPP_SF_qD(1034, 18, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids, Src, v11);
      if ( (BYTE1(xmmword_1400875E0) & 4) != 0 )
        WPP_SF_d(1034, 19, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids, *(unsigned int *)(a2 + 8));
    }
  }
  if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 )
  {
    v21 = *(struct _FILE_OBJECT **)(v4 + 24);
    v22 = *(struct _DEVICE_OBJECT **)(v4 + 40);
    *((_QWORD *)BufferTag + 6) = v4;
    v23 = BufferTag + 16;
    v24 = *(_DWORD *)(v4 + 8);
    if ( *((int *)BufferTag + 8) <= 0 )
    {
      if ( (v24 & 0x400000) == 0 )
      {
LABEL_64:
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartSendDatagram;
        CurrentStackLocation[-1].Context = BufferTag;
        CurrentStackLocation[-1].Control = -32;
        v28 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v28[-1].MajorFunction = 2319;
        v28[-1].DeviceObject = v22;
        v28[-1].FileObject = v21;
        v28[-1].Parameters.Read.Length = v18;
        v28[-1].Parameters.QueryDirectory.FileName = (PUNICODE_STRING)BufferTag;
        _InterlockedIncrement((volatile signed __int32 *)(v4 + 248));
        return IofCallDriver(v22, Irp);
      }
      v25 = (*(_DWORD *)(v4 + 192) & 0x20) == 0;
    }
    else
    {
      if ( (v24 & 0x400000) == 0 )
      {
        if ( (*(_DWORD *)(v4 + 8) & 0x200000) != 0 )
          AfdTdi_TA6toTA4_InPlace(*((_QWORD *)BufferTag + 5), v23);
        goto LABEL_64;
      }
      v25 = (unsigned __int8)AfdTdi_TA6toTA4_InPlace(*((_QWORD *)BufferTag + 5), v23) == 0;
    }
    if ( !v25 )
    {
      v26 = *(_QWORD *)(v4 + 280);
      v21 = *(struct _FILE_OBJECT **)(v26 + 8);
      v22 = *(struct _DEVICE_OBJECT **)(v26 + 16);
    }
    goto LABEL_64;
  }
  memset(v41, 0, 0x48u);
  *((_QWORD *)BufferTag + 6) = Irp;
  *(_QWORD *)&v41[0] = AfdTLDgramSendToComplete;
  *((_QWORD *)&v41[0] + 1) = BufferTag;
  *((_QWORD *)&v41[2] + 1) = &v39;
  *(_QWORD *)&v41[2] = *((_QWORD *)BufferTag + 5);
  *((_QWORD *)&v41[1] + 1) = Irp;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( (unsigned int)AfdTLSendMessages(v4, v41) != 259 )
    AfdTLDgramSendToComplete(BufferTag);
  return 259;
}

```

## disassembly

```asm
0x140007350  mov     [rsp+arg_10], rbx
0x140007355  mov     [rsp+arg_18], rsi
0x14000735a  push    rdi
0x14000735b  push    r12
0x14000735d  push    r13
0x14000735f  push    r14
0x140007361  push    r15
0x140007363  sub     rsp, 140h
0x14000736a  mov     rax, cs:__security_cookie
0x140007371  xor     rax, rsp
0x140007374  mov     [rsp+168h+var_38], rax
0x14000737c  mov     r15, rdx
0x14000737f  mov     rdi, rcx
0x140007382  mov     [rsp+168h+var_E0], rcx
0x14000738a  xor     ebx, ebx
0x14000738c  mov     [rsp+168h+Src], rbx
0x140007391  mov     [rsp+168h+var_F0], ebx
0x140007395  mov     [rsp+168h+var_104], ebx
0x140007399  mov     [rsp+168h+var_100], ebx
0x14000739d  xorps   xmm0, xmm0
0x1400073a0  movups  [rsp+168h+var_D0], xmm0
0x1400073a8  movups  [rsp+168h+var_C0], xmm0
0x1400073b0  mov     rax, [rdx+30h]
0x1400073b4  mov     rsi, [rax+18h]
0x1400073b8  test    byte ptr [rsi+7], 10h
0x1400073bc  jz      short loc_1400073CE
0x1400073be  mov     r14d, 0C0000008h
0x1400073c4  mov     edx, 0BFAh
0x1400073c9  jmp     loc_140007AE5
0x1400073ce  mov     eax, 0AFD1h
0x1400073d3  cmp     [rsi], ax
0x1400073d6  jnz     loc_140007ADA
0x1400073dc  mov     al, [rsi+2]
0x1400073df  mov     r13b, 3
0x1400073e2  sub     al, r13b
0x1400073e5  cmp     al, 1
0x1400073e7  ja      loc_140007ADA
0x1400073ed  mov     [rsp+168h+var_E8], rsi
0x1400073f5  call    cs:__imp_IoIs32bitProcess
0x1400073fc  nop     dword ptr [rax+rax+00h]
0x140007401  mov     r14d, [r15+10h]
0x140007405  test    al, al
0x140007407  jz      loc_140007584
0x14000740d  xorps   xmm0, xmm0
0x140007410  xor     eax, eax
0x140007412  movups  [rsp+168h+var_A8], xmm0
0x14000741a  movups  [rsp+168h+var_98], xmm0
0x140007422  movups  [rsp+168h+var_88], xmm0
0x14000742a  mov     [rsp+168h+Size], rax
0x140007432  lea     r8d, [rax+38h]
0x140007436  cmp     r14d, r8d
0x140007439  jb      loc_140007570
0x14000743f  mov     [rsp+168h+var_108], ebx
0x140007443  mov     cl, [rdi+40h]
0x140007446  test    cl, cl
0x140007448  jz      short loc_14000745D
0x14000744a  test    [r15+20h], r13b
0x14000744e  jz      short loc_14000745D
0x140007450  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140007457  nop     dword ptr [rax+rax+00h]
0x14000745c  int     3; Trap to Debugger
0x14000745d  mov     rdx, [r15+20h]; Src
0x140007461  test    cl, cl
0x140007463  lea     rcx, [rsp+168h+var_A8]; void *
0x14000746b  jz      short loc_140007474
0x14000746d  call    RtlCopyFromUser
0x140007472  jmp     short loc_140007479
0x140007474  call    RtlCopyVolatileMemory
0x140007479  mov     edx, dword ptr [rsp+168h+var_A8]
0x140007480  mov     r13d, dword ptr [rsp+168h+var_A8+4]
0x140007488  mov     [rsp+168h+var_EC], r13d
0x14000748d  mov     [rsp+168h+var_100], r13d
0x140007492  mov     r14d, dword ptr [rsp+168h+Size+4]
0x14000749a  mov     [rsp+168h+Src], r14
0x14000749f  mov     r12, [rsp+168h+Size]
0x1400074a7  mov     [rsp+168h+var_F0], r12d
0x1400074ac  lea     rax, [rsp+168h+var_104]
0x1400074b1  mov     [rsp+168h+var_148], rax
0x1400074b6  xor     r9d, r9d
0x1400074b9  mov     r8d, r13d
0x1400074bc  mov     rcx, rdi
0x1400074bf  call    AfdAllocateMdlChain32
0x1400074c4  mov     [rsp+168h+var_108], eax
0x1400074c8  mov     eax, [rsp+168h+var_108]
0x1400074cc  test    eax, eax
0x1400074ce  jns     short loc_140007514
0x1400074d0  mov     rcx, [rdi+8]
0x1400074d4  mov     [rsp+168h+var_120], rdi
0x1400074d9  mov     [rsp+168h+var_128], rbx
0x1400074de  mov     eax, [rsp+168h+var_108]
0x1400074e2  mov     [rsp+168h+var_130], eax
0x1400074e6  mov     eax, [rsp+168h+var_104]
0x1400074ea  mov     [rsp+168h+var_138], eax
0x1400074ee  mov     [rsp+168h+var_140], rcx
0x1400074f3  mov     dword ptr [rsp+168h+var_148], r13d
0x1400074f8  xor     r9d, r9d
0x1400074fb  mov     r8, rsi
0x1400074fe  mov     edx, 0BD5h
0x140007503  xor     ecx, ecx
0x140007505  call    AFDETW_TRACESENDTO
0x14000750a  mov     r14d, [rsp+168h+var_108]
0x14000750f  jmp     loc_140007B12
0x140007514  jmp     loc_14000767E
0x140007519  mov     rdi, [rsp+168h+var_E0]
0x140007521  mov     [rsp+168h+var_120], rdi
0x140007526  mov     [rsp+168h+var_128], 0
0x14000752f  mov     r14d, [rsp+168h+var_108]
0x140007534  mov     [rsp+168h+var_130], r14d
0x140007539  mov     eax, [rsp+168h+var_104]
0x14000753d  mov     [rsp+168h+var_138], eax
0x140007541  mov     rax, [rdi+8]
0x140007545  mov     [rsp+168h+var_140], rax
0x14000754a  mov     eax, [rsp+168h+var_100]
0x14000754e  mov     dword ptr [rsp+168h+var_148], eax
0x140007552  xor     r9d, r9d
0x140007555  mov     r8, [rsp+168h+var_E8]
0x14000755d  mov     edx, 0BD6h
0x140007562  xor     ecx, ecx
0x140007564  call    AFDETW_TRACESENDTO
0x140007569  xor     ebx, ebx
0x14000756b  jmp     loc_140007B12
0x140007570  mov     r14d, 0C000000Dh
0x140007576  mov     rax, [rdi+8]
0x14000757a  mov     edx, 0BD7h
0x14000757f  jmp     loc_140007AE9
0x140007584  mov     r12d, 68h ; 'h'
0x14000758a  mov     r8d, r12d; Size
0x14000758d  xor     edx, edx; Val
0x14000758f  lea     rcx, [rsp+168h+var_A8]; void *
0x140007597  call    memset
0x14000759c  cmp     r14d, r12d
0x14000759f  jb      loc_140007AC9
0x1400075a5  mov     [rsp+168h+var_108], ebx
0x1400075a9  mov     cl, [rdi+40h]
0x1400075ac  test    cl, cl
0x1400075ae  jz      short loc_1400075C3
0x1400075b0  test    [r15+20h], r13b
0x1400075b4  jz      short loc_1400075C3
0x1400075b6  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400075bd  nop     dword ptr [rax+rax+00h]
0x1400075c2  int     3; Trap to Debugger
0x1400075c3  mov     rdx, [r15+20h]; Src
0x1400075c7  mov     r8, r12; Size
0x1400075ca  test    cl, cl
0x1400075cc  lea     rcx, [rsp+168h+var_A8]; void *
0x1400075d4  jz      short loc_1400075DD
0x1400075d6  call    RtlCopyFromUser
0x1400075db  jmp     short loc_1400075E2
0x1400075dd  call    RtlCopyVolatileMemory
0x1400075e2  mov     r13d, dword ptr [rsp+168h+var_A8+8]
0x1400075ea  mov     [rsp+168h+var_EC], r13d
0x1400075ef  mov     [rsp+168h+var_100], r13d
0x1400075f4  mov     rax, [rsp+168h+var_48]
0x1400075fc  mov     [rsp+168h+Src], rax
0x140007601  mov     r12d, [rsp+168h+var_50]
0x140007609  mov     [rsp+168h+var_F0], r12d
0x14000760e  lea     rax, [rsp+168h+var_104]
0x140007613  mov     [rsp+168h+var_148], rax
0x140007618  xor     r9d, r9d
0x14000761b  mov     r8d, r13d
0x14000761e  mov     rdx, qword ptr [rsp+168h+var_A8]
0x140007626  mov     rcx, rdi
0x140007629  call    AfdAllocateMdlChain
0x14000762e  mov     [rsp+168h+var_108], eax
0x140007632  mov     eax, [rsp+168h+var_108]
0x140007636  test    eax, eax
0x140007638  jns     short loc_14000767E
0x14000763a  mov     rcx, [rdi+8]
0x14000763e  mov     [rsp+168h+var_120], rdi
0x140007643  mov     [rsp+168h+var_128], rbx
0x140007648  mov     eax, [rsp+168h+var_108]
0x14000764c  mov     [rsp+168h+var_130], eax
0x140007650  mov     eax, [rsp+168h+var_104]
0x140007654  mov     [rsp+168h+var_138], eax
0x140007658  mov     [rsp+168h+var_140], rcx
0x14000765d  mov     dword ptr [rsp+168h+var_148], r13d
0x140007662  xor     r9d, r9d
0x140007665  mov     r8, rsi
0x140007668  mov     edx, 0BD8h
0x14000766d  xor     ecx, ecx
0x14000766f  call    AFDETW_TRACESENDTO
0x140007674  mov     r14d, [rsp+168h+var_108]
0x140007679  jmp     loc_140007B12
0x14000767e  mov     [rsp+168h+Entry], rbx
0x140007686  mov     eax, [rsi+8]
0x140007689  bt      eax, 10h
0x14000768d  jnb     short loc_1400076C4
0x14000768f  mov     r14d, 0C00000B0h
0x140007695  mov     [rsp+168h+var_120], rdi
0x14000769a  mov     [rsp+168h+var_128], rbx
0x14000769f  mov     [rsp+168h+var_130], r14d
0x1400076a4  mov     eax, [rsp+168h+var_104]
0x1400076a8  mov     [rsp+168h+var_138], eax
0x1400076ac  mov     rax, [rdi+8]
0x1400076b0  mov     [rsp+168h+var_140], rax
0x1400076b5  mov     dword ptr [rsp+168h+var_148], r13d
0x1400076ba  mov     edx, 0BDBh
0x1400076bf  jmp     loc_140007B05
0x1400076c4  mov     r8d, 1
0x1400076ca  mov     rdx, [rsi+30h]
0x1400076ce  mov     ecx, r12d
0x1400076d1  call    AfdGetBufferTag
0x1400076d6  mov     r14, rax
0x1400076d9  mov     [rsp+168h+Entry], rax
0x1400076e1  mov     edx, [rsi+8]
0x1400076e4  mov     r8d, r12d; Size
0x1400076e7  mov     al, [rdi+40h]
0x1400076ea  mov     rcx, [r14+28h]; void *
0x1400076ee  bt      edx, 8
0x1400076f2  mov     rdx, [rsp+168h+Src]; Src
0x1400076f7  jnb     loc_14000778A
0x1400076fd  test    al, al
0x1400076ff  jz      short loc_140007708
0x140007701  call    RtlCopyFromUser
0x140007706  jmp     short loc_14000770D
0x140007708  call    RtlCopyVolatileMemory
0x14000770d  cmp     r12d, 2
0x140007711  jnb     short loc_140007724
0x140007713  mov     ecx, 0C000000Dh; Status
0x140007718  call    cs:__imp_ExRaiseStatus
0x140007724  mov     rax, [r14+28h]
0x140007728  movzx   ecx, word ptr [rax]; af
0x14000772b  cmp     cx, 23h ; '#'
0x14000772f  jb      short loc_140007742
0x140007731  mov     ecx, 0C0000141h; Status
0x140007736  call    cs:__imp_ExRaiseStatus
0x140007742  call    SOCKADDR_SIZE
0x140007747  movzx   edx, al
0x14000774a  cmp     r12d, edx
0x14000774d  jge     short loc_140007760
0x14000774f  mov     ecx, 0C0000141h; Status
0x140007754  call    cs:__imp_ExRaiseStatus
0x140007760  mov     qword ptr [rsp+168h+var_D0], rbx
0x140007768  mov     rax, [rdi+8]
0x14000776c  mov     qword ptr [rsp+168h+var_D0+8], rax
0x140007774  mov     dword ptr [rsp+168h+var_C0], ebx
0x14000777b  mov     r13d, [rsp+168h+var_104]
0x140007780  mov     qword ptr [rsp+168h+var_C0+8], r13
0x140007788  jmp     short loc_1400077CF
0x14000778a  test    al, al
0x14000778c  jz      short loc_140007795
0x14000778e  call    RtlCopyFromUser
0x140007793  jmp     short loc_14000779A
0x140007795  call    RtlCopyVolatileMemory
0x14000779a  mov     rax, [r14+28h]
0x14000779e  cmp     dword ptr [rax], 1
0x1400077a1  jnz     loc_1400079EE
0x1400077a7  movzx   eax, word ptr [rax+4]
0x1400077ab  add     eax, 8
0x1400077ae  cmp     r12d, eax
0x1400077b1  jb      loc_1400079EE
0x1400077b7  mov     [r14+20h], r12d
0x1400077bb  mov     [r14+18h], rbx
0x1400077bf  mov     [r14+10h], ebx
0x1400077c3  mov     [r14+8], rbx
0x1400077c7  mov     [r14], ebx
0x1400077ca  mov     r13d, [rsp+168h+var_104]
0x1400077cf  mov     [rsp+168h+var_120], rdi
0x1400077d4  mov     rax, [r14+28h]
0x1400077d8  mov     [rsp+168h+var_128], rax
0x1400077dd  mov     [rsp+168h+var_130], ebx
0x1400077e1  mov     [rsp+168h+var_138], r13d
0x1400077e6  mov     rax, [rdi+8]
0x1400077ea  mov     [rsp+168h+var_140], rax
0x1400077ef  mov     eax, [rsp+168h+var_EC]
0x1400077f3  mov     dword ptr [rsp+168h+var_148], eax
0x1400077f7  xor     r9d, r9d
0x1400077fa  mov     r8, rsi
0x1400077fd  mov     edx, 0BDDh
0x140007802  xor     ecx, ecx
0x140007804  call    AFDETW_TRACESENDTO
0x140007809  mov     eax, 1
0x14000780e  lock xadd [rsi+40h], rax
0x140007814  inc     rax
0x140007817  cmp     rax, 1
0x14000781b  jg      short loc_140007824
0x14000781d  mov     ecx, 0Eh
0x140007822  int     29h; Win8: RtlFailFast(ecx)
0x140007824  mov     [r15+8], r13d
0x140007828  test    byte ptr cs:xmmword_1400875E0+1, 4
0x14000782f  jz      short loc_14000789F
0x140007831  mov     edx, 11h
0x140007836  mov     ecx, 40Ah
0x14000783b  mov     eax, [r15+10h]
0x14000783f  mov     dword ptr [rsp+168h+var_148], eax
0x140007843  mov     r9, [r15+20h]
0x140007847  lea     r8, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids
0x14000784e  call    WPP_SF_qD
0x140007853  test    byte ptr cs:xmmword_1400875E0+1, 4
0x14000785a  jz      short loc_14000789F
0x14000785c  mov     edx, 12h
0x140007861  mov     ecx, 40Ah
0x140007866  mov     dword ptr [rsp+168h+var_148], r12d
0x14000786b  mov     r9, [rsp+168h+Src]
0x140007870  lea     r8, WPP_c50ec9d9ea093d45966feac367cb7ead_Traceguids
0x140007877  call    WPP_SF_qD
0x14000787c  test    byte ptr cs:xmmword_1400875E0+1, 4
0x140007883  jz      short loc_14000789F
0x140007885  mov     edx, 13h
0x14000788a  mov     ecx, 40Ah
  ... truncated ...
```
