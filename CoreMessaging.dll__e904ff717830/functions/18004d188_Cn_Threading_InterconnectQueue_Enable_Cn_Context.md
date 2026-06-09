# Cn::Threading::InterconnectQueue::Enable(Cn::Context *)

- ea: `0x18004d188`
- end: `0x18004d273`
- name: `?Enable@InterconnectQueue@Threading@Cn@@SAXPEAVContext@3@@Z`
- size: `235`
- prototype: `void __fastcall(struct Cn::Context *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d040`

## callees

- `0x180007d80`
- `0x18003950c`
- `0x18004d188`
- `0x18004d398`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d214`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d214`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d22e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d22e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d245`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d19c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d1ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d19c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d24c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d24c`

## pseudocode

```c
void __fastcall Cn::Threading::InterconnectQueue::Enable(struct Cn::Context *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  HANDLE EventW; // rax
  signed int LastError; // eax

  AcquireSRWLockExclusive(&Cn::Threading::InterconnectQueue::s_lockType);
  v2 = *((_QWORD *)a1 + 3);
  AcquireSRWLockExclusive((PSRWLOCK)(v2 + 96));
  if ( *(_BYTE *)(v2 + 144) == 1 )
    goto LABEL_12;
  if ( Cn::Threading::InterconnectQueue::s_pqueueVisible )
  {
    wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy>::operator=(v2 + 16);
    wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy>::operator=((char *)Cn::Threading::InterconnectQueue::s_pqueueVisible + 24);
  }
  wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy>::operator=(&Cn::Threading::InterconnectQueue::s_pqueueVisible);
  *(_BYTE *)(v2 + 144) = 1;
  if ( *(_QWORD *)(v2 + 152) )
LABEL_12:
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v4,
      v3,
      v5,
      v6);
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(v2 + 152) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  if ( v2 != -96 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 96));
  ReleaseSRWLockExclusive(&Cn::Threading::InterconnectQueue::s_lockType);
}

```

## disassembly

```asm
0x18004d188  mov     [rsp+arg_0], rbx
0x18004d18d  push    rdi
0x18004d18e  sub     rsp, 20h
0x18004d192  mov     rbx, rcx
0x18004d195  lea     rcx, ?s_lockType@InterconnectQueue@Threading@Cn@@0USlimLock@23@A; SRWLock
0x18004d19c  call    cs:__imp_AcquireSRWLockExclusive
0x18004d1a2  mov     rbx, [rbx+18h]
0x18004d1a6  lea     rdi, [rbx+60h]
0x18004d1aa  mov     rcx, rdi; SRWLock
0x18004d1ad  call    cs:__imp_AcquireSRWLockExclusive
0x18004d1b3  cmp     byte ptr [rbx+90h], 1
0x18004d1ba  jz      loc_18004D26D
0x18004d1c0  mov     rdx, cs:?s_pqueueVisible@InterconnectQueue@Threading@Cn@@0V?$com_ptr_t@VInterconnectQueue@Threading@Cn@@Uerr_exception_policy@wil@@@wil@@A; wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy> Cn::Threading::InterconnectQueue::s_pqueueVisible
0x18004d1c7  test    rdx, rdx
0x18004d1ca  jz      short loc_18004D1E8
0x18004d1cc  lea     rcx, [rbx+10h]
0x18004d1d0  call    ??4?$com_ptr_t@VInterconnectQueue@Threading@Cn@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAVInterconnectQueue@Threading@Cn@@@Z; wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy>::operator=(Cn::Threading::InterconnectQueue *)
0x18004d1d5  mov     rcx, cs:?s_pqueueVisible@InterconnectQueue@Threading@Cn@@0V?$com_ptr_t@VInterconnectQueue@Threading@Cn@@Uerr_exception_policy@wil@@@wil@@A; wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy> Cn::Threading::InterconnectQueue::s_pqueueVisible
0x18004d1dc  add     rcx, 18h
0x18004d1e0  mov     rdx, rbx
0x18004d1e3  call    ??4?$com_ptr_t@VInterconnectQueue@Threading@Cn@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAVInterconnectQueue@Threading@Cn@@@Z; wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy>::operator=(Cn::Threading::InterconnectQueue *)
0x18004d1e8  mov     rdx, rbx
0x18004d1eb  lea     rcx, ?s_pqueueVisible@InterconnectQueue@Threading@Cn@@0V?$com_ptr_t@VInterconnectQueue@Threading@Cn@@Uerr_exception_policy@wil@@@wil@@A; wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy> Cn::Threading::InterconnectQueue::s_pqueueVisible
0x18004d1f2  call    ??4?$com_ptr_t@VInterconnectQueue@Threading@Cn@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAVInterconnectQueue@Threading@Cn@@@Z; wil::com_ptr_t<Cn::Threading::InterconnectQueue,wil::err_exception_policy>::operator=(Cn::Threading::InterconnectQueue *)
0x18004d1f7  mov     byte ptr [rbx+90h], 1
0x18004d1fe  cmp     qword ptr [rbx+98h], 0
0x18004d206  jnz     short loc_18004D26D
0x18004d208  xor     r9d, r9d; lpName
0x18004d20b  xor     r8d, r8d; bInitialState
0x18004d20e  lea     edx, [r9+1]; bManualReset
0x18004d212  xor     ecx, ecx; lpEventAttributes
0x18004d214  call    cs:__imp_CreateEventW
0x18004d21a  mov     [rbx+98h], rax
0x18004d221  test    rax, rax
0x18004d224  jz      short loc_18004D24C
0x18004d226  test    rdi, rdi
0x18004d229  jz      short loc_18004D234
0x18004d22b  mov     rcx, rdi; SRWLock
0x18004d22e  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d234  lea     rcx, ?s_lockType@InterconnectQueue@Threading@Cn@@0USlimLock@23@A; Cn::Threading::SlimLock Cn::Threading::InterconnectQueue::s_lockType
0x18004d23b  mov     rbx, [rsp+28h+arg_0]
0x18004d240  add     rsp, 20h
0x18004d244  pop     rdi
0x18004d245  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18004d24c  call    cs:__imp_GetLastError
0x18004d252  test    eax, eax
0x18004d254  jg      short loc_18004D263
0x18004d256  xor     r8d, r8d; int
0x18004d259  xor     edx, edx; void *
0x18004d25b  mov     ecx, eax; int
0x18004d25d  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18004d263  movzx   eax, ax
0x18004d266  or      eax, 80070000h
0x18004d26b  jmp     short loc_18004D256
0x18004d26d  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
```
