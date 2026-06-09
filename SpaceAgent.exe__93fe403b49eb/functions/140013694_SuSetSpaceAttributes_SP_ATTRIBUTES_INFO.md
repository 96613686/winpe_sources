# SuSetSpaceAttributes(_SP_ATTRIBUTES_INFO *)

- ea: `0x140013694`
- end: `0x1400137e1`
- name: `?SuSetSpaceAttributes@@YAHPEAU_SP_ATTRIBUTES_INFO@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct _SP_ATTRIBUTES_INFO *lpInBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400166f8`
- `0x140016d64`

## callees

- `0x14000b39c`
- `0x140013694`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140013714`
- `KERNEL32!CreateEventW` at `0x140013714`
- `KERNEL32!CloseHandle` at `0x1400137c4`
- `KERNEL32!CloseHandle` at `0x1400137c4`
- `KERNEL32!CancelIo` at `0x140013792`
- `KERNEL32!CancelIo` at `0x140013792`
- `KERNEL32!GetOverlappedResult` at `0x1400137b0`
- `KERNEL32!GetOverlappedResult` at `0x1400137b0`
- `KERNEL32!GetLastError` at `0x14001376b`
- `KERNEL32!GetLastError` at `0x14001376b`
- `KERNEL32!WaitForSingleObject` at `0x140013781`
- `KERNEL32!WaitForSingleObject` at `0x140013781`
- `KERNEL32!DeviceIoControl` at `0x14001375f`
- `KERNEL32!DeviceIoControl` at `0x14001375f`

## pseudocode

```c
__int64 __fastcall SuSetSpaceAttributes(struct _SP_ATTRIBUTES_INFO *lpInBuffer)
{
  bool v1; // zf
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  unsigned int OverlappedResult; // ebx
  HANDLE EventW; // rax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp+7h] BYREF
  _OWORD v9[3]; // [rsp+60h] [rbp+27h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+A0h] [rbp+67h] BYREF

  NumberOfBytesTransferred = 0;
  v1 = (*((_BYTE *)lpInBuffer + 48) & 1) == 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset(v9, 0, 40);
  if ( v1
    || (*((_BYTE *)lpInBuffer + 40) & 1) != 0
    || (v3 = *(_OWORD *)((char *)lpInBuffer + 4),
        LODWORD(v9[0]) = 40,
        v4 = *(_OWORD *)((char *)lpInBuffer + 20),
        BYTE4(v9[2]) = 0,
        *(_OWORD *)((char *)v9 + 4) = v3,
        *(_OWORD *)((char *)&v9[1] + 4) = v4,
        (OverlappedResult = SuRefreshPool((struct _SP_REFRESH_INFO *)v9)) != 0) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    Overlapped.hEvent = EventW;
    if ( !EventW )
    {
      OverlappedResult = 0;
      goto LABEL_12;
    }
    OverlappedResult = DeviceIoControl(Spaceport, 0xE7C81Cu, lpInBuffer, *(_DWORD *)lpInBuffer, 0, 0, 0, &Overlapped);
    if ( !OverlappedResult
      && GetLastError() == 997
      && (!WaitForSingleObject(Overlapped.hEvent, 0x7530u) || (OverlappedResult = CancelIo(Spaceport)) != 0) )
    {
      OverlappedResult = GetOverlappedResult(Spaceport, &Overlapped, &NumberOfBytesTransferred, 0);
    }
  }
  EventW = Overlapped.hEvent;
LABEL_12:
  if ( EventW )
    CloseHandle(EventW);
  return OverlappedResult;
}

```

## disassembly

```asm
0x140013694  mov     [rsp-8+arg_8], rbx
0x140013699  mov     [rsp-8+arg_10], rdi
0x14001369e  push    rbp
0x14001369f  lea     rbp, [rsp-57h]
0x1400136a4  sub     rsp, 90h
0x1400136ab  xor     eax, eax
0x1400136ad  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x1400136b4  test    byte ptr [rcx+30h], 1
0x1400136b8  xorps   xmm0, xmm0
0x1400136bb  xorps   xmm1, xmm1
0x1400136be  mov     [rbp+57h+var_10], rax
0x1400136c2  mov     rdi, rcx
0x1400136c5  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1400136c9  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1400136cd  movups  [rbp+57h+var_30], xmm1
0x1400136d1  movups  [rbp+57h+var_20], xmm1
0x1400136d5  jz      short loc_14001370A
0x1400136d7  test    byte ptr [rcx+28h], 1
0x1400136db  jnz     short loc_14001370A
0x1400136dd  movups  xmm0, xmmword ptr [rcx+4]
0x1400136e1  mov     dword ptr [rbp+57h+var_30], 28h ; '('
0x1400136e8  movups  xmm1, xmmword ptr [rcx+14h]
0x1400136ec  lea     rcx, [rbp+57h+var_30]; struct _SP_REFRESH_INFO *
0x1400136f0  mov     byte ptr [rbp+57h+var_10+4], al
0x1400136f3  movups  [rbp+57h+var_30+4], xmm0
0x1400136f7  movups  [rbp+57h+var_20+4], xmm1
0x1400136fb  call    ?SuRefreshPool@@YAHPEAU_SP_REFRESH_INFO@@@Z; SuRefreshPool(_SP_REFRESH_INFO *)
0x140013700  mov     ebx, eax
0x140013702  test    eax, eax
0x140013704  jz      loc_1400137B8
0x14001370a  xor     r9d, r9d; lpName
0x14001370d  xor     r8d, r8d; bInitialState
0x140013710  xor     edx, edx; bManualReset
0x140013712  xor     ecx, ecx; lpEventAttributes
0x140013714  call    cs:__imp_CreateEventW
0x14001371a  mov     [rbp+57h+Overlapped.hEvent], rax
0x14001371e  test    rax, rax
0x140013721  jnz     short loc_14001372A
0x140013723  xor     ebx, ebx
0x140013725  jmp     loc_1400137BC
0x14001372a  mov     r9d, [rdi]; nInBufferSize
0x14001372d  lea     rax, [rbp+57h+Overlapped]
0x140013731  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140013738  mov     r8, rdi; lpInBuffer
0x14001373b  mov     [rsp+90h+lpOverlapped], rax; lpOverlapped
0x140013740  mov     edx, 0E7C81Ch; dwIoControlCode
0x140013745  mov     [rsp+90h+lpBytesReturned], 0; lpBytesReturned
0x14001374e  mov     [rsp+90h+nOutBufferSize], 0; nOutBufferSize
0x140013756  mov     [rsp+90h+lpOutBuffer], 0; lpOutBuffer
0x14001375f  call    cs:__imp_DeviceIoControl
0x140013765  mov     ebx, eax
0x140013767  test    eax, eax
0x140013769  jnz     short loc_1400137B8
0x14001376b  call    cs:__imp_GetLastError
0x140013771  cmp     eax, 3E5h
0x140013776  jnz     short loc_1400137B8
0x140013778  mov     rcx, [rbp+57h+Overlapped.hEvent]; hHandle
0x14001377c  mov     edx, 7530h; dwMilliseconds
0x140013781  call    cs:__imp_WaitForSingleObject
0x140013787  test    eax, eax
0x140013789  jz      short loc_14001379E
0x14001378b  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x140013792  call    cs:__imp_CancelIo
0x140013798  mov     ebx, eax
0x14001379a  test    eax, eax
0x14001379c  jz      short loc_1400137B8
0x14001379e  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x1400137a5  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400137a9  xor     r9d, r9d; bWait
0x1400137ac  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x1400137b0  call    cs:__imp_GetOverlappedResult
0x1400137b6  mov     ebx, eax
0x1400137b8  mov     rax, [rbp+57h+Overlapped.hEvent]
0x1400137bc  test    rax, rax
0x1400137bf  jz      short loc_1400137CA
0x1400137c1  mov     rcx, rax; hObject
0x1400137c4  call    cs:__imp_CloseHandle
0x1400137ca  lea     r11, [rsp+90h+var_s0]
0x1400137d2  mov     eax, ebx
0x1400137d4  mov     rbx, [r11+18h]
0x1400137d8  mov     rdi, [r11+20h]
0x1400137dc  mov     rsp, r11
0x1400137df  pop     rbp
0x1400137e0  retn
```
