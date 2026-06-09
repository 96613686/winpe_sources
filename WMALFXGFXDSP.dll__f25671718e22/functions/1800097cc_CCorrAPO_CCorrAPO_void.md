# CCorrAPO::~CCorrAPO(void)

- ea: `0x1800097cc`
- end: `0x180009849`
- name: `??1CCorrAPO@@UEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CCorrAPO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009794`

## callees

- `0x180009850`
- `0x1800098e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009836`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009836`

## pseudocode

```c
void __fastcall CCorrAPO::~CCorrAPO(CCorrAPO *this)
{
  *(_QWORD *)this = &CCorrAPO::`vftable'{for `CWMDSPPropImpl'};
  *((_QWORD *)this + 11) = &CCorrAPO::`vftable'{for `CWMDSPComBase'};
  *((_QWORD *)this + 14) = &CCorrAPO::`vftable'{for `IAudioProcessingObject'};
  *((_QWORD *)this + 15) = &CCorrAPO::`vftable'{for `IAudioProcessingObjectRT'};
  *((_QWORD *)this + 16) = &CCorrAPOBase::`vftable'{for `IAudioProcessingObjectConfiguration'};
  *((_QWORD *)this + 50) = &CCorrAPO::`vftable'{for `IAudioSystemEffects2'};
  *((_QWORD *)this + 51) = &CCorrAPO::`vftable'{for `IMMNotificationClient'};
  CCorrAPO::FreeNotificationStuff(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  CCorrAPOBase::~CCorrAPOBase((struct _RTL_CRITICAL_SECTION *)this);
}

```

## disassembly

```asm
0x1800097cc  push    rbx
0x1800097ce  sub     rsp, 20h
0x1800097d2  lea     rax, ??_7CCorrAPO@@6BCWMDSPPropImpl@@@; const CCorrAPO::`vftable'{for `CWMDSPPropImpl'}
0x1800097d9  mov     rbx, rcx
0x1800097dc  mov     [rcx], rax
0x1800097df  lea     rax, ??_7CCorrAPO@@6BCWMDSPComBase@@@; const CCorrAPO::`vftable'{for `CWMDSPComBase'}
0x1800097e6  mov     [rcx+58h], rax
0x1800097ea  lea     rax, ??_7CCorrAPO@@6BIAudioProcessingObject@@@; const CCorrAPO::`vftable'{for `IAudioProcessingObject'}
0x1800097f1  mov     [rcx+70h], rax
0x1800097f5  lea     rax, ??_7CCorrAPO@@6BIAudioProcessingObjectRT@@@; const CCorrAPO::`vftable'{for `IAudioProcessingObjectRT'}
0x1800097fc  mov     [rcx+78h], rax
0x180009800  lea     rax, ??_7CCorrAPOBase@@6BIAudioProcessingObjectConfiguration@@@; const CCorrAPOBase::`vftable'{for `IAudioProcessingObjectConfiguration'}
0x180009807  mov     [rcx+80h], rax
0x18000980e  lea     rax, ??_7CCorrAPO@@6BIAudioSystemEffects2@@@; const CCorrAPO::`vftable'{for `IAudioSystemEffects2'}
0x180009815  mov     [rcx+190h], rax
0x18000981c  lea     rax, ??_7CCorrAPO@@6BIMMNotificationClient@@@; const CCorrAPO::`vftable'{for `IMMNotificationClient'}
0x180009823  mov     [rcx+198h], rax
0x18000982a  call    ?FreeNotificationStuff@CCorrAPO@@QEAAXXZ; CCorrAPO::FreeNotificationStuff(void)
0x18000982f  lea     rcx, [rbx+1A0h]; lpCriticalSection
0x180009836  call    cs:__imp_DeleteCriticalSection
0x18000983c  mov     rcx, rbx; this
0x18000983f  add     rsp, 20h
0x180009843  pop     rbx
0x180009844  jmp     ??1CCorrAPOBase@@UEAA@XZ; CCorrAPOBase::~CCorrAPOBase(void)
```
