# SensorProfile::~SensorProfile(void)

- ea: `0x1800092bc`
- end: `0x18000933c`
- name: `??1SensorProfile@@MEAA@XZ`
- size: `128`
- prototype: `void __fastcall(SensorProfile *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009280`

## callees

- `0x180008f9c`
- `0x1800092bc`
- `0x180009344`
- `0x1800093b0`
- `0x18000aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009305`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009305`

## pseudocode

```c
void __fastcall SensorProfile::~SensorProfile(SensorProfile *this)
{
  *(_QWORD *)this = &SensorProfile::`vftable'{for `IMFSensorProfileInternal'};
  *((_QWORD *)this + 1) = &SensorProfile::`vftable'{for `IMFAttributes'};
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, &WPP_31927b3ff17c3be32b5b8560ff5597aa_Traceguids, this);
  CTUnkArray<IMFSensorProfileBlockedControl>::~CTUnkArray<IMFSensorProfileBlockedControl>((char *)this + 128);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 15);
  CTUnkArray<IMFSensorProfilePin>::~CTUnkArray<IMFSensorProfilePin>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x1800092bc  push    rbx
0x1800092be  sub     rsp, 20h
0x1800092c2  lea     rax, ??_7SensorProfile@@6BIMFSensorProfileInternal@@@; const SensorProfile::`vftable'{for `IMFSensorProfileInternal'}
0x1800092c9  mov     rbx, rcx
0x1800092cc  mov     [rcx], rax
0x1800092cf  lea     rax, ??_7SensorProfile@@6BIMFAttributes@@@; const SensorProfile::`vftable'{for `IMFAttributes'}
0x1800092d6  mov     [rcx+8], rax
0x1800092da  cmp     cs:byte_18008D62D, 10h
0x1800092e1  jnb     short loc_180009318
0x1800092e3  lea     rcx, [rbx+80h]
0x1800092ea  call    ??1?$CTUnkArray@UIMFSensorProfileBlockedControl@@@@QEAA@XZ; CTUnkArray<IMFSensorProfileBlockedControl>::~CTUnkArray<IMFSensorProfileBlockedControl>(void)
0x1800092ef  lea     rcx, [rbx+78h]
0x1800092f3  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800092f8  lea     rcx, [rbx+60h]
0x1800092fc  call    ??1?$CTUnkArray@UIMFSensorProfilePin@@@@QEAA@XZ; CTUnkArray<IMFSensorProfilePin>::~CTUnkArray<IMFSensorProfilePin>(void)
0x180009301  lea     rcx, [rbx+18h]; lpCriticalSection
0x180009305  call    cs:__imp_DeleteCriticalSection
0x18000930b  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x180009312  add     rsp, 20h
0x180009316  pop     rbx
0x180009317  retn
0x180009318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000931f  lea     r8, WPP_31927b3ff17c3be32b5b8560ff5597aa_Traceguids
0x180009326  mov     edx, 21h ; '!'
0x18000932b  mov     r9, rbx
0x18000932e  mov     rcx, [rcx+0D8h]
0x180009335  call    WPP_SF_q
0x18000933a  jmp     short loc_1800092E3
```
