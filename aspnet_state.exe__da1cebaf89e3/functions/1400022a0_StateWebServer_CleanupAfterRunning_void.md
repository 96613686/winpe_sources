# StateWebServer::CleanupAfterRunning(void)

- ea: `0x1400022a0`
- end: `0x1400022e3`
- name: `?CleanupAfterRunning@StateWebServer@@AEAAXXZ`
- size: `67`
- prototype: `void __fastcall(StateWebServer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001a20`
- `0x140002678`

## callees

- `0x1400022a0`
- `0x140004e38`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x1400022c8`
- `WS2_32!__imp_WSACleanup` at `0x1400022c8`
- `KERNEL32!CloseHandle` at `0x1400022bc`
- `KERNEL32!CloseHandle` at `0x1400022d7`
- `KERNEL32!CloseHandle` at `0x1400022bc`
- `KERNEL32!CloseHandle` at `0x1400022d7`

## pseudocode

```c
void __fastcall StateWebServer::CleanupAfterRunning(StateWebServer *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *((_BYTE *)this + 73) = 1;
  Tracker::staticCleanup();
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 != (void *)-1LL )
    CloseHandle(v2);
  if ( *((_BYTE *)this + 4) )
    WSACleanup();
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CloseHandle(v3);
}

```

## disassembly

```asm
0x1400022a0  push    rbx
0x1400022a2  sub     rsp, 20h
0x1400022a6  mov     rbx, rcx
0x1400022a9  mov     byte ptr [rcx+49h], 1
0x1400022ad  call    ?staticCleanup@Tracker@@SAXXZ; Tracker::staticCleanup(void)
0x1400022b2  mov     rcx, [rbx+40h]; hObject
0x1400022b6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400022ba  jz      short loc_1400022C2
0x1400022bc  call    cs:__imp_CloseHandle
0x1400022c2  cmp     byte ptr [rbx+4], 0
0x1400022c6  jz      short loc_1400022CE
0x1400022c8  call    cs:__imp_WSACleanup
0x1400022ce  mov     rcx, [rbx+18h]; hObject
0x1400022d2  test    rcx, rcx
0x1400022d5  jz      short loc_1400022DD
0x1400022d7  call    cs:__imp_CloseHandle
0x1400022dd  add     rsp, 20h
0x1400022e1  pop     rbx
0x1400022e2  retn
```
