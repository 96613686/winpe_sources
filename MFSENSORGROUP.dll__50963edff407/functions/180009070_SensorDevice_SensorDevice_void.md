# SensorDevice::~SensorDevice(void)

- ea: `0x180009070`
- end: `0x180009119`
- name: `??1SensorDevice@@MEAA@XZ`
- size: `169`
- prototype: `void __fastcall(SensorDevice *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008df0`

## callees

- `0x180008bd0`
- `0x180008f9c`
- `0x180009070`
- `0x18000aa08`
- `0x18000f5a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800090e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800090e2`

## pseudocode

```c
void __fastcall SensorDevice::~SensorDevice(SensorDevice *this)
{
  *(_QWORD *)this = &SensorDevice::`vftable'{for `IMFSensorDeviceInternal'};
  *((_QWORD *)this + 1) = &SensorDevice::`vftable'{for `IMFSensorDevice'};
  *((_QWORD *)this + 2) = &SensorDevice::`vftable'{for `IMFGetService'};
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 27);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 21);
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>((_DWORD *)this + 28);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 13);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 12);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset((char *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180009070  push    rbx
0x180009072  sub     rsp, 20h
0x180009076  lea     rax, ??_7SensorDevice@@6BIMFSensorDeviceInternal@@@; const SensorDevice::`vftable'{for `IMFSensorDeviceInternal'}
0x18000907d  mov     rbx, rcx
0x180009080  mov     [rcx], rax
0x180009083  lea     rax, ??_7SensorDevice@@6BIMFSensorDevice@@@; const SensorDevice::`vftable'{for `IMFSensorDevice'}
0x18000908a  mov     [rcx+8], rax
0x18000908e  lea     rax, ??_7SensorDevice@@6BIMFGetService@@@; const SensorDevice::`vftable'{for `IMFGetService'}
0x180009095  mov     [rcx+10h], rax
0x180009099  cmp     cs:byte_18008D62D, 10h
0x1800090a0  jnb     short loc_1800090F5
0x1800090a2  lea     rcx, [rbx+0D8h]
0x1800090a9  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800090ae  lea     rcx, [rbx+0A8h]
0x1800090b5  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800090ba  lea     rcx, [rbx+70h]; void *
0x1800090be  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x1800090c3  lea     rcx, [rbx+68h]
0x1800090c7  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800090cc  lea     rcx, [rbx+60h]
0x1800090d0  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800090d5  lea     rcx, [rbx+50h]
0x1800090d9  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800090de  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800090e2  call    cs:__imp_DeleteCriticalSection
0x1800090e8  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x1800090ef  add     rsp, 20h
0x1800090f3  pop     rbx
0x1800090f4  retn
0x1800090f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090fc  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x180009103  mov     edx, 0Bh
0x180009108  mov     r9, rbx
0x18000910b  mov     rcx, [rcx+0D8h]
0x180009112  call    WPP_SF_q
0x180009117  jmp     short loc_1800090A2
```
