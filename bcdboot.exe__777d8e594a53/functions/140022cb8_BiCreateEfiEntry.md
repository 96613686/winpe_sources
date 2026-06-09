# BiCreateEfiEntry

- ea: `0x140022cb8`
- end: `0x140022e86`
- name: `BiCreateEfiEntry`
- size: `462`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x140021f58`
- `0x140023714`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x140013ee8`
- `0x14001c794`
- `0x1400218e4`
- `0x1400228bc`
- `0x140022cb8`
- `0x14002445c`
- `0x14002515c`
- `0x140025368`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140022e6f`
- `ntdll!RtlFreeHeap` at `0x140022e6f`

## string_xrefs

- `0x140022d60`: `Created boot entry %d '%ws' using cached variable`
- `0x140022de3`: `Created new boot entry %d '%ws'`
- `0x140022e34`: `BiCreateEfiEntry failed %x`

## pseudocode

```c
__int64 __fastcall BiCreateEfiEntry(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  unsigned int *v4; // rdi
  int v6; // eax
  HANDLE v7; // r14
  int SavedBootEntry; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v12; // [rsp+68h] [rbp+48h] BYREF
  PVOID P; // [rsp+70h] [rbp+50h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+58h] BYREF

  v2 = a2 + 16;
  v12 = 0;
  Handle = 0;
  v4 = 0;
  P = 0;
  v6 = BcdOpenObject(a1, (_QWORD *)(a2 + 16), &Handle);
  v7 = Handle;
  SavedBootEntry = v6;
  if ( v6 < 0 )
    goto LABEL_16;
  if ( (*(_BYTE *)(a2 + 48) & 2) == 0 )
  {
    SavedBootEntry = BiCreateBootEntry((__int64)Handle, &P);
    if ( SavedBootEntry >= 0 )
    {
      v4 = (unsigned int *)P;
      SavedBootEntry = BiAddBootEntry(P, &v12);
      if ( SavedBootEntry >= 0 )
      {
        BiLogMessage(2, L"Created new boot entry %d '%ws'", v12, (char *)v4 + v4[4]);
        v4[2] = v12;
        v10 = v12;
        *(_DWORD *)(a2 + 48) |= 0x21u;
        *(_DWORD *)(a2 + 32) = v10;
        *(_QWORD *)(a2 + 40) = v4;
        SavedBootEntry = BiSaveFirmwareVariable(v7, v2, v4, v4[1]);
        if ( SavedBootEntry >= 0 )
        {
          *(_DWORD *)(a2 + 48) |= 2u;
          goto LABEL_17;
        }
      }
      goto LABEL_16;
    }
    goto LABEL_15;
  }
  SavedBootEntry = BiGetSavedBootEntry(Handle, &P);
  if ( SavedBootEntry < 0 )
  {
LABEL_15:
    v4 = (unsigned int *)P;
    goto LABEL_16;
  }
  v4 = (unsigned int *)P;
  if ( (*(_BYTE *)(a2 + 48) & 8) == 0 )
  {
    SavedBootEntry = BiUpdateObjectReferenceInEfiEntry(P, v7);
    if ( SavedBootEntry >= 0 )
    {
      *(_DWORD *)(a2 + 48) |= 0x20u;
      goto LABEL_7;
    }
LABEL_16:
    BiLogMessage(4, L"BiCreateEfiEntry failed %x", (unsigned int)SavedBootEntry);
    goto LABEL_17;
  }
LABEL_7:
  SavedBootEntry = BiAddBootEntry(v4, &v12);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
  BiLogMessage(2, L"Created boot entry %d '%ws' using cached variable", v12, (char *)v4 + v4[4]);
  v4[2] = v12;
  v9 = v12;
  *(_DWORD *)(a2 + 48) |= 1u;
  *(_DWORD *)(a2 + 32) = v9;
  *(_QWORD *)(a2 + 40) = v4;
  SavedBootEntry = BiSaveFirmwareVariable(v7, v2, v4, v4[1]);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
  SavedBootEntry = BiUpdateEfiEntry(a1, a2);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
LABEL_17:
  if ( v7 )
    BcdCloseObject(v7);
  if ( (*(_BYTE *)(a2 + 48) & 1) == 0 && v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)SavedBootEntry;
}

```

## disassembly

```asm
0x140022cb8  push    rbp
0x140022cba  push    rbx
0x140022cbb  push    rsi
0x140022cbc  push    rdi
0x140022cbd  push    r12
0x140022cbf  push    r14
0x140022cc1  push    r15
0x140022cc3  mov     rbp, rsp
0x140022cc6  sub     rsp, 20h
0x140022cca  lea     r12, [rdx+10h]
0x140022cce  mov     [rbp+arg_8], 0
0x140022cd5  mov     rsi, rdx
0x140022cd8  mov     [rbp+Handle], 0
0x140022ce0  xor     edi, edi
0x140022ce2  lea     r8, [rbp+Handle]
0x140022ce6  mov     rdx, r12
0x140022ce9  mov     [rbp+P], rdi
0x140022ced  mov     r15, rcx
0x140022cf0  call    BcdOpenObject
0x140022cf5  mov     r14, [rbp+Handle]
0x140022cf9  mov     ebx, eax
0x140022cfb  test    eax, eax
0x140022cfd  js      loc_140022E31
0x140022d03  test    byte ptr [rsi+30h], 2
0x140022d07  lea     rdx, [rbp+P]
0x140022d0b  mov     rcx, r14
0x140022d0e  jz      loc_140022DBE
0x140022d14  call    BiGetSavedBootEntry
0x140022d19  mov     ebx, eax
0x140022d1b  test    eax, eax
0x140022d1d  js      loc_140022E2D
0x140022d23  test    byte ptr [rsi+30h], 8
0x140022d27  mov     rdi, [rbp+P]
0x140022d2b  jnz     short loc_140022D46
0x140022d2d  mov     rdx, r14
0x140022d30  mov     rcx, rdi
0x140022d33  call    BiUpdateObjectReferenceInEfiEntry
0x140022d38  mov     ebx, eax
0x140022d3a  test    eax, eax
0x140022d3c  js      loc_140022E31
0x140022d42  or      dword ptr [rsi+30h], 20h
0x140022d46  lea     rdx, [rbp+arg_8]
0x140022d4a  mov     rcx, rdi
0x140022d4d  call    BiAddBootEntry
0x140022d52  mov     ebx, eax
0x140022d54  test    eax, eax
0x140022d56  js      loc_140022E31
0x140022d5c  mov     r9d, [rdi+10h]
0x140022d60  lea     rdx, aCreatedBootEnt; "Created boot entry %d '%ws' using cache"...
0x140022d67  mov     r8d, [rbp+arg_8]
0x140022d6b  add     r9, rdi
0x140022d6e  mov     ecx, 2
0x140022d73  call    BiLogMessage
0x140022d78  mov     eax, [rbp+arg_8]
0x140022d7b  mov     r8, rdi
0x140022d7e  mov     [rdi+8], eax
0x140022d81  mov     rdx, r12
0x140022d84  mov     eax, [rbp+arg_8]
0x140022d87  mov     rcx, r14
0x140022d8a  or      dword ptr [rsi+30h], 1
0x140022d8e  mov     [rsi+20h], eax
0x140022d91  mov     [rsi+28h], rdi
0x140022d95  mov     r9d, [rdi+4]
0x140022d99  call    BiSaveFirmwareVariable
0x140022d9e  mov     ebx, eax
0x140022da0  test    eax, eax
0x140022da2  js      loc_140022E31
0x140022da8  mov     rdx, rsi
0x140022dab  mov     rcx, r15
0x140022dae  call    BiUpdateEfiEntry
0x140022db3  mov     ebx, eax
0x140022db5  test    eax, eax
0x140022db7  js      short loc_140022E31
0x140022db9  jmp     loc_140022E45
0x140022dbe  call    BiCreateBootEntry
0x140022dc3  mov     ebx, eax
0x140022dc5  test    eax, eax
0x140022dc7  js      short loc_140022E2D
0x140022dc9  mov     rdi, [rbp+P]
0x140022dcd  lea     rdx, [rbp+arg_8]
0x140022dd1  mov     rcx, rdi
0x140022dd4  call    BiAddBootEntry
0x140022dd9  mov     ebx, eax
0x140022ddb  test    eax, eax
0x140022ddd  js      short loc_140022E31
0x140022ddf  mov     r9d, [rdi+10h]
0x140022de3  lea     rdx, aCreatedNewBoot; "Created new boot entry %d '%ws'"
0x140022dea  mov     r8d, [rbp+arg_8]
0x140022dee  add     r9, rdi
0x140022df1  mov     ecx, 2
0x140022df6  call    BiLogMessage
0x140022dfb  mov     eax, [rbp+arg_8]
0x140022dfe  mov     r8, rdi
0x140022e01  mov     [rdi+8], eax
0x140022e04  mov     rdx, r12
0x140022e07  mov     eax, [rbp+arg_8]
0x140022e0a  mov     rcx, r14
0x140022e0d  or      dword ptr [rsi+30h], 21h
0x140022e11  mov     [rsi+20h], eax
0x140022e14  mov     [rsi+28h], rdi
0x140022e18  mov     r9d, [rdi+4]
0x140022e1c  call    BiSaveFirmwareVariable
0x140022e21  mov     ebx, eax
0x140022e23  test    eax, eax
0x140022e25  js      short loc_140022E31
0x140022e27  or      dword ptr [rsi+30h], 2
0x140022e2b  jmp     short loc_140022E45
0x140022e2d  mov     rdi, [rbp+P]
0x140022e31  mov     r8d, ebx
0x140022e34  lea     rdx, aBicreateefient; "BiCreateEfiEntry failed %x"
0x140022e3b  mov     ecx, 4
0x140022e40  call    BiLogMessage
0x140022e45  test    r14, r14
0x140022e48  jz      short loc_140022E52
0x140022e4a  mov     rcx, r14; Handle
0x140022e4d  call    BcdCloseObject
0x140022e52  test    byte ptr [rsi+30h], 1
0x140022e56  jnz     short loc_140022E75
0x140022e58  test    rdi, rdi
0x140022e5b  jz      short loc_140022E75
0x140022e5d  mov     rcx, gs:60h
0x140022e66  mov     r8, rdi; P
0x140022e69  xor     edx, edx; Flags
0x140022e6b  mov     rcx, [rcx+30h]; HeapHandle
0x140022e6f  call    cs:__imp_RtlFreeHeap
0x140022e75  mov     eax, ebx
0x140022e77  add     rsp, 20h
0x140022e7b  pop     r15
0x140022e7d  pop     r14
0x140022e7f  pop     r12
0x140022e81  pop     rdi
0x140022e82  pop     rsi
0x140022e83  pop     rbx
0x140022e84  pop     rbp
0x140022e85  retn
```
