# BufferWriter::CAsyncIO::CAsyncIO(long *)

- ea: `0x1800a45b4`
- end: `0x1800a465e`
- name: `??0CAsyncIO@BufferWriter@@QEAA@PEAJ@Z`
- size: `170`
- prototype: `__int64 __fastcall(BufferWriter::CAsyncIO *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a4c74`

## callees

- `0x1800a45b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a45da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a4608`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a45da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a4608`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a4620`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a4620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4635`

## pseudocode

```c
BufferWriter::CAsyncIO *__fastcall BufferWriter::CAsyncIO::CAsyncIO(BufferWriter::CAsyncIO *this, int *a2)
{
  HANDLE EventW; // rax
  signed int LastError; // eax

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &BufferWriter::CAsyncIO::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)this + 9) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *a2 = LastError;
  }
  return this;
}

```

## disassembly

```asm
0x1800a45b4  mov     [rsp+arg_0], rbx
0x1800a45b9  push    rdi
0x1800a45ba  sub     rsp, 20h
0x1800a45be  lea     rax, ??_7CAsyncIO@BufferWriter@@6B@; const BufferWriter::CAsyncIO::`vftable'
0x1800a45c5  mov     qword ptr [rcx+8], 0
0x1800a45cd  mov     [rcx], rax
0x1800a45d0  mov     rbx, rcx
0x1800a45d3  add     rcx, 10h; lpCriticalSection
0x1800a45d7  mov     rdi, rdx
0x1800a45da  call    cs:__imp_InitializeCriticalSection
0x1800a45e1  nop     dword ptr [rax+rax+00h]
0x1800a45e6  mov     dword ptr [rbx+38h], 0
0x1800a45ed  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800a45f1  mov     qword ptr [rbx+40h], 0
0x1800a45f9  mov     qword ptr [rbx+48h], 0
0x1800a4601  mov     dword ptr [rbx+50h], 0
0x1800a4608  call    cs:__imp_InitializeCriticalSection
0x1800a460f  nop     dword ptr [rax+rax+00h]
0x1800a4614  xor     r9d, r9d; lpName
0x1800a4617  xor     ecx, ecx; lpEventAttributes
0x1800a4619  lea     edx, [r9+1]; bManualReset
0x1800a461d  mov     r8d, edx; bInitialState
0x1800a4620  call    cs:__imp_CreateEventW
0x1800a4627  nop     dword ptr [rax+rax+00h]
0x1800a462c  mov     [rbx+48h], rax
0x1800a4630  test    rax, rax
0x1800a4633  jnz     short loc_1800A464F
0x1800a4635  call    cs:__imp_GetLastError
0x1800a463c  nop     dword ptr [rax+rax+00h]
0x1800a4641  test    eax, eax
0x1800a4643  jle     short loc_1800A464D
0x1800a4645  movzx   eax, ax
0x1800a4648  or      eax, 80070000h
0x1800a464d  mov     [rdi], eax
0x1800a464f  mov     rax, rbx
0x1800a4652  mov     rbx, [rsp+28h+arg_0]
0x1800a4657  add     rsp, 20h
0x1800a465b  pop     rdi
0x1800a465c  retn
```
