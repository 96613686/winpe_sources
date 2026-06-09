# PrjfGetSetContextFileObject

- ea: `0x140002f3c`
- end: `0x14000347a`
- name: `PrjfGetSetContextFileObject`
- size: `1342`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, char, __int64, __int64, __int64, __int64)`
- caller_count: `15`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140001b3c`
- `0x140007cec`
- `0x1400081f0`
- `0x140022320`
- `0x140023d68`
- `0x140024184`
- `0x14002a6b4`
- `0x14002c3f8`
- `0x14003005c`
- `0x1400396a4`
- `0x140039de8`
- `0x14003d620`
- `0x14003fdf0`
- `0x140040670`
- `0x140041a3c`

## callees

- `0x140002f3c`
- `0x14000b1d0`
- `0x14000d960`
- `0x14000dab0`
- `0x140021550`
- `0x1400217a4`
- `0x140021c5c`
- `0x14003a84c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003457`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003457`
- `FLTMGR!FltGetFileContext` at `0x140002f98`
- `FLTMGR!FltGetFileContext` at `0x140002f98`
- `FLTMGR!FltDeleteFileContext` at `0x14000343d`
- `FLTMGR!FltDeleteFileContext` at `0x14000343d`
- `FLTMGR!FltDeleteStreamContext` at `0x140003423`
- `FLTMGR!FltDeleteStreamContext` at `0x140003423`
- `FLTMGR!FltReleaseContext` at `0x1400033de`
- `FLTMGR!FltReleaseContext` at `0x1400033f5`
- `FLTMGR!FltReleaseContext` at `0x140003409`
- `FLTMGR!FltReleaseContext` at `0x1400033de`
- `FLTMGR!FltReleaseContext` at `0x1400033f5`
- `FLTMGR!FltReleaseContext` at `0x140003409`

## pseudocode

```c
__int64 __fastcall PrjfGetSetContextFileObject(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        int a3,
        char a4,
        char a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        _QWORD *a9)
{
  void *v12; // r12
  NTSTATUS FileContext; // eax
  int v14; // edx
  __int64 v15; // rcx
  int v16; // r8d
  char v17; // r15
  int PrjReparseData; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edi
  int SetFileContext; // eax
  int v23; // edx
  int v24; // r8d
  __int64 v25; // r8
  int SetStreamContext; // eax
  int v27; // edx
  __int64 v28; // rcx
  int v29; // r8d
  _DWORD *v30; // rbx
  int SetStreamHandleContext; // eax
  int v32; // edx
  __int64 v33; // rcx
  int v34; // r8d
  __int64 v35; // rax
  char v37; // [rsp+60h] [rbp-31h] BYREF
  _BYTE Context[15]; // [rsp+61h] [rbp-30h] BYREF
  PFLT_CONTEXT v39; // [rsp+70h] [rbp-21h] BYREF
  __int64 v40; // [rsp+78h] [rbp-19h] BYREF
  PVOID P; // [rsp+80h] [rbp-11h]

  *(_QWORD *)&Context[7] = 0;
  v39 = 0;
  v40 = 0;
  *a8 = 0;
  v12 = 0;
  P = 0;
  *(_WORD *)Context = 0;
  *a9 = 0;
  v37 = 0;
  FileContext = FltGetFileContext(Instance, FileObject, (PFLT_CONTEXT *)&Context[7]);
  v17 = 1;
  if ( FileContext == -1073741275 )
  {
    PrjReparseData = PrjfGetPrjReparseData(Instance, FileObject);
    v21 = PrjReparseData;
    if ( PrjReparseData < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDqd(
          517,
          v19,
          v20,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          10,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          43,
          (char)FileObject,
          PrjReparseData);
      }
      goto LABEL_52;
    }
    if ( !Context[1] && a3 == 1 )
    {
      LOBYTE(v19) = BYTE8(xmmword_14001A3E0) & 0x20;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
        v17 = 0;
      if ( (_BYTE)v19 || v17 )
      {
        LOBYTE(v20) = v17;
        WPP_RECORDER_AND_TRACE_SF_sDq(
          1285,
          v19,
          v20,
          PrjfTraceRecorder,
          5,
          5,
          11,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          53,
          (char)FileObject);
      }
      goto LABEL_52;
    }
    SetFileContext = PrjfGetSetFileContext(Instance, FileObject, a6, a7, (__int64)Context, (__int64)&Context[7]);
    v21 = SetFileContext;
    if ( SetFileContext < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDqd(
          517,
          v23,
          v24,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          12,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          72,
          (char)FileObject,
          SetFileContext);
      }
      goto LABEL_52;
    }
LABEL_24:
    v25 = *(_QWORD *)&Context[7];
    if ( !*(_QWORD *)&Context[7] || P )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v15);
      v25 = *(_QWORD *)&Context[7];
    }
    if ( *(_BYTE *)(v25 + 281) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v15);
      v25 = *(_QWORD *)&Context[7];
    }
    SetStreamContext = PrjfGetSetStreamContext(Instance, FileObject, (_OWORD *)v25, &v37, &v39);
    v21 = SetStreamContext;
    if ( SetStreamContext >= 0 )
    {
      v30 = v39;
      if ( !v39 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v28);
      if ( a3 != 0x80000000 )
        v30[10] = a3;
      if ( a4 || a5 || a3 != 1 && a3 != 0x80000000 )
      {
        SetStreamHandleContext = PrjfGetSetStreamHandleContext(
                                   Instance,
                                   FileObject,
                                   *(PFLT_CONTEXT *)&Context[7],
                                   a5,
                                   (__int64)&v40);
        v21 = SetStreamHandleContext;
        if ( SetStreamHandleContext < 0 )
        {
          if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v32) = xmmword_14001A3D0 & 0x20;
            LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDqd(
              517,
              v32,
              v34,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              5,
              15,
              (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
              148,
              (char)FileObject,
              SetStreamHandleContext);
          }
          v12 = (void *)v40;
          goto LABEL_50;
        }
        v12 = (void *)v40;
        if ( !v40 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v33);
      }
      v35 = *(_QWORD *)&Context[7];
      *(_QWORD *)&Context[7] = 0;
      Context[0] = 0;
      *a8 = v35;
      *a9 = v30;
      v30 = 0;
      v37 = 0;
    }
    else
    {
      if ( (xmmword_14001A3E0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = xmmword_14001A3E0 & 0x20;
        LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDqd(
          1029,
          v27,
          v29,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          4,
          5,
          14,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          110,
          (char)FileObject,
          SetStreamContext);
      }
      v30 = v39;
    }
LABEL_50:
    if ( v30 )
      FltReleaseContext(v30);
    goto LABEL_52;
  }
  if ( FileContext >= 0 )
    goto LABEL_24;
  if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDqd(
      517,
      v14,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      13,
      (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      83,
      (char)FileObject,
      FileContext);
  }
  v21 = -1073741790;
LABEL_52:
  if ( *(_QWORD *)&Context[7] )
    FltReleaseContext(*(PFLT_CONTEXT *)&Context[7]);
  if ( v12 )
    FltReleaseContext(v12);
  if ( v37 )
    FltDeleteStreamContext(Instance, FileObject, 0);
  if ( Context[0] )
    FltDeleteFileContext(Instance, FileObject, 0);
  if ( P )
    ExFreePoolWithTag(P, 0x69724A50u);
  return v21;
}

```

## disassembly

```asm
0x140002f3c  mov     [rsp-8+arg_18], r9b
0x140002f41  push    rbp
0x140002f42  push    rbx
0x140002f43  push    rsi
0x140002f44  push    rdi
0x140002f45  push    r12
0x140002f47  push    r13
0x140002f49  push    r14
0x140002f4b  push    r15
0x140002f4d  lea     rbp, [rsp-7]
0x140002f52  sub     rsp, 98h
0x140002f59  mov     rax, [rbp+3Fh+arg_38]
0x140002f60  xor     ebx, ebx
0x140002f62  mov     r14d, r8d
0x140002f65  mov     qword ptr [rbp+3Fh+Context+7], rbx
0x140002f69  lea     r8, [rbp+3Fh+Context+7]; Context
0x140002f6d  mov     [rbp+3Fh+var_60], rbx
0x140002f71  mov     rsi, rdx
0x140002f74  mov     [rbp+3Fh+var_58], rbx
0x140002f78  mov     [rax], rbx
0x140002f7b  mov     r13, rcx
0x140002f7e  mov     rax, [rbp+3Fh+arg_40]
0x140002f85  mov     r12d, ebx
0x140002f88  mov     [rbp+3Fh+P], rbx
0x140002f8c  mov     [rbp+3Fh+Context+1], bl
0x140002f8f  mov     [rbp+3Fh+Context], bl
0x140002f92  mov     [rax], rbx
0x140002f95  mov     [rbp+3Fh+var_70], bl
0x140002f98  call    cs:__imp_FltGetFileContext
0x140002f9f  nop     dword ptr [rax+rax+00h]
0x140002fa4  lea     r15d, [rbx+1]
0x140002fa8  cmp     eax, 0C0000225h
0x140002fad  jnz     loc_14000317E
0x140002fb3  lea     r9, [rbp+3Fh+Context+1]
0x140002fb7  mov     rdx, rsi; FileObject
0x140002fba  lea     r8, [rbp+3Fh+P]
0x140002fbe  mov     rcx, r13; Instance
0x140002fc1  call    PrjfGetPrjReparseData
0x140002fc6  mov     edi, eax
0x140002fc8  test    eax, eax
0x140002fca  jns     short loc_140003049
0x140002fcc  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140002fd2  lea     rcx, WPP_RECORDER_INITIALIZED
0x140002fd9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140002fe0  setnz   r8b
0x140002fe4  and     dl, 20h
0x140002fe7  jnz     short loc_140002FF2
0x140002fe9  test    r8b, r8b
0x140002fec  jz      loc_1400033EC
0x140002ff2  mov     [rsp+0D0h+var_78], eax
0x140002ff6  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140002ffd  mov     [rsp+0D0h+var_80], rsi
0x140003002  mov     [rsp+0D0h+var_88], 12Bh
0x14000300a  mov     [rsp+0D0h+var_90], rax
0x14000300f  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140003016  mov     [rsp+0D0h+var_98], rax
0x14000301b  mov     word ptr [rsp+0D0h+var_A0], 0Ah
0x140003022  mov     r9, cs:WPP_GLOBAL_Control
0x140003029  mov     ecx, 205h
0x14000302e  mov     dword ptr [rsp+0D0h+var_A8], 5
0x140003036  mov     [rsp+0D0h+var_B0], 2
0x14000303b  mov     r9, [r9+40h]
0x14000303f  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x140003044  jmp     loc_1400033EC
0x140003049  cmp     [rbp+3Fh+Context+1], bl
0x14000304c  jnz     loc_1400030E3
0x140003052  cmp     r14d, r15d
0x140003055  jnz     loc_1400030E3
0x14000305b  mov     dl, byte ptr cs:xmmword_14001A3E0+8
0x140003061  lea     rcx, WPP_RECORDER_INITIALIZED
0x140003068  and     dl, 20h
0x14000306b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003072  jz      short loc_140003081
0x140003074  mov     rax, cs:WPP_GLOBAL_Control
0x14000307b  cmp     [rax+48h], bx
0x14000307f  jnz     short loc_140003084
0x140003081  mov     r15b, bl
0x140003084  test    dl, dl
0x140003086  jnz     short loc_140003091
0x140003088  test    r15b, r15b
0x14000308b  jz      loc_1400033EC
0x140003091  mov     r9, cs:_PrjfTraceRecorder
0x140003098  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000309f  mov     [rsp+0D0h+var_80], rsi
0x1400030a4  mov     ecx, 505h
0x1400030a9  mov     [rsp+0D0h+var_88], 135h
0x1400030b1  mov     r8b, r15b
0x1400030b4  mov     [rsp+0D0h+var_90], rax
0x1400030b9  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400030c0  mov     [rsp+0D0h+var_98], rax
0x1400030c5  mov     word ptr [rsp+0D0h+var_A0], 0Bh
0x1400030cc  mov     dword ptr [rsp+0D0h+var_A8], 5
0x1400030d4  mov     [rsp+0D0h+var_B0], 5
0x1400030d9  call    WPP_RECORDER_AND_TRACE_SF_sDq
0x1400030de  jmp     loc_1400033EC
0x1400030e3  lea     rax, [rbp+3Fh+Context+7]
0x1400030e7  xor     r8d, r8d
0x1400030ea  mov     [rsp+0D0h+var_98], rax; __int64
0x1400030ef  lea     r9, [rbp+3Fh+P]
0x1400030f3  lea     rax, [rbp+3Fh+Context]
0x1400030f7  mov     rdx, rsi; FileObject
0x1400030fa  mov     [rsp+0D0h+var_A0], rax; __int64
0x1400030ff  mov     rcx, r13; Instance
0x140003102  mov     rax, [rbp+3Fh+arg_30]
0x140003106  mov     [rsp+0D0h+var_A8], rax; __int64
0x14000310b  mov     rax, [rbp+3Fh+arg_28]
0x14000310f  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x140003114  call    PrjfGetSetFileContext
0x140003119  mov     edi, eax
0x14000311b  test    eax, eax
0x14000311d  jns     loc_140003200
0x140003123  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140003129  lea     rcx, WPP_RECORDER_INITIALIZED
0x140003130  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003137  setnz   r8b
0x14000313b  and     dl, 20h
0x14000313e  jnz     short loc_140003149
0x140003140  test    r8b, r8b
0x140003143  jz      loc_1400033EC
0x140003149  mov     [rsp+0D0h+var_78], eax
0x14000314d  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140003154  mov     [rsp+0D0h+var_80], rsi
0x140003159  mov     [rsp+0D0h+var_88], 148h
0x140003161  mov     [rsp+0D0h+var_90], rax
0x140003166  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x14000316d  mov     [rsp+0D0h+var_98], rax
0x140003172  mov     word ptr [rsp+0D0h+var_A0], 0Ch
0x140003179  jmp     loc_140003022
0x14000317e  test    eax, eax
0x140003180  jns     short loc_140003200
0x140003182  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140003188  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000318f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003196  setnz   r8b
0x14000319a  and     dl, 20h
0x14000319d  jnz     short loc_1400031A4
0x14000319f  test    r8b, r8b
0x1400031a2  jz      short loc_1400031F6
0x1400031a4  mov     r9, cs:WPP_GLOBAL_Control
0x1400031ab  mov     ecx, 205h
0x1400031b0  mov     [rsp+0D0h+var_78], eax
0x1400031b4  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400031bb  mov     [rsp+0D0h+var_80], rsi
0x1400031c0  mov     [rsp+0D0h+var_88], 153h
0x1400031c8  mov     r9, [r9+40h]
0x1400031cc  mov     [rsp+0D0h+var_90], rax
0x1400031d1  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400031d8  mov     [rsp+0D0h+var_98], rax
0x1400031dd  mov     word ptr [rsp+0D0h+var_A0], 0Dh
0x1400031e4  mov     dword ptr [rsp+0D0h+var_A8], 5
0x1400031ec  mov     [rsp+0D0h+var_B0], 2
0x1400031f1  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x1400031f6  mov     edi, 0C0000022h
0x1400031fb  jmp     loc_1400033EC
0x140003200  mov     r8, qword ptr [rbp+3Fh+Context+7]
0x140003204  test    r8, r8
0x140003207  jz      short loc_14000320F
0x140003209  cmp     [rbp+3Fh+P], rbx
0x14000320d  jz      short loc_140003218
0x14000320f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003214  mov     r8, qword ptr [rbp+3Fh+Context+7]
0x140003218  cmp     [r8+119h], bl
0x14000321f  jz      short loc_14000322A
0x140003221  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003226  mov     r8, qword ptr [rbp+3Fh+Context+7]; Context
0x14000322a  lea     rax, [rbp+3Fh+var_60]
0x14000322e  mov     rdx, rsi; FileObject
0x140003231  lea     r9, [rbp+3Fh+var_70]
0x140003235  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x14000323a  mov     rcx, r13; Instance
0x14000323d  call    PrjfGetSetStreamContext
0x140003242  mov     edi, eax
0x140003244  test    eax, eax
0x140003246  jns     short loc_1400032C5
0x140003248  mov     dl, byte ptr cs:xmmword_14001A3E0
0x14000324e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140003255  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000325c  setnz   r8b
0x140003260  and     dl, 20h
0x140003263  jnz     short loc_14000326A
0x140003265  test    r8b, r8b
0x140003268  jz      short loc_1400032BC
0x14000326a  mov     r9, cs:WPP_GLOBAL_Control
0x140003271  mov     ecx, 405h
0x140003276  mov     [rsp+0D0h+var_78], eax
0x14000327a  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140003281  mov     [rsp+0D0h+var_80], rsi
0x140003286  mov     [rsp+0D0h+var_88], 16Eh
0x14000328e  mov     r9, [r9+40h]
0x140003292  mov     [rsp+0D0h+var_90], rax
0x140003297  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x14000329e  mov     [rsp+0D0h+var_98], rax
0x1400032a3  mov     word ptr [rsp+0D0h+var_A0], 0Eh
0x1400032aa  mov     dword ptr [rsp+0D0h+var_A8], 5
0x1400032b2  mov     [rsp+0D0h+var_B0], 4
0x1400032b7  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x1400032bc  mov     rbx, [rbp+3Fh+var_60]
0x1400032c0  jmp     loc_1400033D6
0x1400032c5  mov     rbx, [rbp+3Fh+var_60]
0x1400032c9  test    rbx, rbx
0x1400032cc  jnz     short loc_1400032D3
0x1400032ce  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400032d3  mov     ecx, 80000000h
0x1400032d8  cmp     r14d, ecx
0x1400032db  jz      short loc_1400032E1
0x1400032dd  mov     [rbx+28h], r14d
0x1400032e1  mov     al, [rbp+3Fh+arg_20]
0x1400032e4  cmp     [rbp+3Fh+arg_18], r12b
0x1400032e8  jnz     short loc_140003300
0x1400032ea  test    al, al
0x1400032ec  jnz     short loc_140003300
0x1400032ee  cmp     r14d, r15d
0x1400032f1  jz      loc_1400033AD
0x1400032f7  cmp     r14d, ecx
0x1400032fa  jz      loc_1400033AD
0x140003300  mov     r8, qword ptr [rbp+3Fh+Context+7]; Context
0x140003304  lea     rcx, [rbp+3Fh+var_58]
0x140003308  mov     [rsp+0D0h+var_A8], rcx; __int64
0x14000330d  mov     r9, rbx
0x140003310  mov     rcx, r13; Instance
0x140003313  mov     [rsp+0D0h+var_B0], al; char
0x140003317  mov     rdx, rsi; FileObject
0x14000331a  call    PrjfGetSetStreamHandleContext
0x14000331f  mov     edi, eax
0x140003321  test    eax, eax
0x140003323  jns     short loc_14000339F
0x140003325  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14000332b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140003332  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003339  setnz   r8b
0x14000333d  and     dl, 20h
0x140003340  jnz     short loc_140003347
0x140003342  test    r8b, r8b
0x140003345  jz      short loc_140003399
0x140003347  mov     r9, cs:WPP_GLOBAL_Control
0x14000334e  mov     ecx, 205h
0x140003353  mov     [rsp+0D0h+var_78], eax
0x140003357  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000335e  mov     [rsp+0D0h+var_80], rsi
0x140003363  mov     [rsp+0D0h+var_88], 194h
0x14000336b  mov     r9, [r9+40h]
0x14000336f  mov     [rsp+0D0h+var_90], rax
0x140003374  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x14000337b  mov     [rsp+0D0h+var_98], rax
0x140003380  mov     word ptr [rsp+0D0h+var_A0], 0Fh
0x140003387  mov     dword ptr [rsp+0D0h+var_A8], 5
0x14000338f  mov     [rsp+0D0h+var_B0], 2
0x140003394  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x140003399  mov     r12, [rbp+3Fh+var_58]
0x14000339d  jmp     short loc_1400033D6
0x14000339f  mov     r12, [rbp+3Fh+var_58]
0x1400033a3  test    r12, r12
0x1400033a6  jnz     short loc_1400033AD
0x1400033a8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400033ad  mov     rax, qword ptr [rbp+3Fh+Context+7]
0x1400033b1  mov     rcx, [rbp+3Fh+arg_38]
0x1400033b8  mov     qword ptr [rbp+3Fh+Context+7], 0
0x1400033c0  mov     [rbp+3Fh+Context], 0
0x1400033c4  mov     [rcx], rax
0x1400033c7  mov     rax, [rbp+3Fh+arg_40]
0x1400033ce  mov     [rax], rbx
0x1400033d1  xor     ebx, ebx
0x1400033d3  mov     [rbp+3Fh+var_70], bl
0x1400033d6  test    rbx, rbx
0x1400033d9  jz      short loc_1400033EA
0x1400033db  mov     rcx, rbx; Context
0x1400033de  call    cs:__imp_FltReleaseContext
0x1400033e5  nop     dword ptr [rax+rax+00h]
0x1400033ea  xor     ebx, ebx
0x1400033ec  mov     rcx, qword ptr [rbp+3Fh+Context+7]; Context
0x1400033f0  test    rcx, rcx
0x1400033f3  jz      short loc_140003401
0x1400033f5  call    cs:__imp_FltReleaseContext
0x1400033fc  nop     dword ptr [rax+rax+00h]
0x140003401  test    r12, r12
0x140003404  jz      short loc_140003415
0x140003406  mov     rcx, r12; Context
0x140003409  call    cs:__imp_FltReleaseContext
0x140003410  nop     dword ptr [rax+rax+00h]
0x140003415  cmp     [rbp+3Fh+var_70], bl
0x140003418  jz      short loc_14000342F
0x14000341a  xor     r8d, r8d; OldContext
0x14000341d  mov     rdx, rsi; FileObject
0x140003420  mov     rcx, r13; Instance
0x140003423  call    cs:__imp_FltDeleteStreamContext
0x14000342a  nop     dword ptr [rax+rax+00h]
0x14000342f  cmp     [rbp+3Fh+Context], bl
0x140003432  jz      short loc_140003449
0x140003434  xor     r8d, r8d; OldContext
0x140003437  mov     rdx, rsi; FileObject
0x14000343a  mov     rcx, r13; Instance
0x14000343d  call    cs:__imp_FltDeleteFileContext
0x140003444  nop     dword ptr [rax+rax+00h]
0x140003449  mov     rcx, [rbp+3Fh+P]; P
0x14000344d  test    rcx, rcx
0x140003450  jz      short loc_140003463
0x140003452  mov     edx, 69724A50h; Tag
0x140003457  call    cs:__imp_ExFreePoolWithTag
0x14000345e  nop     dword ptr [rax+rax+00h]
0x140003463  mov     eax, edi
  ... truncated ...
```
