# PrjfGetSetFileContext

- ea: `0x140021550`
- end: `0x14002179e`
- name: `PrjfGetSetFileContext`
- size: `590`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002f3c`
- `0x14003cc14`
- `0x14003d620`
- `0x140042658`
- `0x140042eac`

## callees

- `0x140001658`
- `0x14000b1d0`
- `0x14000d128`
- `0x140021550`

## import_xrefs

- `FLTMGR!FltSetFileContext` at `0x140021696`
- `FLTMGR!FltSetFileContext` at `0x140021696`
- `FLTMGR!FltGetInstanceContext` at `0x140021591`
- `FLTMGR!FltGetInstanceContext` at `0x140021591`
- `FLTMGR!FltReleaseContext` at `0x1400216af`
- `FLTMGR!FltReleaseContext` at `0x140021767`
- `FLTMGR!FltReleaseContext` at `0x14002177b`
- `FLTMGR!FltReleaseContext` at `0x1400216af`
- `FLTMGR!FltReleaseContext` at `0x140021767`
- `FLTMGR!FltReleaseContext` at `0x14002177b`

## pseudocode

```c
__int64 __fastcall PrjfGetSetFileContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        char a3,
        _QWORD *a4,
        __int128 *a5,
        __int64 a6,
        char *a7,
        _QWORD *a8)
{
  PFLT_CONTEXT v12; // rcx
  int v13; // edx
  __int64 v14; // rcx
  int v15; // edi
  int v16; // r8d
  PFLT_CONTEXT v17; // rbx
  _BYTE *v18; // rbx
  char v19; // si
  __int64 v20; // rcx
  int v21; // edx
  int v22; // r8d
  PFLT_CONTEXT NewContext; // [rsp+60h] [rbp-21h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-19h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+70h] [rbp-11h] BYREF

  NewContext = 0;
  OldContext = 0;
  Context = 0;
  *a8 = 0;
  if ( FltGetInstanceContext(Instance, &Context) < 0 || (v12 = Context) == 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12);
    v12 = Context;
  }
  v15 = PrjfCreateFileContext(v12, a3, a5, (__int16 *)a6, a4, &NewContext);
  if ( v15 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        521,
        v13,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        23,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        76,
        v15);
    }
    v17 = NewContext;
    goto LABEL_27;
  }
  if ( !a3 )
  {
    if ( a6 && *(_QWORD *)(a6 + 8) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14);
    if ( a4 && *a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v14);
  }
  v18 = NewContext;
  v19 = 1;
  v15 = FltSetFileContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &OldContext);
  if ( v15 < 0 )
  {
    FltReleaseContext(v18);
    v17 = 0;
    if ( v15 != -1071906814 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          521,
          v21,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          24,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          108,
          v15);
      }
      goto LABEL_27;
    }
    v18 = OldContext;
    v19 = 0;
    v15 = 0;
  }
  if ( a7 )
    *a7 = v19;
  if ( v18[281] != a3 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v20);
  *a8 = v18;
  v17 = 0;
LABEL_27:
  if ( Context )
    FltReleaseContext(Context);
  if ( v17 )
    FltReleaseContext(v17);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140021550  push    rbp
0x140021552  push    rbx
0x140021553  push    rsi
0x140021554  push    rdi
0x140021555  push    r12
0x140021557  push    r13
0x140021559  push    r14
0x14002155b  push    r15
0x14002155d  lea     rbp, [rsp-7]
0x140021562  sub     rsp, 88h
0x140021569  mov     r15, [rbp+3Fh+arg_38]
0x140021570  xor     ebx, ebx
0x140021572  mov     r13, rdx
0x140021575  mov     [rbp+3Fh+NewContext], rbx
0x140021579  lea     rdx, [rbp+3Fh+Context]; Context
0x14002157d  mov     [rbp+3Fh+var_50], rbx
0x140021581  mov     rsi, r9
0x140021584  mov     [rbp+3Fh+Context], rbx
0x140021588  mov     [r15], rbx
0x14002158b  mov     r14b, r8b
0x14002158e  mov     r12, rcx
0x140021591  call    cs:__imp_FltGetInstanceContext
0x140021598  nop     dword ptr [rax+rax+00h]
0x14002159d  test    eax, eax
0x14002159f  js      short loc_1400215AA
0x1400215a1  mov     rcx, [rbp+3Fh+Context]
0x1400215a5  test    rcx, rcx
0x1400215a8  jnz     short loc_1400215B3
0x1400215aa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400215af  mov     rcx, [rbp+3Fh+Context]; Context
0x1400215b3  mov     rbx, [rbp+3Fh+arg_28]
0x1400215b7  lea     rax, [rbp+3Fh+NewContext]
0x1400215bb  mov     r8, [rbp+3Fh+arg_20]
0x1400215bf  mov     r9, rbx
0x1400215c2  mov     [rsp+0C0h+var_98], rax; __int64
0x1400215c7  mov     dl, r14b
0x1400215ca  mov     [rsp+0C0h+OldContext], rsi; __int64
0x1400215cf  call    PrjfCreateFileContext
0x1400215d4  mov     edi, eax
0x1400215d6  test    eax, eax
0x1400215d8  jns     short loc_140021652
0x1400215da  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400215e0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400215e7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400215ee  setnz   r8b
0x1400215f2  and     dl, 2
0x1400215f5  jnz     short loc_1400215FC
0x1400215f7  test    r8b, r8b
0x1400215fa  jz      short loc_140021649
0x1400215fc  mov     r9, cs:WPP_GLOBAL_Control
0x140021603  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002160a  mov     [rsp+0C0h+var_70], edi
0x14002160e  mov     ecx, 209h
0x140021613  mov     [rsp+0C0h+var_78], 44Ch
0x14002161b  mov     [rsp+0C0h+var_80], rax
0x140021620  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021627  mov     r9, [r9+40h]
0x14002162b  mov     [rsp+0C0h+var_88], rax
0x140021630  mov     [rsp+0C0h+var_90], 17h
0x140021637  mov     dword ptr [rsp+0C0h+var_98], 9
0x14002163f  mov     byte ptr [rsp+0C0h+OldContext], 2
0x140021644  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021649  mov     rbx, [rbp+3Fh+NewContext]
0x14002164d  jmp     loc_14002175E
0x140021652  test    r14b, r14b
0x140021655  jnz     short loc_140021678
0x140021657  test    rbx, rbx
0x14002165a  jz      short loc_140021668
0x14002165c  cmp     qword ptr [rbx+8], 0
0x140021661  jz      short loc_140021668
0x140021663  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140021668  test    rsi, rsi
0x14002166b  jz      short loc_140021678
0x14002166d  cmp     qword ptr [rsi], 0
0x140021671  jz      short loc_140021678
0x140021673  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140021678  mov     rbx, [rbp+3Fh+NewContext]
0x14002167c  lea     rax, [rbp+3Fh+var_50]
0x140021680  mov     esi, 1
0x140021685  mov     [rsp+0C0h+OldContext], rax; OldContext
0x14002168a  mov     r9, rbx; NewContext
0x14002168d  mov     r8d, esi; Operation
0x140021690  mov     rdx, r13; FileObject
0x140021693  mov     rcx, r12; Instance
0x140021696  call    cs:__imp_FltSetFileContext
0x14002169d  nop     dword ptr [rax+rax+00h]
0x1400216a2  mov     edi, eax
0x1400216a4  test    eax, eax
0x1400216a6  jns     loc_14002173F
0x1400216ac  mov     rcx, rbx; Context
0x1400216af  call    cs:__imp_FltReleaseContext
0x1400216b6  nop     dword ptr [rax+rax+00h]
0x1400216bb  xor     ebx, ebx
0x1400216bd  cmp     edi, 0C01C0002h
0x1400216c3  jz      short loc_140021736
0x1400216c5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400216cb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400216d2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400216d9  setnz   r8b
0x1400216dd  and     dl, 2
0x1400216e0  jnz     short loc_1400216E7
0x1400216e2  test    r8b, r8b
0x1400216e5  jz      short loc_14002175E
0x1400216e7  mov     r9, cs:WPP_GLOBAL_Control
0x1400216ee  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400216f5  mov     [rsp+0C0h+var_70], edi
0x1400216f9  mov     ecx, 209h
0x1400216fe  mov     [rsp+0C0h+var_78], 46Ch
0x140021706  mov     [rsp+0C0h+var_80], rax
0x14002170b  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021712  mov     r9, [r9+40h]
0x140021716  mov     [rsp+0C0h+var_88], rax
0x14002171b  mov     [rsp+0C0h+var_90], 18h
0x140021722  mov     dword ptr [rsp+0C0h+var_98], 9
0x14002172a  mov     byte ptr [rsp+0C0h+OldContext], 2
0x14002172f  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140021734  jmp     short loc_14002175E
0x140021736  mov     rbx, [rbp+3Fh+var_50]
0x14002173a  xor     sil, sil
0x14002173d  xor     edi, edi
0x14002173f  mov     rax, [rbp+3Fh+arg_30]
0x140021743  test    rax, rax
0x140021746  jz      short loc_14002174B
0x140021748  mov     [rax], sil
0x14002174b  cmp     [rbx+119h], r14b
0x140021752  jz      short loc_140021759
0x140021754  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140021759  mov     [r15], rbx
0x14002175c  xor     ebx, ebx
0x14002175e  mov     rcx, [rbp+3Fh+Context]; Context
0x140021762  test    rcx, rcx
0x140021765  jz      short loc_140021773
0x140021767  call    cs:__imp_FltReleaseContext
0x14002176e  nop     dword ptr [rax+rax+00h]
0x140021773  test    rbx, rbx
0x140021776  jz      short loc_140021787
0x140021778  mov     rcx, rbx; Context
0x14002177b  call    cs:__imp_FltReleaseContext
0x140021782  nop     dword ptr [rax+rax+00h]
0x140021787  mov     eax, edi
0x140021789  add     rsp, 88h
0x140021790  pop     r15
0x140021792  pop     r14
0x140021794  pop     r13
0x140021796  pop     r12
0x140021798  pop     rdi
0x140021799  pop     rsi
0x14002179a  pop     rbx
0x14002179b  pop     rbp
0x14002179c  retn
```
