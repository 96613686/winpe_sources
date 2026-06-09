# DiagHubCommon::HubTask<long,0>::HubTask<long,0>(void)

- ea: `0x1800084d0`
- end: `0x18000856a`
- name: `??0?$HubTask@J$0A@@DiagHubCommon@@QEAA@XZ`
- size: `154`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004298`
- `0x180027e64`
- `0x18002b798`

## callees

- `0x1800084d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180008516`
- `KERNEL32!CreateEventW` at `0x180008516`
- `KERNEL32!GetLastError` at `0x18000852d`
- `KERNEL32!GetLastError` at `0x180008546`
- `KERNEL32!GetLastError` at `0x18000852d`
- `KERNEL32!GetLastError` at `0x180008546`

## pseudocode

```c
__int64 __fastcall DiagHubCommon::HubTask<long,0>::HubTask<long,0>(__int64 a1)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v4; // ecx

  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &DiagHubCommon::HubTask<long,0>::`vftable';
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = -1;
  *(_DWORD *)(a1 + 96) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 88) = EventW;
  if ( EventW )
  {
    if ( GetLastError() == 183 )
      *(_DWORD *)(a1 + 96) = 1;
  }
  else
  {
    *(_QWORD *)(a1 + 88) = -1;
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
    *(_DWORD *)(a1 + 96) = v4;
  }
  *(_DWORD *)(a1 + 104) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800084d0  push    rbx
0x1800084d2  sub     rsp, 20h
0x1800084d6  mov     qword ptr [rcx+8], 0
0x1800084de  lea     rax, ??_7?$HubTask@J$0A@@DiagHubCommon@@6B@; const DiagHubCommon::HubTask<long,0>::`vftable'
0x1800084e5  mov     [rcx], rax
0x1800084e8  xor     r9d, r9d; lpName
0x1800084eb  mov     qword ptr [rcx+48h], 0
0x1800084f3  mov     rbx, rcx
0x1800084f6  mov     qword ptr [rcx+50h], 0
0x1800084fe  xor     r8d, r8d; bInitialState
0x180008501  mov     qword ptr [rcx+58h], 0FFFFFFFFFFFFFFFFh
0x180008509  mov     dword ptr [rcx+60h], 0
0x180008510  lea     edx, [r9+1]; bManualReset
0x180008514  xor     ecx, ecx; lpEventAttributes
0x180008516  call    cs:__imp_CreateEventW
0x18000851c  mov     [rbx+58h], rax
0x180008520  test    rax, rax
0x180008523  jnz     short loc_180008546
0x180008525  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x18000852d  call    cs:__imp_GetLastError
0x180008533  movzx   ecx, ax
0x180008536  or      ecx, 80070000h
0x18000853c  test    eax, eax
0x18000853e  cmovle  ecx, eax
0x180008541  mov     [rbx+60h], ecx
0x180008544  jmp     short loc_18000855A
0x180008546  call    cs:__imp_GetLastError
0x18000854c  cmp     eax, 0B7h
0x180008551  jnz     short loc_18000855A
0x180008553  mov     dword ptr [rbx+60h], 1
0x18000855a  mov     dword ptr [rbx+68h], 0
0x180008561  mov     rax, rbx
0x180008564  add     rsp, 20h
0x180008568  pop     rbx
0x180008569  retn
```
