# GameInputClient::GameInputClient(IMMDeviceEnumerator *)

- ea: `0x180003b34`
- end: `0x180003cb8`
- name: `??0GameInputClient@@AEAA@PEAUIMMDeviceEnumerator@@@Z`
- size: `388`
- prototype: `GameInputClient *__fastcall(GameInputClient *__hidden this, struct IMMDeviceEnumerator *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000739c`

## callees

- `0x180003b34`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003c5e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003c5e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003c96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003c96`

## pseudocode

```c
GameInputClient *__fastcall GameInputClient::GameInputClient(GameInputClient *this, struct IMMDeviceEnumerator *a2)
{
  *(_QWORD *)this = &GameInputClient::`vftable';
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 11) = (char *)this + 80;
  *((_QWORD *)this + 10) = (char *)this + 80;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 14) = (char *)this + 104;
  *((_QWORD *)this + 13) = (char *)this + 104;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 17) = (char *)this + 128;
  *((_QWORD *)this + 16) = (char *)this + 128;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 21) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IMMDeviceEnumerator *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 26) = &GameInputDispatcher::`vftable';
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = -1;
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_BYTE *)this + 336) = 0;
  *((_WORD *)this + 172) = 0;
  *((_BYTE *)this + 346) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( byte_180069915 )
    GipRawDeviceIO::s_gipClientHandle = CreateFileW(L"\\\\.\\XboxGIP", 0xC0000000, 3u, 0, 3u, 0, 0);
  return this;
}

```

## disassembly

```asm
0x180003b34  mov     [rsp+arg_0], rbx
0x180003b39  push    rdi
0x180003b3a  sub     rsp, 40h
0x180003b3e  xor     edi, edi
0x180003b40  lea     rax, ??_7GameInputClient@@6B@; const GameInputClient::`vftable'
0x180003b47  mov     [rcx], rax
0x180003b4a  lea     rax, [rcx+50h]
0x180003b4e  mov     [rax+10h], edi
0x180003b51  mov     rbx, rcx
0x180003b54  mov     [rax+8], rax
0x180003b58  mov     [rax], rax
0x180003b5b  lea     rax, [rcx+68h]
0x180003b5f  mov     [rax+10h], edi
0x180003b62  mov     [rax+8], rax
0x180003b66  mov     [rax], rax
0x180003b69  lea     rax, [rcx+80h]
0x180003b70  mov     [rax+10h], edi
0x180003b73  mov     [rax+8], rax
0x180003b77  mov     [rax], rax
0x180003b7a  mov     [rcx+8], edi
0x180003b7d  mov     [rcx+10h], rdi
0x180003b81  mov     [rcx+18h], rdi
0x180003b85  mov     [rcx+20h], rdi
0x180003b89  mov     [rcx+98h], rdi
0x180003b90  mov     [rcx+0A0h], edi
0x180003b96  mov     [rcx+0A8h], rdx
0x180003b9d  test    rdx, rdx
0x180003ba0  jz      short loc_180003BB1
0x180003ba2  mov     rax, [rdx]
0x180003ba5  mov     rcx, rdx
0x180003ba8  mov     rax, [rax+8]
0x180003bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb1  mov     [rbx+0B0h], rdi
0x180003bb8  lea     rax, ??_7GameInputDispatcher@@6B@; const GameInputDispatcher::`vftable'
0x180003bbf  mov     [rbx+0B8h], rdi
0x180003bc6  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003bca  mov     [rbx+0C0h], rdi
0x180003bd1  mov     [rbx+0D8h], edi
0x180003bd7  mov     [rbx+0C8h], edi
0x180003bdd  mov     [rbx+0D0h], rax
0x180003be4  mov     [rbx+0E0h], rdi
0x180003beb  mov     [rbx+0E8h], rdi
0x180003bf2  mov     [rbx+100h], rdi
0x180003bf9  mov     [rbx+108h], rdi
0x180003c00  mov     qword ptr [rbx+110h], 0FFFFFFFFFFFFFFFFh
0x180003c0b  mov     [rbx+118h], edi
0x180003c11  mov     [rbx+0F0h], rdi
0x180003c18  mov     [rbx+0F8h], rdi
0x180003c1f  mov     [rbx+120h], rdi
0x180003c26  mov     [rbx+128h], rdi
0x180003c2d  mov     [rbx+130h], rdi
0x180003c34  mov     [rbx+138h], rdi
0x180003c3b  mov     [rbx+140h], rdi
0x180003c42  mov     [rbx+148h], rdi
0x180003c49  mov     [rbx+150h], dil
0x180003c50  mov     [rbx+158h], di
0x180003c57  mov     [rbx+15Ah], dil
0x180003c5e  call    cs:__imp_InitializeCriticalSection
0x180003c65  nop     dword ptr [rax+rax+00h]
0x180003c6a  cmp     cs:byte_180069915, dil
0x180003c71  jz      short loc_180003CA9
0x180003c73  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x180003c78  lea     rcx, FileName; "\\\\.\\XboxGIP"
0x180003c7f  mov     r8d, 3; dwShareMode
0x180003c85  mov     [rsp+48h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180003c89  xor     r9d, r9d; lpSecurityAttributes
0x180003c8c  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180003c91  mov     edx, 0C0000000h; dwDesiredAccess
0x180003c96  call    cs:__imp_CreateFileW
0x180003c9d  nop     dword ptr [rax+rax+00h]
0x180003ca2  mov     cs:?s_gipClientHandle@GipRawDeviceIO@@0PEAXEA, rax; void * GipRawDeviceIO::s_gipClientHandle
0x180003ca9  mov     rax, rbx
0x180003cac  mov     rbx, [rsp+48h+arg_0]
0x180003cb1  add     rsp, 40h
0x180003cb5  pop     rdi
0x180003cb6  retn
```
