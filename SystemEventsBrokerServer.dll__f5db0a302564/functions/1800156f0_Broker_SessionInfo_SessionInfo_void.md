# Broker::_SessionInfo::~_SessionInfo(void)

- ea: `0x1800156f0`
- end: `0x1800157fb`
- name: `??1_SessionInfo@Broker@@QEAA@XZ`
- size: `267`
- prototype: `void __fastcall(Broker::_SessionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f0f0`

## callees

- `0x1800156f0`
- `0x180027010`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18001574d`
- `ntdll!NtDeleteWnfStateName` at `0x1800157da`
- `ntdll!NtDeleteWnfStateName` at `0x1800157e5`
- `ntdll!NtDeleteWnfStateName` at `0x1800157f0`
- `ntdll!NtDeleteWnfStateName` at `0x18001574d`
- `ntdll!NtDeleteWnfStateName` at `0x1800157da`
- `ntdll!NtDeleteWnfStateName` at `0x1800157e5`
- `ntdll!NtDeleteWnfStateName` at `0x1800157f0`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800157c4`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800157cf`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800157c4`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800157cf`

## pseudocode

```c
void __fastcall Broker::_SessionInfo::~_SessionInfo(Broker::_SessionInfo *this)
{
  void *v2; // rcx
  void *v3; // rcx
  volatile signed __int32 *v4; // rbx

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    PowerSettingUnregisterNotification(v2);
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
    PowerSettingUnregisterNotification(v3);
  if ( *((_DWORD *)this + 14) || *((_DWORD *)this + 15) )
    NtDeleteWnfStateName((char *)this + 56);
  if ( *((_DWORD *)this + 16) || *((_DWORD *)this + 17) )
    NtDeleteWnfStateName((char *)this + 64);
  if ( *((_DWORD *)this + 18) || *((_DWORD *)this + 19) )
    NtDeleteWnfStateName((char *)this + 72);
  if ( *((_DWORD *)this + 20) || *((_DWORD *)this + 21) )
    NtDeleteWnfStateName((char *)this + 80);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x1800156f0  push    rbx
0x1800156f2  sub     rsp, 20h
0x1800156f6  mov     rbx, rcx
0x1800156f9  mov     rcx, [rcx+18h]; RegistrationHandle
0x1800156fd  test    rcx, rcx
0x180015700  jnz     loc_1800157C4
0x180015706  mov     rcx, [rbx+20h]; RegistrationHandle
0x18001570a  test    rcx, rcx
0x18001570d  jnz     loc_1800157CF
0x180015713  cmp     dword ptr [rbx+38h], 0
0x180015717  lea     rcx, [rbx+38h]
0x18001571b  jnz     loc_1800157DA
0x180015721  cmp     dword ptr [rbx+3Ch], 0
0x180015725  jnz     loc_1800157DA
0x18001572b  cmp     dword ptr [rbx+40h], 0
0x18001572f  lea     rcx, [rbx+40h]
0x180015733  jnz     loc_1800157E5
0x180015739  cmp     dword ptr [rbx+44h], 0
0x18001573d  jnz     loc_1800157E5
0x180015743  cmp     dword ptr [rbx+48h], 0
0x180015747  lea     rcx, [rbx+48h]
0x18001574b  jz      short loc_1800157BC
0x18001574d  call    cs:__imp_NtDeleteWnfStateName
0x180015753  cmp     dword ptr [rbx+50h], 0
0x180015757  lea     rcx, [rbx+50h]
0x18001575b  jnz     loc_1800157F0
0x180015761  cmp     dword ptr [rbx+54h], 0
0x180015765  jnz     loc_1800157F0
0x18001576b  mov     rbx, [rbx+8]
0x18001576f  test    rbx, rbx
0x180015772  jz      short loc_1800157B6
0x180015774  mov     [rsp+28h+arg_0], rdi
0x180015779  mov     edi, 0FFFFFFFFh
0x18001577e  mov     eax, edi
0x180015780  lock xadd [rbx+8], eax
0x180015785  cmp     eax, 1
0x180015788  jnz     short loc_1800157B1
0x18001578a  mov     rax, [rbx]
0x18001578d  mov     rcx, rbx
0x180015790  mov     rax, [rax]
0x180015793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015798  lock xadd [rbx+0Ch], edi
0x18001579d  cmp     edi, 1
0x1800157a0  jnz     short loc_1800157B1
0x1800157a2  mov     rax, [rbx]
0x1800157a5  mov     rcx, rbx
0x1800157a8  mov     rax, [rax+8]
0x1800157ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157b1  mov     rdi, [rsp+28h+arg_0]
0x1800157b6  add     rsp, 20h
0x1800157ba  pop     rbx
0x1800157bb  retn
0x1800157bc  cmp     dword ptr [rbx+4Ch], 0
0x1800157c0  jz      short loc_180015753
0x1800157c2  jmp     short loc_18001574D
0x1800157c4  call    cs:__imp_PowerSettingUnregisterNotification
0x1800157ca  jmp     loc_180015706
0x1800157cf  call    cs:__imp_PowerSettingUnregisterNotification
0x1800157d5  jmp     loc_180015713
0x1800157da  call    cs:__imp_NtDeleteWnfStateName
0x1800157e0  jmp     loc_18001572B
0x1800157e5  call    cs:__imp_NtDeleteWnfStateName
0x1800157eb  jmp     loc_180015743
0x1800157f0  call    cs:__imp_NtDeleteWnfStateName
0x1800157f6  jmp     loc_18001576B
```
