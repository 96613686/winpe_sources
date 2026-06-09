# BaseSrvFreeConsoleRecord

- ea: `0x18000a54c`
- end: `0x18000a60d`
- name: `BaseSrvFreeConsoleRecord`
- size: `193`
- prototype: `void __fastcall(PVOID *P)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008644`
- `0x180009e9c`
- `0x18000a014`
- `0x18000c088`

## callees

- `0x18000a54c`
- `0x18000a614`

## import_xrefs

- `ntdll!NtClose` at `0x18000a59f`
- `ntdll!NtClose` at `0x18000a59f`
- `ntdll!RtlFreeHeap` at `0x18000a58a`
- `ntdll!RtlFreeHeap` at `0x18000a5fa`
- `ntdll!RtlFreeHeap` at `0x18000a58a`
- `ntdll!RtlFreeHeap` at `0x18000a5fa`

## pseudocode

```c
void __fastcall BaseSrvFreeConsoleRecord(PVOID *P)
{
  PVOID *i; // rcx
  PVOID v3; // r8
  PVOID v4; // rcx
  PVOID *v5; // rax
  PVOID *v6; // rcx
  PVOID v7; // rdx

  if ( P )
  {
    for ( i = (PVOID *)P[9]; i; i = (PVOID *)P[9] )
    {
      P[9] = *i;
      BaseSrvFreeDOSRecord(i);
    }
    v3 = P[8];
    if ( v3 )
      RtlFreeHeap(BaseSrvHeap, 0, v3);
    v4 = P[10];
    if ( v4 )
      NtClose(v4);
    v5 = (PVOID *)DOSHead;
    if ( DOSHead )
    {
      if ( DOSHead == P )
      {
        DOSHead = *P;
      }
      else
      {
        v6 = *(PVOID **)DOSHead;
        if ( *(_QWORD *)DOSHead )
        {
          while ( 1 )
          {
            v7 = *v6;
            if ( v6 == P )
              break;
            v5 = v6;
            v6 = (PVOID *)*v6;
            if ( !v7 )
              goto LABEL_17;
          }
          *v5 = v7;
        }
      }
    }
LABEL_17:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
}

```

## disassembly

```asm
0x18000a54c  test    rcx, rcx
0x18000a54f  jz      locret_18000A60B
0x18000a555  push    rbx
0x18000a556  sub     rsp, 20h
0x18000a55a  mov     rbx, rcx
0x18000a55d  mov     rcx, [rcx+48h]
0x18000a561  jmp     short loc_18000A573
0x18000a563  mov     rax, [rcx]
0x18000a566  mov     [rbx+48h], rax
0x18000a56a  call    BaseSrvFreeDOSRecord
0x18000a56f  mov     rcx, [rbx+48h]
0x18000a573  test    rcx, rcx
0x18000a576  jnz     short loc_18000A563
0x18000a578  mov     r8, [rbx+40h]; P
0x18000a57c  test    r8, r8
0x18000a57f  jz      short loc_18000A596
0x18000a581  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000a588  xor     edx, edx; Flags
0x18000a58a  call    cs:__imp_RtlFreeHeap
0x18000a591  nop     dword ptr [rax+rax+00h]
0x18000a596  mov     rcx, [rbx+50h]; Handle
0x18000a59a  test    rcx, rcx
0x18000a59d  jz      short loc_18000A5AB
0x18000a59f  call    cs:__imp_NtClose
0x18000a5a6  nop     dword ptr [rax+rax+00h]
0x18000a5ab  mov     rax, cs:DOSHead
0x18000a5b2  test    rax, rax
0x18000a5b5  jz      short loc_18000A5E8
0x18000a5b7  cmp     rax, rbx
0x18000a5ba  jnz     short loc_18000A5C8
0x18000a5bc  mov     rax, [rbx]
0x18000a5bf  mov     cs:DOSHead, rax
0x18000a5c6  jmp     short loc_18000A5E8
0x18000a5c8  mov     rcx, [rax]
0x18000a5cb  test    rcx, rcx
0x18000a5ce  jz      short loc_18000A5E8
0x18000a5d0  mov     rdx, [rcx]
0x18000a5d3  cmp     rcx, rbx
0x18000a5d6  jz      short loc_18000A5E5
0x18000a5d8  mov     rax, rcx
0x18000a5db  mov     rcx, rdx
0x18000a5de  test    rdx, rdx
0x18000a5e1  jnz     short loc_18000A5D0
0x18000a5e3  jmp     short loc_18000A5E8
0x18000a5e5  mov     [rax], rdx
0x18000a5e8  mov     rcx, gs:60h
0x18000a5f1  mov     r8, rbx; P
0x18000a5f4  xor     edx, edx; Flags
0x18000a5f6  mov     rcx, [rcx+30h]; HeapHandle
0x18000a5fa  call    cs:__imp_RtlFreeHeap
0x18000a601  nop     dword ptr [rax+rax+00h]
0x18000a606  add     rsp, 20h
0x18000a60a  pop     rbx
0x18000a60b  retn
```
