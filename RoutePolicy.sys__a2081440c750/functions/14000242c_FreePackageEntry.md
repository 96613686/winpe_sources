# FreePackageEntry

- ea: `0x14000242c`
- end: `0x140002490`
- name: `FreePackageEntry`
- size: `100`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400016a0`
- `0x140001d94`
- `0x140001fc0`
- `0x140002138`

## callees

- `0x14000242c`
- `0x14000935c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000244f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002469`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000247d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000244f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002469`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000247d`

## pseudocode

```c
void __fastcall FreePackageEntry(_QWORD *P)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( P )
  {
    v2 = (void *)P[2];
    if ( v2 )
      ExFreePoolWithTag(v2, 0x64667072u);
    v3 = (void *)P[3];
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
0x14000242c  push    rbx
0x14000242e  sub     rsp, 20h
0x140002432  mov     rbx, rcx
0x140002435  test    rcx, rcx
0x140002438  jnz     short loc_140002441
0x14000243a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000243f  jmp     short loc_140002489
0x140002441  mov     rcx, [rcx+10h]; P
0x140002445  test    rcx, rcx
0x140002448  jz      short loc_14000245B
0x14000244a  mov     edx, 64667072h; Tag
0x14000244f  call    cs:__imp_ExFreePoolWithTag
0x140002456  nop     dword ptr [rax+rax+00h]
0x14000245b  mov     rcx, [rbx+18h]; P
0x14000245f  test    rcx, rcx
0x140002462  jz      short loc_140002475
0x140002464  mov     edx, 64667072h; Tag
0x140002469  call    cs:__imp_ExFreePoolWithTag
0x140002470  nop     dword ptr [rax+rax+00h]
0x140002475  mov     edx, 64667072h; Tag
0x14000247a  mov     rcx, rbx; P
0x14000247d  call    cs:__imp_ExFreePoolWithTag
0x140002484  nop     dword ptr [rax+rax+00h]
0x140002489  add     rsp, 20h
0x14000248d  pop     rbx
0x14000248e  retn
```
