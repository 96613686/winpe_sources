# AmiUtilitySetPrivilege(ulong,uchar)

- ea: `0x180039e08`
- end: `0x180039e5e`
- name: `?AmiUtilitySetPrivilege@@YAKKE@Z`
- size: `86`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003a880`
- `0x18003aefc`

## callees

- `0x1800295dc`
- `0x180039e08`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180039e2d`
- `ntdll!RtlNtStatusToDosError` at `0x180039e2d`
- `ntdll!RtlAdjustPrivilege` at `0x180039e21`
- `ntdll!RtlAdjustPrivilege` at `0x180039e21`

## string_xrefs

- `0x180039e40`: `AmiUtilitySetPrivilege`
- `0x180039e39`: `Failed to give privilege [%d]`

## pseudocode

```c
__int64 __fastcall AmiUtilitySetPrivilege(ULONG a1)
{
  ULONG v1; // ebx
  int v2; // eax
  unsigned __int8 OldValue; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  OldValue = 0;
  v2 = RtlAdjustPrivilege(a1, 1u, 0, &OldValue);
  if ( v2 < 0 )
  {
    v1 = RtlNtStatusToDosError(v2);
    AslLogCallPrintf(2, "AmiUtilitySetPrivilege", 61, "Failed to give privilege [%d]", v1);
  }
  return v1;
}

```

## disassembly

```asm
0x180039e08  mov     [rsp+OldValue], dl
0x180039e0c  push    rbx
0x180039e0d  sub     rsp, 30h
0x180039e11  xor     ebx, ebx
0x180039e13  lea     r9, [rsp+38h+OldValue]; OldValue
0x180039e18  xor     r8d, r8d; ForThread
0x180039e1b  mov     [rsp+38h+OldValue], bl
0x180039e1f  mov     dl, 1; NewValue
0x180039e21  call    cs:__imp_RtlAdjustPrivilege
0x180039e27  test    eax, eax
0x180039e29  jns     short loc_180039E56
0x180039e2b  mov     ecx, eax; Status
0x180039e2d  call    cs:__imp_RtlNtStatusToDosError
0x180039e33  mov     r8d, 3Dh ; '='
0x180039e39  lea     r9, aFailedToGivePr; "Failed to give privilege [%d]"
0x180039e40  lea     rdx, aAmiutilitysetp_1; "AmiUtilitySetPrivilege"
0x180039e47  mov     [rsp+38h+var_18], eax
0x180039e4b  mov     ebx, eax
0x180039e4d  lea     ecx, [r8-3Bh]
0x180039e51  call    AslLogCallPrintf
0x180039e56  mov     eax, ebx
0x180039e58  add     rsp, 30h
0x180039e5c  pop     rbx
0x180039e5d  retn
```
