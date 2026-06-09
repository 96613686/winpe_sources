# DafBthGetLocalDeviceInfo

- ea: `0x180022478`
- end: `0x180022680`
- name: `DafBthGetLocalDeviceInfo`
- size: `520`
- prototype: `__int64 __fastcall(HANDLE hFile, LPVOID lpOutBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002103c`

## callees

- `0x1800024ac`
- `0x180021ac8`
- `0x180021b88`
- `0x180022478`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800224f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800224f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002257d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002257d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022622`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022622`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002259e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002259e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002256f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002256f`

## pseudocode

```c
__int64 __fastcall DafBthGetLocalDeviceInfo(HANDLE hFile, LPVOID lpOutBuffer)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  signed int LastError; // eax
  signed int v9; // eax
  int v10; // eax
  bool v11; // cf
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-38h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF

  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
  memset_0(lpOutBuffer, 0, 0x124u);
  Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Overlapped.hEvent )
  {
    v5 = 0;
    if ( DeviceIoControl(hFile, 0x410000u, 0, 0, lpOutBuffer, 0x124u, &BytesReturned, &Overlapped) )
      goto LABEL_25;
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v7 = 19;
        goto LABEL_24;
      }
      goto LABEL_26;
    }
    if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
LABEL_25:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v7 = 18;
      goto LABEL_24;
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 17;
LABEL_24:
      WPP_SF_sd(v6[2], v7, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( Overlapped.hEvent )
  {
    CloseHandle(Overlapped.hEvent);
    v6 = WPP_GLOBAL_Control;
    Overlapped.hEvent = 0;
  }
  v10 = 0;
  if ( v5 )
    v11 = *((_BYTE *)v6 + 25) < 2u;
  else
    v11 = *((_BYTE *)v6 + 25) < 5u;
  if ( v6 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v10) = !v11;
    if ( v10 )
      WPP_SF_sd(v6[2], 20, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x180022478  mov     rax, rsp
0x18002247b  mov     [rax+8], rbx
0x18002247f  mov     [rax+10h], rbp
0x180022483  push    rsi
0x180022484  push    rdi
0x180022485  push    r14
0x180022487  sub     rsp, 60h
0x18002248b  xorps   xmm0, xmm0
0x18002248e  mov     dword ptr [rax+18h], 0
0x180022495  movups  xmmword ptr [rax-38h], xmm0
0x180022499  mov     rsi, rdx
0x18002249c  mov     rdi, rcx
0x18002249f  movups  xmmword ptr [rax-28h], xmm0
0x1800224a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224aa  lea     rbp, WPP_GLOBAL_Control
0x1800224b1  lea     r14, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids
0x1800224b8  cmp     rcx, rbp
0x1800224bb  jz      short loc_1800224D4
0x1800224bd  cmp     byte ptr [rcx+19h], 5
0x1800224c1  jb      short loc_1800224D4
0x1800224c3  mov     rcx, [rcx+10h]
0x1800224c7  mov     edx, 10h
0x1800224cc  mov     r8, r14
0x1800224cf  call    WPP_SF_s
0x1800224d4  xor     edx, edx; Val
0x1800224d6  mov     r8d, 124h; Size
0x1800224dc  mov     rcx, rsi; void *
0x1800224df  call    memset_0
0x1800224e4  xor     edx, edx; lpName
0x1800224e6  xor     ecx, ecx; lpEventAttributes
0x1800224e8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800224ee  lea     r8d, [rdx+1]; dwFlags
0x1800224f2  call    cs:__imp_CreateEventExW
0x1800224f8  mov     [rsp+78h+Overlapped.hEvent], rax
0x1800224fd  test    rax, rax
0x180022500  jnz     short loc_18002253B
0x180022502  call    cs:__imp_GetLastError
0x180022508  mov     ebx, eax
0x18002250a  test    eax, eax
0x18002250c  jle     short loc_180022517
0x18002250e  movzx   ebx, ax
0x180022511  or      ebx, 80070000h
0x180022517  mov     rcx, cs:WPP_GLOBAL_Control
0x18002251e  cmp     rcx, rbp
0x180022521  jz      loc_180022615
0x180022527  cmp     byte ptr [rcx+19h], 2
0x18002252b  jb      loc_180022615
0x180022531  mov     edx, 11h
0x180022536  jmp     loc_1800225FE
0x18002253b  lea     rax, [rsp+78h+Overlapped]
0x180022540  xor     r9d, r9d; nInBufferSize
0x180022543  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180022548  xor     r8d, r8d; lpInBuffer
0x18002254b  lea     rax, [rsp+78h+BytesReturned]
0x180022553  mov     edx, 410000h; dwIoControlCode
0x180022558  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x18002255d  mov     rcx, rdi; hDevice
0x180022560  mov     [rsp+78h+nOutBufferSize], 124h; nOutBufferSize
0x180022568  xor     ebx, ebx
0x18002256a  mov     [rsp+78h+lpOutBuffer], rsi; lpOutBuffer
0x18002256f  call    cs:__imp_DeviceIoControl
0x180022575  test    eax, eax
0x180022577  jnz     loc_18002260E
0x18002257d  call    cs:__imp_GetLastError
0x180022583  cmp     eax, 3E5h
0x180022588  jnz     short loc_1800225D6
0x18002258a  lea     r9d, [rbx+1]; bWait
0x18002258e  mov     rcx, rdi; hFile
0x180022591  lea     r8, [rsp+78h+BytesReturned]; lpNumberOfBytesTransferred
0x180022599  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x18002259e  call    cs:__imp_GetOverlappedResult
0x1800225a4  test    eax, eax
0x1800225a6  jnz     short loc_18002260E
0x1800225a8  call    cs:__imp_GetLastError
0x1800225ae  mov     ebx, eax
0x1800225b0  test    eax, eax
0x1800225b2  jle     short loc_1800225BD
0x1800225b4  movzx   ebx, ax
0x1800225b7  or      ebx, 80070000h
0x1800225bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225c4  cmp     rcx, rbp
0x1800225c7  jz      short loc_180022615
0x1800225c9  cmp     byte ptr [rcx+19h], 3
0x1800225cd  jb      short loc_180022615
0x1800225cf  mov     edx, 12h
0x1800225d4  jmp     short loc_1800225FE
0x1800225d6  test    eax, eax
0x1800225d8  jg      short loc_1800225DE
0x1800225da  mov     ebx, eax
0x1800225dc  jmp     short loc_1800225E7
0x1800225de  movzx   ebx, ax
0x1800225e1  or      ebx, 80070000h
0x1800225e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225ee  cmp     rcx, rbp
0x1800225f1  jz      short loc_180022615
0x1800225f3  cmp     byte ptr [rcx+19h], 3
0x1800225f7  jb      short loc_180022615
0x1800225f9  mov     edx, 13h
0x1800225fe  mov     rcx, [rcx+10h]
0x180022602  mov     r8, r14
0x180022605  mov     dword ptr [rsp+78h+lpOutBuffer], ebx
0x180022609  call    WPP_SF_sd
0x18002260e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022615  mov     rax, [rsp+78h+Overlapped.hEvent]
0x18002261a  test    rax, rax
0x18002261d  jz      short loc_180022638
0x18002261f  mov     rcx, rax; hObject
0x180022622  call    cs:__imp_CloseHandle
0x180022628  mov     rcx, cs:WPP_GLOBAL_Control
0x18002262f  mov     [rsp+78h+Overlapped.hEvent], 0
0x180022638  xor     eax, eax
0x18002263a  test    ebx, ebx
0x18002263c  jnz     short loc_180022644
0x18002263e  cmp     byte ptr [rcx+19h], 5
0x180022642  jmp     short loc_180022648
0x180022644  cmp     byte ptr [rcx+19h], 2
0x180022648  setnb   al
0x18002264b  cmp     rcx, rbp
0x18002264e  jz      short loc_180022669
0x180022650  test    eax, eax
0x180022652  jz      short loc_180022669
0x180022654  mov     rcx, [rcx+10h]
0x180022658  mov     edx, 14h
0x18002265d  mov     r8, r14
0x180022660  mov     dword ptr [rsp+78h+lpOutBuffer], ebx
0x180022664  call    WPP_SF_sd
0x180022669  lea     r11, [rsp+78h+var_18]
0x18002266e  mov     eax, ebx
0x180022670  mov     rbx, [r11+20h]
0x180022674  mov     rbp, [r11+28h]
0x180022678  mov     rsp, r11
0x18002267b  pop     r14
0x18002267d  pop     rdi
0x18002267e  pop     rsi
0x18002267f  retn
```
