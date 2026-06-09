# SrvReadConsole

- ea: `0x14001ff00`
- end: `0x14001ff71`
- name: `SrvReadConsole`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x14001e628`
- `0x14001f474`
- `0x14001ff00`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001ff59`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001ff59`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001ff27`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001ff27`

## pseudocode

```c
__int64 __fastcall SrvReadConsole(__int64 a1)
{
  __int64 v3; // rdx
  int v4; // edi
  __int64 v5; // r8
  __int64 v6; // r9

  if ( *(_QWORD *)(a1 + 328) )
    return 3221225480LL;
  RtlAcquireSRWLockExclusive(a1 + 104);
  v4 = CspQueueInputMessage(a1, 2 - (unsigned int)(*(_BYTE *)(a1 + 360) != 0));
  if ( v4 >= 0 )
  {
    CspTryCompleteReadRequest(a1, v3, v5, v6);
    v4 = 259;
  }
  RtlReleaseSRWLockExclusive(a1 + 104);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001ff00  mov     [rsp+arg_0], rbx
0x14001ff05  mov     [rsp+arg_8], rsi
0x14001ff0a  push    rdi
0x14001ff0b  sub     rsp, 20h
0x14001ff0f  cmp     qword ptr [rcx+148h], 0
0x14001ff17  mov     rbx, rcx
0x14001ff1a  jz      short loc_14001FF23
0x14001ff1c  mov     eax, 0C0000008h
0x14001ff21  jmp     short loc_14001FF61
0x14001ff23  add     rcx, 68h ; 'h'
0x14001ff27  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001ff2d  mov     al, [rbx+168h]
0x14001ff33  mov     rcx, rbx
0x14001ff36  neg     al
0x14001ff38  sbb     edx, edx
0x14001ff3a  add     edx, 2
0x14001ff3d  call    CspQueueInputMessage
0x14001ff42  mov     edi, eax
0x14001ff44  test    eax, eax
0x14001ff46  js      short loc_14001FF55
0x14001ff48  mov     rcx, rbx
0x14001ff4b  call    CspTryCompleteReadRequest
0x14001ff50  mov     edi, 103h
0x14001ff55  lea     rcx, [rbx+68h]
0x14001ff59  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001ff5f  mov     eax, edi
0x14001ff61  mov     rbx, [rsp+28h+arg_0]
0x14001ff66  mov     rsi, [rsp+28h+arg_8]
0x14001ff6b  add     rsp, 20h
0x14001ff6f  pop     rdi
0x14001ff70  retn
```
