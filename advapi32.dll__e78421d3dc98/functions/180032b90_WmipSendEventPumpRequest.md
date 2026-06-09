# WmipSendEventPumpRequest

- ea: `0x180032b90`
- end: `0x180032de2`
- name: `WmipSendEventPumpRequest`
- size: `594`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180032aa0`
- `0x18005cc64`

## callees

- `0x180032b90`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180032c78`
- `ntdll!RtlFreeHeap` at `0x180032c78`
- `ntdll!RtlAllocateHeap` at `0x180032c93`
- `ntdll!RtlAllocateHeap` at `0x180032c93`
- `KERNEL32!GetLastError` at `0x180032d94`
- `KERNEL32!GetLastError` at `0x180032d94`
- `KERNEL32!FreeLibrary` at `0x180032db5`
- `KERNEL32!FreeLibrary` at `0x180032db5`
- `KERNEL32!GetModuleHandleExW` at `0x180032c25`
- `KERNEL32!GetModuleHandleExW` at `0x180032c25`
- `KERNEL32!CancelThreadpoolIo` at `0x180032da8`
- `KERNEL32!CancelThreadpoolIo` at `0x180032da8`
- `KERNEL32!DeviceIoControl` at `0x180032d8a`
- `KERNEL32!DeviceIoControl` at `0x180032d8a`
- `KERNEL32!StartThreadpoolIo` at `0x180032d4a`
- `KERNEL32!StartThreadpoolIo` at `0x180032d4a`

## pseudocode

```c
void WmipSendEventPumpRequest()
{
  PVOID *v0; // rcx
  int v1; // ebx
  int v2; // edi
  _DWORD *v3; // r10
  bool v4; // r8
  __int64 v5; // rdx
  DWORD v6; // esi
  DWORD v7; // ebx
  _DWORD *v8; // r9
  PVOID *v9; // rdx
  __int64 v10; // rbp
  char v11; // bl
  __int64 i; // r8
  _QWORD *v13; // r11
  _QWORD *v14; // r10
  void *v15; // rax
  struct _TP_IO *v16; // rcx

  v0 = (PVOID *)WmipGNHead;
  v1 = 0;
  v2 = 1;
  if ( WmipGNHead != &WmipGNHead )
  {
    do
    {
      if ( *((_DWORD *)v0 + 9) )
      {
        v3 = v0[5];
        v4 = 0;
        v5 = 0;
        do
        {
          if ( *(_QWORD *)&v3[10 * v5 + 2] )
          {
            if ( v4 )
            {
              if ( (v3[10 * v5 + 8] & 0x200000) == 0 )
                ++v1;
            }
            else
            {
              ++v1;
              v4 = (v3[10 * v5 + 8] & 0x200000) != 0;
            }
          }
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (unsigned int)v5 < *((_DWORD *)v0 + 9) );
      }
      v0 = (PVOID *)*v0;
    }
    while ( v0 != &WmipGNHead );
    if ( v1 )
    {
      if ( !GetModuleHandleExW(4u, (LPCWSTR)WmipSendEventPumpRequest, &WmipEventPumpModule) )
      {
LABEL_13:
        WmipEventPumpModule = 0;
        goto LABEL_39;
      }
      v6 = 8 * v1 + 8;
      v7 = 56;
      if ( v6 > 0x38 )
        v7 = v6;
      if ( v7 <= WmipEventPumpBufferSize )
      {
        v8 = WmipEventPumpBuffer;
      }
      else
      {
        if ( WmipEventPumpBuffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, WmipEventPumpBuffer);
        WmipEventPumpBuffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v7);
        v8 = WmipEventPumpBuffer;
        if ( !WmipEventPumpBuffer )
        {
          WmipEventPumpBufferSize = 0;
LABEL_37:
          FreeLibrary(WmipEventPumpModule);
          goto LABEL_13;
        }
        WmipEventPumpBufferSize = v7;
      }
      v9 = (PVOID *)WmipGNHead;
      v10 = 0;
      while ( v9 != &WmipGNHead )
      {
        v11 = 0;
        for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 9); i = (unsigned int)(i + 1) )
        {
          v13 = v9[5];
          if ( v13[5 * i + 1] )
          {
            v14 = &v13[5 * i];
            if ( !v11 || (v14[4] & 0x200000) == 0 )
            {
              *(_QWORD *)&v8[2 * v10 + 2] = v13[5 * i];
              if ( (v14[4] & 0x200000) != 0 )
                v11 = 1;
              v10 = (unsigned int)(v10 + 1);
            }
          }
        }
        v9 = (PVOID *)*v9;
      }
      v15 = (void *)WmipEventPumpOverlappedEvent;
      v16 = WmipEventPumpIo;
      *v8 = v10;
      *(_OWORD *)&WmipEventPumpOverlapped.InternalHigh = 0;
      WmipEventPumpOverlapped.hEvent = v15;
      WmipEventPumpOverlapped.Internal = 0;
      StartThreadpoolIo(v16);
      if ( DeviceIoControl(
             WmipEventPumpTarget,
             0x228144u,
             WmipEventPumpBuffer,
             v6,
             WmipEventPumpBuffer,
             WmipEventPumpBufferSize,
             0,
             &WmipEventPumpOverlapped)
        || GetLastError() == 997 )
      {
        v2 = 2;
        goto LABEL_39;
      }
      CancelThreadpoolIo(WmipEventPumpIo);
      goto LABEL_37;
    }
  }
LABEL_39:
  WmipEventPumpFlags = 0;
  WmipEventPumpState = v2;
}

```

## disassembly

```asm
0x180032b90  push    rbx
0x180032b92  push    rbp
0x180032b93  push    rsi
0x180032b94  push    rdi
0x180032b95  push    r12
0x180032b97  push    r15
0x180032b99  sub     rsp, 48h
0x180032b9d  mov     rcx, cs:WmipGNHead
0x180032ba4  lea     r15, WmipGNHead
0x180032bab  xor     ebx, ebx
0x180032bad  mov     edi, 1
0x180032bb2  cmp     rcx, r15
0x180032bb5  jz      loc_180032DC5
0x180032bbb  mov     r12d, 200000h
0x180032bc1  cmp     dword ptr [rcx+24h], 0
0x180032bc5  jbe     short loc_180032C02
0x180032bc7  mov     r10, [rcx+28h]
0x180032bcb  xor     r8b, r8b
0x180032bce  xor     edx, edx
0x180032bd0  lea     r9, [rdx+rdx*4]
0x180032bd4  cmp     qword ptr [r10+r9*8+8], 0
0x180032bda  jz      short loc_180032BFB
0x180032bdc  test    r8b, r8b
0x180032bdf  jz      short loc_180032BEC
0x180032be1  test    [r10+r9*8+20h], r12d
0x180032be6  jnz     short loc_180032BFB
0x180032be8  inc     ebx
0x180032bea  jmp     short loc_180032BFB
0x180032bec  add     ebx, edi
0x180032bee  movzx   r8d, r8b
0x180032bf2  test    [r10+r9*8+20h], r12d
0x180032bf7  cmovnz  r8d, edi
0x180032bfb  add     edx, edi
0x180032bfd  cmp     edx, [rcx+24h]
0x180032c00  jb      short loc_180032BD0
0x180032c02  mov     rcx, [rcx]
0x180032c05  cmp     rcx, r15
0x180032c08  jnz     short loc_180032BC1
0x180032c0a  test    ebx, ebx
0x180032c0c  jz      loc_180032DC5
0x180032c12  lea     r8, WmipEventPumpModule; phModule
0x180032c19  mov     ecx, 4; dwFlags
0x180032c1e  lea     rdx, WmipSendEventPumpRequest; lpModuleName
0x180032c25  call    cs:__imp_GetModuleHandleExW
0x180032c2b  test    eax, eax
0x180032c2d  jnz     short loc_180032C3F
0x180032c2f  mov     cs:WmipEventPumpModule, 0
0x180032c3a  jmp     loc_180032DC5
0x180032c3f  lea     esi, ds:8[rbx*8]
0x180032c46  mov     ebx, 38h ; '8'
0x180032c4b  cmp     esi, ebx
0x180032c4d  cmova   ebx, esi
0x180032c50  cmp     ebx, cs:WmipEventPumpBufferSize
0x180032c56  jbe     short loc_180032CBB
0x180032c58  cmp     cs:WmipEventPumpBuffer, 0
0x180032c60  jz      short loc_180032C7E
0x180032c62  mov     rcx, gs:60h
0x180032c6b  xor     edx, edx; Flags
0x180032c6d  mov     r8, cs:WmipEventPumpBuffer; P
0x180032c74  mov     rcx, [rcx+30h]; HeapHandle
0x180032c78  call    cs:__imp_RtlFreeHeap
0x180032c7e  mov     rcx, gs:60h
0x180032c87  mov     edx, 8; Flags
0x180032c8c  mov     r8d, ebx; Size
0x180032c8f  mov     rcx, [rcx+30h]; HeapHandle
0x180032c93  call    cs:__imp_RtlAllocateHeap
0x180032c99  mov     cs:WmipEventPumpBuffer, rax
0x180032ca0  mov     r9, rax
0x180032ca3  test    rax, rax
0x180032ca6  jnz     short loc_180032CB3
0x180032ca8  mov     cs:WmipEventPumpBufferSize, eax
0x180032cae  jmp     loc_180032DAE
0x180032cb3  mov     cs:WmipEventPumpBufferSize, ebx
0x180032cb9  jmp     short loc_180032CC2
0x180032cbb  mov     r9, cs:WmipEventPumpBuffer
0x180032cc2  mov     rdx, cs:WmipGNHead
0x180032cc9  xor     ebp, ebp
0x180032ccb  jmp     short loc_180032D17
0x180032ccd  xor     bl, bl
0x180032ccf  xor     r8d, r8d
0x180032cd2  cmp     [rdx+24h], r8d
0x180032cd6  jbe     short loc_180032D14
0x180032cd8  mov     r11, [rdx+28h]
0x180032cdc  lea     rax, [r8+r8*4]
0x180032ce0  cmp     qword ptr [r11+rax*8+8], 0
0x180032ce6  jz      short loc_180032D0B
0x180032ce8  lea     r10, [r11+rax*8]
0x180032cec  test    bl, bl
0x180032cee  jz      short loc_180032CF6
0x180032cf0  test    [r10+20h], r12d
0x180032cf4  jnz     short loc_180032D0B
0x180032cf6  mov     rax, [r11+rax*8]
0x180032cfa  mov     [r9+rbp*8+8], rax
0x180032cff  test    [r10+20h], r12d
0x180032d03  movzx   ebx, bl
0x180032d06  cmovnz  ebx, edi
0x180032d09  add     ebp, edi
0x180032d0b  add     r8d, edi
0x180032d0e  cmp     r8d, [rdx+24h]
0x180032d12  jb      short loc_180032CD8
0x180032d14  mov     rdx, [rdx]
0x180032d17  cmp     rdx, r15
0x180032d1a  jnz     short loc_180032CCD
0x180032d1c  mov     rax, cs:WmipEventPumpOverlappedEvent
0x180032d23  xorps   xmm0, xmm0
0x180032d26  mov     rcx, cs:WmipEventPumpIo; pio
0x180032d2d  mov     [r9], ebp
0x180032d30  movdqu  xmmword ptr cs:WmipEventPumpOverlapped.InternalHigh, xmm0
0x180032d38  mov     cs:WmipEventPumpOverlapped.hEvent, rax
0x180032d3f  mov     cs:WmipEventPumpOverlapped.Internal, 0
0x180032d4a  call    cs:__imp_StartThreadpoolIo
0x180032d50  mov     r8, cs:WmipEventPumpBuffer; lpInBuffer
0x180032d57  lea     rax, WmipEventPumpOverlapped
0x180032d5e  mov     rcx, cs:WmipEventPumpTarget; hDevice
0x180032d65  mov     r9d, esi; nInBufferSize
0x180032d68  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180032d6d  mov     edx, 228144h; dwIoControlCode
0x180032d72  mov     eax, cs:WmipEventPumpBufferSize
0x180032d78  mov     [rsp+78h+lpBytesReturned], 0; lpBytesReturned
0x180032d81  mov     [rsp+78h+nOutBufferSize], eax; nOutBufferSize
0x180032d85  mov     [rsp+78h+lpOutBuffer], r8; lpOutBuffer
0x180032d8a  call    cs:__imp_DeviceIoControl
0x180032d90  test    eax, eax
0x180032d92  jnz     short loc_180032DC0
0x180032d94  call    cs:__imp_GetLastError
0x180032d9a  cmp     eax, 3E5h
0x180032d9f  jz      short loc_180032DC0
0x180032da1  mov     rcx, cs:WmipEventPumpIo; pio
0x180032da8  call    cs:__imp_CancelThreadpoolIo
0x180032dae  mov     rcx, cs:WmipEventPumpModule; hLibModule
0x180032db5  call    cs:__imp_FreeLibrary
0x180032dbb  jmp     loc_180032C2F
0x180032dc0  mov     edi, 2
0x180032dc5  mov     cs:WmipEventPumpFlags, 0
0x180032dcf  mov     cs:WmipEventPumpState, edi
0x180032dd5  add     rsp, 48h
0x180032dd9  pop     r15
0x180032ddb  pop     r12
0x180032ddd  pop     rdi
0x180032dde  pop     rsi
0x180032ddf  pop     rbp
0x180032de0  pop     rbx
0x180032de1  retn
```
