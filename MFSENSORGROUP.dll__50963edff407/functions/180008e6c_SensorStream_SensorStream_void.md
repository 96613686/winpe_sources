# SensorStream::~SensorStream(void)

- ea: `0x180008e6c`
- end: `0x180008eff`
- name: `??1SensorStream@@MEAA@XZ`
- size: `147`
- prototype: `void __fastcall(SensorStream *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008e30`

## callees

- `0x180008e6c`
- `0x180008f9c`
- `0x180008fc0`
- `0x18000904c`
- `0x18000aa08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008ec8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008ec8`

## pseudocode

```c
void __fastcall SensorStream::~SensorStream(SensorStream *this)
{
  *(_QWORD *)this = &SensorStream::`vftable';
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, this);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 84);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 83);
  CTSparseBlock<unsigned long,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0007,20,0>::~CTSparseBlock<unsigned long,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0007,20,0>((char *)this + 120);
  CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>((char *)this + 96);
  CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>((char *)this + 72);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180008e6c  push    rbx
0x180008e6e  sub     rsp, 20h
0x180008e72  lea     rax, ??_7SensorStream@@6B@; const SensorStream::`vftable'
0x180008e79  mov     rbx, rcx
0x180008e7c  mov     [rcx], rax
0x180008e7f  cmp     cs:byte_18008D62D, 10h
0x180008e86  jnb     short loc_180008EDB
0x180008e88  lea     rcx, [rbx+2A0h]
0x180008e8f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180008e94  lea     rcx, [rbx+298h]
0x180008e9b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180008ea0  lea     rcx, [rbx+78h]
0x180008ea4  call    ??1?$CTSparseBlock@KU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0007@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0007,20,0>::~CTSparseBlock<ulong,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0007,20,0>(void)
0x180008ea9  lea     rcx, [rbx+60h]
0x180008ead  call    ??1?$CTUnkArray@UIMFMediaType@@@@QEAA@XZ; CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>(void)
0x180008eb2  lea     rcx, [rbx+48h]
0x180008eb6  call    ??1?$CTUnkArray@UIMFMediaType@@@@QEAA@XZ; CTUnkArray<IMFMediaType>::~CTUnkArray<IMFMediaType>(void)
0x180008ebb  lea     rcx, [rbx+40h]
0x180008ebf  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180008ec4  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008ec8  call    cs:__imp_DeleteCriticalSection
0x180008ece  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x180008ed5  add     rsp, 20h
0x180008ed9  pop     rbx
0x180008eda  retn
0x180008edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee2  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x180008ee9  mov     edx, 17h
0x180008eee  mov     r9, rbx
0x180008ef1  mov     rcx, [rcx+0D8h]
0x180008ef8  call    WPP_SF_q
0x180008efd  jmp     short loc_180008E88
```
