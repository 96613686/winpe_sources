# AipFreeImageContext

- ea: `0x180006738`
- end: `0x1800068a2`
- name: `AipFreeImageContext`
- size: `362`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002b20`
- `0x180002ce0`
- `0x180002f30`

## callees

- `0x180006738`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006769`
- `ntdll!RtlFreeHeap` at `0x180006785`
- `ntdll!RtlFreeHeap` at `0x1800067af`
- `ntdll!RtlFreeHeap` at `0x1800067d8`
- `ntdll!RtlFreeHeap` at `0x1800067f1`
- `ntdll!RtlFreeHeap` at `0x18000680a`
- `ntdll!RtlFreeHeap` at `0x180006823`
- `ntdll!RtlFreeHeap` at `0x18000683c`
- `ntdll!RtlFreeHeap` at `0x180006858`
- `ntdll!RtlFreeHeap` at `0x180006874`
- `ntdll!RtlFreeHeap` at `0x18000688c`
- `ntdll!RtlFreeHeap` at `0x180006769`
- `ntdll!RtlFreeHeap` at `0x180006785`
- `ntdll!RtlFreeHeap` at `0x1800067af`
- `ntdll!RtlFreeHeap` at `0x1800067d8`
- `ntdll!RtlFreeHeap` at `0x1800067f1`
- `ntdll!RtlFreeHeap` at `0x18000680a`
- `ntdll!RtlFreeHeap` at `0x180006823`
- `ntdll!RtlFreeHeap` at `0x18000683c`
- `ntdll!RtlFreeHeap` at `0x180006858`
- `ntdll!RtlFreeHeap` at `0x180006874`
- `ntdll!RtlFreeHeap` at `0x18000688c`

## pseudocode

```c
BOOLEAN __fastcall AipFreeImageContext(PVOID *P)
{
  unsigned int i; // esi
  PVOID *v3; // r8
  BOOLEAN result; // al

  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[48]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[46]);
    for ( i = 0; i < *((_DWORD *)P + 23); ++i )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)P[13] + 2 * i + 1));
    v3 = (PVOID *)P[13];
    if ( v3 != P + 14 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[4]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[6]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[8]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[2]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[51]);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[54]);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x180006738  test    rcx, rcx
0x18000673b  jz      locret_1800068A1
0x180006741  mov     [rsp+arg_0], rbx
0x180006746  mov     [rsp+arg_8], rsi
0x18000674b  push    rdi
0x18000674c  sub     rsp, 20h
0x180006750  mov     rbx, rcx
0x180006753  xor     edx, edx; Flags
0x180006755  mov     rcx, gs:60h
0x18000675e  mov     r8, [rbx+180h]; P
0x180006765  mov     rcx, [rcx+30h]; HeapHandle
0x180006769  call    cs:__imp_RtlFreeHeap
0x18000676f  mov     rcx, gs:60h
0x180006778  xor     edx, edx; Flags
0x18000677a  mov     r8, [rbx+170h]; P
0x180006781  mov     rcx, [rcx+30h]; HeapHandle
0x180006785  call    cs:__imp_RtlFreeHeap
0x18000678b  xor     esi, esi
0x18000678d  cmp     [rbx+5Ch], esi
0x180006790  jbe     short loc_1800067BC
0x180006792  mov     rcx, gs:60h
0x18000679b  xor     edx, edx; Flags
0x18000679d  mov     r8, [rbx+68h]
0x1800067a1  mov     eax, esi
0x1800067a3  add     rax, rax
0x1800067a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800067aa  mov     r8, [r8+rax*8+8]; P
0x1800067af  call    cs:__imp_RtlFreeHeap
0x1800067b5  inc     esi
0x1800067b7  cmp     esi, [rbx+5Ch]
0x1800067ba  jb      short loc_180006792
0x1800067bc  mov     r8, [rbx+68h]; P
0x1800067c0  lea     rax, [rbx+70h]
0x1800067c4  cmp     r8, rax
0x1800067c7  jz      short loc_1800067DE
0x1800067c9  mov     rcx, gs:60h
0x1800067d2  xor     edx, edx; Flags
0x1800067d4  mov     rcx, [rcx+30h]; HeapHandle
0x1800067d8  call    cs:__imp_RtlFreeHeap
0x1800067de  mov     rcx, gs:60h
0x1800067e7  xor     edx, edx; Flags
0x1800067e9  mov     r8, [rbx+20h]; P
0x1800067ed  mov     rcx, [rcx+30h]; HeapHandle
0x1800067f1  call    cs:__imp_RtlFreeHeap
0x1800067f7  mov     rcx, gs:60h
0x180006800  xor     edx, edx; Flags
0x180006802  mov     r8, [rbx+30h]; P
0x180006806  mov     rcx, [rcx+30h]; HeapHandle
0x18000680a  call    cs:__imp_RtlFreeHeap
0x180006810  mov     rcx, gs:60h
0x180006819  xor     edx, edx; Flags
0x18000681b  mov     r8, [rbx+40h]; P
0x18000681f  mov     rcx, [rcx+30h]; HeapHandle
0x180006823  call    cs:__imp_RtlFreeHeap
0x180006829  mov     rcx, gs:60h
0x180006832  xor     edx, edx; Flags
0x180006834  mov     r8, [rbx+10h]; P
0x180006838  mov     rcx, [rcx+30h]; HeapHandle
0x18000683c  call    cs:__imp_RtlFreeHeap
0x180006842  mov     rcx, gs:60h
0x18000684b  xor     edx, edx; Flags
0x18000684d  mov     r8, [rbx+198h]; P
0x180006854  mov     rcx, [rcx+30h]; HeapHandle
0x180006858  call    cs:__imp_RtlFreeHeap
0x18000685e  mov     rcx, gs:60h
0x180006867  xor     edx, edx; Flags
0x180006869  mov     r8, [rbx+1B0h]; P
0x180006870  mov     rcx, [rcx+30h]; HeapHandle
0x180006874  call    cs:__imp_RtlFreeHeap
0x18000687a  mov     rcx, gs:60h
0x180006883  mov     r8, rbx; P
0x180006886  xor     edx, edx; Flags
0x180006888  mov     rcx, [rcx+30h]; HeapHandle
0x18000688c  call    cs:__imp_RtlFreeHeap
0x180006892  mov     rbx, [rsp+28h+arg_0]
0x180006897  mov     rsi, [rsp+28h+arg_8]
0x18000689c  add     rsp, 20h
0x1800068a0  pop     rdi
0x1800068a1  retn
```
