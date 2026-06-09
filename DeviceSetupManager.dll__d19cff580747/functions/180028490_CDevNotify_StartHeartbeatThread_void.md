# CDevNotify::_StartHeartbeatThread(void)

- ea: `0x180028490`
- end: `0x180028582`
- name: `?_StartHeartbeatThread@CDevNotify@@CAJXZ`
- size: `242`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002875c`

## callees

- `0x180021790`
- `0x180022070`
- `0x180028490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800284d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800284d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800284e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800284e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028532`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002851c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002851c`

## pseudocode

```c
__int64 CDevNotify::_StartHeartbeatThread(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  signed int v2; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids);
  CDevNotify::_hEvent = CreateEventW(0, 0, 0, 0);
  if ( !CDevNotify::_hEvent )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
      goto LABEL_14;
  }
  CDevNotify::_hThread = CreateThread(0, 0, CDevNotify::_HeartbeatThreadEntry, 0, 0, 0);
  if ( CDevNotify::_hThread )
    return 0;
  v2 = GetLastError();
  v1 = v2;
  if ( v2 > 0 )
    v1 = (unsigned __int16)v2 | 0x80070000;
  if ( v1 < 0 )
  {
LABEL_14:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids,
        (unsigned int)v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180028490  mov     [rsp+arg_0], rbx
0x180028495  push    rdi
0x180028496  sub     rsp, 30h
0x18002849a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284a1  lea     rdi, WPP_GLOBAL_Control
0x1800284a8  cmp     rcx, rdi
0x1800284ab  jz      short loc_1800284C8
0x1800284ad  test    byte ptr [rcx+1Ch], 20h
0x1800284b1  jz      short loc_1800284C8
0x1800284b3  mov     rcx, [rcx+10h]
0x1800284b7  lea     r8, WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids
0x1800284be  mov     edx, 1Fh
0x1800284c3  call    WPP_SF_
0x1800284c8  xor     r9d, r9d; lpName
0x1800284cb  xor     r8d, r8d; bInitialState
0x1800284ce  xor     edx, edx; bManualReset
0x1800284d0  xor     ecx, ecx; lpEventAttributes
0x1800284d2  call    cs:__imp_CreateEventW
0x1800284d8  mov     cs:?_hEvent@CDevNotify@@0PEAXEA, rax; void * CDevNotify::_hEvent
0x1800284df  test    rax, rax
0x1800284e2  jnz     short loc_1800284FD
0x1800284e4  call    cs:__imp_GetLastError
0x1800284ea  mov     ebx, eax
0x1800284ec  test    eax, eax
0x1800284ee  jle     short loc_1800284F9
0x1800284f0  movzx   ebx, ax
0x1800284f3  or      ebx, 80070000h
0x1800284f9  test    ebx, ebx
0x1800284fb  js      short loc_18002854B
0x1800284fd  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180028506  lea     r8, ?_HeartbeatThreadEntry@CDevNotify@@CAKPEAX@Z; lpStartAddress
0x18002850d  xor     r9d, r9d; lpParameter
0x180028510  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180028518  xor     edx, edx; dwStackSize
0x18002851a  xor     ecx, ecx; lpThreadAttributes
0x18002851c  call    cs:__imp_CreateThread
0x180028522  mov     cs:?_hThread@CDevNotify@@0PEAXEA, rax; void * CDevNotify::_hThread
0x180028529  test    rax, rax
0x18002852c  jz      short loc_180028532
0x18002852e  xor     ebx, ebx
0x180028530  jmp     short loc_180028575
0x180028532  call    cs:__imp_GetLastError
0x180028538  mov     ebx, eax
0x18002853a  test    eax, eax
0x18002853c  jle     short loc_180028547
0x18002853e  movzx   ebx, ax
0x180028541  or      ebx, 80070000h
0x180028547  test    ebx, ebx
0x180028549  jns     short loc_180028575
0x18002854b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028552  cmp     rcx, rdi
0x180028555  jz      short loc_180028575
0x180028557  test    byte ptr [rcx+1Ch], 4
0x18002855b  jz      short loc_180028575
0x18002855d  mov     rcx, [rcx+10h]
0x180028561  lea     r8, WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids
0x180028568  mov     edx, 20h ; ' '
0x18002856d  mov     r9d, ebx
0x180028570  call    WPP_SF_d
0x180028575  mov     eax, ebx
0x180028577  mov     rbx, [rsp+38h+arg_0]
0x18002857c  add     rsp, 30h
0x180028580  pop     rdi
0x180028581  retn
```
