# WmipSendEventPumpRequest

- ea: `0x180036620`
- end: `0x1800368a3`
- name: `WmipSendEventPumpRequest`
- size: `643`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180036510`
- `0x180069300`

## callees

- `0x180036620`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003670e`
- `ntdll!RtlFreeHeap` at `0x18003670e`
- `ntdll!RtlAllocateHeap` at `0x18003672f`
- `ntdll!RtlAllocateHeap` at `0x18003672f`
- `KERNEL32!GetLastError` at `0x180036842`
- `KERNEL32!GetLastError` at `0x180036842`
- `KERNEL32!FreeLibrary` at `0x18003686f`
- `KERNEL32!FreeLibrary` at `0x18003686f`
- `KERNEL32!GetModuleHandleExW` at `0x1800366b5`
- `KERNEL32!GetModuleHandleExW` at `0x1800366b5`
- `KERNEL32!CancelThreadpoolIo` at `0x18003685c`
- `KERNEL32!CancelThreadpoolIo` at `0x18003685c`
- `KERNEL32!DeviceIoControl` at `0x180036832`
- `KERNEL32!DeviceIoControl` at `0x180036832`
- `KERNEL32!StartThreadpoolIo` at `0x1800367ec`
- `KERNEL32!StartThreadpoolIo` at `0x1800367ec`

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
0x180036620  push    rbx
0x180036622  push    rbp
0x180036623  push    rsi
0x180036624  push    rdi
0x180036625  push    r12
0x180036627  push    r15
0x180036629  sub     rsp, 48h
0x18003662d  mov     rcx, cs:WmipGNHead
0x180036634  lea     r15, WmipGNHead
0x18003663b  xor     ebx, ebx
0x18003663d  mov     edi, 1
0x180036642  cmp     rcx, r15
0x180036645  jz      loc_180036885
0x18003664b  mov     r12d, 200000h
0x180036651  cmp     dword ptr [rcx+24h], 0
0x180036655  jbe     short loc_180036692
0x180036657  mov     r10, [rcx+28h]
0x18003665b  xor     r8b, r8b
0x18003665e  xor     edx, edx
0x180036660  lea     r9, [rdx+rdx*4]
0x180036664  cmp     qword ptr [r10+r9*8+8], 0
0x18003666a  jz      short loc_18003668B
0x18003666c  test    r8b, r8b
0x18003666f  jz      short loc_18003667C
0x180036671  test    [r10+r9*8+20h], r12d
0x180036676  jnz     short loc_18003668B
0x180036678  inc     ebx
0x18003667a  jmp     short loc_18003668B
0x18003667c  add     ebx, edi
0x18003667e  movzx   r8d, r8b
0x180036682  test    [r10+r9*8+20h], r12d
0x180036687  cmovnz  r8d, edi
0x18003668b  add     edx, edi
0x18003668d  cmp     edx, [rcx+24h]
0x180036690  jb      short loc_180036660
0x180036692  mov     rcx, [rcx]
0x180036695  cmp     rcx, r15
0x180036698  jnz     short loc_180036651
0x18003669a  test    ebx, ebx
0x18003669c  jz      loc_180036885
0x1800366a2  lea     r8, WmipEventPumpModule; phModule
0x1800366a9  mov     ecx, 4; dwFlags
0x1800366ae  lea     rdx, WmipSendEventPumpRequest; lpModuleName
0x1800366b5  call    cs:__imp_GetModuleHandleExW
0x1800366bc  nop     dword ptr [rax+rax+00h]
0x1800366c1  test    eax, eax
0x1800366c3  jnz     short loc_1800366D5
0x1800366c5  mov     cs:WmipEventPumpModule, 0
0x1800366d0  jmp     loc_180036885
0x1800366d5  lea     esi, ds:8[rbx*8]
0x1800366dc  mov     ebx, 38h ; '8'
0x1800366e1  cmp     esi, ebx
0x1800366e3  cmova   ebx, esi
0x1800366e6  cmp     ebx, cs:WmipEventPumpBufferSize
0x1800366ec  jbe     short loc_18003675D
0x1800366ee  cmp     cs:WmipEventPumpBuffer, 0
0x1800366f6  jz      short loc_18003671A
0x1800366f8  mov     rcx, gs:60h
0x180036701  xor     edx, edx; Flags
0x180036703  mov     r8, cs:WmipEventPumpBuffer; P
0x18003670a  mov     rcx, [rcx+30h]; HeapHandle
0x18003670e  call    cs:__imp_RtlFreeHeap
0x180036715  nop     dword ptr [rax+rax+00h]
0x18003671a  mov     rcx, gs:60h
0x180036723  mov     edx, 8; Flags
0x180036728  mov     r8d, ebx; Size
0x18003672b  mov     rcx, [rcx+30h]; HeapHandle
0x18003672f  call    cs:__imp_RtlAllocateHeap
0x180036736  nop     dword ptr [rax+rax+00h]
0x18003673b  mov     cs:WmipEventPumpBuffer, rax
0x180036742  mov     r9, rax
0x180036745  test    rax, rax
0x180036748  jnz     short loc_180036755
0x18003674a  mov     cs:WmipEventPumpBufferSize, eax
0x180036750  jmp     loc_180036868
0x180036755  mov     cs:WmipEventPumpBufferSize, ebx
0x18003675b  jmp     short loc_180036764
0x18003675d  mov     r9, cs:WmipEventPumpBuffer
0x180036764  mov     rdx, cs:WmipGNHead
0x18003676b  xor     ebp, ebp
0x18003676d  jmp     short loc_1800367B9
0x18003676f  xor     bl, bl
0x180036771  xor     r8d, r8d
0x180036774  cmp     [rdx+24h], r8d
0x180036778  jbe     short loc_1800367B6
0x18003677a  mov     r11, [rdx+28h]
0x18003677e  lea     rax, [r8+r8*4]
0x180036782  cmp     qword ptr [r11+rax*8+8], 0
0x180036788  jz      short loc_1800367AD
0x18003678a  lea     r10, [r11+rax*8]
0x18003678e  test    bl, bl
0x180036790  jz      short loc_180036798
0x180036792  test    [r10+20h], r12d
0x180036796  jnz     short loc_1800367AD
0x180036798  mov     rax, [r11+rax*8]
0x18003679c  mov     [r9+rbp*8+8], rax
0x1800367a1  test    [r10+20h], r12d
0x1800367a5  movzx   ebx, bl
0x1800367a8  cmovnz  ebx, edi
0x1800367ab  add     ebp, edi
0x1800367ad  add     r8d, edi
0x1800367b0  cmp     r8d, [rdx+24h]
0x1800367b4  jb      short loc_18003677A
0x1800367b6  mov     rdx, [rdx]
0x1800367b9  cmp     rdx, r15
0x1800367bc  jnz     short loc_18003676F
0x1800367be  mov     rax, cs:WmipEventPumpOverlappedEvent
0x1800367c5  xorps   xmm0, xmm0
0x1800367c8  mov     rcx, cs:WmipEventPumpIo; pio
0x1800367cf  mov     [r9], ebp
0x1800367d2  movdqu  xmmword ptr cs:WmipEventPumpOverlapped.InternalHigh, xmm0
0x1800367da  mov     cs:WmipEventPumpOverlapped.hEvent, rax
0x1800367e1  mov     cs:WmipEventPumpOverlapped.Internal, 0
0x1800367ec  call    cs:__imp_StartThreadpoolIo
0x1800367f3  nop     dword ptr [rax+rax+00h]
0x1800367f8  mov     r8, cs:WmipEventPumpBuffer; lpInBuffer
0x1800367ff  lea     rax, WmipEventPumpOverlapped
0x180036806  mov     rcx, cs:WmipEventPumpTarget; hDevice
0x18003680d  mov     r9d, esi; nInBufferSize
0x180036810  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180036815  mov     edx, 228144h; dwIoControlCode
0x18003681a  mov     eax, cs:WmipEventPumpBufferSize
0x180036820  mov     [rsp+78h+lpBytesReturned], 0; lpBytesReturned
0x180036829  mov     [rsp+78h+nOutBufferSize], eax; nOutBufferSize
0x18003682d  mov     [rsp+78h+lpOutBuffer], r8; lpOutBuffer
0x180036832  call    cs:__imp_DeviceIoControl
0x180036839  nop     dword ptr [rax+rax+00h]
0x18003683e  test    eax, eax
0x180036840  jnz     short loc_180036880
0x180036842  call    cs:__imp_GetLastError
0x180036849  nop     dword ptr [rax+rax+00h]
0x18003684e  cmp     eax, 3E5h
0x180036853  jz      short loc_180036880
0x180036855  mov     rcx, cs:WmipEventPumpIo; pio
0x18003685c  call    cs:__imp_CancelThreadpoolIo
0x180036863  nop     dword ptr [rax+rax+00h]
0x180036868  mov     rcx, cs:WmipEventPumpModule; hLibModule
0x18003686f  call    cs:__imp_FreeLibrary
0x180036876  nop     dword ptr [rax+rax+00h]
0x18003687b  jmp     loc_1800366C5
0x180036880  mov     edi, 2
0x180036885  mov     cs:WmipEventPumpFlags, 0
0x18003688f  mov     cs:WmipEventPumpState, edi
0x180036895  add     rsp, 48h
0x180036899  pop     r15
0x18003689b  pop     r12
0x18003689d  pop     rdi
0x18003689e  pop     rsi
0x18003689f  pop     rbp
0x1800368a0  pop     rbx
0x1800368a1  retn
```
