# IkeDerefEntryInAuthzBypassTable

- ea: `0x180073820`
- end: `0x1800738c0`
- name: `IkeDerefEntryInAuthzBypassTable`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800687ac`

## callees

- `0x18001afe0`
- `0x180073820`
- `0x180073ab8`
- `0x180073d44`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180073883`
- `ntdll!RtlRemoveEntryHashTable` at `0x180073883`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800738b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073844`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073844`

## pseudocode

```c
void __fastcall IkeDerefEntryInAuthzBypassTable(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // roff
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  EnterCriticalSection(gIkeExtGlobals + 3);
  IkeLookupInAuthzBypassTable(a1, a2, 1, &v6);
  v4 = v6;
  v5 = (_DWORD *)(v6 + 116);
  _InterlockedDecrement((volatile signed __int32 *)(v6 + 116));
  if ( !*v5 )
  {
    RtlRemoveEntryHashTable(&gIkeExtGlobals[61].LockCount, v4, 0);
    WfpRestructureHashtable(&gIkeExtGlobals[61].LockCount);
    IkeFreePeerAuthzBypassEntry(v4);
  }
  LeaveCriticalSection(gIkeExtGlobals + 3);
}

```

## disassembly

```asm
0x180073820  mov     [rsp+arg_0], rbx
0x180073825  push    rdi
0x180073826  sub     rsp, 20h
0x18007382a  mov     rdi, rcx
0x18007382d  mov     [rsp+28h+arg_10], 0
0x180073836  mov     rcx, cs:gIkeExtGlobals
0x18007383d  mov     rbx, rdx
0x180073840  add     rcx, 78h ; 'x'; lpCriticalSection
0x180073844  call    cs:__imp_EnterCriticalSection
0x18007384a  lea     r9, [rsp+28h+arg_10]
0x18007384f  mov     r8d, 1
0x180073855  mov     rdx, rbx
0x180073858  mov     rcx, rdi
0x18007385b  call    IkeLookupInAuthzBypassTable
0x180073860  mov     rbx, [rsp+28h+arg_10]
0x180073865  lock dec dword ptr [rbx+74h]
0x180073869  cmp     dword ptr [rbx+74h], 0
0x18007386d  jnz     short loc_1800738A4
0x18007386f  mov     rcx, cs:gIkeExtGlobals
0x180073876  xor     r8d, r8d
0x180073879  add     rcx, 990h
0x180073880  mov     rdx, rbx
0x180073883  call    cs:__imp_RtlRemoveEntryHashTable
0x180073889  mov     rcx, cs:gIkeExtGlobals
0x180073890  add     rcx, 990h
0x180073897  call    WfpRestructureHashtable
0x18007389c  mov     rcx, rbx
0x18007389f  call    IkeFreePeerAuthzBypassEntry
0x1800738a4  mov     rcx, cs:gIkeExtGlobals
0x1800738ab  add     rcx, 78h ; 'x'
0x1800738af  mov     rbx, [rsp+28h+arg_0]
0x1800738b4  add     rsp, 20h
0x1800738b8  pop     rdi
0x1800738b9  jmp     cs:__imp_LeaveCriticalSection
```
