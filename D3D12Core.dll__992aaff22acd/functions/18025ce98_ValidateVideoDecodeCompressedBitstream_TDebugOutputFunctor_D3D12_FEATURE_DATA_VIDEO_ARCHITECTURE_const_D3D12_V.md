# ValidateVideoDecodeCompressedBitstream(TDebugOutputFunctor &,D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM const &)

- ea: `0x18025ce98`
- end: `0x18025cfce`
- name: `?ValidateVideoDecodeCompressedBitstream@@YAJAEAUTDebugOutputFunctor@@AEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@AEBUD3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM@@@Z`
- size: `310`
- prototype: `int(struct TDebugOutputFunctor *, const struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *, const struct D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18025c0b4`

## callees

- `0x180025550`
- `0x18002ef50`
- `0x18005f00c`
- `0x18025cda8`
- `0x18025ce98`

## string_xrefs

- `0x18025cf49`: `The D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Offset + D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Size exceeds the size of the buffer specified D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::pBuffer.`
- `0x18025cf60`: `The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM must not be a reserved resource.`
- `0x18025cf91`: `The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x18025cfb4`: `The bitstream size must be specified in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Size and cannot be zero.`
- `0x18025cf9a`: `The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Offset must be D3D12_VIDEO_DECODE_MIN_BITSTREAM_OFFSET_ALIGNMENT byte aligned.`
- `0x18025cf77`: `The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM must be a buffer.`

## pseudocode

```c
__int64 __fastcall ValidateVideoDecodeCompressedBitstream(
        struct TDebugOutputFunctor *a1,
        const struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *a2,
        const struct D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM *a3)
{
  unsigned int v6; // ebx
  CResource *v7; // rbp
  UINT64 v8; // rcx
  struct D3D12_RESOURCE_DESC v10; // [rsp+20h] [rbp-68h] BYREF

  v6 = 0;
  v7 = (CResource *)QIFrom<CResource>(a3->pBuffer);
  CResource::GetDesc(v7, &v10);
  if ( v10.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1110,
      "The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM must be a buffer.");
    v6 = -2147024809;
  }
  if ( *((_BYTE *)v7 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1110,
      "The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM must not be a reserved resource.");
  }
  else
  {
    if ( IsVideoHeapTypeSupported(a2, v7) )
      goto LABEL_5;
    TDebugOutputFunctor::operator()(
      a1,
      1110,
      "The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TY"
      "PE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must"
      " not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
  }
  v6 = -2147024809;
LABEL_5:
  if ( LOBYTE(a3->Offset) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1110,
      "The resource in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Offset must be D3D12_VIDEO_DECODE_MIN_BITSTREAM_OFFSET_AL"
      "IGNMENT byte aligned.");
    v6 = -2147024809;
  }
  if ( !a3->Size )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1110,
      "The bitstream size must be specified in D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Size and cannot be zero.");
    v6 = -2147024809;
  }
  v8 = a3->Offset + a3->Size;
  if ( v8 < a3->Offset || v8 > v10.Width )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1110,
      "The D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Offset + D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::Size exceeds the si"
      "ze of the buffer specified D3D12_VIDEO_DECODE_COMPRESSED_BITSTREAM::pBuffer.");
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18025ce98  mov     [rsp+arg_8], rbx
0x18025ce9d  mov     [rsp+arg_18], rbp
0x18025cea2  push    rsi
0x18025cea3  push    rdi
0x18025cea4  push    r12
0x18025cea6  push    r14
0x18025cea8  push    r15
0x18025ceaa  sub     rsp, 60h
0x18025ceae  mov     rdi, rcx
0x18025ceb1  mov     rsi, r8
0x18025ceb4  mov     rcx, [r8]
0x18025ceb7  mov     r14, rdx
0x18025ceba  xor     ebx, ebx
0x18025cebc  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x18025cec1  lea     rdx, [rsp+88h+var_68]; retstr
0x18025cec6  mov     rcx, rax; this
0x18025cec9  mov     rbp, rax
0x18025cecc  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x18025ced1  cmp     [rsp+88h+var_68.Dimension], 1
0x18025ced6  mov     r15d, 456h
0x18025cedc  mov     r12d, 80070057h
0x18025cee2  jnz     loc_18025CF77
0x18025cee8  cmp     byte ptr [rbp+188h], 3
0x18025ceef  jz      short loc_18025CF60
0x18025cef1  mov     rdx, rbp; struct CResource *
0x18025cef4  mov     rcx, r14; struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *
0x18025cef7  call    ?IsVideoHeapTypeSupported@@YA_NAEBUD3D12_FEATURE_DATA_VIDEO_ARCHITECTURE@@PEAVCResource@@@Z; IsVideoHeapTypeSupported(D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE const &,CResource *)
0x18025cefc  test    al, al
0x18025cefe  jz      loc_18025CF91
0x18025cf04  cmp     byte ptr [rsi+8], 0
0x18025cf08  jnz     loc_18025CF9A
0x18025cf0e  cmp     qword ptr [rsi+10h], 0
0x18025cf13  jz      loc_18025CFB4
0x18025cf19  mov     rcx, [rsi+10h]
0x18025cf1d  add     rcx, [rsi+8]
0x18025cf21  cmp     rcx, [rsi+8]
0x18025cf25  jb      short loc_18025CF49
0x18025cf27  cmp     rcx, [rsp+88h+var_68.Width]
0x18025cf2c  ja      short loc_18025CF49
0x18025cf2e  lea     r11, [rsp+88h+var_28]
0x18025cf33  mov     eax, ebx
0x18025cf35  mov     rbx, [r11+38h]
0x18025cf39  mov     rbp, [r11+48h]
0x18025cf3d  mov     rsp, r11
0x18025cf40  pop     r15
0x18025cf42  pop     r14
0x18025cf44  pop     r12
0x18025cf46  pop     rdi
0x18025cf47  pop     rsi
0x18025cf48  retn
0x18025cf49  lea     r8, aTheD3d12VideoD; "The D3D12_VIDEO_DECODE_COMPRESSED_BITST"...
0x18025cf50  mov     edx, r15d
0x18025cf53  mov     rcx, rdi
0x18025cf56  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025cf5b  mov     ebx, r12d
0x18025cf5e  jmp     short loc_18025CF2E
0x18025cf60  lea     r8, aTheResourceInD_7; "The resource in D3D12_VIDEO_DECODE_COMP"...
0x18025cf67  mov     edx, r15d
0x18025cf6a  mov     rcx, rdi
0x18025cf6d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025cf72  mov     ebx, r12d
0x18025cf75  jmp     short loc_18025CF04
0x18025cf77  lea     r8, aTheResourceInD_9; "The resource in D3D12_VIDEO_DECODE_COMP"...
0x18025cf7e  mov     edx, r15d
0x18025cf81  mov     rcx, rdi
0x18025cf84  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025cf89  mov     ebx, r12d
0x18025cf8c  jmp     loc_18025CEE8
0x18025cf91  lea     r8, aTheResourceInD_4; "The resource in D3D12_VIDEO_DECODE_COMP"...
0x18025cf98  jmp     short loc_18025CF67
0x18025cf9a  lea     r8, aTheResourceInD; "The resource in D3D12_VIDEO_DECODE_COMP"...
0x18025cfa1  mov     edx, r15d
0x18025cfa4  mov     rcx, rdi
0x18025cfa7  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025cfac  mov     ebx, r12d
0x18025cfaf  jmp     loc_18025CF0E
0x18025cfb4  lea     r8, aTheBitstreamSi; "The bitstream size must be specified in"...
0x18025cfbb  mov     edx, r15d
0x18025cfbe  mov     rcx, rdi
0x18025cfc1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025cfc6  mov     ebx, r12d
0x18025cfc9  jmp     loc_18025CF19
```
