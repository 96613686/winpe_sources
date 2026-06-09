# Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)

- ea: `0x1400070ec`
- end: `0x14000711f`
- name: `??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(Windows::Rtl::CriticalSectionLockGrant *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400067bc`
- `0x140006984`
- `0x140006b48`
- `0x140006c50`
- `0x140007034`
- `0x1400095ac`
- `0x1400096a4`
- `0x14000a714`
- `0x14000a8ac`
- `0x1400122e0`
- `0x140012400`
- `0x140016870`

## callees

- `0x1400070ec`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x140007112`
- `ntdll!RtlRaiseStatus` at `0x140007112`
- `ntdll!RtlLeaveCriticalSection` at `0x1400070fe`
- `ntdll!RtlLeaveCriticalSection` at `0x1400070fe`

## pseudocode

```c
void __fastcall Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(PRTL_CRITICAL_SECTION *this)
{
  int v2; // eax

  if ( *((_BYTE *)this + 8) )
  {
    v2 = RtlLeaveCriticalSection(*this);
    *((_BYTE *)this + 8) = v2 < 0;
    if ( v2 < 0 )
      RtlRaiseStatus(v2);
  }
}

```

## disassembly

```asm
0x1400070ec  push    rbx
0x1400070ee  sub     rsp, 20h
0x1400070f2  cmp     byte ptr [rcx+8], 0
0x1400070f6  mov     rbx, rcx
0x1400070f9  jz      short loc_140007119
0x1400070fb  mov     rcx, [rcx]; CriticalSection
0x1400070fe  call    cs:__imp_RtlLeaveCriticalSection
0x140007104  mov     edx, eax
0x140007106  shr     edx, 1Fh
0x140007109  mov     [rbx+8], dl
0x14000710c  test    eax, eax
0x14000710e  jns     short loc_140007119
0x140007110  mov     ecx, eax; Status
0x140007112  call    cs:__imp_RtlRaiseStatus
0x140007118  int     3; Trap to Debugger
0x140007119  add     rsp, 20h
0x14000711d  pop     rbx
0x14000711e  retn
```
