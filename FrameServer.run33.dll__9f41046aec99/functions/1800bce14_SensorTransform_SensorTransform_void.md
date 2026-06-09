# SensorTransform::~SensorTransform(void)

- ea: `0x1800bce14`
- end: `0x1800bcf8f`
- name: `??1SensorTransform@@MEAA@XZ`
- size: `379`
- prototype: `void __fastcall(SensorTransform *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bcfd0`

## callees

- `0x1800041f0`
- `0x180008cf0`
- `0x18000a460`
- `0x18002b654`
- `0x1800bce14`
- `0x1800bcf98`
- `0x1800c1760`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bce93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bce93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bcf76`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bcf76`

## pseudocode

```c
void __fastcall SensorTransform::~SensorTransform(SensorTransform *this, const struct std::nothrow_t *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  HMODULE v5; // rcx

  *(_QWORD *)this = &SensorTransform::`vftable'{for `IMFMediaSourceEx'};
  *((_QWORD *)this + 1) = &SensorTransform::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 2) = &SensorTransform::`vftable'{for `IKsControl'};
  *((_QWORD *)this + 3) = &SensorTransform::`vftable'{for `IFSSensorGroupTransform'};
  v3 = (void *)*((_QWORD *)this + 89);
  if ( v3 )
  {
    operator delete(v3, a2);
    *((_QWORD *)this + 89) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 86);
  if ( v4 )
  {
    operator delete(v4, a2);
    *((_QWORD *)this + 86) = 0;
  }
  if ( *((_DWORD *)this + 148) == 2 )
  {
    v5 = (HMODULE)*((_QWORD *)this + 75);
    if ( v5 )
    {
      FreeLibrary(v5);
      *((_QWORD *)this + 75) = 0;
    }
  }
  SensorTransform::Shutdown(this);
  ComSmartPtr<IKsControl>::operator=((char *)this + 656);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      77,
      &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
      (char *)this + 64);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 808);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 800);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 792);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 760);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 736);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 728);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 720);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 696);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 680);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 664);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 656);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 648);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((char *)this + 56);
}

```

## disassembly

```asm
0x1800bce14  mov     [rsp+arg_0], rbx
0x1800bce19  push    rdi
0x1800bce1a  sub     rsp, 20h
0x1800bce1e  lea     rax, ??_7SensorTransform@@6BIMFMediaSourceEx@@@; const SensorTransform::`vftable'{for `IMFMediaSourceEx'}
0x1800bce25  mov     rbx, rcx
0x1800bce28  mov     [rcx], rax
0x1800bce2b  xor     edi, edi
0x1800bce2d  lea     rax, ??_7SensorTransform@@6BIMFGetService@@@; const SensorTransform::`vftable'{for `IMFGetService'}
0x1800bce34  mov     [rcx+8], rax
0x1800bce38  lea     rax, ??_7SensorTransform@@6BIKsControl@@@; const SensorTransform::`vftable'{for `IKsControl'}
0x1800bce3f  mov     [rcx+10h], rax
0x1800bce43  lea     rax, ??_7SensorTransform@@6BIFSSensorGroupTransform@@@; const SensorTransform::`vftable'{for `IFSSensorGroupTransform'}
0x1800bce4a  mov     [rcx+18h], rax
0x1800bce4e  mov     rcx, [rcx+2C8h]; void *
0x1800bce55  test    rcx, rcx
0x1800bce58  jz      short loc_1800BCE66
0x1800bce5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bce5f  mov     [rbx+2C8h], rdi
0x1800bce66  mov     rcx, [rbx+2B0h]; void *
0x1800bce6d  test    rcx, rcx
0x1800bce70  jz      short loc_1800BCE7E
0x1800bce72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bce77  mov     [rbx+2B0h], rdi
0x1800bce7e  cmp     dword ptr [rbx+250h], 2
0x1800bce85  jnz     short loc_1800BCEA0
0x1800bce87  mov     rcx, [rbx+258h]; hLibModule
0x1800bce8e  test    rcx, rcx
0x1800bce91  jz      short loc_1800BCEA0
0x1800bce93  call    cs:__imp_FreeLibrary
0x1800bce99  mov     [rbx+258h], rdi
0x1800bcea0  mov     rcx, rbx; this
0x1800bcea3  call    ?Shutdown@SensorTransform@@UEAAJXZ; SensorTransform::Shutdown(void)
0x1800bcea8  lea     rdi, [rbx+290h]
0x1800bceaf  mov     rcx, rdi
0x1800bceb2  call    ??4?$ComSmartPtr@UIKsControl@@@@QEAAPEAUIKsControl@@PEAU1@@Z; ComSmartPtr<IKsControl>::operator=(IKsControl *)
0x1800bceb7  cmp     cs:byte_18010EC4D, 8
0x1800bcebe  jb      short loc_1800BCEE3
0x1800bcec0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcec7  lea     r9, [rbx+40h]
0x1800bcecb  mov     edx, 4Dh ; 'M'
0x1800bced0  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800bced7  mov     rcx, [rcx+0D8h]
0x1800bcede  call    WPP_SF_S
0x1800bcee3  lea     rcx, [rbx+328h]; void *
0x1800bceea  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800bceef  lea     rcx, [rbx+320h]; void *
0x1800bcef6  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcefb  lea     rcx, [rbx+318h]; void *
0x1800bcf02  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf07  lea     rcx, [rbx+2F8h]; void *
0x1800bcf0e  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800bcf13  lea     rcx, [rbx+2E0h]; void *
0x1800bcf1a  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800bcf1f  lea     rcx, [rbx+2D8h]; void *
0x1800bcf26  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf2b  lea     rcx, [rbx+2D0h]; void *
0x1800bcf32  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf37  lea     rcx, [rbx+2B8h]; void *
0x1800bcf3e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf43  lea     rcx, [rbx+2A8h]; void *
0x1800bcf4a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf4f  lea     rcx, [rbx+298h]; void *
0x1800bcf56  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf5b  mov     rcx, rdi; void *
0x1800bcf5e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf63  lea     rcx, [rbx+288h]; void *
0x1800bcf6a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bcf6f  lea     rcx, [rbx+260h]; lpCriticalSection
0x1800bcf76  call    cs:__imp_DeleteCriticalSection
0x1800bcf7c  lea     rcx, [rbx+38h]; void *
0x1800bcf80  mov     rbx, [rsp+28h+arg_0]
0x1800bcf85  add     rsp, 20h
0x1800bcf89  pop     rdi
0x1800bcf8a  jmp     ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
```
