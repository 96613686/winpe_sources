# CRdpSessionAgentProxy::~CRdpSessionAgentProxy(void)

- ea: `0x1400034c8`
- end: `0x140003583`
- name: `??1CRdpSessionAgentProxy@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(CRdpSessionAgentProxy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400035a0`

## callees

- `0x1400034c8`
- `0x140006010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000351f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000351f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140003503`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140003503`
- `KERNEL32!CloseHandle` at `0x14000352e`
- `KERNEL32!CloseHandle` at `0x14000352e`
- `USER32!PostQuitMessage` at `0x140003540`
- `USER32!PostQuitMessage` at `0x140003540`
- `OLEAUT32!__imp_SysFreeString` at `0x140003538`
- `OLEAUT32!__imp_SysFreeString` at `0x140003538`

## pseudocode

```c
void __fastcall CRdpSessionAgentProxy::~CRdpSessionAgentProxy(CRdpSessionAgentProxy *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgent'};
  *((_QWORD *)this + 1) = &CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgentProxy'};
  *((_QWORD *)this + 2) = &CRdpSessionAgentProxy::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 3) = &CRdpSessionAgentProxy::`vftable'{for `CTSObject'};
  AcquireSRWLockExclusive(&CRdpSessionAgentProxy::s_lockSingleton);
  *((_DWORD *)this + 11) |= 4u;
  CRdpSessionAgentProxy::s_pSingleton = 0;
  ReleaseSRWLockExclusive(&CRdpSessionAgentProxy::s_lockSingleton);
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
    CloseHandle(v2);
  SysFreeString(*((BSTR *)this + 12));
  PostQuitMessage(0);
  v3 = *((_QWORD *)this + 8);
  if ( v3 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  *((_DWORD *)this + 11) |= 8u;
  *((_QWORD *)this + 2) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 3) = &CTSObject::`vftable';
}

```

## disassembly

```asm
0x1400034c8  push    rbx
0x1400034ca  sub     rsp, 20h
0x1400034ce  lea     rax, ??_7CRdpSessionAgentProxy@@6BIRdpSessionAgent@@@; const CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgent'}
0x1400034d5  mov     rbx, rcx
0x1400034d8  mov     [rcx], rax
0x1400034db  lea     rax, ??_7CRdpSessionAgentProxy@@6BIRdpSessionAgentProxy@@@; const CRdpSessionAgentProxy::`vftable'{for `IRdpSessionAgentProxy'}
0x1400034e2  mov     [rcx+8], rax
0x1400034e6  lea     rax, ??_7CRdpSessionAgentProxy@@6BINonDelegatingUnknown@@@; const CRdpSessionAgentProxy::`vftable'{for `INonDelegatingUnknown'}
0x1400034ed  mov     [rcx+10h], rax
0x1400034f1  lea     rax, ??_7CRdpSessionAgentProxy@@6BCTSObject@@@; const CRdpSessionAgentProxy::`vftable'{for `CTSObject'}
0x1400034f8  mov     [rcx+18h], rax
0x1400034fc  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SRWLock
0x140003503  call    cs:__imp_AcquireSRWLockExclusive
0x140003509  or      dword ptr [rbx+2Ch], 4
0x14000350d  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SRWLock
0x140003514  mov     cs:?s_pSingleton@CRdpSessionAgentProxy@@0PEAV1@EA, 0; CRdpSessionAgentProxy * CRdpSessionAgentProxy::s_pSingleton
0x14000351f  call    cs:__imp_ReleaseSRWLockExclusive
0x140003525  mov     rcx, [rbx+58h]; hObject
0x140003529  test    rcx, rcx
0x14000352c  jz      short loc_140003534
0x14000352e  call    cs:__imp_CloseHandle
0x140003534  mov     rcx, [rbx+60h]; bstrString
0x140003538  call    cs:__imp_SysFreeString
0x14000353e  xor     ecx, ecx; nExitCode
0x140003540  call    cs:__imp_PostQuitMessage
0x140003546  mov     rcx, [rbx+40h]
0x14000354a  test    rcx, rcx
0x14000354d  jz      short loc_140003563
0x14000354f  mov     qword ptr [rbx+40h], 0
0x140003557  mov     rax, [rcx]
0x14000355a  mov     rax, [rax+10h]
0x14000355e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003563  or      dword ptr [rbx+2Ch], 8
0x140003567  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x14000356e  mov     [rbx+10h], rax
0x140003572  lea     rax, ??_7CTSObject@@6B@; const CTSObject::`vftable'
0x140003579  mov     [rbx+18h], rax
0x14000357d  add     rsp, 20h
0x140003581  pop     rbx
0x140003582  retn
```
