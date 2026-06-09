# start_next_async_read

- ea: `0x1800bf1c0`
- end: `0x1800bf425`
- name: `start_next_async_read`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800bce30`

## callees

- `0x180006c00`
- `0x1800149c0`
- `0x1800bf1c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf2b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf3c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf3db`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf3f0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf2b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf3c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf3db`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bf3f0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bf396`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bf396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf3a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf3a0`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800bf250`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800bf250`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800bf2c7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800bf2c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bf296`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bf296`

## string_xrefs

- `0x1800bf2b8`: `CreateEvent failed`
- `0x1800bf3ab`: `Reading file truncated`
- `0x1800bf3f6`: `Read error`

## pseudocode

```c
__int64 __fastcall start_next_async_read(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 lpOverlapped; // rdi
  SIZE_T v8; // rbp
  LPVOID v9; // rax
  const char *v10; // r8
  __int64 v11; // rdx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  DWORD v21; // eax
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  v2 = *(_QWORD *)(a2 + 968) == 0;
  NumberOfBytesRead = 0;
  if ( v2 )
    return 1;
  v6 = *(int *)(a2 + 952);
  lpOverlapped = a2 + 80 * v6 + 984;
  *(_DWORD *)(a2 + 952) = ((int)v6 + 1) % 8;
  if ( *(_QWORD *)(lpOverlapped + 40) )
  {
    ResetEvent(*(HANDLE *)(lpOverlapped + 24));
  }
  else
  {
    v8 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(a2 + 888) + 16LL) - 1)
       + 0x10000LL
       - ((unsigned __int64)(unsigned int)(*(_DWORD *)(*(_QWORD *)(a2 + 888) + 16LL) - 1) + 0x10000)
       % *(unsigned int *)(*(_QWORD *)(a2 + 888) + 16LL);
    v9 = VirtualAlloc(0, v8, 0x1000u, 4u);
    if ( !v9 )
    {
      v10 = "Couldn't allocate memory";
      v11 = 12;
LABEL_6:
      archive_set_error(a1, v11, v10);
      result = 4294967266LL;
      *(_DWORD *)(a1 + 4) = 0x8000;
      return result;
    }
    *(_QWORD *)(lpOverlapped + 40) = v9;
    *(_QWORD *)(lpOverlapped + 48) = v8;
    *(_QWORD *)(lpOverlapped + 32) = a1;
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)(lpOverlapped + 24) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      _la_dosmaperr(LastError);
      v14 = (unsigned int *)_o__errno();
      v10 = "CreateEvent failed";
LABEL_9:
      v11 = *v14;
      goto LABEL_6;
    }
  }
  v15 = *(_QWORD *)(a2 + 864);
  v16 = *(unsigned int *)(lpOverlapped + 48);
  if ( v16 > *(_QWORD *)v15 )
    LODWORD(v16) = *(_DWORD *)v15;
  v17 = *(_QWORD *)(a2 + 976);
  if ( *(_QWORD *)(v15 + 8) > v17 )
    *(_QWORD *)(a2 + 968) += v17 - *(_QWORD *)(v15 + 8);
  v18 = *(_QWORD *)(v15 + 8);
  *(_QWORD *)(lpOverlapped + 56) = v18;
  *(_QWORD *)(lpOverlapped + 16) = v18;
  v19 = *(_QWORD *)(a2 + 968);
  if ( v19 <= (unsigned int)v16 )
  {
    *(_QWORD *)(lpOverlapped + 64) = v19;
    *(_QWORD *)(a2 + 968) = 0;
  }
  else
  {
    *(_QWORD *)(lpOverlapped + 64) = (unsigned int)v16;
    *(_QWORD *)(a2 + 968) -= (unsigned int)v16;
  }
  *(_QWORD *)(lpOverlapped + 72) = 0;
  *(_QWORD *)(*(_QWORD *)(a2 + 864) + 8LL) += (unsigned int)v16;
  **(_QWORD **)(a2 + 864) -= (unsigned int)v16;
  v20 = *(_QWORD **)(a2 + 864);
  *(_QWORD *)(a2 + 976) = v20[1];
  if ( !*v20 && *(__int64 *)(a2 + 968) > 0 )
    *(_QWORD *)(a2 + 864) = v20 + 2;
  if ( ReadFile(
         *(HANDLE *)(a2 + 920),
         *(LPVOID *)(lpOverlapped + 40),
         v16,
         &NumberOfBytesRead,
         (LPOVERLAPPED)lpOverlapped) )
  {
    *(_QWORD *)(lpOverlapped + 72) = NumberOfBytesRead;
  }
  else
  {
    v21 = GetLastError();
    if ( v21 == 38 )
    {
      v10 = "Reading file truncated";
      v11 = 0xFFFFFFFFLL;
      goto LABEL_6;
    }
    if ( v21 != 997 )
    {
      if ( v21 == 232 )
      {
        *(_DWORD *)_o__errno() = 11;
      }
      else if ( v21 == 5 )
      {
        *(_DWORD *)_o__errno() = 9;
      }
      else
      {
        _la_dosmaperr(v21);
      }
      v14 = (unsigned int *)_o__errno();
      v10 = "Read error";
      goto LABEL_9;
    }
  }
  ++*(_DWORD *)(a2 + 960);
  return *(_QWORD *)(a2 + 968) == 0;
}

```

## disassembly

```asm
0x1800bf1c0  push    rbx
0x1800bf1c2  push    rbp
0x1800bf1c3  push    rsi
0x1800bf1c4  push    rdi
0x1800bf1c5  sub     rsp, 38h
0x1800bf1c9  cmp     qword ptr [rdx+3C8h], 0
0x1800bf1d1  mov     rbx, rdx
0x1800bf1d4  mov     rsi, rcx
0x1800bf1d7  mov     [rsp+58h+NumberOfBytesRead], 0
0x1800bf1df  jnz     short loc_1800BF1EB
0x1800bf1e1  mov     eax, 1
0x1800bf1e6  jmp     loc_1800BF41C
0x1800bf1eb  movsxd  rdx, dword ptr [rdx+3B8h]
0x1800bf1f2  mov     ecx, 8
0x1800bf1f7  lea     rdi, [rdx+rdx*4]
0x1800bf1fb  lea     eax, [rdx+1]
0x1800bf1fe  shl     rdi, 4
0x1800bf202  cdq
0x1800bf203  add     rdi, 3D8h
0x1800bf20a  idiv    ecx
0x1800bf20c  add     rdi, rbx
0x1800bf20f  mov     [rbx+3B8h], edx
0x1800bf215  cmp     qword ptr [rdi+28h], 0
0x1800bf21a  jnz     loc_1800BF2C3
0x1800bf220  mov     rax, [rbx+378h]
0x1800bf227  lea     r9d, [rcx-4]; flProtect
0x1800bf22b  xor     edx, edx
0x1800bf22d  xor     ecx, ecx; lpAddress
0x1800bf22f  mov     r8d, [rax+10h]
0x1800bf233  lea     ebp, [r8-1]
0x1800bf237  add     rbp, 10000h
0x1800bf23e  mov     rax, rbp
0x1800bf241  div     r8
0x1800bf244  mov     r8d, 1000h; flAllocationType
0x1800bf24a  sub     rbp, rdx
0x1800bf24d  mov     rdx, rbp; dwSize
0x1800bf250  call    cs:__imp_VirtualAlloc
0x1800bf256  test    rax, rax
0x1800bf259  jnz     short loc_1800BF27E
0x1800bf25b  lea     r8, aCouldnTAllocat_1; "Couldn't allocate memory"
0x1800bf262  lea     edx, [rax+0Ch]
0x1800bf265  mov     rcx, rsi
0x1800bf268  call    archive_set_error
0x1800bf26d  mov     eax, 0FFFFFFE2h
0x1800bf272  mov     dword ptr [rsi+4], 8000h
0x1800bf279  jmp     loc_1800BF41C
0x1800bf27e  xor     r9d, r9d; lpName
0x1800bf281  mov     [rdi+28h], rax
0x1800bf285  xor     r8d, r8d; bInitialState
0x1800bf288  mov     [rdi+30h], rbp
0x1800bf28c  xor     ecx, ecx; lpEventAttributes
0x1800bf28e  mov     [rdi+20h], rsi
0x1800bf292  lea     edx, [r9+1]; bManualReset
0x1800bf296  call    cs:__imp_CreateEventW
0x1800bf29c  mov     [rdi+18h], rax
0x1800bf2a0  test    rax, rax
0x1800bf2a3  jnz     short loc_1800BF2CD
0x1800bf2a5  call    cs:__imp_GetLastError
0x1800bf2ab  mov     ecx, eax
0x1800bf2ad  call    __la_dosmaperr
0x1800bf2b2  call    cs:__imp__o__errno
0x1800bf2b8  lea     r8, aCreateeventFai; "CreateEvent failed"
0x1800bf2bf  mov     edx, [rax]
0x1800bf2c1  jmp     short loc_1800BF265
0x1800bf2c3  mov     rcx, [rdi+18h]; hEvent
0x1800bf2c7  call    cs:__imp_ResetEvent
0x1800bf2cd  mov     rcx, [rbx+360h]
0x1800bf2d4  mov     r8d, [rdi+30h]
0x1800bf2d8  cmp     r8, [rcx]
0x1800bf2db  jle     short loc_1800BF2E0
0x1800bf2dd  mov     r8d, [rcx]; nNumberOfBytesToRead
0x1800bf2e0  mov     rax, [rbx+3D0h]
0x1800bf2e7  cmp     [rcx+8], rax
0x1800bf2eb  jle     short loc_1800BF2F8
0x1800bf2ed  sub     rax, [rcx+8]
0x1800bf2f1  add     [rbx+3C8h], rax
0x1800bf2f8  mov     rcx, [rcx+8]
0x1800bf2fc  mov     [rdi+38h], rcx
0x1800bf300  mov     eax, ecx
0x1800bf302  mov     [rdi+10h], ecx
0x1800bf305  sar     rcx, 20h
0x1800bf309  mov     [rdi+14h], ecx
0x1800bf30c  mov     rax, [rbx+3C8h]
0x1800bf313  mov     ecx, r8d
0x1800bf316  cmp     rax, rcx
0x1800bf319  jle     short loc_1800BF328
0x1800bf31b  mov     [rdi+40h], rcx
0x1800bf31f  sub     [rbx+3C8h], rcx
0x1800bf326  jmp     short loc_1800BF337
0x1800bf328  mov     [rdi+40h], rax
0x1800bf32c  mov     qword ptr [rbx+3C8h], 0
0x1800bf337  mov     qword ptr [rdi+48h], 0
0x1800bf33f  mov     rax, [rbx+360h]
0x1800bf346  add     [rax+8], rcx
0x1800bf34a  mov     rax, [rbx+360h]
0x1800bf351  sub     [rax], rcx
0x1800bf354  mov     rcx, [rbx+360h]
0x1800bf35b  mov     rax, [rcx+8]
0x1800bf35f  mov     [rbx+3D0h], rax
0x1800bf366  cmp     qword ptr [rcx], 0
0x1800bf36a  jnz     short loc_1800BF381
0x1800bf36c  cmp     qword ptr [rbx+3C8h], 0
0x1800bf374  jle     short loc_1800BF381
0x1800bf376  lea     rax, [rcx+10h]
0x1800bf37a  mov     [rbx+360h], rax
0x1800bf381  mov     rdx, [rdi+28h]; lpBuffer
0x1800bf385  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800bf38a  mov     rcx, [rbx+398h]; hFile
0x1800bf391  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x1800bf396  call    cs:__imp_ReadFile
0x1800bf39c  test    eax, eax
0x1800bf39e  jnz     short loc_1800BF402
0x1800bf3a0  call    cs:__imp_GetLastError
0x1800bf3a6  cmp     eax, 26h ; '&'
0x1800bf3a9  jnz     short loc_1800BF3BA
0x1800bf3ab  lea     r8, aReadingFileTru; "Reading file truncated"
0x1800bf3b2  or      edx, 0FFFFFFFFh
0x1800bf3b5  jmp     loc_1800BF265
0x1800bf3ba  cmp     eax, 3E5h
0x1800bf3bf  jz      short loc_1800BF40A
0x1800bf3c1  cmp     eax, 0E8h
0x1800bf3c6  jnz     short loc_1800BF3D6
0x1800bf3c8  call    cs:__imp__o__errno
0x1800bf3ce  mov     dword ptr [rax], 0Bh
0x1800bf3d4  jmp     short loc_1800BF3F0
0x1800bf3d6  cmp     eax, 5
0x1800bf3d9  jnz     short loc_1800BF3E9
0x1800bf3db  call    cs:__imp__o__errno
0x1800bf3e1  mov     dword ptr [rax], 9
0x1800bf3e7  jmp     short loc_1800BF3F0
0x1800bf3e9  mov     ecx, eax
0x1800bf3eb  call    __la_dosmaperr
0x1800bf3f0  call    cs:__imp__o__errno
0x1800bf3f6  lea     r8, aReadError; "Read error"
0x1800bf3fd  jmp     loc_1800BF2BF
0x1800bf402  mov     eax, [rsp+58h+NumberOfBytesRead]
0x1800bf406  mov     [rdi+48h], rax
0x1800bf40a  inc     dword ptr [rbx+3C0h]
0x1800bf410  xor     eax, eax
0x1800bf412  cmp     [rbx+3C8h], rax
0x1800bf419  setz    al
0x1800bf41c  add     rsp, 38h
0x1800bf420  pop     rdi
0x1800bf421  pop     rsi
0x1800bf422  pop     rbp
0x1800bf423  pop     rbx
0x1800bf424  retn
```
