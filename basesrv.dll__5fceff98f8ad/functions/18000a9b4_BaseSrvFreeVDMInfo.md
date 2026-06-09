# BaseSrvFreeVDMInfo

- ea: `0x18000a9b4`
- end: `0x18000ab13`
- name: `BaseSrvFreeVDMInfo`
- size: `351`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800094cc`
- `0x18000a898`
- `0x18000ab1c`
- `0x18000abe0`

## callees

- `0x18000a9b4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a9dd`
- `ntdll!RtlFreeHeap` at `0x18000aa01`
- `ntdll!RtlFreeHeap` at `0x18000aa25`
- `ntdll!RtlFreeHeap` at `0x18000aa49`
- `ntdll!RtlFreeHeap` at `0x18000aa70`
- `ntdll!RtlFreeHeap` at `0x18000aa97`
- `ntdll!RtlFreeHeap` at `0x18000aabe`
- `ntdll!RtlFreeHeap` at `0x18000aae2`
- `ntdll!RtlFreeHeap` at `0x18000ab00`
- `ntdll!RtlFreeHeap` at `0x18000a9dd`
- `ntdll!RtlFreeHeap` at `0x18000aa01`
- `ntdll!RtlFreeHeap` at `0x18000aa25`
- `ntdll!RtlFreeHeap` at `0x18000aa49`
- `ntdll!RtlFreeHeap` at `0x18000aa70`
- `ntdll!RtlFreeHeap` at `0x18000aa97`
- `ntdll!RtlFreeHeap` at `0x18000aabe`
- `ntdll!RtlFreeHeap` at `0x18000aae2`
- `ntdll!RtlFreeHeap` at `0x18000ab00`

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
0x18000a9b4  test    rcx, rcx
0x18000a9b7  jz      locret_18000AB11
0x18000a9bd  push    rbx
0x18000a9be  sub     rsp, 20h
0x18000a9c2  mov     r8, [rcx+28h]; P
0x18000a9c6  mov     rbx, rcx
0x18000a9c9  test    r8, r8
0x18000a9cc  jz      short loc_18000A9E9
0x18000a9ce  mov     rcx, gs:60h
0x18000a9d7  xor     edx, edx; Flags
0x18000a9d9  mov     rcx, [rcx+30h]; HeapHandle
0x18000a9dd  call    cs:__imp_RtlFreeHeap
0x18000a9e4  nop     dword ptr [rax+rax+00h]
0x18000a9e9  mov     r8, [rbx+30h]; P
0x18000a9ed  test    r8, r8
0x18000a9f0  jz      short loc_18000AA0D
0x18000a9f2  mov     rcx, gs:60h
0x18000a9fb  xor     edx, edx; Flags
0x18000a9fd  mov     rcx, [rcx+30h]; HeapHandle
0x18000aa01  call    cs:__imp_RtlFreeHeap
0x18000aa08  nop     dword ptr [rax+rax+00h]
0x18000aa0d  mov     r8, [rbx+38h]; P
0x18000aa11  test    r8, r8
0x18000aa14  jz      short loc_18000AA31
0x18000aa16  mov     rcx, gs:60h
0x18000aa1f  xor     edx, edx; Flags
0x18000aa21  mov     rcx, [rcx+30h]; HeapHandle
0x18000aa25  call    cs:__imp_RtlFreeHeap
0x18000aa2c  nop     dword ptr [rax+rax+00h]
0x18000aa31  mov     r8, [rbx+48h]; P
0x18000aa35  test    r8, r8
0x18000aa38  jz      short loc_18000AA55
0x18000aa3a  mov     rcx, gs:60h
0x18000aa43  xor     edx, edx; Flags
0x18000aa45  mov     rcx, [rcx+30h]; HeapHandle
0x18000aa49  call    cs:__imp_RtlFreeHeap
0x18000aa50  nop     dword ptr [rax+rax+00h]
0x18000aa55  mov     r8, [rbx+0C0h]; P
0x18000aa5c  test    r8, r8
0x18000aa5f  jz      short loc_18000AA7C
0x18000aa61  mov     rcx, gs:60h
0x18000aa6a  xor     edx, edx; Flags
0x18000aa6c  mov     rcx, [rcx+30h]; HeapHandle
0x18000aa70  call    cs:__imp_RtlFreeHeap
0x18000aa77  nop     dword ptr [rax+rax+00h]
0x18000aa7c  mov     r8, [rbx+0D0h]; P
0x18000aa83  test    r8, r8
0x18000aa86  jz      short loc_18000AAA3
0x18000aa88  mov     rcx, gs:60h
0x18000aa91  xor     edx, edx; Flags
0x18000aa93  mov     rcx, [rcx+30h]; HeapHandle
0x18000aa97  call    cs:__imp_RtlFreeHeap
0x18000aa9e  nop     dword ptr [rax+rax+00h]
0x18000aaa3  mov     r8, [rbx+0E0h]; P
0x18000aaaa  test    r8, r8
0x18000aaad  jz      short loc_18000AACA
0x18000aaaf  mov     rcx, gs:60h
0x18000aab8  xor     edx, edx; Flags
0x18000aaba  mov     rcx, [rcx+30h]; HeapHandle
0x18000aabe  call    cs:__imp_RtlFreeHeap
0x18000aac5  nop     dword ptr [rax+rax+00h]
0x18000aaca  mov     r8, [rbx+40h]; P
0x18000aace  test    r8, r8
0x18000aad1  jz      short loc_18000AAEE
0x18000aad3  mov     rcx, gs:60h
0x18000aadc  xor     edx, edx; Flags
0x18000aade  mov     rcx, [rcx+30h]; HeapHandle
0x18000aae2  call    cs:__imp_RtlFreeHeap
0x18000aae9  nop     dword ptr [rax+rax+00h]
0x18000aaee  mov     rcx, gs:60h
0x18000aaf7  mov     r8, rbx; P
0x18000aafa  xor     edx, edx; Flags
0x18000aafc  mov     rcx, [rcx+30h]; HeapHandle
0x18000ab00  call    cs:__imp_RtlFreeHeap
0x18000ab07  nop     dword ptr [rax+rax+00h]
0x18000ab0c  add     rsp, 20h
0x18000ab10  pop     rbx
0x18000ab11  retn
```
