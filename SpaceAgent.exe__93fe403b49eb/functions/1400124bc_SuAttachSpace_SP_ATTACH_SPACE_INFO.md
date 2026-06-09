# SuAttachSpace(_SP_ATTACH_SPACE_INFO *)

- ea: `0x1400124bc`
- end: `0x1400126fd`
- name: `?SuAttachSpace@@YAHPEAU_SP_ATTACH_SPACE_INFO@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct _SP_ATTACH_SPACE_INFO *lpInBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400166f8`

## callees

- `0x140004114`
- `0x14000b39c`
- `0x1400124bc`
- `0x1400137e8`
- `0x140013914`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14001254e`
- `KERNEL32!CreateEventW` at `0x14001254e`
- `KERNEL32!CloseHandle` at `0x1400126d0`
- `KERNEL32!CloseHandle` at `0x1400126d0`
- `KERNEL32!CancelIo` at `0x1400125d6`
- `KERNEL32!CancelIo` at `0x1400125d6`
- `KERNEL32!GetOverlappedResult` at `0x1400125fd`
- `KERNEL32!GetOverlappedResult` at `0x1400125fd`
- `KERNEL32!SetLastError` at `0x1400126dd`
- `KERNEL32!SetLastError` at `0x1400126dd`
- `KERNEL32!GetLastError` at `0x1400125a6`
- `KERNEL32!GetLastError` at `0x140012610`
- `KERNEL32!GetLastError` at `0x1400125a6`
- `KERNEL32!GetLastError` at `0x140012610`
- `KERNEL32!WaitForSingleObject` at `0x1400125c5`
- `KERNEL32!WaitForSingleObject` at `0x1400125c5`
- `KERNEL32!QueryPerformanceCounter` at `0x140012509`
- `KERNEL32!QueryPerformanceCounter` at `0x14001261d`
- `KERNEL32!QueryPerformanceCounter` at `0x140012509`
- `KERNEL32!QueryPerformanceCounter` at `0x14001261d`
- `KERNEL32!DeviceIoControl` at `0x14001259a`
- `KERNEL32!DeviceIoControl` at `0x14001259a`

## string_xrefs

- `0x14001255f`: `CreateEvents`

## pseudocode

```c
__int64 __fastcall SuAttachSpace(struct _SP_ATTACH_SPACE_INFO *lpInBuffer)
{
  __int128 v2; // xmm0
  __int128 v3; // xmm1
  unsigned int refreshed; // ebx
  const char *v5; // rdi
  DWORD LastError; // r14d
  int v7; // r8d
  int v8; // r9d
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-19h] BYREF
  LARGE_INTEGER v11; // [rsp+58h] [rbp-11h] BYREF
  __int64 v12; // [rsp+60h] [rbp-9h]
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v14[40]; // [rsp+88h] [rbp+1Fh] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+D0h] [rbp+67h] BYREF

  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset(v14, 0, sizeof(v14));
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  v2 = *(_OWORD *)lpInBuffer;
  *(_DWORD *)v14 = 40;
  v3 = *((_OWORD *)lpInBuffer + 1);
  v14[36] = 0;
  *(_OWORD *)&v14[4] = v2;
  *(_OWORD *)&v14[20] = v3;
  refreshed = SuRefreshPool((struct _SP_REFRESH_INFO *)v14);
  if ( refreshed )
  {
    Overlapped.hEvent = CreateEventW(0, 0, 0, 0);
    if ( Overlapped.hEvent )
    {
      v5 = 0;
      LastError = 0;
      refreshed = DeviceIoControl(Spaceport, 0xE7C820u, lpInBuffer, 0x34u, 0, 0, 0, &Overlapped);
      if ( refreshed )
        goto LABEL_14;
      if ( GetLastError() == 997 )
      {
        if ( !WaitForSingleObject(Overlapped.hEvent, 0x7530u) || (refreshed = CancelIo(Spaceport)) != 0 )
        {
          refreshed = GetOverlappedResult(Spaceport, &Overlapped, &NumberOfBytesTransferred, 0);
          if ( refreshed )
            goto LABEL_14;
          v5 = "GetOverlappedResult";
        }
        else
        {
          v5 = "CancelIo";
        }
      }
      else
      {
        v5 = "DeviceIoControl - IOCTL_SPACEPORT_ATTACH_SPACE";
      }
    }
    else
    {
      refreshed = 0;
      v5 = "CreateEvents";
    }
  }
  else
  {
    v5 = "SuRefreshPool";
  }
  LastError = GetLastError();
LABEL_14:
  QueryPerformanceCounter(&v11);
  if ( refreshed )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjjtx_EventWriteTransfer(
        *((unsigned __int8 *)lpInBuffer + 48),
        (unsigned int)AttachSpaceSucceeded,
        (_DWORD)lpInBuffer + 16,
        v8,
        (__int64)"SuAttachSpace",
        (__int64)lpInBuffer + 16,
        (__int64)lpInBuffer + 32,
        *((_BYTE *)lpInBuffer + 48),
        1000000 * (v11.QuadPart - PerformanceCount.QuadPart) / v12);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjjtsq_EventWriteTransfer(
      (_DWORD)lpInBuffer + 32,
      (unsigned int)AttachSpaceFailed,
      v7,
      v8,
      (__int64)"SuAttachSpace",
      (__int64)lpInBuffer + 16,
      (__int64)lpInBuffer + 32,
      *((_BYTE *)lpInBuffer + 48),
      (__int64)v5,
      LastError);
  }
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  if ( !refreshed )
    SetLastError(LastError);
  return refreshed;
}

```

## disassembly

```asm
0x1400124bc  mov     [rsp-8+arg_8], rbx
0x1400124c1  mov     [rsp-8+arg_10], rsi
0x1400124c6  push    rbp
0x1400124c7  push    rdi
0x1400124c8  push    r14
0x1400124ca  lea     rbp, [rsp-47h]
0x1400124cf  sub     rsp, 0B0h
0x1400124d6  xorps   xmm0, xmm0
0x1400124d9  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x1400124e0  xorps   xmm1, xmm1
0x1400124e3  mov     rsi, rcx
0x1400124e6  xor     eax, eax
0x1400124e8  lea     rcx, [rbp+57h+PerformanceCount]; this
0x1400124ec  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1400124f0  mov     [rbp+57h+var_18], rax
0x1400124f4  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1400124f8  movups  [rbp+57h+var_38], xmm1
0x1400124fc  movups  [rbp+57h+var_28], xmm1
0x140012500  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x140012505  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140012509  call    cs:__imp_QueryPerformanceCounter
0x14001250f  movups  xmm0, xmmword ptr [rsi]
0x140012512  lea     rcx, [rbp+57h+var_38]; struct _SP_REFRESH_INFO *
0x140012516  mov     dword ptr [rbp+57h+var_38], 28h ; '('
0x14001251d  movups  xmm1, xmmword ptr [rsi+10h]
0x140012521  mov     byte ptr [rbp+57h+var_18+4], 0
0x140012525  movups  [rbp+57h+var_38+4], xmm0
0x140012529  movups  [rbp+57h+var_28+4], xmm1
0x14001252d  call    ?SuRefreshPool@@YAHPEAU_SP_REFRESH_INFO@@@Z; SuRefreshPool(_SP_REFRESH_INFO *)
0x140012532  mov     ebx, eax
0x140012534  test    eax, eax
0x140012536  jnz     short loc_140012544
0x140012538  lea     rdi, aSurefreshpool; "SuRefreshPool"
0x14001253f  jmp     loc_140012610
0x140012544  xor     r9d, r9d; lpName
0x140012547  xor     r8d, r8d; bInitialState
0x14001254a  xor     edx, edx; bManualReset
0x14001254c  xor     ecx, ecx; lpEventAttributes
0x14001254e  call    cs:__imp_CreateEventW
0x140012554  mov     [rbp+57h+Overlapped.hEvent], rax
0x140012558  test    rax, rax
0x14001255b  jnz     short loc_14001256B
0x14001255d  xor     ebx, ebx
0x14001255f  lea     rdi, aCreateevents; "CreateEvents"
0x140012566  jmp     loc_140012610
0x14001256b  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140012572  lea     rax, [rbp+57h+Overlapped]
0x140012576  mov     [rsp+0C0h+lpOverlapped], rax; lpOverlapped
0x14001257b  xor     edi, edi
0x14001257d  mov     [rsp+0C0h+lpBytesReturned], rdi; lpBytesReturned
0x140012582  xor     r14d, r14d
0x140012585  mov     [rsp+0C0h+nOutBufferSize], edi; nOutBufferSize
0x140012589  mov     r8, rsi; lpInBuffer
0x14001258c  mov     edx, 0E7C820h; dwIoControlCode
0x140012591  mov     [rsp+0C0h+lpOutBuffer], rdi; lpOutBuffer
0x140012596  lea     r9d, [r14+34h]; nInBufferSize
0x14001259a  call    cs:__imp_DeviceIoControl
0x1400125a0  mov     ebx, eax
0x1400125a2  test    eax, eax
0x1400125a4  jnz     short loc_140012619
0x1400125a6  call    cs:__imp_GetLastError
0x1400125ac  cmp     eax, 3E5h
0x1400125b1  jz      short loc_1400125BC
0x1400125b3  lea     rdi, aDeviceiocontro_6; "DeviceIoControl - IOCTL_SPACEPORT_ATTAC"...
0x1400125ba  jmp     short loc_140012610
0x1400125bc  mov     rcx, [rbp+57h+Overlapped.hEvent]; hHandle
0x1400125c0  mov     edx, 7530h; dwMilliseconds
0x1400125c5  call    cs:__imp_WaitForSingleObject
0x1400125cb  test    eax, eax
0x1400125cd  jz      short loc_1400125EB
0x1400125cf  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x1400125d6  call    cs:__imp_CancelIo
0x1400125dc  mov     ebx, eax
0x1400125de  test    eax, eax
0x1400125e0  jnz     short loc_1400125EB
0x1400125e2  lea     rdi, aCancelio; "CancelIo"
0x1400125e9  jmp     short loc_140012610
0x1400125eb  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x1400125f2  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400125f6  xor     r9d, r9d; bWait
0x1400125f9  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x1400125fd  call    cs:__imp_GetOverlappedResult
0x140012603  mov     ebx, eax
0x140012605  test    eax, eax
0x140012607  jnz     short loc_140012619
0x140012609  lea     rdi, aGetoverlappedr; "GetOverlappedResult"
0x140012610  call    cs:__imp_GetLastError
0x140012616  mov     r14d, eax
0x140012619  lea     rcx, [rbp+57h+var_68]; lpPerformanceCount
0x14001261d  call    cs:__imp_QueryPerformanceCounter
0x140012623  test    ebx, ebx
0x140012625  jz      short loc_140012682
0x140012627  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14001262e  jz      loc_1400126C7
0x140012634  mov     rcx, qword ptr [rbp+57h+var_68]
0x140012638  lea     r8, [rsi+10h]
0x14001263c  sub     rcx, qword ptr [rbp+57h+PerformanceCount]
0x140012640  imul    rax, rcx, 0F4240h
0x140012647  movzx   ecx, byte ptr [rsi+30h]
0x14001264b  cqo
0x14001264d  idiv    [rbp+57h+var_60]
0x140012651  lea     rdx, [rsi+20h]
0x140012655  mov     [rsp+0C0h+var_80], rax
0x14001265a  lea     rax, aSuattachspace; "SuAttachSpace"
0x140012661  mov     dword ptr [rsp+0C0h+lpOverlapped], ecx
0x140012665  mov     [rsp+0C0h+lpBytesReturned], rdx
0x14001266a  lea     rdx, AttachSpaceSucceeded
0x140012671  mov     qword ptr [rsp+0C0h+nOutBufferSize], r8
0x140012676  mov     [rsp+0C0h+lpOutBuffer], rax
0x14001267b  call    McTemplateK0zsjjtx_EventWriteTransfer
0x140012680  jmp     short loc_1400126C7
0x140012682  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x140012689  jz      short loc_1400126C7
0x14001268b  movzx   eax, byte ptr [rsi+30h]
0x14001268f  lea     rcx, [rsi+20h]
0x140012693  mov     [rsp+0C0h+var_78], r14d
0x140012698  lea     rdx, [rsi+10h]
0x14001269c  mov     [rsp+0C0h+var_80], rdi
0x1400126a1  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x1400126a5  lea     rax, aSuattachspace; "SuAttachSpace"
0x1400126ac  mov     [rsp+0C0h+lpBytesReturned], rcx
0x1400126b1  mov     qword ptr [rsp+0C0h+nOutBufferSize], rdx
0x1400126b6  lea     rdx, AttachSpaceFailed
0x1400126bd  mov     [rsp+0C0h+lpOutBuffer], rax
0x1400126c2  call    McTemplateK0zsjjtsq_EventWriteTransfer
0x1400126c7  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x1400126cb  test    rcx, rcx
0x1400126ce  jz      short loc_1400126D6
0x1400126d0  call    cs:__imp_CloseHandle
0x1400126d6  test    ebx, ebx
0x1400126d8  jnz     short loc_1400126E3
0x1400126da  mov     ecx, r14d; dwErrCode
0x1400126dd  call    cs:__imp_SetLastError
0x1400126e3  lea     r11, [rsp+0C0h+var_10]
0x1400126eb  mov     eax, ebx
0x1400126ed  mov     rbx, [r11+28h]
0x1400126f1  mov     rsi, [r11+30h]
0x1400126f5  mov     rsp, r11
0x1400126f8  pop     r14
0x1400126fa  pop     rdi
0x1400126fb  pop     rbp
0x1400126fc  retn
```
