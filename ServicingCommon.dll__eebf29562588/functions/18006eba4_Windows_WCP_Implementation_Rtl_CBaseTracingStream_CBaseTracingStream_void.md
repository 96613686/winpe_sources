# Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(void)

- ea: `0x18006eba4`
- end: `0x18006ec13`
- name: `??1CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAA@XZ`
- size: `111`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006ec20`

## callees

- `0x18006eba4`
- `0x1800a0020`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18006ebe6`
- `ntdll!RtlDeleteCriticalSection` at `0x18006ebe6`
- `ntdll!RtlRaiseStatus` at `0x18006ebf8`
- `ntdll!RtlRaiseStatus` at `0x18006ebf8`

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
0x18006eba4  push    rbx
0x18006eba6  sub     rsp, 20h
0x18006ebaa  cmp     byte ptr [rcx+10h], 0
0x18006ebae  lea     rax, ??_7CBaseTracingStream@Rtl@Implementation@WCP@Windows@@6B@; const Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable'
0x18006ebb5  mov     [rcx], rax
0x18006ebb8  mov     rbx, rcx
0x18006ebbb  jz      short loc_18006EBD6
0x18006ebbd  mov     rcx, [rcx+8]
0x18006ebc1  test    rcx, rcx
0x18006ebc4  jz      short loc_18006EBD6
0x18006ebc6  mov     rax, [rcx]
0x18006ebc9  mov     edx, 1
0x18006ebce  mov     rax, [rax]
0x18006ebd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ebd6  cmp     byte ptr [rbx+888h], 0
0x18006ebdd  jz      short loc_18006EC0C
0x18006ebdf  lea     rcx, [rbx+860h]; CriticalSection
0x18006ebe6  call    cs:__imp_RtlDeleteCriticalSection
0x18006ebed  nop     dword ptr [rax+rax+00h]
0x18006ebf2  test    eax, eax
0x18006ebf4  jns     short loc_18006EC05
0x18006ebf6  mov     ecx, eax; Status
0x18006ebf8  call    cs:__imp_RtlRaiseStatus
0x18006ebff  nop     dword ptr [rax+rax+00h]
0x18006ec04  int     3; Trap to Debugger
0x18006ec05  mov     byte ptr [rbx+888h], 0
0x18006ec0c  add     rsp, 20h
0x18006ec10  pop     rbx
0x18006ec11  retn
```
