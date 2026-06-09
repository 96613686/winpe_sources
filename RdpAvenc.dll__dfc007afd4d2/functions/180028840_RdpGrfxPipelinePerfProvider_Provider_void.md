# RdpGrfxPipelinePerfProvider::Provider(void)

- ea: `0x180028840`
- end: `0x180028929`
- name: `?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800287b0`
- `0x1800293c8`
- `0x180029df8`
- `0x18002bc04`
- `0x18002cb80`
- `0x18002e2f4`
- `0x180065b60`
- `0x1800660a4`
- `0x180066960`
- `0x180067508`
- `0x180067c50`
- `0x18008508a`
- `0x180088b8d`

## callees

- `0x180001418`
- `0x180006974`
- `0x180028840`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028868`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028868`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028914`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028914`

## pseudocode

```c
const struct _tlgProvider_t *RdpGrfxPipelinePerfProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`RdpGrfxPipelinePerfProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800C26F0 = 0;
    v2 = &qword_1800C26E8;
    qword_1800C26E8 = (__int64)&RdpGrfxPipelinePerfProvider::`vftable';
    byte_1800C26F8 = 0;
    dword_1800C26FC = 0;
    CallbackContext = &`RdpGrfxPipelinePerfProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`RdpGrfxPipelinePerfProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    qword_1800C26F0 = (__int64)CallbackContext;
    byte_1800C26F8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800C26FC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800C26E8 + 8))(&qword_1800C26E8);
    InitOnceComplete(&`RdpGrfxPipelinePerfProvider::Instance'::`2'::wrapper, 0, &qword_1800C26E8);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x180028840  mov     rax, rsp
0x180028843  push    rbx
0x180028844  sub     rsp, 20h
0x180028848  lea     r9, [rax+10h]; lpContext
0x18002884c  mov     qword ptr [rax+10h], 0
0x180028854  lea     r8, [rax+8]; fPending
0x180028858  mov     dword ptr [rax+8], 0
0x18002885f  xor     edx, edx; dwFlags
0x180028861  lea     rcx, ?wrapper@?1??Instance@RdpGrfxPipelinePerfProvider@@KAPEAV2@XZ@4V?$static_lazy@VRdpGrfxPipelinePerfProvider@@@details@wil@@A; lpInitOnce
0x180028868  call    cs:__imp_InitOnceBeginInitialize
0x18002886e  test    eax, eax
0x180028870  jz      loc_18002891A
0x180028876  cmp     [rsp+28h+arg_0], 0
0x18002887b  jz      loc_18002891A
0x180028881  lea     rbx, qword_1800C26E8
0x180028888  mov     cs:qword_1800C26F0, 0
0x180028893  lea     rax, ??_7RdpGrfxPipelinePerfProvider@@6B@; const RdpGrfxPipelinePerfProvider::`vftable'
0x18002889a  mov     [rsp+28h+arg_8], rbx
0x18002889f  mov     cs:qword_1800C26E8, rax
0x1800288a6  mov     cs:byte_1800C26F8, 0
0x1800288ad  mov     cs:dword_1800C26FC, 0
0x1800288b7  lea     rax, ?__hInner@?1???0StaticHandle@RdpGrfxPipelinePerfProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `RdpGrfxPipelinePerfProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800288be  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@RdpGrfxPipelinePerfProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x1800288c5  mov     cs:CallbackContext, rax
0x1800288cc  call    atexit
0x1800288d1  mov     rcx, cs:CallbackContext; CallbackContext
0x1800288d8  mov     cs:qword_1800C26F0, rcx
0x1800288df  mov     cs:byte_1800C26F8, 1
0x1800288e6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800288eb  mov     rax, cs:qword_1800C26E8
0x1800288f2  mov     rcx, rbx
0x1800288f5  mov     cs:dword_1800C26FC, 1
0x1800288ff  mov     rax, [rax+8]
0x180028903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028908  mov     r8, rbx; lpContext
0x18002890b  lea     rcx, ?wrapper@?1??Instance@RdpGrfxPipelinePerfProvider@@KAPEAV2@XZ@4V?$static_lazy@VRdpGrfxPipelinePerfProvider@@@details@wil@@A; lpInitOnce
0x180028912  xor     edx, edx; dwFlags
0x180028914  call    cs:__imp_InitOnceComplete
0x18002891a  mov     rax, [rsp+28h+arg_8]
0x18002891f  mov     rax, [rax+8]
0x180028923  add     rsp, 20h
0x180028927  pop     rbx
0x180028928  retn
```
