# KSMidiInDevice::~KSMidiInDevice(void)

- ea: `0x180010e78`
- end: `0x180010f28`
- name: `??1KSMidiInDevice@@UEAA@XZ`
- size: `176`
- prototype: `void __fastcall(KSMidiInDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011560`

## callees

- `0x18000bb04`
- `0x180010e78`
- `0x180027a48`
- `0x18002a020`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ee0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ee0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180010e9c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180010e9c`

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
0x180010e78  push    rbx
0x180010e7a  sub     rsp, 20h
0x180010e7e  mov     rbx, rcx
0x180010e81  lea     rax, ??_7KSMidiInDevice@@6B@; const KSMidiInDevice::`vftable'
0x180010e88  mov     [rcx], rax
0x180010e8b  call    ?Shutdown@KSMidiInDevice@@UEAAJXZ; KSMidiInDevice::Shutdown(void)
0x180010e90  mov     rcx, [rbx+0A0h]; AvrtHandle
0x180010e97  test    rcx, rcx
0x180010e9a  jz      short loc_180010EA2
0x180010e9c  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180010ea2  mov     rcx, [rbx+90h]; hObject
0x180010ea9  lea     rax, [rcx-1]
0x180010ead  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010eb1  ja      short loc_180010EB9
0x180010eb3  call    cs:__imp_CloseHandle
0x180010eb9  mov     rcx, [rbx+88h]; hObject
0x180010ec0  test    rcx, rcx
0x180010ec3  jz      short loc_180010ED4
0x180010ec5  call    cs:__imp_CloseHandle
0x180010ecb  mov     rcx, [rsp+28h]; this
0x180010ed0  test    eax, eax
0x180010ed2  jz      short loc_180010F1D
0x180010ed4  mov     rcx, [rbx+80h]; hObject
0x180010edb  test    rcx, rcx
0x180010ede  jz      short loc_180010EEF
0x180010ee0  call    cs:__imp_CloseHandle
0x180010ee6  mov     rcx, [rsp+28h]; this
0x180010eeb  test    eax, eax
0x180010eed  jz      short loc_180010F12
0x180010eef  mov     rcx, [rbx+70h]
0x180010ef3  test    rcx, rcx
0x180010ef6  jz      short loc_180010F05
0x180010ef8  mov     rax, [rcx]
0x180010efb  mov     rax, [rax+10h]
0x180010eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f04  nop
0x180010f05  mov     rcx, rbx; this
0x180010f08  add     rsp, 20h
0x180010f0c  pop     rbx
0x180010f0d  jmp     ??1KSMidiDevice@@UEAA@XZ; KSMidiDevice::~KSMidiDevice(void)
0x180010f12  mov     edx, 0A0Bh; void *
0x180010f17  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010f1d  mov     edx, 0A0Bh; void *
0x180010f22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
