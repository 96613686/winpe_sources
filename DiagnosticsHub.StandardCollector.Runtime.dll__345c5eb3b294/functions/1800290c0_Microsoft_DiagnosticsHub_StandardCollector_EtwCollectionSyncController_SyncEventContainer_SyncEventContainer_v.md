# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::SyncEventContainer(void)

- ea: `0x1800290c0`
- end: `0x180029137`
- name: `??0SyncEventContainer@EtwCollectionSyncController@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ`
- size: `119`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800290c0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800290ea`
- `KERNEL32!CreateEventW` at `0x1800290ea`
- `KERNEL32!GetLastError` at `0x180029101`
- `KERNEL32!GetLastError` at `0x18002911a`
- `KERNEL32!GetLastError` at `0x180029101`
- `KERNEL32!GetLastError` at `0x18002911a`

## pseudocode

```c
Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer *__fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer::SyncEventContainer(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSyncController::SyncEventContainer *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v4; // ecx

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = -1;
  *((_DWORD *)this + 4) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( EventW )
  {
    if ( GetLastError() == 183 )
      *((_DWORD *)this + 4) = 1;
  }
  else
  {
    *((_QWORD *)this + 1) = -1;
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
    *((_DWORD *)this + 4) = v4;
  }
  return this;
}

```

## disassembly

```asm
0x1800290c0  push    rbx
0x1800290c2  sub     rsp, 20h
0x1800290c6  mov     dword ptr [rcx], 0
0x1800290cc  xor     r9d, r9d; lpName
0x1800290cf  mov     rbx, rcx
0x1800290d2  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x1800290da  mov     dword ptr [rcx+10h], 0
0x1800290e1  xor     r8d, r8d; bInitialState
0x1800290e4  xor     ecx, ecx; lpEventAttributes
0x1800290e6  lea     edx, [r9+1]; bManualReset
0x1800290ea  call    cs:__imp_CreateEventW
0x1800290f0  mov     [rbx+8], rax
0x1800290f4  test    rax, rax
0x1800290f7  jnz     short loc_18002911A
0x1800290f9  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180029101  call    cs:__imp_GetLastError
0x180029107  movzx   ecx, ax
0x18002910a  or      ecx, 80070000h
0x180029110  test    eax, eax
0x180029112  cmovle  ecx, eax
0x180029115  mov     [rbx+10h], ecx
0x180029118  jmp     short loc_18002912E
0x18002911a  call    cs:__imp_GetLastError
0x180029120  cmp     eax, 0B7h
0x180029125  jnz     short loc_18002912E
0x180029127  mov     dword ptr [rbx+10h], 1
0x18002912e  mov     rax, rbx
0x180029131  add     rsp, 20h
0x180029135  pop     rbx
0x180029136  retn
```
