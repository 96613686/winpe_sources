# TelemetrySession::CreateTelemetrySession(TelemetrySession * *)

- ea: `0x18000c134`
- end: `0x18000c26b`
- name: `?CreateTelemetrySession@TelemetrySession@@SAJPEAPEAV1@@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct TelemetrySession **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a210`

## callees

- `0x180001404`
- `0x18000beb0`
- `0x18000c134`
- `0x18000c610`
- `0x18000d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c241`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c241`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c222`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c222`

## pseudocode

```c
__int64 __fastcall TelemetrySession::CreateTelemetrySession(struct TelemetrySession **a1)
{
  struct TelemetrySession *v3; // rax
  struct TelemetrySession *v4; // rbx
  TraceLoggingCorrelationVector *v5; // rax
  TraceLoggingCorrelationVector *v6; // rdx
  struct TelemetrySession *v7; // [rsp+20h] [rbp-28h]
  GUID ProviderId; // [rsp+28h] [rbp-20h] BYREF

  if ( byte_180015F68 )
    return 2147942583LL;
  v3 = (struct TelemetrySession *)operator new(0x10u);
  v4 = v3;
  v7 = v3;
  if ( v3 )
  {
    *((_QWORD *)v3 + 1) = 0;
    *(_QWORD *)v3 = &RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vftable';
    v5 = (TraceLoggingCorrelationVector *)operator new(0x90u);
    *(_QWORD *)&ProviderId.Data1 = v5;
    if ( v5 )
      v6 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v5);
    else
      v6 = 0;
    (*(void (__fastcall **)(struct TelemetrySession *, TraceLoggingCorrelationVector *))(*(_QWORD *)v4 + 48LL))(v4, v6);
  }
  else
  {
    v4 = 0;
  }
  if ( !v4 )
    return 2147942414LL;
  if ( !byte_180015F68 )
  {
    ProviderId = (GUID)*((_OWORD *)off_180015008 - 1);
    if ( RegHandle )
      __fastfail(5u);
    xmmword_180015028 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180015000, &RegHandle) )
      EventSetInformation(
        RegHandle,
        2,
        off_180015008,
        *(unsigned __int16 *)off_180015008,
        v7,
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    byte_180015F68 = 1;
  }
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x18000c134  mov     [rsp+arg_8], rbx
0x18000c139  push    rdi
0x18000c13a  sub     rsp, 40h
0x18000c13e  mov     rax, cs:__security_cookie
0x18000c145  xor     rax, rsp
0x18000c148  mov     [rsp+48h+var_10], rax
0x18000c14d  mov     rdi, rcx
0x18000c150  cmp     cs:byte_180015F68, 0
0x18000c157  jz      short loc_18000C163
0x18000c159  mov     eax, 800700B7h
0x18000c15e  jmp     loc_18000C253
0x18000c163  mov     ecx, 10h; Size
0x18000c168  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c16d  mov     rbx, rax
0x18000c170  mov     [rsp+48h+var_28], rax
0x18000c175  test    rax, rax
0x18000c178  jz      short loc_18000C1C1
0x18000c17a  mov     qword ptr [rax+8], 0
0x18000c182  lea     rax, ??_7?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@6B@; const RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vftable'
0x18000c189  mov     [rbx], rax
0x18000c18c  mov     ecx, 90h; Size
0x18000c191  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c196  mov     qword ptr [rsp+48h+ProviderId.Data1], rax
0x18000c19b  test    rax, rax
0x18000c19e  jz      short loc_18000C1AD
0x18000c1a0  mov     rcx, rax; this
0x18000c1a3  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18000c1a8  mov     rdx, rax
0x18000c1ab  jmp     short loc_18000C1AF
0x18000c1ad  xor     edx, edx
0x18000c1af  mov     rax, [rbx]
0x18000c1b2  mov     rcx, rbx
0x18000c1b5  mov     rax, [rax+30h]
0x18000c1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1be  nop
0x18000c1bf  jmp     short loc_18000C1C3
0x18000c1c1  xor     ebx, ebx
0x18000c1c3  test    rbx, rbx
0x18000c1c6  jnz     short loc_18000C1D2
0x18000c1c8  mov     eax, 8007000Eh
0x18000c1cd  jmp     loc_18000C253
0x18000c1d2  cmp     cs:byte_180015F68, 0
0x18000c1d9  jnz     short loc_18000C24E
0x18000c1db  mov     rax, cs:off_180015008
0x18000c1e2  movups  xmm0, xmmword ptr [rax-10h]
0x18000c1e6  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000c1ec  cmp     cs:RegHandle, 0
0x18000c1f4  jz      short loc_18000C1FD
0x18000c1f6  mov     ecx, 5
0x18000c1fb  int     29h; Win8: RtlFailFast(ecx)
0x18000c1fd  xorps   xmm0, xmm0
0x18000c200  movdqu  cs:xmmword_180015028, xmm0
0x18000c208  lea     r9, RegHandle; RegHandle
0x18000c20f  lea     r8, dword_180015000; CallbackContext
0x18000c216  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000c21d  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000c222  call    cs:__imp_EventRegister
0x18000c228  test    eax, eax
0x18000c22a  jnz     short loc_18000C247
0x18000c22c  mov     r8, cs:off_180015008
0x18000c233  movzx   r9d, word ptr [r8]
0x18000c237  lea     edx, [rax+2]
0x18000c23a  mov     rcx, cs:RegHandle
0x18000c241  call    cs:__imp_EventSetInformation
0x18000c247  mov     cs:byte_180015F68, 1
0x18000c24e  mov     [rdi], rbx
0x18000c251  xor     eax, eax
0x18000c253  mov     rcx, [rsp+48h+var_10]
0x18000c258  xor     rcx, rsp; StackCookie
0x18000c25b  call    __security_check_cookie
0x18000c260  mov     rbx, [rsp+48h+arg_8]
0x18000c265  add     rsp, 40h
0x18000c269  pop     rdi
0x18000c26a  retn
```
