# SensorActivities::~SensorActivities(void)

- ea: `0x18002927c`
- end: `0x1800292c7`
- name: `??1SensorActivities@@MEAA@XZ`
- size: `75`
- prototype: `void __fastcall(SensorActivities *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180029240`

## callees

- `0x180008bd0`
- `0x18002927c`
- `0x180044b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800292a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800292a5`

## pseudocode

```c
void __fastcall SensorActivities::~SensorActivities(SensorActivities *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &SensorActivities::`vftable';
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 11) = 0;
  }
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>((_DWORD *)this + 14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x18002927c  push    rbx
0x18002927e  sub     rsp, 20h
0x180029282  lea     rax, ??_7SensorActivities@@6B@; const SensorActivities::`vftable'
0x180029289  mov     rbx, rcx
0x18002928c  mov     [rcx], rax
0x18002928f  mov     rcx, [rcx+58h]; Block
0x180029293  test    rcx, rcx
0x180029296  jnz     short loc_1800292B8
0x180029298  lea     rcx, [rbx+38h]; void *
0x18002929c  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x1800292a1  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800292a5  call    cs:__imp_DeleteCriticalSection
0x1800292ab  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x1800292b2  add     rsp, 20h
0x1800292b6  pop     rbx
0x1800292b7  retn
0x1800292b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800292bd  mov     qword ptr [rbx+58h], 0
0x1800292c5  jmp     short loc_180029298
```
