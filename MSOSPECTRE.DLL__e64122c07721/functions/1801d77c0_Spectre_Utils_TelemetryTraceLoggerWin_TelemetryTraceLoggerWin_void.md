# Spectre::Utils::TelemetryTraceLoggerWin::TelemetryTraceLoggerWin(void)

- ea: `0x1801d77c0`
- end: `0x1801d7bbe`
- name: `??0TelemetryTraceLoggerWin@Utils@Spectre@@QEAA@XZ`
- size: `1022`
- prototype: `__int64 __fastcall(Spectre::Utils::TelemetryTraceLoggerWin *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1801d5bb0`

## callees

- `0x180016430`
- `0x1800423e0`
- `0x1801d7630`
- `0x1801d77c0`
- `0x1801d8960`
- `0x1801db2b0`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039f8e0`
- `0x1804f99e0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1801d7ad7`
- `KERNEL32!FreeLibrary` at `0x1801d7ad7`
- `KERNEL32!GetModuleHandleExW` at `0x1801d7a81`
- `KERNEL32!GetModuleHandleExW` at `0x1801d7a99`
- `KERNEL32!GetModuleHandleExW` at `0x1801d7a81`
- `KERNEL32!GetModuleHandleExW` at `0x1801d7a99`
- `KERNEL32!GetProcAddress` at `0x1801d7aaf`
- `KERNEL32!GetProcAddress` at `0x1801d7aaf`
- `KERNEL32!GetSystemInfo` at `0x1801d78b8`
- `KERNEL32!GetSystemInfo` at `0x1801d78b8`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x1801d792e`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x1801d792e`
- `api-ms-win-crt-heap-l1-1-0!_aligned_free` at `0x1801d79e8`
- `api-ms-win-crt-heap-l1-1-0!_aligned_free` at `0x1801d79e8`
- `ole32!CoCreateGuid` at `0x1801d795e`
- `ole32!CoCreateGuid` at `0x1801d795e`
- `ADVAPI32!EventRegister` at `0x1801d7a5f`
- `ADVAPI32!EventRegister` at `0x1801d7a5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
Spectre::Utils::TelemetryTraceLoggerWin *__fastcall Spectre::Utils::TelemetryTraceLoggerWin::TelemetryTraceLoggerWin(
        Spectre::Utils::TelemetryTraceLoggerWin *this)
{
  char *v2; // rbp
  __int64 v3; // rbx
  _OWORD *v4; // rax
  char *v5; // rsi
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  TraceLoggingCorrelationVector *v8; // rcx
  void *v9; // rbx
  unsigned int v10; // esi
  FARPROC ProcAddress; // rax
  _DWORD *v12; // rax
  _DWORD *v13; // rcx
  volatile signed __int32 *v14; // rbx
  char v16; // [rsp+40h] [rbp-C8h] BYREF
  GUID v17; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp-90h] BYREF
  GUID pguid; // [rsp+80h] [rbp-88h] BYREF
  GUID ProviderId; // [rsp+90h] [rbp-78h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+A0h] [rbp-68h] BYREF

  *(_QWORD *)this = &Spectre::Utils::TelemetryTraceLoggerWin::`vftable';
  v2 = (char *)this + 8;
  Spectre::Utils::TelemetryTraceUid::CreateUid((GUID **)this + 1);
  Spectre::Utils::TelemetryTraceUid::CreateUid((GUID **)this + 2);
  phModule = (HMODULE)((char *)this + 24);
  v3 = Spectre::Utils::TelemetryTraceUid::Zero;
  v4 = operator new(0x38u);
  if ( v4 )
  {
    *v4 = *(_OWORD *)v3;
    v4[1] = *(_OWORD *)(v3 + 16);
    v4[2] = *(_OWORD *)(v3 + 32);
    *((_QWORD *)v4 + 6) = *(_QWORD *)(v3 + 48);
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 3) = v4;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 15;
  *((_BYTE *)this + 48) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 15;
  *((_BYTE *)this + 80) = 0;
  std::string::assign((char *)this + 80);
  v5 = (char *)this + 112;
  *((_QWORD *)this + 14) = 0;
  GetSystemInfo(&SystemInfo);
  std::string::assign((char *)this + 48);
  v6 = _aligned_malloc(0xA0u, 8u);
  v7 = v6;
  if ( !v6 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  v6[19] = 64;
  pguid = 0;
  CoCreateGuid(&pguid);
  v17 = pguid;
  v7[17] = 17;
  v7[18] = 0x1300000000LL;
  *(_OWORD *)v7 = 0;
  *((_OWORD *)v7 + 1) = 0;
  *((_OWORD *)v7 + 2) = 0;
  *((_OWORD *)v7 + 3) = 0;
  *((_OWORD *)v7 + 4) = 0;
  *((_OWORD *)v7 + 5) = 0;
  *((_OWORD *)v7 + 6) = 0;
  *((_OWORD *)v7 + 7) = 0;
  *((_BYTE *)v7 + 128) = 0;
  TLV::Base64Encode<129>(&v17, 12, v7);
  *((_WORD *)v7 + 8) = 46;
  if ( v5 == &v16 )
  {
    v8 = (TraceLoggingCorrelationVector *)v7;
LABEL_9:
    _aligned_free(v8);
    goto LABEL_10;
  }
  v8 = *(TraceLoggingCorrelationVector **)v5;
  *(_QWORD *)v5 = v7;
  if ( v8 )
    goto LABEL_9;
LABEL_10:
  TraceLoggingCorrelationVector::ToStringImpl(
    *(TraceLoggingCorrelationVector **)v5,
    _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v5 + 144LL), 0),
    (char *)this + 120);
  if ( _InterlockedIncrement64(&qword_1807A1610) == 1 )
  {
    ProviderId = (GUID)*((_OWORD *)off_180754A38 - 1);
    qword_180754A58 = 0;
    qword_180754A60 = 0;
    if ( !EventRegister(&ProviderId, TlgEnableCallback, &dword_180754A30, &qword_180754A50) )
    {
      v9 = off_180754A38;
      v10 = *(unsigned __int16 *)off_180754A38;
      if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0", &phModule)
        || GetModuleHandleExW(0, L"advapi32", &phModule) )
      {
        ProcAddress = GetProcAddress(phModule, "EventSetInformation");
        if ( ProcAddress )
          ((void (__fastcall *)(ULONGLONG, __int64, void *, _QWORD))ProcAddress)(qword_180754A50, 2, v9, v10);
        FreeLibrary(phModule);
      }
    }
  }
  v12 = operator new(0x28u);
  v13 = v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    v12[2] = 1;
    v12[3] = 1;
    *(_QWORD *)v12 = &std::_Ref_count_obj2<Spectre::Utils::TelemTraceLoggerAttributes>::`vftable';
    *((_QWORD *)v12 + 2) = v2;
    *((_QWORD *)v12 + 3) = (char *)this + 16;
    *((_QWORD *)v12 + 4) = (char *)this + 48;
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 4) = v13 + 4;
  v14 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v13;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801d77c0  mov     [rsp+arg_8], rbx
0x1801d77c5  mov     [rsp+arg_10], rbp
0x1801d77ca  push    rsi
0x1801d77cb  push    rdi
0x1801d77cc  push    r12
0x1801d77ce  push    r14
0x1801d77d0  push    r15
0x1801d77d2  sub     rsp, 0E0h
0x1801d77d9  mov     rax, cs:__security_cookie
0x1801d77e0  xor     rax, rsp
0x1801d77e3  mov     [rsp+108h+var_38], rax
0x1801d77eb  mov     rdi, rcx
0x1801d77ee  mov     [rsp+108h+var_D0], rcx
0x1801d77f3  lea     rax, ??_7TelemetryTraceLoggerWin@Utils@Spectre@@6B@; const Spectre::Utils::TelemetryTraceLoggerWin::`vftable'
0x1801d77fa  mov     [rcx], rax
0x1801d77fd  lea     rbp, [rcx+8]
0x1801d7801  mov     rcx, rbp
0x1801d7804  call    ?CreateUid@TelemetryTraceUid@Utils@Spectre@@SA?AV123@XZ; Spectre::Utils::TelemetryTraceUid::CreateUid(void)
0x1801d7809  nop
0x1801d780a  lea     r15, [rdi+10h]
0x1801d780e  mov     rcx, r15
0x1801d7811  call    ?CreateUid@TelemetryTraceUid@Utils@Spectre@@SA?AV123@XZ; Spectre::Utils::TelemetryTraceUid::CreateUid(void)
0x1801d7816  nop
0x1801d7817  lea     rsi, [rdi+18h]
0x1801d781b  mov     [rsp+108h+phModule], rsi
0x1801d7820  mov     rbx, cs:?Zero@TelemetryTraceUid@Utils@Spectre@@2V123@B; Spectre::Utils::TelemetryTraceUid const Spectre::Utils::TelemetryTraceUid::Zero
0x1801d7827  mov     ecx, 38h ; '8'; Size
0x1801d782c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801d7831  xor     r12d, r12d
0x1801d7834  test    rax, rax
0x1801d7837  jz      short loc_1801D785B
0x1801d7839  movups  xmm0, xmmword ptr [rbx]
0x1801d783c  movups  xmmword ptr [rax], xmm0
0x1801d783f  movups  xmm1, xmmword ptr [rbx+10h]
0x1801d7843  movups  xmmword ptr [rax+10h], xmm1
0x1801d7847  movups  xmm0, xmmword ptr [rbx+20h]
0x1801d784b  movups  xmmword ptr [rax+20h], xmm0
0x1801d784f  movsd   xmm1, qword ptr [rbx+30h]
0x1801d7854  movsd   qword ptr [rax+30h], xmm1
0x1801d7859  jmp     short loc_1801D785E
0x1801d785b  mov     rax, r12
0x1801d785e  mov     [rsi], rax
0x1801d7861  mov     [rdi+20h], r12
0x1801d7865  mov     [rdi+28h], r12
0x1801d7869  lea     r14, [rdi+30h]
0x1801d786d  mov     [r14], r12
0x1801d7870  mov     [r14+10h], r12
0x1801d7874  mov     qword ptr [r14+18h], 0Fh
0x1801d787c  mov     byte ptr [r14], 0
0x1801d7880  lea     rcx, [rdi+50h]; void *
0x1801d7884  mov     [rcx], r12
0x1801d7887  mov     [rcx+10h], r12
0x1801d788b  mov     qword ptr [rcx+18h], 0Fh
0x1801d7893  mov     byte ptr [rcx], 0
0x1801d7896  mov     r8d, 0Dh
0x1801d789c  lea     rdx, aCanvasdefault; "CanvasDefault"
0x1801d78a3  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801d78a8  nop
0x1801d78a9  lea     rsi, [rdi+70h]
0x1801d78ad  mov     [rsi], r12
0x1801d78b0  lea     rcx, [rsp+108h+SystemInfo]; lpSystemInfo
0x1801d78b8  call    cs:__imp_GetSystemInfo
0x1801d78be  movzx   eax, word ptr [rsp+108h+SystemInfo]
0x1801d78c6  test    eax, eax
0x1801d78c8  jz      short loc_1801D790F
0x1801d78ca  cmp     eax, 5
0x1801d78cd  jz      short loc_1801D7900
0x1801d78cf  cmp     eax, 9
0x1801d78d2  jz      short loc_1801D78F1
0x1801d78d4  cmp     eax, 0Ch
0x1801d78d7  jz      short loc_1801D78E8
0x1801d78d9  lea     rdx, aUnknown; "UNKNOWN"
0x1801d78e0  mov     r8d, 7
0x1801d78e6  jmp     short loc_1801D791C
0x1801d78e8  lea     rdx, aArm64; "ARM64"
0x1801d78ef  jmp     short loc_1801D7916
0x1801d78f1  lea     rdx, aX64; "x64"
0x1801d78f8  mov     r8d, 3
0x1801d78fe  jmp     short loc_1801D791C
0x1801d7900  lea     rdx, aArm; "ARM"
0x1801d7907  mov     r8d, 3
0x1801d790d  jmp     short loc_1801D791C
0x1801d790f  lea     rdx, aWin32; "WIN32"
0x1801d7916  mov     r8d, 5
0x1801d791c  mov     rcx, r14; void *
0x1801d791f  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801d7924  mov     edx, 8; Alignment
0x1801d7929  mov     ecx, 0A0h; Size
0x1801d792e  call    cs:__imp__aligned_malloc
0x1801d7934  mov     rbx, rax
0x1801d7937  test    rax, rax
0x1801d793a  jz      loc_1801D7BA2
0x1801d7940  mov     qword ptr [rax+98h], 40h ; '@'
0x1801d794b  xorps   xmm0, xmm0
0x1801d794e  movups  xmmword ptr [rsp+108h+pguid.Data1], xmm0
0x1801d7956  lea     rcx, [rsp+108h+pguid]; pguid
0x1801d795e  call    cs:__imp_CoCreateGuid
0x1801d7964  movaps  xmm0, xmmword ptr [rsp+108h+pguid.Data1]
0x1801d796c  movdqa  [rsp+108h+var_B8], xmm0
0x1801d7972  mov     qword ptr [rbx+88h], 11h
0x1801d797d  mov     rax, 1300000000h
0x1801d7987  mov     [rbx+90h], rax
0x1801d798e  xorps   xmm0, xmm0
0x1801d7991  xor     eax, eax
0x1801d7993  movups  xmmword ptr [rbx], xmm0
0x1801d7996  movups  xmmword ptr [rbx+10h], xmm0
0x1801d799a  movups  xmmword ptr [rbx+20h], xmm0
0x1801d799e  movups  xmmword ptr [rbx+30h], xmm0
0x1801d79a2  movups  xmmword ptr [rbx+40h], xmm0
0x1801d79a6  movups  xmmword ptr [rbx+50h], xmm0
0x1801d79aa  movups  xmmword ptr [rbx+60h], xmm0
0x1801d79ae  movups  xmmword ptr [rbx+70h], xmm0
0x1801d79b2  mov     [rbx+80h], al
0x1801d79b8  mov     r8, rbx
0x1801d79bb  lea     edx, [rax+0Ch]
0x1801d79be  lea     rcx, [rsp+108h+var_B8]
0x1801d79c3  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,unsigned __int64,char (&)[129])
0x1801d79c8  mov     word ptr [rbx+10h], 2Eh ; '.'
0x1801d79ce  lea     rax, [rsp+108h+var_C8]
0x1801d79d3  cmp     rsi, rax
0x1801d79d6  jz      short loc_1801D79E5
0x1801d79d8  mov     rcx, [rsi]
0x1801d79db  mov     [rsi], rbx
0x1801d79de  test    rcx, rcx
0x1801d79e1  jz      short loc_1801D79EE
0x1801d79e3  jmp     short loc_1801D79E8
0x1801d79e5  mov     rcx, rbx; Block
0x1801d79e8  call    cs:__imp__aligned_free
0x1801d79ee  mov     rcx, [rsi]; this
0x1801d79f1  mov     rdx, r12
0x1801d79f4  lock xadd [rcx+90h], rdx; unsigned __int64
0x1801d79fd  lea     r8, [rdi+78h]; char *
0x1801d7a01  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801d7a06  mov     eax, 1
0x1801d7a0b  lock xadd cs:qword_1807A1610, rax
0x1801d7a14  inc     rax
0x1801d7a17  cmp     rax, 1
0x1801d7a1b  jnz     loc_1801D7ADD
0x1801d7a21  mov     rax, cs:off_180754A38
0x1801d7a28  movups  xmm0, xmmword ptr [rax-10h]
0x1801d7a2c  movups  xmmword ptr [rsp+108h+ProviderId.Data1], xmm0
0x1801d7a34  mov     cs:qword_180754A58, r12
0x1801d7a3b  mov     cs:qword_180754A60, r12
0x1801d7a42  lea     r9, qword_180754A50; RegHandle
0x1801d7a49  lea     r8, dword_180754A30; CallbackContext
0x1801d7a50  lea     rdx, _TlgEnableCallback; EnableCallback
0x1801d7a57  lea     rcx, [rsp+108h+ProviderId]; ProviderId
0x1801d7a5f  call    cs:__imp_EventRegister
0x1801d7a65  test    eax, eax
0x1801d7a67  jnz     short loc_1801D7ADD
0x1801d7a69  mov     rbx, cs:off_180754A38
0x1801d7a70  movzx   esi, word ptr [rbx]
0x1801d7a73  lea     r8, [rsp+108h+phModule]; phModule
0x1801d7a78  lea     rdx, aApiMsWinEventi; "api-ms-win-eventing-provider-l1-1-0"
0x1801d7a7f  xor     ecx, ecx; dwFlags
0x1801d7a81  call    cs:__imp_GetModuleHandleExW
0x1801d7a87  test    eax, eax
0x1801d7a89  jnz     short loc_1801D7AA3
0x1801d7a8b  lea     r8, [rsp+108h+phModule]; phModule
0x1801d7a90  lea     rdx, aAdvapi32; "advapi32"
0x1801d7a97  xor     ecx, ecx; dwFlags
0x1801d7a99  call    cs:__imp_GetModuleHandleExW
0x1801d7a9f  test    eax, eax
0x1801d7aa1  jz      short loc_1801D7ADD
0x1801d7aa3  lea     rdx, aEventsetinform; "EventSetInformation"
0x1801d7aaa  mov     rcx, [rsp+108h+phModule]; hModule
0x1801d7aaf  call    cs:__imp_GetProcAddress
0x1801d7ab5  test    rax, rax
0x1801d7ab8  jz      short loc_1801D7AD2
0x1801d7aba  mov     r9d, esi
0x1801d7abd  mov     r8, rbx
0x1801d7ac0  mov     edx, 2
0x1801d7ac5  mov     rcx, cs:qword_180754A50
0x1801d7acc  call    cs:__guard_dispatch_icall_fptr
0x1801d7ad2  mov     rcx, [rsp+108h+phModule]; hLibModule
0x1801d7ad7  call    cs:__imp_FreeLibrary
0x1801d7add  mov     ecx, 28h ; '('; Size
0x1801d7ae2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801d7ae7  mov     rcx, rax
0x1801d7aea  mov     [rsp+108h+var_D8], rax
0x1801d7aef  test    rax, rax
0x1801d7af2  jz      short loc_1801D7B20
0x1801d7af4  xorps   xmm0, xmm0
0x1801d7af7  movups  xmmword ptr [rax], xmm0
0x1801d7afa  mov     dword ptr [rax+8], 1
0x1801d7b01  mov     dword ptr [rax+0Ch], 1
0x1801d7b08  lea     rax, ??_7?$_Ref_count_obj2@UTelemTraceLoggerAttributes@Utils@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Utils::TelemTraceLoggerAttributes>::`vftable'
0x1801d7b0f  mov     [rcx], rax
0x1801d7b12  mov     [rcx+10h], rbp
0x1801d7b16  mov     [rcx+18h], r15
0x1801d7b1a  mov     [rcx+20h], r14
0x1801d7b1e  jmp     short loc_1801D7B23
0x1801d7b20  mov     rcx, r12
0x1801d7b23  lea     rax, [rcx+10h]
0x1801d7b27  mov     [rdi+20h], rax
0x1801d7b2b  mov     rbx, [rdi+28h]
0x1801d7b2f  mov     [rdi+28h], rcx
0x1801d7b33  test    rbx, rbx
0x1801d7b36  jz      short loc_1801D7B73
0x1801d7b38  mov     esi, 0FFFFFFFFh
0x1801d7b3d  mov     eax, esi
0x1801d7b3f  lock xadd [rbx+8], eax
0x1801d7b44  cmp     eax, 1
0x1801d7b47  jnz     short loc_1801D7B73
0x1801d7b49  mov     rax, [rbx]
0x1801d7b4c  mov     rcx, rbx
0x1801d7b4f  mov     rax, [rax]
0x1801d7b52  call    cs:__guard_dispatch_icall_fptr
0x1801d7b58  lock xadd [rbx+0Ch], esi
0x1801d7b5d  cmp     esi, 1
0x1801d7b60  jnz     short loc_1801D7B73
0x1801d7b62  mov     rdx, [rbx]
0x1801d7b65  mov     rcx, rbx
0x1801d7b68  mov     rax, [rdx+8]
0x1801d7b6c  call    cs:__guard_dispatch_icall_fptr
0x1801d7b72  nop
0x1801d7b73  mov     rax, rdi
0x1801d7b76  mov     rcx, [rsp+108h+var_38]
0x1801d7b7e  xor     rcx, rsp; StackCookie
0x1801d7b81  call    __security_check_cookie
0x1801d7b86  lea     r11, [rsp+108h+var_28]
0x1801d7b8e  mov     rbx, [r11+38h]
0x1801d7b92  mov     rbp, [r11+40h]
0x1801d7b96  mov     rsp, r11
0x1801d7b99  pop     r15
0x1801d7b9b  pop     r14
0x1801d7b9d  pop     r12
0x1801d7b9f  pop     rdi
0x1801d7ba0  pop     rsi
0x1801d7ba1  retn
0x1801d7ba2  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1801d7ba7  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1801d7bac  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1801d7bb3  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1801d7bb8  call    _CxxThrowException_0
```
