# SpeechMicDiagnostic::CaptureStream::~CaptureStream(void)

- ea: `0x18000dc0c`
- end: `0x18000dd48`
- name: `??1CaptureStream@SpeechMicDiagnostic@@QEAA@XZ`
- size: `316`
- prototype: `void __fastcall(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800076cc`
- `0x180007714`
- `0x180007c88`

## callees

- `0x180002ce0`
- `0x18000d6b4`
- `0x18000dbb8`
- `0x18000dc0c`
- `0x18000f910`
- `0x18000fef4`
- `0x180011010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000dcd7`
- `KERNEL32!DeleteCriticalSection` at `0x18000dcd7`
- `ole32!CoTaskMemFree` at `0x18000dc3d`
- `ole32!CoTaskMemFree` at `0x18000dc3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SpeechMicDiagnostic::CaptureStream::~CaptureStream(SpeechMicDiagnostic::CaptureStream *this)
{
  unsigned __int64 v2; // rdx
  void *v3; // rcx
  void *v4; // rdi
  void *v5; // rdi
  volatile signed __int32 *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  SpeechMicDiagnostic::CaptureStream::Stop(this);
  CSpDynamicString::_free((SpeechMicDiagnostic::CaptureStream *)((char *)this + 144));
  CSpDynamicString::_free((SpeechMicDiagnostic::CaptureStream *)((char *)this + 136));
  CoTaskMemFree(*((LPVOID *)this + 15));
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 )
    operator delete(v3, v2);
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    SpeechMicDiagnostic::LevelMonitor::~LevelMonitor(*((SpeechMicDiagnostic::LevelMonitor **)this + 11));
    operator delete(v4, 0x60u);
  }
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    Microsoft::WRL::ComPtr<IMMDevice>::~ComPtr<IMMDevice>(*((_QWORD *)this + 10));
    operator delete(v5, 8u);
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 9);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = *((_QWORD *)this + 1);
  if ( v8 )
  {
    *((_QWORD *)this + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
}

```

## disassembly

```asm
0x18000dc0c  mov     [rsp+arg_0], rbx
0x18000dc11  push    rdi
0x18000dc12  sub     rsp, 20h
0x18000dc16  mov     rbx, rcx
0x18000dc19  call    ?Stop@CaptureStream@SpeechMicDiagnostic@@QEAAJXZ; SpeechMicDiagnostic::CaptureStream::Stop(void)
0x18000dc1e  nop
0x18000dc1f  lea     rcx, [rbx+90h]; this
0x18000dc26  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000dc2b  nop
0x18000dc2c  lea     rcx, [rbx+88h]; this
0x18000dc33  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000dc38  nop
0x18000dc39  mov     rcx, [rbx+78h]; pv
0x18000dc3d  call    cs:__imp_CoTaskMemFree
0x18000dc44  nop     dword ptr [rax+rax+00h]
0x18000dc49  mov     rcx, [rbx+60h]; void *
0x18000dc4d  test    rcx, rcx
0x18000dc50  jz      short loc_18000DC57
0x18000dc52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc57  mov     rdi, [rbx+58h]
0x18000dc5b  test    rdi, rdi
0x18000dc5e  jz      short loc_18000DC75
0x18000dc60  mov     rcx, rdi; this
0x18000dc63  call    ??1LevelMonitor@SpeechMicDiagnostic@@QEAA@XZ; SpeechMicDiagnostic::LevelMonitor::~LevelMonitor(void)
0x18000dc68  mov     edx, 60h ; '`'; unsigned __int64
0x18000dc6d  mov     rcx, rdi; void *
0x18000dc70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc75  mov     rdi, [rbx+50h]
0x18000dc79  test    rdi, rdi
0x18000dc7c  jz      short loc_18000DC93
0x18000dc7e  mov     rcx, rdi
0x18000dc81  call    ??1?$ComPtr@UIMMDevice@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IMMDevice>::~ComPtr<IMMDevice>(void)
0x18000dc86  mov     edx, 8; unsigned __int64
0x18000dc8b  mov     rcx, rdi; void *
0x18000dc8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc93  mov     rdi, [rbx+48h]
0x18000dc97  test    rdi, rdi
0x18000dc9a  jz      short loc_18000DCD3
0x18000dc9c  or      eax, 0FFFFFFFFh
0x18000dc9f  lock xadd [rdi+8], eax
0x18000dca4  cmp     eax, 1
0x18000dca7  jnz     short loc_18000DCD3
0x18000dca9  mov     rax, [rdi]
0x18000dcac  mov     rcx, rdi
0x18000dcaf  mov     rax, [rax]
0x18000dcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcb7  or      eax, 0FFFFFFFFh
0x18000dcba  lock xadd [rdi+0Ch], eax
0x18000dcbf  cmp     eax, 1
0x18000dcc2  jnz     short loc_18000DCD3
0x18000dcc4  mov     rax, [rdi]
0x18000dcc7  mov     rcx, rdi
0x18000dcca  mov     rax, [rax+8]
0x18000dcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd3  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000dcd7  call    cs:__imp_DeleteCriticalSection
0x18000dcde  nop     dword ptr [rax+rax+00h]
0x18000dce3  nop
0x18000dce4  mov     rcx, [rbx+10h]
0x18000dce8  test    rcx, rcx
0x18000dceb  jz      short loc_18000DD02
0x18000dced  mov     qword ptr [rbx+10h], 0
0x18000dcf5  mov     rax, [rcx]
0x18000dcf8  mov     rax, [rax+10h]
0x18000dcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd01  nop
0x18000dd02  mov     rcx, [rbx+8]
0x18000dd06  test    rcx, rcx
0x18000dd09  jz      short loc_18000DD20
0x18000dd0b  mov     qword ptr [rbx+8], 0
0x18000dd13  mov     rax, [rcx]
0x18000dd16  mov     rax, [rax+10h]
0x18000dd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd1f  nop
0x18000dd20  mov     rcx, [rbx]
0x18000dd23  test    rcx, rcx
0x18000dd26  jz      short loc_18000DD3C
0x18000dd28  mov     qword ptr [rbx], 0
0x18000dd2f  mov     rax, [rcx]
0x18000dd32  mov     rax, [rax+10h]
0x18000dd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd3b  nop
0x18000dd3c  mov     rbx, [rsp+28h+arg_0]
0x18000dd41  add     rsp, 20h
0x18000dd45  pop     rdi
0x18000dd46  retn
```
