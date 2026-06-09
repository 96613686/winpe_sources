# MI_Application_NewSession

- ea: `0x18000a1bc`
- end: `0x18000a224`
- name: `MI_Application_NewSession`
- size: `104`
- prototype: `static MI_Result __stdcall(MI_Application *application, const MI_Char *protocol, const MI_Char *destination, MI_DestinationOptions *options, MI_SessionCallbacks *callbacks, MI_Instance **extendedError, MI_Session *session)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007edc`
- `0x180009304`

## callees

- `0x18000a1bc`
- `0x180021010`

## pseudocode

```c
MI_Result __stdcall MI_Application_NewSession(
        MI_Application *application,
        const MI_Char *protocol,
        const MI_Char *destination,
        MI_DestinationOptions *options,
        MI_SessionCallbacks *callbacks,
        MI_Instance **extendedError,
        MI_Session *session)
{
  const MI_ApplicationFT *ft; // rax

  if ( application )
  {
    ft = application->ft;
    if ( ft )
      return ((unsigned int (__fastcall *)(MI_Application *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, MI_Session *))ft->NewSession)(
               application,
               0,
               0,
               0,
               0,
               0,
               session);
  }
  if ( session )
  {
    *(_OWORD *)&session->reserved1 = 0;
    session->ft = 0;
  }
  return 4;
}

```

## disassembly

```asm
0x18000a1bc  sub     rsp, 48h
0x18000a1c0  test    rcx, rcx
0x18000a1c3  jz      short loc_18000A200
0x18000a1c5  mov     rax, [rcx+10h]
0x18000a1c9  test    rax, rax
0x18000a1cc  jz      short loc_18000A200
0x18000a1ce  mov     rdx, [rsp+48h+session]
0x18000a1d6  xor     r9d, r9d
0x18000a1d9  mov     rax, [rax+8]
0x18000a1dd  xor     r8d, r8d
0x18000a1e0  mov     [rsp+48h+var_18], rdx
0x18000a1e5  xor     edx, edx
0x18000a1e7  mov     [rsp+48h+var_20], 0
0x18000a1f0  mov     [rsp+48h+var_28], 0
0x18000a1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fe  jmp     short loc_18000A21E
0x18000a200  mov     rax, [rsp+48h+session]
0x18000a208  test    rax, rax
0x18000a20b  jz      short loc_18000A219
0x18000a20d  xorps   xmm0, xmm0
0x18000a210  xor     ecx, ecx
0x18000a212  movups  xmmword ptr [rax], xmm0
0x18000a215  mov     [rax+10h], rcx
0x18000a219  mov     eax, 4
0x18000a21e  add     rsp, 48h
0x18000a222  retn
```
