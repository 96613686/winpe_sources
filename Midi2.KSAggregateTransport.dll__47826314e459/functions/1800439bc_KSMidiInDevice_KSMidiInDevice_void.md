# KSMidiInDevice::~KSMidiInDevice(void)

- ea: `0x1800439bc`
- end: `0x180043a6c`
- name: `??1KSMidiInDevice@@UEAA@XZ`
- size: `176`
- prototype: `void __fastcall(KSMidiInDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180043bc0`

## callees

- `0x18000c684`
- `0x1800439bc`
- `0x1800485ac`
- `0x18004a9c0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043a24`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800439e0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800439e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall KSMidiInDevice::~KSMidiInDevice(KSMidiInDevice *this)
{
  void *v2; // rcx
  char *v3; // rcx
  void *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  void *v7; // rcx
  unsigned int v8; // r8d
  const char *v9; // r9
  __int64 v10; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &KSMidiInDevice::`vftable';
  KSMidiInDevice::Shutdown(this);
  v2 = (void *)*((_QWORD *)this + 20);
  if ( v2 )
    AvRevertMmThreadCharacteristics(v2);
  v3 = (char *)*((_QWORD *)this + 18);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 && !CloseHandle(v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  v7 = (void *)*((_QWORD *)this + 16);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
  v10 = *((_QWORD *)this + 14);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  KSMidiDevice::~KSMidiDevice((KsHandleWrapper **)this);
}

```

## disassembly

```asm
0x1800439bc  push    rbx
0x1800439be  sub     rsp, 20h
0x1800439c2  mov     rbx, rcx
0x1800439c5  lea     rax, ??_7KSMidiInDevice@@6B@; const KSMidiInDevice::`vftable'
0x1800439cc  mov     [rcx], rax
0x1800439cf  call    ?Shutdown@KSMidiInDevice@@UEAAJXZ; KSMidiInDevice::Shutdown(void)
0x1800439d4  mov     rcx, [rbx+0A0h]; AvrtHandle
0x1800439db  test    rcx, rcx
0x1800439de  jz      short loc_1800439E6
0x1800439e0  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800439e6  mov     rcx, [rbx+90h]; hObject
0x1800439ed  lea     rax, [rcx-1]
0x1800439f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800439f5  ja      short loc_1800439FD
0x1800439f7  call    cs:__imp_CloseHandle
0x1800439fd  mov     rcx, [rbx+88h]; hObject
0x180043a04  test    rcx, rcx
0x180043a07  jz      short loc_180043A18
0x180043a09  call    cs:__imp_CloseHandle
0x180043a0f  mov     rcx, [rsp+28h]; this
0x180043a14  test    eax, eax
0x180043a16  jz      short loc_180043A61
0x180043a18  mov     rcx, [rbx+80h]; hObject
0x180043a1f  test    rcx, rcx
0x180043a22  jz      short loc_180043A33
0x180043a24  call    cs:__imp_CloseHandle
0x180043a2a  mov     rcx, [rsp+28h]; this
0x180043a2f  test    eax, eax
0x180043a31  jz      short loc_180043A56
0x180043a33  mov     rcx, [rbx+70h]
0x180043a37  test    rcx, rcx
0x180043a3a  jz      short loc_180043A49
0x180043a3c  mov     rax, [rcx]
0x180043a3f  mov     rax, [rax+10h]
0x180043a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a48  nop
0x180043a49  mov     rcx, rbx; this
0x180043a4c  add     rsp, 20h
0x180043a50  pop     rbx
0x180043a51  jmp     ??1KSMidiDevice@@UEAA@XZ; KSMidiDevice::~KSMidiDevice(void)
0x180043a56  mov     edx, 0A0Bh; void *
0x180043a5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180043a61  mov     edx, 0A0Bh; void *
0x180043a66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
