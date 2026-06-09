# Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(void)

- ea: `0x140026cf8`
- end: `0x140026d5a`
- name: `??1CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140026d60`

## callees

- `0x140026cf8`
- `0x14002b010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x140026d3a`
- `ntdll!RtlDeleteCriticalSection` at `0x140026d3a`
- `ntdll!RtlRaiseStatus` at `0x140026d46`
- `ntdll!RtlRaiseStatus` at `0x140026d46`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this)
{
  bool v1; // zf
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  int v4; // eax

  v1 = *((_BYTE *)this + 16) == 0;
  *(_QWORD *)this = &Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable';
  if ( !v1 )
  {
    v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
    if ( v3 )
      (**v3)(v3, 1);
  }
  if ( *((_BYTE *)this + 2184) )
  {
    v4 = RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 2144));
    if ( v4 < 0 )
      RtlRaiseStatus(v4);
    *((_BYTE *)this + 2184) = 0;
  }
}

```

## disassembly

```asm
0x140026cf8  push    rbx
0x140026cfa  sub     rsp, 20h
0x140026cfe  cmp     byte ptr [rcx+10h], 0
0x140026d02  lea     rax, ??_7CBaseTracingStream@Rtl@Implementation@WCP@Windows@@6B@; const Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable'
0x140026d09  mov     [rcx], rax
0x140026d0c  mov     rbx, rcx
0x140026d0f  jz      short loc_140026D2A
0x140026d11  mov     rcx, [rcx+8]
0x140026d15  test    rcx, rcx
0x140026d18  jz      short loc_140026D2A
0x140026d1a  mov     rax, [rcx]
0x140026d1d  mov     edx, 1
0x140026d22  mov     rax, [rax]
0x140026d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026d2a  cmp     byte ptr [rbx+888h], 0
0x140026d31  jz      short loc_140026D54
0x140026d33  lea     rcx, [rbx+860h]; CriticalSection
0x140026d3a  call    cs:__imp_RtlDeleteCriticalSection
0x140026d40  test    eax, eax
0x140026d42  jns     short loc_140026D4D
0x140026d44  mov     ecx, eax; Status
0x140026d46  call    cs:__imp_RtlRaiseStatus
0x140026d4c  int     3; Trap to Debugger
0x140026d4d  mov     byte ptr [rbx+888h], 0
0x140026d54  add     rsp, 20h
0x140026d58  pop     rbx
0x140026d59  retn
```
