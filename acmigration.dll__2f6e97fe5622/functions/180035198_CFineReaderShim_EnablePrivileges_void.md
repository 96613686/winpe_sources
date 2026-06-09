# CFineReaderShim::EnablePrivileges(void)

- ea: `0x180035198`
- end: `0x18003520e`
- name: `?EnablePrivileges@CFineReaderShim@@AEAAKXZ`
- size: `118`
- prototype: `unsigned int __fastcall(CFineReaderShim *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180035400`
- `0x180035500`

## callees

- `0x180035198`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800351dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800351dc`
- `ntdll!RtlAdjustPrivilege` at `0x1800351c5`
- `ntdll!RtlAdjustPrivilege` at `0x1800351c5`

## string_xrefs

- `0x1800351e2`: `Failed to enable privileges for fine reader migration shim [%d]`
- `0x1800351ef`: `CFineReaderShim::EnablePrivileges`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::EnablePrivileges(CFineReaderShim *this)
{
  __int64 v1; // rbx
  NTSTATUS v2; // eax
  ULONG v3; // ebx
  CFineReaderShim *OldValue; // [rsp+40h] [rbp+8h] BYREF
  ULONG Privilege; // [rsp+48h] [rbp+10h]
  int v7; // [rsp+4Ch] [rbp+14h]

  OldValue = this;
  v1 = 0;
  Privilege = 17;
  LOBYTE(OldValue) = 0;
  v7 = 18;
  while ( 1 )
  {
    v2 = RtlAdjustPrivilege(*(&Privilege + v1), 1u, 0, (PBOOLEAN)&OldValue);
    if ( v2 )
      break;
    v1 = (unsigned int)(v1 + 1);
    if ( (unsigned int)v1 >= 2 )
      return 0;
  }
  v3 = RtlNtStatusToDosError(v2);
  AslLogCallPrintf(
    1,
    "CFineReaderShim::EnablePrivileges",
    348,
    "Failed to enable privileges for fine reader migration shim [%d]",
    v3);
  return v3;
}

```

## disassembly

```asm
0x180035198  mov     rax, rsp
0x18003519b  mov     [rax+8], rcx
0x18003519f  push    rbx
0x1800351a0  sub     rsp, 30h
0x1800351a4  xor     ebx, ebx
0x1800351a6  mov     dword ptr [rax+10h], 11h
0x1800351ad  mov     [rax+8], bl
0x1800351b0  mov     dword ptr [rax+14h], 12h
0x1800351b7  mov     ecx, [rsp+rbx*4+38h+Privilege]; Privilege
0x1800351bb  lea     r9, [rsp+38h+OldValue]; OldValue
0x1800351c0  xor     r8d, r8d; ForThread
0x1800351c3  mov     dl, 1; NewValue
0x1800351c5  call    cs:__imp_RtlAdjustPrivilege
0x1800351cb  test    eax, eax
0x1800351cd  jnz     short loc_1800351DA
0x1800351cf  inc     ebx
0x1800351d1  cmp     ebx, 2
0x1800351d4  jb      short loc_1800351B7
0x1800351d6  xor     ebx, ebx
0x1800351d8  jmp     short loc_180035206
0x1800351da  mov     ecx, eax; Status
0x1800351dc  call    cs:__imp_RtlNtStatusToDosError
0x1800351e2  lea     r9, aFailedToEnable; "Failed to enable privileges for fine re"...
0x1800351e9  mov     r8d, 15Ch
0x1800351ef  lea     rdx, aCfinereadershi; "CFineReaderShim::EnablePrivileges"
0x1800351f6  mov     [rsp+38h+var_18], eax
0x1800351fa  mov     ecx, 1
0x1800351ff  mov     ebx, eax
0x180035201  call    AslLogCallPrintf
0x180035206  mov     eax, ebx
0x180035208  add     rsp, 30h
0x18003520c  pop     rbx
0x18003520d  retn
```
