# CMpeg2PBDAPESStreamParser::~CMpeg2PBDAPESStreamParser(void)

- ea: `0x18002c514`
- end: `0x18002c596`
- name: `??1CMpeg2PBDAPESStreamParser@@UEAA@XZ`
- size: `130`
- prototype: `void __fastcall(CMpeg2PBDAPESStreamParser *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c7b0`

## callees

- `0x180028640`
- `0x18002c514`
- `0x18002c688`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002c56b`
- `KERNEL32!DeleteCriticalSection` at `0x18002c56b`
- `WINMM!timeKillEvent` at `0x18002c554`
- `WINMM!timeKillEvent` at `0x18002c554`

## pseudocode

```c
void __fastcall CMpeg2PBDAPESStreamParser::~CMpeg2PBDAPESStreamParser(CMpeg2PBDAPESStreamParser *this)
{
  CMpeg2PESStreamParser *v2; // rdi
  UINT v3; // ecx

  *(_QWORD *)this = &CMpeg2PBDAPESStreamParser::`vftable';
  v2 = (CMpeg2PBDAPESStreamParser *)((char *)this + 2536);
  *((_QWORD *)this + 317) = &CMpeg2PBDAPESStreamParser::`vftable'{for `CDemuxBaseParser'};
  *((_QWORD *)this + 323) = &CMpeg2PBDAPESStreamParser::`vftable'{for `CBufferSourceManager'};
  v3 = *((_DWORD *)this + 893);
  if ( v3 )
  {
    timeKillEvent(v3);
    *((_DWORD *)this + 893) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 3576));
  CMpeg2PESStreamParser::~CMpeg2PESStreamParser(v2);
  *(_QWORD *)this = &CMpeg2PBDAParser::`vftable';
  CTAGTables::~CTAGTables((CMpeg2PBDAPESStreamParser *)((char *)this + 8));
}

```

## disassembly

```asm
0x18002c514  mov     [rsp+arg_0], rbx
0x18002c519  push    rdi
0x18002c51a  sub     rsp, 20h
0x18002c51e  lea     rax, ??_7CMpeg2PBDAPESStreamParser@@6B@; const CMpeg2PBDAPESStreamParser::`vftable'
0x18002c525  mov     rbx, rcx
0x18002c528  mov     [rcx], rax
0x18002c52b  lea     rdi, [rcx+9E8h]
0x18002c532  lea     rax, ??_7CMpeg2PBDAPESStreamParser@@6BCDemuxBaseParser@@@; const CMpeg2PBDAPESStreamParser::`vftable'{for `CDemuxBaseParser'}
0x18002c539  mov     [rdi], rax
0x18002c53c  lea     rax, ??_7CMpeg2PBDAPESStreamParser@@6BCBufferSourceManager@@@; const CMpeg2PBDAPESStreamParser::`vftable'{for `CBufferSourceManager'}
0x18002c543  mov     [rcx+0A18h], rax
0x18002c54a  mov     ecx, [rcx+0DF4h]; uTimerID
0x18002c550  test    ecx, ecx
0x18002c552  jz      short loc_18002C564
0x18002c554  call    cs:__imp_timeKillEvent
0x18002c55a  mov     dword ptr [rbx+0DF4h], 0
0x18002c564  lea     rcx, [rbx+0DF8h]; lpCriticalSection
0x18002c56b  call    cs:__imp_DeleteCriticalSection
0x18002c571  mov     rcx, rdi; this
0x18002c574  call    ??1CMpeg2PESStreamParser@@UEAA@XZ; CMpeg2PESStreamParser::~CMpeg2PESStreamParser(void)
0x18002c579  lea     rax, ??_7CMpeg2PBDAParser@@6B@; const CMpeg2PBDAParser::`vftable'
0x18002c580  lea     rcx, [rbx+8]; this
0x18002c584  mov     [rbx], rax
0x18002c587  mov     rbx, [rsp+28h+arg_0]
0x18002c58c  add     rsp, 20h
0x18002c590  pop     rdi
0x18002c591  jmp     ??1CTAGTables@@QEAA@XZ; CTAGTables::~CTAGTables(void)
```
