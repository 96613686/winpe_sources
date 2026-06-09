# ServiceMain

- ea: `0x18000c050`
- end: `0x18000c0a0`
- name: `ServiceMain`
- size: `80`
- prototype: `void __fastcall(int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c050`
- `0x18000caa8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c071`
- `msvcrt!_wcsicmp` at `0x18000c071`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000c07b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000c07b`
- `combase!__imp_CoGetSharedServiceId` at `0x18000c088`
- `combase!__imp_CoGetSharedServiceId` at `0x18000c088`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const unsigned __int16 **a2)
{
  unsigned int v3; // edx
  ServiceBase *v4; // rcx

  if ( a1 )
  {
    if ( a2 && a1 == 2 && !_wcsicmp(a2[1], L"debug") )
      DebugBreak();
    if ( (int)CoGetSharedServiceId(&RWService::g_ulServiceId) >= 0 )
      ServiceBase::ServiceMain(v4, v3, a2);
  }
}

```

## disassembly

```asm
0x18000c050  test    ecx, ecx
0x18000c052  jz      short locret_18000C09F
0x18000c054  push    rbx
0x18000c055  sub     rsp, 20h
0x18000c059  mov     rbx, rdx
0x18000c05c  test    rdx, rdx
0x18000c05f  jz      short loc_18000C081
0x18000c061  cmp     ecx, 2
0x18000c064  jnz     short loc_18000C081
0x18000c066  mov     rcx, [rbx+8]; String1
0x18000c06a  lea     rdx, aDebug; "debug"
0x18000c071  call    cs:__imp__wcsicmp
0x18000c077  test    eax, eax
0x18000c079  jnz     short loc_18000C081
0x18000c07b  call    cs:__imp_DebugBreak
0x18000c081  lea     rcx, ?g_ulServiceId@RWService@@2KA; ulong RWService::g_ulServiceId
0x18000c088  call    cs:__imp_CoGetSharedServiceId
0x18000c08e  test    eax, eax
0x18000c090  js      short loc_18000C09A
0x18000c092  mov     r8, rbx; unsigned __int16 **
0x18000c095  call    ?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z; ServiceBase::ServiceMain(ulong,ushort const * *)
0x18000c09a  add     rsp, 20h
0x18000c09e  pop     rbx
0x18000c09f  retn
```
