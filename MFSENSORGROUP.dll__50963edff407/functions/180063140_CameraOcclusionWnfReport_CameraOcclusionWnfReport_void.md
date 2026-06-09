# CameraOcclusionWnfReport::~CameraOcclusionWnfReport(void)

- ea: `0x180063140`
- end: `0x180063183`
- name: `??1CameraOcclusionWnfReport@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CameraOcclusionWnfReport *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180035180`

## callees

- `0x18003b10c`
- `0x180044b28`
- `0x180063140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063170`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180063170`

## pseudocode

```c
void __fastcall CameraOcclusionWnfReport::~CameraOcclusionWnfReport(CameraOcclusionWnfReport *this)
{
  void *v2; // rcx

  utl::vector<wil::com_ptr_t<IMFCameraOcclusionStateReportInternal,wil::err_returncode_policy>,utl::allocator<wil::com_ptr_t<IMFCameraOcclusionStateReportInternal,wil::err_returncode_policy>>>::_Uninit((char *)this + 80);
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 != (void *)-1LL )
  {
    *((_QWORD *)this + 8) = v2;
    operator delete(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x180063140  push    rbx
0x180063142  sub     rsp, 20h
0x180063146  mov     rbx, rcx
0x180063149  add     rcx, 50h ; 'P'
0x18006314d  call    ?_Uninit@?$vector@V?$com_ptr_t@UIMFCameraOcclusionStateReportInternal@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMFCameraOcclusionStateReportInternal@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@AEAAXXZ; utl::vector<wil::com_ptr_t<IMFCameraOcclusionStateReportInternal,wil::err_returncode_policy>,utl::allocator<wil::com_ptr_t<IMFCameraOcclusionStateReportInternal,wil::err_returncode_policy>>>::_Uninit(void)
0x180063152  mov     rcx, [rbx+38h]; Block
0x180063156  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006315a  jz      short loc_18006316C
0x18006315c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180063163  mov     [rbx+40h], rcx
0x180063167  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006316c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180063170  call    cs:__imp_DeleteCriticalSection
0x180063176  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x18006317d  add     rsp, 20h
0x180063181  pop     rbx
0x180063182  retn
```
