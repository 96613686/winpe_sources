# CMetadataUnknownReaderWriter::FillCache(void)

- ea: `0x1800a0a44`
- end: `0x1800a0b0c`
- name: `?FillCache@CMetadataUnknownReaderWriter@@IEAAJXZ`
- size: `200`
- prototype: `__int64 __fastcall(CMetadataUnknownReaderWriter *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a07a0`
- `0x1800a0840`
- `0x1800a0950`
- `0x1801ac130`

## callees

- `0x180036cb4`
- `0x1800a0a44`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0a83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a0a83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0a60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0ae3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0a60`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0ae3`

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
0x1800a0a44  mov     [rsp+arg_0], rbx
0x1800a0a49  mov     [rsp+arg_8], rsi
0x1800a0a4e  push    rdi
0x1800a0a4f  sub     rsp, 20h
0x1800a0a53  lea     rsi, [rcx+98h]
0x1800a0a5a  mov     rdi, rcx
0x1800a0a5d  mov     rcx, rsi; pvar
0x1800a0a60  call    cs:__imp_PropVariantClear
0x1800a0a66  mov     ebx, eax
0x1800a0a68  test    eax, eax
0x1800a0a6a  js      short loc_1800A0AD0
0x1800a0a6c  mov     ecx, [rdi+80h]
0x1800a0a72  sub     ecx, [rdi+88h]; cb
0x1800a0a78  mov     [rdi+0A0h], ecx
0x1800a0a7e  mov     word ptr [rsi], 41h ; 'A'
0x1800a0a83  call    cs:__imp_CoTaskMemAlloc
0x1800a0a89  mov     [rdi+0A8h], rax
0x1800a0a90  mov     r9, rax
0x1800a0a93  test    rax, rax
0x1800a0a96  jz      short loc_1800A0AFA
0x1800a0a98  mov     rax, [rdi+78h]
0x1800a0a9c  mov     r8d, [rdi+0A0h]; unsigned int
0x1800a0aa3  lea     rdx, [rax+10h]
0x1800a0aa7  neg     rax
0x1800a0aaa  sbb     rcx, rcx
0x1800a0aad  and     rcx, rdx; struct IStream *
0x1800a0ab0  mov     rdx, r9; void *
0x1800a0ab3  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800a0ab8  mov     ebx, eax
0x1800a0aba  test    eax, eax
0x1800a0abc  js      short loc_1800A0AEB
0x1800a0abe  mov     rsi, [rsp+28h+arg_8]
0x1800a0ac3  mov     eax, ebx
0x1800a0ac5  mov     rbx, [rsp+28h+arg_0]
0x1800a0aca  add     rsp, 20h
0x1800a0ace  pop     rdi
0x1800a0acf  retn
0x1800a0ad0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a0ad7  jz      short loc_1800A0AE0
0x1800a0ad9  mov     ecx, eax; int
0x1800a0adb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a0ae0  mov     rcx, rsi; pvar
0x1800a0ae3  call    cs:__imp_PropVariantClear
0x1800a0ae9  jmp     short loc_1800A0ABE
0x1800a0aeb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a0af2  jnz     short loc_1800A0AD9
0x1800a0af4  test    eax, eax
0x1800a0af6  jns     short loc_1800A0ABE
0x1800a0af8  jmp     short loc_1800A0AE0
0x1800a0afa  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a0b01  mov     ebx, 8007000Eh
0x1800a0b06  jz      short loc_1800A0AE0
0x1800a0b08  mov     ecx, ebx
0x1800a0b0a  jmp     short loc_1800A0ADB
```
