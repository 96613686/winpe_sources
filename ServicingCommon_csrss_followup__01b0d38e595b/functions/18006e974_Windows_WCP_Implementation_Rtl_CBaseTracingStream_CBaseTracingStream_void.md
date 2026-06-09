# Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(void)

- ea: `0x18006e974`
- end: `0x18006e9e3`
- name: `??1CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAA@XZ`
- size: `111`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006e9f0`

## callees

- `0x18006e974`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18006e9b6`
- `ntdll!RtlDeleteCriticalSection` at `0x18006e9b6`
- `ntdll!RtlRaiseStatus` at `0x18006e9c8`
- `ntdll!RtlRaiseStatus` at `0x18006e9c8`

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
0x18006e974  push    rbx
0x18006e976  sub     rsp, 20h
0x18006e97a  cmp     byte ptr [rcx+10h], 0
0x18006e97e  lea     rax, ??_7CBaseTracingStream@Rtl@Implementation@WCP@Windows@@6B@; const Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable'
0x18006e985  mov     [rcx], rax
0x18006e988  mov     rbx, rcx
0x18006e98b  jz      short loc_18006E9A6
0x18006e98d  mov     rcx, [rcx+8]
0x18006e991  test    rcx, rcx
0x18006e994  jz      short loc_18006E9A6
0x18006e996  mov     rax, [rcx]
0x18006e999  mov     edx, 1
0x18006e99e  mov     rax, [rax]
0x18006e9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e9a6  cmp     byte ptr [rbx+888h], 0
0x18006e9ad  jz      short loc_18006E9DC
0x18006e9af  lea     rcx, [rbx+860h]; CriticalSection
0x18006e9b6  call    cs:__imp_RtlDeleteCriticalSection
0x18006e9bd  nop     dword ptr [rax+rax+00h]
0x18006e9c2  test    eax, eax
0x18006e9c4  jns     short loc_18006E9D5
0x18006e9c6  mov     ecx, eax; Status
0x18006e9c8  call    cs:__imp_RtlRaiseStatus
0x18006e9cf  nop     dword ptr [rax+rax+00h]
0x18006e9d4  int     3; Trap to Debugger
0x18006e9d5  mov     byte ptr [rbx+888h], 0
0x18006e9dc  add     rsp, 20h
0x18006e9e0  pop     rbx
0x18006e9e1  retn
```
