# CPhotoThumbnailProvider::Initialize(ushort const *,ulong)

- ea: `0x18000fe40`
- end: `0x18000fef5`
- name: `?Initialize@CPhotoThumbnailProvider@@UEAAJPEBGK@Z`
- size: `181`
- prototype: `int(CPhotoThumbnailProvider *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000fe40`
- `0x1800110b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000fe88`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18000fe88`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPhotoThumbnailProvider::Initialize(const struct _GUID *this, const unsigned __int16 *a2, DWORD a3)
{
  unsigned __int64 v6; // r8
  const struct _GUID *v7; // rcx
  HRESULT v8; // ebx
  unsigned __int64 v9; // r8
  IStream *ppstm; // [rsp+48h] [rbp+20h] BYREF

  v6 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v6 )
    ShellPrivateTraceEvent(this, 0xEu, v6, 1u);
  ppstm = 0;
  v8 = SHCreateStreamOnFileW(a2, a3, &ppstm);
  if ( v8 >= 0 )
    v8 = (*(__int64 (__fastcall **)(unsigned __int8 *, IStream *, _QWORD))(*(_QWORD *)this[-1].Data4 + 24LL))(
           this[-1].Data4,
           ppstm,
           a3);
  v9 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v9 )
    ShellPrivateTraceEvent(v7, 0xEu, v9, 2u);
  if ( ppstm )
    ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fe40  mov     [rsp+arg_0], rbx
0x18000fe45  mov     [rsp+arg_8], rsi
0x18000fe4a  push    rdi
0x18000fe4b  sub     rsp, 20h
0x18000fe4f  mov     edi, r8d
0x18000fe52  mov     rbx, rdx
0x18000fe55  mov     rsi, rcx
0x18000fe58  mov     rax, cs:WPP_GLOBAL_Control
0x18000fe5f  mov     r8, [rax+38h]; unsigned __int64
0x18000fe63  test    r8, r8
0x18000fe66  jz      short loc_18000FE75
0x18000fe68  mov     r9b, 1; unsigned __int8
0x18000fe6b  mov     edx, 0Eh; unsigned int
0x18000fe70  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000fe75  mov     [rsp+28h+ppstm], 0
0x18000fe7e  lea     r8, [rsp+28h+ppstm]; ppstm
0x18000fe83  mov     edx, edi; grfMode
0x18000fe85  mov     rcx, rbx; pszFile
0x18000fe88  call    cs:__imp_SHCreateStreamOnFileW
0x18000fe8e  mov     ebx, eax
0x18000fe90  test    eax, eax
0x18000fe92  js      short loc_18000FEAE
0x18000fe94  lea     rcx, [rsi-8]
0x18000fe98  mov     rax, [rcx]
0x18000fe9b  mov     r8d, edi
0x18000fe9e  mov     rdx, [rsp+28h+ppstm]
0x18000fea3  mov     rax, [rax+18h]
0x18000fea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feac  mov     ebx, eax
0x18000feae  mov     rax, cs:WPP_GLOBAL_Control
0x18000feb5  mov     r8, [rax+38h]; unsigned __int64
0x18000feb9  test    r8, r8
0x18000febc  jz      short loc_18000FECC
0x18000febe  mov     r9b, 2; unsigned __int8
0x18000fec1  mov     edx, 0Eh; unsigned int
0x18000fec6  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000fecb  nop
0x18000fecc  mov     rcx, [rsp+28h+ppstm]
0x18000fed1  test    rcx, rcx
0x18000fed4  jz      short loc_18000FEE3
0x18000fed6  mov     rax, [rcx]
0x18000fed9  mov     rax, [rax+10h]
0x18000fedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee2  nop
0x18000fee3  mov     eax, ebx
0x18000fee5  mov     rbx, [rsp+28h+arg_0]
0x18000feea  mov     rsi, [rsp+28h+arg_8]
0x18000feef  add     rsp, 20h
0x18000fef3  pop     rdi
0x18000fef4  retn
```
