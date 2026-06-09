# FreeRulesEntry

- ea: `0x140002498`
- end: `0x1400024e2`
- name: `FreeRulesEntry`
- size: `74`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001fc0`
- `0x140002abc`

## callees

- `0x140002498`
- `0x14000935c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400024bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024cf`

## pseudocode

```c
void __fastcall FreeRulesEntry(_QWORD *P)
{
  void *v2; // rcx

  if ( P )
  {
    v2 = (void *)P[2];
    if ( v2 )
      ExFreePoolWithTag(v2, 0x64667072u);
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
0x140002498  push    rbx
0x14000249a  sub     rsp, 20h
0x14000249e  mov     rbx, rcx
0x1400024a1  test    rcx, rcx
0x1400024a4  jnz     short loc_1400024AD
0x1400024a6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400024ab  jmp     short loc_1400024DB
0x1400024ad  mov     rcx, [rcx+10h]; P
0x1400024b1  test    rcx, rcx
0x1400024b4  jz      short loc_1400024C7
0x1400024b6  mov     edx, 64667072h; Tag
0x1400024bb  call    cs:__imp_ExFreePoolWithTag
0x1400024c2  nop     dword ptr [rax+rax+00h]
0x1400024c7  mov     edx, 64667072h; Tag
0x1400024cc  mov     rcx, rbx; P
0x1400024cf  call    cs:__imp_ExFreePoolWithTag
0x1400024d6  nop     dword ptr [rax+rax+00h]
0x1400024db  add     rsp, 20h
0x1400024df  pop     rbx
0x1400024e0  retn
```
