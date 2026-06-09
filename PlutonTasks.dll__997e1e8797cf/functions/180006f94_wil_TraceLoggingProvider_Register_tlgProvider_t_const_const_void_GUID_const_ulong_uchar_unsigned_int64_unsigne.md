# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180006f94`
- end: `0x180006fc8`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `52`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037dc`

## callees

- `0x180001654`
- `0x18000a010`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  __int64 v4; // rax

  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 16) = 1;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(a2);
  v4 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v4 + 8))(this);
}

```

## disassembly

```asm
0x180006f94  push    rbx
0x180006f96  sub     rsp, 20h
0x180006f9a  mov     rbx, rcx
0x180006f9d  mov     [rcx+8], rdx
0x180006fa1  mov     byte ptr [rcx+10h], 1
0x180006fa5  mov     rcx, rdx; CallbackContext
0x180006fa8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006fad  mov     rax, [rbx]
0x180006fb0  mov     rcx, rbx
0x180006fb3  mov     dword ptr [rbx+14h], 1
0x180006fba  mov     rax, [rax+8]
0x180006fbe  add     rsp, 20h
0x180006fc2  pop     rbx
0x180006fc3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
