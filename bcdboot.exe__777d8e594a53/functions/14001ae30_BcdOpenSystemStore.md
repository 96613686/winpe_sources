# BcdOpenSystemStore

- ea: `0x14001ae30`
- end: `0x14001ae8e`
- name: `BcdOpenSystemStore`
- size: `94`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001a964`

## callees

- `0x1400133e4`
- `0x14001ae30`
- `0x14001ae94`
- `0x14001bd44`

## import_xrefs

- `ntdll!ZwReleaseMutant` at `0x14001ae7b`
- `ntdll!ZwReleaseMutant` at `0x14001ae7b`

## string_xrefs

- `0x14001ae4d`: `BcdOpenSystemStore: Failed to acquire BCD sync mutant.Status: %x`

## pseudocode

```c
__int64 __fastcall BcdOpenSystemStore(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx

  v2 = BiAcquireBcdSyncMutant(0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v3 = BiOpenSystemStore(a1, 0);
    if ( BcdMutantHandle != (HANDLE)-1LL )
      ZwReleaseMutant(BcdMutantHandle, 0);
  }
  else
  {
    BiLogMessage(4, L"BcdOpenSystemStore: Failed to acquire BCD sync mutant.Status: %x", (unsigned int)v2);
  }
  return v3;
}

```

## disassembly

```asm
0x14001ae30  mov     [rsp+arg_0], rbx
0x14001ae35  push    rdi
0x14001ae36  sub     rsp, 20h
0x14001ae3a  mov     rdi, rcx
0x14001ae3d  xor     ecx, ecx
0x14001ae3f  call    BiAcquireBcdSyncMutant
0x14001ae44  mov     ebx, eax
0x14001ae46  test    eax, eax
0x14001ae48  jns     short loc_14001AE60
0x14001ae4a  mov     r8d, eax
0x14001ae4d  lea     rdx, aBcdopensystems; "BcdOpenSystemStore: Failed to acquire B"...
0x14001ae54  mov     ecx, 4
0x14001ae59  call    BiLogMessage
0x14001ae5e  jmp     short loc_14001AE81
0x14001ae60  xor     edx, edx
0x14001ae62  mov     rcx, rdi
0x14001ae65  call    BiOpenSystemStore
0x14001ae6a  mov     rcx, cs:BcdMutantHandle; MutantHandle
0x14001ae71  mov     ebx, eax
0x14001ae73  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001ae77  jz      short loc_14001AE81
0x14001ae79  xor     edx, edx; ReleaseCount
0x14001ae7b  call    cs:__imp_ZwReleaseMutant
0x14001ae81  mov     eax, ebx
0x14001ae83  mov     rbx, [rsp+28h+arg_0]
0x14001ae88  add     rsp, 20h
0x14001ae8c  pop     rdi
0x14001ae8d  retn
```
