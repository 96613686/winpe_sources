# CheckForOpenHandles

- ea: `0x140005960`
- end: `0x140005af0`
- name: `CheckForOpenHandles`
- size: `400`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140007124`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140005960`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400059df`
- `KERNEL32!GetLastError` at `0x1400059df`
- `KERNEL32!CreateEventW` at `0x1400059d1`
- `KERNEL32!CreateEventW` at `0x1400059d1`
- `KERNEL32!WaitForSingleObject` at `0x140005a33`
- `KERNEL32!WaitForSingleObject` at `0x140005a33`
- `KERNEL32!CloseHandle` at `0x140005a54`
- `KERNEL32!CloseHandle` at `0x140005a54`
- `ntdll!NtFsControlFile` at `0x140005a20`
- `ntdll!NtFsControlFile` at `0x140005a20`
- `ntdll!RtlNtStatusToDosError` at `0x140005adb`
- `ntdll!RtlNtStatusToDosError` at `0x140005adb`

## pseudocode

```c
ULONG CheckForOpenHandles()
{
  _QWORD *v0; // rcx
  HANDLE EventW; // rsi
  DWORD v3; // ebx
  unsigned int Status; // edi
  _QWORD *v5; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
      WPP_SF_(v0[2], 31, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return GetLastError();
  v3 = 0;
  if ( NtFsControlFile(hDevice, EventW, 0, 0, &IoStatusBlock, 0x14094Cu, 0, 0, 0, 0) != 259
    || (v3 = WaitForSingleObject(EventW, 0xFFFFFFFF), Status = -1073741823, v3 != -1) )
  {
    Status = IoStatusBlock.Status;
  }
  if ( v3 != -1 )
    v3 = 0;
  CloseHandle(EventW);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    {
      WPP_SF_d(v5[2], 33, WPP_e7926938627732e63f903c41c3c41751_Traceguids, Status);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( Status == -2147483613 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
      WPP_SF_(v5[2], 34, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
    return 1794;
  }
  else
  {
    if ( !v3 )
      return RtlNtStatusToDosError(Status);
    return v3;
  }
}

```

## disassembly

```asm
0x140005960  push    rbx
0x140005962  push    rbp
0x140005963  push    rsi
0x140005964  push    rdi
0x140005965  push    r14
0x140005967  sub     rsp, 60h
0x14000596b  xorps   xmm0, xmm0
0x14000596e  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x140005973  mov     rcx, cs:WPP_GLOBAL_Control
0x14000597a  lea     rbp, WPP_GLOBAL_Control
0x140005981  lea     r14, WPP_e7926938627732e63f903c41c3c41751_Traceguids
0x140005988  cmp     rcx, rbp
0x14000598b  jz      short loc_1400059C7
0x14000598d  test    byte ptr [rcx+1Ch], 1
0x140005991  jz      short loc_1400059AB
0x140005993  mov     rcx, [rcx+10h]
0x140005997  mov     edx, 1Eh
0x14000599c  mov     r8, r14
0x14000599f  call    WPP_SF_
0x1400059a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059ab  cmp     rcx, rbp
0x1400059ae  jz      short loc_1400059C7
0x1400059b0  test    byte ptr [rcx+1Ch], 8
0x1400059b4  jz      short loc_1400059C7
0x1400059b6  mov     rcx, [rcx+10h]
0x1400059ba  mov     edx, 1Fh
0x1400059bf  mov     r8, r14
0x1400059c2  call    WPP_SF_
0x1400059c7  xor     r9d, r9d; lpName
0x1400059ca  xor     r8d, r8d; bInitialState
0x1400059cd  xor     edx, edx; bManualReset
0x1400059cf  xor     ecx, ecx; lpEventAttributes
0x1400059d1  call    cs:__imp_CreateEventW
0x1400059d7  mov     rsi, rax
0x1400059da  test    rax, rax
0x1400059dd  jnz     short loc_1400059EA
0x1400059df  call    cs:__imp_GetLastError
0x1400059e5  jmp     loc_140005AE5
0x1400059ea  mov     rcx, cs:hDevice; FileHandle
0x1400059f1  lea     rax, [rsp+88h+var_38]
0x1400059f6  xor     ebx, ebx
0x1400059f8  xor     r9d, r9d; ApcContext
0x1400059fb  mov     [rsp+88h+OutputBufferLength], ebx; OutputBufferLength
0x1400059ff  xor     r8d, r8d; ApcRoutine
0x140005a02  mov     [rsp+88h+OutputBuffer], rbx; OutputBuffer
0x140005a07  mov     rdx, rsi; Event
0x140005a0a  mov     [rsp+88h+InputBufferLength], ebx; InputBufferLength
0x140005a0e  mov     [rsp+88h+InputBuffer], rbx; InputBuffer
0x140005a13  mov     [rsp+88h+FsControlCode], 14094Ch; FsControlCode
0x140005a1b  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x140005a20  call    cs:__imp_NtFsControlFile
0x140005a26  cmp     eax, 103h
0x140005a2b  jnz     short loc_140005A45
0x140005a2d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005a30  mov     rcx, rsi; hHandle
0x140005a33  call    cs:__imp_WaitForSingleObject
0x140005a39  mov     ebx, eax
0x140005a3b  mov     edi, 0C0000001h
0x140005a40  cmp     eax, 0FFFFFFFFh
0x140005a43  jz      short loc_140005A49
0x140005a45  mov     edi, dword ptr [rsp+88h+var_38]
0x140005a49  xor     eax, eax
0x140005a4b  mov     rcx, rsi; hObject
0x140005a4e  cmp     ebx, 0FFFFFFFFh
0x140005a51  cmovnz  ebx, eax
0x140005a54  call    cs:__imp_CloseHandle
0x140005a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a61  cmp     rcx, rbp
0x140005a64  jz      short loc_140005AAA
0x140005a66  test    byte ptr [rcx+1Ch], 8
0x140005a6a  jz      short loc_140005A84
0x140005a6c  mov     rcx, [rcx+10h]
0x140005a70  mov     edx, 20h ; ' '
0x140005a75  mov     r8, r14
0x140005a78  call    WPP_SF_
0x140005a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a84  cmp     rcx, rbp
0x140005a87  jz      short loc_140005AAA
0x140005a89  test    byte ptr [rcx+1Ch], 8
0x140005a8d  jz      short loc_140005AAA
0x140005a8f  mov     rcx, [rcx+10h]
0x140005a93  mov     edx, 21h ; '!'
0x140005a98  mov     r9d, edi
0x140005a9b  mov     r8, r14
0x140005a9e  call    WPP_SF_d
0x140005aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140005aaa  cmp     edi, 80000023h
0x140005ab0  jnz     short loc_140005AD5
0x140005ab2  cmp     rcx, rbp
0x140005ab5  jz      short loc_140005ACE
0x140005ab7  test    byte ptr [rcx+1Ch], 2
0x140005abb  jz      short loc_140005ACE
0x140005abd  mov     rcx, [rcx+10h]
0x140005ac1  mov     edx, 22h ; '"'
0x140005ac6  mov     r8, r14
0x140005ac9  call    WPP_SF_
0x140005ace  mov     eax, 702h
0x140005ad3  jmp     short loc_140005AE5
0x140005ad5  test    ebx, ebx
0x140005ad7  jnz     short loc_140005AE3
0x140005ad9  mov     ecx, edi; Status
0x140005adb  call    cs:__imp_RtlNtStatusToDosError
0x140005ae1  mov     ebx, eax
0x140005ae3  mov     eax, ebx
0x140005ae5  add     rsp, 60h
0x140005ae9  pop     r14
0x140005aeb  pop     rdi
0x140005aec  pop     rsi
0x140005aed  pop     rbp
0x140005aee  pop     rbx
0x140005aef  retn
```
