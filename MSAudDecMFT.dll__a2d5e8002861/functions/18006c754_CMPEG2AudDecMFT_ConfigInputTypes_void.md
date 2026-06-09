# CMPEG2AudDecMFT::ConfigInputTypes(void)

- ea: `0x18006c754`
- end: `0x18006c851`
- name: `?ConfigInputTypes@CMPEG2AudDecMFT@@AEAAJXZ`
- size: `253`
- prototype: `__int64 __fastcall(CMPEG2AudDecMFT *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006bb40`

## callees

- `0x180031154`
- `0x18003120c`
- `0x18006c754`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18006c76f`
- `MFPlat!MFCreateMediaType` at `0x18006c76f`

## pseudocode

```c
__int64 __fastcall CMPEG2AudDecMFT::ConfigInputTypes(CMPEG2AudDecMFT *this)
{
  HRESULT inited; // ebx
  IMFMediaType *ppMFType; // [rsp+38h] [rbp+10h] BYREF

  ppMFType = 0;
  inited = MFCreateMediaType(&ppMFType);
  if ( inited >= 0 )
  {
    if ( !ppMFType )
      return (unsigned int)inited;
    inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
               ppMFType,
               &MF_MT_MAJOR_TYPE,
               &MEDIATYPE_Audio);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_SUBTYPE,
                 &MFAudioFormat_MPEG);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                   ppMFType,
                   &MF_MT_COMPRESSED,
                   1);
        if ( inited >= 0 )
        {
          inited = CMFTSimpleBase::_InitAvailableInputTypeArray((CMPEG2AudDecMFT *)((char *)this + 120), 1u);
          if ( inited >= 0 )
            CMFTSimpleBase::_SetAvailableInputType((CMPEG2AudDecMFT *)((char *)this + 120), 0, ppMFType);
        }
      }
    }
  }
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006c754  mov     [rsp+arg_0], rbx
0x18006c759  push    rdi
0x18006c75a  sub     rsp, 20h
0x18006c75e  mov     rdi, rcx
0x18006c761  mov     [rsp+28h+ppMFType], 0
0x18006c76a  lea     rcx, [rsp+28h+ppMFType]; ppMFType
0x18006c76f  call    cs:__imp_MFCreateMediaType
0x18006c776  nop     dword ptr [rax+rax+00h]
0x18006c77b  mov     ebx, eax
0x18006c77d  test    eax, eax
0x18006c77f  js      loc_18006C82C
0x18006c785  mov     rcx, [rsp+28h+ppMFType]
0x18006c78a  test    rcx, rcx
0x18006c78d  jz      loc_18006C843
0x18006c793  mov     rax, [rcx]
0x18006c796  lea     r8, MEDIATYPE_Audio
0x18006c79d  lea     rdx, MF_MT_MAJOR_TYPE
0x18006c7a4  mov     rax, [rax+0C0h]
0x18006c7ab  call    cs:__guard_dispatch_icall_fptr
0x18006c7b1  mov     ebx, eax
0x18006c7b3  test    eax, eax
0x18006c7b5  js      short loc_18006C82C
0x18006c7b7  mov     rcx, [rsp+28h+ppMFType]
0x18006c7bc  lea     r8, MFAudioFormat_MPEG
0x18006c7c3  lea     rdx, MF_MT_SUBTYPE
0x18006c7ca  mov     rax, [rcx]
0x18006c7cd  mov     rax, [rax+0C0h]
0x18006c7d4  call    cs:__guard_dispatch_icall_fptr
0x18006c7da  mov     ebx, eax
0x18006c7dc  test    eax, eax
0x18006c7de  js      short loc_18006C82C
0x18006c7e0  mov     rcx, [rsp+28h+ppMFType]
0x18006c7e5  lea     rdx, MF_MT_COMPRESSED
0x18006c7ec  mov     r8d, 1
0x18006c7f2  mov     rax, [rcx]
0x18006c7f5  mov     rax, [rax+0A8h]
0x18006c7fc  call    cs:__guard_dispatch_icall_fptr
0x18006c802  mov     ebx, eax
0x18006c804  test    eax, eax
0x18006c806  js      short loc_18006C82C
0x18006c808  mov     edx, 1; unsigned int
0x18006c80d  lea     rcx, [rdi+78h]; this
0x18006c811  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x18006c816  mov     ebx, eax
0x18006c818  test    eax, eax
0x18006c81a  js      short loc_18006C82C
0x18006c81c  mov     r8, [rsp+28h+ppMFType]; struct IMFMediaType *
0x18006c821  lea     rcx, [rdi+78h]; this
0x18006c825  xor     edx, edx; unsigned int
0x18006c827  call    ?_SetAvailableInputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableInputType(ulong,IMFMediaType *)
0x18006c82c  mov     rcx, [rsp+28h+ppMFType]
0x18006c831  test    rcx, rcx
0x18006c834  jz      short loc_18006C843
0x18006c836  mov     rax, [rcx]
0x18006c839  mov     rax, [rax+10h]
0x18006c83d  call    cs:__guard_dispatch_icall_fptr
0x18006c843  mov     eax, ebx
0x18006c845  mov     rbx, [rsp+28h+arg_0]
0x18006c84a  add     rsp, 20h
0x18006c84e  pop     rdi
0x18006c84f  retn
```
