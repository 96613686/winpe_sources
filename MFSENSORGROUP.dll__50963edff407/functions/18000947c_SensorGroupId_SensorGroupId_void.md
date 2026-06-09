# SensorGroupId::~SensorGroupId(void)

- ea: `0x18000947c`
- end: `0x18000957b`
- name: `??1SensorGroupId@@MEAA@XZ`
- size: `255`
- prototype: `void __fastcall(SensorGroupId *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009440`

## callees

- `0x180008fc0`
- `0x180008fe4`
- `0x18000947c`
- `0x180009584`
- `0x180009600`
- `0x180044b28`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000953b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000953b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094fa`

## pseudocode

```c
void __fastcall SensorGroupId::~SensorGroupId(SensorGroupId *this)
{
  void *v2; // rcx
  void *v3; // rcx
  SensorGroupProperty *v4; // rsi
  __int64 v5; // rdi
  HKEY v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)this = &SensorGroupId::`vftable'{for `IMFSensorGroupId'};
  *((_QWORD *)this + 1) = &SensorGroupId::`vftable'{for `IMFSensorGroupIdInternal'};
  CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll((char *)this + 120);
  v2 = (void *)*((_QWORD *)this + 28);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 28) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 29);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 29) = 0;
  }
  *((_DWORD *)this + 60) = 0;
  v4 = (SensorGroupId *)((char *)this + 1920);
  v5 = 26;
  do
  {
    v4 = (SensorGroupProperty *)((char *)v4 - 64);
    SensorGroupProperty::~SensorGroupProperty(v4);
    --v5;
  }
  while ( v5 );
  v6 = (HKEY)*((_QWORD *)this + 27);
  if ( v6 )
    RegCloseKey(v6);
  v7 = *((_QWORD *)this + 22);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *((_QWORD *)this + 18) = &AutoSecurityAttributes::`vftable';
  AutoSecurityAttributes::Reset((SensorGroupId *)((char *)this + 144));
  CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x18000947c  push    rbx
0x18000947e  push    rbp
0x18000947f  push    rsi
0x180009480  push    rdi
0x180009481  sub     rsp, 28h
0x180009485  lea     rax, ??_7SensorGroupId@@6BIMFSensorGroupId@@@; const SensorGroupId::`vftable'{for `IMFSensorGroupId'}
0x18000948c  mov     rbx, rcx
0x18000948f  mov     [rcx], rax
0x180009492  lea     rax, ??_7SensorGroupId@@6BIMFSensorGroupIdInternal@@@; const SensorGroupId::`vftable'{for `IMFSensorGroupIdInternal'}
0x180009499  mov     [rcx+8], rax
0x18000949d  add     rcx, 78h ; 'x'
0x1800094a1  call    ?RemoveAll@?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAAXXZ; CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll(void)
0x1800094a6  mov     rcx, [rbx+0E0h]; Block
0x1800094ad  test    rcx, rcx
0x1800094b0  jnz     loc_180009551
0x1800094b6  mov     rcx, [rbx+0E8h]; Block
0x1800094bd  test    rcx, rcx
0x1800094c0  jnz     loc_180009566
0x1800094c6  mov     dword ptr [rbx+0F0h], 0
0x1800094d0  lea     rsi, [rbx+780h]
0x1800094d7  mov     edi, 1Ah
0x1800094dc  sub     rsi, 40h ; '@'
0x1800094e0  mov     rcx, rsi; this
0x1800094e3  call    ??1SensorGroupProperty@@UEAA@XZ; SensorGroupProperty::~SensorGroupProperty(void)
0x1800094e8  sub     rdi, 1
0x1800094ec  jnz     short loc_1800094DC
0x1800094ee  mov     rcx, [rbx+0D8h]; hKey
0x1800094f5  test    rcx, rcx
0x1800094f8  jz      short loc_180009500
0x1800094fa  call    cs:__imp_RegCloseKey
0x180009500  mov     rcx, [rbx+0B0h]
0x180009507  test    rcx, rcx
0x18000950a  jz      short loc_180009518
0x18000950c  mov     rax, [rcx]
0x18000950f  mov     rax, [rax+10h]
0x180009513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009518  lea     rcx, [rbx+90h]; this
0x18000951f  lea     rax, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180009526  mov     [rcx], rax
0x180009529  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18000952e  lea     rcx, [rbx+78h]
0x180009532  call    ??1?$CTUnkArray@UIMFMediaType@@@@QEAA@XZ; CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>(void)
0x180009537  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000953b  call    cs:__imp_DeleteCriticalSection
0x180009541  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x180009548  add     rsp, 28h
0x18000954c  pop     rdi
0x18000954d  pop     rsi
0x18000954e  pop     rbp
0x18000954f  pop     rbx
0x180009550  retn
0x180009551  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009556  mov     qword ptr [rbx+0E0h], 0
0x180009561  jmp     loc_1800094B6
0x180009566  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000956b  mov     qword ptr [rbx+0E8h], 0
0x180009576  jmp     loc_1800094C6
```
