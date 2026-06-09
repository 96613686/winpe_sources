# CMetadataUnknownReaderWriter::FillCache(void)

- ea: `0x1800a36ac`
- end: `0x1800a3787`
- name: `?FillCache@CMetadataUnknownReaderWriter@@IEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(CMetadataUnknownReaderWriter *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a33f0`
- `0x1800a3490`
- `0x1800a35b0`
- `0x1801af6c0`

## callees

- `0x1800542e8`
- `0x1800a36ac`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a36f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a36f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a36c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a3758`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a36c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a3758`

## pseudocode

```c
__int64 __fastcall CMetadataUnknownReaderWriter::FillCache(CMetadataUnknownReaderWriter *this)
{
  PROPVARIANT *v1; // rsi
  HRESULT FullBufferFromStream; // eax
  unsigned int v4; // ebx
  SIZE_T v5; // rcx
  void *v6; // rax
  int v8; // ecx

  v1 = (PROPVARIANT *)((char *)this + 152);
  FullBufferFromStream = PropVariantClear((PROPVARIANT *)this + 19);
  v4 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
    {
LABEL_8:
      PropVariantClear(v1);
      return v4;
    }
    goto LABEL_6;
  }
  v5 = (unsigned int)(*((_DWORD *)this + 32) - *((_DWORD *)this + 34));
  *((_DWORD *)this + 40) = v5;
  *(_WORD *)v1 = 65;
  v6 = CoTaskMemAlloc(v5);
  *((_QWORD *)this + 21) = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_8;
    v8 = -2147024882;
    goto LABEL_7;
  }
  FullBufferFromStream = ReadFullBufferFromStream(
                           (struct IStream *)((*((_QWORD *)this + 15) + 16LL) & -(__int64)(*((_QWORD *)this + 15) != 0)),
                           v6,
                           *((_DWORD *)this + 40));
  v4 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_8;
LABEL_6:
    v8 = FullBufferFromStream;
LABEL_7:
    DoStackCapture(v8);
    goto LABEL_8;
  }
  return v4;
}

```

## disassembly

```asm
0x1800a36ac  mov     [rsp+arg_0], rbx
0x1800a36b1  mov     [rsp+arg_8], rsi
0x1800a36b6  push    rdi
0x1800a36b7  sub     rsp, 20h
0x1800a36bb  lea     rsi, [rcx+98h]
0x1800a36c2  mov     rdi, rcx
0x1800a36c5  mov     rcx, rsi; pvar
0x1800a36c8  call    cs:__imp_PropVariantClear
0x1800a36cf  nop     dword ptr [rax+rax+00h]
0x1800a36d4  mov     ebx, eax
0x1800a36d6  test    eax, eax
0x1800a36d8  js      short loc_1800A3745
0x1800a36da  mov     ecx, [rdi+80h]
0x1800a36e0  sub     ecx, [rdi+88h]; cb
0x1800a36e6  mov     [rdi+0A0h], ecx
0x1800a36ec  mov     word ptr [rsi], 41h ; 'A'
0x1800a36f1  call    cs:__imp_CoTaskMemAlloc
0x1800a36f8  nop     dword ptr [rax+rax+00h]
0x1800a36fd  mov     [rdi+0A8h], rax
0x1800a3704  mov     r9, rax
0x1800a3707  test    rax, rax
0x1800a370a  jz      short loc_1800A3775
0x1800a370c  mov     rax, [rdi+78h]
0x1800a3710  mov     r8d, [rdi+0A0h]; unsigned int
0x1800a3717  lea     rdx, [rax+10h]
0x1800a371b  neg     rax
0x1800a371e  sbb     rcx, rcx
0x1800a3721  and     rcx, rdx; struct IStream *
0x1800a3724  mov     rdx, r9; void *
0x1800a3727  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800a372c  mov     ebx, eax
0x1800a372e  test    eax, eax
0x1800a3730  js      short loc_1800A3766
0x1800a3732  mov     rsi, [rsp+28h+arg_8]
0x1800a3737  mov     eax, ebx
0x1800a3739  mov     rbx, [rsp+28h+arg_0]
0x1800a373e  add     rsp, 20h
0x1800a3742  pop     rdi
0x1800a3743  retn
0x1800a3745  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a374c  jz      short loc_1800A3755
0x1800a374e  mov     ecx, eax; int
0x1800a3750  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a3755  mov     rcx, rsi; pvar
0x1800a3758  call    cs:__imp_PropVariantClear
0x1800a375f  nop     dword ptr [rax+rax+00h]
0x1800a3764  jmp     short loc_1800A3732
0x1800a3766  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a376d  jnz     short loc_1800A374E
0x1800a376f  test    eax, eax
0x1800a3771  jns     short loc_1800A3732
0x1800a3773  jmp     short loc_1800A3755
0x1800a3775  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a377c  mov     ebx, 8007000Eh
0x1800a3781  jz      short loc_1800A3755
0x1800a3783  mov     ecx, ebx
0x1800a3785  jmp     short loc_1800A3750
```
