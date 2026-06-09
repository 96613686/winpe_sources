# BaseSrvRemoveWOWRecordByTaskId

- ea: `0x18000c16c`
- end: `0x18000c1f3`
- name: `BaseSrvRemoveWOWRecordByTaskId`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000a388`

## callees

- `0x18000ab1c`
- `0x18000c16c`

## import_xrefs

- `ntdll!NtClose` at `0x18000c1c7`
- `ntdll!NtClose` at `0x18000c1c7`
- `ntdll!NtSetEvent` at `0x18000c1b7`
- `ntdll!NtSetEvent` at `0x18000c1b7`

## pseudocode

```c
__int64 __fastcall BaseSrvRemoveWOWRecordByTaskId(__int64 a1, int a2)
{
  void *v4; // rbx
  _QWORD *v5; // rdx
  __int64 v6; // rax
  void *v7; // rcx

  if ( !a1 )
    return 3221225485LL;
  v4 = *(void **)(a1 + 56);
  v5 = 0;
  while ( 1 )
  {
    if ( !v4 )
      return 3221226021LL;
    v6 = *((_QWORD *)v4 + 4);
    if ( *(_DWORD *)v4 == a2 )
      break;
    v5 = v4;
    v4 = (void *)*((_QWORD *)v4 + 4);
  }
  if ( v5 )
    v5[4] = v6;
  else
    *(_QWORD *)(a1 + 56) = v6;
  v7 = (void *)*((_QWORD *)v4 + 1);
  if ( v7 )
  {
    NtSetEvent(v7, 0);
    NtClose(*((HANDLE *)v4 + 1));
    *((_QWORD *)v4 + 1) = 0;
  }
  BaseSrvFreeWOWRecord(v4);
  return 0;
}

```

## disassembly

```asm
0x18000c16c  push    rbx
0x18000c16e  sub     rsp, 20h
0x18000c172  mov     r8d, edx
0x18000c175  test    rcx, rcx
0x18000c178  jnz     short loc_18000C181
0x18000c17a  mov     eax, 0C000000Dh
0x18000c17f  jmp     short loc_18000C1EC
0x18000c181  mov     rbx, [rcx+38h]
0x18000c185  xor     edx, edx
0x18000c187  test    rbx, rbx
0x18000c18a  jz      short loc_18000C1E7
0x18000c18c  mov     rax, [rbx+20h]
0x18000c190  cmp     [rbx], r8d
0x18000c193  jz      short loc_18000C19D
0x18000c195  mov     rdx, rbx
0x18000c198  mov     rbx, rax
0x18000c19b  jmp     short loc_18000C187
0x18000c19d  test    rdx, rdx
0x18000c1a0  jnz     short loc_18000C1A8
0x18000c1a2  mov     [rcx+38h], rax
0x18000c1a6  jmp     short loc_18000C1AC
0x18000c1a8  mov     [rdx+20h], rax
0x18000c1ac  mov     rcx, [rbx+8]; EventHandle
0x18000c1b0  test    rcx, rcx
0x18000c1b3  jz      short loc_18000C1DB
0x18000c1b5  xor     edx, edx; PreviousState
0x18000c1b7  call    cs:__imp_NtSetEvent
0x18000c1be  nop     dword ptr [rax+rax+00h]
0x18000c1c3  mov     rcx, [rbx+8]; Handle
0x18000c1c7  call    cs:__imp_NtClose
0x18000c1ce  nop     dword ptr [rax+rax+00h]
0x18000c1d3  mov     qword ptr [rbx+8], 0
0x18000c1db  mov     rcx, rbx; P
0x18000c1de  call    BaseSrvFreeWOWRecord
0x18000c1e3  xor     eax, eax
0x18000c1e5  jmp     short loc_18000C1EC
0x18000c1e7  mov     eax, 0C0000225h
0x18000c1ec  add     rsp, 20h
0x18000c1f0  pop     rbx
0x18000c1f1  retn
```
