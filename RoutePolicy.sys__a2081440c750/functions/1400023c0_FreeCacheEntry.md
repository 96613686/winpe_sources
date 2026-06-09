# FreeCacheEntry

- ea: `0x1400023c0`
- end: `0x140002424`
- name: `FreeCacheEntry`
- size: `100`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001fc0`
- `0x14000294c`
- `0x1400029f4`

## callees

- `0x1400023c0`
- `0x14000935c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400023e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002411`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002411`

## pseudocode

```c
void __fastcall FreeCacheEntry(_QWORD *P)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( P )
  {
    v2 = (void *)P[3];
    if ( v2 )
      ExFreePoolWithTag(v2, 0x64667072u);
    v3 = (void *)P[4];
    if ( v3 )
      ExFreePoolWithTag(v3, 0x64667072u);
    ExFreePoolWithTag(P, 0x64667072u);
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
}

```

## disassembly

```asm
0x1400023c0  push    rbx
0x1400023c2  sub     rsp, 20h
0x1400023c6  mov     rbx, rcx
0x1400023c9  test    rcx, rcx
0x1400023cc  jnz     short loc_1400023D5
0x1400023ce  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400023d3  jmp     short loc_14000241D
0x1400023d5  mov     rcx, [rcx+18h]; P
0x1400023d9  test    rcx, rcx
0x1400023dc  jz      short loc_1400023EF
0x1400023de  mov     edx, 64667072h; Tag
0x1400023e3  call    cs:__imp_ExFreePoolWithTag
0x1400023ea  nop     dword ptr [rax+rax+00h]
0x1400023ef  mov     rcx, [rbx+20h]; P
0x1400023f3  test    rcx, rcx
0x1400023f6  jz      short loc_140002409
0x1400023f8  mov     edx, 64667072h; Tag
0x1400023fd  call    cs:__imp_ExFreePoolWithTag
0x140002404  nop     dword ptr [rax+rax+00h]
0x140002409  mov     edx, 64667072h; Tag
0x14000240e  mov     rcx, rbx; P
0x140002411  call    cs:__imp_ExFreePoolWithTag
0x140002418  nop     dword ptr [rax+rax+00h]
0x14000241d  add     rsp, 20h
0x140002421  pop     rbx
0x140002422  retn
```
