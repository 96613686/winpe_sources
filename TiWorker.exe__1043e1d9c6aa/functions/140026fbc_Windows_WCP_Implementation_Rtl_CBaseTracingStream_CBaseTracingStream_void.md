# Windows::WCP::Implementation::Rtl::CBaseTracingStream::~CBaseTracingStream(void)

- ea: `0x140026fbc`
- end: `0x14002701e`
- name: `??1CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140027030`

## callees

- `0x140026fbc`
- `0x14002b010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x14002700a`
- `ntdll!RtlRaiseStatus` at `0x14002700a`
- `ntdll!RtlDeleteCriticalSection` at `0x140026ffe`
- `ntdll!RtlDeleteCriticalSection` at `0x140026ffe`

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
0x140026fbc  push    rbx
0x140026fbe  sub     rsp, 20h
0x140026fc2  cmp     byte ptr [rcx+10h], 0
0x140026fc6  lea     rax, ??_7CBaseTracingStream@Rtl@Implementation@WCP@Windows@@6B@; const Windows::WCP::Implementation::Rtl::CBaseTracingStream::`vftable'
0x140026fcd  mov     [rcx], rax
0x140026fd0  mov     rbx, rcx
0x140026fd3  jz      short loc_140026FEE
0x140026fd5  mov     rcx, [rcx+8]
0x140026fd9  test    rcx, rcx
0x140026fdc  jz      short loc_140026FEE
0x140026fde  mov     rax, [rcx]
0x140026fe1  mov     edx, 1
0x140026fe6  mov     rax, [rax]
0x140026fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fee  cmp     byte ptr [rbx+888h], 0
0x140026ff5  jz      short loc_140027018
0x140026ff7  lea     rcx, [rbx+860h]; CriticalSection
0x140026ffe  call    cs:__imp_RtlDeleteCriticalSection
0x140027004  test    eax, eax
0x140027006  jns     short loc_140027011
0x140027008  mov     ecx, eax; Status
0x14002700a  call    cs:__imp_RtlRaiseStatus
0x140027010  int     3; Trap to Debugger
0x140027011  mov     byte ptr [rbx+888h], 0
0x140027018  add     rsp, 20h
0x14002701c  pop     rbx
0x14002701d  retn
```
