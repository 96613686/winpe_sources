# SensorProfileCollection::~SensorProfileCollection(void)

- ea: `0x18000b93c`
- end: `0x18000b9c8`
- name: `??1SensorProfileCollection@@MEAA@XZ`
- size: `140`
- prototype: `void __fastcall(SensorProfileCollection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b900`

## callees

- `0x180008f9c`
- `0x18000aa08`
- `0x18000b93c`
- `0x18000bb0c`
- `0x180044b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b991`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b991`

## pseudocode

```c
void __fastcall SensorProfileCollection::~SensorProfileCollection(SensorProfileCollection *this)
{
  *(_QWORD *)this = &SensorProfileCollection::`vftable'{for `IMFSensorProfileCollectionInternal'};
  *((_QWORD *)this + 1) = &SensorProfileCollection::`vftable'{for `IMFAttributes'};
  operator delete(*((void **)this + 11));
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids, this);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)this + 13);
  CTUnkArray<IMFSensorProfileInternal>::~CTUnkArray<IMFSensorProfileInternal>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x18000b93c  push    rbx
0x18000b93e  sub     rsp, 20h
0x18000b942  lea     rax, ??_7SensorProfileCollection@@6BIMFSensorProfileCollectionInternal@@@; const SensorProfileCollection::`vftable'{for `IMFSensorProfileCollectionInternal'}
0x18000b949  mov     rbx, rcx
0x18000b94c  mov     [rcx], rax
0x18000b94f  lea     rax, ??_7SensorProfileCollection@@6BIMFAttributes@@@; const SensorProfileCollection::`vftable'{for `IMFAttributes'}
0x18000b956  mov     [rcx+8], rax
0x18000b95a  mov     rcx, [rcx+58h]; Block
0x18000b95e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b963  mov     qword ptr [rbx+58h], 0
0x18000b96b  mov     dword ptr [rbx+60h], 0
0x18000b972  cmp     cs:byte_18008D62D, 10h
0x18000b979  jnb     short loc_18000B9A4
0x18000b97b  lea     rcx, [rbx+68h]
0x18000b97f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18000b984  lea     rcx, [rbx+40h]
0x18000b988  call    ??1?$CTUnkArray@UIMFSensorProfileInternal@@@@QEAA@XZ; CTUnkArray<IMFSensorProfileInternal>::~CTUnkArray<IMFSensorProfileInternal>(void)
0x18000b98d  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000b991  call    cs:__imp_DeleteCriticalSection
0x18000b997  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x18000b99e  add     rsp, 20h
0x18000b9a2  pop     rbx
0x18000b9a3  retn
0x18000b9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9ab  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x18000b9b2  mov     edx, 0Fh
0x18000b9b7  mov     r9, rbx
0x18000b9ba  mov     rcx, [rcx+0D8h]
0x18000b9c1  call    WPP_SF_q
0x18000b9c6  jmp     short loc_18000B97B
```
