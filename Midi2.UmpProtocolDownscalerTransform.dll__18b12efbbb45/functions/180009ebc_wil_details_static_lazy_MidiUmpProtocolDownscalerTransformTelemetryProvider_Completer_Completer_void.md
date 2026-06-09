# wil::details::static_lazy<MidiUmpProtocolDownscalerTransformTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180009ebc`
- end: `0x180009f8f`
- name: `??1Completer@?$static_lazy@VMidiUmpProtocolDownscalerTransformTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a798`

## callees

- `0x180002e70`
- `0x180009ebc`
- `0x180013010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009f4a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180009f4a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009f32`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180009f32`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009f72`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009f72`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiUmpProtocolDownscalerTransformTelemetryProvider>::Completer::~Completer(
        _DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(ULONGLONG **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    ProviderId = *(GUID *)(v3[1] - 16);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v3, v3 + 4) )
      EventSetInformation(
        v3[4],
        2,
        v3[1],
        *(unsigned __int16 *)v3[1],
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180009ebc  push    rbx
0x180009ebe  push    rsi
0x180009ebf  push    rdi
0x180009ec0  push    r14
0x180009ec2  sub     rsp, 48h
0x180009ec6  mov     rax, cs:__security_cookie
0x180009ecd  xor     rax, rsp
0x180009ed0  mov     [rsp+68h+var_38], rax
0x180009ed5  cmp     dword ptr [rcx+8], 0
0x180009ed9  mov     rdi, rcx
0x180009edc  jnz     loc_180009F68
0x180009ee2  mov     rbx, [rcx]
0x180009ee5  mov     rsi, [rbx+20h]
0x180009ee9  mov     [rbx+10h], rsi
0x180009eed  mov     byte ptr [rbx+18h], 1
0x180009ef1  mov     rax, [rsi+8]
0x180009ef5  lea     r14, [rsi+20h]
0x180009ef9  cmp     qword ptr [r14], 0
0x180009efd  movups  xmm0, xmmword ptr [rax-10h]
0x180009f01  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180009f07  jz      short loc_180009F10
0x180009f09  mov     ecx, 5
0x180009f0e  int     29h; Win8: RtlFailFast(ecx)
0x180009f10  mov     r9, r14; RegHandle
0x180009f13  mov     qword ptr [rsi+28h], 0
0x180009f1b  mov     r8, rsi; CallbackContext
0x180009f1e  mov     qword ptr [rsi+30h], 0
0x180009f26  lea     rdx, _tlgEnableCallback; EnableCallback
0x180009f2d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x180009f32  call    cs:__imp_EventRegister
0x180009f38  test    eax, eax
0x180009f3a  jnz     short loc_180009F50
0x180009f3c  mov     r8, [rsi+8]
0x180009f40  lea     edx, [rax+2]
0x180009f43  mov     rcx, [r14]
0x180009f46  movzx   r9d, word ptr [r8]
0x180009f4a  call    cs:__imp_EventSetInformation
0x180009f50  mov     rax, [rbx+8]
0x180009f54  lea     rcx, [rbx+8]
0x180009f58  mov     dword ptr [rbx+1Ch], 1
0x180009f5f  mov     rax, [rax+8]
0x180009f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f68  mov     rcx, [rdi]; lpInitOnce
0x180009f6b  mov     edx, [rdi+8]; dwFlags
0x180009f6e  lea     r8, [rcx+8]; lpContext
0x180009f72  call    cs:__imp_InitOnceComplete
0x180009f78  mov     rcx, [rsp+68h+var_38]
0x180009f7d  xor     rcx, rsp; StackCookie
0x180009f80  call    __security_check_cookie
0x180009f85  add     rsp, 48h
0x180009f89  pop     r14
0x180009f8b  pop     rdi
0x180009f8c  pop     rsi
0x180009f8d  pop     rbx
0x180009f8e  retn
```
