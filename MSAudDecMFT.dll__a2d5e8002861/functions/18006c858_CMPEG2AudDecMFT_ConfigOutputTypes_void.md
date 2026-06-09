# CMPEG2AudDecMFT::ConfigOutputTypes(void)

- ea: `0x18006c858`
- end: `0x18006cde6`
- name: `?ConfigOutputTypes@CMPEG2AudDecMFT@@AEAAJXZ`
- size: `1422`
- prototype: `__int64 __fastcall(CMPEG2AudDecMFT *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006bb40`

## callees

- `0x1800310a0`
- `0x1800314e0`
- `0x18006c858`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18006c88c`
- `MFPlat!MFCreateMediaType` at `0x18006c9e2`
- `MFPlat!MFCreateMediaType` at `0x18006cb33`
- `MFPlat!MFCreateMediaType` at `0x18006cc83`
- `MFPlat!MFCreateMediaType` at `0x18006c88c`
- `MFPlat!MFCreateMediaType` at `0x18006c9e2`
- `MFPlat!MFCreateMediaType` at `0x18006cb33`
- `MFPlat!MFCreateMediaType` at `0x18006cc83`

## pseudocode

```c
__int64 __fastcall CMPEG2AudDecMFT::ConfigOutputTypes(CMPEG2AudDecMFT *this)
{
  CMFTSimpleBase *v1; // rdi
  HRESULT inited; // ebx
  IMFMediaType *v3; // rcx
  IMFMediaType *ppMFType; // [rsp+50h] [rbp+28h] BYREF

  v1 = (CMPEG2AudDecMFT *)((char *)this + 120);
  ppMFType = 0;
  inited = CMFTSimpleBase::_InitAvailableOutputTypeArray((CMPEG2AudDecMFT *)((char *)this + 120), 4u);
  if ( inited < 0 )
    goto LABEL_42;
  inited = MFCreateMediaType(&ppMFType);
  if ( inited < 0 )
    goto LABEL_42;
  if ( !ppMFType )
    return (unsigned int)inited;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MEDIATYPE_Audio);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &MFAudioFormat_Float);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_BITS_PER_SAMPLE,
             32);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_NUM_CHANNELS,
             2);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_BLOCK_ALIGNMENT,
             8);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_ALL_SAMPLES_INDEPENDENT,
             1);
  if ( inited < 0 )
    goto LABEL_42;
  CMFTSimpleBase::_SetAvailableOutputType(v1, 0, ppMFType);
  if ( ppMFType )
  {
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    ppMFType = 0;
  }
  inited = MFCreateMediaType(&ppMFType);
  if ( inited < 0 )
    goto LABEL_42;
  if ( !ppMFType )
    return (unsigned int)inited;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MEDIATYPE_Audio);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &MFAudioFormat_PCM);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_BITS_PER_SAMPLE,
             16);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_NUM_CHANNELS,
             2);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_BLOCK_ALIGNMENT,
             4);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_ALL_SAMPLES_INDEPENDENT,
             1);
  if ( inited < 0 )
    goto LABEL_42;
  CMFTSimpleBase::_SetAvailableOutputType(v1, 1u, ppMFType);
  if ( ppMFType )
  {
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    ppMFType = 0;
  }
  inited = MFCreateMediaType(&ppMFType);
  if ( inited < 0 )
    goto LABEL_42;
  if ( !ppMFType )
    return (unsigned int)inited;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MEDIATYPE_Audio);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &MFAudioFormat_Float);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_BITS_PER_SAMPLE,
             32);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_NUM_CHANNELS,
             1);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_AUDIO_BLOCK_ALIGNMENT,
             4);
  if ( inited < 0 )
    goto LABEL_42;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_ALL_SAMPLES_INDEPENDENT,
             1);
  if ( inited < 0 )
    goto LABEL_42;
  CMFTSimpleBase::_SetAvailableOutputType(v1, 2u, ppMFType);
  if ( ppMFType )
  {
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    ppMFType = 0;
  }
  inited = MFCreateMediaType(&ppMFType);
  if ( inited < 0 )
    goto LABEL_42;
  if ( !ppMFType )
    return (unsigned int)inited;
  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_MAJOR_TYPE,
             &MEDIATYPE_Audio);
  if ( inited < 0
    || (inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFAudioFormat_PCM),
        inited < 0)
    || (inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_AUDIO_BITS_PER_SAMPLE,
                   16),
        inited < 0)
    || (inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_AUDIO_NUM_CHANNELS,
                   1),
        inited < 0)
    || (inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                   2),
        inited < 0)
    || (inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_ALL_SAMPLES_INDEPENDENT,
                   1),
        inited < 0) )
  {
LABEL_42:
    v3 = ppMFType;
  }
  else
  {
    CMFTSimpleBase::_SetAvailableOutputType(v1, 3u, ppMFType);
    if ( !ppMFType )
      return (unsigned int)inited;
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    v3 = 0;
    ppMFType = 0;
  }
  if ( v3 )
    ((void (__fastcall *)(IMFMediaType *))v3->lpVtbl->Release)(v3);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006c858  push    rbp
0x18006c85a  push    rbx
0x18006c85b  push    rdi
0x18006c85c  push    r14
0x18006c85e  mov     rbp, rsp
0x18006c861  sub     rsp, 28h
0x18006c865  lea     rdi, [rcx+78h]
0x18006c869  mov     [rbp+ppMFType], 0
0x18006c871  mov     rcx, rdi; this
0x18006c874  mov     edx, 4; unsigned int
0x18006c879  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x18006c87e  mov     ebx, eax
0x18006c880  test    eax, eax
0x18006c882  js      loc_18006CDC3
0x18006c888  lea     rcx, [rbp+ppMFType]; ppMFType
0x18006c88c  call    cs:__imp_MFCreateMediaType
0x18006c893  nop     dword ptr [rax+rax+00h]
0x18006c898  mov     ebx, eax
0x18006c89a  test    eax, eax
0x18006c89c  js      loc_18006CDC3
0x18006c8a2  mov     rcx, [rbp+ppMFType]
0x18006c8a6  test    rcx, rcx
0x18006c8a9  jz      loc_18006CDD9
0x18006c8af  mov     rax, [rcx]
0x18006c8b2  lea     r8, MEDIATYPE_Audio
0x18006c8b9  lea     rdx, MF_MT_MAJOR_TYPE
0x18006c8c0  mov     rax, [rax+0C0h]
0x18006c8c7  call    cs:__guard_dispatch_icall_fptr
0x18006c8cd  mov     ebx, eax
0x18006c8cf  test    eax, eax
0x18006c8d1  js      loc_18006CDC3
0x18006c8d7  mov     rcx, [rbp+ppMFType]
0x18006c8db  lea     r8, MFAudioFormat_Float
0x18006c8e2  lea     rdx, MF_MT_SUBTYPE
0x18006c8e9  mov     rax, [rcx]
0x18006c8ec  mov     rax, [rax+0C0h]
0x18006c8f3  call    cs:__guard_dispatch_icall_fptr
0x18006c8f9  mov     ebx, eax
0x18006c8fb  test    eax, eax
0x18006c8fd  js      loc_18006CDC3
0x18006c903  mov     rcx, [rbp+ppMFType]
0x18006c907  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18006c90e  mov     r8d, 20h ; ' '
0x18006c914  mov     rax, [rcx]
0x18006c917  mov     rax, [rax+0A8h]
0x18006c91e  call    cs:__guard_dispatch_icall_fptr
0x18006c924  mov     ebx, eax
0x18006c926  test    eax, eax
0x18006c928  js      loc_18006CDC3
0x18006c92e  mov     rcx, [rbp+ppMFType]
0x18006c932  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18006c939  mov     r8d, 2
0x18006c93f  mov     rax, [rcx]
0x18006c942  mov     rax, [rax+0A8h]
0x18006c949  call    cs:__guard_dispatch_icall_fptr
0x18006c94f  mov     ebx, eax
0x18006c951  test    eax, eax
0x18006c953  js      loc_18006CDC3
0x18006c959  mov     rcx, [rbp+ppMFType]
0x18006c95d  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18006c964  mov     r8d, 8
0x18006c96a  mov     rax, [rcx]
0x18006c96d  mov     rax, [rax+0A8h]
0x18006c974  call    cs:__guard_dispatch_icall_fptr
0x18006c97a  mov     ebx, eax
0x18006c97c  test    eax, eax
0x18006c97e  js      loc_18006CDC3
0x18006c984  mov     rcx, [rbp+ppMFType]
0x18006c988  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18006c98f  mov     r14d, 1
0x18006c995  mov     r8d, r14d
0x18006c998  mov     rax, [rcx]
0x18006c99b  mov     rax, [rax+0A8h]
0x18006c9a2  call    cs:__guard_dispatch_icall_fptr
0x18006c9a8  mov     ebx, eax
0x18006c9aa  test    eax, eax
0x18006c9ac  js      loc_18006CDC3
0x18006c9b2  mov     r8, [rbp+ppMFType]; struct IMFMediaType *
0x18006c9b6  xor     edx, edx; unsigned int
0x18006c9b8  mov     rcx, rdi; this
0x18006c9bb  call    ?_SetAvailableOutputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableOutputType(ulong,IMFMediaType *)
0x18006c9c0  mov     rcx, [rbp+ppMFType]
0x18006c9c4  test    rcx, rcx
0x18006c9c7  jz      short loc_18006C9DE
0x18006c9c9  mov     rax, [rcx]
0x18006c9cc  mov     rax, [rax+10h]
0x18006c9d0  call    cs:__guard_dispatch_icall_fptr
0x18006c9d6  mov     [rbp+ppMFType], 0
0x18006c9de  lea     rcx, [rbp+ppMFType]; ppMFType
0x18006c9e2  call    cs:__imp_MFCreateMediaType
0x18006c9e9  nop     dword ptr [rax+rax+00h]
0x18006c9ee  mov     ebx, eax
0x18006c9f0  test    eax, eax
0x18006c9f2  js      loc_18006CDC3
0x18006c9f8  mov     rcx, [rbp+ppMFType]
0x18006c9fc  test    rcx, rcx
0x18006c9ff  jz      loc_18006CDD9
0x18006ca05  mov     rax, [rcx]
0x18006ca08  lea     r8, MEDIATYPE_Audio
0x18006ca0f  lea     rdx, MF_MT_MAJOR_TYPE
0x18006ca16  mov     rax, [rax+0C0h]
0x18006ca1d  call    cs:__guard_dispatch_icall_fptr
0x18006ca23  mov     ebx, eax
0x18006ca25  test    eax, eax
0x18006ca27  js      loc_18006CDC3
0x18006ca2d  mov     rcx, [rbp+ppMFType]
0x18006ca31  lea     r8, MFAudioFormat_PCM
0x18006ca38  lea     rdx, MF_MT_SUBTYPE
0x18006ca3f  mov     rax, [rcx]
0x18006ca42  mov     rax, [rax+0C0h]
0x18006ca49  call    cs:__guard_dispatch_icall_fptr
0x18006ca4f  mov     ebx, eax
0x18006ca51  test    eax, eax
0x18006ca53  js      loc_18006CDC3
0x18006ca59  mov     rcx, [rbp+ppMFType]
0x18006ca5d  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18006ca64  mov     r8d, 10h
0x18006ca6a  mov     rax, [rcx]
0x18006ca6d  mov     rax, [rax+0A8h]
0x18006ca74  call    cs:__guard_dispatch_icall_fptr
0x18006ca7a  mov     ebx, eax
0x18006ca7c  test    eax, eax
0x18006ca7e  js      loc_18006CDC3
0x18006ca84  mov     rcx, [rbp+ppMFType]
0x18006ca88  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18006ca8f  mov     r8d, 2
0x18006ca95  mov     rax, [rcx]
0x18006ca98  mov     rax, [rax+0A8h]
0x18006ca9f  call    cs:__guard_dispatch_icall_fptr
0x18006caa5  mov     ebx, eax
0x18006caa7  test    eax, eax
0x18006caa9  js      loc_18006CDC3
0x18006caaf  mov     rcx, [rbp+ppMFType]
0x18006cab3  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18006caba  mov     r8d, 4
0x18006cac0  mov     rax, [rcx]
0x18006cac3  mov     rax, [rax+0A8h]
0x18006caca  call    cs:__guard_dispatch_icall_fptr
0x18006cad0  mov     ebx, eax
0x18006cad2  test    eax, eax
0x18006cad4  js      loc_18006CDC3
0x18006cada  mov     rcx, [rbp+ppMFType]
0x18006cade  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18006cae5  mov     r8d, r14d
0x18006cae8  mov     rax, [rcx]
0x18006caeb  mov     rax, [rax+0A8h]
0x18006caf2  call    cs:__guard_dispatch_icall_fptr
0x18006caf8  mov     ebx, eax
0x18006cafa  test    eax, eax
0x18006cafc  js      loc_18006CDC3
0x18006cb02  mov     r8, [rbp+ppMFType]; struct IMFMediaType *
0x18006cb06  mov     edx, r14d; unsigned int
0x18006cb09  mov     rcx, rdi; this
0x18006cb0c  call    ?_SetAvailableOutputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableOutputType(ulong,IMFMediaType *)
0x18006cb11  mov     rcx, [rbp+ppMFType]
0x18006cb15  test    rcx, rcx
0x18006cb18  jz      short loc_18006CB2F
0x18006cb1a  mov     rax, [rcx]
0x18006cb1d  mov     rax, [rax+10h]
0x18006cb21  call    cs:__guard_dispatch_icall_fptr
0x18006cb27  mov     [rbp+ppMFType], 0
0x18006cb2f  lea     rcx, [rbp+ppMFType]; ppMFType
0x18006cb33  call    cs:__imp_MFCreateMediaType
0x18006cb3a  nop     dword ptr [rax+rax+00h]
0x18006cb3f  mov     ebx, eax
0x18006cb41  test    eax, eax
0x18006cb43  js      loc_18006CDC3
0x18006cb49  mov     rcx, [rbp+ppMFType]
0x18006cb4d  test    rcx, rcx
0x18006cb50  jz      loc_18006CDD9
0x18006cb56  mov     rax, [rcx]
0x18006cb59  lea     r8, MEDIATYPE_Audio
0x18006cb60  lea     rdx, MF_MT_MAJOR_TYPE
0x18006cb67  mov     rax, [rax+0C0h]
0x18006cb6e  call    cs:__guard_dispatch_icall_fptr
0x18006cb74  mov     ebx, eax
0x18006cb76  test    eax, eax
0x18006cb78  js      loc_18006CDC3
0x18006cb7e  mov     rcx, [rbp+ppMFType]
0x18006cb82  lea     r8, MFAudioFormat_Float
0x18006cb89  lea     rdx, MF_MT_SUBTYPE
0x18006cb90  mov     rax, [rcx]
0x18006cb93  mov     rax, [rax+0C0h]
0x18006cb9a  call    cs:__guard_dispatch_icall_fptr
0x18006cba0  mov     ebx, eax
0x18006cba2  test    eax, eax
0x18006cba4  js      loc_18006CDC3
0x18006cbaa  mov     rcx, [rbp+ppMFType]
0x18006cbae  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18006cbb5  mov     r8d, 20h ; ' '
0x18006cbbb  mov     rax, [rcx]
0x18006cbbe  mov     rax, [rax+0A8h]
0x18006cbc5  call    cs:__guard_dispatch_icall_fptr
0x18006cbcb  mov     ebx, eax
0x18006cbcd  test    eax, eax
0x18006cbcf  js      loc_18006CDC3
0x18006cbd5  mov     rcx, [rbp+ppMFType]
0x18006cbd9  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18006cbe0  mov     r8d, r14d
0x18006cbe3  mov     rax, [rcx]
0x18006cbe6  mov     rax, [rax+0A8h]
0x18006cbed  call    cs:__guard_dispatch_icall_fptr
0x18006cbf3  mov     ebx, eax
0x18006cbf5  test    eax, eax
0x18006cbf7  js      loc_18006CDC3
0x18006cbfd  mov     rcx, [rbp+ppMFType]
0x18006cc01  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18006cc08  mov     r8d, 4
0x18006cc0e  mov     rax, [rcx]
0x18006cc11  mov     rax, [rax+0A8h]
0x18006cc18  call    cs:__guard_dispatch_icall_fptr
0x18006cc1e  mov     ebx, eax
0x18006cc20  test    eax, eax
0x18006cc22  js      loc_18006CDC3
0x18006cc28  mov     rcx, [rbp+ppMFType]
0x18006cc2c  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18006cc33  mov     r8d, r14d
0x18006cc36  mov     rax, [rcx]
0x18006cc39  mov     rax, [rax+0A8h]
0x18006cc40  call    cs:__guard_dispatch_icall_fptr
0x18006cc46  mov     ebx, eax
0x18006cc48  test    eax, eax
0x18006cc4a  js      loc_18006CDC3
0x18006cc50  mov     r8, [rbp+ppMFType]; struct IMFMediaType *
0x18006cc54  mov     edx, 2; unsigned int
0x18006cc59  mov     rcx, rdi; this
0x18006cc5c  call    ?_SetAvailableOutputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableOutputType(ulong,IMFMediaType *)
0x18006cc61  mov     rcx, [rbp+ppMFType]
0x18006cc65  test    rcx, rcx
0x18006cc68  jz      short loc_18006CC7F
0x18006cc6a  mov     rax, [rcx]
0x18006cc6d  mov     rax, [rax+10h]
0x18006cc71  call    cs:__guard_dispatch_icall_fptr
0x18006cc77  mov     [rbp+ppMFType], 0
0x18006cc7f  lea     rcx, [rbp+ppMFType]; ppMFType
0x18006cc83  call    cs:__imp_MFCreateMediaType
0x18006cc8a  nop     dword ptr [rax+rax+00h]
0x18006cc8f  mov     ebx, eax
0x18006cc91  test    eax, eax
0x18006cc93  js      loc_18006CDC3
0x18006cc99  mov     rcx, [rbp+ppMFType]
0x18006cc9d  test    rcx, rcx
0x18006cca0  jz      loc_18006CDD9
0x18006cca6  mov     rax, [rcx]
0x18006cca9  lea     r8, MEDIATYPE_Audio
0x18006ccb0  lea     rdx, MF_MT_MAJOR_TYPE
0x18006ccb7  mov     rax, [rax+0C0h]
0x18006ccbe  call    cs:__guard_dispatch_icall_fptr
0x18006ccc4  mov     ebx, eax
0x18006ccc6  test    eax, eax
0x18006ccc8  js      loc_18006CDC3
0x18006ccce  mov     rcx, [rbp+ppMFType]
0x18006ccd2  lea     r8, MFAudioFormat_PCM
0x18006ccd9  lea     rdx, MF_MT_SUBTYPE
0x18006cce0  mov     rax, [rcx]
0x18006cce3  mov     rax, [rax+0C0h]
0x18006ccea  call    cs:__guard_dispatch_icall_fptr
0x18006ccf0  mov     ebx, eax
0x18006ccf2  test    eax, eax
0x18006ccf4  js      loc_18006CDC3
0x18006ccfa  mov     rcx, [rbp+ppMFType]
0x18006ccfe  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18006cd05  mov     r8d, 10h
0x18006cd0b  mov     rax, [rcx]
0x18006cd0e  mov     rax, [rax+0A8h]
0x18006cd15  call    cs:__guard_dispatch_icall_fptr
0x18006cd1b  mov     ebx, eax
0x18006cd1d  test    eax, eax
0x18006cd1f  js      loc_18006CDC3
0x18006cd25  mov     rcx, [rbp+ppMFType]
0x18006cd29  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18006cd30  mov     r8d, r14d
0x18006cd33  mov     rax, [rcx]
0x18006cd36  mov     rax, [rax+0A8h]
0x18006cd3d  call    cs:__guard_dispatch_icall_fptr
0x18006cd43  mov     ebx, eax
0x18006cd45  test    eax, eax
0x18006cd47  js      short loc_18006CDC3
0x18006cd49  mov     rcx, [rbp+ppMFType]
0x18006cd4d  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18006cd54  mov     r8d, 2
0x18006cd5a  mov     rax, [rcx]
0x18006cd5d  mov     rax, [rax+0A8h]
0x18006cd64  call    cs:__guard_dispatch_icall_fptr
0x18006cd6a  mov     ebx, eax
0x18006cd6c  test    eax, eax
0x18006cd6e  js      short loc_18006CDC3
0x18006cd70  mov     rcx, [rbp+ppMFType]
0x18006cd74  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18006cd7b  mov     r8d, r14d
0x18006cd7e  mov     rax, [rcx]
0x18006cd81  mov     rax, [rax+0A8h]
0x18006cd88  call    cs:__guard_dispatch_icall_fptr
0x18006cd8e  mov     ebx, eax
0x18006cd90  test    eax, eax
0x18006cd92  js      short loc_18006CDC3
0x18006cd94  mov     r8, [rbp+ppMFType]; struct IMFMediaType *
0x18006cd98  mov     edx, 3; unsigned int
0x18006cd9d  mov     rcx, rdi; this
0x18006cda0  call    ?_SetAvailableOutputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableOutputType(ulong,IMFMediaType *)
  ... truncated ...
```
