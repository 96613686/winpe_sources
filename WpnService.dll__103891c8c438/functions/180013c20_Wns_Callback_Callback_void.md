# Wns::Callback::~Callback(void)

- ea: `0x180013c20`
- end: `0x180013c9f`
- name: `??1Callback@Wns@@UEAA@XZ`
- size: `127`
- prototype: `void __fastcall(RTL_CONDITION_VARIABLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013be0`

## callees

- `0x180003190`
- `0x180013c20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c70`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x180013c5b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x180013c5b`

## pseudocode

```c
void __fastcall Wns::Callback::~Callback(RTL_CONDITION_VARIABLE *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  this->Ptr = &Wns::Callback::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)&this[3];
  EnterCriticalSection((LPCRITICAL_SECTION)&this[3]);
  while ( this[2].Ptr )
    SleepConditionVariableCS(this + 8, v2, 0xFFFFFFFF);
  if ( v2 )
    LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&this[1]);
}

```

## disassembly

```asm
0x180013c20  mov     [rsp+arg_10], rbx
0x180013c25  mov     [rsp+arg_0], rcx
0x180013c2a  push    rdi
0x180013c2b  sub     rsp, 20h
0x180013c2f  mov     rbx, rcx
0x180013c32  lea     rax, ??_7Callback@Wns@@6B@; const Wns::Callback::`vftable'
0x180013c39  mov     [rcx], rax
0x180013c3c  lea     rdi, [rcx+18h]
0x180013c40  mov     [rsp+28h+arg_8], rdi
0x180013c45  mov     rcx, rdi; lpCriticalSection
0x180013c48  call    cs:__imp_EnterCriticalSection
0x180013c4e  jmp     short loc_180013C61
0x180013c50  lea     rcx, [rbx+40h]; ConditionVariable
0x180013c54  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180013c58  mov     rdx, rdi; CriticalSection
0x180013c5b  call    cs:__imp_SleepConditionVariableCS
0x180013c61  cmp     qword ptr [rbx+10h], 0
0x180013c66  ja      short loc_180013C50
0x180013c68  test    rdi, rdi
0x180013c6b  jz      short loc_180013C77
0x180013c6d  mov     rcx, rdi; lpCriticalSection
0x180013c70  call    cs:__imp_LeaveCriticalSection
0x180013c76  nop
0x180013c77  jmp     short loc_180013C83
0x180013c79  mov     rbx, [rsp+28h+arg_0]
0x180013c7e  mov     rdi, [rsp+28h+arg_8]
0x180013c83  mov     rcx, rdi; lpCriticalSection
0x180013c86  call    cs:__imp_DeleteCriticalSection
0x180013c8c  lea     rcx, [rbx+8]
0x180013c90  mov     rbx, [rsp+28h+arg_10]
0x180013c95  add     rsp, 20h
0x180013c99  pop     rdi
0x180013c9a  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
