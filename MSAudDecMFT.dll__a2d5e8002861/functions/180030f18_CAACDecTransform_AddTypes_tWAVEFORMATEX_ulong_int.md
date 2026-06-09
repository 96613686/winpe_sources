# CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)

- ea: `0x180030f18`
- end: `0x180030fff`
- name: `?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z`
- size: `231`
- prototype: `int(CAACDecTransform *__hidden this, struct tWAVEFORMATEX *, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800305d4`
- `0x180030924`

## callees

- `0x180030f18`
- `0x18003120c`
- `0x1800314e0`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x180030f60`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x180030f60`
- `MFPlat!MFCreateMediaType` at `0x180030f3d`
- `MFPlat!MFCreateMediaType` at `0x180030f3d`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::_AddTypes(
        CAACDecTransform *this,
        struct tWAVEFORMATEX *a2,
        unsigned int a3,
        int a4)
{
  HRESULT v8; // edi
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-38h] BYREF

  ppMFType = 0;
  v8 = MFCreateMediaType(&ppMFType);
  if ( v8 >= 0 )
  {
    v8 = MFInitMediaTypeFromWaveFormatEx(ppMFType, a2, a2->cbSize + 18);
    if ( v8 >= 0 )
    {
      if ( a4 )
      {
        CMFTSimpleBase::_SetAvailableInputType((CAACDecTransform *)((char *)this + 24), a3, ppMFType);
      }
      else if ( !*((_DWORD *)this + 64056)
             || (v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD, _QWORD))ppMFType->lpVtbl->SetBlob)(
                        ppMFType,
                        &MF_MT_MPEG4_SAMPLE_DESCRIPTION,
                        *((_QWORD *)this + 32029),
                        *((unsigned int *)this + 64060)),
                 v8 >= 0) )
      {
        CMFTSimpleBase::_SetAvailableOutputType((CAACDecTransform *)((char *)this + 24), a3, ppMFType);
      }
    }
  }
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030f18  push    rbx
0x180030f1a  push    rbp
0x180030f1b  push    rsi
0x180030f1c  push    rdi
0x180030f1d  push    r14
0x180030f1f  sub     rsp, 40h
0x180030f23  mov     rbx, rcx
0x180030f26  mov     [rsp+68h+ppMFType], 0
0x180030f2f  lea     rcx, [rsp+68h+ppMFType]; ppMFType
0x180030f34  mov     r14d, r9d
0x180030f37  mov     esi, r8d
0x180030f3a  mov     rbp, rdx
0x180030f3d  call    cs:__imp_MFCreateMediaType
0x180030f44  nop     dword ptr [rax+rax+00h]
0x180030f49  mov     edi, eax
0x180030f4b  test    eax, eax
0x180030f4d  js      short loc_180030F72
0x180030f4f  movzx   r8d, word ptr [rbp+10h]
0x180030f54  mov     rdx, rbp; pWaveFormat
0x180030f57  mov     rcx, [rsp+68h+ppMFType]; pMFType
0x180030f5c  add     r8d, 12h; cbBufSize
0x180030f60  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x180030f67  nop     dword ptr [rax+rax+00h]
0x180030f6c  mov     edi, eax
0x180030f6e  test    eax, eax
0x180030f70  jns     short loc_180030F97
0x180030f72  mov     rcx, [rsp+68h+ppMFType]
0x180030f77  test    rcx, rcx
0x180030f7a  jz      short loc_180030F89
0x180030f7c  mov     rax, [rcx]
0x180030f7f  mov     rax, [rax+10h]
0x180030f83  call    cs:__guard_dispatch_icall_fptr
0x180030f89  mov     eax, edi
0x180030f8b  add     rsp, 40h
0x180030f8f  pop     r14
0x180030f91  pop     rdi
0x180030f92  pop     rsi
0x180030f93  pop     rbp
0x180030f94  pop     rbx
0x180030f95  retn
0x180030f97  test    r14d, r14d
0x180030f9a  jz      short loc_180030FAE
0x180030f9c  mov     r8, [rsp+68h+ppMFType]; struct IMFMediaType *
0x180030fa1  lea     rcx, [rbx+18h]; this
0x180030fa5  mov     edx, esi; unsigned int
0x180030fa7  call    ?_SetAvailableInputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableInputType(ulong,IMFMediaType *)
0x180030fac  jmp     short loc_180030F72
0x180030fae  cmp     dword ptr [rbx+3E8E0h], 0
0x180030fb5  jnz     short loc_180030FC9
0x180030fb7  mov     r8, [rsp+68h+ppMFType]; struct IMFMediaType *
0x180030fbc  lea     rcx, [rbx+18h]; this
0x180030fc0  mov     edx, esi; unsigned int
0x180030fc2  call    ?_SetAvailableOutputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableOutputType(ulong,IMFMediaType *)
0x180030fc7  jmp     short loc_180030F72
0x180030fc9  mov     rcx, [rsp+68h+ppMFType]
0x180030fce  lea     rdx, MF_MT_MPEG4_SAMPLE_DESCRIPTION
0x180030fd5  mov     r9d, [rbx+3E8F0h]
0x180030fdc  mov     r8, [rbx+3E8E8h]
0x180030fe3  mov     rax, [rcx]
0x180030fe6  mov     rax, [rax+0D0h]
0x180030fed  call    cs:__guard_dispatch_icall_fptr
0x180030ff3  mov     edi, eax
0x180030ff5  test    eax, eax
0x180030ff7  js      loc_180030F72
0x180030ffd  jmp     short loc_180030FB7
```
