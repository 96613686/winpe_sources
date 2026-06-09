# Windows::Rtl::CriticalSectionLockGrant::Acquire(void)

- ea: `0x1400071c8`
- end: `0x1400071f3`
- name: `?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ`
- size: `43`
- prototype: `__int64 __fastcall(Windows::Rtl::CriticalSectionLockGrant *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400067bc`
- `0x140006984`
- `0x140006b48`
- `0x140006c50`
- `0x1400095ac`
- `0x1400096a4`
- `0x14000a714`
- `0x14000a8ac`
- `0x1400122e0`
- `0x140012400`
- `0x140016870`

## callees

- `0x1400071c8`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1400071db`
- `ntdll!RtlEnterCriticalSection` at `0x1400071db`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::CriticalSectionLockGrant::Acquire(PRTL_CRITICAL_SECTION *this)
{
  NTSTATUS v1; // edx

  v1 = 0;
  if ( !*((_BYTE *)this + 8) )
  {
    v1 = RtlEnterCriticalSection(*this);
    *((_BYTE *)this + 8) = v1 >= 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400071c8  push    rbx
0x1400071ca  sub     rsp, 20h
0x1400071ce  xor     edx, edx
0x1400071d0  mov     rbx, rcx
0x1400071d3  cmp     [rcx+8], dl
0x1400071d6  jnz     short loc_1400071EB
0x1400071d8  mov     rcx, [rcx]; CriticalSection
0x1400071db  call    cs:__imp_RtlEnterCriticalSection
0x1400071e1  mov     edx, eax
0x1400071e3  shr     eax, 1Fh
0x1400071e6  xor     al, 1
0x1400071e8  mov     [rbx+8], al
0x1400071eb  mov     eax, edx
0x1400071ed  add     rsp, 20h
0x1400071f1  pop     rbx
0x1400071f2  retn
```
