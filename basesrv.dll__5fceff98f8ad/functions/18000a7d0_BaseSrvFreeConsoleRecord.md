# BaseSrvFreeConsoleRecord

- ea: `0x18000a7d0`
- end: `0x18000a891`
- name: `BaseSrvFreeConsoleRecord`
- size: `193`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008938`
- `0x18000a194`
- `0x18000a2f8`
- `0x18000c434`

## callees

- `0x18000a7d0`
- `0x18000a898`

## import_xrefs

- `ntdll!NtClose` at `0x18000a823`
- `ntdll!NtClose` at `0x18000a823`
- `ntdll!RtlFreeHeap` at `0x18000a80e`
- `ntdll!RtlFreeHeap` at `0x18000a87e`
- `ntdll!RtlFreeHeap` at `0x18000a80e`
- `ntdll!RtlFreeHeap` at `0x18000a87e`

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
0x18000a7d0  test    rcx, rcx
0x18000a7d3  jz      locret_18000A88F
0x18000a7d9  push    rbx
0x18000a7da  sub     rsp, 20h
0x18000a7de  mov     rbx, rcx
0x18000a7e1  mov     rcx, [rcx+48h]
0x18000a7e5  jmp     short loc_18000A7F7
0x18000a7e7  mov     rax, [rcx]
0x18000a7ea  mov     [rbx+48h], rax
0x18000a7ee  call    BaseSrvFreeDOSRecord
0x18000a7f3  mov     rcx, [rbx+48h]
0x18000a7f7  test    rcx, rcx
0x18000a7fa  jnz     short loc_18000A7E7
0x18000a7fc  mov     r8, [rbx+40h]; P
0x18000a800  test    r8, r8
0x18000a803  jz      short loc_18000A81A
0x18000a805  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000a80c  xor     edx, edx; Flags
0x18000a80e  call    cs:__imp_RtlFreeHeap
0x18000a815  nop     dword ptr [rax+rax+00h]
0x18000a81a  mov     rcx, [rbx+50h]; Handle
0x18000a81e  test    rcx, rcx
0x18000a821  jz      short loc_18000A82F
0x18000a823  call    cs:__imp_NtClose
0x18000a82a  nop     dword ptr [rax+rax+00h]
0x18000a82f  mov     rax, cs:DOSHead
0x18000a836  test    rax, rax
0x18000a839  jz      short loc_18000A86C
0x18000a83b  cmp     rax, rbx
0x18000a83e  jnz     short loc_18000A84C
0x18000a840  mov     rax, [rbx]
0x18000a843  mov     cs:DOSHead, rax
0x18000a84a  jmp     short loc_18000A86C
0x18000a84c  mov     rcx, [rax]
0x18000a84f  test    rcx, rcx
0x18000a852  jz      short loc_18000A86C
0x18000a854  mov     rdx, [rcx]
0x18000a857  cmp     rcx, rbx
0x18000a85a  jz      short loc_18000A869
0x18000a85c  mov     rax, rcx
0x18000a85f  mov     rcx, rdx
0x18000a862  test    rdx, rdx
0x18000a865  jnz     short loc_18000A854
0x18000a867  jmp     short loc_18000A86C
0x18000a869  mov     [rax], rdx
0x18000a86c  mov     rcx, gs:60h
0x18000a875  mov     r8, rbx; P
0x18000a878  xor     edx, edx; Flags
0x18000a87a  mov     rcx, [rcx+30h]; HeapHandle
0x18000a87e  call    cs:__imp_RtlFreeHeap
0x18000a885  nop     dword ptr [rax+rax+00h]
0x18000a88a  add     rsp, 20h
0x18000a88e  pop     rbx
0x18000a88f  retn
```
