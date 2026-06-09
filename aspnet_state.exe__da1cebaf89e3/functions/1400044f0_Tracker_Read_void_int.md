# Tracker::Read(void *,int)

- ea: `0x1400044f0`
- end: `0x140004638`
- name: `?Read@Tracker@@QEAAJPEAXH@Z`
- size: `328`
- prototype: `__int64 __fastcall(Tracker *this, CHAR *, ULONG)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400017ac`

## callees

- `0x140003518`
- `0x1400044f0`
- `0x140004638`
- `0x140004ab8`
- `0x140004b0c`
- `0x140004f90`
- `0x1400055e0`
- `0x140006590`

## import_xrefs

- `WS2_32!WSARecv` at `0x1400045b0`
- `WS2_32!WSARecv` at `0x1400045b0`
- `WS2_32!__imp_WSAGetLastError` at `0x1400045bb`
- `WS2_32!__imp_WSAGetLastError` at `0x1400045bb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000457d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000457d`

## string_xrefs

- `0x140004610`: `Tracker::Read`

## pseudocode

```c
__int64 __fastcall Tracker::Read(Tracker *this, CHAR *a2, ULONG a3)
{
  unsigned int v4; // ebx
  TrackerCompletion *v7; // rax
  TrackerCompletion *v8; // rax
  struct IUnknown *v9; // rdi
  int v10; // edx
  int Error; // ebp
  _WSABUF Buffers; // [rsp+40h] [rbp-28h] BYREF
  DWORD Flags; // [rsp+70h] [rbp+8h] BYREF
  DWORD NumberOfBytesRecvd; // [rsp+88h] [rbp+20h] BYREF

  *((_QWORD *)this + 4) = Tracker::ProcessReading;
  v4 = 0;
  v7 = (TrackerCompletion *)MemAllocClear(0x40u);
  if ( !v7 )
  {
    v9 = 0;
    goto LABEL_9;
  }
  v8 = TrackerCompletion::TrackerCompletion(v7, this);
  v9 = (struct IUnknown *)v8;
  if ( !v8 )
  {
LABEL_9:
    v4 = -2147024882;
    goto LABEL_10;
  }
  (*(void (__fastcall **)(TrackerCompletion *))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = *((_DWORD *)this + 54);
  Buffers.len = a3;
  Buffers.buf = a2;
  NumberOfBytesRecvd = 0;
  Flags = 0;
  TrackerList::SetExpire(Tracker::s_pTrackerList, v10);
  GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 220));
  if ( WSARecv(*((_QWORD *)this + 6), &Buffers, 1u, &NumberOfBytesRecvd, &Flags, (LPWSAOVERLAPPED)&v9[1], 0) == -1 )
  {
    Error = WSAGetLastError();
    if ( Error != 997 )
    {
      TrackerList::SetNoExpire(Tracker::s_pTrackerList, *((_DWORD *)this + 54));
      *((_QWORD *)this + 4) = 0;
      ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
      v4 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v4 = Error;
    }
  }
LABEL_10:
  ReleaseInterface(v9);
  Tracker::RecordProcessError(this, v4, L"Tracker::Read");
  return v4;
}

```

## disassembly

```asm
0x1400044f0  mov     [rsp+arg_8], rbx
0x1400044f5  mov     [rsp+arg_10], rbp
0x1400044fa  push    rsi
0x1400044fb  push    rdi
0x1400044fc  push    r14
0x1400044fe  sub     rsp, 50h
0x140004502  lea     rax, ?ProcessReading@Tracker@@AEAAJJH@Z; Tracker::ProcessReading(long,int)
0x140004509  mov     rsi, rcx
0x14000450c  mov     [rcx+20h], rax
0x140004510  xor     ebx, ebx
0x140004512  mov     ebp, r8d
0x140004515  mov     r14, rdx
0x140004518  lea     ecx, [rbx+40h]; unsigned __int64
0x14000451b  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140004520  test    rax, rax
0x140004523  jz      loc_140004600
0x140004529  mov     rdx, rsi; struct Tracker *
0x14000452c  mov     rcx, rax; this
0x14000452f  call    ??0TrackerCompletion@@QEAA@PEAVTracker@@@Z; TrackerCompletion::TrackerCompletion(Tracker *)
0x140004534  mov     rdi, rax
0x140004537  test    rax, rax
0x14000453a  jz      loc_140004603
0x140004540  mov     rax, [rax]
0x140004543  mov     rcx, rdi
0x140004546  mov     rax, [rax+8]
0x14000454a  call    cs:__guard_dispatch_icall_fptr
0x140004550  mov     edx, [rsi+0D8h]; int
0x140004556  mov     rcx, cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA; this
0x14000455d  mov     [rsp+68h+Buffers.len], ebp
0x140004561  mov     [rsp+68h+Buffers.buf], r14
0x140004566  mov     [rsp+68h+NumberOfBytesRecvd], ebx
0x14000456d  mov     [rsp+68h+Flags], ebx
0x140004571  call    ?SetExpire@TrackerList@@QEAAXH@Z; TrackerList::SetExpire(int)
0x140004576  lea     rcx, [rsi+0DCh]; lpSystemTimeAsFileTime
0x14000457d  call    cs:__imp_GetSystemTimeAsFileTime
0x140004583  mov     rcx, [rsi+30h]; s
0x140004587  lea     rax, [rdi+8]
0x14000458b  mov     [rsp+68h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x140004590  lea     r9, [rsp+68h+NumberOfBytesRecvd]; lpNumberOfBytesRecvd
0x140004598  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x14000459d  lea     r8d, [rbx+1]; dwBufferCount
0x1400045a1  lea     rax, [rsp+68h+Flags]
0x1400045a6  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x1400045ab  mov     [rsp+68h+lpFlags], rax; lpFlags
0x1400045b0  call    cs:__imp_WSARecv
0x1400045b6  cmp     eax, 0FFFFFFFFh
0x1400045b9  jnz     short loc_140004608
0x1400045bb  call    cs:__imp_WSAGetLastError
0x1400045c1  mov     ebp, eax
0x1400045c3  cmp     eax, 3E5h
0x1400045c8  jz      short loc_140004608
0x1400045ca  mov     edx, [rsi+0D8h]; int
0x1400045d0  mov     rcx, cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA; this
0x1400045d7  call    ?SetNoExpire@TrackerList@@QEAA_NH@Z; TrackerList::SetNoExpire(int)
0x1400045dc  mov     [rsi+20h], rbx
0x1400045e0  mov     rcx, rdi
0x1400045e3  mov     rax, [rdi]
0x1400045e6  mov     rax, [rax+10h]
0x1400045ea  call    cs:__guard_dispatch_icall_fptr
0x1400045f0  movzx   ebx, bp
0x1400045f3  or      ebx, 80070000h
0x1400045f9  test    ebp, ebp
0x1400045fb  cmovle  ebx, ebp
0x1400045fe  jmp     short loc_140004608
0x140004600  mov     rdi, rbx
0x140004603  mov     ebx, 8007000Eh
0x140004608  mov     rcx, rdi; struct IUnknown *
0x14000460b  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x140004610  lea     r8, aTrackerRead; "Tracker::Read"
0x140004617  mov     edx, ebx; int
0x140004619  mov     rcx, rsi; this
0x14000461c  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x140004621  lea     r11, [rsp+68h+var_18]
0x140004626  mov     eax, ebx
0x140004628  mov     rbx, [r11+28h]
0x14000462c  mov     rbp, [r11+30h]
0x140004630  mov     rsp, r11
0x140004633  pop     r14
0x140004635  pop     rdi
0x140004636  pop     rsi
0x140004637  retn
```
