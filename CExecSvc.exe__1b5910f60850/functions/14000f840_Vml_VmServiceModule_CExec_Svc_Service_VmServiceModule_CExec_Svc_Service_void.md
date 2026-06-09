# Vml::VmServiceModule<CExec::Svc::Service>::~VmServiceModule<CExec::Svc::Service>(void)

- ea: `0x14000f840`
- end: `0x14000f883`
- name: `??1?$VmServiceModule@VService@Svc@CExec@@@Vml@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000fe00`
- `0x1400233b0`

## callees

- `0x140008160`
- `0x14000f840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f87c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f855`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000f855`

## pseudocode

```c
void __fastcall Vml::VmServiceModule<CExec::Svc::Service>::~VmServiceModule<CExec::Svc::Service>(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 160);
  if ( v2 )
    LocalFree(v2);
  std::wstring::~wstring((char **)(a1 + 208));
  std::wstring::~wstring((char **)(a1 + 176));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
}

```

## disassembly

```asm
0x14000f840  push    rbx
0x14000f842  sub     rsp, 20h
0x14000f846  mov     rbx, rcx
0x14000f849  mov     rcx, [rcx+0A0h]; hMem
0x14000f850  test    rcx, rcx
0x14000f853  jz      short loc_14000F85B
0x14000f855  call    cs:__imp_LocalFree
0x14000f85b  lea     rcx, [rbx+0D0h]
0x14000f862  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f867  lea     rcx, [rbx+0B0h]
0x14000f86e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f873  lea     rcx, [rbx+28h]
0x14000f877  add     rsp, 20h
0x14000f87b  pop     rbx
0x14000f87c  jmp     cs:__imp_DeleteCriticalSection
```
