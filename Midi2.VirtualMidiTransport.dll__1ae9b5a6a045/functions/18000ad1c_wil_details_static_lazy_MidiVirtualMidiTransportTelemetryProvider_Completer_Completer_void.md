# wil::details::static_lazy<MidiVirtualMidiTransportTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18000ad1c`
- end: `0x18000adef`
- name: `??1Completer@?$static_lazy@VMidiVirtualMidiTransportTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b5f8`

## callees

- `0x1800038f0`
- `0x18000ad1c`
- `0x180021010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000adaa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000adaa`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000ad92`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000ad92`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000add2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000add2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MidiVirtualMidiTransportTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x18000ad1c  push    rbx
0x18000ad1e  push    rsi
0x18000ad1f  push    rdi
0x18000ad20  push    r14
0x18000ad22  sub     rsp, 48h
0x18000ad26  mov     rax, cs:__security_cookie
0x18000ad2d  xor     rax, rsp
0x18000ad30  mov     [rsp+68h+var_38], rax
0x18000ad35  cmp     dword ptr [rcx+8], 0
0x18000ad39  mov     rdi, rcx
0x18000ad3c  jnz     loc_18000ADC8
0x18000ad42  mov     rbx, [rcx]
0x18000ad45  mov     rsi, [rbx+20h]
0x18000ad49  mov     [rbx+10h], rsi
0x18000ad4d  mov     byte ptr [rbx+18h], 1
0x18000ad51  mov     rax, [rsi+8]
0x18000ad55  lea     r14, [rsi+20h]
0x18000ad59  cmp     qword ptr [r14], 0
0x18000ad5d  movups  xmm0, xmmword ptr [rax-10h]
0x18000ad61  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000ad67  jz      short loc_18000AD70
0x18000ad69  mov     ecx, 5
0x18000ad6e  int     29h; Win8: RtlFailFast(ecx)
0x18000ad70  mov     r9, r14; RegHandle
0x18000ad73  mov     qword ptr [rsi+28h], 0
0x18000ad7b  mov     r8, rsi; CallbackContext
0x18000ad7e  mov     qword ptr [rsi+30h], 0
0x18000ad86  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000ad8d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000ad92  call    cs:__imp_EventRegister
0x18000ad98  test    eax, eax
0x18000ad9a  jnz     short loc_18000ADB0
0x18000ad9c  mov     r8, [rsi+8]
0x18000ada0  lea     edx, [rax+2]
0x18000ada3  mov     rcx, [r14]
0x18000ada6  movzx   r9d, word ptr [r8]
0x18000adaa  call    cs:__imp_EventSetInformation
0x18000adb0  mov     rax, [rbx+8]
0x18000adb4  lea     rcx, [rbx+8]
0x18000adb8  mov     dword ptr [rbx+1Ch], 1
0x18000adbf  mov     rax, [rax+8]
0x18000adc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc8  mov     rcx, [rdi]; lpInitOnce
0x18000adcb  mov     edx, [rdi+8]; dwFlags
0x18000adce  lea     r8, [rcx+8]; lpContext
0x18000add2  call    cs:__imp_InitOnceComplete
0x18000add8  mov     rcx, [rsp+68h+var_38]
0x18000addd  xor     rcx, rsp; StackCookie
0x18000ade0  call    __security_check_cookie
0x18000ade5  add     rsp, 48h
0x18000ade9  pop     r14
0x18000adeb  pop     rdi
0x18000adec  pop     rsi
0x18000aded  pop     rbx
0x18000adee  retn
```
