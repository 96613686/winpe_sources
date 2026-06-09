# CreateBufferWriterEvent

- ea: `0x180013a58`
- end: `0x180013b51`
- name: `CreateBufferWriterEvent`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012acc`

## callees

- `0x180001460`
- `0x180013a58`
- `0x180017f44`
- `0x1800184fc`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013afd`
- `KERNEL32!GetLastError` at `0x180013afd`
- `KERNEL32!OpenEventW` at `0x180013b14`
- `KERNEL32!OpenEventW` at `0x180013b14`
- `KERNEL32!CreateEventW` at `0x180013aef`
- `KERNEL32!CreateEventW` at `0x180013aef`

## pseudocode

```c
HANDLE CreateBufferWriterEvent()
{
  HANDLE EventW; // rbx
  _QWORD v2[5]; // [rsp+20h] [rbp-19h] BYREF
  LPSECURITY_ATTRIBUTES lpEventAttributes; // [rsp+48h] [rbp+Fh]
  __int64 v4; // [rsp+50h] [rbp+17h]
  char v5; // [rsp+58h] [rbp+1Fh]
  __int128 v6; // [rsp+60h] [rbp+27h]
  int v7; // [rsp+70h] [rbp+37h]
  int v8; // [rsp+74h] [rbp+3Bh]
  int v9; // [rsp+78h] [rbp+3Fh]
  int v10; // [rsp+7Ch] [rbp+43h]

  v2[1] = 0;
  v6 = 0;
  v2[0] = &Mp2DemuxSec::CWriteEventSec::`vftable';
  lpEventAttributes = 0;
  v4 = 0;
  v5 = 0;
  v7 = 11;
  v8 = 18;
  v9 = 19;
  v10 = 20;
  Mp2DemuxSec::CDemuxSec::CreateSids((Mp2DemuxSec::CDemuxSec *)v2);
  (*(void (__fastcall **)(_QWORD *))(v2[0] + 32LL))(v2);
  EventW = CreateEventW(lpEventAttributes, 1, 0, L"Global\\DmCapToggle");
  if ( !EventW && GetLastError() == 5 )
    EventW = OpenEventW(2u, 0, L"Global\\DmCapToggle");
  v2[0] = &Mp2DemuxSec::CDemuxDiagnosticsSec::`vftable';
  Mp2DemuxSec::CDemuxSec::~CDemuxSec((Mp2DemuxSec::CDemuxSec *)v2);
  return EventW;
}

```

## disassembly

```asm
0x180013a58  mov     [rsp-8+arg_0], rbx
0x180013a5d  push    rbp
0x180013a5e  lea     rbp, [rsp-57h]
0x180013a63  sub     rsp, 90h
0x180013a6a  mov     rax, cs:__security_cookie
0x180013a71  xor     rax, rsp
0x180013a74  mov     [rbp+57h+var_10], rax
0x180013a78  xorps   xmm0, xmm0
0x180013a7b  mov     [rbp+57h+var_68], 0
0x180013a83  lea     rax, ??_7CWriteEventSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CWriteEventSec::`vftable'
0x180013a8a  movdqa  [rbp+57h+var_30], xmm0
0x180013a8f  lea     rcx, [rbp+57h+var_70]; this
0x180013a93  mov     [rbp+57h+var_70], rax
0x180013a97  mov     [rbp+57h+lpEventAttributes], 0
0x180013a9f  mov     [rbp+57h+var_40], 0
0x180013aa7  mov     [rbp+57h+var_38], 0
0x180013aab  mov     [rbp+57h+var_20], 0Bh
0x180013ab2  mov     [rbp+57h+var_1C], 12h
0x180013ab9  mov     [rbp+57h+var_18], 13h
0x180013ac0  mov     [rbp+57h+var_14], 14h
0x180013ac7  call    ?CreateSids@CDemuxSec@Mp2DemuxSec@@AEAAJXZ; Mp2DemuxSec::CDemuxSec::CreateSids(void)
0x180013acc  mov     rax, [rbp+57h+var_70]
0x180013ad0  lea     rcx, [rbp+57h+var_70]
0x180013ad4  mov     rax, [rax+20h]
0x180013ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013add  mov     rcx, [rbp+57h+lpEventAttributes]; lpEventAttributes
0x180013ae1  lea     r9, Name; "Global\\DmCapToggle"
0x180013ae8  xor     r8d, r8d; bInitialState
0x180013aeb  lea     edx, [r8+1]; bManualReset
0x180013aef  call    cs:__imp_CreateEventW
0x180013af5  mov     rbx, rax
0x180013af8  test    rax, rax
0x180013afb  jnz     short loc_180013B1D
0x180013afd  call    cs:__imp_GetLastError
0x180013b03  cmp     eax, 5
0x180013b06  jnz     short loc_180013B1D
0x180013b08  lea     r8, Name; "Global\\DmCapToggle"
0x180013b0f  xor     edx, edx; bInheritHandle
0x180013b11  lea     ecx, [rbx+2]; dwDesiredAccess
0x180013b14  call    cs:__imp_OpenEventW
0x180013b1a  mov     rbx, rax
0x180013b1d  lea     rax, ??_7CDemuxDiagnosticsSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CDemuxDiagnosticsSec::`vftable'
0x180013b24  lea     rcx, [rbp+57h+var_70]; this
0x180013b28  mov     [rbp+57h+var_70], rax
0x180013b2c  call    ??1CDemuxSec@Mp2DemuxSec@@UEAA@XZ; Mp2DemuxSec::CDemuxSec::~CDemuxSec(void)
0x180013b31  mov     rax, rbx
0x180013b34  mov     rcx, [rbp+57h+var_10]
0x180013b38  xor     rcx, rsp; StackCookie
0x180013b3b  call    __security_check_cookie
0x180013b40  mov     rbx, [rsp+90h+arg_0]
0x180013b48  add     rsp, 90h
0x180013b4f  pop     rbp
0x180013b50  retn
```
