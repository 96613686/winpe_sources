# BiReleasePrivilege

- ea: `0x140021888`
- end: `0x1400218db`
- name: `BiReleasePrivilege`
- size: `83`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14001df18`
- `0x14001e648`
- `0x14001f570`
- `0x14001fe24`
- `0x1400218e4`
- `0x140023218`
- `0x140023448`
- `0x1400235bc`
- `0x140023824`
- `0x14002467c`
- `0x140024714`
- `0x14002483c`
- `0x140024a28`
- `0x140024b30`

## callees

- `0x1400216fc`
- `0x140021888`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1400218cf`
- `ntdll!NtSetInformationThread` at `0x1400218cf`

## pseudocode

```c
NTSTATUS __fastcall BiReleasePrivilege(__int64 a1)
{
  bool v1; // zf
  NTSTATUS result; // eax
  __int64 ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_BYTE *)(a1 + 4) == 0;
  LOBYTE(ThreadInformation) = 0;
  if ( v1 )
    result = BiAdjustPrivilege(*(_DWORD *)a1, 0, (bool *)&ThreadInformation);
  if ( !*(_BYTE *)(a1 + 5) )
  {
    ThreadInformation = 0;
    return NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  return result;
}

```

## disassembly

```asm
0x140021888  push    rbx
0x14002188a  sub     rsp, 20h
0x14002188e  cmp     byte ptr [rcx+4], 0
0x140021892  mov     rbx, rcx
0x140021895  mov     byte ptr [rsp+28h+ThreadInformation], 0
0x14002189a  jnz     short loc_1400218AA
0x14002189c  mov     ecx, [rcx]
0x14002189e  lea     r8, [rsp+28h+ThreadInformation]
0x1400218a3  xor     edx, edx
0x1400218a5  call    BiAdjustPrivilege
0x1400218aa  cmp     byte ptr [rbx+5], 0
0x1400218ae  jnz     short loc_1400218D5
0x1400218b0  mov     r9d, 8; ThreadInformationLength
0x1400218b6  mov     [rsp+28h+ThreadInformation], 0
0x1400218bf  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1400218c4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400218cb  lea     edx, [r9-3]; ThreadInformationClass
0x1400218cf  call    cs:__imp_NtSetInformationThread
0x1400218d5  add     rsp, 20h
0x1400218d9  pop     rbx
0x1400218da  retn
```
