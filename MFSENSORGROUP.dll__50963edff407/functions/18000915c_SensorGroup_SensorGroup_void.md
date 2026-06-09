# SensorGroup::~SensorGroup(void)

- ea: `0x18000915c`
- end: `0x180009276`
- name: `??1SensorGroup@@MEAA@XZ`
- size: `282`
- prototype: `void __fastcall(SensorGroup *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009120`

## callees

- `0x180008bd0`
- `0x180008f9c`
- `0x18000915c`
- `0x180009600`
- `0x18000aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009210`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009260`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000924a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000924a`

## pseudocode

```c
void __fastcall SensorGroup::~SensorGroup(SensorGroup *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &SensorGroup::`vftable'{for `IMFSensorGroup'};
  *((_QWORD *)this + 1) = &SensorGroup::`vftable'{for `IMFSensorGroupInternal'};
  *((_QWORD *)this + 2) = &SensorGroup::`vftable'{for `IMFGetService'};
  if ( *((_QWORD *)this + 19) )
  {
    SwDeviceClose();
    *((_QWORD *)this + 19) = 0;
  }
  v2 = (void *)*((_QWORD *)this + 20);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 20) = 0;
  }
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 48);
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>((_DWORD *)this + 50);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 24);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 22);
  *((_QWORD *)this + 15) = &AutoSecurityAttributes::`vftable';
  AutoSecurityAttributes::Reset((SensorGroup *)((char *)this + 120));
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>((_DWORD *)this + 24);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 10);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x18000915c  push    rbx
0x18000915e  sub     rsp, 20h
0x180009162  lea     rax, ??_7SensorGroup@@6BIMFSensorGroup@@@
0x180009169  mov     rbx, rcx
0x18000916c  mov     [rcx], rax
0x18000916f  lea     rax, ??_7SensorGroup@@6BIMFSensorGroupInternal@@@
0x180009176  mov     [rcx+8], rax
0x18000917a  lea     rax, ??_7SensorGroup@@6BIMFGetService@@@
0x180009181  mov     [rcx+10h], rax
0x180009185  mov     rcx, [rcx+98h]
0x18000918c  test    rcx, rcx
0x18000918f  jnz     loc_18000924A
0x180009195  mov     rcx, [rbx+0A0h]; hObject
0x18000919c  test    rcx, rcx
0x18000919f  jnz     loc_180009260
0x1800091a5  cmp     cs:byte_18008D62D, 10h
0x1800091ac  jnb     short loc_180009223
0x1800091ae  lea     rcx, [rbx+180h]
0x1800091b5  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x1800091ba  lea     rcx, [rbx+0C8h]; void *
0x1800091c1  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ
0x1800091c6  lea     rcx, [rbx+0C0h]
0x1800091cd  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x1800091d2  lea     rcx, [rbx+0B0h]
0x1800091d9  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x1800091de  lea     rcx, [rbx+78h]; this
0x1800091e2  lea     rax, ??_7AutoSecurityAttributes@@6B@
0x1800091e9  mov     [rcx], rax
0x1800091ec  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ
0x1800091f1  lea     rcx, [rbx+60h]; void *
0x1800091f5  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ
0x1800091fa  lea     rcx, [rbx+50h]
0x1800091fe  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x180009203  lea     rcx, [rbx+48h]
0x180009207  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x18000920c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180009210  call    cs:__imp_DeleteCriticalSection
0x180009216  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA
0x18000921d  add     rsp, 20h
0x180009221  pop     rbx
0x180009222  retn
0x180009223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000922a  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x180009231  mov     edx, 0Bh
0x180009236  mov     r9, rbx
0x180009239  mov     rcx, [rcx+0D8h]
0x180009240  call    WPP_SF_q
0x180009245  jmp     loc_1800091AE
0x18000924a  call    cs:__imp_SwDeviceClose
0x180009250  mov     qword ptr [rbx+98h], 0
0x18000925b  jmp     loc_180009195
0x180009260  call    cs:__imp_CloseHandle
0x180009266  mov     qword ptr [rbx+0A0h], 0
0x180009271  jmp     loc_1800091A5
```
