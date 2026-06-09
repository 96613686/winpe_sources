# Rdp::Avenc::Umrdp::CGpuFrameProcessor::ReleaseAndAcquireReady(void)

- ea: `0x18001d6d0`
- end: `0x18001d978`
- name: `?ReleaseAndAcquireReady@CGpuFrameProcessor@Umrdp@Avenc@Rdp@@UEAAJXZ`
- size: `680`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CGpuFrameProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002470`
- `0x1800153f8`
- `0x180015480`
- `0x18001ce50`
- `0x18001d494`
- `0x18001d6d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d934`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d934`

## string_xrefs

- `0x18001d7f1`: `GPU readback mode has changed`
- `0x18001d8bd`: `Rdp::Avenc::Umrdp::CGpuFrameProcessor::ReleaseAndAcquireReady`
- `0x18001d8c4`: `GpuReadbackModeChange: Id %d, Readback %d`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CGpuFrameProcessor::ReleaseAndAcquireReady(
        Rdp::Avenc::Umrdp::CGpuFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // bl
  bool v6; // si
  bool v7; // r13
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  int v11; // esi
  __int64 v12; // rdx
  const char *v13; // r9
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  int v19; // r8d
  int v20; // [rsp+20h] [rbp-A8h]
  __int64 v21; // [rsp+28h] [rbp-A0h]
  __int16 v22[4]; // [rsp+30h] [rbp-98h]
  const char *v23; // [rsp+60h] [rbp-68h] BYREF
  int *v24; // [rsp+68h] [rbp-60h] BYREF
  const char *v25; // [rsp+70h] [rbp-58h] BYREF
  __int64 v26; // [rsp+78h] [rbp-50h] BYREF
  const char *v27; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  int v30; // [rsp+D8h] [rbp+10h] BYREF
  int v31; // [rsp+E0h] [rbp+18h] BYREF
  int v32; // [rsp+E8h] [rbp+20h] BYREF

  v5 = 1;
  v6 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      14,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      CurrentThreadId);
  }
  v11 = *(unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)this + 3) + 120LL) + 206LL);
  if ( *((_BYTE *)this + 56) != (_BYTE)v11 )
  {
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v30 = *(unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)this + 3) + 120LL) + 206LL);
      v12 = *((_QWORD *)this + 3);
      v31 = *(_DWORD *)(*(_QWORD *)(v12 + 120) + 196LL);
      v32 = *(_DWORD *)(v12 + 128);
      v23 = "GPU readback mode has changed";
      v24 = &xmmword_1800C21A0;
      v25 = "RdpAvenc";
      v26 = 0x1000000;
      v27 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&unk_1800AD768,
        a3,
        a4,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
    *(_DWORD *)v22 = v11;
    try
    {
      LODWORD(v21) = *(_DWORD *)(*((_QWORD *)this + 3) + 128LL);
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        (wchar_t *)L"GpuReadbackModeChange: Id %d, Readback %d",
        "Rdp::Avenc::Umrdp::CGpuFrameProcessor::ReleaseAndAcquireReady",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
        0x1FAu,
        v21,
        *(_QWORD *)v22);
      *((_BYTE *)this + 56) = v11;
      Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::DestroyRdpSurface((char *)this - 80);
      Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface((Rdp::Avenc::Umrdp::CGpuFrameProcessor *)((char *)this - 80));
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
        v13);
      Rdp::Avenc::Umrdp::CUmrdpProcessor::ReportCriticalError(
        *(Rdp::Avenc::Umrdp::CUmrdpProcessor **)(*((_QWORD *)this + 3) + 120LL),
        3u,
        v19);
      v5 = 1;
    }
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v5 = 0;
  }
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = GetCurrentThreadId();
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v20,
      v21,
      15,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d6d0  mov     [rsp+arg_0], rcx
0x18001d6d5  push    rbx
0x18001d6d6  push    rsi
0x18001d6d7  push    rdi
0x18001d6d8  push    r12
0x18001d6da  push    r13
0x18001d6dc  push    r14
0x18001d6de  push    r15
0x18001d6e0  sub     rsp, 90h
0x18001d6e7  mov     rdi, rcx
0x18001d6ea  lea     r14, WPP_GLOBAL_Control
0x18001d6f1  mov     rax, cs:WPP_GLOBAL_Control
0x18001d6f8  mov     bl, 1
0x18001d6fa  cmp     rax, r14
0x18001d6fd  jz      short loc_18001D70F
0x18001d6ff  test    [rax+1Ch], bl
0x18001d702  jz      short loc_18001D70F
0x18001d704  cmp     byte ptr [rax+19h], 4
0x18001d708  jb      short loc_18001D70F
0x18001d70a  mov     sil, bl
0x18001d70d  jmp     short loc_18001D712
0x18001d70f  xor     sil, sil
0x18001d712  lea     r12, WPP_RECORDER_INITIALIZED
0x18001d719  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001d720  setnz   r13b
0x18001d724  test    sil, sil
0x18001d727  jnz     short loc_18001D737
0x18001d729  test    r13b, r13b
0x18001d72c  jnz     short loc_18001D737
0x18001d72e  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001d735  jmp     short loc_18001D76F
0x18001d737  call    cs:__imp_GetCurrentThreadId
0x18001d73d  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18001d741  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001d748  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x18001d74d  mov     [rsp+0C8h+var_98], 0Eh; __int16
0x18001d754  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d75b  mov     r9, [rcx+28h]; int
0x18001d75f  mov     r8b, r13b; int
0x18001d762  mov     dl, sil; int
0x18001d765  mov     rcx, [rcx+10h]; int
0x18001d769  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001d76e  nop
0x18001d76f  mov     rax, [rdi+18h]
0x18001d773  mov     rcx, [rax+78h]
0x18001d777  movzx   esi, byte ptr [rcx+0CEh]
0x18001d77e  nop
0x18001d77f  cmp     [rdi+38h], sil
0x18001d783  jz      loc_18001D8EE
0x18001d789  mov     eax, cs:dword_1800C1058
0x18001d78f  cmp     eax, 4
0x18001d792  jbe     loc_18001D89C
0x18001d798  mov     rcx, cs:qword_1800C1070
0x18001d79f  mov     rax, cs:qword_1800C1068
0x18001d7a6  mov     rdx, 470000000000h
0x18001d7b0  test    rdx, rax
0x18001d7b3  jz      loc_18001D89C
0x18001d7b9  mov     rax, rcx
0x18001d7bc  and     rax, rdx
0x18001d7bf  cmp     rax, rcx
0x18001d7c2  jnz     loc_18001D89C
0x18001d7c8  mov     [rsp+0C8h+arg_8], esi
0x18001d7cf  mov     rdx, [rdi+18h]
0x18001d7d3  mov     rax, [rdx+78h]
0x18001d7d7  mov     ecx, [rax+0C4h]
0x18001d7dd  mov     [rsp+0C8h+arg_10], ecx
0x18001d7e4  mov     eax, [rdx+80h]
0x18001d7ea  mov     [rsp+0C8h+arg_18], eax
0x18001d7f1  lea     rax, aGpuReadbackMod; "GPU readback mode has changed"
0x18001d7f8  mov     [rsp+0C8h+var_68], rax
0x18001d7fd  lea     rax, xmmword_1800C21A0
0x18001d804  mov     [rsp+0C8h+var_60], rax
0x18001d809  lea     rax, aRdpavenc; "RdpAvenc"
0x18001d810  mov     [rsp+0C8h+var_58], rax
0x18001d815  mov     [rsp+0C8h+var_50], 1000000h
0x18001d81e  lea     rax, aCheckpoint; "Checkpoint"
0x18001d825  mov     [rsp+0C8h+var_48], rax
0x18001d82d  lea     rax, [rsp+0C8h+arg_8]
0x18001d835  mov     [rsp+0C8h+var_70], rax
0x18001d83a  lea     rax, [rsp+0C8h+arg_10]
0x18001d842  mov     [rsp+0C8h+var_78], rax
0x18001d847  lea     rax, [rsp+0C8h+arg_18]
0x18001d84f  mov     [rsp+0C8h+var_80], rax
0x18001d854  lea     rax, [rsp+0C8h+var_68]
0x18001d859  mov     qword ptr [rsp+0C8h+var_88], rax
0x18001d85e  lea     rax, [rsp+0C8h+var_60]
0x18001d863  mov     [rsp+0C8h+MessageGuid], rax
0x18001d868  lea     rax, [rsp+0C8h+var_58]
0x18001d86d  mov     qword ptr [rsp+0C8h+var_98], rax
0x18001d872  lea     rax, [rsp+0C8h+var_50]
0x18001d877  mov     [rsp+0C8h+var_A0], rax
0x18001d87c  lea     rax, [rsp+0C8h+var_48]
0x18001d884  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18001d889  lea     rdx, unk_1800AD768
0x18001d890  lea     rcx, dword_1800C1058
0x18001d897  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d89c  mov     rcx, [rdi+18h]
0x18001d8a0  mov     dword ptr [rsp+0C8h+var_98], esi
0x18001d8a4  mov     eax, [rcx+80h]
0x18001d8aa  mov     dword ptr [rsp+0C8h+var_A0], eax
0x18001d8ae  mov     [rsp+0C8h+var_A8], 1FAh; unsigned int
0x18001d8b6  lea     r9, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001d8bd  lea     r8, aRdpAvencUmrdpC_0; "Rdp::Avenc::Umrdp::CGpuFrameProcessor::"...
0x18001d8c4  lea     rdx, aGpureadbackmod; "GpuReadbackModeChange: Id %d, Readback "...
0x18001d8cb  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001d8d2  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001d8d7  mov     [rdi+38h], sil
0x18001d8db  lea     rcx, [rdi-50h]
0x18001d8df  call    ?DestroyRdpSurface@?$CFrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@@Umrdp@Avenc@Rdp@@IEAAXXZ; Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::DestroyRdpSurface(void)
0x18001d8e4  lea     rcx, [rdi-50h]; this
0x18001d8e8  call    ?CreateRdpSurface@CGpuFrameProcessor@Umrdp@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Umrdp::CGpuFrameProcessor::CreateRdpSurface(void)
0x18001d8ed  nop
0x18001d8ee  jmp     short loc_18001D907
0x18001d8f0  lea     r14, WPP_GLOBAL_Control
0x18001d8f7  mov     bl, 1
0x18001d8f9  lea     r12, WPP_RECORDER_INITIALIZED
0x18001d900  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001d907  mov     rax, cs:WPP_GLOBAL_Control
0x18001d90e  cmp     rax, r14
0x18001d911  jz      short loc_18001D91E
0x18001d913  test    [rax+1Ch], bl
0x18001d916  jz      short loc_18001D91E
0x18001d918  cmp     byte ptr [rax+19h], 4
0x18001d91c  jnb     short loc_18001D920
0x18001d91e  xor     bl, bl
0x18001d920  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001d927  setnz   dil
0x18001d92b  test    bl, bl
0x18001d92d  jnz     short loc_18001D934
0x18001d92f  test    dil, dil
0x18001d932  jz      short loc_18001D963
0x18001d934  call    cs:__imp_GetCurrentThreadId
0x18001d93a  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18001d93e  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x18001d943  mov     [rsp+0C8h+var_98], 0Fh; __int16
0x18001d94a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d951  mov     r9, [rcx+28h]; int
0x18001d955  mov     r8b, dil; int
0x18001d958  mov     dl, bl; int
0x18001d95a  mov     rcx, [rcx+10h]; int
0x18001d95e  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001d963  xor     eax, eax
0x18001d965  add     rsp, 90h
0x18001d96c  pop     r15
0x18001d96e  pop     r14
0x18001d970  pop     r13
0x18001d972  pop     r12
0x18001d974  pop     rdi
0x18001d975  pop     rsi
0x18001d976  pop     rbx
0x18001d977  retn
```
