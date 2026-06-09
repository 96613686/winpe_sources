# CreateTapiThread(void)

- ea: `0x14004d270`
- end: `0x14004d34f`
- name: `?CreateTapiThread@@YAHXZ`
- size: `223`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140049f40`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14004d270`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004d2ec`
- `KERNEL32!GetLastError` at `0x14004d2ec`
- `KERNEL32!SetLastError` at `0x14004d330`
- `KERNEL32!SetLastError` at `0x14004d330`
- `KERNEL32!CreateThread` at `0x14004d2d4`
- `KERNEL32!CreateThread` at `0x14004d2d4`

## pseudocode

```c
_BOOL8 CreateTapiThread(void)
{
  DWORD v0; // ebx
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  v0 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  g_hTapiWorkerThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)TapiWorkerThread, 0, 0, &ThreadId);
  if ( !g_hTapiWorkerThread )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, LastError);
    }
    if ( v0 )
      SetLastError(v0);
  }
  return v0 == 0;
}

```

## disassembly

```asm
0x14004d270  mov     [rsp+arg_8], rbx
0x14004d275  push    rdi
0x14004d276  sub     rsp, 30h
0x14004d27a  mov     [rsp+38h+ThreadId], 0
0x14004d282  xor     ebx, ebx
0x14004d284  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d28b  lea     rdi, WPP_GLOBAL_Control
0x14004d292  cmp     rcx, rdi
0x14004d295  jz      short loc_14004D2B8
0x14004d297  test    byte ptr [rcx+1Ch], 4
0x14004d29b  jz      short loc_14004D2B8
0x14004d29d  cmp     byte ptr [rcx+19h], 5
0x14004d2a1  jb      short loc_14004D2B8
0x14004d2a3  mov     rcx, [rcx+10h]
0x14004d2a7  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004d2ae  mov     edx, 8Fh
0x14004d2b3  call    WPP_SF_
0x14004d2b8  lea     rax, [rsp+38h+ThreadId]
0x14004d2bd  xor     r9d, r9d; lpParameter
0x14004d2c0  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14004d2c5  lea     r8, ?TapiWorkerThread@@YAKPEAX@Z; lpStartAddress
0x14004d2cc  xor     edx, edx; dwStackSize
0x14004d2ce  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x14004d2d2  xor     ecx, ecx; lpThreadAttributes
0x14004d2d4  call    cs:__imp_CreateThread
0x14004d2db  nop     dword ptr [rax+rax+00h]
0x14004d2e0  mov     cs:?g_hTapiWorkerThread@@3PEAXEA, rax; void * g_hTapiWorkerThread
0x14004d2e7  test    rax, rax
0x14004d2ea  jnz     short loc_14004D33C
0x14004d2ec  call    cs:__imp_GetLastError
0x14004d2f3  nop     dword ptr [rax+rax+00h]
0x14004d2f8  mov     ebx, eax
0x14004d2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d301  cmp     rcx, rdi
0x14004d304  jz      short loc_14004D32A
0x14004d306  test    byte ptr [rcx+1Ch], 4
0x14004d30a  jz      short loc_14004D32A
0x14004d30c  cmp     byte ptr [rcx+19h], 2
0x14004d310  jb      short loc_14004D32A
0x14004d312  mov     rcx, [rcx+10h]
0x14004d316  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004d31d  mov     edx, 90h
0x14004d322  mov     r9d, eax
0x14004d325  call    WPP_SF_d
0x14004d32a  test    ebx, ebx
0x14004d32c  jz      short loc_14004D33C
0x14004d32e  mov     ecx, ebx; dwErrCode
0x14004d330  call    cs:__imp_SetLastError
0x14004d337  nop     dword ptr [rax+rax+00h]
0x14004d33c  xor     eax, eax
0x14004d33e  test    ebx, ebx
0x14004d340  mov     rbx, [rsp+38h+arg_8]
0x14004d345  setz    al
0x14004d348  add     rsp, 30h
0x14004d34c  pop     rdi
0x14004d34d  retn
```
