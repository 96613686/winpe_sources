# CreateStatusObjects

- ea: `0x18001bd74`
- end: `0x18001be24`
- name: `CreateStatusObjects`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x18001cc8c`

## callees

- `0x18001bd74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bde8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001be09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001bde8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001be09`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001bd99`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001bd99`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001bdc7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001bdc7`

## string_xrefs

- `0x18001bdd3`: `WinSAT.Status.Update`
- `0x18001bdf4`: `WinSAT.Status.Read`

## pseudocode

```c
__int64 CreateStatusObjects()
{
  HANDLE FileMappingW; // rax

  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x80Cu, L"WinSAT.SharedMemory");
  qword_18004FFA0 = FileMappingW;
  if ( FileMappingW )
  {
    Src = MapViewOfFile(FileMappingW, 4u, 0, 0, 0x80Cu);
    qword_18004FFE0 = CreateEventW(0, 0, 0, L"WinSAT.Status.Update");
    hEvent = CreateEventW(0, 0, 0, L"WinSAT.Status.Read");
  }
  return 0;
}

```

## disassembly

```asm
0x18001bd74  sub     rsp, 38h
0x18001bd78  xor     r9d, r9d; dwMaximumSizeHigh
0x18001bd7b  lea     rax, Name; "WinSAT.SharedMemory"
0x18001bd82  mov     [rsp+38h+lpName], rax; lpName
0x18001bd87  xor     edx, edx; lpFileMappingAttributes
0x18001bd89  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001bd8d  mov     [rsp+38h+dwMaximumSizeLow], 80Ch; dwMaximumSizeLow
0x18001bd95  lea     r8d, [r9+4]; flProtect
0x18001bd99  call    cs:__imp_CreateFileMappingW
0x18001bda0  nop     dword ptr [rax+rax+00h]
0x18001bda5  mov     cs:qword_18004FFA0, rax
0x18001bdac  test    rax, rax
0x18001bdaf  jz      short loc_18001BE1C
0x18001bdb1  xor     r9d, r9d; dwFileOffsetLow
0x18001bdb4  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 80Ch; dwNumberOfBytesToMap
0x18001bdbd  xor     r8d, r8d; dwFileOffsetHigh
0x18001bdc0  mov     rcx, rax; hFileMappingObject
0x18001bdc3  lea     edx, [r9+4]; dwDesiredAccess
0x18001bdc7  call    cs:__imp_MapViewOfFile
0x18001bdce  nop     dword ptr [rax+rax+00h]
0x18001bdd3  lea     r9, aWinsatStatusUp; "WinSAT.Status.Update"
0x18001bdda  xor     r8d, r8d; bInitialState
0x18001bddd  xor     edx, edx; bManualReset
0x18001bddf  mov     cs:Src, rax
0x18001bde6  xor     ecx, ecx; lpEventAttributes
0x18001bde8  call    cs:__imp_CreateEventW
0x18001bdef  nop     dword ptr [rax+rax+00h]
0x18001bdf4  lea     r9, aWinsatStatusRe; "WinSAT.Status.Read"
0x18001bdfb  xor     r8d, r8d; bInitialState
0x18001bdfe  xor     edx, edx; bManualReset
0x18001be00  mov     cs:qword_18004FFE0, rax
0x18001be07  xor     ecx, ecx; lpEventAttributes
0x18001be09  call    cs:__imp_CreateEventW
0x18001be10  nop     dword ptr [rax+rax+00h]
0x18001be15  mov     cs:hEvent, rax
0x18001be1c  xor     eax, eax
0x18001be1e  add     rsp, 38h
0x18001be22  retn
```
