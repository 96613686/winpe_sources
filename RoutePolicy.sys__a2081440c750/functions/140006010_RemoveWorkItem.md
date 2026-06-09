# RemoveWorkItem

- ea: `0x140006010`
- end: `0x140006073`
- name: `RemoveWorkItem`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140002d00`
- `0x140007110`

## callees

- `0x140006010`
- `0x14000935c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006053`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006053`

## pseudocode

```c
void __fastcall RemoveWorkItem(__int64 a1)
{
  char *v2; // rdx
  char *i; // rcx
  char *v4; // rax
  char **v5; // rdx

  v2 = (char *)RoutePolicyCallout::g_pCalloutContext + 64;
  for ( i = (char *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 8); ; i = *(char **)i )
  {
    if ( i == v2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(i, v2, a1);
      return;
    }
    v4 = *(char **)i;
    if ( *((_QWORD *)i + 2) == a1 )
      break;
  }
  if ( *((char **)v4 + 1) != i || (v5 = (char **)*((_QWORD *)i + 1), *v5 != i) )
    __fastfail(3u);
  *v5 = v4;
  *((_QWORD *)v4 + 1) = v5;
  ExFreePoolWithTag(i, 0x64667072u);
}

```

## disassembly

```asm
0x140006010  sub     rsp, 28h
0x140006014  mov     rdx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x14000601b  mov     r8, rcx
0x14000601e  add     rdx, 40h ; '@'
0x140006022  mov     rcx, [rdx]; P
0x140006025  cmp     rcx, rdx
0x140006028  jz      short loc_140006068
0x14000602a  mov     rax, [rcx]
0x14000602d  cmp     [rcx+10h], r8
0x140006031  jz      short loc_140006038
0x140006033  mov     rcx, rax
0x140006036  jmp     short loc_140006025
0x140006038  cmp     [rax+8], rcx
0x14000603c  jnz     short loc_140006061
0x14000603e  mov     rdx, [rcx+8]
0x140006042  cmp     [rdx], rcx
0x140006045  jnz     short loc_140006061
0x140006047  mov     [rdx], rax
0x14000604a  mov     [rax+8], rdx
0x14000604e  mov     edx, 64667072h; Tag
0x140006053  call    cs:__imp_ExFreePoolWithTag
0x14000605a  nop     dword ptr [rax+rax+00h]
0x14000605f  jmp     short loc_14000606D
0x140006061  mov     ecx, 3
0x140006066  int     29h; Win8: RtlFailFast(ecx)
0x140006068  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000606d  add     rsp, 28h
0x140006071  retn
```
