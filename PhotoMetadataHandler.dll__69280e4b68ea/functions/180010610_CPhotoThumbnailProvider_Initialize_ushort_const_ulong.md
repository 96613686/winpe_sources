# CPhotoThumbnailProvider::Initialize(ushort const *,ulong)

- ea: `0x180010610`
- end: `0x1800106cc`
- name: `?Initialize@CPhotoThumbnailProvider@@UEAAJPEBGK@Z`
- size: `188`
- prototype: `__int64 __fastcall(const struct _GUID *this, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010610`
- `0x18001186c`
- `0x180029010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180010658`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180010658`

## pseudocode

```c
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
0x180010610  mov     [rsp+arg_0], rbx
0x180010615  mov     [rsp+arg_8], rsi
0x18001061a  push    rdi
0x18001061b  sub     rsp, 20h
0x18001061f  mov     edi, r8d
0x180010622  mov     rbx, rdx
0x180010625  mov     rsi, rcx
0x180010628  mov     rax, cs:WPP_GLOBAL_Control
0x18001062f  mov     r8, [rax+38h]; unsigned __int64
0x180010633  test    r8, r8
0x180010636  jz      short loc_180010645
0x180010638  mov     r9b, 1; unsigned __int8
0x18001063b  mov     edx, 0Eh; unsigned int
0x180010640  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180010645  mov     [rsp+28h+ppstm], 0
0x18001064e  lea     r8, [rsp+28h+ppstm]; ppstm
0x180010653  mov     edx, edi; grfMode
0x180010655  mov     rcx, rbx; pszFile
0x180010658  call    cs:__imp_SHCreateStreamOnFileW
0x18001065f  nop     dword ptr [rax+rax+00h]
0x180010664  mov     ebx, eax
0x180010666  test    eax, eax
0x180010668  js      short loc_180010684
0x18001066a  lea     rcx, [rsi-8]
0x18001066e  mov     rax, [rcx]
0x180010671  mov     r8d, edi
0x180010674  mov     rdx, [rsp+28h+ppstm]
0x180010679  mov     rax, [rax+18h]
0x18001067d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010682  mov     ebx, eax
0x180010684  mov     rax, cs:WPP_GLOBAL_Control
0x18001068b  mov     r8, [rax+38h]; unsigned __int64
0x18001068f  test    r8, r8
0x180010692  jz      short loc_1800106A2
0x180010694  mov     r9b, 2; unsigned __int8
0x180010697  mov     edx, 0Eh; unsigned int
0x18001069c  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800106a1  nop
0x1800106a2  mov     rcx, [rsp+28h+ppstm]
0x1800106a7  test    rcx, rcx
0x1800106aa  jz      short loc_1800106B9
0x1800106ac  mov     rax, [rcx]
0x1800106af  mov     rax, [rax+10h]
0x1800106b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106b8  nop
0x1800106b9  mov     eax, ebx
0x1800106bb  mov     rbx, [rsp+28h+arg_0]
0x1800106c0  mov     rsi, [rsp+28h+arg_8]
0x1800106c5  add     rsp, 20h
0x1800106c9  pop     rdi
0x1800106ca  retn
```
