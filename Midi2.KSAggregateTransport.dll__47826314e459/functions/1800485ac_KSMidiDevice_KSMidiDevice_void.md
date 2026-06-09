# KSMidiDevice::~KSMidiDevice(void)

- ea: `0x1800485ac`
- end: `0x18004866a`
- name: `??1KSMidiDevice@@UEAA@XZ`
- size: `190`
- prototype: `void __fastcall(KSMidiDevice *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800439bc`
- `0x180043b80`

## callees

- `0x180005044`
- `0x180043a74`
- `0x1800467b0`
- `0x1800485ac`
- `0x18004a750`
- `0x180057c3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004861c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004861c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800485d1`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800485d1`

## pseudocode

```c
void __fastcall KSMidiDevice::~KSMidiDevice(KsHandleWrapper **this)
{
  KsHandleWrapper *v2; // rcx
  KsHandleWrapper *v3; // rdi
  KsHandleWrapper *v4; // rdi
  KsHandleWrapper *v5; // rcx
  KsHandleWrapper *v6; // rdi
  KsHandleWrapper *v7; // rbx

  *this = (KsHandleWrapper *)&KSMidiOutDevice::`vftable';
  KSMidiDevice::Shutdown((KSMidiDevice *)this);
  v2 = this[12];
  if ( v2 )
    AvRevertMmThreadCharacteristics(v2);
  v3 = this[11];
  if ( v3 )
  {
    CMidiXProc::~CMidiXProc(this[11]);
    operator delete(v3);
  }
  v4 = this[10];
  if ( v4 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(this[10]);
    operator delete(v4);
  }
  v5 = this[8];
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = this[7];
  if ( v6 )
  {
    KsHandleWrapper::~KsHandleWrapper(this[7]);
    operator delete(v6);
  }
  v7 = this[6];
  if ( v7 )
  {
    KsHandleWrapper::~KsHandleWrapper(v7);
    operator delete(v7);
  }
}

```

## disassembly

```asm
0x1800485ac  mov     [rsp+arg_0], rbx
0x1800485b1  push    rdi
0x1800485b2  sub     rsp, 20h
0x1800485b6  mov     rbx, rcx
0x1800485b9  lea     rax, ??_7KSMidiOutDevice@@6B@; const KSMidiOutDevice::`vftable'
0x1800485c0  mov     [rcx], rax
0x1800485c3  call    ?Shutdown@KSMidiDevice@@UEAAJXZ; KSMidiDevice::Shutdown(void)
0x1800485c8  mov     rcx, [rbx+60h]; AvrtHandle
0x1800485cc  test    rcx, rcx
0x1800485cf  jz      short loc_1800485D7
0x1800485d1  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800485d7  mov     rdi, [rbx+58h]
0x1800485db  test    rdi, rdi
0x1800485de  jz      short loc_1800485F5
0x1800485e0  mov     rcx, rdi; this
0x1800485e3  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x1800485e8  mov     edx, 90h
0x1800485ed  mov     rcx, rdi; Block
0x1800485f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800485f5  mov     rdi, [rbx+50h]
0x1800485f9  test    rdi, rdi
0x1800485fc  jz      short loc_180048613
0x1800485fe  mov     rcx, rdi; this
0x180048601  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180048606  mov     edx, 68h ; 'h'
0x18004860b  mov     rcx, rdi; Block
0x18004860e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048613  mov     rcx, [rbx+40h]; pv
0x180048617  test    rcx, rcx
0x18004861a  jz      short loc_180048622
0x18004861c  call    cs:__imp_CoTaskMemFree
0x180048622  mov     rdi, [rbx+38h]
0x180048626  test    rdi, rdi
0x180048629  jz      short loc_180048640
0x18004862b  mov     rcx, rdi; this
0x18004862e  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048633  mov     edx, 0D8h
0x180048638  mov     rcx, rdi; Block
0x18004863b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048640  mov     rbx, [rbx+30h]
0x180048644  test    rbx, rbx
0x180048647  jz      short loc_18004865F
0x180048649  mov     rcx, rbx; this
0x18004864c  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180048651  mov     edx, 0D8h
0x180048656  mov     rcx, rbx; Block
0x180048659  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004865e  nop
0x18004865f  mov     rbx, [rsp+28h+arg_0]
0x180048664  add     rsp, 20h
0x180048668  pop     rdi
0x180048669  retn
```
