# BiReleaseBcdSyncMutant

- ea: `0x14001c014`
- end: `0x14001c036`
- name: `BiReleaseBcdSyncMutant`
- size: `34`
- prototype: `NTSTATUS __fastcall(char)`
- caller_count: `18`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140013b48`
- `0x140013b9c`
- `0x140013c1c`
- `0x140013ee8`
- `0x1400140c4`
- `0x14001474c`
- `0x140014ec8`
- `0x1400186fc`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x14001a8c4`
- `0x14001a964`
- `0x14001ac80`
- `0x14001acec`
- `0x14001adb8`
- `0x14001bb00`
- `0x140021c10`

## callees

- `0x14001c014`

## import_xrefs

- `ntdll!ZwReleaseMutant` at `0x14001c02b`
- `ntdll!ZwReleaseMutant` at `0x14001c02b`

## pseudocode

```c
NTSTATUS __fastcall BiReleaseBcdSyncMutant(char a1)
{
  NTSTATUS result; // eax

  if ( !a1 && BcdMutantHandle != (HANDLE)-1LL )
    return ZwReleaseMutant(BcdMutantHandle, 0);
  return result;
}

```

## disassembly

```asm
0x14001c014  sub     rsp, 28h
0x14001c018  test    cl, cl
0x14001c01a  jnz     short loc_14001C031
0x14001c01c  mov     rcx, cs:BcdMutantHandle; MutantHandle
0x14001c023  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001c027  jz      short loc_14001C031
0x14001c029  xor     edx, edx; ReleaseCount
0x14001c02b  call    cs:__imp_ZwReleaseMutant
0x14001c031  add     rsp, 28h
0x14001c035  retn
```
