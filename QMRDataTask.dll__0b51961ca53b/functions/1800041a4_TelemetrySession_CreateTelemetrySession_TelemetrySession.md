# TelemetrySession::CreateTelemetrySession(TelemetrySession * *)

- ea: `0x1800041a4`
- end: `0x1800042db`
- name: `?CreateTelemetrySession@TelemetrySession@@SAJPEAPEAV1@@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct TelemetrySession **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003140`

## callees

- `0x180001404`
- `0x180003f20`
- `0x1800041a4`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180004292`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180004292`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800042b1`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800042b1`

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

  if ( byte_180023D20 )
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
  if ( !byte_180023D20 )
  {
    ProviderId = *(GUID *)&(*off_180023008)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_180023028 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180023000, &RegHandle) )
      EventSetInformation(
        RegHandle,
        2,
        (char *)off_180023008,
        *(unsigned __int16 *)off_180023008,
        v7,
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    byte_180023D20 = 1;
  }
  *a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x1800041a4  mov     [rsp+arg_8], rbx
0x1800041a9  push    rdi
0x1800041aa  sub     rsp, 40h
0x1800041ae  mov     rax, cs:__security_cookie
0x1800041b5  xor     rax, rsp
0x1800041b8  mov     [rsp+48h+var_10], rax
0x1800041bd  mov     rdi, rcx
0x1800041c0  cmp     cs:byte_180023D20, 0
0x1800041c7  jz      short loc_1800041D3
0x1800041c9  mov     eax, 800700B7h
0x1800041ce  jmp     loc_1800042C3
0x1800041d3  mov     ecx, 10h; Size
0x1800041d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041dd  mov     rbx, rax
0x1800041e0  mov     [rsp+48h+var_28], rax
0x1800041e5  test    rax, rax
0x1800041e8  jz      short loc_180004231
0x1800041ea  mov     qword ptr [rax+8], 0
0x1800041f2  lea     rax, ??_7?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@6B@; const RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vftable'
0x1800041f9  mov     [rbx], rax
0x1800041fc  mov     ecx, 90h; Size
0x180004201  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004206  mov     qword ptr [rsp+48h+ProviderId.Data1], rax
0x18000420b  test    rax, rax
0x18000420e  jz      short loc_18000421D
0x180004210  mov     rcx, rax; this
0x180004213  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180004218  mov     rdx, rax
0x18000421b  jmp     short loc_18000421F
0x18000421d  xor     edx, edx
0x18000421f  mov     rax, [rbx]
0x180004222  mov     rcx, rbx
0x180004225  mov     rax, [rax+30h]
0x180004229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422e  nop
0x18000422f  jmp     short loc_180004233
0x180004231  xor     ebx, ebx
0x180004233  test    rbx, rbx
0x180004236  jnz     short loc_180004242
0x180004238  mov     eax, 8007000Eh
0x18000423d  jmp     loc_1800042C3
0x180004242  cmp     cs:byte_180023D20, 0
0x180004249  jnz     short loc_1800042BE
0x18000424b  mov     rax, cs:off_180023008
0x180004252  movups  xmm0, xmmword ptr [rax-10h]
0x180004256  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000425c  cmp     cs:RegHandle, 0
0x180004264  jz      short loc_18000426D
0x180004266  mov     ecx, 5
0x18000426b  int     29h; Win8: RtlFailFast(ecx)
0x18000426d  xorps   xmm0, xmm0
0x180004270  movdqu  cs:xmmword_180023028, xmm0
0x180004278  lea     r9, RegHandle; RegHandle
0x18000427f  lea     r8, dword_180023000; CallbackContext
0x180004286  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000428d  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180004292  call    cs:__imp_EventRegister
0x180004298  test    eax, eax
0x18000429a  jnz     short loc_1800042B7
0x18000429c  mov     r8, cs:off_180023008
0x1800042a3  movzx   r9d, word ptr [r8]
0x1800042a7  lea     edx, [rax+2]
0x1800042aa  mov     rcx, cs:RegHandle
0x1800042b1  call    cs:__imp_EventSetInformation
0x1800042b7  mov     cs:byte_180023D20, 1
0x1800042be  mov     [rdi], rbx
0x1800042c1  xor     eax, eax
0x1800042c3  mov     rcx, [rsp+48h+var_10]
0x1800042c8  xor     rcx, rsp; StackCookie
0x1800042cb  call    __security_check_cookie
0x1800042d0  mov     rbx, [rsp+48h+arg_8]
0x1800042d5  add     rsp, 40h
0x1800042d9  pop     rdi
0x1800042da  retn
```
