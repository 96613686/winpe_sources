# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180007d3c`
- end: `0x180007d70`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `52`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007434`

## callees

- `0x1800015d4`
- `0x18000c010`

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
0x180007d3c  push    rbx
0x180007d3e  sub     rsp, 20h
0x180007d42  mov     rbx, rcx
0x180007d45  mov     [rcx+8], rdx
0x180007d49  mov     byte ptr [rcx+10h], 1
0x180007d4d  mov     rcx, rdx; CallbackContext
0x180007d50  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180007d55  mov     rax, [rbx]
0x180007d58  mov     rcx, rbx
0x180007d5b  mov     dword ptr [rbx+14h], 1
0x180007d62  mov     rax, [rax+8]
0x180007d66  add     rsp, 20h
0x180007d6a  pop     rbx
0x180007d6b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
