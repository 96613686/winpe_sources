# AsyncPipe::Connect(ushort const *,IAsyncPipeCallback *)

- ea: `0x14000d490`
- end: `0x14000d5ab`
- name: `?Connect@AsyncPipe@@QEAAJPEBGPEAUIAsyncPipeCallback@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(Synchronizer **this, LPCWSTR lpFileName, struct IAsyncPipeCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000a4a0`

## callees

- `0x14000d490`
- `0x14000e1b4`
- `0x14000e4cc`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d552`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000d4cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000d4cf`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x14000d538`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x14000d538`

## string_xrefs

- `0x14000d4fd`: `CreateFile`

## pseudocode

```c
__int64 __fastcall AsyncPipe::Connect(Synchronizer **this, LPCWSTR lpFileName, struct IAsyncPipeCallback *a3)
{
  HANDLE FileW; // rax
  void *v6; // rbx
  DWORD LastError; // eax
  int v8; // ebx
  DWORD v9; // eax
  const char *v10; // rcx
  DWORD v12; // eax
  const char *v13; // rcx
  void *dwFlagsAndAttributes; // [rsp+28h] [rbp-20h]
  DWORD Mode; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 3u, 0x40010000u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 2 )
      return (unsigned __int16)v8 | 0x80070000;
    if ( LastError == 231 )
      return (unsigned __int16)v8 | 0x80070000;
    if ( LastError == 5 )
      return (unsigned __int16)v8 | 0x80070000;
    v9 = GetLastError();
    __FatalError(v10, 0x77u, "CreateFile", v9);
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return (unsigned int)v8;
  }
  else
  {
    Mode = 2;
    if ( !SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
      v12 = GetLastError();
      if ( v12 == 233 )
      {
        CloseHandle(v6);
        return 2147942633LL;
      }
      __FatalError(v13, 0x83u, "SetNamedPipeHandleState", v12);
    }
    (*(void (__fastcall **)(struct IAsyncPipeCallback *))(*(_QWORD *)a3 + 8LL))(a3);
    Synchronizer::EnqueueEvent(this[1], (struct SynchronizedObject *)this, 0, v6, a3, dwFlagsAndAttributes);
    return 0;
  }
}

```

## disassembly

```asm
0x14000d490  mov     [rsp+arg_0], rbx
0x14000d495  mov     [rsp+arg_8], rsi
0x14000d49a  push    rdi
0x14000d49b  sub     rsp, 40h
0x14000d49f  mov     rax, rdx
0x14000d4a2  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14000d4ab  mov     rdi, r8
0x14000d4ae  mov     dword ptr [rsp+48h+dwFlagsAndAttributes], 40010000h; void *
0x14000d4b6  mov     rsi, rcx
0x14000d4b9  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14000d4c1  mov     rcx, rax; lpFileName
0x14000d4c4  xor     r9d, r9d; lpSecurityAttributes
0x14000d4c7  xor     r8d, r8d; dwShareMode
0x14000d4ca  mov     edx, 0C0000000h; dwDesiredAccess
0x14000d4cf  call    cs:__imp_CreateFileW
0x14000d4d5  mov     rbx, rax
0x14000d4d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d4dc  jnz     short loc_14000D522
0x14000d4de  call    cs:__imp_GetLastError
0x14000d4e4  mov     ebx, eax
0x14000d4e6  cmp     eax, 2
0x14000d4e9  jz      short loc_14000D515
0x14000d4eb  cmp     eax, 0E7h
0x14000d4f0  jz      short loc_14000D515
0x14000d4f2  cmp     eax, 5
0x14000d4f5  jz      short loc_14000D515
0x14000d4f7  call    cs:__imp_GetLastError
0x14000d4fd  lea     r8, aCreatefile; "CreateFile"
0x14000d504  mov     edx, 77h ; 'w'; unsigned int
0x14000d509  mov     r9d, eax; unsigned int
0x14000d50c  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d511  test    ebx, ebx
0x14000d513  jle     short loc_14000D51E
0x14000d515  movzx   ebx, bx
0x14000d518  or      ebx, 80070000h
0x14000d51e  mov     eax, ebx
0x14000d520  jmp     short loc_14000D59B
0x14000d522  xor     r9d, r9d; lpCollectDataTimeout
0x14000d525  mov     [rsp+48h+Mode], 2
0x14000d52d  xor     r8d, r8d; lpMaxCollectionCount
0x14000d530  lea     rdx, [rsp+48h+Mode]; lpMode
0x14000d535  mov     rcx, rbx; hNamedPipe
0x14000d538  call    cs:__imp_SetNamedPipeHandleState
0x14000d53e  test    eax, eax
0x14000d540  jnz     short loc_14000D573
0x14000d542  call    cs:__imp_GetLastError
0x14000d548  cmp     eax, 0E9h
0x14000d54d  jnz     short loc_14000D55F
0x14000d54f  mov     rcx, rbx; hObject
0x14000d552  call    cs:__imp_CloseHandle
0x14000d558  mov     eax, 800700E9h
0x14000d55d  jmp     short loc_14000D59B
0x14000d55f  mov     r9d, eax; unsigned int
0x14000d562  lea     r8, aSetnamedpipeha; "SetNamedPipeHandleState"
0x14000d569  mov     edx, 83h; unsigned int
0x14000d56e  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d573  mov     rax, [rdi]
0x14000d576  mov     rcx, rdi
0x14000d579  mov     rax, [rax+8]
0x14000d57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d582  mov     rcx, [rsi+8]; this
0x14000d586  mov     r9, rbx; void *
0x14000d589  xor     r8d, r8d; int
0x14000d58c  mov     qword ptr [rsp+48h+dwCreationDisposition], rdi; void *
0x14000d591  mov     rdx, rsi; struct SynchronizedObject *
0x14000d594  call    ?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z; Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)
0x14000d599  xor     eax, eax
0x14000d59b  mov     rbx, [rsp+48h+arg_0]
0x14000d5a0  mov     rsi, [rsp+48h+arg_8]
0x14000d5a5  add     rsp, 40h
0x14000d5a9  pop     rdi
0x14000d5aa  retn
```
