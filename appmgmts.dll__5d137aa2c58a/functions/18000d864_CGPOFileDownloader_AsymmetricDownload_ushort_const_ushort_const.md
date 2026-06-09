# CGPOFileDownloader::AsymmetricDownload(ushort const *,ushort const *)

- ea: `0x18000d864`
- end: `0x18000d948`
- name: `?AsymmetricDownload@CGPOFileDownloader@@QEAAKPEBG0@Z`
- size: `228`
- prototype: `__int64 __fastcall(CGPOFileDownloader *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005cec`

## callees

- `0x18000d864`
- `0x18000d950`
- `0x18000da3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d90b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d922`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d90b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d898`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d898`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d937`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d937`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d8b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d8b7`

## pseudocode

```c
__int64 __fastcall CGPOFileDownloader::AsymmetricDownload(
        CGPOFileDownloader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  bool v3; // zf
  HLOCAL v7; // rax
  DWORD LastError; // edi
  HANDLE EventW; // rax
  unsigned int v10; // eax
  void *v11; // rcx
  void *v12; // rcx

  v3 = *(_QWORD *)this == 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 14) = 0;
  if ( v3 )
  {
    v7 = LocalAlloc(0, 0xF000u);
    *(_QWORD *)this = v7;
    if ( !v7 )
    {
      LastError = 14;
LABEL_6:
      LocalFree(*(HLOCAL *)this);
      *(_QWORD *)this = 0;
      return LastError;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 5) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_6;
    }
  }
  LastError = CGPOFileDownloader::GetEndpointFiles(this, a2, a3);
  if ( !LastError )
  {
    v10 = CGPOFileDownloader::PerformDownload(this);
    v11 = (void *)*((_QWORD *)this + 4);
    LastError = v10;
    if ( v11 )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 4) = 0;
    }
    v12 = (void *)*((_QWORD *)this + 3);
    if ( v12 )
    {
      CloseHandle(v12);
      *((_QWORD *)this + 3) = 0;
    }
    if ( LastError )
      DeleteFileW(a3);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d864  push    rbx
0x18000d866  push    rbp
0x18000d867  push    rsi
0x18000d868  push    rdi
0x18000d869  sub     rsp, 28h
0x18000d86d  cmp     qword ptr [rcx], 0
0x18000d871  mov     rsi, r8
0x18000d874  mov     rbp, rdx
0x18000d877  mov     dword ptr [rcx+30h], 0
0x18000d87e  mov     rbx, rcx
0x18000d881  mov     dword ptr [rcx+8], 0
0x18000d888  mov     dword ptr [rcx+38h], 0
0x18000d88f  jnz     short loc_18000D8E4
0x18000d891  mov     edx, 0F000h; uBytes
0x18000d896  xor     ecx, ecx; uFlags
0x18000d898  call    cs:__imp_LocalAlloc
0x18000d89e  mov     [rbx], rax
0x18000d8a1  test    rax, rax
0x18000d8a4  jnz     short loc_18000D8AB
0x18000d8a6  lea     edi, [rax+0Eh]
0x18000d8a9  jmp     short loc_18000D8D2
0x18000d8ab  xor     r9d, r9d; lpName
0x18000d8ae  xor     r8d, r8d; bInitialState
0x18000d8b1  xor     ecx, ecx; lpEventAttributes
0x18000d8b3  lea     edx, [r9+1]; bManualReset
0x18000d8b7  call    cs:__imp_CreateEventW
0x18000d8bd  mov     [rbx+28h], rax
0x18000d8c1  test    rax, rax
0x18000d8c4  jnz     short loc_18000D8E4
0x18000d8c6  call    cs:__imp_GetLastError
0x18000d8cc  mov     edi, eax
0x18000d8ce  test    eax, eax
0x18000d8d0  jz      short loc_18000D8E4
0x18000d8d2  mov     rcx, [rbx]; hMem
0x18000d8d5  call    cs:__imp_LocalFree
0x18000d8db  mov     qword ptr [rbx], 0
0x18000d8e2  jmp     short loc_18000D93D
0x18000d8e4  mov     r8, rsi; unsigned __int16 *
0x18000d8e7  mov     rdx, rbp; unsigned __int16 *
0x18000d8ea  mov     rcx, rbx; this
0x18000d8ed  call    ?GetEndpointFiles@CGPOFileDownloader@@AEAAKPEBG0@Z; CGPOFileDownloader::GetEndpointFiles(ushort const *,ushort const *)
0x18000d8f2  mov     edi, eax
0x18000d8f4  test    eax, eax
0x18000d8f6  jnz     short loc_18000D93D
0x18000d8f8  mov     rcx, rbx; this
0x18000d8fb  call    ?PerformDownload@CGPOFileDownloader@@AEAAKXZ; CGPOFileDownloader::PerformDownload(void)
0x18000d900  mov     rcx, [rbx+20h]; hObject
0x18000d904  mov     edi, eax
0x18000d906  test    rcx, rcx
0x18000d909  jz      short loc_18000D919
0x18000d90b  call    cs:__imp_CloseHandle
0x18000d911  mov     qword ptr [rbx+20h], 0
0x18000d919  mov     rcx, [rbx+18h]; hObject
0x18000d91d  test    rcx, rcx
0x18000d920  jz      short loc_18000D930
0x18000d922  call    cs:__imp_CloseHandle
0x18000d928  mov     qword ptr [rbx+18h], 0
0x18000d930  test    edi, edi
0x18000d932  jz      short loc_18000D93D
0x18000d934  mov     rcx, rsi; lpFileName
0x18000d937  call    cs:__imp_DeleteFileW
0x18000d93d  mov     eax, edi
0x18000d93f  add     rsp, 28h
0x18000d943  pop     rdi
0x18000d944  pop     rsi
0x18000d945  pop     rbp
0x18000d946  pop     rbx
0x18000d947  retn
```
