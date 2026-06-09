# KSMidiDevice::~KSMidiDevice(void)

- ea: `0x180027a48`
- end: `0x180027b06`
- name: `??1KSMidiDevice@@UEAA@XZ`
- size: `190`
- prototype: `void __fastcall(KSMidiDevice *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010e78`
- `0x180011520`

## callees

- `0x180004434`
- `0x180010f30`
- `0x180025cfc`
- `0x180027a48`
- `0x180029db0`
- `0x18003c59c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ab8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ab8`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180027a6d`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180027a6d`

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
0x180027a48  mov     [rsp+arg_0], rbx
0x180027a4d  push    rdi
0x180027a4e  sub     rsp, 20h
0x180027a52  mov     rbx, rcx
0x180027a55  lea     rax, ??_7KSMidiOutDevice@@6B@; const KSMidiOutDevice::`vftable'
0x180027a5c  mov     [rcx], rax
0x180027a5f  call    ?Shutdown@KSMidiDevice@@UEAAJXZ; KSMidiDevice::Shutdown(void)
0x180027a64  mov     rcx, [rbx+60h]; AvrtHandle
0x180027a68  test    rcx, rcx
0x180027a6b  jz      short loc_180027A73
0x180027a6d  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180027a73  mov     rdi, [rbx+58h]
0x180027a77  test    rdi, rdi
0x180027a7a  jz      short loc_180027A91
0x180027a7c  mov     rcx, rdi; this
0x180027a7f  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180027a84  mov     edx, 90h
0x180027a89  mov     rcx, rdi; Block
0x180027a8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027a91  mov     rdi, [rbx+50h]
0x180027a95  test    rdi, rdi
0x180027a98  jz      short loc_180027AAF
0x180027a9a  mov     rcx, rdi; this
0x180027a9d  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180027aa2  mov     edx, 68h ; 'h'
0x180027aa7  mov     rcx, rdi; Block
0x180027aaa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027aaf  mov     rcx, [rbx+40h]; pv
0x180027ab3  test    rcx, rcx
0x180027ab6  jz      short loc_180027ABE
0x180027ab8  call    cs:__imp_CoTaskMemFree
0x180027abe  mov     rdi, [rbx+38h]
0x180027ac2  test    rdi, rdi
0x180027ac5  jz      short loc_180027ADC
0x180027ac7  mov     rcx, rdi; this
0x180027aca  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180027acf  mov     edx, 0D8h
0x180027ad4  mov     rcx, rdi; Block
0x180027ad7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027adc  mov     rbx, [rbx+30h]
0x180027ae0  test    rbx, rbx
0x180027ae3  jz      short loc_180027AFB
0x180027ae5  mov     rcx, rbx; this
0x180027ae8  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180027aed  mov     edx, 0D8h
0x180027af2  mov     rcx, rbx; Block
0x180027af5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027afa  nop
0x180027afb  mov     rbx, [rsp+28h+arg_0]
0x180027b00  add     rsp, 20h
0x180027b04  pop     rdi
0x180027b05  retn
```
