# CDataReaderCoordinator::ReleaseResources(void)

- ea: `0x1800044b0`
- end: `0x18000456f`
- name: `?ReleaseResources@CDataReaderCoordinator@@QEAAXXZ`
- size: `191`
- prototype: `void __fastcall(CDataReaderCoordinator *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a5c`
- `0x180003a70`

## callees

- `0x1800044b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004508`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004508`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800044f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800044f4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004536`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004549`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004536`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004524`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004512`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004524`

## pseudocode

```c
void __fastcall CDataReaderCoordinator::ReleaseResources(CDataReaderCoordinator *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *((_DWORD *)this + 20) = 1;
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *(_QWORD *)this )
    SetEvent(*(HANDLE *)this);
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    WaitForSingleObject(v4, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = 0;
  }
  v5 = (void *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    LocalFree(v5);
    *((_QWORD *)this + 5) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 6);
  if ( v6 )
    LocalFree(v6);
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
}

```

## disassembly

```asm
0x1800044b0  mov     [rsp+arg_0], rbx
0x1800044b5  push    rdi
0x1800044b6  sub     rsp, 20h
0x1800044ba  mov     rbx, rcx
0x1800044bd  mov     dword ptr [rcx+50h], 1
0x1800044c4  mov     rcx, [rcx+10h]; hObject
0x1800044c8  xor     edi, edi
0x1800044ca  test    rcx, rcx
0x1800044cd  jz      short loc_1800044D9
0x1800044cf  call    cs:__imp_CloseHandle
0x1800044d5  mov     [rbx+10h], rdi
0x1800044d9  mov     rcx, [rbx+18h]; hObject
0x1800044dd  test    rcx, rcx
0x1800044e0  jz      short loc_1800044EC
0x1800044e2  call    cs:__imp_CloseHandle
0x1800044e8  mov     [rbx+18h], rdi
0x1800044ec  mov     rcx, [rbx]; hEvent
0x1800044ef  test    rcx, rcx
0x1800044f2  jz      short loc_1800044FA
0x1800044f4  call    cs:__imp_SetEvent
0x1800044fa  mov     rcx, [rbx+8]; hHandle
0x1800044fe  test    rcx, rcx
0x180004501  jz      short loc_18000451C
0x180004503  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180004508  call    cs:__imp_WaitForSingleObject
0x18000450e  mov     rcx, [rbx+8]; hObject
0x180004512  call    cs:__imp_CloseHandle
0x180004518  mov     [rbx+8], rdi
0x18000451c  mov     rcx, [rbx]; hObject
0x18000451f  test    rcx, rcx
0x180004522  jz      short loc_18000452D
0x180004524  call    cs:__imp_CloseHandle
0x18000452a  mov     [rbx], rdi
0x18000452d  mov     rcx, [rbx+28h]; hMem
0x180004531  test    rcx, rcx
0x180004534  jz      short loc_180004540
0x180004536  call    cs:__imp_LocalFree
0x18000453c  mov     [rbx+28h], rdi
0x180004540  mov     rcx, [rbx+30h]; hMem
0x180004544  test    rcx, rcx
0x180004547  jz      short loc_18000454F
0x180004549  call    cs:__imp_LocalFree
0x18000454f  xor     eax, eax
0x180004551  xorps   xmm0, xmm0
0x180004554  movups  xmmword ptr [rbx+28h], xmm0
0x180004558  mov     [rbx+38h], rax
0x18000455c  mov     [rbx+40h], rax
0x180004560  mov     [rbx+48h], rdi
0x180004564  mov     rbx, [rsp+28h+arg_0]
0x180004569  add     rsp, 20h
0x18000456d  pop     rdi
0x18000456e  retn
```
