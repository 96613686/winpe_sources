# BaseSrvFreeVDMInfo

- ea: `0x18000a72c`
- end: `0x18000a88b`
- name: `BaseSrvFreeVDMInfo`
- size: `351`
- prototype: `BOOLEAN __fastcall(_QWORD *P)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800091dc`
- `0x18000a614`
- `0x18000a894`
- `0x18000a960`

## callees

- `0x18000a72c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a755`
- `ntdll!RtlFreeHeap` at `0x18000a779`
- `ntdll!RtlFreeHeap` at `0x18000a79d`
- `ntdll!RtlFreeHeap` at `0x18000a7c1`
- `ntdll!RtlFreeHeap` at `0x18000a7e8`
- `ntdll!RtlFreeHeap` at `0x18000a80f`
- `ntdll!RtlFreeHeap` at `0x18000a836`
- `ntdll!RtlFreeHeap` at `0x18000a85a`
- `ntdll!RtlFreeHeap` at `0x18000a878`
- `ntdll!RtlFreeHeap` at `0x18000a755`
- `ntdll!RtlFreeHeap` at `0x18000a779`
- `ntdll!RtlFreeHeap` at `0x18000a79d`
- `ntdll!RtlFreeHeap` at `0x18000a7c1`
- `ntdll!RtlFreeHeap` at `0x18000a7e8`
- `ntdll!RtlFreeHeap` at `0x18000a80f`
- `ntdll!RtlFreeHeap` at `0x18000a836`
- `ntdll!RtlFreeHeap` at `0x18000a85a`
- `ntdll!RtlFreeHeap` at `0x18000a878`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeVDMInfo(_QWORD *P)
{
  void *v1; // r8
  void *v3; // r8
  void *v4; // r8
  void *v5; // r8
  void *v6; // r8
  void *v7; // r8
  void *v8; // r8
  void *v9; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v1 = (void *)P[5];
    if ( v1 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    v3 = (void *)P[6];
    if ( v3 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    v4 = (void *)P[7];
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    v5 = (void *)P[9];
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    v6 = (void *)P[24];
    if ( v6 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    v7 = (void *)P[26];
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v8 = (void *)P[28];
    if ( v8 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    v9 = (void *)P[8];
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000a72c  test    rcx, rcx
0x18000a72f  jz      locret_18000A889
0x18000a735  push    rbx
0x18000a736  sub     rsp, 20h
0x18000a73a  mov     r8, [rcx+28h]; P
0x18000a73e  mov     rbx, rcx
0x18000a741  test    r8, r8
0x18000a744  jz      short loc_18000A761
0x18000a746  mov     rcx, gs:60h
0x18000a74f  xor     edx, edx; Flags
0x18000a751  mov     rcx, [rcx+30h]; HeapHandle
0x18000a755  call    cs:__imp_RtlFreeHeap
0x18000a75c  nop     dword ptr [rax+rax+00h]
0x18000a761  mov     r8, [rbx+30h]; P
0x18000a765  test    r8, r8
0x18000a768  jz      short loc_18000A785
0x18000a76a  mov     rcx, gs:60h
0x18000a773  xor     edx, edx; Flags
0x18000a775  mov     rcx, [rcx+30h]; HeapHandle
0x18000a779  call    cs:__imp_RtlFreeHeap
0x18000a780  nop     dword ptr [rax+rax+00h]
0x18000a785  mov     r8, [rbx+38h]; P
0x18000a789  test    r8, r8
0x18000a78c  jz      short loc_18000A7A9
0x18000a78e  mov     rcx, gs:60h
0x18000a797  xor     edx, edx; Flags
0x18000a799  mov     rcx, [rcx+30h]; HeapHandle
0x18000a79d  call    cs:__imp_RtlFreeHeap
0x18000a7a4  nop     dword ptr [rax+rax+00h]
0x18000a7a9  mov     r8, [rbx+48h]; P
0x18000a7ad  test    r8, r8
0x18000a7b0  jz      short loc_18000A7CD
0x18000a7b2  mov     rcx, gs:60h
0x18000a7bb  xor     edx, edx; Flags
0x18000a7bd  mov     rcx, [rcx+30h]; HeapHandle
0x18000a7c1  call    cs:__imp_RtlFreeHeap
0x18000a7c8  nop     dword ptr [rax+rax+00h]
0x18000a7cd  mov     r8, [rbx+0C0h]; P
0x18000a7d4  test    r8, r8
0x18000a7d7  jz      short loc_18000A7F4
0x18000a7d9  mov     rcx, gs:60h
0x18000a7e2  xor     edx, edx; Flags
0x18000a7e4  mov     rcx, [rcx+30h]; HeapHandle
0x18000a7e8  call    cs:__imp_RtlFreeHeap
0x18000a7ef  nop     dword ptr [rax+rax+00h]
0x18000a7f4  mov     r8, [rbx+0D0h]; P
0x18000a7fb  test    r8, r8
0x18000a7fe  jz      short loc_18000A81B
0x18000a800  mov     rcx, gs:60h
0x18000a809  xor     edx, edx; Flags
0x18000a80b  mov     rcx, [rcx+30h]; HeapHandle
0x18000a80f  call    cs:__imp_RtlFreeHeap
0x18000a816  nop     dword ptr [rax+rax+00h]
0x18000a81b  mov     r8, [rbx+0E0h]; P
0x18000a822  test    r8, r8
0x18000a825  jz      short loc_18000A842
0x18000a827  mov     rcx, gs:60h
0x18000a830  xor     edx, edx; Flags
0x18000a832  mov     rcx, [rcx+30h]; HeapHandle
0x18000a836  call    cs:__imp_RtlFreeHeap
0x18000a83d  nop     dword ptr [rax+rax+00h]
0x18000a842  mov     r8, [rbx+40h]; P
0x18000a846  test    r8, r8
0x18000a849  jz      short loc_18000A866
0x18000a84b  mov     rcx, gs:60h
0x18000a854  xor     edx, edx; Flags
0x18000a856  mov     rcx, [rcx+30h]; HeapHandle
0x18000a85a  call    cs:__imp_RtlFreeHeap
0x18000a861  nop     dword ptr [rax+rax+00h]
0x18000a866  mov     rcx, gs:60h
0x18000a86f  mov     r8, rbx; P
0x18000a872  xor     edx, edx; Flags
0x18000a874  mov     rcx, [rcx+30h]; HeapHandle
0x18000a878  call    cs:__imp_RtlFreeHeap
0x18000a87f  nop     dword ptr [rax+rax+00h]
0x18000a884  add     rsp, 20h
0x18000a888  pop     rbx
0x18000a889  retn
```
