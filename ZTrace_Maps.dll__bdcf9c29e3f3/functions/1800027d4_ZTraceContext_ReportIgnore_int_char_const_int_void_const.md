# ZTraceContext::ReportIgnore(int,char const *,int,void const *)

- ea: `0x1800027d4`
- end: `0x1800028cb`
- name: `?ReportIgnore@ZTraceContext@@QEAAXHPEBDHPEBX@Z`
- size: `247`
- prototype: `void __fastcall(ZTraceContext *__hidden this, int, const char *, int, const void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003320`
- `0x180003350`

## callees

- `0x1800024bc`
- `0x1800027d4`
- `0x1800037b4`
- `0x180003854`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002832`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002890`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002832`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002890`

## pseudocode

```c
void __fastcall ZTraceContext::ReportIgnore(ZTraceContext *this, int a2, const char *a3, int a4, const void *a5)
{
  ZTracer *v5; // r14

  v5 = qword_1800072B8;
  if ( qword_1800072B8 )
  {
    if ( a5 == (const void *)-1LL )
    {
      if ( (Microsoft_Windows_ZTraceMapsEnableBits & 2) != 0 )
        McTemplateU0dsd_EventWriteTransfer((_DWORD)this, (unsigned int)FlowControl_IgnoreNoThis, a2, (_DWORD)a3, a4);
      if ( s_fShouldSpewDebug )
      {
        if ( IsDebuggerPresent() )
          ZTracer::DebugMsg(v5, "%s:%s: originated %08x (%d)", "[Z!I] ", a3, a2, a4);
      }
    }
    else
    {
      if ( (Microsoft_Windows_ZTraceMapsEnableBits & 2) != 0 )
        McTemplateU0dspd_EventWriteTransfer(
          (_DWORD)this,
          (unsigned int)FlowControl_Ignore,
          a2,
          (_DWORD)a3,
          (char)a5,
          a4);
      if ( s_fShouldSpewDebug && IsDebuggerPresent() )
        ZTracer::DebugMsg(v5, "%s:%s@%p: originated %08x (%d)", "[Z!I] ", a3, a5, a2, a4);
    }
  }
}

```

## disassembly

```asm
0x1800027d4  push    rbx
0x1800027d6  push    rbp
0x1800027d7  push    rsi
0x1800027d8  push    rdi
0x1800027d9  push    r14
0x1800027db  sub     rsp, 40h
0x1800027df  mov     r14, cs:qword_1800072B8
0x1800027e6  mov     edi, r9d
0x1800027e9  mov     rsi, r8
0x1800027ec  mov     ebp, edx
0x1800027ee  test    r14, r14
0x1800027f1  jz      loc_1800028C0
0x1800027f7  mov     rbx, [rsp+68h+arg_20]
0x1800027ff  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002803  jnz     short loc_180002863
0x180002805  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 2
0x18000280c  jz      short loc_180002825
0x18000280e  mov     dword ptr [rsp+68h+var_48], r9d
0x180002813  mov     r9, r8
0x180002816  mov     r8d, edx
0x180002819  lea     rdx, _FlowControl_IgnoreNoThis
0x180002820  call    McTemplateU0dsd_EventWriteTransfer
0x180002825  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x18000282c  jz      loc_1800028C0
0x180002832  call    cs:__imp_IsDebuggerPresent
0x180002838  test    eax, eax
0x18000283a  jz      loc_1800028C0
0x180002840  mov     [rsp+68h+var_40], edi
0x180002844  lea     r8, aZI; "[Z!I] "
0x18000284b  mov     r9, rsi
0x18000284e  mov     dword ptr [rsp+68h+var_48], ebp
0x180002852  lea     rdx, aSSOriginated08; "%s:%s: originated %08x (%d)"
0x180002859  mov     rcx, r14; this
0x18000285c  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x180002861  jmp     short loc_1800028C0
0x180002863  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 2
0x18000286a  jz      short loc_180002887
0x18000286c  mov     [rsp+68h+var_40], edi
0x180002870  lea     rdx, _FlowControl_Ignore
0x180002877  mov     r9, rsi
0x18000287a  mov     [rsp+68h+var_48], rbx
0x18000287f  mov     r8d, ebp
0x180002882  call    McTemplateU0dspd_EventWriteTransfer
0x180002887  cmp     cs:?s_fShouldSpewDebug@@3HA, 0; int s_fShouldSpewDebug
0x18000288e  jz      short loc_1800028C0
0x180002890  call    cs:__imp_IsDebuggerPresent
0x180002896  test    eax, eax
0x180002898  jz      short loc_1800028C0
0x18000289a  mov     [rsp+68h+var_38], edi
0x18000289e  lea     r8, aZI; "[Z!I] "
0x1800028a5  mov     [rsp+68h+var_40], ebp
0x1800028a9  lea     rdx, aSSPOriginated0; "%s:%s@%p: originated %08x (%d)"
0x1800028b0  mov     r9, rsi
0x1800028b3  mov     [rsp+68h+var_48], rbx
0x1800028b8  mov     rcx, r14; this
0x1800028bb  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x1800028c0  add     rsp, 40h
0x1800028c4  pop     r14
0x1800028c6  pop     rdi
0x1800028c7  pop     rsi
0x1800028c8  pop     rbp
0x1800028c9  pop     rbx
0x1800028ca  retn
```
